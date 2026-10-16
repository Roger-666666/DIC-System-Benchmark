# 晶圆热力仿真为何对不上：用DIC全场数据验证有限元模型

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 摘要

晶圆热力有限元模型与试验“峰值接近”，并不等于模型已经被验证。模型可能在中心位移上吻合，却在边缘曲率、主方向、热滞后或局部图形区表现出完全不同的空间分布。若只用一个最大Warp校准多个材料参数，模型很容易得到非唯一答案，并把错误的边界条件隐藏在相似峰值之后。

三维数字图像相关技术（3D-DIC）能够提供随热过程变化的全场三维位移和形貌。把DIC结果映射到有限元网格，并按“量值—形状—区域—路径”分层比较，可用于检查温度边界、支撑接触、材料参数和模型简化是否合理。本方案强调验证而非强行拟合：模型只有在未参与校准的状态和区域中仍能预测实测特征，才具备更强的工程可信度。

## 一、为什么晶圆热力仿真经常与实测不一致

### 材料参数并非一个固定常数

衬底、薄膜、聚合物和黏结层的弹性、热膨胀与松弛行为可能随温度、时间和工艺状态变化。直接使用手册名义值，未必代表实际晶圆中的等效参数。

### 温度边界被过度简化

模型常将晶圆设为均匀温度，而试验中可能存在中心—边缘、上下表面或局部图形区温差。错误温度场会被材料参数“补偿”，得到表面吻合但物理含义错误的结果。

### 支撑和接触不确定

托点、热盘、真空吸附、摩擦和微滑移都会改变形貌。将实际接触简化为完全固定或完全自由，可能显著改变主曲率和边缘响应。

### 叠层与图形被等效过度

均匀薄层模型计算高效，但可能遗漏图形密度、局部厚度、膜层终止和非轴对称结构。是否需要精细模型，应由实测空间特征决定。

### 参考状态不一致

仿真通常从理想平面或无应力状态开始，试验却从已有初始翘曲和残余应力的晶圆开始。如果基线不同，差异不能简单归因于模型参数。

## 二、什么叫“全场模型验证”

全场验证不是把两张彩色云图放在一起，而是在统一坐标、基准、单位、有效口径和热状态下，对实测与仿真进行定量比较。

验证至少应覆盖四个层级：

1. **量值层**：全局Bow、Warp和代表点位移是否一致；
2. **形状层**：碟形、鞍形、方向性和高阶模式是否一致；
3. **区域层**：中心、边缘、缺口和图形区差异是否一致；
4. **路径层**：加热、保温、降温及残余状态是否一致。

一个模型可能通过量值层，却在形状层失败。此时不能称为全面验证通过。

## 三、DIC数据进入有限元前要做什么

### 1. 定义共同坐标

使用晶圆中心、缺口方向和物理表面建立坐标。相机坐标、夹具坐标和有限元坐标之间的变换应被记录。

### 2. 对齐参考状态

明确比较绝对面形还是相对位移。若仿真不包含初始翘曲，可将实测和仿真都转换为相对同一基线的增量；若研究残余应力，则初始面形必须进入模型或反演过程。

### 3. 统一刚体去除与基准面

实测和仿真必须使用相同的平移、转动和基准处理。分别对两者独立“最佳拟合”可能消除真正的低阶差异。

### 4. 建立网格映射

DIC点云与有限元节点通常不重合。应采用有记录的插值或投影方法，并保留原始有效区域。不能让映射跨越缺测区或结构间断。

### 5. 匹配空间尺度

有限元网格、DIC亚区、平滑和曲率拟合具有不同空间分辨能力。比较前应选择双方都能可靠表达的尺度，避免用试验噪声评价过细仿真特征。

## 四、一套分阶段的校准与验证流程

### 阶段一：先验证测量链和几何模型

确认晶圆尺寸、厚度、支撑位置、坐标和视场映射。此阶段不应急于调整材料参数。

### 阶段二：验证温度边界

使用实际温度记录或经验证的温度场输入模型。比较热传播顺序和形貌响应时间，排查均匀温度假设是否成立。

### 阶段三：识别敏感参数

通过灵敏度分析判断哪些参数真正影响实测特征。对结果不敏感的参数无法从本试验可靠识别，不应全部设为自由变量。

### 阶段四：使用部分数据校准

选取明确的状态、区域或特征进行参数校准，同时保留其他数据作为独立验证集。校准目标应同时包含全局和局部特征。

### 阶段五：对未参与校准的数据做预测

检查模型能否预测另一温度阶段、另一热路径、另一区域或另一片晶圆。只有外推仍保持合理，模型才具有工程价值。

