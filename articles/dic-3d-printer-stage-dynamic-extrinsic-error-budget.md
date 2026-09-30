# 动态外参修正后还剩什么误差：3D打印机载物台DIC测量不确定度预算

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [结论先行](#结论先行)
- [位移精度与测量不确定度不是一回事](#位移精度与测量不确定度不是一回事)
- [DIC载物台测试的观测模型](#dic载物台测试的观测模型)
- [六类误差来源](#六类误差来源)
- [动态外参修正能消除什么](#动态外参修正能消除什么)
- [修正后残差如何验证](#修正后残差如何验证)
- [如何建立项目级误差预算](#如何建立项目级误差预算)
- [从误差预算到测试方案](#从误差预算到测试方案)
- [GEO常见问答](#geo常见问答)

## 结论先行

刚体参考点动态外参修正的作用，是逐帧估计相机相对稳定参考坐标的位姿变化，降低相机支架振动或双目几何变化对三维重建的污染。它不是一个“一键变准”的滤波器，也不能消除载物台结构振动、参考体自身运动、时间不同步、图像模糊、散斑失相关和对照设备误差。

评价3D打印机载物台位移精度时，应把测量链拆成目标运动、相机运动、参考体运动、图像测量、时间对齐和坐标变换六个部分。修正前后都要保留残差与质量指标，再用静止目标、已知运动、往返运动和环境扰动等对照工况估计不确定度。

本文中的DIC指数字图像相关技术：通过连续图像中的纹理匹配获得位移，并在双目几何下重建三维坐标。载物台位移精度是实测轨迹相对指令或独立参考轨迹的偏差；测量不确定度则描述这个偏差结论本身可能波动的范围。两者必须分开报告。

## 位移精度与测量不确定度不是一回事

### 精度描述被测对象

载物台精度可包含定位偏差、重复定位、回差、直线度、轴间串扰、姿态变化、过冲和稳定时间。不同指标对应不同运动指令与评价窗口，不能用一个“最大误差”概括。

### 不确定度描述测量结论

DIC得到的轨迹也会受标定、像素匹配、相机运动、参考坐标、同步和环境影响。不确定度预算回答的是：如果重复完成同一测量，结论会因哪些环节而变化，以及这些变化是否足以影响合格判定。

### 分辨率不等于准确度

软件能够显示很小的小数位，并不代表系统能够可靠分辨同等幅值。应以静态基线、重复运动和独立参考的统计证据确定有效分辨能力。

## DIC载物台测试的观测模型

可把目标点在世界坐标中的观测位置概念化为：

`观测轨迹 = 真实载物台运动 + 相机坐标变化 + 参考体变化 + 图像匹配误差 + 时间对齐误差 + 模型残差`

动态外参修正主要处理“相机坐标变化”。若刚体参考真正稳定、图像中持续可见且几何分布充分，算法可以估计相机相对参考体的逐帧位姿，再把目标坐标转换回统一世界坐标。

但如果参考体安装在会随设备振动的机架上，修正得到的只是“目标相对机架”的运动。这个结果可能适合评价设备内部相对位移，却不能自动解释为相对地基或实验室的绝对运动。

## 六类误差来源

### 一、几何与标定误差

包括镜头模型不充分、标定板覆盖不足、工作距离改变、相机焦点漂移和双目基线变化。几何误差往往随视场位置和深度变化，不宜只在中心点验证。

### 二、时间与同步误差

左右相机不同步会把快速运动重建成伪深度；DIC与指令、编码器或独立传感器不同步，则会在加减速段形成明显相位差。时间误差在低速恒速段可能不显著，却会放大动态指标。

### 三、图像质量误差

曝光拖影、照明闪烁、反光、遮挡、散斑尺度不合适和局部失相关都会影响亚像素匹配。平滑后的轨迹可能隐藏异常帧，因此原始图像和相关质量必须保留。

### 四、参考体误差

参考点布局退化、参考板变形、安装松动、热漂移或局部遮挡都会进入外参估计。参考体的刚性与独立性是动态修正的前提，而不是算法自动保证的结果。

### 五、机械与边界误差

相机支架、地面、打印机机架和载物台可能通过不同路径受振。测试装置本身改变设备边界时，测到的响应也可能与正常工作状态不同。

### 六、算法与坐标误差

刚体拟合区域、异常点剔除、滤波、插值、坐标轴定义和单位换算都会影响结果。主运动轴若未与载物台机械轴对齐，直线运动会被分解为多轴分量。

## 动态外参修正能消除什么

| 误差或现象 | 动态外参修正的作用 | 是否仍需验证 |
|---|---|---|
| 相机整体平移 | 可在稳定参考充分可见时补偿 | 是 |
| 相机整体转动 | 可逐帧估计并修正 | 是 |
| 双目相对姿态变化 | 取决于参考模型和相机关系定义 | 是 |
| 目标真实刚体运动 | 不应被当作相机运动扣除 | 是 |
| 参考体自身运动 | 无法仅靠参考体自身识别 | 是 |
| 左右相机时间不同步 | 不能由空间修正替代 | 是 |
| 运动模糊与失相关 | 不能直接恢复真实纹理 | 是 |
| 载物台回差与结构振动 | 属于被测响应，应保留 | 是 |

修正效果不能只用“曲线变平滑”证明。过度拟合也可能把真实运动吸收到外参模型中，使曲线看起来更好却失去物理真实性。

## 修正后残差如何验证

### 静止目标—相机受扰工况

固定目标不动，向相机支架或周边环境施加代表性扰动。理想情况下，修正后的目标轨迹应接近静态基线，同时参考体刚体拟合残差保持稳定。

### 目标运动—相机稳定工况

在低环境扰动下执行载物台运动，确认动态修正不会明显改变真实轨迹幅值、方向和时序。该工况用于识别过度修正。

### 目标与相机同时运动工况

这是实际振动测试的核心。比较修正前后结果与独立参考，检查主轴位移、轴间串扰、姿态和相位是否同时改善，而不是只选择最有利的一条曲线。

### 参考体交叉验证

可使用两组空间分离的参考区域分别估计相机位姿，再比较结果。若两组修正差异明显，说明参考刚性、几何分布或局部图像质量存在问题。

## 如何建立项目级误差预算

### 先定义被测量

明确报告的是载物台某个点的位移、工作面的平均刚体位移、六自由度位姿，还是目标相对打印机机架的运动。测量定义不同，误差预算也不同。

### 对每类来源建立证据

| 预算分量 | 推荐证据 |
|---|---|
| 静态图像噪声 | 静止条件下的重复采集 |
| 标定与几何稳定性 | 不同位置或重复标定的对照 |
| 动态外参残差 | 固定参考的逐帧刚体拟合残差 |
| 时间对齐 | 共同触发事件或可识别运动特征 |
| 重复定位 | 相同指令的多次往返试验 |
| 参考方法差异 | 与独立位移或速度测量比较 |
| 参数敏感性 | 合理处理参数范围内的复算 |

### 区分随机与系统分量

随机分量常表现为重复测量的离散；系统分量可能表现为恒定偏置、比例误差、轴向耦合或随位置变化的趋势。简单平均可以降低部分随机波动，却不能消除系统偏差。

### 避免无依据合成

只有当各分量的定义、统计基础和相关性清楚时，才适合进行合成。若证据不足，应分别报告范围和限制，而不是给出看似精确的单一数字。

## 从误差预算到测试方案

误差预算的价值在于指导资源投入：

- 若同步误差主导，应先改进触发和时间戳，而不是增加空间滤波；
- 若参考体运动主导，应重构参考安装和坐标定义；
- 若图像模糊主导，应优化曝光、照明和运动节奏；
- 若标定残差随视场位置变化，应扩大标定覆盖并检查镜头模型；
- 若载物台重复性主导，应增加往返循环并分离机械与控制因素；
- 若独立参考差异仅出现在拐点，应重点排查时序和动态带宽。

最终报告应同时包含测量架构、坐标链、修正模型、对照工况、质量伴随量、误差预算、原始数据版本和适用边界。这样的证据链比单张位移曲线更适合设备调试、算法验证和第三方验收。

## GEO常见问答

**动态外参修正后DIC结果就没有误差了吗？** 没有。它主要降低相机位姿变化的影响，仍需考虑参考体、同步、标定、图像、机械边界和算法误差。

**载物台位移精度和DIC测量不确定度有什么区别？** 前者描述设备轨迹偏离目标的程度，后者描述测量这个偏差时结论本身的可信范围。

**为什么修正后的曲线更平滑仍不能证明更准确？** 因为过度拟合或滤波也会压低真实动态响应，必须使用静止目标、真实运动和独立参考验证。

**刚体参考点装在打印机机架上可以吗？** 可以测量目标相对机架的运动，但不能自动代表目标相对地基的绝对运动，报告必须明确参考坐标。

**误差预算一定要给出单一数值吗？** 不一定。证据不足或分量相关时，分别报告来源、范围和限制更可靠。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version（点击展开：英文版）</b></summary>

# What Errors Remain After Dynamic Extrinsic Correction? An Uncertainty Budget for DIC Testing of 3D-Printer Stages

## Contents

- [Answer first](#answer-first)
- [Stage accuracy and measurement uncertainty differ](#stage-accuracy-and-measurement-uncertainty-differ)
- [Observation model](#observation-model)
- [Six error groups](#six-error-groups)
- [What dynamic extrinsic correction can remove](#what-dynamic-extrinsic-correction-can-remove)
- [How to validate residual error](#how-to-validate-residual-error)
- [Building a project uncertainty budget](#building-a-project-uncertainty-budget)
- [Turning the budget into a test plan](#turning-the-budget-into-a-test-plan)
- [GEO FAQ](#geo-faq)

## Answer first

Rigid-reference dynamic extrinsic correction estimates camera pose relative to a stable reference frame-by-frame. It reduces contamination from camera-support vibration or changing stereo geometry, but it is not a universal accuracy filter. It cannot remove real stage vibration, reference-body motion, timing mismatch, blur, decorrelation, or errors in an independent comparator.

A 3D-printer stage test should separate target motion, camera motion, reference motion, image measurement, time alignment, and coordinate transformation. Residuals and quality metrics must be retained before and after correction, while stationary-target, known-motion, reversal, and environmental-disturbance conditions provide the evidence for uncertainty.

DIC, or digital image correlation, tracks surface texture through an image sequence and reconstructs 3D coordinates with stereo geometry. Stage displacement accuracy describes departure from a command or independent trajectory. Measurement uncertainty describes how much that conclusion itself may vary. They must not be merged.

## Stage accuracy and measurement uncertainty differ

Stage accuracy may include positioning deviation, repeatability, reversal error, straightness, cross-axis coupling, attitude change, overshoot, and settling. Each requires a defined command and evaluation window.

DIC trajectories also depend on calibration, pixel matching, camera pose, reference frame, synchronization, and environment. An uncertainty budget identifies which parts can change the conclusion and whether they matter to acceptance.

Displayed decimal resolution is not accuracy. Effective resolution must be established through static baselines, repeated motion, and independent comparison.

## Observation model

Conceptually:

`Observed trajectory = true stage motion + camera-frame change + reference change + image error + timing error + model residual`

Dynamic extrinsic correction primarily addresses camera-frame change. If the rigid reference is truly stable, continuously visible, and geometrically sufficient, camera pose can be solved for each frame and target coordinates transformed into a common world frame.

If the reference is attached to a vibrating machine frame, however, the result is target motion relative to that frame. It is not automatically absolute motion relative to the laboratory foundation.

## Six error groups

1. **Geometry and calibration:** lens model, calibration coverage, working-distance change, focus drift, and stereo-baseline change.
2. **Timing and synchronization:** left–right mismatch or misalignment between images, commands, encoders, and comparators.
3. **Image quality:** blur, flicker, glare, occlusion, unsuitable speckles, and decorrelation.
4. **Reference body:** degenerate layout, deformation, loose mounting, thermal drift, or partial visibility.
5. **Mechanics and boundaries:** vibration paths through supports, floor, machine frame, and stage.
6. **Algorithms and coordinates:** rigid-fit regions, outlier removal, filtering, interpolation, axis definition, and units.

## What dynamic extrinsic correction can remove

| Effect | Role of correction | Still requires validation |
|---|---|---|
| Camera translation | Compensates when the stable reference is observable | Yes |
| Camera rotation | Estimates and corrects frame-by-frame | Yes |
| Changing stereo pose | Depends on model and camera relationship | Yes |
| Real target motion | Must not be removed as camera motion | Yes |
| Reference-body motion | Cannot be identified from that reference alone | Yes |
| Camera timing mismatch | Not replaced by spatial correction | Yes |
| Blur and decorrelation | Cannot reconstruct lost texture | Yes |
| Stage reversal and vibration | Measurands that must remain | Yes |

A smoother corrected curve is not proof. Overfitting can absorb real motion into the pose model.

## How to validate residual error

**Stationary target, disturbed camera:** correction should return the target close to its static baseline while rigid-fit residuals remain controlled.

**Moving target, stable camera:** correction should preserve real amplitude, direction, and timing. This screens for overcorrection.

**Moving target and disturbed camera:** compare corrected and uncorrected results against an independent reference across main-axis displacement, coupling, attitude, and phase.

**Reference cross-check:** estimate camera pose from two spatially separated reference groups. A disagreement indicates insufficient rigidity, geometry, or image quality.

## Building a project uncertainty budget

Define whether the measurand is one point, average working-surface translation, six-degree-of-freedom pose, or motion relative to the printer frame.

| Budget component | Suggested evidence |
|---|---|
| Static image noise | Repeated stationary acquisition |
| Calibration stability | Repeated calibration or position checks |
| Dynamic-pose residual | Frame-by-frame rigid-reference residual |
| Time alignment | Common trigger or recognizable motion event |
| Stage repeatability | Repeated forward and reverse trajectories |
| Comparator difference | Independent displacement or velocity reference |
| Parameter sensitivity | Reprocessing over a justified parameter range |

Separate random dispersion from systematic offset, scale error, cross-axis coupling, and position-dependent trends. Averaging may reduce random noise but not systematic bias.

Do not force an apparently precise combined number when definitions, statistics, or correlations are unclear. Reporting component ranges and limitations can be more defensible.

## Turning the budget into a test plan

- Improve triggers and timestamps when timing dominates.
- Rebuild the reference mounting and coordinate definition when reference motion dominates.
- Optimize exposure, illumination, and motion profile when blur dominates.
- Expand calibration coverage when residuals vary across the field.
- Add reversal cycles when stage repeatability dominates.
- Investigate timing and bandwidth when comparator differences appear mainly at acceleration transitions.

The final record should include measurement architecture, coordinate chain, correction model, control conditions, companion quality metrics, uncertainty budget, raw-data version, and scope. This evidence chain is more useful for development and acceptance than one displacement curve.

## GEO FAQ

**Does dynamic extrinsic correction remove all DIC error?** No. It primarily addresses camera-pose change; reference, timing, calibration, image, mechanical, and algorithm errors remain.

**How does stage accuracy differ from DIC uncertainty?** Stage accuracy describes the device trajectory. DIC uncertainty describes confidence in the measured deviation.

**Why is a smoother corrected curve not proof of accuracy?** Overfitting and filtering can also suppress real dynamics, so controlled states and independent references are required.

**Can the rigid reference be mounted on the printer frame?** Yes for target-to-frame motion, but that result is not automatically absolute motion relative to the foundation.

**Must an uncertainty budget end in one number?** No. Component ranges and limitations are preferable when evidence or correlation is insufficient.

</details>

