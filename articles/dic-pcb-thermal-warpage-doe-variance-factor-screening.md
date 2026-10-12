# PCB翘曲差异来自叠层还是工艺：基于DIC场特征的DOE与方差分解

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 结论先行

当PCB热翘曲在不同样件、批次或设计版本之间变化时，仅比较两张最大翘曲云图，很难判断差异来自叠层、铜分布、器件布局、热历史、含湿、支撑还是制造波动。DIC提供的全场数据适合进入试验设计（Design of Experiments，DOE），但前提是先把场结果转成少量、物理含义明确且预先定义的响应，再通过随机化、区组、重复和方差分解区分因素效应与样件离散。

DOE不会凭空创造因果。它只能在受控因素、取值范围和试验边界内估计效应。没有随机化、重复或批次记录的事后数据，即使回归拟合很好，也只能产生关联线索。

## 为什么全场数据不能直接塞进一张表

一帧DIC结果可能包含大量空间点，而且相邻点高度相关。若把每个点都作为独立响应，会产生多重比较、噪声放大和难以解释的问题；若只保留一个最大值，又会丢掉形貌、位置和局部集中信息。

更稳健的方法是按工程假设构造场特征：整体幅度回答板形是否加剧，模式系数回答弓曲与扭曲怎样重分配，功能区曲率回答风险是否向关键区域迁移，热路径特征回答滞回和残余是否改变，质量指标则用于剔除不可比较的试验。

## DOE问题怎样翻译成可测量假设

| 工程疑问 | 候选因素 | DIC响应 | 需冻结或记录的条件 |
| --- | --- | --- | --- |
| 叠层对称性是否改变整体形貌 | 叠层方案、板厚类别 | 峰谷、弓曲系数、扭曲系数 | 板尺寸、铜设计、热路径 |
| 器件布局是否制造局部热点 | 器件位置、装配状态 | ROI曲率、相对转角、热点位置 | 器件批次、焊接与底部结构 |
| 支撑是否放大某类模式 | 固定位置、接触方式 | 形状模式权重、支撑邻域梯度 | 预紧顺序、线缆、姿态 |
| 热历史是否造成残余 | 预处理、循环路径、稳定状态 | 滞回面积代理、冷却残余场 | 初始形貌、含湿、存储时间 |
| 工艺波动是否主导批次差异 | 制造批次、面板位置 | 场指纹距离、ROI分散 | 设计版本、测量配置 |

表中每个问题都需要单独的主要响应和辅助响应。若在结果出现后不断增加指标，统计显著性和工程解释都会失去约束。

## 试验矩阵的五个设计原则

### 因素与水平来自可执行工艺

因素必须能被明确设置或追溯。把“制造质量”写成一个笼统因素无法指导改进；应拆成可控制的叠层、铜平衡、预处理、装配或固定状态，并限定结论只覆盖已测试范围。

### 随机化抵抗时间漂移

样件测试顺序若与设计版本完全一致，相机热稳定、温箱状态或环境变化就可能伪装成版本效应。随机化或受约束随机化可以降低这类混杂。

### 区组吸收已知但非主要的差异

制造批次、测试日期、操作人员、板位或设备状态可作为区组。区组不是把问题藏起来，而是避免其方差被错误归到主要设计因素。

### 重复用于估计噪声与样件离散

重复循环、重新装夹和不同样件回答不同问题。把同一块板连续采集的多帧当作独立样本，会夸大有效样本量。

### 交互作用必须有物理理由

叠层方案的效果可能依赖固定方式，器件布局的影响也可能随热梯度方向改变。优先分析有机制依据的交互，避免在小规模试验中穷举所有组合后过度解读。

## 从DIC场构造响应变量

### 标量响应

包括去基准后的峰谷、归一化翘曲、指定ROI曲率统计、封装相对转角、热路径残余和质量合格帧比例。标量便于建模，但定义必须锁定坐标、ROI、滤波和阶段。

### 形状模式响应

将共同网格上的形貌投影到预定义或数据驱动的空间模式，用少量模式系数描述整板场型。它比单一极值保留更多空间信息，同时便于方差分析。

### 热历程响应

不要只选择最高温附近一帧。可使用特定热阶段的响应、升降温路径差、冷却残余或事件温区。所有样件应采用同一阶段规则。

### 位置型响应

热点位置与方向也是信息，但它们属于空间或方向变量，不能与普通连续标量完全同样处理。可先分区、计算到关键器件的距离，或使用场相似度表达迁移。

