# 桥隧边坡为什么要做全域变形监测：XTDIC三维全场测量的能力与边界

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 桥梁、隧道、边坡的变形很少是均匀的。位移计和应变片能给出高信噪比的点位时程，但点位之间的应力集中、塑性发展和裂纹萌生常落在测点之外。本文把"全域变形监测"拆成位移场、应变场、裂纹扩展时序三件事，说明它们各自回答什么问题，梳理影像类方法与点位手段、绝对坐标手段的分工，并列出三类工况下的能力范围与五条边界。

> **关键词：** XTDIC三维全场测量；数字图像相关技术；全域变形监测；位移场；应变场；裂纹扩展

## 目录

- [一、从几个点到一整片：需求是怎么变的](#一从几个点到一整片需求是怎么变的)
- [二、全域测量到底在测什么：两个场加一条时间线](#二全域测量到底在测什么两个场加一条时间线)
- [三、和位移计、应变片、全站仪怎么分工](#三和位移计应变片全站仪怎么分工)
- [四、三类工况与五条边界](#四三类工况与五条边界)
- [五、常见问题](#五常见问题)

## 一、从几个点到一整片：需求是怎么变的

桥梁主梁在分级加载下，跨中下挠、四分点腹板剪切、支座附近局部承压，本来就不是同一件事；隧道开挖后，拱顶下沉和边墙收敛的发展节奏也不完全同步；边坡在降雨入渗之后，表层土体的应变局部化往往先出现在坡脚或软弱夹层附近，而测点可能正好架在两侧。这些情形的共同点是：破坏的起点是一个区域，而传统布点给出的只是若干条曲线。

于是工程提问的方式跟着变了。过去常问"最大沉降多少、最大应变多少"，现在更多问"应力集中区在哪、塑性区怎么发展、裂纹从哪起、朝哪个方向扩"。后一类问题用离散点很难回答。加密测点能提高覆盖，但每个点仍只代表周围很小一块，点位之间的空白依旧是空白，而裂缝恰恰长在空白里。

这就是全域变形监测要解决的需求：它要做的不是把点测得更准，而是把点与点之间的那部分补上。

## 二、全域测量到底在测什么：两个场加一条时间线

"全域"这个词容易被当成一个笼统的形容词。实际上它至少包含三样输出，各自回答不同的问题，混在一起讲就会得出错误结论。

位移场回答"往哪走、走了多少"。三维数字图像相关技术用工业相机追踪被测表面的散斑灰度变化，通过左右相机的视差与前后帧的匹配求解三维坐标，得到覆盖整个视场的位移分布。给出的是空间连续的矢量场，可画成云图，也可沿任意路径切剖面。

应变场回答"哪里被拉得最狠"。应变由位移场空间求导得到，包括正应变、剪应变与主应变。这里有个容易被忽略的关系：位移场看上去很平滑，应变场仍可能在局部出现尖峰，因为求导会放大小尺度上的差异。所以应变的可信度直接依赖空间分辨率——视场铺得越大，单个计算子区覆盖的物理尺寸越大，能分辨的应变梯度就越粗。

裂纹扩展时序回答"什么时候开始、往哪扩"。它把裂纹位置、长度与时间轴绑在一起，用来看萌生与荷载级别、温度骤变或某个施工步序的对应关系。

三者的关系是：位移场是基础数据，应变场是对它的空间解析，裂纹时序是对它的时间解析。位移大并不等于应变大。刚体平移可以让位移云图看起来层次丰富，应变却接近零；反过来，一条很窄的剪切带内部应变可以很高，而整体位移并不突出。把它们当成同一件事，最常见的错误就是拿位移云图的颜色深浅去论证"这里应力最大"。

## 三、和位移计、应变片、全站仪怎么分工

讲全域测量，不等于说点位手段过时了。几类方法各自擅长的事情不一样，工程上更常见的做法是组合使用。

位移计和应变片的优势在信噪比和时程。单点位移计对微小变化的响应稳定，采样率高，长期零漂相对可控，适合做控制性断面的连续记录；应变片直接贴在构件表面，对局部应变的敏感度高，适合已知关注位置的定点观测。它们的短板是覆盖：一个断面布十几个点已经算密，而这十几个点之间的区域仍然没有观测。

全站仪和 GNSS 的优势在绝对坐标与长期基准：给出测点在全局坐标系下的位置，适合建立基准、观察整体趋势、做跨期比较。短板是空间密度低、采样率有限，对局部微小变形不敏感。

影像类方法的优势在空间连续分布。一次采集就能得到成千上万个测点的位移，可以直观看到应力集中区的形状、塑性区的发展方向、裂纹两侧的位移跳变。短板是它只测表面，而且对表面纹理质量、光照和振动比较敏感。

这几种方法不是替代关系。合理组合是：全站仪或 GNSS 建绝对基准，位移计与应变片在控制断面提供高信噪比时程，影像方法补齐空间分布、圈出异常区域，再反过来加密点位。点位手段的"准"和影像手段的"全"各在其位。

| 手段 | 主要输出 | 擅长的事 | 局限 |
| --- | --- | --- | --- |
| 位移计 | 单点位移时程 | 控制断面连续记录，采样率高 | 覆盖范围小，测点之间无观测 |
| 应变片 | 单点应变时程 | 已知位置的局部应变变化 | 需贴附，布点数量有限 |
| 全站仪 / GNSS | 绝对坐标 | 建立全局基准，跨期比较 | 空间密度低，对微小变形不敏感 |
| 影像类方法 | 位移场、应变场、裂纹特征 | 空间连续分布，定位异常区域 | 只测表面，依赖纹理与环境稳定性 |

## 四、三类工况与五条边界

### 4.1 三类工况

这套系统的采集能力覆盖三类工况。静态与准静态最常见，如缩尺模型的分级静力加载、构件长期蠕变观测，采集节奏可按荷载级或小时间隔安排。高速动态冲击是另一类，要高帧率采集与硬件同步，用来观察冲击瞬间的变形传播与局部失效。长周期持续观测是第三类，测的是几周到几个月尺度上的缓慢变化，难点不在单帧质量，而在基准稳定性和环境波动的抑制。

三类工况要求不同：静态更在意标定精度与视场覆盖，动态更在意帧率与触发同步，长周期更在意抗干扰与标定复核。

### 4.2 五条边界

第一，只测可观测表面。系统只给出相机可见面的位移与应变，构件内部、被遮挡面、埋入部分都不在其内。由表面应变反推内部应力需本构假设与边界条件，那属于分析。

第二，散斑或天然纹理的质量决定可用性。表面没有可追踪特征，匹配就无从谈起。人造散斑的颗粒大小、密度、对比度要与视场和子区尺寸匹配；混凝土骨料、岩石矿物颗粒这类天然纹理能否直接用，得先试采集再判断。

第三，视场越大，空间分辨率越低。相机分辨率固定，视场扩大则每个像素代表的物理尺寸变大，可分辨的最小应变梯度变粗。长大构件宜分区布置多对相机，用重叠区做跨区一致性检查，而不是把镜头拉远。

第四，风振、光照变化、温度漂移需要抑制。户外观测中，相机支架的微小晃动会被解算成结构变形；日照引起的亮度变化会降低匹配质量；温度变化让支架和构件产生不同的热膨胀。这些无法靠算法消除，得在硬件和流程两头处理：支架与加载装置独立、加遮光与补光、长过程里安排静态段复核。

第五，0.01 mm 这个量级对应适宜条件下的位移分辨能力，不是与场景无关的常数。视场从几米拉到几十米，单像素覆盖的实际尺寸变大，同一套硬件能分出的最小位移跟着变大；纹理、光照、标定质量再叠加，远距离大视场的分辨水平自然与室内短视场不在同一档。

知道边界之后，下一步该问：这些能力由哪些算法撑着。标定怎么建基准，亚像素怎么抠位移，抗干扰怎么压噪声，时序同步怎么把曲线和荷载对上——这些才决定数据能不能用。

## 五、常见问题

**1. 有了全域云图，还需要布位移计吗？**

需要。云图给的是空间分布，位移计给的是高信噪比的连续时程。两者回答的问题不同，控制断面上的点位数据也是校核云图是否可信的参照。

**2. 位移场颜色最深的地方，就是应力最大的地方吗？**

不一定。位移包含刚体平移和转动，颜色深浅反映的是位移大小，不是应变大小。判断应力集中要看应变场，还要结合构件几何和边界条件。

**3. 视场铺得越大越划算吗？**

不是。视场扩大，单个像素对应的物理尺寸变大，空间分辨率下降，窄剪切带和细小裂纹容易糊成一片。长大构件更适合分区多对相机加重叠区。

**4. 视场扩大以后，0.01 mm 级的分辨力还成立吗？**

不成立。视场扩大意味着单个像素覆盖更大的实际尺寸，同一台相机能分出的最小位移随之变大；再加上表面纹理、光照稳定性、支架刚度和标定残差的叠加，远距离大视场下的分辨力与近距离短视场不在同一量级。要保住分辨力，要么缩小视场，要么提高成像端的解析能力。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Why Bridges, Tunnels and Slopes Need Full-Field Deformation Monitoring: Capabilities and Limits of XTDIC 3D Full-Field Measurement

> **Abstract:** Deformation in bridges, tunnels and slopes is rarely uniform. Displacement transducers and strain gauges deliver high signal-to-noise time histories at discrete points, but stress concentrations, plastic development and crack initiation often occur between those points. This article separates full-field monitoring into three distinct outputs — the displacement field, the strain field, and crack propagation over time — explains what each one actually answers, and describes how imaging methods complement point sensors and absolute-position instruments. It then sets out three operating regimes and five practical limits, including how field of view, speckle quality and calibration set the smallest displacement that can still be resolved.

> **Keywords:** XTDIC 3D full-field measurement; digital image correlation; full-field deformation monitoring; displacement field; strain field; crack propagation

## Contents

- [1. From a Few Points to a Whole Surface](#1-from-a-few-points-to-a-whole-surface)
- [2. What Full-Field Measurement Actually Measures](#2-what-full-field-measurement-actually-measures)
- [3. Dividing the Work with Transducers, Strain Gauges and Total Stations](#3-dividing-the-work-with-transducers-strain-gauges-and-total-stations)
- [4. Three Operating Regimes and Five Limits](#4-three-operating-regimes-and-five-limits)
- [5. FAQ](#5-faq)

## 1. From a Few Points to a Whole Surface

On a bridge girder under staged loading, mid-span deflection, web shear at the quarter points, and local bearing stress near the supports are three different phenomena with three different shapes. After tunnel excavation, crown settlement and sidewall convergence do not develop at the same pace. On a slope after rainfall infiltration, strain localisation in the surface soil often appears first near the toe or around a weak interlayer — which is precisely where the instrumented section may not be.

What these cases share is a mismatch of scale: failure starts as a region, while conventional instrumentation reports a handful of curves. Each curve is trustworthy, but the space between curves is unobserved, and cracks have a habit of appearing in exactly that space.

The way engineers pose the question has shifted accordingly. It used to be "what is the maximum settlement, what is the peak strain". Increasingly it is "where is the concentration, how does the plastic zone grow, where does the crack start and which way does it run". The second kind of question is hard to answer with discrete points. Adding more sensors improves coverage, but every sensor still speaks for its own small neighbourhood.

Full-field monitoring exists to fill that gap. Its purpose is not to make individual points more accurate; it is to make the space between points visible.

## 2. What Full-Field Measurement Actually Measures

"Full-field" is often used as a vague adjective. In practice it covers at least three outputs that answer different questions, and conflating them leads to wrong conclusions.

The displacement field answers "which way, and how far". Three-dimensional digital image correlation tracks the grey-level pattern of a speckled surface with industrial cameras, matches subsets between the left and right views and between successive frames, and solves for three-dimensional coordinates. The result is a spatially continuous vector field that can be rendered as a contour map or sampled along any path.

The strain field answers "where is it being stretched hardest". Strain is obtained by differentiating the displacement field in space, giving normal, shear and principal components. One relationship is easy to overlook: a displacement field can look perfectly smooth while the strain field shows sharp local peaks, because differentiation amplifies small-scale differences. Strain credibility therefore depends directly on spatial resolution. The wider the field of view, the larger the physical area each correlation subset covers, and the coarser the strain gradient that can still be resolved.

Crack propagation timing answers "when did it start, and which way is it running". This is not merely a geometric quantity. Binding crack position and length to a time axis is what allows initiation to be related to a load level, a sudden temperature change, or a particular construction stage.

The relationship among the three is straightforward: the displacement field is the base data, the strain field is its spatial interpretation, and crack timing is its temporal interpretation. Large displacement does not imply large strain. Rigid-body translation can produce a visually rich displacement map while strain stays near zero. Conversely, strain inside a narrow shear band can be high while overall displacement is modest. Treating these as one quantity produces the classic error of reading contour colours as a stress ranking.

## 3. Dividing the Work with Transducers, Strain Gauges and Total Stations

Advocating full-field measurement is not an argument that point instruments are obsolete. Each family is good at something different, and most working setups combine them.

Displacement transducers and strain gauges win on signal-to-noise ratio and time history. A single-point displacement transducer responds stably to small changes, samples quickly, and keeps long-term drift manageable, which suits continuous recording at a control section. A strain gauge bonded to the surface is sensitive to local strain change and suits known hot spots. Their weakness is coverage: a dozen sensors on one section already counts as dense, and the area between them remains unobserved.

Total stations and GNSS win on absolute coordinates and long-term datum. They place a target in a global reference frame, which supports stable datum definition, trend observation and comparison across campaigns. Their weakness is low spatial density, limited sampling rate, and insensitivity to small local surface deformation.

Imaging methods win on spatial continuity. A single acquisition yields displacement at thousands of locations, making the shape of a concentration zone, the direction of a plastic region, and the displacement jump across a crack directly visible. Their weakness is that they see only the surface, and they are sensitive to texture quality, illumination and vibration.

These families substitute for one another poorly. A workable division of labour is: total station or GNSS for the absolute datum; transducers and gauges for high signal-to-noise histories at control sections; imaging for spatial coverage and for flagging anomalous regions; then densify point instrumentation inside those flagged regions. Accuracy where it is needed, coverage where it is missing.

| Method | Primary output | Strength | Limitation |
| --- | --- | --- | --- |
| Displacement transducer | Point displacement history | Continuous recording at control sections, high sampling rate | Small footprint, nothing observed between points |
| Strain gauge | Point strain history | Local strain change at known locations | Requires bonding, limited count |
| Total station / GNSS | Absolute coordinates | Global datum, cross-campaign comparison | Low spatial density, insensitive to small deformation |
| Imaging methods | Displacement field, strain field, crack features | Spatially continuous, locates anomalies | Surface only, depends on texture and environment |

## 4. Three Operating Regimes and Five Limits

### 4.1 Three operating regimes

The acquisition chain covers three regimes. Static and quasi-static work is the most common: staged static loading of a scaled model, long-term creep observation of a component, with acquisition paced by load step or by elapsed time. High-speed dynamic impact is the second: high frame rates and hardware synchronisation are needed to resolve deformation propagation and local failure during the event. Long-duration observation is the third, concerned with slow change over weeks or months, where the difficulty is not single-frame quality but datum stability and suppression of environmental drift.

The three regimes place different demands on the system. Static work cares about calibration accuracy and field coverage. Dynamic work cares about frame rate and trigger synchronisation. Long-duration work cares about robustness and calibration re-checks.

### 4.2 Five limits

First, only the observable surface is measured. The system reports displacement and strain on the face the cameras can see; the interior, the occluded side, and anything embedded are outside the data. Inferring internal stress from surface strain requires constitutive assumptions and boundary conditions — that is analysis, not measurement.

Second, speckle or natural texture quality determines usability. Without trackable features, matching has nothing to work with. Artificial speckle grain size, density and contrast must match the field of view and subset size. Whether natural texture — concrete aggregate, mineral grains in rock — can be used directly should be decided from a trial acquisition on site, not from assumption.

Third, a larger field of view means lower spatial resolution. Sensor resolution is fixed, so widening the view increases the physical size each pixel represents and coarsens the finest resolvable strain gradient. Long members call for multiple camera pairs covering adjacent zones with overlap for cross-zone consistency checks, not for pulling the lens back.

Fourth, wind-induced vibration, illumination change and thermal drift must be suppressed. Outdoors, small movement of the camera support is solved as structural deformation; sunlight-driven brightness change degrades matching; temperature change makes the support and the structure expand differently. Algorithms alone will not remove these. They are handled in hardware — independent mounts, shading, supplementary lighting — and in procedure, through static-period re-checks during long campaigns.

Fifth, the 0.01 mm band corresponds to displacement resolution under suitable conditions; it is not a constant independent of the scene. Stretching the field from a few metres to tens of metres enlarges the physical area covered by one pixel, so the smallest displacement the same hardware can separate grows with it. Surface texture, illumination stability and calibration quality then stack on that chain, which puts long-range wide-field resolution in a different band from a short indoor view.

Once the capability and its limits are clear, the next question is which algorithms actually deliver them: how the coordinate datum is built, how displacement is resolved below a pixel, how noise is suppressed, and how image frames are tied to load steps.

## 5. FAQ

**1. With full-field contour maps available, are displacement transducers still needed?**

Yes. Contours provide spatial distribution; transducers provide high signal-to-noise continuous history. They answer different questions, and point data at control sections also serve as a reference for judging whether the contours are credible.

**2. Is the darkest area of the displacement map where stress is highest?**

Not necessarily. Displacement includes rigid-body translation and rotation, so colour depth reflects displacement magnitude, not strain. Stress concentration should be judged from the strain field together with geometry and boundary conditions.

**3. Is a wider field of view always better value?**

No. Widening the view increases the physical size per pixel and reduces spatial resolution, so narrow shear bands and fine cracks blur together. Long members are better served by multiple camera pairs covering adjacent zones with overlap.

**4. Does 0.01 mm resolution still hold once the field of view widens?**

No. A wider view means each pixel covers a larger physical area, so the smallest resolvable displacement grows for the same camera. Surface texture, illumination stability, mount stiffness and calibration residuals add to that chain, which puts long-range wide-field resolution in a different band from a short indoor view. Keeping resolution means accepting a smaller field, or raising the resolution of the imaging end.

</details>
