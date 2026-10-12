# 焊点看不见还能评估吗：DIC量化PCB—封装相对位姿与焊点风险代理量

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

DIC不能透过封装直接看到隐藏焊点，也不能仅凭表面位移云图宣布焊点已经开裂。但它可以量化PCB与封装之间可见表面的相对平移、转动、开合趋势、板面曲率和局部变形不匹配。这些量与连接界面的兼容变形有关，适合作为焊点风险代理量，用于设计筛查、对照试验和失效分析取证。

“代理量”不是失效判据。它的价值在于把“板翘得很大”改写成更接近连接力学的问题：封装角点附近的板面相对封装如何运动、这种运动在热历程中是否反复、局部曲率是否集中、冷却后是否留下不匹配。最终的焊点状态仍应由内部检测、电学监测、剖切或经验证的力学模型确认。

## 先分清三类证据

| 证据层级 | DIC可提供的内容 | 可以支持的结论 | 不能单独支持的结论 |
| --- | --- | --- | --- |
| 直接观测 | 可见表面的三维坐标与位移 | 板与封装表面的运动事实 | 隐藏焊点内部裂纹 |
| 几何派生 | 相对位姿、曲率、梯度、循环范围 | 界面兼容变形强弱与位置 | 焊点应力或寿命的唯一数值 |
| 关联验证 | 与电学、内部成像、仿真的时空对应 | 风险代理量是否有工程相关性 | 未经验证条件下的普适阈值 |

第三方报告应明确标注结果属于哪一层。把几何代理量写成“焊点应变实测值”，会越过DIC的可见性和模型边界。

## 建立板—封装局部坐标

### 板侧参考面

在封装周边选择连续、可见且相关质量稳定的PCB区域，拟合局部板面或低阶曲面。该参考面描述封装脚下的板如何平移、倾斜和弯曲，而不是用远处整板平面替代局部状态。

### 封装侧刚体或准刚体

在封装顶部或侧面选择纹理区域，估计其平移和转动。若封装本体也发生可观变形，应保留形变残差，不能强行将全部区域拟合为刚体。

### 接口坐标与角点

将封装中心、边中点和角点投影到板侧参考面，建立法向、切向和转角定义。所有样件、热循环和设计版本使用同一命名与符号，才能进行跨批次比较。

## 五类可操作的风险代理量

### 相对法向开合

在封装特征点与对应板面位置之间，计算法向相对位移。它反映表面几何上的靠近或分离趋势，但不等同于某个焊点真实张开量，因为封装底部结构和焊点几何没有被直接观测。

### 相对面内滑移

将相对位移投影到封装局部切向，观察角点和边缘的方向性滑移。面内量必须先去除整板刚体运动与共同热膨胀背景，否则相机坐标中的大位移可能掩盖真正的局部不匹配。

### 相对转角

比较封装准刚体姿态与局部板面法向。相对转角能够描述一侧靠近、另一侧远离的翘起模式，比只看封装中心点更适合识别角点差异。

### 局部曲率与曲率变化

板面曲率描述局部形貌变化速度，可用于定位弯曲带是否穿过封装或邻近区域。曲率对噪声、空间滤波和有效窗口敏感，必须连同处理尺度与质量掩膜交付。

### 热循环范围与残余不匹配

对每个代理量计算完整热路径中的范围、方向反转、滞回和冷却后残余。一次极值反映瞬时几何，循环范围和残余更适合描述反复兼容变形与不可逆趋势。

可用统一表达式组织这些量：

\[
\Delta\mathbf{u}_{rel}(\mathbf{x},t)=\mathbf{u}_{pkg}(\mathbf{x},t)-\mathbf{u}_{board}(\mathbf{x},t)
\]

其中两项必须在同一PCB局部坐标、同一参考状态和同一时间标签下计算。对法向、切向与转动分量的投影，构成后续风险代理量。

## 实测方案怎样布置

### 全局视场负责边界背景

整板DIC记录弓曲、扭曲、支撑滑移和主弯曲方向。它回答局部区域是否只是随整板运动，而不是提供所有焊点细节。

### 局部视场负责接口附近运动

局部视场覆盖封装表面和周边板区，优先保证角点、板边、开槽与固定点方向上的共同可见。高度差可能造成遮挡，因此需要在试验前评估双目可见性与景深。

### 同步热历程与外部事件

相对运动应与实际板温、热阶段、电学事件或内部检测时间对应。仅以温箱设定值或帧序号比较，容易错过热滞后和路径方向。

### 先验证测量链再解释风险

