# 三维DIC怎么测出晶圆的离面翘曲：三条技术主线

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 晶圆热翘曲测量难在三个前提同时不成立：被测物在升温、被测物被窗口挡住、被测物整体在漂。三维DIC要在这三个前提下拿到亚微米级的离面数据，靠的不是某一项绝技，而是三条技术主线各自解决一段：双目立体视觉把“面外”变成可解算的几何量，亚像素散斑匹配把几何量推进到亚微米分辨率，误差抑制算法把窗口折射、刚体漂移、温度错配三类干扰逐一扣掉。本文按“几何—匹配—误差”的顺序拆这三条主线，并说明从位移场到翘曲量、再到CTE的换算路径。

> **关键词：** 三维DIC；离面位移；双目立体视觉；亚像素匹配；折射校准；刚体位移消除；热膨胀系数

## 目录

- [一、三个前提同时不成立](#一三个前提同时不成立)
- [二、主线一：双目几何，把面外变成可解算的量](#二主线一双目几何把面外变成可解算的量)
- [三、主线二：亚像素匹配，把分辨率推下去](#三主线二亚像素匹配把分辨率推下去)
- [四、主线三：误差抑制，三类干扰逐项扣掉](#四主线三误差抑制三类干扰逐项扣掉)
- [五、从位移场到翘曲量：参考面是第一个岔路口](#五从位移场到翘曲量参考面是第一个岔路口)
- [六、从位移场到CTE：差分、拟合与陷阱](#六从位移场到cte差分拟合与陷阱)
- [七、这套方法在哪里会失效](#七这套方法在哪里会失效)
- [八、常见问题](#八常见问题)

## 一、三个前提同时不成立

常规的形貌测量有一个默认前提：被测物静止，环境稳定，视线不受阻挡。晶圆热翘曲测试把这三条同时打破。

升温过程中晶圆一直在动，等温阶段才勉强算静止；高低温试验箱有观察窗，相机只能隔着玻璃看；升温带来热气流，空气密度不均，成像条纹抖动。再加上晶圆本身是低对比度的镜面硅片，直接成像几乎是白板。

| 干扰源 | 量级感受 | 后果 |
| --- | --- | --- |
| 窗口折射 | 与入射角、窗厚相关 | 位移场整体缩放与畸变 |
| 热气流 | 随时间波动 | 图像抖动、匹配噪声上升 |
| 刚体漂移 | 与装夹、热膨胀相关 | 真实变形被整体平移掩盖 |
| 表面低对比度 | — | 相关匹配无从下手 |

## 二、主线一：双目几何，把面外变成可解算的量

单目相机拍一张平面，能得到面内的两个坐标，面外那一维是丢掉的。

双目立体视觉的思路就是三角测量：两台相机从不同角度观察同一点，两条视线在空间中交会，交点就是该点的三维坐标。前提是两台相机的相对位置与姿态已知，也就是标定。

| 环节 | 解决什么 | 失准后的表现 |
| --- | --- | --- |
| 内参标定 | 每台相机的成像模型 | 全场均匀缩放误差 |
| 外参标定 | 两相机的相对位姿 | 深度方向系统性倾斜 |
| 畸变校正 | 镜头非线性 | 边缘区域弯曲失真 |
| 参考面建立 | 零位基准 | 翘曲量整体偏移一个常数 |

晶圆测试里，标定还有一个特殊要求：要在“实际成像条件”下完成。隔着观察窗标定和拆掉窗标定，结果不一样，冷态与热态的光路也略有差别。

拿到三维坐标之后，离面位移的定义就变得直白：同一物点在变形前后的三维坐标之差，投影到参考面法向上的分量。

## 三、主线二：亚像素匹配，把分辨率推下去

相机传感器的像素是有限的。一片 150 mm 直径的晶圆，若在图像里占 2000 像素宽度，一个像素对应 75 μm。如果只做到整像素匹配，量化台阶就有 75 μm，测出来的曲线会是阶梯状。

亚像素算法的思路是：整像素匹配只找到一个粗略位置，真正的极值点落在相邻像素之间。利用相关系数在极值附近的分布形状（拟合抛物面或高斯曲面），可以把这个位置插值到 0.01 像素甚至更细的量级。这样一来，同一个 75 μm/像素 的成像比例，位移分辨率能落到亚微米。

| 环节 | 作用 | 对最终精度的贡献 |
| --- | --- | --- |
| 散斑/纹理质量 | 提供可匹配的随机特征 | 决定匹配是否可靠 |
| 子区尺寸 | 匹配窗口大小 | 大子区抗噪好、空间分辨率低 |
| 亚像素插值 | 突破整像素量化 | 把台阶降到亚微米量级 |
| 立体匹配 | 左右图像素对应 | 决定深度（离面）精度 |

硅片表面是镜面的，没有天然纹理，直接拍出来是一片均匀亮区，相关系数曲面平坦，匹配会在任意位置“收敛”，结果是随机噪声。所以要么在表面制作散斑，要么利用表面已有的微结构（电路图形、镀层颗粒）作为天然特征。

高温场景下散斑还有个额外要求：在 150℃ 全程不能起皮、不能流淌、不能与基底发生相对滑移。散斑一旦在某个温度点滑移，之后的位移场就整体偏移。

## 四、主线三：误差抑制，三类干扰逐项扣掉

**第一类：刚体位移。** 晶圆放在试验箱的支架上，支架随温度膨胀、样品可能轻微滑移、相机支架本身也在热胀。一片直径 150 mm 的晶圆，如果整体平移 50 μm，测出来的“翘曲”就虚高 50 μm。

处理办法是刚体位移消除：选取一组假定不变的基准点（或利用形貌拟合），解算出整体平移与旋转的六个自由度，从位移场中扣除。关键在“假定不变”的判断——基准选错，扣掉的就是真实变形。

**第二类：视窗折射。** 相机隔着观察窗拍摄，光线从空气进入玻璃再进入腔内热空气，两次折射。平板玻璃在正入射时影响小，但相机在视场边缘是斜着看进去的，等效光程被拉长，成像位置产生偏移，于是位移场出现与视场位置相关的系统性畸变。

处理办法是折射校准：把窗口的厚度与折射率、相机的视角关系纳入模型，对视线的传播路径做反向追迹，把像点位置修正回真实空间位置。

**第三类：温度与图像的错配。** 升温不是瞬间完成的，样品温度与腔内空气温度、与热电偶读数之间有时间差；相机采集与温度记录若不同步，某一帧图像对应的真实温度就说不准。对于要反演 CTE 的应用，温度错配直接变成系数误差。

处理办法是温-图同步：由同一触发源驱动温度记录与图像采集，或者以温度平台（保温段）作为对齐锚点，把帧号与温度节点一一绑定。

| 干扰 | 性质 | 表现特征 | 对策 |
| --- | --- | --- | --- |
| 刚体位移 | 全场一致的平移/旋转 | 位移场整体偏移 | 基准点解算后扣除六自由度 |
| 视窗折射 | 与视场位置相关的偏差 | 中心正常、边缘畸变 | 折射模型反向追迹校准 |
| 温度错配 | 时间轴错位 | CTE 系数整体偏移 | 同源触发或平台锚定 |
| 热气流 | 随机噪声 | 高频抖动、匹配残差大 | 等待均温、多帧平均 |

## 五、从位移场到翘曲量：参考面是第一个岔路口

参考面通常有三种取法：拟合平面（最小二乘）、三点定面、以及以初始状态为零位。三种取法算出来的翘曲值可以差出一大截，尤其在形貌非对称时。

| 参考面取法 | 计算方式 | 适用与代价 |
| --- | --- | --- |
| 最小二乘拟合平面 | 全场残差平方和最小 | 通用，但对局部塌陷不敏感 |
| 三点定面 | 取三个支撑点确定平面 | 贴合实际支撑工况，选点敏感 |
| 初始状态零位 | 以第一帧为基准 | 便于看演化，掩盖初始形貌 |
| 拟合球面 | 扣除整体球面弯曲 | 分离“整体拱起”与“局部起伏” |

实际操作里，比较稳的做法是同时给出两组数：一组以初始状态为零位（看随温度演化），一组以拟合平面为基准（看绝对形貌）。

## 六、从位移场到CTE：差分、拟合与陷阱

热膨胀系数的反演，本质上是从位移场里提取“单位温升对应的应变”。路径是：取两个温度节点的位移场，做差得到相对位移，再对空间坐标求梯度得到应变，应变除以温差就是等效 CTE。

**陷阱一：把刚体位移当成热膨胀。** 如果刚体位移没有扣干净，差分出来的“膨胀”里混着整体平移，CTE 会算得偏大。

**陷阱二：用局部点代替全场。** 单点反演对噪声极其敏感，一个点的匹配误差 0.5 μm，在 10 mm 基距上就是 50 με 的应变误差。全场拟合（把上万个点一起做最小二乘）能把随机误差压下去。

**陷阱三：忽略非均匀性。** 真实晶圆的膨胀不是均匀的，局部有约束、有界面、有结构差异。用一个全场平均值代表整片，会把局部失配掩盖掉。

| 反演步骤 | 输入 | 输出 | 主要风险 |
| --- | --- | --- | --- |
| 位移场差分 | 两温度节点位移场 | 相对位移场 | 刚体残余导致偏差 |
| 空间梯度 | 相对位移场 | 应变场 | 噪声放大 |
| 除以温差 | 应变场 + 温度 | 等效 CTE 场 | 温度错配 |
| 分区统计 | CTE 场 | 中心/边缘/象限值 | 分区不当掩盖梯度 |

## 七、这套方法在哪里会失效

**表面全镜面且无法制斑**：无纹理，匹配不可靠。此时要么改变表面状态，要么换方法。

**温度超出散斑与光学件的承受范围**：散斑起皮、窗口软化、镜头失焦，数据不可用。

**变形量超出景深与视场**：翘曲太大导致部分区域离焦或移出视场，匹配断掉。这时要扩大视场、牺牲空间分辨率，或者分段测量。

**腔内强对流**：热气流引起的折射率波动会持续抬升噪声，即使平均也难以完全压制。等温平台采集是最实际的缓解办法。

**需要纳米级形貌**：DIC 的强项是全场位移与应变，不是纳米级面形。追求极致面形精度，干涉类方法更合适。

## 八、常见问题

**1. 单相机能不能测离面位移？**

可以，但有条件。单目方法通常依赖投影条纹、散焦深度或已知的刚体运动假设，精度和适用性与双目立体视觉不同。双目之所以成为热翘曲测量的主流，是因为它在不改变被测物表面光学性质的前提下直接给出三维坐标，且对大变形鲁棒。

**2. 亚像素精度是不是越高越好？**

未必。亚像素插值能到 0.01 像素量级，但实际精度受散斑质量、噪声、标定误差共同限制。把算法指标当成系统精度，是选型时最常见的误判。系统精度要用标准件实测验证，而不是读参数表。

**3. 为什么一定要扣刚体位移？**

因为晶圆在试验箱里不是绝对固定的。支架热膨胀、样品微滑移、相机热漂移都会产生整体位移，量级与真实翘曲相当。不扣除，测出来的就是“支架加样品”的合成运动，不是晶圆的变形。

**4. 视窗折射的影响有多大，能不能忽略？**

取决于窗口厚度、相机视角和视场大小。正入射、薄窗、小视场时可以近似忽略；大视场、斜视、厚窗时偏差会达到与待测量同量级。判断办法很简单：同样样品，开窗测一次、开箱测一次，差异就是折射的贡献。

**5. 全温域连续采集，图像存得下吗？**

按节点采集而不是连续录像，是常规做法。16 个温度节点、每个节点若干帧，数据量完全可控。真正需要连续高速采集的是跌落、冲击这类瞬态过程，热翘曲的时间尺度是分钟级，不需要高帧率。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>English Version (Click to Expand)</b></summary>

> **Abstract:** Thermal warp measurement on wafers is hard because three assumptions fail at the same time: the object is heating, the object sits behind a window, and the object drifts as a whole. Getting sub-micron out-of-plane data under those conditions is not a matter of one clever trick but of three technical threads, each solving one segment. Stereo geometry turns "out-of-plane" into a solvable quantity; sub-pixel speckle matching pushes that quantity down to sub-micron resolution; error-suppression algorithms remove window refraction, rigid-body drift and temperature misalignment one by one. This article follows the geometry–matching–error sequence and then traces the conversion path from displacement field to warp value and to CTE.

> **Keywords:** 3D DIC; out-of-plane displacement; stereo vision; sub-pixel matching; refraction calibration; rigid-body removal; CTE

## Contents

- [1. Three Assumptions Fail at Once](#1-three-assumptions-fail-at-once)
- [2. Thread One: Stereo Geometry](#2-thread-one-stereo-geometry)
- [3. Thread Two: Sub-Pixel Matching](#3-thread-two-sub-pixel-matching)
- [4. Thread Three: Suppressing Three Kinds of Interference](#4-thread-three-suppressing-three-kinds-of-interference)
- [5. From Displacement Field to Warp: The Reference Plane](#5-from-displacement-field-to-warp-the-reference-plane)
- [6. From Displacement Field to CTE](#6-from-displacement-field-to-cte)
- [7. Where the Method Breaks Down](#7-where-the-method-breaks-down)
- [8. FAQ](#8-faq)

## 1. Three Assumptions Fail at Once

Conventional topography measurement assumes a stationary object, a stable environment and an unobstructed line of sight. A wafer thermal warp test breaks all three.

During a ramp the wafer keeps moving; only on a hold plateau is it approximately still. The chamber has a viewing window, so the cameras look through glass. Heating drives air currents, and uneven air density makes the image shimmer. Add a low-contrast mirror-like silicon surface, and direct imaging amounts to photographing a whiteboard.

| Disturbance | Order of magnitude | Consequence |
| --- | --- | --- |
| Window refraction | Depends on incidence angle and glass thickness | Global scaling and distortion of the displacement field |
| Hot air | Fluctuates in time | Image shimmer, higher matching noise |
| Rigid-body drift | Depends on fixture and thermal expansion | Real deformation masked by bulk translation |
| Low surface contrast | — | Correlation matching has nothing to lock onto |

## 2. Thread One: Stereo Geometry

A single camera viewing a plane yields two in-plane coordinates; the out-of-plane dimension is lost.

Stereo vision is triangulation: two cameras observe the same point from different angles, and the two lines of sight intersect at the point's 3D coordinate. The intersection presupposes that the relative position and orientation of the cameras are known, which is what calibration provides.

| Step | What it solves | Symptom when wrong |
| --- | --- | --- |
| Intrinsic calibration | Imaging model of each camera | Uniform scaling error across the field |
| Extrinsic calibration | Relative pose of the two cameras | Systematic tilt in depth |
| Distortion correction | Lens nonlinearity | Curvature distortion near the edges |
| Reference plane definition | Zero datum | Constant offset in warp values |

In wafer testing, calibration must be performed under the actual imaging conditions. Calibrating through the window and with the window removed give different results, and a cold calibration used hot differs in the optical path.

Once 3D coordinates exist, out-of-plane displacement is the difference in 3D position of the same material point before and after deformation, projected onto the reference-surface normal.

## 3. Thread Two: Sub-Pixel Matching

Sensor pixels are finite: a 150 mm wafer spanning 2000 pixels puts 75 μm on one pixel, so integer matching would quantise the curve into 75 μm steps.

Sub-pixel methods work on a simple observation: integer matching finds a coarse peak, but the true extremum lies between adjacent pixels. Fitting the correlation surface near the peak (paraboloid or Gaussian) interpolates that position to 0.01 pixel or finer. At the same 75 μm/pixel imaging scale, displacement resolution then lands in the sub-micron range.

| Element | Role | Contribution to final accuracy |
| --- | --- | --- |
| Speckle/texture quality | Provides matchable random features | Determines whether matching is reliable at all |
| Subset size | Matching window | Large subsets resist noise, lower spatial resolution |
| Sub-pixel interpolation | Breaks the integer quantisation | Brings the step down to sub-micron |
| Stereo matching | Pixel correspondence across cameras | Determines depth (out-of-plane) accuracy |

A mirror-like silicon surface has no natural texture: the image is uniform, the correlation surface flat, and matching "converges" anywhere — producing random noise. Either a speckle pattern is applied or existing micro-structure (circuit features, coating grains) is used as natural texture.

At elevated temperature the pattern has an extra requirement: through the whole 150℃ run it must not peel, flow, or slide relative to the substrate. Once it slips at some temperature, every subsequent displacement field is offset.

## 4. Thread Three: Suppressing Three Kinds of Interference

**Rigid-body motion.** The wafer rests on a fixture; the fixture expands, the sample may slip, and the camera mount expands too. On a 150 mm wafer, a 50 μm bulk translation inflates "warp" by 50 μm.

The remedy is rigid-body removal: choose reference points assumed fixed (or fit the shape), solve the six degrees of freedom, and subtract them. Everything hinges on that judgement — pick the wrong reference and you subtract real deformation.

**Window refraction.** The camera looks through glass into hot air, crossing two interfaces. A flat plate at normal incidence has little effect, but near the field edge the oblique view lengthens the optical path and shifts the image, adding a position-dependent distortion.

The remedy is refraction calibration: incorporate window thickness, refractive index and viewing angle into a model, trace the ray path backwards, and correct image positions into real space.

**Temperature–image misalignment.** The sample temperature lags the chamber air and the thermocouple reading; if acquisition and logging are not synchronised, the true temperature of a frame is uncertain — a coefficient error in CTE inversion.

The remedy is temperature–image synchronisation: drive both from one trigger source, or anchor frames to temperature plates (hold segments) so frame index and temperature node bind one-to-one.

| Disturbance | Nature | Signature | Countermeasure |
| --- | --- | --- | --- |
| Rigid-body motion | Global translation/rotation | Field offset as a whole | Solve and subtract six DOF using reference points |
| Window refraction | Position-dependent bias | Centre fine, edges distorted | Backward ray tracing with refraction model |
| Temperature mismatch | Time-axis offset | CTE offset across the board | Common trigger or plate anchoring |
| Hot air | Random noise | High-frequency jitter, large residuals | Wait for thermal equilibrium, average frames |

## 5. From Displacement Field to Warp: The Reference Plane

Three conventions dominate: least-squares plane fit, three-point plane, and initial state as zero. They can differ substantially, especially for asymmetric shapes.

| Reference choice | Computation | Trade-off |
| --- | --- | --- |
| Least-squares plane fit | Minimises residual sum of squares | General purpose, insensitive to local collapse |
| Three-point plane | Plane through three support points | Matches actual support conditions, sensitive to point choice |
| Initial state zero | First frame as datum | Good for evolution, hides initial shape |
| Sphere fit | Removes global spherical bow | Separates overall arch from local undulation |

In practice the sturdier approach is to report two sets: one referenced to the initial state (evolution with temperature) and one referenced to a fitted plane (absolute topography).

## 6. From Displacement Field to CTE

Inverting the thermal expansion coefficient means extracting strain per unit temperature rise: difference two temperature nodes for relative displacement, take the spatial gradient for strain, divide by the temperature difference for equivalent CTE.

**Trap one: treating rigid-body motion as thermal expansion.** If residual rigid-body motion survives, the differenced "expansion" contains bulk translation and the CTE comes out too large.

**Trap two: substituting a local point for the full field.** A 0.5 μm matching error over a 10 mm baseline is a 50 με strain error; a full-field least-squares fit over tens of thousands of points suppresses random error.

**Trap three: ignoring non-uniformity.** Real wafers do not expand uniformly; local constraints, interfaces and structural differences mean a field average hides the local mismatch.

| Inversion step | Input | Output | Main risk |
| --- | --- | --- | --- |
| Field differencing | Two temperature nodes | Relative displacement field | Residual rigid-body motion |
| Spatial gradient | Relative displacement field | Strain field | Noise amplification |
| Division by ΔT | Strain field and temperature | Equivalent CTE field | Temperature misalignment |
| Zonal statistics | CTE field | Centre/edge/quadrant values | Poor zoning hides gradients |

## 7. Where the Method Breaks Down

**Fully mirror-like surfaces with no feasible patterning.** No texture, unreliable matching. Either change the surface state or change the method.

**Temperature beyond what speckle and optics tolerate.** Pattern peeling, window softening, lens defocus — data unusable.

**Deformation exceeding depth of field and field of view.** Large warp defocuses or pushes regions out of frame, breaking matching. Widen the field and sacrifice resolution, or measure in segments.

**Strong convection inside the chamber.** Refractive-index fluctuations raise the noise floor, and averaging cannot fully suppress them; acquiring on hold plateaus is the practical mitigation.

**Nanometre-level topography requirements.** DIC's strength is full-field displacement and strain, not nanometre surface form; interferometric methods suit the latter better.

## 8. FAQ

**1. Can a single camera measure out-of-plane displacement?**

Yes, with conditions. Monocular approaches rely on projected fringes, defocus depth or known rigid-body assumptions, with different accuracy and applicability than stereo. Stereo dominates thermal warp work because it delivers 3D coordinates without altering the specimen's optical properties.

**2. Is higher sub-pixel precision always better?**

Not necessarily. Interpolation can reach 0.01 pixel, but real accuracy is limited jointly by speckle quality, noise and calibration error. Treating an algorithm figure as system accuracy is the most common selection error; verify against a reference artefact instead.

**3. Why must rigid-body motion be removed?**

Because the wafer is not absolutely fixed inside the chamber. Fixture expansion, slight sample slip and camera thermal drift all produce bulk motion comparable to the real warp, so the result would be the combined motion of fixture and sample.

**4. How large is window refraction, and can it be ignored?**

It depends on window thickness, viewing angle and field size. At normal incidence, thin glass and a small field, it is negligible; with a large field, oblique views and thick glass, the bias reaches the same order as the quantity being measured.

**5. Can full-range continuous acquisition store that much imagery?**

Acquiring at nodes rather than recording continuously is standard practice: sixteen temperature nodes with a few frames each is a manageable dataset. Continuous high-speed capture is for drop and impact events; thermal warp evolves over minutes.

</details>
