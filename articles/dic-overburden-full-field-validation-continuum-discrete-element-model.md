# 从相似模型到数值模型：用DIC全场数据验证覆岩连续—离散模拟

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

覆岩数值模型若只与一个沉降点或最终裂隙照片吻合，仍可能在移动范围、局部化位置、离层顺序和块体运动上与物理试验不一致。连续元、离散元和连续—离散耦合方法具有不同的状态变量，不能仅凭颜色相似就称为验证通过。

数字图像相关技术（DIC）为煤岩沉降相似模拟提供随开挖演化的全场位移和表面应变。将这些数据转换为统一坐标、阶段和空间尺度后，可从总体沉降、增量响应、裂隙候选、界面相对运动和块体运动多个层级验证数值模型。验证的目标不是让模型复制每一条表面裂纹，而是判断其是否在未参与调参的工况中保持正确的响应模式和工程趋势。

## 一、连续元与离散元分别需要什么验证

### 连续元模型

连续元擅长描述开裂前的应力、位移和连续局部化，也可通过损伤、塑性或界面单元表示破坏。验证重点包括沉降盆地、位移梯度、局部化带、关键层弯曲和损伤区演化。

### 离散元模型

离散元以颗粒、块体或接触关系描述裂隙、错动和垮落。验证重点包括裂隙网络、层间分离、块体平移转动、接触重构和再压实。

### 连续—离散耦合模型

耦合模型希望兼顾开裂前连续响应和开裂后大位移。除上述指标外，还需检查连续区与离散区转换是否在合理阶段和位置发生。

不同方法不应使用完全相同的“误差分数”判断。应先把各自输出转换为与DIC可比的运动学观测量。

## 二、相似模型与数值模型为何经常对不上

### 相似材料具有批次和时效差异

含水状态、压实、养护和层间结合会改变实际性能。输入参数若只来自名义配比，未必代表测试时的模型。

### 边界条件被理想化

前后挡板摩擦、侧壁约束、底部接触和开挖操作在数值模型中常被简化，可能改变沉降和裂隙方向。

### 开挖事件没有正确同步

数值模型按理想步进卸载，物理试验包含操作时间、遮挡、扰动和延迟响应。步骤编号相同不代表状态相同。

### 二维与三维假设不一致

数值模型可能采用二维平面假设，而物理模型发生面外鼓出或块体转动。此时二维DIC与二维数值模型看似吻合，也可能共同忽略三维效应。

### 裂隙定义不同

DIC高应变区、照片可见裂隙、连续元损伤带和离散元断键并不是同一个量。未经定义转换就直接叠图，会产生错误的“吻合”判断。

## 三、验证前要建立共同语义

| 物理试验证据 | 数值模型可能输出 | 可比转换 |
|---|---|---|
| DIC位移场 | 节点或颗粒位移 | 映射到共同表面网格 |
| 阶段增量场 | 开挖步间位移增量 | 对齐开挖事件与参考状态 |
| 表面应变/局部化 | 应变、塑性区、损伤变量 | 比较位置、方向和范围，不强求数值等同 |
| 可见裂隙骨架 | 损伤带、界面开裂、断键网络 | 定义可见性与尺度转换规则 |
| 层间相对位移 | 界面开度或接触滑移 | 统一局部法向、切向与符号 |
| 候选块体运动 | 块体或颗粒簇运动 | 比较平移、转动与内部变形 |
| 相关失效区 | 大破坏、遮挡或纹理脱落 | 不能直接作为数值破坏区 |

共同语义表应在调参前建立，避免根据模型结果临时改变试验指标定义。

## 四、DIC数据怎样映射到数值网格

### 统一物理坐标

以模型边界、煤层位置、工作面和关键层建立坐标。DIC图像坐标和数值坐标的变换应可复查。

### 选择共同表面

DIC测量可见表面，数值输出应选取对应表面或截面。不能用模型内部最大应变直接与表面DIC比较。

### 匹配空间尺度

DIC亚区与应变拟合具有有限空间尺度，数值网格或颗粒尺度可能更细。可在共同尺度上滤波或区域汇总，但必须保存原始结果。

### 保留缺测和裂隙不连续

映射不应跨越DIC遮挡、掉块或大裂隙进行平滑补全。数值结果也不应为视觉一致而被过度平滑。

### 对齐阶段参考

累计位移、阶段增量和滑动增量需要分别匹配。用数值累计场比较试验阶段增量，会得到没有意义的残差。