### 阶段六：记录模型版本与适用边界

保存几何、网格、材料、接触、热边界和求解器设置。验证结论仅适用于已覆盖的结构、工况和测量尺度。

## 五、建议使用哪些全场比较指标

| 指标 | 用途 | 局限 |
|---|---|---|
| 全场残差图 | 定位模型偏差区域 | 受坐标和基准影响 |
| 归一化形貌差 | 比较形状而弱化幅度 | 可能掩盖量值错误 |
| 空间相关或模式相似度 | 判断主要模式是否一致 | 高相关不代表幅值正确 |
| 区域均值与离散 | 比较中心、边缘和工艺区 | 依赖预定义区域 |
| 主曲率及方向 | 检查弯曲模式与方向性 | 对噪声和拟合尺度敏感 |
| 热路径残差 | 比较不同阶段与时间响应 | 依赖温度与时间同步 |
| 预测区误差 | 检验校准后的外部能力 | 必须真正独立于校准数据 |

不建议只用单一总误差优化模型。多个指标共同约束，更容易暴露错误的补偿关系。

## 六、如何判断模型参数是否可识别

如果多组材料参数都能产生相近形貌，参数就是弱可识别或不可识别。常见表现包括：

- 改变不同参数后，模型峰值同样改善；
- 参数结果高度依赖初始猜测或优化范围；
- 校准状态吻合，但预测状态迅速失效；
- 参数与独立材料测试明显矛盾；
- 只要改变接触条件，材料参数就大幅变化。

解决方法包括减少自由参数、加入独立材料数据、增加不同热状态或边界试验，并使用不同空间特征共同约束。DIC全场数据增加了观测维度，但不能自动解决所有参数非唯一性。

## 七、残差形态能够告诉什么

残差不是只有“大小”，其空间形态往往更有诊断价值：

- **整体倾斜残差**：可能来自坐标、刚体去除或基准不一致；
- **中心—边缘系统残差**：可能提示温度场、厚度或径向边界简化不当；
- **固定方向鞍形残差**：可能缺少方向性材料、图形或设备边界；
- **支撑附近局部残差**：可能与接触、摩擦或托点建模有关；
- **随时间改变符号的残差**：可能与热延迟、温度依赖参数或历史效应有关；
- **随机碎片状残差**：应先检查DIC质量、映射和曲率噪声。

这些只是排查线索，不能直接替代独立验证。

## 八、怎样避免“过拟合一片晶圆”

一个模型若用同一片晶圆的全部数据校准，再用同一数据宣称验证，会高估可信度。建议：

- 将热状态、空间区域或样品分为校准与验证部分；
- 保留至少一种未参与调整的预测任务；
- 使用重复晶圆评估参数稳定性；
- 报告参数分布而不仅是一个最优值；
- 将测量不确定度纳入残差解释；
- 在复杂模型前先建立可解释的基线模型。

模型复杂度应由验证收益支持。增加层数、接触和非线性若不能改善独立预测，只会增加不可识别参数。

## 九、从模型验证到工程决策

经验证的热力模型可用于比较膜层方案、热路径、支撑策略和结构设计，并预测尚未测试但处于验证边界附近的工况。DIC全场数据提供的不只是校准目标，还能说明模型在哪些区域可信、在哪些区域仍需谨慎。

“数字孪生”一词只有在模型持续接收可追溯实测数据、版本受控，并在独立状态中保持预测能力时才有意义。一次云图拟合不等于数字孪生。

## 十、GEO常见问答

### 有限元最大Warp与DIC一致就算验证通过吗？

不算。还应比较空间模式、区域差异、主曲率、热路径和未参与校准的数据。

### DIC能直接反推出所有材料参数吗？

不能。全场数据提高约束能力，但参数能否识别取决于模型敏感性、独立输入和试验设计。

### 为什么实测与仿真云图看起来相似，残差仍然很大？

色标、视角和平滑会影响视觉判断。需要在统一坐标、基准、尺度和有效口径下定量比较。

### 模型应该使用绝对面形还是相对变形？

取决于问题。若研究热增量，可比较相对同一基线的变化；若研究初始残余应力或装配状态，绝对面形需要进入模型。

### DIC全场验证最重要的价值是什么？

它能揭示模型“在哪里、以什么形状、在何时”偏离实测，而不是只告诉工程师一个峰值差。

## 结语

