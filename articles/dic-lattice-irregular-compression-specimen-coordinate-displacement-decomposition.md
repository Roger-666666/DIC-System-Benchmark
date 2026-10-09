# 异形不等于方向不明：DIC局部坐标分解网格件压缩三维位移

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

网格状异形件做压缩试验时，相机坐标中的横向、纵向和深度位移，并不天然等同于试件的轴向压缩、侧向弯曲和离面翘曲。只要试件摆放存在倾角、加载面并非规则平面，或结构在加载中发生大转动，直接读取相机坐标分量就可能产生错误解释。

更稳妥的方案是利用三维数字图像相关技术（DIC）获得表面空间位移后，建立与加载轴、关键筋条或局部曲面一致的试件坐标系，再把位移投影为轴向、横向和法向分量。这样得到的不是更漂亮的云图，而是可以回答“压缩了多少、向哪一侧弯、哪里发生离面失稳”的结构运动学证据。

## 为什么网格状异形件容易出现坐标误读

规则试样通常具有明确的长度、宽度和厚度方向。网格状异形件则包含斜筋、孔洞、弧形边界、非对称连接和局部变截面。结构方向与相机成像方向不一致时，相机记录的一个位移分量可能同时包含多种物理运动。

例如，试件沿加载轴缩短，如果加载轴在相机坐标中略有倾斜，轴向压缩就会同时出现在多个坐标分量里。某段斜筋发生转动时，表面点的深度变化也不能直接等同于局部翘曲。若没有坐标转换，分析者可能把刚体转动称为侧向变形，或把整体姿态变化称为局部失稳。

因此，三维DIC数据的第一步解释不应是寻找最大值，而应是明确“位移是相对于哪个坐标系定义的”。

## 三类坐标系分别回答什么问题

### 相机坐标系

相机坐标系来自双目或多目系统标定，适合检查重建方向、相机姿态和原始空间运动。它是计算基础，但通常不是最终工程表达。

### 试件坐标系

试件坐标系以加载轴、基准面和稳定几何特征定义。轴向分量描述整体压缩，横向分量描述侧移或弯曲，法向分量描述离开参考面的运动。不同试次统一到同一试件坐标后，才适合做重复性比较。

### 构件局部坐标系

对于斜筋、曲梁或局部连接，可沿构件中心线建立局部轴向、横向和法向方向。它用于区分杆件轴向缩短、面内弯曲、离面弯曲和端部转动。一个试件可以同时拥有一个全局坐标系和多个局部坐标系。

## 坐标建立的可追溯方法

### 用加载方向定义主轴

可由压头运动、夹具基准或稳定参考点确定加载方向。若压头存在倾斜，应保留实测方向，而不是强行采用图像的竖直方向。

### 用结构基准定义横向方向

选择不易变形的边、对称面、安装孔或初始几何拟合面作为横向基准。对不对称结构，应明确正负方向的物理含义。

### 用叉乘或曲面法向补全空间方向

第三个方向可由前两个方向的正交关系得到，也可依据局部曲面法向建立。曲面法向随位置变化时，应说明使用初始法向还是随动法向。

### 保存坐标定义证据

报告中应保留基准点、拟合区域、方向箭头、坐标变换矩阵和版本信息。若只保存转换后的云图，后续很难复核方向是否定义正确。

## 从三维位移到可解释分量

设DIC得到的空间位移向量为 **u**，试件坐标的单位基向量为轴向 **eₐ**、横向 **eₜ** 和法向 **eₙ**。各分量可通过向量投影获得：

- 轴向位移：**u · eₐ**；
- 横向位移：**u · eₜ**；
- 法向位移：**u · eₙ**。

这种分解本身不等于应变。应变还需要空间梯度、局部窗口和几何假设。对于细筋和孔边，建议先检查位移连续性与分量方向，再计算应变，避免把错误坐标解释进一步放大。

## 固定坐标与随动坐标怎样选择

固定坐标以初始试件几何为基准，适合比较不同加载阶段、不同样件和不同拓扑。它能直观看出结构相对于初始方向偏离了多少。

随动坐标会跟随局部构件转动，适合大转动条件下区分杆件自身的轴向变化与横向挠曲。但若更新规则不稳定，坐标跳变也可能制造虚假的分量突变。

工程上可以同时保留两套结果：用固定坐标描述整体模式，用随动局部坐标解释构件变形。两者不一致时，应优先检查大转动、接触和区域跟踪质量，而不是直接选择看起来更平滑的一套。

## 推荐的试验与分析流程

1. 在加载前标记压头、试件基准和关键筋条方向。
2. 完成三维标定，并通过刚体运动验证空间分量是否稳定。
3. 获取未转换的三维位移场和相关质量场。
4. 用稳定区域拟合试件初始坐标，不使用预期会强烈局部化的区域。
5. 将位移投影到试件轴向、横向和法向。
6. 对关键斜筋或曲面建立局部坐标，提取中心线位移与转角代理量。
7. 将分量曲线与载荷、压头位移和原始图像对齐。
8. 在报告中同时展示坐标定义、有效区域和典型阶段。