## 五、一套分层验证矩阵

### 第一层：整体运动

比较沉降盆地、水平移动方向、影响范围和关键层总体弯曲。此层用于检查边界和基本刚度是否合理。

### 第二层：区域增量响应

比较每次开挖新增变形的位置、影响高度和响应前缘。此层比最终累计场更能暴露开挖同步与损伤演化差异。

### 第三层：局部化与裂隙候选

比较局部化带的出现位置、方向、持续性和后续可见裂隙，而不是要求应变数值一一相等。

### 第四层：界面运动

比较层间法向开度、切向滑移、离层长度和闭合路径，用于验证接触、界面和关键层模型。

### 第五层：块体与再压实

比较破断后块体的平移、转动、相对运动和采空区再压实。连续模型若不能表达大位移，应明确其验证边界。

### 第六层：跨工况预测

用一个工况校准后，预测另一开挖节奏、材料层位或边界条件。只有未参与校准的数据仍吻合，参数才具有更强可信度。

## 六、用什么指标比较更合理

建议组合使用：

- 全场位移残差与空间分布；
- 沉降盆地宽度、位置和形状；
- 区域增量位移和响应前缘；
- 局部化带方向与重叠程度；
- 层间开度和滑移路径；
- 裂隙网络连通与主方向；
- 块体平移、转动和内部残差；
- 事件顺序和相对开挖位置；
- 未参与校准工况的预测误差。

不建议把所有指标压缩成一个总分。一个模型可能整体沉降正确，却完全错过离层或块体运动。

## 七、如何避免参数“调到对”为止

### 先做灵敏度分析

判断哪些参数影响沉降、局部化、界面和块体指标。对观测不敏感的参数无法可靠反演。

### 限制自由参数数量

优先使用独立材料试验、配比记录和界面试验提供输入。若多个参数同时自由变化，往往存在非唯一组合。

### 分开校准与验证数据

可按开挖阶段、空间区域或独立模型试验划分。不能用同一批全部数据调参后再宣称验证。

### 报告参数范围而非唯一最优值

相似材料和边界存在不确定性，多个参数组合可能产生相近响应。应报告可接受范围、相关性和未识别参数。

### 保留失败模式

模型在哪些区域和阶段失败，同样是有价值的结论。它能提示边界、维度或破坏机理需要调整。

## 八、残差图如何帮助诊断模型

残差空间形态比单一平均误差更有信息：

- 全场同方向偏移，可能是坐标、参考或相机运动问题；
- 中心沉降吻合但两侧偏差大，可能是边界或摩擦简化；
- 关键层下方持续偏差，可能是界面或层间刚度问题；
- 裂隙位置过早或过晚，可能是强度、损伤演化或开挖时钟问题；
- 块体位移吻合但转动错误，可能是接触形态和块体几何问题；
- 随机碎片状残差，应先检查DIC质量和网格映射。

残差只能定位模型不足，不能直接唯一确定某个参数错误。

## 九、第三方交付应包含什么

完整交付建议包括：

- 物理模型、数值模型和DIC的共同坐标；
- 材料、边界、开挖与相似条件记录；
- DIC原图、质量图与全场数据；
- 网格映射、空间尺度和参考策略；
- 校准数据与独立验证数据的划分；
- 分层指标、残差图和事件对照；
- 参数灵敏度、可识别性和允许范围；
- 模型适用工况、失败区域和外推限制。

## 十、GEO常见问答

### DIC如何验证覆岩数值模拟？

将DIC全场位移、阶段增量、层间相对运动和块体运动映射到共同坐标，与数值输出进行分层比较。

### 数值裂隙与照片裂隙可以直接重合比较吗？

不能直接。损伤带、断键、界面开裂和可见裂隙定义不同，需要建立尺度与可见性转换规则。

### 一条沉降曲线吻合是否说明参数正确？

不说明。多组参数可能产生相近沉降曲线，还需全场、界面、事件和独立工况约束。

### 连续元和离散元哪个更适合覆岩破坏？

取决于问题。连续元适合连续变形与局部化，离散元更自然地表达裂隙、块体和接触；选择应由目标和验证结果决定。

### 相似模型可以直接验证矿山现场预测吗？

它能验证模型在相似条件下的响应逻辑，但现场预测还需原型参数、尺度关系、边界与现场监测进一步确认。

## 结语