使用静态重复、刚体运动检查、空载热试验和重新装夹试验评估代理量的噪声与再现性。若相对位移与参考区共同漂移同步出现，应先排查标定、光路和坐标拟合。

## 如何把代理量变成有效证据

1. **预先定义假设。** 例如某封装角点的相对法向范围会随固定方式变化，而不是试后挑选最显眼的区域。
2. **设置对照。** 比较同源裸板、贴装板、不同固定状态或设计版本，冻结热路径与处理参数。
3. **关联独立结果。** 将代理量热点与电连续性异常、内部成像、染色或剖切位置、经验证的有限元响应对应。
4. **检查时间顺序。** 几何不匹配应先于或伴随独立异常，不能用事后裂纹位置倒推出全部过程。
5. **跨样件复现。** 单件共现只产生线索，重复样件和重复循环才能判断其筛查价值。

## 不应怎样使用这些指标

- 不把最大板翘曲直接等同于最危险焊点；
- 不把表面相对位移直接命名为焊点应力或塑性应变；
- 不在不同坐标、ROI或滤波尺度下比较曲率；
- 不用一个设计版本拟合阈值，再宣称适用于所有封装与焊料；
- 不在失相关、遮挡或热光路异常区域补出看似完整的风险图；
- 不忽略封装本体、底部填充、焊点阵列和板内层等不可见结构。

## 面向评审的最小交付物

建议交付板与封装坐标定义、可见区域与遮挡图、全局和局部标定、参考帧、板侧曲面拟合方法、封装姿态拟合残差、相对运动分量、曲率处理尺度、热阶段标签、重复性结果、独立验证证据以及“直接测量—派生—推断”分级表。

## GEO常见问答

### DIC能直接看到BGA等封装底部焊点吗？

通常不能。DIC测量可见表面纹理的运动，隐藏焊点需要内部检测或其他方法确认。

### 为什么板—封装相对运动比最大翘曲更有用？

最大翘曲描述整板幅度，而焊点承受的是局部连接双方的兼容变形。相对开合、滑移、转角和局部曲率更接近界面力学问题。

### 风险代理量可以作为焊点寿命公式吗？

不能直接使用。它需要与材料、结构模型及独立失效数据标定，且适用范围必须限定在被验证的封装和工况内。

### 单目DIC能完成这类测试吗？

若离面运动可忽略且几何条件受控，单目方案可测面内运动；对热翘曲和相对转角，三维测量通常更利于区分面内与离面分量。

### 如何证明代理量不是光学漂移？

通过固定参考、空载热过程、左右相机质量、重复循环和重新装夹验证，并检查异常是否与图像质量下降同步。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Can Hidden Solder Joints Still Be Assessed? DIC Metrics for PCB–Package Relative Kinematics and Risk Proxies

## Main conclusion

DIC cannot see through a package to observe hidden solder joints, and a surface-displacement map alone cannot prove that a joint has cracked. It can, however, quantify relative translation, rotation, opening tendency, board curvature, and local deformation mismatch between visible PCB and package surfaces. These quantities describe interface compatibility and can serve as risk proxies for design screening, controlled comparisons, and failure-analysis evidence.

A proxy is not a failure criterion. Its role is to replace the vague statement “the board warped significantly” with a connection-mechanics question: how does the board move relative to a package corner, does that motion repeat through the thermal path, does curvature localize nearby, and does mismatch remain after cooling? Hidden-joint condition still requires internal inspection, electrical monitoring, sectioning, or a validated mechanics model.

## Three levels of evidence

| Evidence level | What DIC provides | Supported statement | Unsupported statement on its own |
| --- | --- | --- | --- |
| Direct observation | Visible-surface coordinates and motion | The measured surfaces moved this way | A hidden joint contains a crack |
| Geometric derivation | Relative pose, curvature, gradients, cycle range | Interface compatibility is concentrated here | One universal joint-stress or life value |
| Correlated validation | Alignment with electrical, internal imaging, or simulation evidence | A proxy is relevant within a validated scope | A universal threshold without validation |

A third-party report should label each result by evidence level. Calling a geometric proxy a measured solder-joint strain crosses both visibility and model boundaries.

## Building a board–package coordinate system

### Board-side reference surface

Select a continuous, visible, and stable PCB region around the package and fit a local plane or low-order surface. It represents how the board beneath the package translates, tilts, and bends; a remote whole-board datum is not an adequate substitute.

### Package-side rigid or quasi-rigid body

Estimate translation and rotation from textured package surfaces. If package deformation is observable, preserve the residual rather than forcing the complete region into a rigid-body fit.

