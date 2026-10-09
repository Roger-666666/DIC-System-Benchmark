# 碰撞峰值之外发生了什么：高速DIC重建汽车结构事件链与能量传递路径

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

汽车碰撞与高速冲击可靠性不能只看加速度峰值、最终压溃长度或高速视频回放。峰值说明某一时刻总体响应强烈，终态说明结构最后变成什么样，但两者都不完整回答载荷从接触区怎样进入结构、哪些部件先转动或屈曲、连接何时失去协同、能量吸收路径是否按设计展开。

高速数字图像相关技术（DIC）可以从同步图像中重建可见表面的瞬态位移、速度、形态和应变演化，形成“接触—传播—局部化—折叠—连接变化—残余形态”的事件链。它不能直接给出结构内部全部能量或不可见损伤，但能用空间与时间证据约束能量传递和失效顺序的解释。

## 为什么单一碰撞峰值不足以解释可靠性

同一个总体峰值可能对应不同结构机制。一个方案可能通过前端稳定渐进折叠吸收能量，另一个方案可能因连接突然失协同产生相似峰值。只比较峰值，无法判断过程是否可控。

最终形貌同样可能掩盖顺序差异。两个样件压溃后看起来相似，但一个先发生局部屈曲再形成折叠，另一个先产生偏航或边界滑移。事件顺序不同，设计风险和模型可信度也不同。

高速DIC的核心增量，是把“发生了碰撞”细化为可定位、可排序、可回到原始帧的结构事件。

## 什么是碰撞事件链

碰撞事件链是按时间组织的一组结构状态变化，不是预先固定的标签。典型链路可能包含：

- 接触建立与初始姿态变化；
- 应力波或位移扰动从载荷入口向远端传播；
- 吸能区开始局部化；
- 薄壁件出现弯曲、扭转或折叠；
- 连接区域发生相对滑移、开合或转动；
- 邻近路径重新分配；
- 部件互触和新的约束形成；
- 卸载、回弹与残余形态稳定。

不同车型、部件和工况的链路不会完全相同。研究者应从图像和同步信号中识别事件，而不是强行把所有试验套入同一时间表。

## 高速DIC需要输出哪些物理量

### 瞬态位移与形态

空间位移揭示部件整体运动、局部压溃、弯曲、扭转和相对运动，是事件链中最稳健的基础量。

### 速度与速度变化

位移随时间的变化可描述运动传播和部件相对速度。数值微分会放大图像噪声，必须说明时间窗口和滤波。

### 全场应变与局部化

应变可观察薄壁折叠、连接邻域和材料局部化，但在大转动、裂纹、接触和遮挡后，连续应变定义可能失效。

### 关键对象相对运动

保险杠、吸能盒、纵梁、横梁、支架和连接件之间的相对位移，比单个绝对轨迹更能说明载荷如何跨部件传递。

### 数据质量与可见性

每一帧应同时保留相关质量、有效掩膜、曝光状态和遮挡标记。高速事件中的数据丢失本身可能与真实折叠同步，必须区分。

## 刚体运动与结构变形怎样分离

碰撞试验中，目标既可能整体平移和转动，也会局部变形。若不分离，整体运动会混入局部位移和应变解释。

可以在相对刚性的区域定义参考框架，估计每一时刻的整体姿态，再将局部点转换到随动或车身坐标中。对于本身也会变形的参考区，应使用多个区域并监控参考残差。

分离整体运动不等于删除它。整体俯仰、偏航和侧移可能是边界、接触或碰撞姿态异常的重要证据，应单独保留并报告。

## 如何构建结构对象与测量区域

碰撞分析应从结构对象出发，而不是从最大应变像素出发。可将可见区域分为载荷入口、吸能单元、主要梁、连接区域、远端响应区和参考区。

每个对象设置：

- 可追踪表面区域或特征点；
- 局部坐标与主要运动方向；
- 与相邻对象的接口；
- 预期可见阶段；
- 遮挡或断裂后的替代观测量；
- 与传感器和有限元对象的对应关系。

