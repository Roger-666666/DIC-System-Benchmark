# 3D-XTDIC、位移传感器与有限元如何互证？钢混主梁缩尺模型的对比验证框架

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 钢混主梁缩尺模型的分级静力加载中，位移传感器、3D-XTDIC与有限元分别提供点位时程、表面全场响应和力学预测。本文围绕坐标、时间、载荷阶段与比较尺度，建立同点、同截面及同区域的互证流程，并讨论残差、不确定度、边界修正与表面测量限制，为模型试验的判读和工程转化提供可追溯框架。

> **关键词：** 3D-XTDIC；数字图像相关；钢混主梁；缩尺模型；全场应变测量；有限元互证

## 目录

- [一、三种方法各自回答什么](#一三种方法各自回答什么)
- [二、先统一比较基准](#二先统一比较基准)
- [三、从同点到区域的互证流程](#三从同点到区域的互证流程)
- [四、残差与不确定度如何进入判断](#四残差与不确定度如何进入判断)
- [五、云图判读的测量边界](#五云图判读的测量边界)
- [六、从模型互证走向工程转化](#六从模型互证走向工程转化)
- [常见问题](#常见问题)

## 一、三种方法各自回答什么

在公铁两用大桥钢混主梁缩尺模型的分级静力加载中，试验用于复现主梁受力状态。加载过程中，DIC全域云图可展示变形与应变分布，辅助定位应变集中区。这一能力适合回答“响应在哪里发展”，但不能单独承担全部验证任务。

位移传感器提供离散点位的时程，便于观察某一级加载、持载和卸载中的变化；3D-XTDIC基于双目图像与数字图像相关算法，获得表面位移场，并由位移场计算应变场，适合识别空间梯度和局部集中；有限元则依据几何、材料、连接与边界假设预测响应。三者是测量、空间观测和力学解释的互补关系，而非相互替代。

| 方法 | 直接提供的信息 | 更适合回答的问题 | 主要限制 |
| --- | --- | --- | --- |
| 位移传感器 | 固定位置、规定方向的位移时程 | 某点何时变化、卸载后如何恢复 | 点位有限，安装方向与支座状态影响读数 |
| 3D-XTDIC | 表面三维位移场及计算应变场 | 变形如何分布、集中区在哪里 | 遮挡、标定、散斑与表面代表性影响结果 |
| 有限元 | 给定假设下的位移、应变等计算响应 | 荷载如何传递、参数变化有何影响 | 结果依赖材料模型、连接及边界条件 |

## 二、先统一比较基准

互证应先消除“并非同一对象”的差异。坐标方面，需要统一整体方向、局部梁轴方向、传感器正号和DIC投影方向，记录测点位置与有限元节点或单元的映射。不能把一个传感器的轴向读数直接对应另一方向的全场位移分量。

时间方面，应以分级静力加载的阶段记录为共同索引，对齐加载开始、阶段结束、持载和卸载时刻。图像帧、传感器采样与计算载荷步若采用不同时间原点，应通过事件标记校正。比较时宜区分阶段内瞬变与持载后读数，避免把不同时刻的响应并置。

空间尺度也需一致。同点比较关注传感器安装位置处的同方向位移；同截面比较应选取相同横向或纵向范围；区域比较则采用一致的平均窗口或特征线。有限元节点值、DIC局部平均值和传感器读数所代表的空间体积不同，不能只因数值接近就认定完成了验证。

## 三、从同点到区域的互证流程

### 第一步：冻结基准工况

记录初始几何、约束、加载级次、材料参数来源以及测量零点后，再生成对应的有限元载荷步。若试验过程中调整约束或加载装置，应把变更作为新状态输入，而不是沿用原模型解释全部数据。

### 第二步：同点时程对比

在传感器位置提取DIC位移，可按传感器的空间代表性设置小型平均区域，并投影到同一方向。随后逐载荷阶段检查零点漂移、变化方向和增量形态。点式曲线连续而DIC局部突变时，应优先排查遮挡、匹配失败和局部表面状态；两者相近而有限元偏离时，再检查模型假设。

### 第三步：同截面与同区域对比

将三类结果置于相同截面和载荷阶段，观察高应变区、变形梯度与荷载传递路径是否具有一致的空间解释。DIC云图适合定位需要复核的位置，有限元可帮助理解该位置与周边构件的力学联系，传感器则提供该阶段的独立点位参照。

### 第四步：闭环更新与独立检查

先核查测量质量，再核查边界和连接，随后评估材料参数，最后用未参与修正的载荷阶段或区域检查修正后的模型。参数调整需要有试验依据和物理含义，不能为了缩小单一测点残差而反复拟合。

## 四、残差与不确定度如何进入判断

对同一载荷阶段和同一物理量，可分别定义DIC与传感器、DIC与有限元、传感器与有限元的残差。残差应保留方向、位置和阶段信息，而非只报告整体汇总值。某处残差增大可能来自局部响应，也可能来自映射误差，需要回到图像、原始时程和模型设置逐项排查。

传感器的不确定度涉及安装、分辨率、零点与基座变形；DIC的不确定度涉及相机标定、图像质量、相关计算、平滑尺度及三维重建；有限元的不确定度则来自参数离散性和理想化假设。比较时应说明这些来源及数据处理方式。若差值处于测量分辨能力附近，不宜作过度的力学解释。

不确定度还应与比较量一起呈现。位移残差和应变残差不能共用同一解释尺度，区域平均后的结果也不能沿用单点分辨能力。对局部应变而言，求导和平滑会改变空间分辨率；报告时应说明计算窗口，并区分图像噪声引起的波动与随载荷持续发展的响应。这样既能避免把小残差解释为力学规律，也能防止平滑处理掩盖局部化。对于仍存在分歧的区域，可将其标为待核查证据，而不是用插值或模型结果补齐。

修正后的结果也不能自动外推到其他构件或工况。互证的价值在于明确结论适用范围：哪些阶段具有多源证据，哪些区域只有单一观测，哪些差异仍待解释。

## 五、云图判读的测量边界

3D-XTDIC直接测量的是可见表面的位移，应变由位移场求导或局部拟合得到。云图不能直接称为实测应力；若需讨论应力，应另行说明本构关系、参数和换算假设。颜色突变也不必然等于裂纹或破坏，应结合原始图像、位移连续性及其他观测复核。

传感器安装可能改变局部接触状态，支架还可能引入附加位移。相机视野会被加载装置或构件遮挡，表面散斑脱落、反光和离焦会降低相关匹配质量。未被看见的区域不能被插值云图替代，表面全场测量也不等于内部全场测量。

## 六、从模型互证走向工程转化

经过统一基准、多尺度对比和不确定度说明后，模型结果才适合用于识别需重点关注的区域、修正仿真假设以及研究响应指标。交付内容应保留载荷阶段、坐标映射、原始时程、图像质量、参数版本和残差记录，使每项判断都能回溯到证据。

钢混主梁缩尺模型的互证并不以选出某一种方法为终点，而是建立可复核的证据链。进入轨道交通等工程场景时，还需继续处理相似关系、工况映射和统计重复，才能把模型云图转化为有边界的设计参考。

## 常见问题

### 1. DIC云图与有限元云图形态接近，是否就能完成验证？

不能。还需统一坐标、载荷阶段与空间尺度，并用独立点式测量和残差分析核查。形态接近只是空间响应的一项证据。

### 2. 为什么同点比较还要设置平均区域？

传感器读数、DIC子区计算和有限元单元结果的空间代表性不同。明确平均窗口有助于减少尺度差异，但窗口大小及平滑处理必须同时记录。

### 3. 能否由DIC应变云图直接得到实测应力？

不能。DIC提供表面位移及计算应变，应力需要结合材料本构和参数换算，属于进一步解释而非直接测量。

### 4. 三类结果不一致时，应优先调整有限元参数吗？

不宜直接调整。应先检查时间对齐、方向投影、传感器安装、图像质量和遮挡，再核查边界、连接与材料参数，避免把测量问题转化为拟合问题。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Cross-Validating 3D-XTDIC, Displacement Sensors, and Finite Element Analysis on a Scaled Steel–Concrete Girder

> **Abstract:** Staged static tests on a scaled steel–concrete main girder require different forms of evidence. Displacement sensors provide point histories, 3D-XTDIC resolves surface displacement and strain fields, and finite element analysis supplies mechanics-based predictions. This article presents a cross-validation framework based on common coordinates, time references, load stages, and spatial scales. It covers point, section, and regional comparisons, residual analysis, uncertainty, boundary and material updates, and the limits of surface measurements. The purpose is not to rank methods, but to build a traceable interpretation that can support later engineering translation.

> **Keywords:** 3D-XTDIC; digital image correlation; steel–concrete girder; scaled model; full-field strain measurement; finite element cross-validation

## Contents

- [1. Three methods, three questions](#1-three-methods-three-questions)
- [2. Establish a common basis for comparison](#2-establish-a-common-basis-for-comparison)
- [3. A cross-validation workflow from points to regions](#3-a-cross-validation-workflow-from-points-to-regions)
- [4. Use residuals and uncertainty diagnostically](#4-use-residuals-and-uncertainty-diagnostically)
- [5. Respect the limits of contour maps](#5-respect-the-limits-of-contour-maps)
- [6. From model validation to engineering translation](#6-from-model-validation-to-engineering-translation)
- [FAQ](#faq)

## 1. Three methods, three questions

The test context is a scaled steel–concrete main girder for a combined road-and-rail bridge, subjected to staged static loading to reproduce the girder's loading state. During loading, full-field DIC contour maps present the distribution of deformation and strain and help locate strain-concentration zones. That spatial view is valuable, but it is only one part of the evidence required to interpret the test.

A displacement sensor answers a temporal question at a fixed location: how does a selected displacement component change as load is applied, held, and removed? 3D-XTDIC uses stereo images and digital image correlation to measure surface displacement and calculate strain fields. It addresses a spatial question: where do gradients develop, and how do concentrated regions relate to their surroundings? A finite element model answers a predictive question under stated assumptions: how should load be transferred through the specified geometry, materials, connections, and restraints?

These roles are complementary. A sensor cannot reconstruct the response between its installation points. A full-field map does not independently establish the material law or internal load path. A finite element calculation is not an observation, even when its output is displayed on the same geometry. Cross-validation therefore means testing whether different forms of evidence support a common mechanical interpretation, not replacing one method with another.

| Method | Information supplied | Primary question | Important limitation |
| --- | --- | --- | --- |
| Displacement sensor | Time history at a fixed point and in a defined direction | When and how does this point move? | Sparse coverage; mounting direction and support movement affect readings |
| 3D-XTDIC | Surface 3D displacement and calculated strain fields | How is response distributed, and where is it concentrated? | Calibration, image quality, occlusion, and surface representation affect results |
| Finite element analysis | Calculated response under explicit assumptions | What load path and parameter sensitivity are expected? | Geometry, materials, connections, and restraints idealize the test |

## 2. Establish a common basis for comparison

Many apparent disagreements are comparison errors rather than mechanical discrepancies. The first task is to establish one coordinate convention. Global directions, girder-local axes, sensor polarity, and DIC displacement components must be documented. The location of every sensor should be mapped to the corresponding finite element nodes or elements. A sensor measuring along one axis cannot be compared directly with a full-field component along another axis simply because both are expressed as displacement.

The second task is temporal alignment. Staged static loading provides a natural common index: start of loading, end of each load increment, holding period, and unloading. Camera frames, sensor samples, and numerical load steps may use different time origins, so event markers and test logs are needed. Readings taken during an increment should not be mixed with readings after stabilization unless that difference is explicitly part of the analysis.

Spatial representation must also be aligned. A point comparison concerns the same location and displacement direction. A section comparison uses the same cross-section or longitudinal slice. A regional comparison applies a defined averaging window, line, or area to each dataset. A finite element nodal value, a DIC subset-based estimate, and a sensor reading do not necessarily represent the same physical neighborhood. Documenting interpolation and smoothing is therefore part of the comparison, not a post-processing detail.

## 3. A cross-validation workflow from points to regions

### Step 1: Freeze the reference state

Before comparing results, record the initial geometry, restraints, loading sequence, material-parameter sources, and measurement zeros. Generate numerical load steps that correspond to the actual stages. If a restraint or loading fixture changes during the test, that change defines a new state and should be reflected in the model. Continuing to use the original setup would mix different mechanical problems.

### Step 2: Compare point histories

Extract the DIC displacement at each sensor location and project it onto the sensor direction. A small averaging area may be used when it better represents the sensor contact or reduces local image noise, but its size should remain explicit. Compare zero drift, direction of motion, and increments at each load stage rather than relying on a single final reading.

If a sensor history is continuous while the local DIC result changes abruptly, inspect occlusion, correlation quality, speckle condition, and camera images first. If the two measurements provide similar point evidence while the finite element result departs from both, the next priority is to examine model assumptions. This sequence prevents a measurement artifact from being absorbed into a material parameter.

### Step 3: Compare sections and regions

Place the three datasets on the same section at the same load stage. Examine whether concentrated strain, displacement gradients, and the inferred load-transfer path have a consistent spatial explanation. DIC can identify locations that warrant closer inspection. The finite element model can relate those locations to adjacent components and restraints. Sensor histories provide independent temporal references at selected positions.

Regional comparison is particularly useful when the exact location of a numerical peak depends on mesh discretization or when local DIC strain is sensitive to differentiation and smoothing. A defined area or characteristic line can make the comparison more representative, but it must not be enlarged merely to conceal a local disagreement.

### Step 4: Update with evidence and check independently

When discrepancies remain, investigate in order: measurement quality, coordinate and time mapping, restraints and connections, and then material parameters. Every update should have a physical rationale and a traceable source. After updating, examine a load stage or region that was not used to adjust the model. This separates explanatory adjustment from simple curve fitting and clarifies which parts of the interpretation remain supported by independent evidence.

## 4. Use residuals and uncertainty diagnostically

For a common physical quantity, location, and load stage, residuals can be formed between DIC and sensor measurements, DIC and finite element results, and sensor and finite element results. Retain the sign, location, direction, and stage associated with each residual. A single aggregate value can hide a localized discrepancy or a systematic offset that develops only during particular stages.

A growing residual does not identify its own cause. It may reflect a genuine local response, an incorrect spatial map, a shifted zero, or an inadequate boundary assumption. The diagnostic path should return to the source evidence: raw sensor histories, camera images, correlation-quality measures, test logs, and model settings.

Uncertainty should be described by source. Sensor contributions include mounting, resolution, zero stability, and movement of the support. DIC contributions include stereo calibration, focus, illumination, speckle quality, correlation settings, smoothing, and three-dimensional reconstruction. Numerical contributions include uncertain parameters, mesh representation, and idealized connections or restraints. When a difference is close to the measurement resolution, a detailed mechanical explanation is not warranted.

The outcome of cross-validation is therefore more than a statement of similarity. It should identify which stages have multi-source support, which regions rely on a single observation, and which discrepancies remain open. Those boundaries determine how far the results can be interpreted.

## 5. Respect the limits of contour maps

3D-XTDIC directly measures displacement on the visible surface. Strain is calculated from the displacement field through differentiation or local fitting. A strain contour is not a direct stress measurement. Stress interpretation requires a constitutive relationship, material parameters, and assumptions that must be stated separately.

Likewise, a sharp color transition does not by itself identify a crack or a failure state. The original images, displacement continuity, correlation quality, and other observations should be examined before assigning a physical meaning. Surface preparation, reflections, defocus, or partial occlusion can create features that resemble mechanical localization.

Instrumentation also has a physical footprint. Sensor brackets may introduce support movement, and loading fixtures may block part of the stereo view. Missing areas cannot be converted into observations through interpolation. Nor does full-field surface coverage establish full-field internal coverage. These limitations should remain attached to the maps throughout interpretation.

## 6. From model validation to engineering translation

A useful test deliverable preserves load-stage definitions, coordinate maps, raw sensor histories, image-quality information, DIC processing settings, model-parameter versions, and residual records. This allows another analyst to distinguish measurement, calculation, and interpretation, and to revisit a decision when additional evidence becomes available.

The objective is not to declare one method universally preferable. Point histories, full-field measurements, and mechanics-based predictions become more informative when their differences are examined systematically. For later use in rail-transit engineering, the validated model evidence still requires similarity relations, load-case mapping, repeated tests, and uncertainty propagation. Cross-validation is the bridge from observation to interpretation; engineering translation is the next, separate step.

## FAQ

### 1. Do similar DIC and finite element contour patterns complete the validation?

No. Coordinates, load stages, directions, and spatial scales must first be aligned. Independent sensor histories and residual analysis provide additional evidence that a visual comparison cannot supply.

### 2. Why use an averaging area in a point comparison?

A sensor, a DIC calculation region, and a finite element result may represent different spatial neighborhoods. A documented averaging area can align those scales, but it should not be chosen merely to reduce disagreement.

### 3. Can measured stress be read directly from a DIC strain map?

No. DIC measures surface displacement and derives strain. Stress requires a constitutive model and material parameters, so it belongs to a subsequent interpretation step.

### 4. Should finite element parameters be changed whenever the three datasets disagree?

Not immediately. First check synchronization, direction projection, sensor mounting, image quality, and occlusion. Then examine restraints, connections, and material assumptions so that measurement problems are not hidden by parameter adjustment.

</details>