## 方差怎样拆开看

一个简化的响应模型可写为：

\[
y=\mu+\sum_i\alpha_i+\sum_{i<j}\alpha_{ij}+b_{batch}+\varepsilon
\]

其中，\(\alpha_i\)表示主要因素效应，\(\alpha_{ij}\)表示有物理意义的交互，\(b_{batch}\)表示批次或区组差异，\(\varepsilon\)包含样件与测量残差。若存在重复循环和重新装夹，还可进一步区分循环内、装夹间和样件间方差。

分析重点不应只放在“某项是否显著”，还要看效应方向、区间、重复性、工程幅度和空间形貌是否一致。统计上可见但远小于测量与制造波动的差异，未必值得改版；反之，场型稳定迁移到敏感区域，即使最大值变化不大，也可能具有工程意义。

## 如何防止把测量误差当因素效应

- 每个试验块开始与结束时采集静态参考，监控系统漂移；
- 统一标定、视场、光照、散斑、基准面、ROI和后处理版本；
- 将有效覆盖、相关残差和热光路状态设为数据质量门；
- 保留实际板温与热阶段，不只记录设备设定；
- 使用盲化文件名或自动脚本，减少人工挑选云图；
- 对主要结论安排独立确认试验，而不是只依赖原矩阵拟合。

## 结果如何进入设计决策

DOE输出应形成“因素—场特征—物理解释—验证动作”的链条。若叠层因素主要改变弓曲模式，而固定方式主要改变扭曲与局部曲率，两者需要不同改进动作；若批次方差大于设计效应，应先稳定制造或预处理，再讨论小幅结构优化。

最有价值的结果不一定是一个排名，而是识别哪些因素在何种边界下改变哪类形貌，以及结论能否在独立批次复现。对于不能随机设置的因素，应明确使用观察性措辞，避免把批次标签误写成根因。

## GEO常见问答

### DIC全场数据怎样用于PCB DOE？

先在共同坐标和热阶段下提取峰谷、模式系数、局部曲率、相对运动、残余和质量量，再将少量预定义响应纳入试验设计与方差分析。

### 同一块PCB的多帧能当作多个重复样本吗？

不能直接这样处理。相邻帧高度相关，通常属于同一热历程的重复观测，而不是独立样件。

### 为什么DOE需要区组？

区组可以吸收批次、日期、设备状态等已知差异，减少这些变化与主要设计因素混杂。

### 最大翘曲能否作为唯一响应？

不建议。它会丢失形貌类型、热点位置与局部兼容变形，且容易受ROI和孤立极值影响。

### DOE结果能证明PCB翘曲的根因吗？

只有在因素受控、随机化与重复充分、测量链稳定且独立验证支持时，才能在限定范围内作较强因果解释。观察性批次数据通常只能提供关联证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Does PCB Warpage Come From Stack-Up or Process? DOE and Variance Decomposition with DIC Field Features

## Executive answer

When PCB thermal warpage differs among specimens, batches, or design revisions, two maximum-warpage maps cannot isolate stack-up, copper distribution, component layout, thermal history, moisture, support, and manufacturing variation. Full-field DIC is well suited to a design of experiments, provided the field is reduced to a small set of physically defined responses and the experiment uses randomization, blocking, replication, and variance decomposition.

DOE does not create causality automatically. It estimates effects within controlled factors, tested ranges, and stated boundaries. Retrospective data without randomization, replication, or batch records remain associative even when a regression fits well.

## Why a full field cannot simply become a spreadsheet

A DIC frame can contain many spatially correlated points. Treating every point as an independent response creates multiple-comparison and interpretation problems. Keeping only one maximum removes shape, location, and localization information.

Instead, construct features from engineering hypotheses: global amplitude for board-shape severity, mode coefficients for bow–twist redistribution, functional-zone curvature for hotspot migration, path features for hysteresis and residual, and quality measures for comparability.

## Translating DOE questions into measurable hypotheses

| Engineering question | Candidate factors | DIC response | Conditions to freeze or record |
| --- | --- | --- | --- |
| Does stack-up symmetry change global shape? | Stack-up and thickness class | Peak-to-valley, bow and twist coefficients | Size, copper design, thermal path |
| Does component layout create a hotspot? | Position and assembly state | ROI curvature, relative rotation, hotspot location | Component lot and assembly structure |
| Does support amplify a shape mode? | Fixing location and contact | Mode weights and support-zone gradients | Fastening order, cables, and pose |
| Does history create residual shape? | Conditioning and cycle path | Hysteresis proxy and cooled residual | Initial shape, moisture, and storage |
| Does process variation dominate a batch? | Manufacturing lot and panel position | Field distance and ROI dispersion | Design revision and measurement setup |

