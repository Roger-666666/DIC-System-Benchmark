# 晶圆为什么会“弯”：CTE失配如何把热应力变成翘曲

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 晶圆变弯不是材料“软了”，而是叠层材料的热膨胀系数（CTE）各不相同、层与层之间又被粘接牢牢约束，热机械应力找不到别的出口，只能以翘曲的形式释放。本文把这条链条拆成四段讲清楚：CTE差异从哪里来、约束怎么形成、应力为什么偏偏选择“弯”这条路、弯了之后在制造与可靠性上要付什么代价；顺带把翘曲、弯曲、共面度、离面位移这几个老被混用的词分开定义，并说明为什么这件事得用全场三维手段看，而不是量一个点的位移。

> **关键词：** 晶圆翘曲；热膨胀系数失配；热机械应力；离面位移；共面度；三维DIC

## 目录

- [一、先把几个词分开：弯曲、翘曲、共面度](#一先把几个词分开弯曲翘曲共面度)
- [二、CTE失配：一块晶圆上从来没有“同一种材料”](#二cte失配一块晶圆上从来没有同一种材料)
- [三、约束从哪来：粘接把自由伸缩变成受迫变形](#三约束从哪来粘接把自由伸缩变成受迫变形)
- [四、应力为什么偏偏选“弯”这条路](#四应力为什么偏偏选弯这条路)
- [五、弯的形态不止一种](#五弯的形态不止一种)
- [六、四重代价：从贴片偏移到焊点疲劳](#六四重代价从贴片偏移到焊点疲劳)
- [七、温度一到，问题为什么集中爆发](#七温度一到问题为什么集中爆发)
- [八、只看一个点的位移，为什么不够](#八只看一个点的位移为什么不够)
- [九、常见问题](#九常见问题)

## 一、先把几个词分开：弯曲、翘曲、共面度

现场有三句典型说法，几乎每次讨论都会碰上：这片刻“拱起来像薯片”，这片刻“边缘塌了”，这片刻“过炉就裂”。三句听着都在说“弯”，指向的却是三个不同的量。

“拱起来”说的是整体曲率，对应弯曲（bow）——中心相对参考面的偏离，一个带符号的单值。“边缘塌了”说的是峰谷跨度，对应翘曲（warp）——最高点与最低点之差。“过炉就裂”则往往发生在局部，既不是弯曲也不是翘曲，而是某一小片区域的陡峭起伏，平均值完全看不出来。

再往下一层，工程验收用的是共面度（coplanarity）：各点是否落在允许的平面带内。它不关心形貌长相，只关心有没有超出带宽。

| 说法 | 对应的量 | 为什么不能互相替代 |
| --- | --- | --- |
| 拱起来像薯片 | 弯曲 bow | 只反映中心偏离，说不清边缘 |
| 边缘塌了 | 翘曲 warp | 峰谷差能算，但不知塌在哪 |
| 过炉就裂 | 局部起伏 | 被平均值抹平，要靠场数据 |
| 来料合不合格 | 共面度 | 只给判定，不给形貌 |

一句话：弯曲和翘曲是标量，共面度是判定，而局部起伏只有场数据看得见——这也是后面要引入三维全场测量的原因。指标怎么分层、报告怎么写，是另一个话题；这篇要回答的是更靠前的那个问题：**它为什么会弯。**

## 二、CTE失配：一块晶圆上从来没有“同一种材料”

单晶硅的热膨胀系数很低，常被引用在 2.6 ~ 3.0 ppm/℃ 这个量级。如果晶圆真的只是一片纯硅，热胀冷缩几乎可以忽略。

问题在于，真正进入工艺和封装环节的晶圆，早就不是一片纯硅了。硅衬底上面叠着介质薄膜、金属互连层，封装阶段还要加上基板、塑封料、焊料。这些材料的热膨胀系数差着一个数量级。

| 材料层 | 典型 CTE（ppm/℃） | 与硅的倍数关系 |
| --- | --- | --- |
| 硅芯片 / 衬底 | 2.6 ~ 3.0 | 1×（基准） |
| 铜互连 / 引线框架 | 16 ~ 17 | 约 6× |
| 基板 BT / ABF | 12 ~ 17 | 约 5 ~ 6× |
| 塑封料 EMC | 8 ~ 15 | 约 3 ~ 5× |
| 焊料 SAC305 | 21 ~ 25 | 约 8× |

这张表最值得盯的是倍数关系。温度升高 100℃，硅伸长约 0.3 μm/mm，焊料伸长约 2.3 μm/mm，同一段长度上两者差了近 2 μm/mm。晶圆这种直径 150 mm、厚度 1 mm 的薄片，差出来的量没有地方消化。

塑封料 CTE 8 ~ 15 ppm/℃ 是配方差异造成的宽区间，不是测量误差。

## 三、约束从哪来：粘接把自由伸缩变成受迫变形

如果各层只是叠在一起、彼此能滑动，温度变化时各伸各的，晶圆不会弯。真正制造麻烦的是“粘住”这件事。

薄膜沉积、键合、塑封，本质都是让两层材料在界面上形成牢固结合。结合一旦形成，界面两侧的位移就必须连续：上层想多伸一点，下层只肯伸一点点，于是上层被压、下层被拉，界面附近产生剪切与正应力。这就是热机械应力的来源。

| 结构因素 | 变化方向 | 对翘曲的影响 |
| --- | --- | --- |
| 层间 CTE 差 | 差越大 | 同温升下应力越大，翘曲越明显 |
| 膜层厚度 | 越厚 | 单层弯矩贡献增加，整体刚度也增加，方向取决于层位 |
| 界面结合强度 | 越强 | 位移连续性约束越硬，应力累积越快 |
| 衬底厚度 | 越薄 | 抗弯刚度按厚度三次方下降，同样应力下变形放大 |
| 温度区间 | 越宽 | 累积应变越大，进入塑性后出现残余变形 |

薄片抗弯刚度与厚度的三次方相关，厚度减半，刚度掉到八分之一。这就是为什么减薄工序之后，同一片晶圆的翘曲往往突然变得难看——应力没变，抵抗变形的能力没了。

## 四、应力为什么偏偏选“弯”这条路

应力释放有三条路：裂、滑、弯。

裂，是界面分层或膜层开裂，能量释放最彻底，代价也最大；滑，是位错运动与塑性变形，在高温下才活跃；弯，是整体几何形状改变，把面内应力转成离面位移。三条路里，弯的门槛最低。

从力学上看，这是典型的“薄膜应力驱动板弯曲”问题：面内失配应变在厚度方向积分后形成一个等效弯矩，薄板在弯矩作用下产生曲率。应力是“因”，弯矩是“中间量”，曲率是“果”，翘曲量是曲率在整个跨度上积分出来的结果。

## 五、弯的形态不止一种

实际测出来，晶圆的离面形貌很少是规整的球面。常见有四类。

**球面型**：中心拱起或凹陷，四周大致对称，多出现在膜层均匀、应力各向同性的情形。

**马鞍型**：一个方向拱起、垂直方向下凹，源于两个主方向应力不等。

**花瓣型**：沿周向出现数个起伏花瓣，常见于圆形边界约束、局部开口或沉积均匀性不足的情况。

**局部塌陷**：整体还算平，某一区域突然下陷或凸起。这类最危险，因为平均值看不出来，但那一处的芯片恰恰是最容易裂的。

| 形貌类型 | 主要成因 | 风险特征 |
| --- | --- | --- |
| 球面型 | 膜层均匀、应力各向同性 | 整体共面度超差，贴片偏移 |
| 马鞍型 | 两主方向应力不等 | 某一条带上应力集中 |
| 花瓣型 | 周向约束不均、沉积不均 | 边缘局部超差 |
| 局部塌陷 | 局部结构差异、异物、空洞 | 单点裂纹、焊点开路 |

## 六、四重代价：从贴片偏移到焊点疲劳

翘曲不是外观问题，它会顺着链条往下传，每一环都有具体代价。

| 环节 | 具体表现 | 机理连接 |
| --- | --- | --- |
| 制造与封装 | 贴片偏移、枕头效应、桥接、虚焊开路 | 表面不平导致焊膏厚度不均、贴装压力分布不均 |
| 器件可靠性 | 芯片裂纹、界面分层、焊点疲劳 | 残余应力叠加循环载荷，界面成为薄弱面 |
| 设计约束 | 互连与散热路径被改变 | 形貌变化改变接触热阻与走线位置 |
| 测试验证 | 高温腔体内全场测量困难 | 窗口折射、热气流、装夹约束干扰测量 |

翘曲本身是残余应力的表征，残余应力叠加使用中的温度循环，会加速界面疲劳。焊点疲劳裂纹往往从应力最集中的角点起裂，而角点恰好是翘曲梯度最大的地方。

## 七、温度一到，问题为什么集中爆发

常温下测一片晶圆，常常是平的；过一遍工艺，问题全出来了。原因在于晶圆在整个生命周期里要经历多次温度往复，每一次都在累积。

| 阶段 | 典型温度区间 | 主要热机械事件 |
| --- | --- | --- |
| 薄膜沉积 | 数百摄氏度 | 沉积温度与室温的差值形成初始应力 |
| 回流焊接 | 峰值 240℃ 以上 | 焊料熔化约束消失，冷却后重新锁定形变 |
| 温度循环筛选 | 大幅度往复 | 循环塑性累积，翘曲幅值随循环漂移 |
| 服役工况 | 接近室温至中温 | 自热与外部热环境叠加 |

回流焊之所以关键，是因为它是一次“约束状态重置”。焊料熔化的瞬间，层间约束消失，各层自由伸缩；冷却凝固时，约束在高温状态下的尺寸上重新建立，室温下的形貌就被“锁定”在那个状态。

而且，形貌演化并不是单调的：温度上升，翘曲持续增大，到某个温度点之后不升反降。这不是测量出错，而是应力释放与材料软化在起作用。

## 八、只看一个点的位移，为什么不够

到这里，测量需求的轮廓已经清楚了：要全温域、要全场、要形貌。

传统手段里，位移传感器只能给单点或少量点位；光学轮廓类方法给的是某一温度下的静态形貌快照，连续升温过程需要停机切换。这两类都能回答“弯了多少”，回答不了“怎么弯的、哪里弯得最狠、什么时候开始转折”。

以三维 DIC 为例，它通过双目成像重建表面三维坐标，逐点算出离面位移，于是同一套数据里同时存在整体翘曲标量、局部塌陷位置、随温度变化的形貌序列。

| 需求 | 单点手段 | 静态形貌手段 | 全场三维手段 |
| --- | --- | --- | --- |
| 整体翘曲量 | 可（需多点推算） | 可 | 可 |
| 局部塌陷定位 | 难（漏检概率高） | 可 | 可 |
| 全温域连续演化 | 可（点位有限） | 需多次停机 | 可 |
| 应变场与 CTE 反演 | 不可 | 不可 | 可 |
| 仿真对标输入 | 弱 | 中 | 强 |

## 九、常见问题

**1. 晶圆越薄越容易弯吗？**

是，但原因不只是“薄了软”。抗弯刚度与厚度三次方相关，厚度减半刚度降到八分之一。

**2. 常温测出来是平的，为什么过炉就出问题？**

因为常温形貌是历史约束状态的结果，不代表全温域行为。回流焊会重置约束：熔化时各层自由伸缩，凝固时在高温尺寸上重新锁定。室温平、峰值温度翘得很厉害的组合并不少见，只测室温等于漏掉主要矛盾。

**3. 翘曲度和共面度是一回事吗？**

不是。翘曲是峰谷跨度，描述形貌起伏幅度；共面度是各点是否落在允许的平面带内，是验收判定。一片晶圆可以翘曲很大但共面度合格（整体缓慢拱起），也可以翘曲不大但共面度超差（局部塌陷）。前者影响贴装工艺，后者直接威胁单颗芯片。

**4. 单晶硅本身 CTE 很小，为什么还会弯？**

因为弯的不是纯硅。真正参与变形的是硅加介质层、金属层、基板、塑封料的叠层结构，其中金属与焊料的 CTE 是硅的六到八倍。失配来自层与层的差，不是来自硅本身的大小。

**5. 测翘曲为什么不直接用激光测距扫一遍？**

可以扫，但拿到的是离散点云，且扫描过程需要时间，升温过程中的动态演化难以连续捕捉；另外点云不含面内信息，做不了应变与 CTE 反演。如果目标只是来料抽检，扫描够用；如果目标是机理分析与仿真对标，需要全场同步的位移场与应变场。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>点击展开：English Version (Click to Expand)</b></summary>

> **Abstract:** A wafer does not bow because the material has gone soft. It bows because stacked layers have different coefficients of thermal expansion (CTE) and are bonded firmly enough that they cannot slide past one another. The thermomechanical stress has nowhere else to go, so it escapes as out-of-plane deformation. This article unpacks the chain in four links: where the CTE mismatch comes from, how the constraint forms, why the stress takes the bending route, and what the resulting bow costs in manufacturing and reliability. It also separates four terms that are routinely confused — bow, warp, coplanarity and out-of-plane displacement — and explains why the problem needs a full-field, three-dimensional view rather than a displacement reading at one point.

> **Keywords:** wafer warp; CTE mismatch; thermomechanical stress; out-of-plane displacement; coplanarity; 3D DIC

## Contents

- [1. Separating the Terms: Bow, Warp, Coplanarity](#1-separating-the-terms-bow-warp-coplanarity)
- [2. CTE Mismatch: A Wafer Is Never One Material](#2-cte-mismatch-a-wafer-is-never-one-material)
- [3. Where the Constraint Comes From](#3-where-the-constraint-comes-from)
- [4. Why the Stress Chooses Bending](#4-why-the-stress-chooses-bending)
- [5. Bending Has More Than One Shape](#5-bending-has-more-than-one-shape)
- [6. Four Costs: From Placement Offset to Solder Fatigue](#6-four-costs-from-placement-offset-to-solder-fatigue)
- [7. Why Problems Cluster Once Temperature Rises](#7-why-problems-cluster-once-temperature-rises)
- [8. Why a Single-Point Reading Falls Short](#8-why-a-single-point-reading-falls-short)
- [9. FAQ](#9-faq)

## 1. Separating the Terms: Bow, Warp, Coplanarity

**Bow** is the deviation of the wafer centre from a reference plane — a signed scalar. A 200 μm centre rise says nothing about whether the shape is a clean dome or a flat middle with flared edges.

**Warp** is the peak-to-valley spread of the free surface relative to a reference plane. It sits closer to the actual risk, because chip cracks and placement offsets usually start where the local undulation is largest.

**Coplanarity** is an acceptance-oriented metric: how well all surface points fall inside an allowed plane band. It does not care about shape, only whether the band is exceeded.

**Out-of-plane displacement** is the output language of full-field methods such as DIC: the normal movement of every point, a field rather than a number. Bow and warp can be computed from it; the reverse is not true.

| Metric | What it describes | Data form | Typical use |
| --- | --- | --- | --- |
| Bow | Centre offset from reference plane | Signed scalar | Quick read on overall arch direction |
| Warp | Peak-to-valley spread of the field | Scalar | Risk assessment of topography amplitude |
| Coplanarity | Whether points stay inside the band | Threshold verdict | Incoming inspection, process release |
| Out-of-plane field | Normal movement per point | 2D/3D field | Shape evolution, simulation correlation, CTE inversion |

## 2. CTE Mismatch: A Wafer Is Never One Material

Monocrystalline silicon has a low CTE, commonly quoted at 2.6–3.0 ppm/℃. A truly plain silicon sheet would barely expand at all.

The problem is that a wafer entering process and packaging is no longer plain silicon: a silicon substrate carries dielectric films and metal interconnect layers, and packaging adds substrate, mould compound and solder. The CTE of these layers differs by an order of magnitude.

| Layer | Typical CTE (ppm/℃) | Multiple of silicon |
| --- | --- | --- |
| Silicon die / substrate | 2.6–3.0 | 1× (baseline) |
| Copper interconnect / leadframe | 16–17 | ~6× |
| Substrate BT / ABF | 12–17 | ~5–6× |
| Mould compound EMC | 8–15 | ~3–5× |
| Solder SAC305 | 21–25 | ~8× |

What matters in that table is the ratios. Over a 100℃ rise, silicon expands about 0.3 μm/mm and solder about 2.3 μm/mm — nearly 2 μm per millimetre of difference, which a 150 mm disc one millimetre thick has nowhere to absorb.

The 8–15 ppm/℃ band for mould compound is formulation difference, not measurement spread. Substituting a midpoint into a thermal-matching calculation can bias the whole conclusion.

## 3. Where the Constraint Comes From

If the layers could slide, each would expand on its own and nothing would bend. The trouble comes from bonding.

Deposition, bonding and moulding all create a firm interface. Displacement must then be continuous across it: the upper layer wants to expand more, the lower expands less, so the upper layer ends in compression, the lower in tension, with shear and normal stress near the interface.

| Structural factor | Direction of change | Effect on warp |
| --- | --- | --- |
| Interlayer CTE difference | Larger difference | Higher stress at the same temperature rise |
| Film thickness | Thicker | Adds bending moment, also adds stiffness; net direction depends on layer position |
| Interface strength | Stronger | Harder displacement continuity, faster stress build-up |
| Substrate thickness | Thinner | Bending stiffness falls with the cube of thickness; same stress, larger deformation |
| Temperature range | Wider | Larger accumulated strain, residual deformation after yielding |

Bending stiffness scales with the cube of thickness, so halving thickness cuts stiffness to one-eighth — which is why warp often deteriorates sharply after a thinning step.

## 4. Why the Stress Chooses Bending

Stress has three escape routes: crack, slip, bend.

Cracking releases energy most completely and costs most; slip is dislocation motion and plastic deformation, active at elevated temperature; bending changes the geometry itself, converting in-plane stress into out-of-plane displacement. Of the three, bending has the lowest threshold.

Mechanically this is film-stress-driven plate bending: the in-plane mismatch strain, integrated through the thickness, produces an equivalent bending moment, and the plate responds with curvature. Stress is the cause, moment the intermediate, curvature the result, and warp is curvature integrated across the span.

## 5. Bending Has More Than One Shape

In practice the out-of-plane shape is rarely a clean dome. Four patterns recur.

**Spherical.** The centre arches up or down with roughly symmetric surroundings, typical of uniform films under isotropic stress.

**Saddle.** One direction arches while the perpendicular direction sags, from unequal principal stresses.

**Petal.** Several undulations appear around the circumference, traced to non-uniform edge constraint or deposition.

**Local collapse.** Broadly flat, but one region dips or bulges — the most dangerous type, because the average looks fine while that region is where dies crack first.

| Shape | Main cause | Risk signature |
| --- | --- | --- |
| Spherical | Uniform film, isotropic stress | Coplanarity out of tolerance, placement offset |
| Saddle | Unequal principal stresses | Stress concentration along one band |
| Petal | Non-uniform circumferential constraint | Local edge out-of-tolerance |
| Local collapse | Local structural difference, void, foreign matter | Single-die crack, open solder joint |

## 6. Four Costs: From Placement Offset to Solder Fatigue

Warp is not cosmetic; it propagates down the chain, with a concrete cost at each link.

| Stage | Manifestation | Mechanistic link |
| --- | --- | --- |
| Manufacturing and packaging | Placement offset, pillow effect, bridging, open joints | Surface unevenness causes uneven paste thickness and uneven placement pressure |
| Device reliability | Die crack, interfacial delamination, solder fatigue | Residual stress plus cyclic load, interface as the weak plane |
| Design constraints | Interconnect and thermal paths altered | Shape change alters contact resistance and routing position |
| Test and verification | Full-field measurement inside a hot chamber is difficult | Window refraction, hot air, fixture constraint |

Residual stress superimposed on service cycling accelerates interfacial fatigue, and solder fatigue cracks initiate at the corner where stress concentrates — exactly where the warp gradient is steepest.

## 7. Why Problems Cluster Once Temperature Rises

A wafer measured at room temperature is often flat; run it through a process and problems appear, because repeated temperature excursions accumulate over its life.

| Stage | Typical range | Main thermomechanical event |
| --- | --- | --- |
| Film deposition | Several hundred ℃ | Initial stress set by the gap between deposition and room temperature |
| Reflow | Peak above 240℃ | Solder melts, constraint vanishes, geometry re-locks on cooling |
| Thermal cycling screen | Large excursions | Cyclic plasticity accumulates, warp drifts with cycle count |
| Service | Near room to moderate | Self-heating plus external thermal environment |

Reflow matters because it resets the constraint state: at melting, interlayer constraint disappears and every layer expands freely; on solidification, constraint is rebuilt on the high-temperature dimensions, so the room-temperature shape is locked into that state.

The evolution is also not monotonic. Warp grows with temperature, then reverses beyond a certain point — stress relaxation and material softening, not measurement error.

## 8. Why a Single-Point Reading Falls Short

By now the measurement requirement is clear: full temperature range, full field, topography.

Displacement sensors give one point or a few, often needing contact or close mounting; optical profilometry gives a static snapshot at one temperature, and a ramp requires stopping and switching. Both answer "how much did it bend"; neither answers "how did it bend, where is it worst, when does it turn".

Take 3D DIC: stereo imaging reconstructs surface coordinates and out-of-plane displacement is computed point by point, so one dataset holds the global warp scalar, the location of local collapse and the shape sequence versus temperature.

| Requirement | Point sensor | Static profilometry | Full-field 3D |
| --- | --- | --- | --- |
| Global warp value | Yes, by inference from several points | Yes | Yes |
| Local collapse location | Difficult, high miss rate | Yes | Yes |
| Continuous evolution over temperature | Yes, limited points | Requires repeated stops | Yes |
| Strain field and CTE inversion | No | No | Yes |
| Input for simulation correlation | Weak | Moderate | Strong |

## 9. FAQ

**1. Are thinner wafers always more prone to bow?**

Yes, and not merely because they are softer. Bending stiffness scales with the cube of thickness, so halving thickness cuts stiffness to one-eighth.

**2. It measures flat at room temperature. Why does it fail after reflow?**

Because the room-temperature shape is the result of a past constraint state, not a predictor of full-range behaviour. Reflow resets the constraint: layers expand freely during melting, then re-lock on high-temperature dimensions during solidification.

**3. Are warp and coplanarity the same thing?**

No. Warp is the peak-to-valley spread, an amplitude descriptor. Coplanarity is whether points fall inside an allowed band, an acceptance verdict. A wafer can have large warp yet pass coplanarity, or modest warp yet fail on a local collapse.

**4. Silicon has a low CTE, so why does it bow at all?**

Because what bends is not pure silicon. The deforming structure is the stack of silicon plus dielectric, metal, substrate and mould compound, and the CTE of metals and solders is six to eight times that of silicon.

**5. Why not just scan the surface with a laser rangefinder?**

You can, but you get a discrete point cloud, and dynamic evolution during a ramp is hard to capture continuously. Point clouds also carry no in-plane information, so strain and CTE inversion are out of reach. For incoming inspection a scan is adequate; for mechanism analysis you need a synchronised full-field displacement and strain field.

</details>