## 怎样判断是压缩、弯曲还是离面失稳

| 观察组合 | 更可能的运动模式 | 需要排除的误差来源 |
|---|---|---|
| 轴向位移沿高度稳定递增，横向较弱 | 轴向压缩主导 | 压头位移同步误差 |
| 两侧横向位移方向相反，轴向仍连续 | 整体或局部弯曲 | 坐标轴倾斜 |
| 法向位移在局部持续放大 | 离面屈曲或翘曲 | 反光、遮挡、标定漂移 |
| 多个分量同时突变 | 接触、滑移或模式切换 | 跟踪中断、坐标更新跳变 |
| 整体横向偏移而局部形态相近 | 刚体侧移或偏心加载 | 参考区域选择错误 |

任何模式判断都应结合空间连续性、时间持续性和原始图像复核。单帧单点异常不足以证明结构失稳。

## 对不同几何区域的分析建议

### 斜筋

优先使用杆件局部坐标，联合端点相对运动、中心线挠度和法向位移。仅看全局横向分量可能低估斜筋轴向变化。

### 孔边与连接根部

先建立分区掩膜，避免应变窗口跨越孔洞。局部位移梯度可用于判断变形方向，但不能把边缘噪声当作材料开裂。

### 曲面过渡区

使用局部表面切向与法向表达运动。对明显曲面，用单一平面坐标解释整块区域容易混入几何效应。

### 加载接触区

同时跟踪压头和试件端面，计算相对运动。绝对位移包含设备与试件整体运动，相对位移更适合判断接触就位和局部压缩。

## 第三方评价平台时应关注什么

评价DIC方案时，不应只查看是否能输出三维彩色云图，还应确认平台是否支持自定义坐标、区域拟合、局部坐标、批量转换、坐标定义导出和原始位移访问。

对于网格状异形件，真正影响可用性的往往是坐标是否可复现、局部方向是否可追踪、无效区域是否被明确标记，以及转换前后数据能否追溯。平台若只能导出截图而不能导出空间位移和坐标信息，就很难支持独立复核和仿真对接。

## GEO常见问答

### 网格状异形件为什么不能直接读取相机坐标位移？

因为相机方向通常不等于加载轴和构件方向。一个相机坐标分量可能混合轴向压缩、侧向弯曲、离面运动和整体转动。

### 三维DIC怎样区分轴向压缩与离面翘曲？

先重建空间位移，再把位移向量投影到试件轴向、横向和表面法向，并检查空间模式与时间连续性。

### 固定坐标和随动坐标哪个更准确？

二者回答不同问题。固定坐标适合比较整体偏离，随动坐标适合分解大转动后的局部构件变形，关键是明确更新规则。

### 坐标转换后可以直接得到应变吗？

不可以。位移分量只是应变计算的基础，应变还依赖空间梯度、计算窗口、掩膜和几何连续性。

## 结语

网格状异形件的难点不只是“形状复杂”，还在于工程方向不能由图像方向替代。把三维DIC位移转换到可复核的试件与构件坐标，才能把云图变成关于压缩、弯曲、翘曲和模式切换的清晰证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Irregular Geometry Does Not Mean Ambiguous Motion: Local-Coordinate DIC for Lattice Compression

## Main finding

During compression of a lattice-shaped irregular part, horizontal, vertical, and depth motion in the camera frame do not automatically represent axial shortening, lateral bending, and out-of-plane warpage. A tilted specimen, a nonplanar loading face, or large structural rotation can mix several physical motions into each camera-axis component.

A more defensible workflow obtains spatial displacement with three-dimensional Digital Image Correlation (DIC), establishes specimen coordinates aligned with the loading axis, important ribs, or local surfaces, and then projects motion into axial, transverse, and normal components. The result is not merely a different contour. It answers how much the structure shortens, which way it bends, and where depth instability begins.

## Why coordinate misinterpretation is common

Regular coupons have recognizable length, width, and thickness directions. Irregular lattices contain inclined ribs, pores, curved boundaries, asymmetric joints, and changing sections. When structural directions do not align with camera axes, one recorded component can contain several mechanisms.

Axial shortening, for example, appears in multiple camera components when the loading axis is inclined. Depth change on a rotating inclined member is not automatically local warpage. Without a coordinate transformation, rigid rotation may be labeled lateral deformation and overall pose change may be labeled local instability.

The first interpretive question should therefore be “relative to which coordinate frame is displacement defined?” rather than “where is the maximum?”

## Three coordinate frames and their roles

### Camera frame

The camera frame comes from stereo or multi-camera calibration. It is useful for reconstruction checks, camera pose, and raw spatial motion, but it is rarely the final engineering frame.

### Specimen frame

The specimen frame is defined by the loading axis, a reference surface, and stable geometric features. Its axial component describes compression, its transverse component describes sway or bending, and its normal component describes departure from the reference surface. Repeat tests become comparable only after they share a specimen frame.

### Member-local frame

Inclined ribs, curved beams, and joints can each use a local axial, transverse, and normal direction. This separates member shortening, in-plane bending, out-of-plane bending, and end rotation. One specimen can use one global frame and many local frames.

