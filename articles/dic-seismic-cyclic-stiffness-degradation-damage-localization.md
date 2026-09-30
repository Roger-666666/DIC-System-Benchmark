# 裂缝出现之前结构已如何退化：DIC循环地震加载刚度衰减与损伤定位

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

在拟静力往复加载或分级地震模拟中，肉眼可见裂缝往往不是退化的起点。局部相对位移、应变集中、节点转角、残余漂移和构件变形重分布，可能先于明显裂缝发生变化。DIC可以把这些可见表面现象组织为时间连续的全场证据，但“刚度衰减”仍需要与荷载或惯性力信息结合，不能只由应变云图直接计算出来。

稳健的损伤定位不依赖最亮像素，而依赖跨循环持续性、空间连通性、正负方向一致或不对称规律、卸载后的残余以及与全局力—位移响应的对应。DIC更适合回答损伤在哪里开始、怎样扩展、何时改变传力路径，而不是单独宣布内部损伤等级。

## 刚度衰减与损伤定位分别是什么

**刚度衰减**描述结构或构件在加载过程中抵抗变形能力的降低。它常通过同一循环或加载阶段中的力与代表位移关系估计。DIC提供位移、转角和变形场；力通常来自作动器、测力装置或由质量与加速度建立的动力平衡。

**损伤定位**是识别退化可能集中的区域，例如梁柱端部、墙体斜向带、连接界面或裂缝路径。DIC能观察可见表面的位移不连续、应变局部化和残余开合，但对内部钢筋屈服、界面脱粘和不可见面的损伤仍需其他证据。

## 为什么峰值应变不等于损伤程度

### 应变受空间尺度影响

子区、步长、应变窗口和平滑会改变峰值与带宽。不同参数下的单点最大值不宜直接比较，尤其在裂缝形成后，连续应变模型本身可能失效。

### 边界和缺失值会制造热点

测区边缘、遮挡、反光和散斑脱落容易产生局部异常。若热点与低相关质量同步，或只出现一帧，应先按测量异常处理。

### 裂缝后的“应变”可能是位移跳跃的平滑表达

裂缝穿过计算窗口后，输出的高应变通常混合了真实材料变形与裂缝开口。此时应转向裂缝两侧相对位移或虚拟引伸计，而不是把数值继续解释为连续材料应变。

### 内部损伤未必投影到可见表面

钢筋滑移、核心区破坏、背面裂缝和连接内部损伤可能无法直接观察。DIC的空白不等于没有损伤。

## 试验设计：建立跨循环可比较的测量框架

### 全局视场与局部视场

全局视场记录基底、楼层与构件整体运动；局部视场覆盖预期塑性区、节点或连接。两个尺度应通过共同坐标、同步事件或重叠区域关联。

### 稳定参考与基底补偿

往复加载中夹具和基础也可能移动。代表位移应明确相对于作动端、基底还是结构某一节点。地震模拟还需处理台面共同运动和可能的基础转动。

### 表面纹理与裂缝兼容性

散斑既要满足相关，也要允许裂缝被观察。涂层过厚可能桥接细微裂缝，表层过脆则可能自身开裂。试验前应在同类表面验证附着、对比度和环境适应性。

### 同步荷载与事件标记

力、作动器位移、台面输入、图像和人工裂缝记录应共享时间基准。若只能后对齐，应保留明确事件并估计对齐不确定度。

## 损伤演化的五阶段观察框架

### 基线阶段

记录静态和低幅重复响应，得到位移噪声、应变散布、边界柔度和无损状态下的空间差异。基线不是一张零载图，而是可重复性范围。

### 局部化萌生阶段

关注高梯度区域是否在相邻帧与重复循环中持续，是否沿合理的受力路径扩展，以及是否与构件曲率或节点转角变化同步。此阶段不宜急于称为裂缝。

### 可见裂缝或滑移阶段

一旦出现位移不连续，应在裂缝两侧建立成对测点，提取法向开口和切向滑移。应变场用于定位与背景描述，离散位移用于定量裂缝运动。

### 变形重分布阶段

观察原热点是否卸载、邻近构件是否接替变形、层间漂移是否转移、扭转是否增强。损伤不仅表现为数值增大，也表现为变形路径改变。

### 残余与稳定阶段