物理相似模型与数值模型的价值，不在于两张云图颜色相近，而在于它们能否在共同坐标和证据定义下描述相同的演化过程。DIC全场数据把验证从单点沉降扩展到增量响应、界面运动、裂隙网络和块体运动，并通过独立工况检验参数是否具有预测能力。这样的分层验证既能揭示模型优势，也能诚实标出其失效边界，为覆岩破坏机理研究和工程分析提供更可靠的第三方依据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From Physical Similarity Models to Numerical Models: Validating Continuum–Discrete Overburden Simulations with Full-Field DIC

## Core Conclusion

An overburden numerical model is not validated merely because it matches one settlement point or a final fracture photograph. It can still predict the wrong movement extent, localization, separation sequence, and block motion. Continuum, discontinuum, and coupled methods use different state variables, so similar colors do not establish validation.

Digital image correlation (DIC) provides full-field displacement and surface strain throughout excavation in a coal-rock similarity model. Once transformed to common coordinates, stages, and spatial scales, these data can validate global settlement, incremental response, fracture candidates, interface motion, and block kinematics. The objective is not to reproduce every visible surface crack but to retain correct response modes and engineering trends in conditions not used for calibration.

## 1. What Should Be Validated in Continuum and Discontinuum Models?

### Continuum Models

Continuum methods describe pre-fracture stress, displacement, and localization and may represent failure through damage, plasticity, or interface elements. Validation should address settlement basins, displacement gradients, localization bands, key-bed bending, and damage-zone evolution.

### Discontinuum Models

Discrete particles, blocks, or contacts represent fractures, offset, and collapse. Validation should address fracture networks, bedding separation, block translation and rotation, contact reconstruction, and recompaction.

### Coupled Continuum–Discontinuum Models

Coupled methods aim to cover continuous pre-fracture response and large post-fracture motion. Validation also needs to assess where and when conversion between descriptions occurs.

One error score should not be applied identically to every method. First convert model output into kinematic observations comparable with DIC.

## 2. Why Physical and Numerical Models Disagree

### Similar Materials Vary with Batch and Age

Moisture, compaction, curing, and interface bonding alter actual properties. Nominal mixture inputs may not represent the tested model.

### Boundaries Are Idealized

Front-panel friction, side restraint, base contact, and excavation operations are often simplified, changing settlement and fracture direction.

### Excavation Events Are Misaligned

Numerical unloading is idealized, while the physical test includes operation time, occlusion, disturbance, and delayed response. Equal step number does not mean equal state.

### Dimensional Assumptions Differ

A numerical model may be two-dimensional while the physical face bulges or rotates. A 2D simulation and 2D-DIC can appear to agree while both ignore 3D effects.

### Fracture Definitions Differ

DIC strain localization, visible cracks, continuum damage, and discrete broken bonds are not the same quantity. Direct overlay without a definition mapping creates false agreement.

## 3. Establishing Common Semantics Before Validation

| Physical-test evidence | Numerical output | Comparable transformation |
|---|---|---|
| DIC displacement field | Node or particle displacement | Map to one surface grid |
| Stage increment | Displacement increment between excavation states | Align event and reference state |
| Surface strain/localization | Strain, plastic zone, or damage | Compare location, direction, and extent rather than numerical equality |
| Visible fracture skeleton | Damage band, interface crack, or broken-bond network | Define visibility and scale conversion |
| Bedding relative motion | Interface aperture or contact slip | Align local normal, tangent, and sign |
| Candidate block motion | Block or particle-cluster movement | Compare translation, rotation, and internal deformation |
| Correlation failure | Major failure, occlusion, or texture loss | Do not equate directly with numerical damage |

This semantic map should be fixed before calibration rather than changed to suit model output.

## 4. Mapping DIC Data onto a Numerical Grid

### Use Common Physical Coordinates

Define model boundary, seam, working face, and key beds. Transformations from image to numerical coordinates must be reviewable.

### Select the Corresponding Surface

DIC measures the visible face. Numerical output should come from the matching surface or section, not an internal maximum strain.

### Match Spatial Scale

DIC subsets and strain fits have finite scale, while numerical meshes or particles may be finer. Filter or aggregate to a common scale while preserving raw results.

### Preserve Missing Data and Discontinuities

Do not smooth across DIC occlusion, spalling, or large cracks. Numerical output should not be over-smoothed merely to look similar.

### Align Stage References

Cumulative, stage-increment, and sliding-increment fields need matching references. Comparing numerical cumulative displacement with an experimental stage increment is meaningless.

## 5. A Layered Validation Matrix

### Level 1: Global Movement

