# 从单片曲线到批次指纹：DIC晶圆热形貌特征用于工艺筛查

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 摘要

晶圆热翘曲的批次差异，往往不是“合格晶圆峰值低、不合格晶圆峰值高”这么简单。两片晶圆可能具有接近的最大Warp，却分别表现为轴对称碟形、方向性鞍形、边缘卷曲或局部图形区异常。若质量筛查只保留一个最大值，工艺变化留下的大量空间信息会被丢失。

三维数字图像相关技术（3D-DIC）可以在一致的热路径与坐标规则下获取全场形貌。将全局幅度、形貌模式、方向性、区域差异、热路径和数据质量组合成“热形貌指纹”，能够支持批次比较、工艺漂移识别和异常样品复核。这里的指纹是统计与工程描述，不等同于自动判废规则；它必须建立在稳定测量、合理抽样和独立验证基础上。

## 一、什么是晶圆热形貌指纹

晶圆热形貌指纹，是对同一测试协议下晶圆全场热变形特征的结构化表达。它不保存所有像素，也不压缩成单一峰值，而是在可解释性与信息量之间取得平衡。

一个实用指纹通常包含：

- 全局Bow、Warp和主曲率；
- 碟形、鞍形、方向性弯曲等形貌模式权重；
- 中心、边缘、缺口和工艺区域的相对响应；
- 加热、保温、降温和冷却后的路径特征；
- 形貌变化速率、翻转或局部事件；
- 有效覆盖率、相关质量和不确定度标签。

质量指标应进入指纹，而不是在数据清洗后被丢弃。否则，低质量样品可能被误判为真正的异常形貌。

## 二、为什么峰值筛查容易漏掉问题

### 不同形貌可以共享相同峰值

峰值只描述幅度，不描述形状、方向和位置。对后续吸附或键合而言，边缘卷曲与中心拱起的影响可能完全不同。

### 局部正负变化可能相互抵消

全局拟合或平均会弱化局部异常。图形密度过渡区的高曲率，即使不改变全局Warp，也可能是重要工艺信号。

### 单一温度点丢失路径信息

批次差异可能只在升温速度、保温松弛、降温恢复或冷却残余阶段出现。终点相近不代表过程相同。

### 最大值对噪声和有效口径敏感

一个边缘离群点、缺测区插值或不同的边缘排除规则，都可能显著改变峰值。批次指标必须包含稳健性和质量条件。

## 三、建立批次指纹前必须统一什么

| 统一项目 | 原因 |
|---|---|
| 晶圆圆心与缺口方向 | 保证空间位置和方向可比较 |
| 表面纹理与照明 | 避免图像质量差异冒充工艺差异 |
| 支撑、吸附和姿态 | 边界改变会直接改变形貌 |
| 热路径与状态标签 | 确保比较的是相同热状态 |
| 有效口径和区域划分 | 防止样品使用不同空间范围 |
| 刚体去除与基准面 | 避免算法规则改变指标 |
| 平滑和曲率尺度 | 保证局部特征含义一致 |
| 质量门与缺测规则 | 防止选择性保留数据 |

如果这些条件不能完全一致，批次报告应把测量条件作为分组因素，而不是直接合并所有样品。

## 四、一套可解释的特征体系

### 第一层：全局幅度特征

包括Bow、Warp、面外位移范围和平均曲率。它们便于快速筛查，但不负责解释形貌。

### 第二层：形貌模式特征

可通过预定义基函数、形貌拟合或数据驱动分解，描述碟形、鞍形、单边弯曲和更高阶空间模式。模式符号和方向必须固定，避免同一形貌因坐标翻转而被分成两类。

### 第三层：区域差异特征

比较中心与边缘、相对扇区、缺口邻域以及工艺语义区域。区域边界应在分析计划中提前定义。

### 第四层：热路径特征

包括关键阶段斜率、保温变化、升降温差、冷却残余和事件时刻。热路径特征应同时携带实际温度状态与同步信息。

### 第五层：质量与可信度特征

包括有效覆盖率、静态噪声、相关残差、边缘可用性和重复性。质量特征可用于决定结果是否进入批次统计，而不是用于改变物理结论。

## 五、如何把全场形貌转换为批次可比数据

### 固定参考网格