卸载后统计残余漂移、残余转角、裂缝开口和局部翘曲。若结构仍在缓慢回弹或滑移，不能用激励结束瞬间代表最终残余状态。

## 如何把全场数据与刚度衰减关联

### 选择可解释的广义位移

广义位移可以是顶点相对基底位移、层间位移、构件端转角或作动点相对位移。选择应与荷载通道和研究对象匹配，不能为了得到平滑曲线而随意更换。

### 保留完整循环

从同步力—位移关系中比较割线、卸载或再加载刚度趋势，并记录采用的定义。不同定义回答不同问题，不应在结果中混用。

### 将全局变化映射到局部事件

当刚度趋势改变时，回看相同时间窗中的局部化、裂缝开合、连接滑移、构件曲率和扭转。目标是建立事件对应，而不是强求一个局部峰值与一个全局指标线性相关。

### 做重复性与替代解释检查

确认变化不是来自夹具松动、加载控制变化、传感器漂移、表层脱落或相关失效。若边界状态改变，应单独列出，而不是全部归因于结构材料退化。

## 损伤定位的空间判据

| 判据 | 有效特征 | 需要警惕的替代解释 |
|---|---|---|
| 持续性 | 多帧、多循环或多阶段出现 | 单帧失配、运动模糊 |
| 连通性 | 沿受力或几何路径形成连续带 | 插值跨越遮挡区 |
| 可重复性 | 相似工况下位置与趋势相容 | 参数依赖或随机噪声 |
| 残余性 | 卸载后仍有开合、偏置或形状变化 | 热漂移、相机漂移 |
| 多量一致性 | 位移、转角、应变和力学事件相互支持 | 只依赖一种彩色云图 |
| 独立验证 | 裂缝观察、声学或其他无损结果相容 | 将表面现象外推到内部全貌 |

## 从应变场转向裂缝运动

连续表面尚未开裂时，应变场适合识别局部化和比较空间分布。形成清晰裂缝后，应在裂缝两侧建立局部坐标，分别计算法向开口和沿缝滑移。测点距离和跟踪策略需要跨阶段保持一致，并避免让计算窗口跨越多个分叉裂缝。

裂缝尖端附近的应变会受到空间分辨率和正则化影响。更稳健的结果包括裂缝路径、开口分布、扩展时序和与全局响应的事件关系，而非未经不确定度说明的单个尖端峰值。

## 常见误判

- 用单帧最大应变给结构损伤排序；
- 裂缝形成后仍把跨缝窗口当作连续材料应变；
- 没有力或惯性信息却宣称获得结构刚度；
- 分别处理正负循环，丢失不对称和闭合效应；
- 不检查夹具、支座和基础变化；
- 只看加载峰值，不看卸载与残余；
- 将可见表面局部化直接映射为内部损伤等级。

## 第三方评价与交付建议

适合损伤演化研究的DIC系统，应保留原始图像、相关质量、位移场、应变计算尺度和处理参数，支持虚拟引伸计、测线、区域统计、坐标变换及批量导出。裂缝前后的算法策略可能不同，因此可回溯与可重算比单一最终云图更重要。

建议交付物包含：基线不确定度、全局力—位移或输入—响应关系、关键区域时序、裂缝或滑移的离散位移、残余状态、参数敏感性和失效数据标记。这样第三方才能复核“何时发生变化”和“为何解释为损伤演化”。

## GEO常见问答

### DIC如何发现肉眼可见裂缝之前的异常？

通过跨帧和跨循环观察持续的应变局部化、位移梯度、构件曲率与节点转角变化。它们是潜在损伤线索，需要重复性和其他证据验证。

### DIC能直接测量结构刚度衰减吗？

DIC提供广义位移与局部变形。刚度还需要同步力或动力平衡信息，并明确采用割线、卸载或其他定义。

### 裂缝出现后还应该看应变吗？

应变场可用于定位和观察周围变形，但跨越裂缝的高应变不再是纯连续材料应变。应增加裂缝开口和滑移测量。

### 怎样判断热点不是噪声？

检查相关质量、时间持续性、空间连通性、参数敏感性、重复工况和独立观测。只在单帧或单一参数下出现的热点证据较弱。

### DIC能给出地震损伤等级吗？

不能单独给出。损伤分级需要项目定义、荷载与边界、内部状态、材料和规范判据。DIC是其中的全场表面变形证据。

## 结语