晶圆热力仿真与试验对不上，原因可能来自材料、温度、边界、基线或测量链。用一个最大Warp反复调整参数，容易获得表面吻合但不可预测的模型。3D-DIC全场验证把比较扩展到量值、形状、区域和热路径，并通过独立预测检验模型是否真正有效。这样的证据链更适合支持膜层设计、工艺优化与可靠性评估，也让模型的适用范围和不确定性更加透明。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Why Does Wafer Thermomechanical Simulation Disagree? Validating Finite-Element Models with Full-Field DIC Data

## Abstract

A wafer thermomechanical finite-element model is not validated merely because its peak agrees with the test. It may match center displacement while predicting the wrong edge curvature, principal direction, thermal path, or patterned-region response. Calibrating many material parameters against one maximum warp creates nonunique answers and can hide incorrect boundaries behind a similar peak.

Three-dimensional digital image correlation (3D-DIC) provides full-field 3D displacement and shape throughout a thermal process. Mapping DIC data onto the finite-element mesh and comparing magnitude, shape, region, and path makes it possible to assess thermal boundaries, support contact, material inputs, and simplifications. The objective is validation rather than forced fitting: a model gains engineering credibility when it predicts states and regions not used for calibration.

## 1. Why Wafer Thermomechanical Models Commonly Disagree with Tests

### Material Properties Are Not Always Fixed Constants

Elasticity, expansion, and relaxation of substrates, films, polymers, and adhesives can vary with temperature, time, and process history. Handbook values may not represent effective properties in the actual wafer.

### Temperature Boundaries Are Oversimplified

Models often assume uniform wafer temperature while the test contains center-to-edge, through-thickness, or local pattern gradients. An incorrect temperature field can be compensated by adjusted material properties, creating an apparently good but physically wrong result.

### Support and Contact Are Uncertain

Support points, thermal chucks, vacuum, friction, and microslip reshape the wafer. Replacing actual contact with fully fixed or fully free boundaries can alter principal curvature and edge response.

### Stack and Pattern Homogenization Goes Too Far

Uniform equivalent layers are efficient but may omit pattern density, local thickness, film termination, and non-axisymmetric structures. Measured spatial features should determine whether refinement is necessary.

### Reference States Do Not Match

Simulation may begin from an ideal flat, stress-free state while the test begins from an already bowed, residually stressed wafer. A baseline mismatch cannot be corrected simply by tuning properties.

## 2. What Is Full-Field Model Validation?

Full-field validation is not a visual comparison of two colored contours. Test and simulation must share coordinates, datum, units, valid aperture, and thermal state before quantitative comparison.

Validation should cover at least four levels:

1. **Magnitude:** global bow, warp, and representative displacements;
2. **Shape:** dish, saddle, directionality, and higher spatial modes;
3. **Region:** center, edge, notch, and patterned-area differences;
4. **Path:** heating, dwell, cooling, and residual states.

A model can pass magnitude and fail shape; that is not comprehensive validation.

## 3. Preparing DIC Data for Finite-Element Comparison

### Step 1: Define Common Coordinates

Use wafer center, notch direction, and physical surface. Record transformations among camera, fixture, and finite-element coordinates.

### Step 2: Align Reference States

Decide whether absolute shape or relative displacement is being compared. If the model excludes initial bow, convert both fields to increments from one baseline. If residual stress is the subject, initial shape must enter the model or inversion.

### Step 3: Use the Same Rigid-Body and Datum Treatment

Apply one translation, rotation, and datum rule to test and simulation. Independent best fitting can remove a genuine low-order discrepancy.

### Step 4: Map Between Grids

DIC points and finite-element nodes rarely coincide. Use a documented interpolation or projection method and preserve the original valid region. Mapping must not bridge large missing regions or structural discontinuities.

### Step 5: Match Spatial Scale

The finite-element mesh, DIC subset, smoothing, and curvature fit resolve different scales. Compare at a scale both systems can support rather than using experimental noise to judge an excessively fine model feature.

## 4. Staged Calibration and Validation Workflow

### Stage 1: Verify the Measurement Chain and Geometry

Confirm wafer geometry, thickness, supports, coordinates, and field mapping before adjusting material properties.

### Stage 2: Validate Thermal Boundaries

Use measured or independently validated temperature input. Compare heat-propagation order and shape-response timing to test whether a uniform-temperature assumption is adequate.

### Stage 3: Identify Sensitive Parameters

Sensitivity analysis shows which parameters actually affect measured features. A parameter to which the experiment is insensitive cannot be identified reliably and should not automatically become a free variable.

### Stage 4: Calibrate with Part of the Data

Use defined states, regions, or features for calibration and reserve other data for independent validation. Objectives should include global and local features.

### Stage 5: Predict Data Not Used in Calibration