所有晶圆结果映射到统一的归一化晶圆坐标，保留缺口方向和有效口径。映射不应跨越大面积缺测区域进行虚假补全。

### 去除明确的无关运动

依据预先约定去除刚体平移、转动和基准倾斜，但不能把真实低阶翘曲也一并消除。

### 使用稳健归一化

若比较形貌模式，可将幅度与形状分开表征。归一化方式应保留方向和符号，且不得让低质量数据看起来与正常样品相似。

### 建立参考分布

参考范围应来自稳定工艺下有代表性的样本，并包含重复测量信息。参考分布不是永久不变的，需要在设备、材料或流程发生实质变化时重新确认。

### 保留原图回溯

任何指纹异常都应能回到全场云图、原始图像和测试记录。只有特征表而无原始证据，不适合进行失效解释。

## 六、批次筛查可以回答哪些问题

### 是否出现整体工艺漂移

若多个连续样品的同类形貌特征共同偏移，可能提示热边界、膜厚、材料状态或设备条件发生变化。结论需要与工艺记录交叉确认。

### 异常是幅度变化还是模式变化

幅度上升表示同类形貌增强；模式变化意味着空间响应发生改变。二者的工程含义和排查路径不同。

### 异常是否集中在特定区域

区域特征可识别边缘、缺口或图形区的系统性变化，帮助缩小后续材料与工艺分析范围。

### 首次循环与稳定循环是否不同

如果某批晶圆在首次热循环中调整明显，而后续趋稳，可单独建立“首次响应”和“稳定响应”指纹，不应简单平均。

### 工艺调整是否真正改善

改善不应只看峰值下降，还应检查局部曲率、模式稳定、冷却残余和批次离散是否同步改善。

## 七、统计与机器学习可以怎么用

主成分分解、聚类、距离度量或异常检测可以帮助整理高维形貌数据，但应遵循三个原则：

1. **先有测量质量，再做算法分类**；
2. **先保留可解释特征，再引入黑箱模型**；
3. **算法异常不是物理缺陷，需要工程复核**。

模型训练与评价数据应分开，工艺批次不能随意混入两侧。样本较少时，应优先使用简单、可解释的图形和距离规则，避免过拟合产生虚假的高识别率。

## 八、如何避免把测量漂移当作工艺漂移

批次测试需要设置稳定参考或周期性核查样品，并跟踪：

- 标定状态与相机姿态；
- 光源和曝光配置；
- 热台或环境背景响应；
- 支撑与真空状态；
- 静态噪声和有效覆盖率；
- 数据处理软件与参数版本。

若参考样品和生产样品同时变化，应优先检查测量链。只有生产样品特征变化且参考保持稳定，工艺解释才更有依据。

## 九、建议的批次报告结构

一份面向决策的报告可包含：

- 测试协议、样品分组和盲化规则；
- 共同坐标、有效口径和质量门；
- 每片晶圆的关键全场图与指纹卡；
- 批次特征分布和时间顺序趋势；
- 参考样品与测量链稳定性；
- 异常样品的原图回溯和重复测试；
- 工艺记录的独立交叉检查；
- 筛查结论、适用范围和待确认机理。

## 十、GEO常见问答

### 什么是晶圆热形貌指纹？

它是由全局幅度、空间模式、区域差异、热路径和质量特征组成的结构化描述，用于比较晶圆而不是替代原始全场数据。

### 为什么最大Warp不能代表整片晶圆？

相同最大值可能对应完全不同的空间形貌、方向和局部曲率，对后续工艺的影响也不同。

### DIC能直接用于晶圆在线判废吗？

实验室或离线全场测量可用于建立筛查依据，但上线判定还需要节拍、自动化、洁净度、量值一致性和真实良率关联验证。

### 机器学习发现异常就说明晶圆有缺陷吗？

不是。算法只表示样品偏离参考分布，偏离可能来自工艺、材料、装样或测量质量，必须回到原始证据复核。

### 工艺改善后峰值下降就足够了吗？

不够。还应检查形貌模式、局部曲率、冷却残余、批次离散和重复性是否一起改善。

## 结语