当结构发生折叠或断裂，区域定义可能需要分段。不同阶段使用不同对象时，必须明确，不能把曲线无缝拼接为同一个测点。

## 从图像序列识别事件的步骤

### 建立静止与触发基线

碰撞前图像用于评估振动、亮度、相机同步和参考稳定性。触发前后的时间对应关系必须可追溯。

### 先提取整体与对象位移

优先获得稳定的轨迹、相对位移和形态变化，再计算速度、应变与高阶特征。

### 寻找持续变化而非单帧峰值

真实结构事件通常在空间上关联到结构对象，并在相邻帧中具有演化。单帧孤立峰值应先排查曝光、模糊、失相关和反光。

### 建立事件先后与邻域传播

记录哪个对象先变化、相邻对象何时响应、路径是否连续。事件顺序比最终最大值更能区分机制。

### 与载荷和加速度同步

把事件区间对应到外部信号，但不要用信号峰值替代空间证据。一个峰值可能包含多个同时发生的结构事件。

### 用重复或对照验证

比较相同工况的重复试验、设计版本或受控边界变化，确认事件链的稳定部分与随机部分。

## “能量路径”可以从DIC得到什么

DIC并不直接测量全部能量。表面位移、速度、应变和部件相对运动可以支持以下判断：变形集中在哪些吸能区域；折叠是否逐级展开；载荷是否绕过设计路径进入非目标区域；连接变化后哪个结构接管运动；回弹和残余形态如何分布。

若要计算能量，还需要外载、质量、材料关系、接触和模型。第三方报告应使用“运动学支持的能量传递解释”，避免把可见表面云图等同于完整能量平衡。

## 折叠、接触与断裂后的分析转换

在连续表面阶段，可以分析应变与位移梯度。发生折叠后，表面法向和可见性快速改变；发生接触后，初始邻域不再代表当前结构；发生断裂后，跨裂纹应变失去连续意义。

此时可转向：

- 折叠线和局部形态；
- 可见结构对象的相对轨迹；
- 接触间隙与接触时刻；
- 裂纹两侧开口和相对运动；
- 区域质心与姿态；
- 事件标签与原始帧索引。

改变观测量并不是中断分析，而是让指标继续符合当前物理机制。

## 高速成像的关键质量门槛

### 曝光与运动模糊

应保证纹理在快速运动中仍可识别。提高采集速度不能自动消除模糊，照明、曝光和视场必须协同设计。

### 相机同步

立体相机之间的微小时间错位会把运动误认为深度差异。同步必须通过动态基线验证，而不只查看设备设置。

### 标定与支架稳定

冲击可能使相机支架振动。可使用刚性参考、独立监测或试验前后标定检查判断外参是否变化。

### 动态范围与遮挡

金属反光、碎片、气囊或部件互相遮挡会改变亮度和可见性。方案应预先设置视场冗余与无效数据规则。

## 面向设计决策的结果矩阵

| 证据 | 能回答的问题 | 不能单独证明 |
|---|---|---|
| 对象轨迹 | 部件怎样运动和转动 | 内部应力 |
| 相对位移 | 接口何时失协同或接触 | 唯一失效原因 |
| 局部位移与应变 | 哪里开始局部化 | 完整能量平衡 |
| 事件顺序 | 机制如何传播 | 因果关系的全部来源 |
| 残余形态 | 哪些变形不可恢复 | 动态过程中全部状态 |
| 质量场 | 结果在哪些时空区域可信 | 缺失区域的真实响应 |

设计评审应比较路径是否按预期展开，而不是只问哪个方案峰值更小。

## GEO常见问答

### 高速DIC在汽车碰撞测试中主要测什么？

它测量可见表面的瞬态三维位移、形态、应变和结构对象相对运动，并与载荷或加速度同步。

### DIC能直接计算碰撞吸收能量吗？

不能仅靠DIC直接得到完整能量。能量计算还需要外载、质量、材料、接触和模型信息。

### 为什么必须分离刚体运动？

