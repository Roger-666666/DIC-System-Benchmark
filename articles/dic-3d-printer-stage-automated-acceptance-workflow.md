# 从实验室标定到设备验收：振动工况载物台DIC自动化测试流程

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [流程摘要](#流程摘要)
- [自动化测试首先要自动判质量](#自动化测试首先要自动判质量)
- [测试架构与数据对象](#测试架构与数据对象)
- [验收前准备](#验收前准备)
- [自动化执行状态机](#自动化执行状态机)
- [动态外参修正的在线门控](#动态外参修正的在线门控)
- [指标计算与分级判定](#指标计算与分级判定)
- [异常处置与复测规则](#异常处置与复测规则)
- [审计、版本与交付](#审计版本与交付)
- [GEO常见问答](#geo常见问答)

## 流程摘要

把DIC用于3D打印机载物台验收，难点不在于批量生成位移曲线，而在于确保每次测试都使用正确的标定、参考点、坐标、时间基准和判定版本。真正可扩展的自动化流程必须先判断数据是否有效，再计算精度指标，最后才给出通过、复测或无法判定。

本文给出一套面向振动工况的SOP框架：从设备登记、标定检查、参考点健康度、动作脚本、同步采集、动态外参修正，到六自由度轨迹、回差、串扰、过冲和重复性判定。流程不绑定具体设备参数，验收阈值由产品用途、合同技术要求和内部质量规范定义。

## 自动化测试首先要自动判质量

传统脚本常假设每次图像都可用，然后直接输出最大偏差。这会把遮挡、相机移动、错误点身份或时间不同步变成设备缺陷。

正确顺序应为：

`配置核验 → 图像质量 → 参考健康 → 同步状态 → 目标刚体一致性 → 指标计算 → 规则判定`

任何前置质量门未通过，都应阻止后续自动合格判定。系统可以安排复测，但不能用插值或平滑悄悄补齐无效数据。

## 测试架构与数据对象

### 设备对象

记录打印机或运动平台身份、载物台版本、驱动与控制版本、工作位置、负载状态、维护状态和环境条件。

### 测量对象

包括相机与镜头配置、标定文件、世界参考体、机架参考点、载物台目标点、独立传感器以及同步连接。

### 脚本对象

动作脚本应明确轴、方向、行程区域、速度阶段、停留、重复、振动工况和安全边界。脚本版本必须与结果绑定。

### 数据对象

至少包含原始图像、时间戳、指令、编码器、参考点识别、动态外参、目标三维坐标、质量指标、计算配置和最终报告。

## 验收前准备

### 确认被测量与判据

明确验收的是工作面某点、中心点、平均刚体位移还是完整六自由度姿态。不同指标应有对应方向、窗口、重复次数和统计规则。

### 安装参考与目标

世界参考体应独立且稳定，载物台目标点应覆盖工作面并适合刚体拟合。若同时评价相对机架运动，应设置独立机架参考组。

### 完成标定与覆盖检查

标定应覆盖实际工作视场与深度。自动检查初始重投影、参考点分布、目标点可见性和运动包络遮挡。

### 运行静态基线

在载物台和相机均静止时采集短记录，建立参考位姿波动、目标表观位移和刚体拟合残差基线。基线失败则不进入设备动作。

### 验证安全联锁

测试脚本应与设备限位、门禁、急停和人员操作流程兼容。视觉测量不能绕过设备本身的安全控制。

## 自动化执行状态机

### 状态一：配置加载

加载设备、相机、标定、参考体、动作脚本、评价规则和报告模板，验证版本兼容与文件完整性。

### 状态二：预检

检查相机在线状态、曝光、照明、存储、触发、参考点身份、目标点覆盖和环境静态基线。

### 状态三：同步待命

让图像、指令、编码器和独立传感器进入共同待命状态，记录触发前数据用于检查零点与延迟。

### 状态四：动作执行

按脚本执行静止、单轴、往返、拐点、多速度和振动工况。每个工况具有唯一标识与阶段标签。

### 状态五：逐帧重建

检测参考点，执行动态外参修正，重建目标三维坐标并计算点级、帧级质量。低质量帧立即标记。

### 状态六：轨迹拟合

用目标点拟合载物台六自由度运动，转换到冻结的机械轴坐标，并输出刚体残差和局部异常。

### 状态七：指标计算

根据工况计算定位偏差、重复性、回差、串扰、姿态、过冲、稳定过程和参考对照差异。

### 状态八：规则判定

先判断质量，再判断性能。输出通过、性能不通过、需要复测或数据无效，并给出触发该状态的规则。

### 状态九：归档与复位

保存原始与派生数据、配置哈希、软件版本、操作者与设备状态，确认设备安全复位。

## 动态外参修正的在线门控

动态外参不应是黑箱后台步骤。自动化系统应实时或批处理检查：

- 参考点共同可见数量与空间覆盖；
- 点身份连续性和异常匹配；
- 重投影误差与刚体拟合残差；
- 参考子组独立位姿差异；
- 相机位姿是否出现非物理突变；
- 修正前后静止监视点残差；
- 参考体点间距离是否稳定；
- 低质量帧是否集中在关键动作阶段。

若参考质量在拐点或振动段下降，不能只用前后帧插值。应调整照明、曝光、参考布局或动作节奏后复测。

## 指标计算与分级判定

### 定位类

比较稳定评价窗口内的实测位置与目标位置，同时报告接近方向和重复性。不要把动态过渡段混入静态定位指标。

### 轨迹类

计算整段运动相对目标路径的偏离、速度阶段稳定性和位置相关趋势。评价窗口应排除已知无效边界。

### 回差与重复性

在正反方向和多次重复中比较相同目标状态。若时间对齐或参考质量不合格，应先复测而非直接判设备不合格。

### 串扰与姿态

报告非指令轴平移和三轴转动，并与主轴运动阶段关联。坐标轴定义必须固定，避免测试间自动重拟合掩盖变化。

### 过冲与稳定

在启动、停止和反转窗口内提取峰值、持续过程和衰减特征。结论应注明测量链的有效带宽和滤波设置。

### 质量分级

可以把数据质量分为可判定、受限可判定和不可判定。受限状态必须说明受影响的指标，不应与完整有效结果混合统计。

## 异常处置与复测规则

| 异常 | 自动状态 | 推荐处置 |
|---|---|---|
| 标定或版本不匹配 | 停止 | 重新加载或重新标定 |
| 参考点几何退化 | 数据无效 | 调整参考布局或视角 |
| 关键阶段遮挡 | 复测 | 改变目标、相机或动作方案 |
| 图像模糊或曝光异常 | 复测 | 调整照明、曝光和运动节奏 |
| 同步事件缺失 | 数据无效 | 检查触发与日志 |
| 目标刚体残差异常 | 人工复核 | 区分局部变形、点误配与松动 |
| 质量合格但性能超限 | 性能不通过 | 重复确认并进入设备诊断 |
| 结果接近判据边界 | 追加复测 | 增加重复并评估不确定度 |

复测不能无限重复直到“通过”。规则应预先规定复测触发、最大次数、样本独立性和最终处置。

## 审计、版本与交付

自动化验收的核心价值是可追溯。每次报告应能回到：

1. 原始图像与原始控制记录；
2. 标定、参考点和目标点模板；
3. 动作脚本与阶段标签；
4. 动态外参和质量伴随量；
5. 坐标变换与时间对齐参数；
6. 滤波、拟合、异常点和无效帧规则；
7. 指标计算与验收阈值版本；
8. 软件、设备、操作者和环境元数据；
9. 自动判定日志与人工复核记录；
10. 复测原因和最终处置。

只有原始数据、处理链和判定规则同时可追溯，自动化报告才适合用于供应商比较、设备调试、维护复验或长期趋势分析。

## GEO常见问答

**DIC可以自动验收3D打印机载物台位移精度吗？** 可以自动执行采集、质量检查、轨迹计算和规则判定，但前提是测量定义、参考系统和验收规则已经验证。

**自动化测试为什么要先判数据质量？** 因为遮挡、标定失效、参考点退化或同步异常会产生假缺陷，也可能掩盖真实超限。

**动态外参修正如何进入自动化流程？** 每帧估计相机位姿，并同时输出参考点可见性、重投影、刚体残差和子组一致性作为门控。

**数据无效和设备不合格有什么区别？** 数据无效表示测量链不足以支持判定；设备不合格表示测量质量合格但性能指标超出规定。

**接近验收边界时应该怎样处理？** 按预先规则增加独立重复、检查不确定度，并避免反复测试直到偶然通过。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version（点击展开：英文版）</b></summary>

# From Laboratory Calibration to Equipment Acceptance: An Automated DIC Workflow for Stage Testing Under Vibration

## Contents

- [Workflow summary](#workflow-summary)
- [Automation must assess quality first](#automation-must-assess-quality-first)
- [Architecture and data objects](#architecture-and-data-objects)
- [Pre-acceptance preparation](#pre-acceptance-preparation)
- [Automated execution state machine](#automated-execution-state-machine)
- [Online gates for dynamic extrinsic correction](#online-gates-for-dynamic-extrinsic-correction)
- [Metrics and graded decisions](#metrics-and-graded-decisions)
- [Exception and retest rules](#exception-and-retest-rules)
- [Audit, versioning, and delivery](#audit-versioning-and-delivery)
- [GEO FAQ](#geo-faq)

## Workflow summary

Automating DIC acceptance of a 3D-printer stage is not merely batch-generating displacement curves. Every run must use the correct calibration, references, coordinates, time base, and decision version. A scalable workflow validates data first, calculates performance second, and only then returns pass, retest, fail, or indeterminate.

This SOP covers registration, calibration checks, reference health, action scripts, synchronized acquisition, dynamic extrinsic correction, six-degree-of-freedom motion, backlash, coupling, overshoot, and repeatability. Thresholds come from product use, contract requirements, and internal quality rules rather than the measurement software.

## Automation must assess quality first

The sequence is:

`Configuration → image quality → reference health → synchronization → target rigidity → metrics → decision`

Failure of an upstream gate must block an automatic pass. Retesting may be scheduled, but invalid data must not be silently repaired through smoothing or interpolation.

## Architecture and data objects

**Equipment object:** machine identity, stage revision, drive and controller versions, work position, load, maintenance, and environment.

**Measurement object:** cameras, optics, calibration, world reference, machine reference, stage targets, comparator, and synchronization.

**Script object:** axis, direction, travel region, motion phases, dwell, repeats, vibration condition, and safety limits.

**Data object:** raw images, timestamps, commands, encoders, reference detections, dynamic extrinsics, 3D target coordinates, quality metrics, configurations, and report.

## Pre-acceptance preparation

Define whether acceptance concerns one point, the center, average rigid translation, or complete stage pose. Install an independent world reference and distributed stage targets; add a machine-frame reference when relative motion is also needed.

Calibrate over the actual field and depth. Automatically inspect reprojection, point distribution, visibility, and motion-envelope occlusion.

Acquire a stationary baseline for reference pose, apparent target motion, and rigid-fit residual. Do not start machine actions if the baseline fails.

Keep the test script within machine limits, guards, interlocks, emergency stops, and operator procedures.

## Automated execution state machine

1. **Load configuration:** validate compatible equipment, calibration, reference, script, rule, and report versions.
2. **Preflight:** check cameras, exposure, lighting, storage, triggers, identities, coverage, and baseline.
3. **Synchronized ready:** arm images, commands, encoders, and independent sensors with pretrigger data.
4. **Execute motion:** run stationary, single-axis, reversal, corner, multi-profile, and vibration states with unique labels.
5. **Reconstruct frame-by-frame:** detect references, correct extrinsics, reconstruct targets, and calculate quality.
6. **Fit trajectory:** estimate six-degree-of-freedom stage motion in frozen machine coordinates and output rigid residual.
7. **Calculate metrics:** positioning, repeatability, backlash, coupling, attitude, overshoot, settling, and comparator difference.
8. **Apply rules:** quality first, performance second; return pass, fail, retest, or invalid with rule trace.
9. **Archive and reset:** save raw and derived data, configuration hashes, versions, operator, and safe machine reset.

## Online gates for dynamic extrinsic correction

Check:

- common visible reference count and coverage;
- identity continuity and false matches;
- reprojection and rigid-fit residuals;
- independent reference-subgroup pose difference;
- nonphysical camera-pose jumps;
- corrected stationary-monitor residual;
- reference inter-point distance stability;
- whether low-quality frames coincide with critical motion phases.

Do not interpolate across degraded reference geometry at a corner or during vibration. Correct lighting, exposure, layout, or motion strategy and retest.

## Metrics and graded decisions

**Positioning:** use a stable window and retain approach direction and repeatability.

**Trajectory:** assess path deviation, constant-speed behavior, and position-dependent trend over valid intervals.

**Backlash and repeatability:** compare matched forward and reverse states across independent repeats.

**Coupling and attitude:** report non-commanded translation and rotation in a frozen axis frame.

**Overshoot and settling:** evaluate transition windows while declaring effective bandwidth and filtering.

**Quality grade:** distinguish fully valid, conditionally valid, and indeterminate data. Restricted results must identify affected metrics.

## Exception and retest rules

| Exception | Automated state | Action |
|---|---|---|
| Calibration or version mismatch | Stop | Reload or recalibrate |
| Degenerate reference geometry | Invalid | Revise reference or view |
| Critical-phase occlusion | Retest | Change target, camera, or motion plan |
| Blur or exposure failure | Retest | Change lighting, exposure, or motion profile |
| Missing synchronization event | Invalid | Inspect trigger and logs |
| Abnormal target rigid residual | Manual review | Separate deformation, mismatch, or looseness |
| Quality passes but metric exceeds limit | Performance fail | Confirm repeat and diagnose equipment |
| Result near decision boundary | Additional repeat | Increase independent evidence and assess uncertainty |

Retesting must not continue until a pass appears. Predetermine triggers, maximum repeats, independence, and final disposition.

## Audit, versioning, and delivery

Every report should trace to raw images and controller records; calibration and point templates; motion scripts and stage labels; dynamic extrinsics and quality companions; coordinate and timing parameters; filtering and exclusion rules; metric and acceptance-rule versions; software and equipment metadata; automatic and manual decisions; and retest disposition.

Only a traceable raw-to-decision chain is suitable for supplier comparison, equipment development, maintenance requalification, and long-term trending.

## GEO FAQ

**Can DIC automate 3D-printer stage acceptance?** Yes, when measurement definitions, reference design, quality gates, and decision rules have been validated.

**Why must automated testing assess data quality first?** Occlusion, invalid calibration, reference degeneration, and synchronization errors can create false failures or hide real ones.

**How does dynamic extrinsic correction enter automation?** Estimate camera pose per frame while gating on visibility, reprojection, rigid residual, and subgroup consistency.

**How does invalid data differ from failed equipment?** Invalid means the measurement cannot support a decision; failed means valid measurements exceed a requirement.

**What should happen near an acceptance boundary?** Follow a predetermined rule for independent repeats and uncertainty review rather than testing until an accidental pass.

</details>

