# 隧道变形监测的三个难点：拱顶沉降、拱腰剪切带与下穿扰动

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 隧道变形监测难在三点：拱顶沉降的最大值只是漏斗中心，拱腰的弧形应变带不等于已经开裂，下穿施工的扰动必须按工序拆开看。本文结合分层围岩相似模型的坍塌试验与盾构下穿的扰动试验，说明三类现象各自怎么读、容易错在哪、现场该查什么。

> **关键词：** XTDIC三维全场测量；数字图像相关技术；隧道变形监测；拱顶沉降；塑性剪切带；下穿扰动

## 目录

- [一、三个难点为什么总是一起出现](#一三个难点为什么总是一起出现)
- [二、拱顶沉降：最大量不等于关键判据](#二拱顶沉降最大量不等于关键判据)
- [三、拱腰的弧形带：应变集中不等于已经开裂](#三拱腰的弧形带应变集中不等于已经开裂)
- [四、下穿扰动：把工序拆开看](#四下穿扰动把工序拆开看)
- [五、共性检查清单](#五共性检查清单)
- [六、常见问题](#六常见问题)

## 一、三个难点为什么总是一起出现

隧道变形不是一次发生。开挖卸掉围岩的自重支撑，应力重新分配，变形跟着施工步序一段段放出来；支护装上后，围岩与支护又互相约束。这种“边挖边变”决定三件事同时成立：变形有明确的工序依赖、观测面长期被遮挡、破坏先兆以区域形式出现而不是落在某个点上。

洞内条件也不帮忙。支护、台车、管线、通风管在相机与洞壁之间来回穿，一个断面常常凑不出完整视场；低照度靠补光，补光稍不均匀散斑对比度就掉；粉尘水汽让图像忽明忽暗，匹配质量跟着波动。结果是空洞多、断点多。

点式手段依然有用：收敛计、水准、多点位移计给出的绝对量值与长期趋势，是判断整体稳定的底盘。但它给出的是一条曲线，而破坏往往从一个区域开始——拱顶上方的一段覆土、拱腰附近的一条带、下穿段地表的一侧。这些区域落在测点之间时，曲线一切正常，裂缝已经在别处长出来。

隧道场景需要的不是更密的点，而是能覆盖区域、能回到工序时间轴上的空间数据。下面三个难点是同一件事的三个切面。

## 二、拱顶沉降：最大量不等于关键判据

分层构筑的围岩相似材料模型，在围岩卸荷下模拟失稳坍塌，全域测量给出的第一层信息是沉降分布：拱顶覆土层沉降最大，随距拱顶距离增大而减小，形成完整的沉降漏斗。结论本身不新鲜，有价值的是漏斗形态。

最大值只是漏斗中心。同样一个最大沉降，漏斗可以窄而深，也可以宽而平，对支护的含义完全不同：窄而深说明变形集中在拱顶附近，拱腰以上是重点；宽而平说明影响范围已经铺开，边墙和地表都得跟着看。只看一个数，两者分不开。

梯度和对称性更值得追。横向梯度大，说明差异沉降明显，结构容易在梯度最大的位置受剪；漏斗偏在一侧，往往对应围岩强弱不均或施工偏差。这些在单点曲线上看不出来，在位移云图上却一目了然。

还有一条常被忽略：漏斗边界的迁移比峰值更早。卸荷初期，沉降集中在拱顶正上方；继续卸荷，等值线向外扩，边界先动、峰值后动。把边界位置随时间画成曲线，它常常先于最大沉降出现明显变化，是比峰值更灵敏的过程指标。

操作上，视场必须覆盖拱顶到两侧足够远，否则漏斗边界被画幅截断，看到的永远是“局部最深”的假象。参考区要在不受开挖影响处并写明；一旦落在沉降区内，位移都会被系统性削掉一部分。

## 三、拱腰的弧形带：应变集中不等于已经开裂

同一组试验的主应变云图上，拱腰会出现一条向外扩展的弧形带，公开描述称之为塑性剪切带。这个说法容易引出两种误读。

第一种是把它当裂缝。高应变带表示变形梯度大、材料变形不协调；裂缝表示材料已经断开。两者时间有先后、空间常重合，却不是一回事。直接叫裂缝会高估破坏程度；只认可见裂缝，又会漏掉带贯通前的阶段。

第二种是把它当几何上精确的线。带宽取决于材料、应力状态，也取决于计算参数：子区越大、步长越稀，带被抹得越宽越模糊；子区太小，噪声又把带切碎。所以带的位置比带宽可靠，带的走向比带内应变值可靠。

真正有用的是演化。带从拱腰起，向拱顶或边墙延伸；延伸过程中带内应变上升、带外反而可能下降，因为变形被集中进去了。只盯全场最大值，看到的是数字在涨；看带的长度与连通性，看到的是“正在贯通”。后者对支护决策更有意义：加强位置应当对着正在形成的带，而不是对着当前最大值。

两个陷阱值得点名。一是补光不均造成的假带：光斑边缘对比度下降会让匹配失准，形成方向随机的条带，回原图一看就露馅。二是遮挡造成的空洞被插值填平：插出来的连续区看着很像贯通的带，其实是算出来的，不是测出来的。空洞应当保留并标注。

## 四、下穿扰动：把工序拆开看

盾构下穿既有构筑物的相似模型试验，完整模拟掘进与后退两段工序，全域测量给出两条核心结论：地表沉降极值集中在隧道正上方；时序曲线能把掘进阶段的沉降增长与后退阶段的小幅回弹区分开。

这两条结论怎么用，比结论本身更重要。

第一条解决扰动范围从哪里算。既然极值集中在轴线正上方，横向剖面上的衰减形态就是判断影响宽度的依据。沉降衰减到某个比例的位置，可作为扰动边界的粗略标识；比例取多少要按上方构筑物容许变形定，套通用数字没有意义。

第二条解决回弹怎么解释。后退阶段出现小幅回弹，最容易被写成“应力恢复、变形回退”，这超出了测量能支撑的范围。表面回弹是观测现象，可能来自卸载后的弹性恢复，也可能来自支护刚度重分配、土层再压密，甚至来自参考状态的选取。要区分这些机制，得结合支护受力、土压力、孔隙水压力，单靠位移场推不出来。

拆工序意味着时间轴必须可靠。掘进、暂停、后退在图像序列里的分界不能靠文件时间戳猜。帧与工序事件之间要有硬件同步或可核对的事件标记，否则曲线上的“回弹”可能只是阶段对齐错了位置。

## 五、共性检查清单

三个难点看着不同，落到操作上有共同的检查项。下表可以直接对着现场流程走一遍。

| 检查项 | 判据 | 异常表现 | 处理动作 |
| --- | --- | --- | --- |
| 视场覆盖 | 漏斗与剪切带完整落在视场内 | 等值线在边缘被切断，出现假的最深点 | 扩大视场或分区布设，重叠区做一致性检查 |
| 参考区选取 | 位于不受开挖影响处并有记录 | 整体位移被系统性削减 | 重选参考区、重新解算，不沿用旧结果 |
| 空洞与遮挡 | 空洞位置明确标注，未插值填充 | 出现无源头的连续带 | 回原图核查，保留空缺 |
| 时序对齐 | 帧与掘进、暂停、后退一一对应 | 曲线拐点整体平移 | 补硬件同步或事件标记，重新对齐 |
| 色标与量纲 | 同一工序序列内色标统一 | 相邻阶段颜色相近但量值差数倍 | 固定色标范围并在图中标注 |
| 应变参数 | 子区与步长适配关注尺度 | 剪切带被抹宽或被噪声切碎 | 按带的最小可分辨宽度反推参数 |

清单里没有一条需要昂贵设备，但每条都能让结论变得不可用。隧道监测的失败多数不是测不出，而是测出却没法解释。

三个难点拆完，会发现共同前提是同一个：空间数据必须和工序时间轴绑在一起才谈得上判读。要把这套东西搬到现场连续用，还要解决采样节奏问题——振动台、冲击与长期观测对采集的要求几乎没有交集，那属于方案选型的范围。

## 六、常见问题

**1. 拱顶沉降最大值能直接作为控制指标吗？**

可以作为参考，但不宜单独使用。最大值只反映漏斗中心，漏斗的宽度、梯度、对称性和边界迁移同样重要，后者往往先于峰值发生变化。

**2. 应变云图上的弧形带就是裂缝吗？**

不是。弧形带表示变形局部化，说明该区域应变梯度大；裂缝表示材料已经断开。两者在时间上有先后，空间上常重合，判读时不能等同。

**3. 剪切带的宽度能作为定量指标吗？**

要谨慎。带宽受材料、应力状态和计算参数共同影响，子区与步长变化会明显改变带的宽度。带的位置、走向和连通性比宽度更稳定。

**4. 后退阶段的位移回弹说明围岩稳定了吗？**

不能这样推断。回弹是表面观测现象，其机制可能是弹性恢复、支护刚度重分配或土层再压密，需要结合支护受力和土压力等信息判断。

**5. 洞内光照差，补光能不能随便加？**

不能。补光不均会在应变场上生成方向随机的假带，光斑边缘尤其明显。补光应尽量均匀覆盖视场，并在采集前用原始图像检查对比度是否一致。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Three Difficulties in Tunnel Deformation Monitoring: Crown Settlement, Haunch Shear Bands, and Undercrossing Disturbance

> **Abstract:** Tunnel monitoring runs into three recurring difficulties. The maximum crown settlement marks only the center of a settlement trough; an arc-shaped strain band at the haunch is not a crack; and disturbance from an undercrossing must be separated by construction stage. Drawing on a layered similitude model of tunnel collapse and a shield-undercrossing model, this article explains how each phenomenon should be read, where misreadings typically arise, and what to check on site.

> **Keywords:** XTDIC full-field 3D measurement; digital image correlation; tunnel deformation monitoring; crown settlement; plastic shear band; undercrossing disturbance

## Contents

- [1. Why the three difficulties appear together](#1-why-the-three-difficulties-appear-together)
- [2. Crown settlement: the maximum is not the governing criterion](#2-crown-settlement-the-maximum-is-not-the-governing-criterion)
- [3. The haunch band: strain concentration is not a crack](#3-the-haunch-band-strain-concentration-is-not-a-crack)
- [4. Undercrossing disturbance: separate the construction stages](#4-undercrossing-disturbance-separate-the-construction-stages)
- [5. A shared inspection checklist](#5-a-shared-inspection-checklist)
- [6. FAQ](#6-faq)

## 1. Why the three difficulties appear together

Tunnel deformation is not a single event. Excavation removes part of the ground's self-support, stresses redistribute, and deformation is released stage by stage along the construction sequence. Once support is installed, ground and support begin to constrain each other. This "deform while excavating" process makes three conditions hold at once: deformation depends on construction stage, the observed surface is persistently obstructed, and failure precursors appear as regions rather than at single points.

The underground environment does not help. Support members, trolleys, pipes, and ventilation ducts pass between the camera and the tunnel wall, so a complete field of view at one section is often hard to assemble. Low illumination requires artificial light, and slightly uneven lighting reduces speckle contrast. Dust and moisture make images flicker, and matching quality fluctuates with them. The practical consequence is more data gaps and more breaks in the time series.

Point-based instruments remain useful underground. Convergence tapes, levelling, and multipoint extensometers provide absolute values and long-term trends that anchor the overall assessment. What they cannot provide is spatial extent, while tunnel failure frequently begins in a region: a stretch of overburden above the crown, a band near the haunch, one side of the ground surface above an undercrossing. When that region falls between measurement points, the curves look normal while a crack opens somewhere else.

What the tunnel case needs is therefore not denser points but spatial data that can be returned to the construction timeline. The three difficulties below are three faces of that same requirement.

## 2. Crown settlement: the maximum is not the governing criterion

In a layered similitude model of tunnel ground, unloading simulated the complete process from instability to collapse. Full-field measurement first delivers a settlement distribution: the overburden above the crown settles most, decreasing with distance from the crown and forming a complete settlement trough. The statement itself is not new; measurements and numerical models both produce it. What carries information is the morphology of the trough.

The maximum is only the center. For the same maximum settlement, a trough can be narrow and deep or wide and shallow, and the two mean different things for support. A narrow, deep trough concentrates deformation near the crown, making the zone above the haunch the focus; a wide, shallow trough indicates that the affected area has already expanded, so side walls and the surface must be included. A single number cannot separate the two.

Gradient and symmetry deserve more attention. A steep lateral gradient implies differential settlement, and a structure is likely to be sheared where the gradient peaks. A trough offset to one side usually corresponds to uneven ground or construction deviation. Neither is visible in a point curve, while both are obvious in a displacement map.

One further point is often missed: the trough boundary migrates earlier than the peak. Early in unloading, settlement concentrates directly above the crown; as unloading continues, contours expand outward. The boundary moves first and the peak follows. Plotted against time, the boundary position often changes noticeably before the maximum settlement does, which makes it a more sensitive process indicator.

Operationally, the field of view must extend far enough on both sides of the crown. Otherwise the trough boundary is cut off by the frame, and what remains always looks like a localized maximum. The reference region must sit outside the influenced zone, and its location should be stated in the report; if the reference falls inside the settling area, part of every displacement is systematically removed.

## 3. The haunch band: strain concentration is not a crack

In the same test series, the maximum principal strain map shows an arc-shaped band at the haunch, extending outward. The public description calls it a plastic shear band. The term invites two misreadings.

The first is to treat it as a crack. A high-strain band in a contour map indicates a large deformation gradient, where the material deforms incompatibly. A crack means the material has separated. The two are ordered in time and often coincide in space, but they are not the same. Calling the arc a crack overstates the damage; recognizing only visible cracks misses everything that happens before the band connects.

The second is to treat it as a geometrically precise line. Band width depends on the material and stress state, and also on processing parameters: larger subsets and wider spacing smear the band; very small subsets fragment it with noise. Band position is more reliable than band width, and band orientation is more reliable than the absolute strain value inside it.

The genuinely useful information is evolution. The band starts at the haunch and extends toward the crown or the side wall. As it extends, strain inside rises while strain outside may fall, because deformation concentrates into the band. Watching only the global maximum shows numbers increasing; watching band length and connectivity shows the band connecting. The latter matters more for support decisions: reinforcement should target the forming band, not the current maximum.

Two technical traps are worth naming. Uneven lighting creates false bands: reduced contrast at a light spot's edge degrades matching and produces a strip with arbitrary orientation, which disappears once the raw images are checked. Occlusion creates gaps that interpolation can close: the interpolated continuous region looks like a connected band but is computed rather than measured. Gaps should be retained and labelled, not filled into a continuous field.

## 4. Undercrossing disturbance: separate the construction stages

A similitude model of a shield tunnel passing beneath an existing structure reproduced the complete excavation and retreat sequence. Full-field measurement produced two central observations: surface settlement peaks directly above the tunnel axis, and the time series separates settlement growth during excavation from a small rebound during retreat.

How these observations are used matters more than the observations themselves.

The first answers where the disturbance zone begins. Since the peak lies directly above the axis, the attenuation profile across the section becomes the basis for judging affected width. The position where settlement decays to a chosen fraction can serve as a rough disturbance boundary. What fraction to use depends on the allowable deformation of the structure above; a universal number does not exist.

The second answers how the rebound should be explained. A small rebound during retreat is easily written up as stress recovery and deformation reversal, which claims more than the measurement supports. Surface rebound is an observed phenomenon. It may come from elastic recovery after unloading, from redistribution of support stiffness, from recompaction of soil, or even from the choice of reference state. Separating these mechanisms requires support loads, earth pressure, or pore pressure; a displacement field alone cannot do it.

Separating stages also requires a reliable time axis. The boundaries between excavation, pause, and retreat must not be inferred from file timestamps. Image frames and construction events need hardware synchronization or at least verifiable event marks; otherwise an apparent rebound may simply be a stage that was aligned incorrectly.

## 5. A shared inspection checklist

The three difficulties differ in appearance but share operational checks. The table can be walked through against a field procedure.

| Check | Criterion | Symptom of failure | Action |
| --- | --- | --- | --- |
| Field coverage | Trough and shear band fall entirely inside the frame | Contours cut at the edge; a false local maximum | Enlarge the field or use zoned layout with overlap checks |
| Reference region | Outside the influenced zone, location documented | All displacements systematically reduced | Reselect and re-process; do not reuse old results |
| Gaps and occlusion | Gap positions labelled, not interpolated | A continuous band with no visible source | Return to raw images; keep the gap |
| Time alignment | Frames map one-to-one to excavation stages | Curve breakpoints shifted as a whole | Add hardware sync or event marks; re-align |
| Colour scale | Fixed within one construction sequence | Adjacent stages look similar but differ several-fold | Fix the scale and annotate it |
| Strain parameters | Subset and spacing fit the scale of interest | Band smeared or fragmented by noise | Derive parameters from the narrowest resolvable band |

None of these checks requires expensive equipment, yet any one of them can render a conclusion unusable. Tunnel monitoring failures are rarely failures of measurement; they are failures of interpretation.

Having taken the three difficulties apart, a common precondition emerges: spatial data must be tied to the construction timeline before it can be interpreted. Moving that capability into continuous field use raises a separate question of sampling rhythm, since shaking tables, impacts, and long-term observation have almost nothing in common in their acquisition requirements.

## 6. FAQ

**1. Can maximum crown settlement be used as a stand-alone control index?**

As a reference, yes; alone, no. The maximum reflects only the trough center. Width, gradient, symmetry, and boundary migration matter as much, and the latter often change before the peak does.

**2. Is the arc-shaped band in a strain map a crack?**

No. The band indicates strain localization and a large deformation gradient; a crack means the material has separated. They are ordered in time and often overlap in space, but they must not be equated.

**3. Can band width be used as a quantitative indicator?**

With caution. Width depends on material, stress state, and processing parameters, and changes markedly with subset size and spacing. Position, orientation, and connectivity are more stable.

**4. Does rebound during retreat mean the ground has stabilized?**

That cannot be inferred. Rebound is a surface observation whose mechanism may be elastic recovery, redistribution of support stiffness, or soil recompaction, and it requires support load and earth pressure data to interpret.

**5. Can lighting be added freely in a dark tunnel?**

No. Uneven lighting produces false bands with arbitrary orientation, especially at the edge of a light spot. Illumination should cover the field evenly, and contrast should be checked on raw images before acquisition.

</details>