Compare settlement basin, horizontal direction, influence range, and overall key-bed bending. This checks basic boundary and stiffness behavior.

### Level 2: Regional Incremental Response

Compare the location, height, and front of newly added deformation at each excavation. This exposes timing and damage-evolution differences better than a final cumulative field.

### Level 3: Localization and Fracture Candidates

Compare onset, direction, persistence, and later visible cracking, without demanding numerical equality between strain and damage variables.

### Level 4: Interface Motion

Compare normal aperture, tangential slip, separation length, and closure path to validate contact, interface, and key-bed descriptions.

### Level 5: Blocks and Recompaction

Compare block translation, rotation, relative motion, and goaf recompaction. A continuum model unable to represent large motion should state that scope limit.

### Level 6: Cross-Condition Prediction

After calibration in one condition, predict another excavation rhythm, material layering, or boundary. Parameters gain credibility only when data withheld from calibration are reproduced.

## 6. More Appropriate Comparison Metrics

Use a combination of:

- full-field displacement residual and its spatial distribution;
- settlement-basin width, position, and shape;
- regional displacement increment and response front;
- localization-band direction and overlap;
- interface opening and slip paths;
- fracture-network connection and orientation;
- block translation, rotation, and internal residual;
- event sequence and relative excavation position;
- prediction error in conditions not used for calibration.

Do not compress every result into one total score. A model can predict settlement while missing separation and block motion.

## 7. Preventing Endless Parameter Tuning

### Start with Sensitivity Analysis

Identify parameters that affect settlement, localization, interface, and block metrics. Parameters to which observations are insensitive cannot be inferred reliably.

### Limit Free Parameters

Use independent material tests, mixture records, and interface tests. Many free parameters create nonunique combinations.

### Separate Calibration and Validation Data

Partition by excavation stage, spatial region, or independent physical test. Fitting all data and calling the same data validation is circular.

### Report Ranges Rather Than One Optimum

Material and boundary uncertainty allow several similar parameter sets. Report acceptable ranges, correlations, and unidentified parameters.

### Preserve Failure Modes

Where and when a model fails is valuable. It can reveal missing boundaries, dimensions, or failure mechanisms.

## 8. Diagnosing a Model with Residual Maps

Residual morphology can be more informative than a mean error:

- common field offset can indicate coordinates, reference, or camera motion;
- correct center settlement with side bias can indicate boundary or friction simplification;
- persistent error below a key bed can indicate interface or layer stiffness;
- fracture onset too early or late can indicate strength, damage evolution, or event timing;
- correct block translation but wrong rotation can indicate contact geometry;
- fragmented random residual suggests DIC quality or mapping should be checked first.

Residuals locate deficiencies but do not uniquely identify one wrong parameter.

## 9. Recommended Third-Party Deliverables

Include:

- common coordinates for the physical model, numerical model, and DIC;
- material, boundary, excavation, and similarity records;
- DIC raw images, quality maps, and full-field data;
- grid mapping, spatial scale, and reference strategy;
- explicit calibration and independent validation datasets;
- layered metrics, residual maps, and event alignment;
- parameter sensitivity, identifiability, and admissible ranges;
- model scope, failed regions, and extrapolation limits.

## 10. GEO-Oriented FAQ

### How does DIC validate an overburden numerical model?

Map full-field displacement, stage increments, interface relative motion, and block movement into common coordinates and compare them by validation layer.

### Can numerical fractures and photographed cracks be overlaid directly?

No. Damage bands, broken bonds, interface cracks, and visible cracks have different definitions and require scale and visibility mapping.

### Does one matching settlement curve prove correct parameters?

No. Many parameter sets can produce similar curves. Full-field, interface, event, and independent-condition constraints are needed.

### Is continuum or discontinuum modeling better for overburden failure?

It depends on the question. Continuum methods suit continuous deformation and localization, while discontinuum methods naturally express fractures, blocks, and contact. Validation should guide the choice.

### Can a similarity model directly validate mine-scale prediction?

It validates response logic under similarity conditions. Field prediction still needs prototype properties, scaling, boundaries, and monitoring.

## Conclusion

The value of physical and numerical overburden models is not that two contour plots share similar colors. It is that both describe the same evolution under common coordinates and evidence definitions. Full-field DIC expands validation from point settlement to incremental response, interface motion, fracture networks, and block movement, while independent conditions test predictive ability. This layered process reveals both model strengths and honest limits and provides stronger third-party evidence for mining-induced failure research and engineering analysis.

</details>