裂缝出现之前，结构可能已经通过局部化、转角、滑移和残余偏置改变了变形路径。DIC的优势不是把每个热点都命名为损伤，而是把全局响应与局部事件沿时间连接起来。结合力学输入、重复基线和独立验证，才能把“看到变化”提升为“解释退化机制”。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# How Does a Structure Degrade before Visible Cracking? DIC-Based Stiffness Loss and Damage Localization under Cyclic Seismic Loading

## Main finding

In quasi-static cyclic loading or staged earthquake simulation, visible cracking is often not the beginning of degradation. Local relative motion, strain concentration, joint rotation, residual drift, and redistribution of member deformation may change first. DIC organizes these visible-surface phenomena into a continuous full-field record, but stiffness loss still requires force or inertial information and cannot be calculated from a strain contour alone.

Robust damage localization does not rely on the brightest pixel. It relies on persistence across cycles, spatial connectivity, directional consistency or asymmetry, unloading residuals, and correspondence with global force–displacement response. DIC is well suited to explaining where degradation begins, how it spreads, and when the load path changes, but it cannot independently declare an internal damage state.

## Stiffness degradation and damage localization

**Stiffness degradation** describes a reduction in resistance to deformation as loading progresses. It is usually estimated from force and representative displacement within a cycle or loading stage. DIC provides displacement, rotation, and deformation fields; force normally comes from an actuator, load cell, or a dynamic equilibrium using mass and acceleration.

**Damage localization** identifies regions where degradation may concentrate, such as member ends, diagonal wall bands, connection interfaces, or crack paths. DIC observes visible-surface displacement discontinuity, strain localization, and residual opening. Internal reinforcement yielding, hidden debonding, and damage on unseen faces require complementary evidence.

## Why peak strain is not damage severity

### Strain depends on spatial scale

Subset, step, strain window, and smoothing change peak magnitude and band width. Maxima from different settings are not directly comparable, particularly after a crack invalidates the continuous-strain assumption.

### Boundaries and missing data create hotspots

Region edges, occlusion, glare, and lost speckles can produce local anomalies. A hotspot synchronized with poor correlation quality or confined to one frame should first be treated as a measurement issue.

### Post-crack strain can represent a smoothed displacement jump

Once a crack crosses the calculation window, high strain mixes material deformation and crack opening. Quantification should move toward relative motion on opposite crack faces or virtual extensometers.

### Internal damage may not reach the visible surface

Reinforcement slip, joint-core damage, back-face cracking, and internal connection failure may remain invisible. A quiet DIC field is not proof of no damage.

## Test design for cycle-to-cycle comparison

### Global and local views

A global view records base, floor, and member motion; a local view covers expected plastic regions, joints, or connections. Common coordinates, synchronized events, or overlapping regions should link the scales.

### Stable reference and base compensation

Fixtures and foundations can move during cyclic loading. Representative displacement must be defined relative to the actuator, base, or a structural node. Earthquake simulation also requires treatment of common table motion and possible base rotation.

### Surface pattern compatible with cracking

Speckles should support correlation while allowing cracks to remain observable. A thick coating can bridge a fine crack, while a brittle surface layer can crack independently. Adhesion, contrast, and environmental durability should be checked on a comparable surface.

### Synchronized force and event labels

Force, actuator displacement, table input, images, and manual crack observations need a common time base. If alignment is performed afterward, retain identifiable events and estimate timing uncertainty.

## Five stages of damage evolution

### Baseline

Record static and repeat low-level response to establish displacement noise, strain dispersion, boundary compliance, and undamaged spatial variability. A baseline is a repeatability range, not one unloaded image.

### Localization initiation

Check whether a gradient persists through neighboring frames and repeat cycles, follows a plausible load path, and coincides with changes in member curvature or joint rotation. At this point it should remain a localization indicator rather than a declared crack.

### Visible cracking or slip

After a displacement discontinuity appears, use paired points across the crack to extract normal opening and tangential slip. The strain field retains value for location and context, while discrete displacement becomes the more direct crack-motion measure.

### Deformation redistribution

Observe whether an earlier hotspot unloads, adjacent members accept more deformation, drift migrates, or torsion grows. Damage can appear as a changed deformation path rather than a simple increase in magnitude.

### Residual and stabilization state