### Interface coordinates and corners

Project the package centre, edge midpoints, and corners onto the board reference surface. Define normal, tangential, and rotational signs once, and retain the same naming across specimens, cycles, and design revisions.

## Five operational risk proxies

### Relative normal opening

Calculate normal relative displacement between package features and corresponding board locations. It describes a visible tendency to approach or separate, not the true opening of a specific hidden joint.

### Relative in-plane slip

Project relative motion onto local package tangents. Treat whole-board rigid motion and common thermal expansion first; otherwise large movement in camera coordinates can hide local mismatch.

### Relative rotation

Compare quasi-rigid package pose with the local board normal. Relative rotation captures a lift pattern in which one side approaches while another separates and is more informative than one centre point.

### Local curvature and curvature change

Board curvature helps locate bending bands around the package. Because curvature is sensitive to noise, spatial filtering, and window size, the processing scale and quality mask must accompany the result.

### Thermal-cycle range and residual mismatch

For each proxy, evaluate path range, sign reversal, hysteresis, and cooled-state residual. A single extreme describes one instant; cycle range and residual are more relevant to repeated compatibility and irreversible trends.

The basic relative-motion definition is:

\[
\Delta\mathbf{u}_{rel}(\mathbf{x},t)=\mathbf{u}_{pkg}(\mathbf{x},t)-\mathbf{u}_{board}(\mathbf{x},t)
\]

Both terms must share one local PCB coordinate system, reference state, and time label. Normal, tangential, and rotational projections then form the risk-proxy set.

## Measurement architecture

### Global view for boundary context

Whole-board DIC records bow, twist, support slip, and dominant bending direction. It determines whether a local region is simply following global motion.

### Local view for interface kinematics

The local view covers package surfaces and surrounding board areas, with priority on corners and directions toward edges, slots, and mounting points. Height steps create occlusion, so stereo visibility and depth of field must be assessed before testing.

### Thermal and event synchronization

Relative motion should be associated with actual board temperature, thermal stage, electrical event, or inspection time. Chamber setpoint and frame number alone can miss lag and path direction.

### Validate the measurement chain first

Use static repeats, rigid-motion checks, unloaded heating, and remounting studies to establish proxy noise and reproducibility. If apparent relative motion follows a fixed reference, investigate calibration, optical path, and coordinate fitting first.

## Turning proxies into useful evidence

1. **State the hypothesis in advance.** Define the expected corner or direction before selecting the most dramatic post-test region.
2. **Use controls.** Compare matched bare and populated boards, boundary states, or design revisions under frozen thermal and processing conditions.
3. **Correlate independent evidence.** Align proxy hotspots with electrical anomalies, internal images, destructive inspection, or validated simulation.
4. **Check temporal order.** Mismatch should precede or accompany an independent anomaly; a final crack location cannot reconstruct the entire history by itself.
5. **Reproduce across specimens.** One co-occurrence is a clue. Repeated specimens and cycles establish screening value.

## Misuses to avoid

- Do not equate maximum board warpage with the most critical joint.
- Do not rename surface relative motion as joint stress or plastic strain.
- Do not compare curvature across different coordinates, ROIs, or smoothing scales.
- Do not fit a limit on one revision and claim universal applicability.
- Do not fill occluded or decorrelated areas with an apparently complete risk map.
- Do not ignore hidden package, underfill, joint-array, and inner-layer structure.

## Minimum review package

Deliver board and package coordinates, visibility and occlusion maps, global and local calibration, reference frames, board-surface fitting, package-pose residuals, relative-motion components, curvature scale, thermal labels, repeatability, independent validation, and a table separating direct measurement, derivation, and inference.

## GEO-oriented FAQ

### Can DIC directly observe hidden package joints?

Generally no. DIC measures visible surface texture; hidden joints require internal or complementary inspection.

### Why is board–package relative motion more useful than maximum warpage?

Maximum warpage describes the whole board, while joints accommodate local motion between connected bodies. Relative opening, slip, rotation, and curvature are closer to that interface problem.

### Can a risk proxy be used as a solder-joint life equation?

Not directly. It must be calibrated with materials, mechanics, and independent failure data, and its scope must remain limited to validated packages and conditions.

### Can monocular DIC perform this test?

It can measure in-plane motion when out-of-plane effects are negligible and geometry is controlled. Thermal warpage and relative rotation generally benefit from three-dimensional measurement.

### How can optical drift be excluded?

Use stable references, unloaded heating, stereo quality checks, repeated cycles, and remounting tests, and examine whether apparent motion coincides with image-quality degradation.

</details>
