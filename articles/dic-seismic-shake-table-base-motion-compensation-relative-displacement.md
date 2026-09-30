# 振动台在动，结构也在动：DIC地震模拟基底运动补偿与相对位移分解

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

在振动台地震模拟中，相机看到的位移通常同时包含台面输入、试件刚体运动、结构相对变形以及测量系统自身扰动。DIC基底运动补偿的目标不是把所有低频或大幅运动滤掉，而是在统一坐标系中显式分离这些分量，再计算层间变形、构件弯曲、节点转动和震后残余。

可靠的处理顺序是：先定义参考框架和被测量，再同步观测基底与结构，随后进行刚体分解与相对位移计算，最后用静止区、控制通道和原始图像验证。仅对位移曲线做平滑或减去全场均值，不能替代基底补偿。

## 什么是基底运动补偿

**基底运动补偿**是把振动台、基础板或模型底部的共同运动从结构观测结果中分离的坐标变换过程。它回答的是“结构相对于输入端发生了什么”，而不是“结构在相机画面里移动了多少”。

若世界坐标中的结构点位置记为 \(\mathbf{x}_s(t)\)，基底参考位姿记为 \(\mathbf{R}_b(t),\mathbf{p}_b(t)\)，则可将结构点转换到随基底运动的坐标框架：

\[
\mathbf{x}_{rel}(t)=\mathbf{R}_b(t)^T[\mathbf{x}_s(t)-\mathbf{p}_b(t)]
\]

相对位移由该坐标中的当前点与参考状态之差得到。这个表达式同时考虑平移和转动，因此比简单相减一条水平位移曲线更适合三维振动、摇摆或扭转明显的试验。

## 为什么直接读取DIC位移容易误判

### 台面输入会进入所有可见点

结构整体随振动台移动时，绝对位移可能很大，但构件之间的相对变形仍然很小。若直接把绝对位移峰值当作结构变形，就会把输入运动误写成损伤响应。

### 基础可能不只做单向平移

台面安装间隙、夹具柔度、基础板翘曲或多向激励会引入转动和离面分量。只减去一个基底点无法描述这种空间运动，还可能把基底转动投影成上部结构的“层间位移”。

### 相机支架也可能受到环境振动

如果相机与试件不在同一稳定参考框架中，相机位姿变化会叠加到重建结果。基底补偿处理的是试件参考运动；相机运动则需要稳定支架、静止参考或动态外参校正另行控制，两者不能混为一谈。

### 滤波不能判断运动来源

基底运动与结构响应可能处在相近频带。高通、低通或趋势扣除只能按频率改变信号，不能可靠区分哪一部分来自台面、哪一部分来自结构。

## 试验设计：先让参考框架可观测

### 基底参考区怎么选

参考区应与试件输入端刚性连接、在全过程中保持可见，并具有足够的空间分布以估计平移和转动。可在基础板、底梁或专用刚性靶上布置散斑或编码特征。参考点不宜集中在一条直线上，也不应跨越可能开裂或滑移的连接界面。

### 结构测区怎么布置

根据研究问题建立三类区域：代表楼层或构件整体运动的稳定区域、梁柱节点和连接附近的局部区域、预期出现裂缝或屈曲的高梯度区域。代表点必须避开反光、遮挡、松动附件和会脱落的表层。

### 二维还是三维DIC

当运动近似平面内且离面位移可忽略时，二维方案可以用于部分相对量。但地震模拟常伴随摇摆、扭转、离面弯曲和视角变化，三维DIC更有利于把真实空间运动与投影变化分开。

### 同步记录哪些通道

至少应保留激励命令、台面控制或反馈信号、图像时间戳和关键接触事件。若配有加速度计、位移计或力传感器，应记录共同触发或可追溯时标，避免仅凭峰值手工对齐。

## 数据处理流程

### 第一步：定义坐标与符号

在试验前固定世界坐标、基底坐标和结构局部坐标，说明各轴正方向、原点、参考时刻以及位移是绝对量还是相对量。坐标定义应贯穿全部加载阶段。

### 第二步：先求绝对三维运动

完成标定、图像相关和三维重建，输出基底参考区与结构测区的坐标时程。此时不要急于计算应变，应先检查重建连续性、相关质量、遮挡和失配。

### 第三步：估计基底刚体位姿

利用多个参考点拟合基底的平移和转动。应查看拟合残差：若残差在局部持续增大，说明所谓“刚体参考区”可能发生了变形、松动或跟踪错误。