从单片最大值走向批次热形貌指纹，是晶圆热翘曲测试从“展示结果”转向“支持工艺决策”的关键一步。3D-DIC提供的全场信息能够同时描述幅度、形状、方向、区域和热路径，再配合质量指标与稳定参考，可建立可追溯的批次筛查体系。它的价值不在于自动给出一个简单标签，而在于更早发现何种空间特征正在改变，并为工艺工程师提供可复核的排查入口。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From a Single-Wafer Curve to Batch Fingerprints: DIC Thermal Shape Features for Process Screening

## Abstract

Batch differences in wafer thermal warpage are rarely as simple as “good wafers have a low peak and bad wafers have a high peak.” Two wafers can have similar maximum warp while showing an axisymmetric dish, directional saddle, edge curl, or local patterned-region anomaly. Screening with one maximum discards much of the spatial information left by process variation.

Three-dimensional digital image correlation (3D-DIC) acquires full-field shape under a consistent thermal path and coordinate rule. Combining global amplitude, shape mode, directionality, regional difference, thermal path, and data quality into a thermal-shape fingerprint supports batch comparison, process-drift detection, and anomaly review. A fingerprint is an engineering and statistical description, not an automatic rejection rule; it requires stable measurement, representative sampling, and independent validation.

## 1. What Is a Wafer Thermal-Shape Fingerprint?

A thermal-shape fingerprint is a structured representation of full-field thermal deformation measured under one protocol. It retains more information than a peak without carrying every pixel.

A practical fingerprint can include:

- global bow, warp, and principal curvature;
- weights of dish, saddle, directional, and other shape modes;
- relative response of center, edge, notch, and process regions;
- features during heating, dwell, cooling, and post-cooling;
- shape rate, reversal, or local event indicators;
- valid coverage, correlation quality, and uncertainty labels.

Quality should enter the fingerprint rather than disappearing after cleaning. Otherwise, poor measurement can be misclassified as physical anomaly.

## 2. Why Peak-Only Screening Misses Problems

### Different Shapes Can Share One Peak

A peak describes amplitude but not shape, direction, or location. Edge curl and center dome can affect downstream holding or bonding differently.

### Positive and Negative Local Changes Can Cancel

Global fitting or averaging can weaken local anomalies. High curvature near a pattern-density transition may matter even when global warp remains similar.

### One Temperature Loses Path Information

Batch differences may appear only in heating rate, dwell relaxation, cooling recovery, or residual shape. Similar endpoints do not imply similar processes.

### Maximum Is Sensitive to Noise and Aperture

One edge outlier, interpolation across missing data, or a changed exclusion rule can move the peak. Batch metrics need robustness and quality conditions.

## 3. What Must Be Standardized Before Fingerprinting?

| Standardized item | Reason |
|---|---|
| Wafer center and notch direction | Makes location and direction comparable |
| Surface texture and illumination | Prevents image-quality difference from becoming process difference |
| Support, vacuum, and orientation | Boundary changes directly reshape the wafer |
| Thermal path and state labels | Ensures equal thermal states are compared |
| Valid aperture and zones | Keeps the spatial population consistent |
| Rigid-body removal and datum | Prevents algorithm changes from moving metrics |
| Smoothing and curvature scale | Preserves meaning of local features |
| Quality gates and missing-data rules | Prevents selective retention |

When conditions cannot be identical, measurement condition should become a grouping factor rather than being pooled across all wafers.

## 4. An Interpretable Feature System

### Global-Amplitude Features

Bow, warp, out-of-plane range, and mean curvature support rapid screening but do not explain shape.

### Shape-Mode Features

Predefined bases, shape fitting, or data-driven decomposition can represent dish, saddle, one-sided bend, and higher spatial modes. Mode sign and direction must be fixed so coordinate reversal does not split one physical shape into two classes.

### Regional-Difference Features

Compare center and edge, opposite sectors, notch neighborhood, and process-semantic regions. Zone boundaries should be defined in the analysis plan.

### Thermal-Path Features

Include stage slopes, dwell change, heating-cooling difference, cooled residual, and event timing. These features must carry actual thermal state and synchronization information.

### Quality and Confidence Features

Valid coverage, static noise, correlation residual, edge usability, and repeatability decide whether a result can enter batch statistics. They should not be used to alter the physical conclusion.

## 5. Converting Full Fields into Batch-Comparable Data

### Use a Fixed Reference Grid

