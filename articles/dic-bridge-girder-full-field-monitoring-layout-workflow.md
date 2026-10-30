# 桥梁全域变形监测怎么布点：XTDIC在缩尺主梁加载中的方案设计

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 布点不是把视场铺满就完事。本文以公铁两用大桥钢混主梁缩尺模型的分级静力加载为例，说明跨中、四分点、支座、腹板、组合界面、底板各自关注什么，视场该按单对还是分区划分、重叠区用来查什么，标定如何与加载工况绑定，输出图表的口径怎么统一，以及从缩尺模型推向现场时哪些结论要收着说。另以混凝土梁试件的四点弯曲加载作补充对照。

> **关键词：** XTDIC三维全场测量；数字图像相关技术；桥梁变形监测；测点布置；视场划分；缩尺模型

## 目录

- [一、工程问题：缩尺主梁加载要回答什么](#一工程问题缩尺主梁加载要回答什么)
- [二、布点与视场：每一处关注点要的不一样](#二布点与视场每一处关注点要的不一样)
- [三、标定与工况映射：把图像帧钉在荷载级上](#三标定与工况映射把图像帧钉在荷载级上)
- [四、结果输出、判读与缩尺到现场的边界](#四结果输出判读与缩尺到现场的边界)
- [五、常见问题](#五常见问题)

## 一、工程问题：缩尺主梁加载要回答什么

缩尺模型试验的目的通常不是复现某座桥的实测值，而是在可控条件下看清受力路径。钢混主梁由两种材料、一道组合界面和沿纵向变化的截面组成，各部分响应节奏并不一致，分级加载把这一过程拉成一系列可比较的状态。

先列清楚要回答的问题，比先架相机有用：

- 加载全过程中，应力沿主梁的扩散路径是什么形状，从加载点往两侧怎么传；
- 应变集中区落在什么位置，是跨中下缘、腹板中部，还是组合界面附近；
- 各部位变形随荷载级如何发展，有没有某一级之后斜率明显改变；
- 卸载后残余变形有多大，恢复到什么程度。

四个问题要的答案形式不同：第一个要覆盖，第二个要空间分辨率，第三个要可靠的时间轴，第四个要参考状态一致。一套布点满足不了全部，取舍就发生在视场划分上。

## 二、布点与视场：每一处关注点要的不一样

### 2.1 跨中与四分点

跨中下缘是受弯最直接的位置，竖向位移与纵向应变反映整体刚度，荷载—位移曲线也常在此取点。四分点在对称加载下剪力与弯矩的组合不同于跨中，腹板附近的剪应变往往比跨中更值得看。

两处对分辨率要求不同：跨中下缘应变沿纵向变化平缓，子区可稍大；四分点腹板剪应变方向性强，子区偏大会把剪切带抹平。

### 2.2 支座附近

支座附近是另一类问题：局部承压、剪力集中、应力流方向改变都在这里。全域测量的价值在这类区域比较明显——点式布点难判断承压区范围，云图能看出高应变区从支座边缘往哪个方向延伸、延伸多远。

这里也容易出问题：金属支座与加载装置反光干扰匹配，遮挡造成空洞。布点要么调整机位避开，要么在报告中标明无效区。

### 2.3 腹板沿高度的应变梯度

梁弯曲时，腹板沿高度的应变并不均匀：中性轴附近接近零，向上下缘增大。刻画梯度要靠空间分辨率。若一个子区的高度占了腹板深度的一大块，梯度被平均成一条平线，云图看起来"应力分布均匀"，实际并非如此。

做法是沿高度分带，每带容纳几个子区，再看应变沿高度分布是否连续。

### 2.4 组合界面与底板

组合界面连接两种材料。荷载下钢与混凝土的变形不完全同步，界面附近出现相对滑移。位移场可给出界面两侧位移差，该差值沿纵向的分布，比几个单点读数更能说明滑移集中在哪一段。

底板承受拉力，关注受拉区应变水平与范围。混凝土梁四点弯曲可作对照：分级加载下，腹板与底板的应力集中位置在云图上比较清楚，这两处是全域测量容易出结果的地方。

| 部位 | 主要关注量 | 布点与视场考虑 |
| --- | --- | --- |
| 跨中下缘 | 竖向位移、纵向应变 | 纵向变化平缓，子区可稍大，需覆盖整个下缘宽度 |
| 四分点腹板 | 剪应变、主应变方向 | 剪切带有方向性，子区需偏小 |
| 支座附近 | 局部承压、应力流方向 | 关注影响范围，避反光与遮挡 |
| 腹板沿高度 | 应变梯度、中性轴位置 | 沿高度分带，每带留足子区 |
| 组合界面 | 界面两侧相对滑移 | 视场须同时覆盖钢与混凝土两侧 |
| 底板 | 受拉区应变分布 | 关注范围而非单点，需连续覆盖 |

### 2.5 视场怎么划

单对相机覆盖小模型更划算：一次标定、一个基准、无需拼接，处理也简单。代价是分辨率被摊薄，模型再大一点，腹板的应变梯度就保不住。

长大构件适合多对相机分区，原则不是平均切，而是按关注程度与遮挡关系切：腹板、组合界面给小视场高分辨率，跨中、底板给大视场。相邻分区留重叠区做一致性检查——同一位置被两组相机同时看到，两边数据应当对得上，对不上就说明标定或拼接有问题。

还有一个细节：相机支架必须与加载装置独立。支架若固定在反力架上，加载时反力架的变形会经支架传到相机，被解算成结构变形，表现为整个视场一起动，还常与荷载级同步，事后很难剔除。

## 三、标定与工况映射：把图像帧钉在荷载级上

分级静力加载的特点是每级有保持段，采集节奏应跟着这个结构走：加载到位、变形稳定后连续采集一段，这段既是数据也是静态复核的素材，然后进入下一级。

稳定段多长要现场判断：没稳定就采集，位移偏小；等太久，混凝土徐变起作用，读数继续缓慢变化。可以在保持段内连采若干帧，看位移序列是否收敛到平台，再取平台段。

卸载段同样要记录：它反映弹性恢复与残余变形的比例，也是判断是否进入非线性阶段的依据。漏记，事后分不清斜率变化是损伤还是漂移。

每帧图像都要绑定荷载工况：级号、加载还是卸载、是否处于稳定段。人工记录也能做，但级数一多容易出错；硬件联动更稳，加载信号直接触发采集，帧与荷载级一一对应。映射做不好，荷载—位移曲线上的拐点就会系统性偏移，而这种偏移在图上看着完全正常。

参考状态是零载还是某一级之后，也要写明。零载为参考得累积位移，适合看趋势；某级为参考得增量位移，适合看局部变化。两种口径都对但不能混用，否则曲线会出现莫名的跳变。

## 四、结果输出、判读与缩尺到现场的边界

### 4.1 输出形态

一套完整输出通常包含四类图：荷载—位移曲线、截面变形曲线、应变云图、关键点时序曲线。

四类图必须同源。云图与曲线若来自不同参考帧或滤波设置，就会互相矛盾。跨级比较时色标要统一：这一级 0 到 500 微应变、下一级 0 到 2000，颜色看着差不多，实际差好几倍。

### 4.2 判读的三条规矩

先看曲线再看云图。曲线给出整体趋势和异常级数，云图解释异常出现在哪个位置；顺序反过来，容易被颜色带着走。

云图上的高应变区要回到原始图像确认。反光、散斑脱落、局部污渍都会在应变场上形成假的集中区，看一眼原图能排除大半。

任何突变都要找对应的荷载事件。应变在某一级突然跳变，若该级没有加载动作也没观察到异常，更可能是测量问题。

### 4.3 从缩尺到现场

缩尺模型的结论不能直接搬到实桥。几何缩尺改变了厚度与跨度之比，也改变了自重与荷载的比例；材料相似很难做到，骨料尺寸不随缩尺缩小；模型边界比现场理想，支座是理想铰或滚轴，现场还有沉降、摩阻与温度约束。

测量层面更直接：模型在室内，光照稳、无风、温差小，视场不过几米；现场视场可能几十米，风振、日照、温差全进来，标称精度能否达到要看具体条件，模型上分辨得出的梯度到现场可能就分辨不出来。

所以能迁移的是机理认识和趋势判断，不能迁移的是数值。报告宜写"在该模型中观察到应力沿某路径扩散"，而不是"该桥的应力集中位于某处"。

桥梁的布点逻辑大体如此。隧道要更难一些：开挖面持续推进、观测面被遮挡、洞内光照恶劣，这几件事叠加，视场划分与基准传递的方式都得重新设计。

## 五、常见问题

**1. 模型不大，一对相机全包行不行？**

行，而且更划算：单次标定、统一基准、无需拼接。但要先确认最关注的区域（比如腹板沿高度的应变梯度）在全视场下仍有足够子区，否则改用分区。

**2. 重叠区要留多宽？**

没有固定比例。重叠区要能容纳若干完整子区，并覆盖边界附近最关注的构造，一般按边界处构件特征尺寸的若干倍估算。

**3. 卸载段的数据有什么用？**

它给出弹性恢复与残余变形的比例，是判断模型是否进入非线性阶段的依据，也能帮助区分结构响应与测量漂移。

**4. 云图色标范围设大一点是不是更保险？**

不是。范围过大会压低对比度，局部集中区看起来一片均匀；范围过小则大面积饱和。关键是跨荷载级保持同一色标，并在图注里写明范围。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Placing Measurement Points for Full-Field Bridge Monitoring: XTDIC Layout Design for a Scaled Girder Test

> **Abstract:** Coverage is not the same thing as a good layout. Using staged static loading of a scaled steel-concrete girder from a combined road-rail bridge as the working example, this article explains what the mid-span, quarter points, supports, web, composite interface and bottom slab each require, when a single camera pair beats multiple zones, what overlap regions are for, how calibration and load cases bind to image frames, how output conventions stay consistent, and which conclusions survive the move from laboratory model to real structure. A four-point bending test on a concrete beam serves as a secondary reference.

> **Keywords:** XTDIC 3D full-field measurement; digital image correlation; bridge deformation monitoring; sensor layout; field-of-view partitioning; scaled model

## Contents

- [1. The Engineering Questions a Scaled Girder Test Must Answer](#1-the-engineering-questions-a-scaled-girder-test-must-answer)
- [2. Layout and Field of View: Each Location Wants Something Different](#2-layout-and-field-of-view-each-location-wants-something-different)
- [3. Calibration and Load Mapping: Pinning Frames to Load Steps](#3-calibration-and-load-mapping-pinning-frames-to-load-steps)
- [4. Output, Interpretation and the Limits of Scaling](#4-output-interpretation-and-the-limits-of-scaling)
- [5. FAQ](#5-faq)

## 1. The Engineering Questions a Scaled Girder Test Must Answer

A scaled model test is rarely about reproducing measured values from a particular bridge. Its purpose is to make the load path visible under controlled conditions. A steel-concrete girder combines two materials, a composite interface and a varying cross-section, and these parts do not respond in step. Staged loading turns the response into comparable states that the model makes observable more than once.

Writing the questions down first is more useful than positioning cameras first:

- What shape does stress take as it spreads through the girder, and how does it travel out from the load points?
- Where do strain concentrations sit: lower mid-span fibre, mid-depth web, or near the composite interface?
- How does deformation at each location develop with load level, and is there a step after which the slope changes?
- How much residual deformation remains after unloading, and how far does the structure recover?

The four want four different answers: coverage, spatial resolution, a reliable time axis and a consistent reference state. No single layout satisfies all four; the trade-off happens where the field is divided.

## 2. Layout and Field of View: Each Location Wants Something Different

### 2.1 Mid-span and quarter points

The lower mid-span fibre is the most direct bending location: displacement and longitudinal strain there reflect overall stiffness, which is why the load-displacement curve is usually sampled at that point. At the quarter points, shear and moment combine differently, and web shear strain often matters more.

Resolution demand differs: longitudinal strain at lower mid-span varies gently, so a larger subset is tolerable, while quarter-point web shear is strongly directional and an oversized subset smooths the band away.

### 2.2 Near the supports

The support region is a different problem: local bearing, shear concentration and redirected stress flow all coincide there. Full-field measurement earns its place here — discrete gauges struggle to show how far the bearing zone extends, while a contour map shows which way the high-strain region runs.

It is also where things go wrong: reflection from steel bearing components and loading hardware interferes with matching, and occlusion leaves holes. Reposition the cameras or mark the invalid region in the report.

### 2.3 Strain gradient through the web depth

Under bending, strain through the web is not uniform: near zero at the neutral axis, growing toward the outer fibres. Resolving that gradient needs spatial resolution. If one subset spans much of the web depth, the gradient averages into a flat line and the map appears to show uniform stress, which it is not.

The practice is to divide the web depth into bands holding several subsets each, then check whether the strain profile is continuous and has the expected shape. A kink usually indicates a detail change or local defect at that height.

### 2.4 Composite interface and bottom slab

The composite interface joins two materials. Under load, steel and concrete do not deform in step, so relative slip develops. A displacement map yields the difference across the interface, and its distribution along the span says more about where slip concentrates than a few transducer readings.

The bottom slab carries tension, so the quantity of interest is the level and extent of tensile strain. The four-point bending test on a concrete beam is a useful cross-check: under staged loading, concentration in the web and bottom slab is clearly visible on the contour map.

| Location | Quantity of interest | Layout and field-of-view consideration |
| --- | --- | --- |
| Lower mid-span | Vertical displacement, longitudinal strain | Gentle variation, larger subset acceptable, must cover full width |
| Quarter-point web | Shear strain, principal direction | Directional band, smaller subsets needed |
| Near supports | Local bearing, stress flow | Extent of influence matters, avoid reflection and occlusion |
| Web depth | Strain gradient, neutral axis | Divide into bands with enough subsets each |
| Composite interface | Relative slip across interface | Field must cover steel and concrete sides |
| Bottom slab | Tensile strain distribution | Extent rather than point, needs continuous coverage |

### 2.5 Dividing the field of view

A single camera pair over a small model is the better bargain: one calibration, one datum, no stitching, simpler processing. The cost is diluted resolution; grow the model slightly and the web gradient stops being resolvable.

Long members suit multiple zoned pairs. The principle is not even division but division by criticality and occlusion: small fields and high resolution for the web and composite interface, wide fields for mid-span and the bottom slab. Leave overlap between adjacent zones for consistency checking: the same location seen by two pairs should yield matching results, and a mismatch points to calibration or stitching.

One detail is easy to overlook. Camera mounts must be independent of the loading frame. Mount them on the reaction frame and its deformation travels through the mount into the cameras, where it is solved as structural deformation. The signature is the whole field moving together, often in step with load level — convincing enough to be mistaken for real signal, and hard to remove afterwards.

## 3. Calibration and Load Mapping: Pinning Frames to Load Steps

Staged loading holds at each level, and acquisition should follow: load, wait for deformation to settle, record a sequence that serves as data and as a static re-check, then advance.

How long to hold is a site judgement. Record too early and displacement reads low; wait too long and concrete creep resumes. Record several frames within the hold and take the plateau once the series converges.

The unloading branch deserves recording too. It carries the ratio of elastic recovery to residual deformation and indicates whether the model has entered a nonlinear stage. Skip it, and there is no way afterwards to tell a genuine slope change from measurement drift.

Every frame must carry its load case: step number, loading or unloading, and whether it falls inside the hold. Manual logging works until the step count grows. Hardware linkage is steadier, with the loading signal triggering acquisition for one-to-one correspondence. Poor mapping shifts inflection points systematically, and the resulting curve still looks normal.

State the reference explicitly. Referenced to zero load, the result is cumulative displacement and suits trend; referenced to a given step, it is incremental and suits local change. Both are valid, but mixing them produces jumps with no physical cause.

## 4. Output, Interpretation and the Limits of Scaling

### 4.1 Output forms

A complete set usually has four parts: the load-displacement curve, section deformation curves, strain contours, and point histories.

All four must share one source. Contours and curves from different reference frames or filters will contradict each other while each looks reasonable alone. Across load levels, keep the colour scale fixed: 0-500 microstrain at one level and 0-2000 at the next look similar while differing fourfold.

### 4.2 Three rules for reading results

Read curves before contours. Curves establish trend and flag the anomalous step; contours then explain where it sits. The reverse order lets colour lead.

Take any high-strain region back to the raw image. Reflection, speckle loss and staining all produce false concentrations, and a glance at the original frame removes most of them.

Tie every jump to a load event. A sudden strain change at a step with no loading action and no observed anomaly is more likely a measurement problem than a structural response.

### 4.3 From model to site

Model conclusions do not transfer directly to a real bridge. Geometric scaling changes the ratio of thickness to span and the balance of self-weight against load. Material similarity is never exact: aggregate size does not shrink with the model. Boundary conditions are far more ideal — hinges and rollers versus settlement, friction and thermal restraint.

The measurement differences are more immediate. A model sits indoors with stable lighting, no wind and small temperature swings, across a field of a few metres. A site is outdoors, the field may span tens of metres, and wind, sunlight and the diurnal cycle all enter. Whether the nominal accuracy figure is reached depends on those conditions, and a gradient resolved on a model may vanish once the field widens.

What transfers is mechanistic understanding and trend judgement. What does not is the number. A report should say that stress was observed to spread along a given path in that model, not that stress concentrates at a given location in that bridge.

That covers bridges. Tunnels are harder in a different way: the face keeps advancing, the observation surface is partly occluded, and lighting inside is poor. Field partitioning and datum transfer both need redesigning.

## 5. FAQ

**1. The model is small — can one camera pair cover everything?**

Yes, and it is the better bargain: one calibration, one datum, no stitching. Confirm first that the most critical region, such as the strain gradient through the web depth, still holds enough subsets across the full field. If not, move to zones.

**2. How wide should the overlap be?**

There is no fixed ratio. It must hold several complete subsets and cover the most critical detail near the boundary. A working estimate is a few times the feature size of the member there.

**3. What is the point of recording the unloading branch?**

It gives the ratio of elastic recovery to residual deformation, indicates whether the model has entered a nonlinear stage, and separates structural response from measurement drift.

**4. Is a wider colour scale safer?**

No. Too wide flattens contrast so local concentrations look uniform; too narrow saturates large areas. Keep one colour scale across load levels and state the range in the caption.

</details>
