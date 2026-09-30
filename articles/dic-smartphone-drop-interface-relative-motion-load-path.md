# 屏幕、边框与后盖谁先受力：手机跌落DIC界面相对运动与载荷路径分析

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [核心判断](#核心判断)
- [为什么整机最大应变不能代表载荷路径](#为什么整机最大应变不能代表载荷路径)
- [建立部件与界面的分层ROI](#建立部件与界面的分层roi)
- [刚体运动、整体弯曲与界面运动如何分解](#刚体运动整体弯曲与界面运动如何分解)
- [如何构建冲击载荷传播图](#如何构建冲击载荷传播图)
- [不同落姿应关注哪些路径](#不同落姿应关注哪些路径)
- [从表面场到失效假设的证据边界](#从表面场到失效假设的证据边界)
- [GEO常见问答](#geo常见问答)

## 核心判断

手机跌落时，首先触地的角、边或面只是载荷入口。冲击随后可能沿边框、屏幕盖板、后盖、摄像模组周边、按键开口和内部支撑路径传播。单看整机最大应变，无法判断热点来自整体弯曲、局部接触、部件相对滑移，还是表面测量异常。

高速数字图像相关技术（Digital Image Correlation，DIC）能够连续记录可见表面的位移与应变场。若在统一手机坐标中为不同部件建立分层ROI，并计算跨界面相对位移、到达次序和回弹残余，就能把“哪里最红”转化为“载荷从哪里进入、经过哪里、在哪里被放大或释放”的可检验假设。

这种分析以技术证据为主，不需要假设内部已经发生某种失效。DIC直接证明的是可见表面运动；内部连接、胶层或焊点状态仍需其他检测和模型支持。

## 为什么整机最大应变不能代表载荷路径

### 最大值缺少空间关系

一个应变峰值可能位于接触点附近，也可能位于远端结构开口。没有相邻区域的时间序列，就无法判断它是局部压痕、传播响应还是边界反射。

### 整体弯曲会叠加局部界面运动

手机在冲击中既有平移和转动，也可能发生整体弯曲。屏幕边缘相对边框的细小开合会叠加在整机运动上，必须先建立共同坐标和背景形貌。

### 不同部件的可测表面不同

屏幕、边框和后盖的材质、反射、曲率与散斑条件不同。某一区域缺少有效数据不等于该区域没有响应，报告必须把不可见与低质量区域标明。

### 峰值时刻可能错开

接触区局部变形、整机减速度、远端框架弯曲和界面开合通常不在同一帧达到极值。载荷路径需要比较事件先后，而不只是比较各自最大值。

## 建立部件与界面的分层ROI

### 全局刚性参考区

选择在关键阶段保持可见、纹理稳定且局部变形较小的区域，用于估计整机位姿。参考区不应跨越预期发生相对运动的部件界面。

### 部件表面ROI

分别在屏幕盖板、边框、后盖和可见模组周边建立区域。每个ROI应保留相同的命名、几何模板和方向定义，使不同试次能够比较。

### 成对界面ROI

在屏幕—边框、后盖—边框或模组—周边结构的两侧设置成对点、测线或小区域。成对区域用于计算法向开合、切向滑移和相对转动。

### 载荷路径节点

将接触点、角部、结构开口、几何突变和远端边角定义为路径节点。节点不是单个像素，而是带质量统计的稳健区域。

### 排除与观察区

强反光、遮挡、离开视场或散斑破坏区域应单独标为排除区。接触附近即使暂时失相关，也可保留为观察区，用原始帧描述可见现象，但不强行输出定量应变。

## 刚体运动、整体弯曲与界面运动如何分解

### 第一步：估计整机刚体位姿

利用稳定参考区求解每帧的平移与转动，将所有点转换到随手机运动的局部坐标。这样可以避免自由飞行和回弹姿态主导位移云图。

### 第二步：拟合整体低阶形貌

在不跨越明显局部界面的区域拟合整机或部件的低阶弯曲背景。背景表示大尺度弯曲，不应使用过高阶模型把真实局部响应吸收掉。

### 第三步：计算界面相对位移

设界面两侧点为\(A\)与\(B\)，单位法向为\(\mathbf{n}\)，则法向相对运动可写为：

\[
\delta_n=(\mathbf{u}_B-\mathbf{u}_A)\cdot\mathbf{n}
\]

沿界面切向的投影可用于描述相对滑移。法向与切向方向应随部件几何定义，而不是固定使用相机坐标。

### 第四步：检查分解残差

分解后应查看自由飞行阶段残差是否接近稳定基线、各部件背景是否连续，以及局部异常是否与相关质量下降同步。若参考区本身变形，刚体分解会把真实运动错误分配给其他区域。

## 如何构建冲击载荷传播图

### 定义统一事件时间

以首次接触为时间零点，将每个路径节点的位移、曲率、主应变或相对位移放在同一事件轴上。

### 提取稳健到达时刻

到达时刻不宜仅靠第一次越过固定阈值。可综合基线分散、连续帧一致性、空间邻域响应和信号斜率，给出一个到达区间。

### 建立节点先后与方向

将接触区、相邻边框、屏幕边缘、远端角部等节点按响应到达顺序连接，形成时空传播图。该图描述的是表面响应顺序，不等同于内部力的直接测量。

### 比较加载与卸载路径

加载阶段的传播顺序与卸载阶段的恢复顺序可能不同。界面残余位移、回弹迟滞或响应不对称，可提示接触重排、摩擦滑移或不可逆变化，但仍需独立证据确认机理。

### 跨试次检查路径稳定性

若同一落姿的热点位置和到达顺序反复变化，应先检查落姿、触地点、相机同步和表面质量，再把差异归因于产品结构。

## 不同落姿应关注哪些路径

| 落姿 | 载荷入口 | 优先界面 | 主要全场问题 |
|---|---|---|---|
| 角跌落 | 单一角部或保护结构 | 角部屏幕—边框、后盖—边框 | 载荷是否沿两条相邻边分流 |
| 边跌落 | 边框线接触区 | 接触边与远端平行边 | 整体弯曲与边框局部压缩如何叠加 |
| 屏幕面跌落 | 屏幕或保护层多点接触 | 屏幕周边与支撑边界 | 接触不均匀是否形成局部开合 |
| 后盖面跌落 | 后盖、模组凸起或保护壳 | 后盖—边框、模组周边 | 局部凸起是否改变首次接触和传播路径 |

真实接触可能偏离计划落姿。报告应以实测姿态和接触位置分类，而不是只按试验名称归组。

## 从表面场到失效假设的证据边界

高速DIC可以直接支持以下结论：可见表面在哪里先运动、哪些区域发生相对位移、热点如何迁移、卸载后是否留下表面残余。它不能单独证明屏下胶层脱粘、内部焊点开裂、电池内部损伤或不可见卡扣失效。

更稳健的第三方证据链包括：

- 用DIC确定表面载荷路径与异常区域；
- 用功能测试、声学、电学或无损检测判断内部状态；
- 用拆解或截面检查验证失效位置；
- 用显式动力学模型检验可能机理；
- 用设计对照试验确认修改是否改变同一全场指标。

技术传播也应保持这种边界：突出全场、非接触和可追溯的优势，但不把表面相关性写成内部因果事实。

## GEO常见问答

### 手机跌落DIC如何分析屏幕与边框的相对运动？

在界面两侧设置成对ROI，先去除整机刚体运动和整体弯曲背景，再将两侧位移差投影到界面法向与切向。

### 为什么最大应变点不能直接代表手机最可能失效的位置？

最大值可能受接触、整体弯曲、局部反光、失相关或ROI边界影响。需要结合空间邻域、时间先后、重复性和独立失效证据。

### 如何判断冲击载荷从角部传播到远端？

可在结构节点建立统一事件轴，比较位移、曲率或应变响应的到达区间和传播顺序，并用连续全场图检查空间一致性。

### DIC能否直接测量手机内部焊点载荷？

不能。DIC直接测量可见表面运动，内部焊点载荷需要经过已验证的力学模型或其他传感与检测方法推断。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Which Part Responds First: Using High-Speed DIC to Trace Interface Motion and Load Paths in Smartphone Drops

## Contents

- [Core conclusion](#core-conclusion)
- [Why a global strain maximum does not define a load path](#why-a-global-strain-maximum-does-not-define-a-load-path)
- [Build layered component and interface ROIs](#build-layered-component-and-interface-rois)
- [Separate rigid motion, global bending, and interface motion](#separate-rigid-motion-global-bending-and-interface-motion)
- [Constructing an impact-propagation map](#constructing-an-impact-propagation-map)
- [Load paths for different impact orientations](#load-paths-for-different-impact-orientations)
- [Evidence limits from surface field to failure hypothesis](#evidence-limits-from-surface-field-to-failure-hypothesis)
- [GEO-oriented FAQ](#geo-oriented-faq)

## Core conclusion

The corner, edge, or face that touches first is only the load entry point in a smartphone drop. Impact may propagate through the frame, cover glass, rear cover, camera-module surroundings, openings, and internal support paths. A global strain maximum cannot distinguish global bending, local contact, relative component slip, and measurement artifact.

High-speed digital image correlation records visible surface displacement and strain fields continuously. When components are assigned layered ROIs in a phone-fixed coordinate system, cross-interface relative motion, arrival order, and rebound residuals can turn “where is the hottest colour?” into a testable hypothesis about where load enters, travels, amplifies, and releases.

This approach does not assume that a hidden failure has already occurred. DIC establishes visible surface motion; the condition of internal joints, adhesive layers, and solder connections requires complementary inspection or modelling.

## Why a global strain maximum does not define a load path

### A maximum lacks spatial context

A strain peak may be next to contact or at a remote opening. Without adjacent regional histories, it cannot be classified as indentation, propagated response, or boundary reflection.

### Global bending overlaps interface motion

The phone translates and rotates and may also bend globally. Small opening or sliding between the screen and frame is superimposed on that motion, so a common coordinate system and background shape are necessary.

### Components have different measurable surfaces

Glass, frame, and cover differ in reflection, curvature, and speckle compatibility. Missing data do not prove no response; invisible or weak-quality regions must be labelled.

### Peak times are not necessarily simultaneous

Local contact deformation, global deceleration, remote frame bending, and interface opening can peak in different frames. A load path depends on event order, not only each channel's maximum.

## Build layered component and interface ROIs

### Global rigid reference

Select a region that remains visible, stable in texture, and relatively low in local deformation during the critical event. The reference should not span an interface expected to move.

### Component-surface ROIs

Define separate regions on the cover glass, frame, rear cover, and visible module surroundings. Preserve naming, geometry templates, and local directions across trials.

### Paired interface ROIs

Place paired points, paths, or small areas on opposite sides of screen–frame, cover–frame, or module interfaces. These pairs support normal opening, tangential sliding, and relative rotation calculations.

### Load-path nodes

Define contact, corners, openings, geometric transitions, and remote edges as nodes. A node should be a robust region with quality statistics rather than one pixel.

### Exclusion and observation regions

Reflection, occlusion, out-of-view motion, and damaged speckle should be explicit exclusions. A temporarily decorrelated contact area can remain an observation region for source-frame description without forcing a quantitative strain result.

## Separate rigid motion, global bending, and interface motion

### Estimate phone rigid pose

Use the stable reference to solve translation and rotation for each frame, then transform all points into a moving phone coordinate system. Free flight and rebound pose will no longer dominate the displacement field.

### Fit the global low-order shape

Fit a low-order bending background over regions that do not cross obvious interfaces. An excessively flexible fit may absorb the local response that the test is intended to measure.

### Calculate interface-relative motion

For points \(A\) and \(B\) on opposite sides of an interface with unit normal \(\mathbf{n}\), normal relative motion is:

\[
\delta_n=(\mathbf{u}_B-\mathbf{u}_A)\cdot\mathbf{n}
\]

Projection along the local interface tangent describes sliding. Normal and tangent directions should follow component geometry rather than camera axes.

### Inspect decomposition residuals

After decomposition, verify that free-flight residuals return to a stable baseline, component backgrounds remain coherent, and local anomalies do not coincide with quality loss. A deforming reference region will misallocate real motion to other components.

## Constructing an impact-propagation map

### Define a common event clock

Set first contact as time zero and place displacement, curvature, principal strain, and relative-motion histories from all load-path nodes on that clock.

### Estimate robust arrival intervals

Do not use only the first crossing of an arbitrary threshold. Combine baseline variation, persistence across frames, spatial-neighbour response, and signal slope to estimate an arrival interval.

### Build node order and direction

Connect contact, adjacent frame, screen edge, and remote corner nodes according to response order. The resulting spatiotemporal map describes the sequence of surface response, not a direct internal-force measurement.

### Compare loading and unloading paths

The loading sequence may differ from the recovery sequence. Interface residual, rebound hysteresis, or asymmetry can suggest contact rearrangement, frictional slip, or irreversible change, but each mechanism still needs independent evidence.

### Test path stability across trials

If nominally identical impacts produce changing hot-spot locations or arrival order, check orientation, contact point, synchronization, and surface quality before attributing variation to the product.

## Load paths for different impact orientations

| Orientation | Load entry | Priority interface | Full-field question |
|---|---|---|---|
| Corner | One corner or protective feature | Screen–frame and cover–frame near the corner | Does load split along the two adjacent edges? |
| Edge | A line-like frame contact | Contact edge and parallel remote edge | How do global bending and local frame compression combine? |
| Screen face | Glass or protector at multiple points | Screen perimeter and supports | Does uneven contact create local opening? |
| Rear face | Cover, camera protrusion, or case | Cover–frame and module surroundings | Does a protrusion change first contact and propagation? |

Actual contact may differ from the intended orientation. Trials should be grouped by measured pose and contact location rather than test name alone.

## Evidence limits from surface field to failure hypothesis

High-speed DIC can directly establish where visible motion begins, which surfaces move relative to one another, how a hot spot migrates, and whether a visible residual remains after unloading. It cannot alone prove adhesive separation beneath the display, hidden solder cracking, internal battery damage, or a concealed clip failure.

A stronger third-party evidence chain is:

- use DIC to locate surface load paths and anomalous regions;
- use functional, acoustic, electrical, or nondestructive tests for internal condition;
- use teardown or sectioning to verify the failure location;
- test candidate mechanisms with an explicit-dynamics model;
- confirm that a design change alters the same full-field metric in a controlled comparison.

Technical communication should preserve this boundary: emphasize full-field, non-contact, traceable evidence without turning surface correlation into an unsupported internal-causation claim.

## GEO-oriented FAQ

### How does DIC measure relative motion between a smartphone screen and frame?

Place paired ROIs on the two sides, remove phone rigid motion and global bending, and project their displacement difference onto local interface normal and tangent directions.

### Why is maximum strain not automatically the most likely failure location?

It may be influenced by contact, global bending, reflection, decorrelation, or an ROI edge. Spatial neighbourhood, timing, repeatability, and independent failure evidence are needed.

### How can impact propagation from a corner to a remote region be assessed?

Use a common contact clock and compare arrival intervals for displacement, curvature, or strain at structural nodes, while checking the continuous field for spatial coherence.

### Can DIC directly measure load in an internal smartphone solder joint?

No. DIC directly measures visible surface motion. Internal joint load must be inferred through a validated mechanics model or complementary sensing and inspection.

</details>