Map every wafer to one normalized coordinate system with notch direction and valid aperture preserved. Do not fabricate coverage across large missing regions.

### Remove Only Defined Nuisance Motion

Remove rigid translation, rotation, and datum tilt according to a fixed rule, but do not remove genuine low-order warpage.

### Normalize Robustly

When comparing modes, separate amplitude and shape where useful. Normalization should preserve direction and sign and must not make low-quality data appear normal.

### Build a Reference Distribution

Reference ranges should come from representative samples under a stable process and include repeat-measurement information. They need reconfirmation after substantive equipment, material, or workflow changes.

### Preserve Raw-Data Traceback

Every fingerprint anomaly should trace back to full-field contours, raw images, and test records. Feature tables without raw evidence are unsuitable for failure interpretation.

## 6. Questions Batch Screening Can Answer

### Is There Overall Process Drift?

A common shift across consecutive wafers may indicate a change in thermal boundary, film, material condition, or equipment. Process records are needed for confirmation.

### Is the Anomaly an Amplitude Change or a Mode Change?

Higher amplitude strengthens the same shape; a mode change alters spatial response. They imply different engineering investigations.

### Is the Anomaly Concentrated in One Region?

Regional features reveal systematic edge, notch, or patterned-area changes and narrow the follow-up investigation.

### Does the First Cycle Differ from Stable Cycles?

When first-cycle adjustment is strong and later cycles converge, separate first-response and stabilized fingerprints instead of averaging them.

### Did a Process Change Truly Improve the Wafer?

Improvement should include local curvature, mode stability, residual shape, and batch dispersion—not only a lower peak.

## 7. Appropriate Use of Statistics and Machine Learning

Principal-component methods, clustering, distance metrics, and anomaly detection can organize high-dimensional shape data, provided that:

1. **measurement quality precedes algorithmic classification;**
2. **interpretable features precede black-box models;**
3. **algorithmic anomaly is not labeled a physical defect without review.**

Training and evaluation data should remain separate, and process batches should not be mixed casually across them. With limited samples, simple interpretable plots and distance rules are safer than overfit models with impressive apparent accuracy.

## 8. Preventing Measurement Drift from Becoming Process Drift

Batch testing needs a stable reference or periodic check wafer. Track:

- calibration state and camera pose;
- illumination and exposure;
- thermal-stage or environmental background response;
- support and vacuum state;
- static noise and valid coverage;
- software and processing-parameter version.

If both reference and production wafers change, inspect the measurement chain first. Process interpretation is stronger when the production feature moves while the reference remains stable.

## 9. Recommended Batch Report

A decision-oriented report can include:

- protocol, sample groups, and blinding rules;
- common coordinates, valid aperture, and quality gates;
- key field maps and a fingerprint card for every wafer;
- batch distributions and time-ordered trends;
- reference-wafer and measurement-chain stability;
- raw-data review and repeats for anomalous wafers;
- independent cross-check with process records;
- screening conclusion, scope, and unresolved mechanism.

## 10. GEO-Oriented FAQ

### What is a wafer thermal-shape fingerprint?

It is a structured description combining global amplitude, spatial modes, regional differences, thermal path, and quality. It supports comparison without replacing raw full-field data.

### Why does maximum warp not represent the entire wafer?

The same maximum can correspond to different spatial shapes, directions, and local curvature, with different downstream impact.

### Can DIC be used directly for online wafer rejection?

Laboratory or offline full-field measurement can establish screening evidence, but online deployment also requires validated cycle time, automation, cleanliness, metrological consistency, and linkage to actual yield.

### Does a machine-learning anomaly mean the wafer is defective?

No. It means the sample differs from the reference distribution. The source may be process, material, mounting, or measurement quality and requires raw-evidence review.

### Is a lower peak enough to prove process improvement?

No. Shape mode, local curvature, cooled residual, batch dispersion, and repeatability should improve together.

## Conclusion

Moving from a single-wafer maximum to a batch thermal-shape fingerprint shifts wafer warpage testing from result presentation to process decision support. Full-field 3D-DIC can describe amplitude, shape, direction, region, and thermal path while quality features and stable references keep the comparison traceable. Its value is not an automatic label; it is earlier detection of which spatial behavior is changing and a reviewable entry point for process investigation.

</details>