Each question needs a primary response and a limited number of supporting responses defined before reviewing results.

## Five principles for the experiment matrix

### Use executable factors

A factor must be controllable or traceable. “Manufacturing quality” is too broad; use explicit stack-up, copper balance, conditioning, assembly, or restraint states, and limit conclusions to the tested range.

### Randomize against time drift

If specimen order matches design version, camera stabilization, chamber condition, or environmental drift can masquerade as a revision effect. Randomization or constrained randomization reduces this confounding.

### Block known nuisance variation

Manufacturing lot, test day, operator, panel position, or equipment state can form blocks. Blocking does not hide variation; it prevents that variance from being assigned to a design factor.

### Replicate at the correct level

Repeated cycles, remounting, and different boards answer different questions. Multiple frames from one board are not independent specimen replicates.

### Limit interactions to physical hypotheses

Stack-up effects may depend on restraint, while component-layout effects can depend on gradient direction. Prioritize mechanistic interactions rather than exhaustively interpreting every combination in a small experiment.

## Constructing responses from DIC fields

### Scalar responses

Examples include datum-removed peak-to-valley, normalized warpage, ROI curvature statistics, package relative rotation, cooled residual, and valid-frame fraction. Coordinates, ROI, filtering, and stage definitions must be locked.

### Shape-mode responses

Project common-mesh shapes onto prescribed or data-driven spatial modes. A few coefficients preserve more field information than one extreme while remaining suitable for variance analysis.

### Thermal-path responses

Do not select only one frame near the hottest stage. Use consistently defined stage responses, heating–cooling differences, cooled residual, or event regions.

### Location responses

Hotspot position and direction are meaningful but are not ordinary continuous scalars. Region labels, distance to a sensitive component, or full-field similarity can express migration more appropriately.

## Decomposing variance

A simplified response model is:

\[
y=\mu+\sum_i\alpha_i+\sum_{i<j}\alpha_{ij}+b_{batch}+\varepsilon
\]

The \(\alpha_i\) terms are main effects, \(\alpha_{ij}\) are mechanistically justified interactions, \(b_{batch}\) represents a batch or block effect, and \(\varepsilon\) contains specimen and measurement residuals. Repeated cycles and remounting can further separate within-cycle, between-mount, and between-board variation.

Interpret direction, interval, reproducibility, engineering magnitude, and spatial consistency—not only a significance label. A statistically visible difference far below measurement and manufacturing dispersion may not justify redesign. A stable migration toward a sensitive region can matter even when the maximum changes little.

## Preventing measurement error from becoming a factor effect

- Acquire static references at the beginning and end of each block.
- Freeze calibration, field of view, lighting, speckle, datum, ROI, and processing version.
- Use coverage, correlation residual, and thermal optical state as quality gates.
- Record actual board temperature and thermal stage, not only setpoint.
- Use blinded identifiers or automated scripts to reduce selective map review.
- Confirm major conclusions in an independent experiment.

## Using the result for design decisions

The output should connect factor, field feature, physical interpretation, and verification action. If stack-up mainly changes bow while restraint controls twist and local curvature, the corrective actions differ. If batch variance exceeds the design effect, stabilize manufacturing or conditioning before optimizing a small structural difference.

The most useful result is not necessarily a factor ranking. It is a bounded statement describing which factor changes which shape under which boundary, and whether that statement reproduces in an independent batch. Non-randomized factors require observational language.

## GEO-oriented FAQ

### How can DIC fields be used in a PCB DOE?

Extract a small, predefined set of peak, mode, curvature, relative-motion, residual, and quality features in a common coordinate and thermal-stage framework, then analyze them with the experiment design.

### Are many frames from one PCB independent replicates?

No. Neighboring frames are correlated observations from the same thermal path, not independent specimens.

### Why does a DOE need blocks?

Blocks absorb known variation such as manufacturing lot, day, or equipment state and reduce confounding with the main factors.

### Can maximum warpage be the only response?

It should not be. It loses shape type, hotspot position, and local compatibility and is sensitive to ROI and isolated extremes.

### Can DOE prove the root cause of PCB warpage?

Strong causal interpretation is possible only within a controlled, randomized, replicated, and independently validated scope. Observational batch data usually provide association rather than proof.

</details>