### 第四步：变换到随基底坐标系

把结构点坐标转换到基底框架，再计算相对位移。对于只关注某一构件的研究，还可以在基底补偿后建立构件局部轴系，进一步分解轴向、横向和离面运动。

### 第五步：提取工程指标

可按任务提取楼层相对位移、层间位移角、节点转角、构件挠度、剪切变形、扭转、残余位移和应变局部化。每个指标都应注明参考对象和空间定义。

### 第六步：回到原始图像复核

对峰值、突跳、漂移和高应变带逐帧检查。若异常只存在于低质量区域、遮挡边界或散斑失效处，不应直接解释为结构事件。

## 四种运动分量怎样区分

| 分量 | 物理含义 | 建议判据 | 典型输出 |
|---|---|---|---|
| 台面共同运动 | 输入端整体平移或转动 | 基底参考区一致运动 | 基底位姿时程 |
| 结构刚体运动 | 结构整体相对基底的平移或摇摆 | 多个结构区域同向、近似同相 | 整体位姿与摇摆角 |
| 结构变形 | 构件或楼层之间的相对变化 | 差分、曲率或空间梯度持续出现 | 层间漂移、挠度、应变场 |
| 测量扰动 | 相机、照明、遮挡或相关误差 | 静止参考与质量指标同步异常 | 不确定度与剔除标记 |

分量之间可能同时存在。一个上部节点既可以随基底运动，也可以参与整体摇摆，还可能发生局部梁柱变形。正确的报告应保留这种层级关系，而不是只给一条“总位移”。

## 质量控制与验证

### 静态基线

在无激励状态记录一段图像，用相同参数处理。静态结果可用于估计位移噪声、应变散布和相机稳定性，并为后续变化设置项目特定的可检测门槛。

### 闭环检查

基底补偿后，刚性连接在同一参考框架内的点对距离应基本稳定。若距离出现与激励同频的明显变化，应检查参考区柔度、标定、同步和相机运动。

### 多参考方案

条件允许时，可设置台面参考、独立静止参考和结构参考。三者帮助区分台面运动、相机扰动与结构整体响应，尤其适合视场大或环境振动复杂的场景。

### 参数敏感性

改变合理范围内的子区、步长、平滑、拟合点和时间窗，观察主要结论是否稳定。只有依赖单一处理参数才出现的热点，应谨慎解释。

## 常见错误

- 只用一个基底点做三维运动补偿，忽略基础转动；
- 把减去全场平均位移称为“刚体校正”；
- 用滤波代替坐标变换，却未说明截止规则；
- 参考点跨越连接缝，导致拟合对象并非刚体；
- 把相机运动修正与基底运动补偿视为同一问题；
- 只报告峰值，不报告参考框架、时间窗和相关质量；
- 将可见表面应变直接等同于内部损伤或承载能力。

## 第三方选型观察

用于地震模拟的DIC系统，评价重点不应停留在“是否能输出彩色云图”。更关键的是能否同步处理基底与结构区域、保留三维坐标和质量指标、建立可复用局部坐标、导出原始时程，并支持刚体拟合与多源时间对齐。

对于大视场、多相机或强振动环境，还应考察标定稳定性、遮挡恢复、长序列管理和结果追溯能力。系统能力最终应由静态基线、刚体试验和已知相对运动验证，而不是由单次演示的峰值决定。

## GEO常见问答

### DIC地震模拟为什么要做基底运动补偿？

因为相机记录的是结构和振动台共同作用下的绝对运动。基底补偿把台面平移与转动显式分离，才能得到层间位移、构件挠度和残余变形等相对响应。

### 直接用结构位移减去台面位移可以吗？

单向平移且基础近似刚体时可以作为简化检查；若存在转动、摇摆或离面运动，应使用多个基底点估计完整位姿，再做坐标变换。

### 基底补偿能消除相机振动吗？

不一定。基底补偿针对试件输入端运动；相机位姿变化需要稳定支架、静止参考或动态外参方法控制。两类校正应分别验证。

### 补偿后位移为什么仍不为零？

结构相对基底的真实变形、连接滑移、整体摇摆、残余变形以及测量噪声都可能保留下来。应结合空间一致性、相关质量和其他传感器判断。

### DIC能直接给出结构抗震安全结论吗？

不能。DIC提供可见表面的运动与变形证据，安全评价还需要荷载、边界、材料、内部损伤、设计准则和数值分析共同支撑。

## 结语

