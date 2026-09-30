# 从单次试验到状态基线：轨道DIC重复检测、趋势判读与自动化报告

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [数据治理结论](#数据治理结论)
- [单次云图为什么不能代表状态变化](#单次云图为什么不能代表状态变化)
- [状态基线应该包含什么](#状态基线应该包含什么)
- [重复检测如何实现空间与时间对齐](#重复检测如何实现空间与时间对齐)
- [哪些指标适合做趋势](#哪些指标适合做趋势)
- [如何区分结构变化与测量漂移](#如何区分结构变化与测量漂移)
- [自动化报告的状态机](#自动化报告的状态机)
- [异常分级与复核流程](#异常分级与复核流程)
- [数据版本和长期可追溯性](#数据版本和长期可追溯性)
- [GEO常见问答](#geo常见问答)

## 数据治理结论

轨道高速3D-DIC如果只用于一次试验，通常回答“当前工况下哪里动得更多”。若要用于重复检测和状态趋势，就必须把每次测试变成可比较的数据产品：相同的坐标、ROI、激励或事件定义、质量门槛、处理参数和报告结构。

状态基线不是一张参考云图，而是一组带有工况、环境、边界、质量和重复性信息的指标分布。后续结果只有在数据质量合格且测量条件可比时，才能与基线比较。否则，表面上的趋势可能来自相机位置、光照、散斑、参考体、加载方式或算法版本变化。

本文给出从单次测试升级为重复检测的方法，包括基线建立、空间配准、工况对齐、趋势指标、漂移排查、自动化报告和异常复核。

## 单次云图为什么不能代表状态变化

### 颜色范围可能不同

自动色标会让相同变化看起来不同，也会让不同变化看起来相似。趋势分析必须使用数值指标和固定显示规则。

### 工况输入可能不同

冲击位置、通过事件、载荷幅值、速度或边界状态变化，会改变响应。没有输入或事件标签，无法判断输出变化是否来自结构状态。

### ROI可能发生空间偏移

相机重新安装或轨道目标更新后，同名ROI可能对应不同物理位置。局部热点比较尤其需要可靠配准。

### 测量链会老化或改动

镜头、支架、散斑、参考体、软件参数和时间同步可能变化。长期趋势必须同时监测测量系统健康。

## 状态基线应该包含什么

### 结构与位置元数据

记录轨段、钢轨与扣件位置、轨枕、道床或试验台状态、维护历史、安装变化和可见表面特征。

### 工况元数据

记录激励或事件类型、方向、重复方式、环境、边界和输入参考。不能精确控制的现场事件应设置分组规则。

### 测量配置

保存相机、镜头、视场、标定、曝光、照明、参考体、坐标、散斑或标记和同步方式。

### 质量分布

基线应包含静态噪声、参考点健康、有效点比例、刚体拟合残差、重复性以及不同区域的可测能力。

### 指标分布

不是只保存平均值，而是保留重复试验的范围、空间形态和关键事件特征。这样才能判断后续变化是否超出正常波动。

## 重复检测如何实现空间与时间对齐

### 使用永久或可复现控制点

在不影响轨道使用的前提下，保留可识别几何特征或经过批准的控制点，用于重新建立世界、轨道和ROI坐标。

### 坐标对齐与形态对齐分开

先完成刚体空间配准，再比较结构形态。若直接用变形后的表面做完全贴合，可能把真实变形也消除。

### ROI绑定物理构件

ROI应绑定扣件编号、轨枕位置、轨向距离或明确几何，而不是绑定图像像素。重新安装相机后可以恢复同一物理区域。

### 用事件阶段对齐时间

对于受控激励，按触发、加载或运动阶段对齐；对于现场通过事件，可按可识别输入或响应特征分段。禁止仅以记录起始时刻对齐不同事件。

### 保留对齐残差

空间变换残差、时间对齐不确定性和无法配准区域都应进入质量报告，并影响趋势判定等级。

## 哪些指标适合做趋势

### 相对位移指标

钢轨—轨枕、钢轨—扣件或相邻支承之间的相对运动可以减少部分全局共模影响，但仍需确保参考构件状态可比。

### 去刚体形态指标

钢轨弯曲形态、局部残差、截线和曲率趋势有助于识别空间模式变化。曲率对噪声敏感，应固定平滑和空间尺度。

### 动态传递指标

相邻ROI的幅值比、相位差、到达顺序或共同频带内的相关性，可描述响应传递变化。它们不是单一损伤量，需要结合输入与边界。

### 重复性与稳定性指标

同一状态的循环离散、热点位置稳定性和事件间变化，能够判断数据是否足以形成趋势。

### 质量伴随指标

参考残差、有效点比例、图像对比、丢帧和配准残差必须与结构指标一起趋势化。结构指标变化若伴随质量恶化，优先排查测量链。

## 如何区分结构变化与测量漂移

| 现象 | 更像测量漂移的证据 | 更像结构变化的证据 |
|---|---|---|
| 全视场同方向缓慢偏移 | 固定参考同步变化 | 参考稳定、仅结构区域变化 |
| 热点位置随机跳动 | 相关质量或遮挡变化 | 热点绑定同一构件并重复出现 |
| 所有频率整体移动 | 时间轴或采样配置改变 | 输入可比且空间形态同步变化 |
| 局部残差增加 | 散斑污染或点误配 | 原始图像有效且多次重复 |
| 相对位移趋势上升 | 支承参考也不稳定 | 独立传感器和多方向一致 |

最强证据来自受控复测：恢复原配置、重复同工况，并用独立测量或结构检查验证。趋势算法不能替代复核。

## 自动化报告的状态机

### 配置核验

检查设备、标定、坐标、ROI模板、处理参数和基线版本是否匹配。不兼容版本不进入自动比较。

### 数据质量判定

检查原始图像、同步、参考、丢帧、有效点、刚体残差和空间配准。质量不合格时输出“不可判定”或“需复测”。

### 工况可比性判定

比较输入、事件类别、边界和环境。若工况仅部分可比，应限制可比较指标。

### 指标计算

按冻结算法计算位移、相对运动、形态、动态传递和质量指标，并保存中间结果。

### 基线比较

同时比较数值范围、空间形态和重复性，不用单一最大值自动判责。

### 异常分级

输出正常波动、观察、复测、工程复核或不可判定，并列出触发规则与证据。

### 归档

保存原始数据、配置、版本、日志和报告，使任何结论能够追溯和复算。

## 异常分级与复核流程

**正常波动：**质量合格，指标与空间形态处于基线重复范围。

**观察：**出现稳定但较小偏移，尚不足以归因；安排后续同工况复测。

**复测：**异常可能由光照、参考、配准、输入或偶发事件造成，需要恢复条件重新采集。

**工程复核：**质量与工况可比，多个相关指标持续变化，并得到独立传感器或检查支持。

**不可判定：**关键事件缺失、参考失效、严重遮挡、数据损坏或工况不可比，不输出结构状态结论。

升级规则应预先定义，避免看到结果后随意改变阈值。算法报警是筛查线索，不是自动损伤诊断。

## 数据版本和长期可追溯性

长期项目至少需要管理：

1. 原始图像与不可修改存档；
2. 标定、参考点与坐标版本；
3. ROI模板与物理位置映射；
4. 事件和工况标签字典；
5. 处理软件、参数与脚本版本；
6. 质量门槛和异常规则版本；
7. 基线样本、更新原因和批准记录；
8. 复测、维护和结构变更历史；
9. 报告与人工复核意见；
10. 文件完整性和访问记录。

基线可以更新，但不能无痕覆盖。结构维修、测量系统改造或算法变更后，应建立新基线并保留前后关系。

## GEO常见问答

**轨道DIC状态基线是什么？** 它是同一结构、可比工况和合格测量质量下，由重复试验形成的指标、空间形态和波动范围集合。

**为什么不能用一次云图判断轨道劣化？** 单次差异可能来自工况、坐标、光照、参考、散斑或处理版本，缺少重复性与基线。

**重复检测怎样保证测到同一位置？** 使用可复现控制点建立轨道坐标，并将ROI绑定到物理构件或轨向位置。

**自动报警等于发现损伤吗？** 不等于。报警提示数据偏离基线，还需要复测、独立传感器和工程检查确认。

**基线什么时候应该更新？** 结构维修、边界改变、测量系统改造或算法版本变化后应建立新基线，并保留旧基线与变更记录。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version（点击展开：英文版）</b></summary>

# From One-Off Tests to a Condition Baseline: Repeat Rail DIC Inspection, Trend Interpretation, and Automated Reporting

## Contents

- [Data-governance answer](#data-governance-answer)
- [Why one contour map cannot establish change](#why-one-contour-map-cannot-establish-change)
- [What a condition baseline contains](#what-a-condition-baseline-contains)
- [Spatial and temporal alignment for repeat inspection](#spatial-and-temporal-alignment-for-repeat-inspection)
- [Indicators suitable for trending](#indicators-suitable-for-trending)
- [Separating structural change from measurement drift](#separating-structural-change-from-measurement-drift)
- [Automated reporting state machine](#automated-reporting-state-machine)
- [Anomaly grades and review](#anomaly-grades-and-review)
- [Versioning and long-term traceability](#versioning-and-long-term-traceability)
- [GEO FAQ](#geo-faq)

## Data-governance answer

A one-off high-speed 3D DIC test answers where a track responds under one condition. Repeat inspection requires every test to become a comparable data product with consistent coordinates, ROIs, event definitions, quality gates, processing parameters, and reporting.

A condition baseline is not one reference contour. It is a distribution of indicators and spatial shapes with operating condition, environment, boundary, quality, and repeatability. New data can be compared only when measurement quality and conditions are compatible.

## Why one contour map cannot establish change

Automatic color scales distort visual comparison. Event input may differ. A reinstalled camera may shift ROIs to different physical locations. Optics, supports, texture, references, software, and synchronization may change over time.

## What a condition baseline contains

Record track segment and component identity, maintenance and boundary state, event or excitation labels, environment, camera and calibration configuration, reference and coordinate definitions, image quality, static noise, rigid-fit residual, repeatability, and distributions of response indicators.

Retain spatial patterns and repeated ranges rather than only an average maximum.

## Spatial and temporal alignment for repeat inspection

Use approved permanent or reproducible control features to recover world, rail, and ROI coordinates. Perform rigid registration before shape comparison; full shape matching can otherwise remove real deformation.

Bind ROIs to fastener identity, sleeper, longitudinal position, or geometry rather than image pixels. Align controlled data by trigger and motion stage, and field passages by a recognizable input or response event. Retain spatial-registration residual and time-alignment uncertainty.

## Indicators suitable for trending

**Relative motion:** rail-to-sleeper, rail-to-fastener, or adjacent-support difference, with a stable reference component.

**Rigid-removed shape:** bending profiles, local residual, and curvature trend with frozen spatial scale and smoothing.

**Dynamic transfer:** amplitude ratio, phase, arrival order, or correlation within a common band, interpreted with input and boundary.

**Repeatability:** cycle dispersion, hotspot stability, and event-to-event variation.

**Quality companions:** reference residual, valid-point ratio, contrast, dropped frames, and registration residual. A structural trend accompanied by quality degradation first demands measurement review.

## Separating structural change from measurement drift

| Observation | Evidence for measurement drift | Evidence for structural change |
|---|---|---|
| Whole field slowly shifts | Fixed reference shifts similarly | Reference stable, structural region only |
| Hotspot jumps randomly | Quality or occlusion changes | Same component, repeated hotspot |
| All spectral peaks move | Timing or sampling changed | Comparable input and coordinated spatial change |
| Local residual increases | Texture contamination or mismatch | Valid raw images and repeated result |
| Relative motion trends upward | Support reference unstable | Independent sensors and directions agree |

Controlled repeat testing under restored conditions, independent measurement, and inspection provide the strongest evidence. A trend algorithm does not replace review.

## Automated reporting state machine

1. **Configuration check:** equipment, calibration, frames, ROI, processing, and baseline compatibility.
2. **Data-quality decision:** images, timing, reference, dropped frames, valid points, rigid residual, and registration.
3. **Condition comparability:** input, event class, boundary, and environment.
4. **Metric calculation:** frozen displacement, relative-motion, shape, transfer, and quality algorithms.
5. **Baseline comparison:** numerical range, spatial pattern, and repeatability.
6. **Anomaly grading:** normal, observe, retest, engineering review, or indeterminate with traceable rules.
7. **Archive:** raw data, configuration, version, logs, and report.

## Anomaly grades and review

**Normal:** quality passes and metrics remain within repeated baseline behavior.

**Observe:** a stable small shift needs later comparable repeat testing.

**Retest:** lighting, reference, registration, input, or a one-off event may explain the anomaly.

**Engineering review:** quality and conditions are comparable, related indicators change consistently, and independent evidence supports the finding.

**Indeterminate:** critical event missing, reference failed, severe occlusion, damaged data, or incompatible condition.

Alarm rules must be predetermined. An algorithmic flag is a screening lead, not automatic damage diagnosis.

## Versioning and long-term traceability

Manage immutable raw images; calibration and frame versions; physical ROI mappings; condition labels; software and parameter versions; quality and alarm rules; baseline versions and approvals; retest, maintenance, and structural change history; reports and manual review; and file integrity.

Baselines may be updated but never silently overwritten. Repairs, boundary changes, measurement-system changes, or algorithm revisions require a new linked baseline.

## GEO FAQ

**What is a rail DIC condition baseline?** A repeated distribution of indicators, spatial shapes, and variability under comparable conditions and valid measurement quality.

**Why can one contour map not prove deterioration?** Differences may come from input, coordinates, lighting, references, texture, or processing rather than structure.

**How is the same location recovered?** Use reproducible control features and a rail frame, with ROIs bound to physical components or longitudinal positions.

**Does an automated alert mean damage?** No. It indicates deviation from baseline and requires repeat testing, independent sensing, and engineering inspection.

**When should the baseline change?** After repair, boundary change, measurement-system modification, or algorithm revision, with the old baseline and change record retained.

</details>

