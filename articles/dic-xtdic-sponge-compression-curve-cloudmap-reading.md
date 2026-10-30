# 云图与曲线怎么对上：XTDIC海绵压缩试验的输出解读

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 海绵压缩试验做完，设备给出两类结果：一条 ROI 平均应变曲线和一组应变全场云图。曲线说明整体走到哪一步，云图说明哪里先变形、哪里最狠，两者缺一不可。本文按加载步划分三个阶段，逐段说明判读价值，并给出曲线与云图的对照方法、报告出图要素和四种常见误读。

> **关键词：** XTDIC；数字图像相关技术；海绵压缩；应变云图；ROI 曲线；三段划分；数据判读

## 目录

- [一、两类结果，各回答一个问题](#一两类结果各回答一个问题)
- [二、ROI 曲线的三段怎么划](#二roi-曲线的三段怎么划)
- [三、云图补的是空间信息](#三云图补的是空间信息)
- [四、曲线与云图怎么对照](#四曲线与云图怎么对照)
- [五、报告里该放哪几张图](#五报告里该放哪几张图)
- [六、四种常见误读](#六四种常见误读)
- [七、常见问题](#七常见问题)

## 一、两类结果，各回答一个问题

试验做完，设备给的其实就两样：一条 ROI 平均应变随加载步变化的曲线，一组 Y 向工程应变的全场云图。很多人下意识把云图当配图，重点全放在曲线上，这是个挺常见的偏差。

曲线是把一块区域压成一个数。好处是干净、好比较、能看出趋势，代价是把空间信息全丢了。云图正好相反，它保留了每个位置的值，能看出哪里先动、哪里最狠，但单看一张图，说不清整体走到了哪一步。

两类结果不是主次关系，是互补关系。曲线回答“整体到了哪一步”，云图回答“哪里先到、哪里最狠”。缺一个，结论就会偏：只有曲线，容易把局部先屈服当成整体屈服；只有云图，容易把某一帧的极值当成全过程的极值。

容易被忽略的前提是：两类结果来自同一次采集、同一批图像、同一个参考帧。若曲线是一套参数算的、云图是另一套，二者本来就不该对上，对照前先确认。

## 二、ROI 曲线的三段怎么划

曲线不是一条直线，先平、再陡、最后放缓。三段与加载步对应，划段要拿加载步做坐标，而不是凭眼睛找拐点。

| 阶段 | 加载步区间 | 曲线特征 | 判读价值 |
| --- | --- | --- | --- |
| 接触调整与线弹性 | 0–100 | 应变维持在 0 附近 | 验证初始状态与系统稳定性 |
| 屈服与平台起始 | 100–300 | 应变快速达到约 -30% | 定位屈服拐点 |
| 泡孔坍塌平台 | 300–650 | 应变峰值接近 -70%，速率放缓且平滑 | 判断吸能平台是否够长够稳 |

第一段的意义常被低估。应变几乎不动，其实是最直接的系统体检：如果曲线在缓慢爬升或者抖动，说明参考帧不稳、试样没贴合，或者环境光在变。带着这样的起点往下走，后面的拐点位置都会偏。

第二段信息量最大。应变在很短的区间里从接近零冲到三成，曲线出现明显的突变拐点。这个拐点对应泡孔壁开始弯曲屈曲，材料由线弹性进入屈服。工程上关心“什么时候开始失效”，答案基本落在这个位置上。要注意，拐点是曲线上的特征，不是云图上的，靠云图找很难找准。

第三段最长，也最容易被误读。应变速率放缓，曲线进入平台，压缩应变继续增加，峰值接近七成。这个平台是吸能的主要区间，平台越长越平稳，缓冲吸能的能力越有讨论价值。曲线在这里没有明显锯齿，说明泡孔坍塌是渐进的，不是成批脆断。反过来，如果平台段出现密集抖动，先查加载是否平稳、图像是否丢帧，再考虑材料本身。

三段之间没有硬边界，加载步的划分依据要写进报告。换一台试验机、换一个加载速率，区间数值会变，但“先平、再陡、后缓”的形状和对应的物理过程不变。

## 三、云图补的是空间信息

云图至少能读出三层东西。

第一层是量级。同一加载步下，云图的色标范围和曲线读数要对得上，这是最基本的自洽检查。曲线读 -30%，云图上大部分区域也落在 -30% 附近，这一帧才可信。

第二层是梯度方向。压缩不均匀，靠近压盘的区域往往先进入高应变，中部与边缘的水平不一样。梯度往哪个方向走，决定了测点布置、传感器粘贴位置和重点观察区。

第三层是局部异常。云图上如果出现孤立极值斑点，和周围梯度不连续，那多半不是材料行为，而是反光、遮挡或者局部失配。这类点在看曲线时是看不见的，因为 ROI 平均会把它抹平。

要提醒一句：云图给的是表面量。海绵内部是三维泡孔结构，表面塌陷得厉害，不代表内部同样塌陷；反过来，表面看着还好，内部可能已经塌了。要看内部结构，得靠断面观察或者别的成像手段，云图替代不了。

## 四、曲线与云图怎么对照

方法不复杂：同一加载步，取曲线读数，再取一条穿过 ROI 的截面，看两者量级是否自洽。曲线读 -30%，截面上大部分区域也在 -30% 附近，说明这一帧站得住。

不自洽的情况更值得关注。曲线平滑、云图却出现孤立极值，通常是局部失配或者反光，不是材料真的在那里突变。反过来，曲线出现台阶而云图整体连续，多半是 ROI 里混进了边缘区域或者背景。两种情况的处理方向完全不同：前者回原始图像找那一帧，后者回去改 ROI。

还有一种常见现象：不同加载步的云图长得差不多，颜色都很“满”。这往往是色标被自动拉伸，每一帧都撑满整个色阶，看起来处处高应变。这时候要回到固定色标重新出图，再判断。

不必每一帧都对照，挑关键步就够了：加载前、屈服拐点、平台中段、接近末端，四个位置对一遍，基本能判断整条曲线是否可信。

## 五、报告里该放哪几张图

不必把每一帧都放进去，放多了反而抓不住重点。一组够用的图通常包括四张：加载前的参考状态，用来交代起点；屈服拐点附近一张，对应曲线的突变位置；平台区中段一张，展示应变的分布形态；接近末端一张，说明压缩到了什么程度。

四张图配统一色标，叠上 ROI 边界和阶段划分依据，读者能自己把曲线和云图对上。图注里写清加载步、色标上下限和单位。

## 六、四种常见误读

| 误读 | 典型表现 | 更稳妥的读法 |
| --- | --- | --- |
| 把工程应变当真实材料应变 | 直接把 -70% 当成材料压缩率 | 工程应变按初始尺寸计算，泡孔坍塌后局部真实应变与它不同 |
| 把平台平缓当成已经致密化 | 看到曲线不再陡升就认为压实 | 平台区是泡孔坍塌、致密化前期，真正压实还在更后面 |
| 用不同色标的云图跨批次比较 | 两批颜色相近就认为一致 | 色标不同则颜色不可比，须统一上下限 |
| 只看最终一张云图 | 用末帧代表全过程 | 过程信息在中间帧 |

第一种最普遍。工程应变的分母是初始高度，压缩到七成时试样已是薄片，局部泡孔的真实应变量级和工程值不是一回事。拿工程应变去填本构模型，参数会系统性偏。

第二种是把“平台”和“压实”混了。平台区应变还在增长，只是速率放缓，泡孔壁还在继续坍塌，离真正的致密化还有距离。把这段当成终点，会低估材料的吸能行程。

第三种是出图习惯问题。自动色标方便，但跨批次比较时颜色和量值脱钩，两个批次看着一样红，实际可能差一个量级。

第四种是时间成本。末帧信息量最低，它只告诉你终点在哪，不告诉你路径怎么走。屈服从哪里开始、平台稳不稳，全在中间帧里。

## 七、常见问题

**1. 只有一个 ROI 平均曲线，够不够用？**

作为主结果够用，作为单一结果不够。它适合看趋势和定位拐点，但看不出空间分布。至少要配几张关键步的云图，否则局部先屈服这类问题会被平均掉。

**2. 云图上出现孤立的高应变点要紧吗？**

先看它是否和周围梯度连续。孤立的、边界生硬的斑点，多数是反光或失配，回原始图像能看出来。如果它随加载步逐步扩展、和整体梯度连成片，那才是材料行为。

**3. 同一批数据，两个人出的云图不一样，是什么原因？**

多半是参考帧、ROI 边界、色标范围或者平滑参数不同。这四项写进报告，差异就能解释。写不进去，两张图就没法比较。

**4. 平台区多长算够？**

没有统一的门槛。要看具体应用：减振垫关心的是在工作应力范围内能不能维持稳定承载，防护包装关心的是吸能行程够不够。同一材料在不同厚度、不同密度下平台长度也不同，只能在同一批次内部做相对比较。

**5. 这套结果能直接用来标定仿真本构吗？**

可以提供弹性段模量、屈服拐点和平台段的数据支撑，但要注意工程应变与真实应变的差别，以及云图只反映表面。标定前先把这几项口径统一，比直接拟合一条曲线靠谱。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Reading Contours Against Curves: Interpreting the Output of Sponge Compression Tests with XTDIC

> **Abstract:** A sponge compression test produces two kinds of result: an ROI-averaged strain curve and a set of full-field strain contours. The curve says how far the whole specimen has gone; the contour says where deformation started first and where it is most severe. This article divides the loading into three stages by load step, explains what each stage is worth reading for, and sets out how to cross-check curve and contour, what a report should show, and four common misreadings.

> **Keywords:** XTDIC; digital image correlation; sponge compression; strain contour; ROI curve; stage division; data interpretation

## Contents

- [1. Two results, two questions](#1-two-results-two-questions)
- [2. Dividing the ROI curve into three stages](#2-dividing-the-roi-curve-into-three-stages)
- [3. What the contour adds](#3-what-the-contour-adds)
- [4. Cross-checking curve and contour](#4-cross-checking-curve-and-contour)
- [5. Which figures belong in the report](#5-which-figures-belong-in-the-report)
- [6. Four common misreadings](#6-four-common-misreadings)
- [7. FAQ](#7-faq)

## 1. Two results, two questions

A finished test leaves two things: a curve of ROI-averaged strain against load step, and a set of full-field contours of engineering strain in the Y direction. Many people treat the contour as an illustration and watch only the curve.

A curve compresses a region into one number: clean and comparable, at the price of all spatial information. A contour keeps a value at every position, showing where movement started and where it is worst, but cannot say how far the specimen has travelled.

The two are complementary rather than primary and secondary. The curve answers how far; the contour answers where first and where worst. With the curve alone, local yielding is easily taken for global yielding; with the contour alone, one frame's extreme is taken for the extreme of the whole process.

One precondition is easy to overlook: both results must come from the same acquisition and reference frame. A curve from one parameter set and a contour from another were never meant to agree.

## 2. Dividing the ROI curve into three stages

The curve starts flat, steepens, then flattens again, and the three parts correspond to load steps. Anchor the division on load step numbers rather than on where the knee looks.

| Stage | Load steps | Curve feature | What it is worth reading for |
| --- | --- | --- | --- |
| Contact take-up and linear elasticity | 0–100 | Strain stays near zero | Confirms initial state and system stability |
| Yield and start of the plateau | 100–300 | Strain rises quickly to about -30% | Locates the yield knee |
| Cell collapse plateau | 300–650 | Peak near -70%, rate slows, curve smooth | Shows whether the plateau is long and steady |

The first stage is underrated. Strain barely moves, yet this is the most direct system check: a creeping or wobbling curve means an unstable reference, a poorly seated specimen or changing ambient light. Such a baseline shifts every later knee.

The second stage carries the most information. Strain climbs from near zero to thirty percent over a short interval and the curve shows a clear knee, where cell walls buckle and the material passes into yield. The question of when failure starts is answered largely here. The knee belongs to the curve, not the contour, where it is hard to find.

The third stage is the longest and the most often misread. The rate drops, the curve settles into a gentle plateau, and strain keeps rising towards a peak near seventy percent. This is the main energy-absorbing range: the longer and steadier, the more there is to say about cushioning. No sawtooth means cells collapse progressively rather than in brittle batches. Dense jaggedness calls for a check of loading smoothness and dropped frames before blaming the material.

There are no hard boundaries, and the basis for the division belongs in the report. Change the machine or the loading rate and the numbers move, while the shape and the physics behind it do not.

## 3. What the contour adds

A contour carries at least three layers of information.

The first is magnitude. At a given load step the colour limits must agree with the curve reading: a curve at -30% and a contour with most of its area near -30% support each other.

The second is gradient direction. Compression is not uniform: regions near the platen enter high strain first, and the middle and edges differ. Which way it runs decides where gauges go and where to look closely.

The third is local anomaly. An isolated extreme that breaks the surrounding gradient is usually glare, obstruction or a local mismatch rather than material behaviour. Such points are invisible in the curve, because ROI averaging smooths them away.

One caution: a contour is a surface quantity. Heavy surface collapse does not imply the same inside, and an intact surface may hide collapsed cells. The interior needs sectioning or another imaging method.

## 4. Cross-checking curve and contour

The method is simple: at the same load step, take the curve reading and a section across the ROI, and see whether the magnitudes agree. A curve at -30% with most of the section near -30% means the frame holds up.

Disagreement deserves more attention. A smooth curve with an isolated extreme on the contour usually means local mismatch or glare, not a jump in the material; a stepped curve with a continuous contour usually means the ROI includes an edge or background. The fixes run in opposite directions: back to the raw images, or back to the ROI.

Another familiar sight is a set of contours that look alike, with colour filling the scale: automatic scaling stretches every frame across the full range. Replot with fixed limits before judging.

Rhythm matters too. There is no need to check every frame: before loading, at the yield knee, mid-plateau and near the end is enough to judge the curve.

## 5. Which figures belong in the report

Too many frames and the reader loses the thread. Four usually suffice: the reference state, one near the yield knee, one mid-plateau, one near the end.

Give all four one colour scale and overlay the ROI boundary and the basis for the stage division; state the load step, colour limits and units in the caption.

## 6. Four common misreadings

| Misreading | How it shows up | A sounder reading |
| --- | --- | --- |
| Treating engineering strain as true material strain | Using -70% directly as the compression ratio | Engineering strain uses the initial height; local true strain differs |
| Reading a gentle plateau as full densification | Assuming compaction once the curve stops climbing | The plateau is cell collapse and early densification; compaction comes later |
| Comparing contours with different colour scales | Judging two batches consistent because colours look alike | Different scales make colours incomparable; fix the limits first |
| Looking only at the final contour | Letting the last frame stand for the process | Process information sits in the middle frames |

The first is the most widespread. Engineering strain is divided by the initial height, and at seventy percent the specimen is a thin sheet whose local cell strain differs. Feeding it into a constitutive model biases the parameters systematically.

The second confuses plateau with compaction. Strain is still rising on the plateau, only more slowly, and cell walls are still collapsing. Taking the plateau as the end underestimates the energy-absorbing stroke.

The third is a plotting habit: automatic scaling detaches colour from magnitude, so two batches may look equally red while differing by an order of magnitude.

The fourth is a matter of time budget. The final frame carries the least information: it marks where the process ended, not how it got there.

## 7. FAQ

**1. Is a single ROI-averaged curve enough?**

As the main result, yes; as the only result, no. It shows the trend and locates the knee but carries no spatial distribution. A few contours at key steps are needed, or local yielding disappears into the average.

**2. Does an isolated high-strain spot on the contour matter?**

First check whether it connects to the surrounding gradient. An isolated spot with a hard boundary is usually glare or mismatch and can be traced in the raw images. If it grows with load step and merges into the gradient, it is material behaviour.

**3. Two people processed the same data and got different contours. Why?**

Usually a different reference frame, ROI boundary, colour range or smoothing setting. Write these four into the report and the difference explains itself.

**4. How long is long enough for the plateau?**

There is no universal threshold. It depends on the application: a vibration pad needs stable load carrying within its working stress range, protective packaging needs enough stroke. Thickness and density change the plateau length too, so comparison is safer within one batch.

**5. Can these results calibrate a constitutive model directly?**

They support the elastic modulus, the yield knee and the plateau, provided the gap between engineering and true strain is handled and the contour's surface-only nature is kept in mind. Settle those conventions first.

</details>