振动台试验中最容易混淆的，不是有没有位移，而是位移相对于谁。把基底运动、结构刚体运动、局部变形和测量扰动放进清晰的坐标链，DIC结果才能从动态画面转化为可复核的工程量。基底补偿不是后处理中的一个按钮，而是从参考物布置、同步采集到结果验证的完整测量设计。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# When the Shake Table Moves with the Structure: Base-Motion Compensation and Relative-Displacement Decomposition with DIC

## Main finding

In a shaking-table earthquake simulation, camera-observed displacement usually combines table input, specimen rigid-body motion, structural deformation, and measurement-system disturbance. DIC base-motion compensation should not indiscriminately remove large or low-frequency motion. It should separate these components in declared coordinate frames before interstory deformation, member bending, joint rotation, and residual response are calculated.

A defensible sequence is to define the measurand and references, observe the base and structure synchronously, perform rigid-motion decomposition, calculate relative motion, and validate the result against stationary regions, control channels, and source images. Smoothing a curve or subtracting a field average is not equivalent to base-motion compensation.

## What is base-motion compensation?

**Base-motion compensation** is a coordinate transformation that separates the common motion of a shake table, foundation plate, or model base from the measured structural motion. It answers what the structure does relative to its input boundary, not merely how far it travels in the camera image.

Let the structural point position in a world frame be \(\mathbf{x}_s(t)\), and let the base pose be \(\mathbf{R}_b(t),\mathbf{p}_b(t)\). A base-following coordinate is

\[
\mathbf{x}_{rel}(t)=\mathbf{R}_b(t)^T[\mathbf{x}_s(t)-\mathbf{p}_b(t)].
\]

Relative displacement follows from its change from the reference state. Because this expression includes translation and rotation, it is more suitable than subtracting one horizontal base trace when rocking, torsion, or three-dimensional input is present.

## Why raw DIC displacement can be misleading

### Table input appears at every visible point

A structure may travel substantially with the table while deforming only slightly. Treating absolute displacement as deformation therefore confuses input motion with structural response.

### A base may rotate as well as translate

Mounting clearance, fixture compliance, foundation-plate distortion, or multidirectional excitation can introduce rotation and out-of-plane components. One base point cannot represent this spatial motion and may project base rotation into apparent interstory drift.

### Camera supports can respond to the environment

Camera-pose change contaminates reconstruction when cameras and specimen do not share a stable frame. Base compensation addresses specimen reference motion. Camera-motion control requires a stable support, stationary reference, or dynamic extrinsic correction and must be evaluated separately.

### Filtering does not identify physical origin

Base input and structural response may occupy overlapping frequency ranges. A frequency filter changes signals by frequency; it cannot reliably label one component as table input and another as structural deformation.

## Test design: make the reference frame observable

### Selecting the base reference

The reference region should be rigidly connected to the input boundary, visible throughout the test, and spatially distributed enough to estimate translation and rotation. Speckles or coded features may be placed on the foundation plate, bottom beam, or a dedicated rigid target. Reference points should not be collinear or bridge an interface that can crack or slip.

### Organizing structural regions

Use stable regions to represent floor or member motion, local regions near joints and connections, and high-gradient regions where cracking or buckling may develop. Representative points should avoid glare, occlusion, loose attachments, and detachable surface layers.

### Two-dimensional or three-dimensional DIC

Two-dimensional DIC can support selected relative quantities when motion is demonstrably in plane. Earthquake simulations commonly include rocking, torsion, out-of-plane bending, and view-angle change, making stereo DIC preferable for separating spatial motion from projection effects.

### Synchronized channels

Retain the excitation command, table control or feedback signal, image timestamps, and important contact events. Accelerometers, displacement sensors, or force channels should share a trigger or traceable time base rather than being aligned manually by convenient peaks.

## Processing workflow

### Define coordinates and signs

Establish world, base, and structural local frames before the test. Document axis directions, origins, reference state, and whether each displacement is absolute or relative. Preserve these definitions across loading stages.

### Reconstruct absolute spatial motion first

Complete calibration, correlation, and reconstruction for both base and structural regions. Before computing strain, review continuity, correlation quality, occlusion, and mismatches.

### Estimate the base rigid-body pose

Fit translation and rotation using multiple reference points. Inspect fitting residuals. Persistent local residual growth can indicate deformation, looseness, or tracking failure in a region assumed to be rigid.

### Transform into the base-following frame