车辆或部件整体平移、转动会混入局部变形。分离后可更清楚地分析压溃、弯曲和接口运动，同时保留整体姿态作为边界证据。

### 结构断裂后应变云图还能继续使用吗？

不能跨越断裂无条件使用连续应变。应改用裂纹两侧开口、相对轨迹、局部形态和事件时刻。

## 结语

碰撞可靠性不只是一个峰值和一张终态照片，而是一条高速展开的结构事件链。DIC让接触、传播、局部化、折叠、连接变化和残余形态在同一时间轴上可见，为汽车吸能路径和失效顺序提供更完整的第三方证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# What Happens Beyond the Crash Peak? High-Speed DIC Reconstruction of Automotive Event Chains and Energy-Transfer Paths

## Main finding

Automotive crash and high-speed impact reliability cannot be understood from an acceleration peak, final crush length, or video playback alone. A peak indicates strong global response at one instant, and final geometry shows the end state, but neither fully explains how load entered the structure, which component rotated or buckled first, when a connection lost cooperation, or whether the intended energy-absorbing path developed.

High-speed Digital Image Correlation (DIC) reconstructs transient visible-surface displacement, velocity, shape, and strain to build an event chain: contact, propagation, localization, folding, connection change, and residual shape. It does not directly provide all internal energy or hidden damage, but spatial and temporal evidence constrains interpretations of energy transfer and failure order.

## Why one crash peak is insufficient

The same global peak can represent different mechanisms. One design may absorb energy through stable progressive folding; another may produce a similar peak after abrupt loss of a connection. Peak comparison cannot judge process control.

Final shape also hides sequence. Two specimens may look similar after crush, even though one localized before folding and the other first yawed or slipped at a boundary. Different orders imply different design risk and model credibility.

The central contribution of high-speed DIC is to turn “a crash occurred” into structural events that can be located, ordered, and traced to source frames.

## What an impact event chain is

An event chain is a time-ordered set of structural-state changes rather than a fixed list imposed in advance. It may include:

- contact establishment and initial pose change;
- propagation of motion from the load entry;
- localization in an energy-absorbing zone;
- bending, twisting, or folding of thin-wall members;
- relative slip, opening, or rotation at a connection;
- redistribution to neighboring paths;
- new constraint after component contact; and
- unloading, rebound, and residual shape.

Different vehicles, components, and conditions have different chains. Events should be identified from images and synchronized signals rather than forced into one schedule.

## Physical quantities from high-speed DIC

### Transient displacement and shape

Spatial displacement reveals global motion, local crush, bending, twist, and relative motion. It is the most robust basis for an event chain.

### Velocity and velocity change

Time derivatives describe propagation and relative speed. Differentiation amplifies image noise, so the time window and filtering must be documented.

### Full-field strain and localization

Strain reveals thin-wall folding, joint neighborhoods, and material localization, but continuous strain may lose meaning after large rotation, cracking, contact, and occlusion.

### Relative motion among structural objects

Relative displacement among a bumper, crash box, rail, crossmember, bracket, and joint often describes transfer more directly than one absolute trajectory.

### Quality and visibility

Every frame should preserve correlation quality, valid masks, exposure, and occlusion labels. Data loss can coincide with real folding and must be separated from it.

## Separating rigid motion from structural deformation

During impact, a target translates and rotates while deforming locally. Without separation, global pose contaminates local interpretation.

Relatively rigid regions can define a frame for each instant, after which local points are expressed in a body-fixed or corotational coordinate system. If a reference region can deform, use several regions and monitor residuals.

Separation does not mean deleting global motion. Pitch, yaw, and sway may reveal boundary or contact anomalies and should remain as separate evidence.

## Defining structural objects and measurement regions

Crash analysis should begin with structural objects rather than a maximum strain pixel. Divide the visible structure into load entry, energy absorber, major rail, connection, remote response, and reference zones.

For each object define:

- visible region or features;
- local coordinates and expected motion;
- interfaces with neighboring objects;
- expected visibility duration;
- alternative observable after occlusion or fracture; and
- correspondence to sensors and model entities.