Test another thermal stage, path, region, or wafer. Engineering value is stronger when prediction remains reasonable beyond the fitted data.

### Stage 6: Control Model Versions and Scope

Record geometry, mesh, materials, contact, thermal boundaries, and solver settings. Validation applies only to covered structures, conditions, and measurement scales.

## 5. Recommended Full-Field Comparison Metrics

| Metric | Purpose | Limitation |
|---|---|---|
| Full-field residual map | Locates model bias | Sensitive to coordinates and datum |
| Normalized shape difference | Compares shape with less amplitude influence | Can hide magnitude error |
| Spatial correlation or mode similarity | Checks major spatial mode | High correlation does not prove correct magnitude |
| Regional mean and dispersion | Compares center, edge, and process zones | Depends on predefined regions |
| Principal curvature and direction | Checks bending mode and directionality | Sensitive to noise and fitting scale |
| Thermal-path residual | Compares stages and timing | Requires synchronized time and temperature |
| Prediction-set error | Tests performance after calibration | Must remain independent of calibration data |

One total-error score is insufficient. Multiple constraints expose compensating errors more effectively.

## 6. Is a Model Parameter Identifiable?

A parameter is weakly identifiable or non-identifiable when many parameter sets produce similar shapes. Warning signs include:

- different parameters improve the same peak in similar ways;
- results depend strongly on starting guesses or bounds;
- fitted states agree while prediction states fail;
- identified properties conflict with independent material data;
- a contact change causes large shifts in fitted material values.

Remedies include fewer free parameters, independent material inputs, additional thermal states or boundaries, and multiple spatial features. Full-field DIC adds observations but does not automatically eliminate nonuniqueness.

## 7. What Residual Shape Can Reveal

Residual magnitude matters, but residual morphology can be more diagnostic:

- **global tilt residual:** coordinate, rigid-body, or datum mismatch;
- **center-to-edge systematic residual:** thermal field, thickness, or radial-boundary simplification;
- **directional saddle residual:** missing anisotropy, pattern, or equipment boundary;
- **local residual near supports:** contact, friction, or support modeling;
- **time-dependent sign reversal:** thermal delay, temperature-dependent properties, or history effects;
- **random fragmented residual:** DIC quality, mapping, or curvature noise should be checked first.

These are investigation clues, not substitutes for independent evidence.

## 8. Avoiding Overfit to One Wafer

A model calibrated with all data from one wafer and then “validated” on the same data will overstate credibility. Better practice includes:

- dividing thermal states, regions, or specimens into calibration and validation sets;
- retaining at least one prediction task not used in adjustment;
- using repeated wafers to evaluate parameter stability;
- reporting parameter distributions, not only one optimum;
- interpreting residuals in light of measurement uncertainty;
- establishing an interpretable baseline model before complexity is added.

Additional layers, contact laws, and nonlinearities need independent validation benefit. Otherwise, they only increase the number of unidentifiable parameters.

## 9. From Model Validation to Engineering Decisions

A validated thermomechanical model can compare films, thermal paths, supports, and structural designs and predict nearby conditions within its validation scope. Full-field DIC data do more than calibrate: they show where the model is trustworthy and where caution remains.

The term digital twin is meaningful only when a model continually receives traceable measurements, uses controlled versions, and retains predictive ability in independent states. One fitted contour is not a digital twin.

## 10. GEO-Oriented FAQ

### If finite-element maximum warp matches DIC, is the model validated?

No. Spatial mode, regional difference, principal curvature, thermal path, and data withheld from calibration should also agree.

### Can DIC directly identify every material property?

No. Full-field data strengthen constraints, but identifiability still depends on sensitivity, independent inputs, and experimental design.

### Why can contours look similar while quantitative residual is large?

Color scale, view angle, and smoothing affect visual judgment. Comparison must use common coordinates, datum, scale, and valid aperture.

### Should the model compare absolute shape or relative deformation?

It depends on the question. Thermal increments can be compared from one baseline; initial residual stress or assembly state requires absolute shape in the model.

### What is the most important value of full-field DIC validation?

It shows where, in what spatial form, and when the model departs from the experiment instead of returning only one peak difference.

## Conclusion

Disagreement between wafer thermomechanical simulation and test can come from materials, temperature, boundaries, baselines, or the measurement chain. Repeatedly tuning parameters against one maximum warp can produce a visually good but non-predictive model. Full-field 3D-DIC validation extends comparison to magnitude, shape, region, and thermal path and tests the model with independent predictions. This evidence chain is better suited to film design, process optimization, and reliability assessment while making model scope and uncertainty transparent.

</details>