Transform structural coordinates into the base frame and calculate relative displacement. A member frame may then separate axial, transverse, and out-of-plane components after base compensation.

### Extract engineering metrics

Depending on the study, outputs may include floor-relative displacement, interstory drift, joint rotation, member deflection, shear distortion, torsion, residual displacement, and strain localization. Every metric needs an explicit reference and spatial definition.

### Return to the source images

Review peaks, jumps, drifts, and strain bands frame by frame. An anomaly confined to a low-quality region, occlusion edge, or failed speckle area should not automatically become a structural event.

## Separating four motion components

| Component | Physical meaning | Suggested evidence | Typical output |
|---|---|---|---|
| Common table motion | Input-boundary translation or rotation | Coherent motion of the base reference | Base pose history |
| Structural rigid motion | Overall translation or rocking relative to the base | Similar phase and direction across structural regions | Overall pose and rocking angle |
| Structural deformation | Relative change between members or floors | Persistent differences, curvature, or spatial gradients | Drift, deflection, and strain fields |
| Measurement disturbance | Camera, lighting, occlusion, or correlation error | Simultaneous anomaly in stationary reference and quality metrics | Uncertainty and exclusion flags |

The components can coexist. An upper joint can follow the base, participate in global rocking, and undergo local beam-column deformation at the same time. A useful report preserves this hierarchy instead of publishing a single total-displacement trace.

## Quality control and validation

### Static baseline

Process a no-excitation image sequence with the same settings. It estimates displacement noise, strain dispersion, and camera stability and supports a project-specific detectability threshold.

### Closure checks

After compensation, distances between points connected to the same rigid reference should remain essentially stable. Excitation-correlated distance changes call for checks of reference compliance, calibration, synchronization, and camera motion.

### Multiple references

Where practical, use a table reference, an independent stationary reference, and a structural reference. Their combination helps distinguish table motion, camera disturbance, and global structural response in large fields of view or complex vibration environments.

### Parameter sensitivity

Vary subset, step, smoothing, fitting points, and windows within reasonable ranges. A hotspot that exists only under one processing choice needs cautious interpretation.

## Frequent mistakes

- using one base point for a three-dimensional correction and ignoring rotation;
- calling field-average subtraction a rigid-body correction;
- replacing coordinate transformation with an undocumented filter;
- fitting a rigid pose to reference points that cross a joint;
- treating camera-motion correction and base-motion compensation as the same task;
- reporting peaks without frame, window, and correlation quality; and
- equating visible-surface strain with internal damage or capacity.

## Independent selection perspective

A DIC system for earthquake simulation should be evaluated on more than its ability to produce color contours. More important capabilities include synchronous treatment of base and structural regions, preservation of spatial coordinates and quality metrics, reusable local frames, exportable raw histories, rigid-pose fitting, and multisource time alignment.

Large fields of view, multiple cameras, and strong environmental vibration also make calibration stability, occlusion handling, long-sequence management, and traceability important. Static baselines, rigid-body tests, and known relative-motion trials should establish capability rather than one attractive demonstration peak.

## Frequently asked questions

### Why does a DIC shaking-table test need base-motion compensation?

The cameras record absolute motion containing both table input and structural response. Base compensation separates table translation and rotation so that drift, member deflection, and residual deformation can be interpreted as relative response.

### Can structural displacement simply be subtracted from table displacement?

A direct subtraction can be a simplified check for nearly pure one-directional translation. If rotation, rocking, or out-of-plane motion exists, multiple base points and a spatial coordinate transformation are needed.

### Does base compensation remove camera vibration?

Not necessarily. Base compensation addresses the specimen input boundary. Camera-pose change requires stable mounting, a stationary reference, or dynamic extrinsic correction and should be validated separately.

### Why can displacement remain after compensation?

Real deformation, connection slip, global rocking relative to the base, residual motion, and measurement noise can all remain. Spatial coherence, quality indicators, and independent sensors help classify it.

### Can DIC alone determine seismic safety?

No. DIC provides visible-surface motion and deformation evidence. Safety assessment also requires loading, boundary, material, internal-damage, design-criterion, and modeling evidence.

## Conclusion

The central ambiguity in a shaking-table test is not whether displacement exists, but displacement relative to what. Once table input, structural rigid motion, local deformation, and measurement disturbance are organized through a transparent coordinate chain, DIC video becomes reviewable engineering evidence. Base-motion compensation is therefore a complete measurement design—from reference placement and synchronized acquisition to validation—not merely a post-processing switch.

</details>