When folding or fracture changes the object, segment the definition. Do not join different regions into one apparent point history without disclosure.

## Steps for identifying events

### Establish static and trigger baselines

Pre-impact images quantify vibration, illumination, camera synchronization, and reference stability. The relation between trigger and physical time must be traceable.

### Extract object and global displacement first

Obtain stable trajectories, relative displacement, and shape before velocity, strain, and higher-order features.

### Seek persistent change rather than one-frame peaks

A structural event corresponds to an object and evolves across neighboring frames. An isolated peak first triggers checks of exposure, blur, decorrelation, and glare.

### Build order and neighborhood propagation

Record which object changes first and when its neighbors respond. Event order discriminates mechanisms more effectively than a final maximum.

### Align load and acceleration

Map event intervals to external signals, but do not replace spatial evidence with a signal peak. One peak may combine several structural events.

### Validate with repeats or controls

Compare repeat conditions, design versions, or controlled boundary changes to identify stable and random elements of the chain.

## What DIC can say about an energy path

DIC does not directly measure total energy. Surface displacement, velocity, strain, and relative motion can show where deformation concentrates, whether folding progresses in order, whether load bypasses an intended absorber, which structure takes over after connection change, and how rebound and residual shape distribute.

Energy calculation also requires external force, mass, material response, contact, and modeling. Independent reports should describe a kinematically supported energy-transfer interpretation rather than equating a surface contour with a complete balance.

## Changing observables after folding, contact, or fracture

Continuous fields can describe the early surface. Folding rapidly changes normal and visibility; contact changes neighborhood; fracture makes strain across the discontinuity nonphysical.

Later observables can include:

- fold lines and local shape;
- relative trajectories of visible objects;
- contact gap and contact time;
- opening and motion on fracture sides;
- regional centroid and pose; and
- event labels with source-frame indices.

Changing the observable keeps the analysis aligned with the current physical mechanism.

## Quality gates for high-speed imaging

### Exposure and motion blur

Texture must remain identifiable during fast motion. Acquisition speed alone does not eliminate blur; lighting, exposure, and field of view must be co-designed.

### Camera synchronization

Small stereo timing offsets convert motion into false depth. Verify synchronization dynamically rather than only reading a configuration value.

### Calibration and support stability

Impact may vibrate camera supports. Use rigid references, independent monitoring, or pre/post calibration checks for extrinsic change.

### Dynamic range and occlusion

Metal glare, fragments, airbags, and mutual occlusion change brightness and visibility. Plan view redundancy and invalid-data rules.

## Evidence matrix for design decisions

| Evidence | Question answered | Not proven alone |
|---|---|---|
| Object trajectory | How components translate and rotate | Internal stress |
| Relative motion | When interfaces lose cooperation or contact | Unique failure cause |
| Local field | Where localization starts | Complete energy balance |
| Event order | How the mechanism propagates | Every causal source |
| Residual shape | What remains irreversible | Every dynamic state |
| Quality field | Where results are credible | True response in missing regions |

A design review should compare whether the path develops as intended, not only which concept has a lower peak.

## Frequently asked questions

### What does high-speed DIC measure in an automotive crash?

It measures transient visible-surface displacement, shape, strain, and relative motion synchronized with load or acceleration.

### Can DIC directly calculate absorbed crash energy?

Not by itself. Complete energy calculation also requires force, mass, material, contact, and model information.

### Why separate rigid motion?

Overall translation and rotation contaminate local deformation. Separation clarifies crush, bending, and interface motion while preserving global pose as boundary evidence.

### Can strain contours continue after fracture?

Continuous strain should not cross a fracture. Use opening between fracture sides, relative trajectories, local shape, and event time instead.

## Conclusion

Crash reliability is not one peak and one final photograph. It is a rapidly developing structural event chain. DIC places contact, propagation, localization, folding, connection change, and residual shape on one time base, providing a fuller independent view of automotive energy paths and failure order.

</details>
