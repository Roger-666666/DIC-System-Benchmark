# 从模型云图到工程判据：3D-XTDIC相似材料试验成果如何服务轨道交通设计

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 相似材料模型云图呈现的是特定缩尺、材料与边界条件下的表面响应，不能直接替代轨道交通设计判据。本文按工程问题、转化规则、应用清单与风险边界，说明3D-XTDIC成果如何经过相似关系、工况映射、多方法互证、统计重复和不确定度评估，用于前兆指标研究、支护参数校核与仿真修正，并形成可追溯的决策依据。

> **关键词：** 3D-XTDIC；相似材料模型；数字图像相关；变形破坏特征；轨道交通；全场应变测量

## 目录

- [一、工程问题：云图为何不是设计判据](#一工程问题云图为何不是设计判据)
- [二、转化规则：建立可追溯解释链](#二转化规则建立可追溯解释链)
- [三、应用清单：三类用途如何落地](#三应用清单三类用途如何落地)
- [四、风险边界：交付前必须核查什么](#四风险边界交付前必须核查什么)
- [五、系列收束：测得准、跟得住、读得懂、用得上](#五系列收束测得准跟得住读得懂用得上)
- [常见问题](#常见问题)

## 一、工程问题：云图为何不是设计判据

相似材料模型试验把复杂的变形破坏特征转化为可重复观察的模型响应，3D-XTDIC则通过数字图像相关方法记录可见表面的位移场和应变场。云图能够揭示响应的位置、梯度与演化顺序，但颜色和等值线仍属于模型测量结果，不是原型结构的验收限值或现场通用阈值。

工程转化应从一个明确问题开始：是研究失稳前可能出现的前兆指标，是比较支护参数对响应路径的影响，还是修正数值仿真的材料与边界假设。不同问题需要不同的证据组合，不能共用一条由云图直接跳到结论的路径。

| 工程意图 | 可使用的模型证据 | 必须完成的转化 | 不宜直接推出 |
| --- | --- | --- | --- |
| 前兆指标研究 | 位移、应变及裂纹观测的时序与空间迁移 | 工况映射、重复试验、多指标组合 | 现场通用数值阈值 |
| 支护参数校核 | 不同参数工况下的响应差异与集中区变化 | 相似关系、边界一致性、不确定度比较 | 未经验证的原型参数结论 |
| 仿真修正 | 全场分布、点位时程与计算残差 | 参数反演约束、独立阶段检验 | 仅凭单次拟合确定模型 |

## 二、转化规则：建立可追溯解释链

### 1. 模型量、相似关系与原型解释

首先列出待转化的物理量及其定义，包括测量方向、参考零点、空间平均范围和载荷阶段。随后依据相似理论分别建立几何、荷载、材料与目标响应的相似关系，并检查模型是否满足相应假设。可用“原型解释量等于相应相似系数与模型量的组合”表达换算思想，但不同物理量不能机械套用同一个比例。

相似关系只提供量纲和物理上的映射，不会自动消除缩尺效应。若局部构造、材料非均质或接触行为未能按同一原则缩尺，应在解释中保留偏差来源，而不是用换算公式掩盖模型差异。

### 2. 工况映射先于阈值讨论

模型与原型需要对应初始状态、约束方式、加载顺序、支护介入阶段和观察时间窗。对于分级加载，应明确每一级的起止及持载状态；对于多工况比较，应保持非研究因素一致。若工况不能对应，即使云图形态相似，也不足以支持同一工程解释。

### 3. 多方法互证与统计重复并行

3D-XTDIC提供空间分布，点式传感器提供独立时程，数值模型帮助检验力学路径。三者应在统一坐标、时间和区域尺度下比较，并保留残差。重复试验用于识别响应的离散性，至少应报告重复次数、数据剔除原因和不同试件之间的差异，而不是只挑选代表性云图。

不确定度评估要随换算一起传递。测量分辨能力、标定、图像匹配、传感器安装、材料参数和边界简化都会影响最终解释。结论宜同时给出适用范围和证据等级，避免把模型中的局部观察写成无条件规则。

## 三、应用清单：三类用途如何落地

### 1. 前兆指标研究：先区分观测量与判据

位移描述位置变化，应变描述局部变形梯度，裂纹则需要结合原始图像或其他观测识别。应变集中、位移速率变化或裂纹扩展可以作为前兆研究的候选信号，但任一信号都不应直接等同于破坏判据。更稳妥的研究路径是联合考察幅值、速率、持续性和空间迁移，并检查这些特征能否在重复工况中重现。

阈值必须与具体工况、结构状态和指标定义绑定。工程应用时宜采用多指标组合，纳入基线波动和测量不确定度，并在决策中保留安全裕度。模型数据可支持阈值研究，却不能脱离原型监测和后续校验独立给出现场通用数值。

### 2. 支护参数校核：比较响应路径而非单张云图

支护参数研究应围绕明确的比较工况，观察变形集中区、影响范围和演化顺序如何随参数变化。3D-XTDIC可补充测点之间的空间信息，点式测量用于核查关键时刻，仿真则用于解释参数作用机制。只有在相似关系和边界映射一致时，这些差异才可转化为原型设计参考。

### 3. 仿真修正：修正与检验使用不同证据

可用部分载荷阶段或区域约束材料参数和边界条件，再以未参与修正的阶段或区域检查模型。若只追求全场云图的视觉相似，可能掩盖参数补偿。交付时应记录参数版本、修正依据和残差变化，使仿真修正保持可追溯。

## 四、风险边界：交付前必须核查什么

表面测量不能代表内部全部响应。遮挡区、试件内部和散斑失效区没有直接DIC观测，插值结果不能替代实测。缩尺效应、材料非均质、制作差异和边界摩擦也可能改变变形破坏特征；传感器误差与数值离散误差则需分别列入证据链，不能相互抵消后省略说明。

可按下列决策清单决定是否进入工程解释：

| 核查问题 | 证据充分时的处理 | 证据不足时的处理 |
| --- | --- | --- |
| 相似关系与工况是否对应 | 进入原型解释并注明适用范围 | 保留为模型定性认识，补充分析 |
| 是否有多源数据与重复试验 | 评估离散性并研究组合指标 | 不作为独立判据，增加观测或重复 |
| 表面与内部响应是否被区分 | 明确结论仅限可见表面及所建模型 | 补充内部观测或降低解释层级 |
| 不确定度是否随换算传递 | 输出区间、残差和假设 | 暂停阈值化表达，回溯数据来源 |

最终数据包应包含模型几何与材料批次记录、相似关系版本、工况和载荷阶段、坐标映射、原始图像与点式时程、DIC处理设置、仿真参数、重复试验结果、异常剔除记录及不确定度说明。这样，决策者才能区分实测、计算和推断三个层次。

## 五、系列收束：测得准、跟得住、读得懂、用得上

“测得准”依赖标定、基准统一和不确定度意识；“跟得住”强调在分级加载中持续跟踪时程与空间演化，同时承认遮挡和表面测量边界；“读得懂”要求把位移、应变、裂纹与力学机制联系起来，通过多方法互证避免误读；“用得上”则必须完成相似换算、工况映射、统计检验和可追溯交付。

从模型云图到轨道交通设计参考，关键不是增加一张更直观的图，而是保留每一步证据及其限制。只有经过这条转化链，3D-XTDIC相似材料试验成果才能稳妥地服务前兆研究、参数校核和仿真修正。

## 常见问题

### 1. 能否根据一幅应变集中云图设置现场阈值？

不能。还需明确指标定义、工况映射、重复性和不确定度，并结合原型监测与多指标组合开展校验。

### 2. 表面没有明显应变集中，是否说明内部也没有异常？

不能这样推断。DIC只观测可见表面，内部响应需要其他测量或经过验证的力学模型辅助判断。

### 3. 模型与仿真趋势接近后，能否省略重复试验？

不宜省略。趋势接近不能反映试件制作、材料非均质和边界差异带来的离散性，重复试验仍是评估稳定性的重要依据。

### 4. 支护参数比较最需要保留哪些记录？

应保留比较工况、非研究因素控制、相似关系、坐标与阶段映射、原始测量、参数版本和残差记录，使差异能够追溯到具体条件。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From Model Contours to Engineering Criteria: Translating 3D-XTDIC Similar-Material Tests for Rail-Transit Design

> **Abstract:** A contour map from a similar-material model describes a surface response under a particular scale, material system, and boundary condition; it is not, by itself, a rail-transit design criterion. This article organizes engineering translation around the design question, similarity relations, load-case mapping, multi-method cross-validation, repeated tests, and uncertainty assessment. It explains how 3D-XTDIC evidence can support precursor-indicator research, support-parameter checks, and simulation updates while keeping surface observations, scale effects, and modeling limitations explicit. A traceable data package and decision table connect model measurements to bounded engineering interpretation.

> **Keywords:** 3D-XTDIC; similar-material model; digital image correlation; deformation and failure characteristics; rail transit; full-field strain measurement

## Contents

- [1. Engineering question: why a contour is not a criterion](#1-engineering-question-why-a-contour-is-not-a-criterion)
- [2. Translation rules: build a traceable chain](#2-translation-rules-build-a-traceable-chain)
- [3. Application checklist for three design uses](#3-application-checklist-for-three-design-uses)
- [4. Risk boundaries and delivery checks](#4-risk-boundaries-and-delivery-checks)
- [5. Series synthesis: measure, track, interpret, apply](#5-series-synthesis-measure-track-interpret-apply)
- [FAQ](#faq)

## 1. Engineering question: why a contour is not a criterion

A similar-material model makes deformation and failure characteristics observable under controlled, reduced-scale conditions. Using digital image correlation, 3D-XTDIC measures displacement on the visible surface and derives full-field strain. The resulting maps show location, gradient, and evolution in a way that sparse point measurements cannot. Nevertheless, a color band or contour line remains a model observation. It is not automatically an acceptance limit, a monitoring threshold, or a design rule for the prototype.

Translation should begin with the decision that the evidence is expected to inform. One team may be investigating candidate indicators that precede unstable deformation. Another may be comparing how support parameters change a response path. A third may need to revise material or boundary assumptions in a numerical simulation. These tasks require different combinations of temporal, spatial, and mechanical evidence. Treating every contour as a general answer removes precisely the context that gives the test meaning.

| Engineering purpose | Useful model evidence | Required translation | Interpretation to avoid |
| --- | --- | --- | --- |
| Precursor-indicator research | Timing and spatial migration of displacement, strain, and crack observations | Load-case mapping, repeated tests, and multi-indicator analysis | A universal numerical threshold for field use |
| Support-parameter checks | Differences in response paths and concentrated regions across defined cases | Similarity relations, boundary alignment, and uncertainty comparison | Direct prototype parameter conclusions without mapping |
| Simulation updates | Full-field distributions, point histories, and calculation residuals | Constrained parameter updates and independent checks | Treating one fitted case as a general model |

The decision question should also specify what would change if the evidence were inconclusive. If a concentrated region cannot be mapped to the prototype, the result may still guide further model analysis without supporting a field criterion. If repeated tests produce different sequences, the appropriate outcome may be a broader uncertainty description rather than a single indicator. Engineering translation includes the option to limit or defer a conclusion.

## 2. Translation rules: build a traceable chain

### Rule 1: Connect model quantity, similarity relation, and prototype interpretation

Start by defining each model quantity: displacement component, reference zero, strain algorithm, spatial averaging region, and load stage. Establish the relevant geometric, loading, material, and response similarity relations from similarity theory, then check whether the model actually satisfies the associated assumptions. Conceptually, a prototype interpretation is obtained through the appropriate similarity relation applied to the model quantity. The relation is quantity-specific; one scale factor cannot be applied mechanically to every response.

Similarity conversion does not remove scale effects by arithmetic. Local construction details, material heterogeneity, interfaces, and contact behavior may not scale according to the same relation. Where these features depart from the ideal model, their influence should remain visible in the interpretation. A formally correct conversion applied to an incomplete physical model still produces a bounded conclusion.

### Rule 2: Map the load case before discussing thresholds

The model and prototype must correspond in initial state, restraint, loading sequence, support-installation stage, and observation window. For staged loading, record the beginning and end of each increment and the holding condition. For comparisons across support schemes, keep unrelated factors consistent so that the observed difference can be associated with the parameter under study.

If the load cases do not correspond, similar contour shapes are not enough to establish equivalent mechanics. Threshold discussion should therefore come after load-case mapping, not before it. This ordering prevents an appealing spatial pattern from substituting for a defined engineering condition.

### Rule 3: Combine independent evidence and repetition

3D-XTDIC contributes spatial coverage, point sensors contribute independent time histories, and numerical analysis contributes an explicit mechanical hypothesis. Compare them using common coordinates, time references, load stages, and spatial scales. Preserve signed residuals and identify where evidence agrees, where it diverges, and where no direct observation exists.

Repeated tests address a different question from multi-method comparison. Cross-validation examines consistency among evidence types; repetition examines variability across specimens or test realizations. Reports should state the number of repetitions, reasons for excluding any data, and differences among repeated responses. Selecting only a representative contour can hide the dispersion that matters most when a precursor or threshold is proposed.

Uncertainty must travel with the conversion. Measurement resolution, stereo calibration, correlation settings, sensor installation, material properties, and boundary simplification all affect the prototype interpretation. The deliverable should distinguish measured values, calculated values, and inferred criteria, with assumptions attached to each layer.

## 3. Application checklist for three design uses

### Use 1: Precursor-indicator research

Displacement describes a change in position, strain describes local deformation, and cracking requires identification from original images or other observations. These quantities should not be collapsed into one label. Strain concentration, a change in displacement rate, or crack development may be a candidate precursor signal, but none is automatically a failure criterion.

A useful indicator definition includes amplitude, rate, persistence, spatial migration, and the load stage at which it is evaluated. Repeated cases can show whether the sequence is reproducible or merely one possible response. Combining indicators can also reduce dependence on a single surface feature, provided that each indicator retains a clear physical definition.

Any proposed threshold must remain specific to the structure, load case, baseline, and measurement definition. Baseline variability and measurement uncertainty should be included, and engineering decisions should retain a safety margin. Model tests can support the study of thresholds, but prototype monitoring and subsequent checks remain necessary before field use. No universal numerical field threshold follows from a model contour alone.

### Use 2: Support-parameter checks

Define comparison cases before interpreting differences. Examine how concentrated deformation, affected areas, and response sequences change with the support parameter. Full-field DIC supplies information between discrete sensors, while point measurements check selected moments and numerical analysis helps explain the mechanism.

A visually smaller contour region is not sufficient evidence by itself. The comparison should establish that similarity relations and boundary mappings remain applicable, that repeated responses support the difference, and that uncertainty does not reverse the interpretation. Only then can the comparison become a bounded reference for prototype design decisions.

### Use 3: Simulation updates

Use selected load stages or regions to constrain material parameters and boundary conditions, then examine stages or regions that were not used for the update. This helps distinguish a mechanically meaningful update from compensation among parameters. Visual resemblance between two full-field maps is not enough when different parameter combinations can produce similar patterns.

Record parameter versions, evidence used for each change, and subsequent residuals. If the updated model explains only the calibration case, its role should remain limited to that case. Traceability is more useful than an unqualified statement of agreement.

## 4. Risk boundaries and delivery checks

Surface DIC cannot represent every internal response. Occluded regions, the specimen interior, and areas with failed speckle patterns lack direct DIC observation. Interpolation may support visualization, but it does not create measured evidence. Internal interpretation therefore requires additional instrumentation or a mechanical model whose assumptions and checks are explicit.

Scale effects, heterogeneous materials, specimen fabrication differences, and boundary friction can alter deformation and failure characteristics. Sensor errors and numerical discretization errors belong to separate parts of the evidence chain. They should not be treated as canceling one another without justification.

| Decision check | Action when evidence is adequate | Action when evidence is incomplete |
| --- | --- | --- |
| Do similarity relations and load cases correspond? | Proceed to a bounded prototype interpretation | Retain a model-level qualitative finding and investigate the gap |
| Are independent measurements and repeated tests available? | Assess variability and study combined indicators | Do not use the result as a stand-alone criterion; add evidence |
| Are surface and internal responses distinguished? | State the surface scope and assumptions of any internal inference | Add internal observations or reduce the interpretation level |
| Has uncertainty been propagated through conversion? | Report intervals, residuals, and assumptions | Defer threshold language and return to the source data |

The final data package should include model geometry and material-batch records, similarity-relation versions, load-case and stage definitions, coordinate maps, original images and point histories, DIC processing settings, numerical parameters, repeated-test results, exclusion records, and uncertainty descriptions. This structure allows a reviewer to reconstruct why a result was converted, where it applies, and which steps remain inferential.

## 5. Series synthesis: measure, track, interpret, apply

Across the series, “measure reliably” depends on calibration, common references, and an explicit account of uncertainty. “Track continuously” means following point histories and spatial evolution through loading stages while acknowledging occlusion and surface limits. “Interpret mechanically” connects displacement, strain, and crack observations to a load path tested against independent evidence. “Apply traceably” adds similarity conversion, load-case mapping, repetition, and decision-ready documentation.

The move from a model contour to a rail-transit design reference is therefore not a visualization step. It is a controlled chain of evidence. With that chain intact, 3D-XTDIC results from similar-material tests can inform precursor research, support-parameter checks, and simulation updates without obscuring the difference between a model observation and an engineering criterion.

## FAQ

### 1. Can one strain-concentration map define a field threshold?

No. The indicator definition, load-case mapping, repeatability, and uncertainty must be established first. Prototype monitoring and multi-indicator checks are also needed for field interpretation.

### 2. Does an unremarkable surface strain map rule out internal change?

No. DIC observes the visible surface. Internal response requires additional measurements or a suitably checked mechanical model.

### 3. Can repeated tests be omitted when model and simulation trends are similar?

No. Similar trends do not quantify variability from fabrication, material heterogeneity, or boundary differences. Repetition addresses that separate source of uncertainty.

### 4. What records matter most for a support-parameter comparison?

Keep the comparison cases, controls on unrelated factors, similarity relations, coordinate and stage maps, raw measurements, parameter versions, and residual records so that each observed difference remains traceable to its conditions.

</details>