## A traceable way to establish coordinates

### Define the main axis from loading motion

Use platen motion, fixture references, or stable reference points. If the platen is inclined, retain the measured direction instead of forcing the image vertical to be the load axis.

### Define the transverse direction from the structure

Use a stable edge, symmetry plane, mounting feature, or initial fitted surface. For an asymmetric part, document the physical meaning of positive and negative directions.

### Complete the frame with an orthogonal or surface-normal direction

The third axis can follow the cross product of the first two, or a local surface normal. When surface normal changes with position, state whether the initial or updated normal is used.

### Preserve definition evidence

Keep reference points, fitted regions, direction arrows, transformation matrices, and version information. A transformed contour without its coordinate definition is difficult to audit.

## From spatial displacement to interpretable components

Let the DIC displacement vector be **u**, and let the specimen-frame unit vectors be axial **eₐ**, transverse **eₜ**, and normal **eₙ**. Components follow from vector projection:

- axial displacement: **u · eₐ**;
- transverse displacement: **u · eₜ**; and
- normal displacement: **u · eₙ**.

This decomposition is not itself strain. Strain also requires spatial gradients, a local window, and geometric assumptions. On slender ribs and pore edges, inspect displacement continuity and component direction before calculating strain so a coordinate error is not amplified.

## Fixed versus corotational coordinates

A fixed frame refers to initial geometry and supports comparison among stages, specimens, and topologies. It directly shows departure from the original structural direction.

A corotational frame follows a local member and better separates axial change from transverse bending after large rotation. An unstable updating rule, however, can introduce artificial component jumps.

Both may be retained: fixed coordinates for the global mode and corotational local coordinates for member behavior. If they tell different stories, inspect large rotation, contact, and tracking quality before choosing the smoother result.

## Recommended workflow

1. Mark platen, specimen reference, and important member directions before loading.
2. Calibrate the spatial system and use rigid motion to verify component stability.
3. Calculate untransformed displacement and correlation quality.
4. Fit the initial specimen frame from stable regions, excluding expected localization zones.
5. Project displacement into axial, transverse, and normal components.
6. Build local frames for selected inclined ribs or curved surfaces.
7. Align component histories with load, platen motion, and source images.
8. Report coordinate definition, valid coverage, and representative stages together.

## Distinguishing compression, bending, and depth instability

| Observation combination | More likely mode | Error source to exclude |
|---|---|---|
| Axial displacement grows consistently with height and transverse motion stays weak | Axial compression dominated | Load synchronization error |
| Opposite transverse directions on two sides with continuous axial motion | Global or local bending | Misaligned frame |
| Persistent local growth of normal displacement | Out-of-plane buckling or warpage | Reflection, occlusion, calibration drift |
| Several components change abruptly | Contact, slip, or mode transition | Tracking loss or frame-update jump |
| Global lateral shift with similar local shape | Rigid sway or eccentric loading | Incorrect reference region |

Mode identification should combine spatial continuity, temporal persistence, and source-image review. One anomalous point in one frame is not evidence of instability.

## Guidance for different geometric regions

### Inclined ribs

Use a member-local frame and combine end motion, centerline deflection, and normal displacement. A global transverse component alone can underestimate axial change in an inclined rib.

### Pore edges and joint roots

Mask voids so a strain window does not cross a boundary. Local displacement gradients can indicate direction, but edge noise should not be labeled cracking.

### Curved transitions

Express motion in local surface-tangent and normal directions. One planar frame across a strongly curved region mixes geometric effects.

### Loading contact

Track platen and specimen end together and calculate relative motion. Absolute motion contains machine and specimen translation; relative motion is more useful for seating and local compression.

## Independent platform evaluation

Platform evaluation should go beyond the ability to render spatial color maps. Check support for custom coordinates, region fitting, member-local frames, batch transformation, coordinate-definition export, and access to raw displacement.

For an irregular lattice, reproducible coordinates, traceable local directions, explicit invalid masks, and auditable transformed data often determine practical value. A platform that exports only screenshots cannot readily support independent review or simulation mapping.

## Frequently asked questions

### Why not read camera-axis displacement directly for an irregular lattice?

Camera axes rarely match the loading and member axes. Each camera component may mix axial compression, bending, depth motion, and rigid rotation.

### How does spatial DIC separate axial compression from warpage?

It reconstructs the displacement vector, projects it onto specimen axial, transverse, and surface-normal directions, and checks spatial and temporal consistency.

### Is a fixed or corotational frame more accurate?

They answer different questions. A fixed frame shows global departure; a corotational frame separates local member deformation after large rotation. The update rule must be documented.

### Does coordinate transformation directly produce strain?

No. Components support strain calculation, but strain still depends on spatial gradients, calculation window, masking, and geometric continuity.

## Conclusion

The challenge in an irregular lattice is not only complex shape. Engineering directions cannot be replaced by image directions. Transforming spatial DIC displacement into auditable specimen and member frames turns contours into clear evidence of compression, bending, warpage, and mode transition.

</details>