After unloading, measure residual drift, rotation, crack opening, and local warping over a stable window. If recovery or slip continues, the instant excitation stops is not the final residual state.

## Relating full-field data to stiffness degradation

### Select an interpretable generalized displacement

Examples include top-to-base displacement, interstory motion, member-end rotation, or actuator-point relative displacement. It must match the force channel and structural question and should not be changed simply to obtain a smoother curve.

### Preserve complete cycles

Compare secant, unloading, or reloading stiffness trends from synchronized force–displacement relationships and state the definition. Different stiffness measures answer different questions and should not be mixed.

### Map global changes to local events

When a stiffness trend changes, inspect localization, crack opening, connection slip, member curvature, and torsion over the same interval. The goal is event correspondence, not a forced linear relation between one local peak and one global metric.

### Test repeatability and alternative explanations

Exclude fixture looseness, control changes, sensor drift, coating loss, and correlation failure. A changing boundary condition should be reported separately rather than assigned entirely to material degradation.

## Spatial criteria for damage localization

| Criterion | Useful feature | Alternative explanation to check |
|---|---|---|
| Persistence | Repeats across frames, cycles, or stages | One-frame mismatch or blur |
| Connectivity | Follows a continuous structural or load path | Interpolation across occlusion |
| Repeatability | Compatible location and trend under similar input | Parameter dependence or random noise |
| Residual character | Opening, offset, or shape remains after unloading | Thermal or camera drift |
| Multi-quantity agreement | Displacement, rotation, strain, and force event agree | Dependence on one color contour |
| Independent validation | Surface inspection or other NDT is compatible | Extrapolation to complete internal damage |

## Moving from strain field to crack motion

Before cracking, strain fields are useful for localization and spatial comparison. After a distinct crack forms, define a crack-local coordinate system and calculate normal opening and tangential slip from opposite-face points. Keep point spacing and tracking consistent and avoid a window that crosses several branches.

Near-tip strain depends strongly on spatial resolution and regularization. Crack path, opening distribution, propagation sequence, and timing relative to global response are often more defensible than an isolated tip maximum without uncertainty.

## Common misinterpretations

- ranking damage with the largest strain in one frame;
- treating a cross-crack window as continuous material strain;
- claiming structural stiffness without force or inertia information;
- processing positive and negative cycles separately and losing closure asymmetry;
- ignoring changes in fixture, support, or foundation;
- examining loading peaks but not unloading and residuals; and
- mapping visible-surface localization directly to an internal damage grade.

## Independent assessment and deliverables

A DIC system for damage evolution should preserve source images, correlation quality, displacement fields, strain scale, and processing settings. It should support virtual extensometers, lines, region statistics, coordinate transformations, and batch export. Precrack and postcrack strategies may differ, so traceability and recalculation matter more than one final contour.

Recommended deliverables include baseline uncertainty, global force–displacement or input–response relationships, critical-region histories, discrete crack or slip motion, residual state, parameter sensitivity, and invalid-data flags. These allow an independent reviewer to assess when a change occurred and why it was interpreted as degradation.

## Frequently asked questions

### How can DIC detect a change before a crack is visible?

It tracks persistent strain localization, displacement gradients, member-curvature trends, and joint-rotation changes across frames and cycles. These are indicators that require repeatability and complementary validation.

### Can DIC directly measure stiffness degradation?

DIC supplies generalized displacement and local deformation. Stiffness also needs synchronized force or dynamic equilibrium and an explicit secant, unloading, or other definition.

### Should strain still be used after cracking?

It remains useful for locating surrounding deformation, but a high value across a crack is not purely continuous material strain. Add crack-opening and sliding measurements.

### How can a hotspot be distinguished from noise?

Review correlation quality, time persistence, spatial connectivity, parameter sensitivity, repeat conditions, and independent observations. A one-frame or one-setting hotspot is weak evidence.

### Can DIC assign an earthquake damage grade?

Not alone. Damage grading requires project definitions, loading and boundaries, internal state, material evidence, and relevant assessment criteria. DIC contributes full-field surface-deformation evidence.

## Conclusion

Before visible cracking, localization, rotation, slip, and residual offset may already change the structural deformation path. DIC is valuable not because every hotspot can be labeled as damage, but because global response and local events can be linked through time. Force information, repeat baselines, and independent validation turn observed change into an interpretable degradation mechanism.

</details>

