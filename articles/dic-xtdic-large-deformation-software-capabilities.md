# 硬件之外的半台设备：XTDIC软件在海绵超大压缩中的四项能力

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 海绵压缩到70%量级时，散斑随泡孔坍塌剧烈挤压，常规相关计算容易在中途失相关、断线。XTDIC软件侧有三项策略应对：大变形迭代匹配让子区随形变调整，动态参考帧在中途更换基准，ROI空间平均压掉泡孔破裂带来的锯齿噪声；加上全场输出与报告组织，构成硬件之外的另一半能力。本文按“解决什么操作困境、结果上表现为什么差异、什么时候该开”来讲这四项，并给出四条参数经验与换硬件的判断。

> **关键词：** XTDIC；数字图像相关技术；大变形匹配；动态参考帧；ROI平均；海绵压缩

## 目录

- [一、设备能力的一半在软件](#一设备能力的一半在软件)
- [二、三项计算策略：跟得住、有基准、压得平](#二三项计算策略跟得住有基准压得平)
- [三、全场输出与报告：空间和时间两个维度](#三全场输出与报告空间和时间两个维度)
- [四、四条参数经验，以及什么时候该换硬件](#四四条参数经验以及什么时候该换硬件)
- [五、常见问题](#五常见问题)

## 一、设备能力的一半在软件

相机、镜头、光源、支架配齐，只是把“能拍到”这件事解决了。同一批图像交给不同的参数设置，云图可以差出一个量级：有的整段连续，有的压到一半突然一片空白，后面全是无效点。差别不在硬件，在软件怎么处理这批图像。

海绵压缩之所以难，在于三件事同时发生。变形量太大，压缩到70%量级属于超大非线性变形，散斑随泡孔一起被挤压、旋转、畸变；纹理变化太剧烈，泡孔坍塌时局部灰度瞬间重排，前后帧的相关性掉得很快；噪声来源分散，泡孔随机破裂引入的坏点不是白噪声，而是聚在坍塌区，看上去像真实的应变条带。

这三件事对应三项策略：跟得住、有基准、压得平。

## 二、三项计算策略：跟得住、有基准、压得平

**大变形迭代匹配**解决的是“压到后半程，固定子区跟不住”。常规相关里，子区大小固定、形状是方的，只允许平移。海绵压到30%以下还能勉强跟上，再往下，子区覆盖的表面已经被压扁、拉斜、转了角度，方框里的内容跟参考帧对不上，相关系数掉到阈值以下，计算就在这一点中断。中断会传染：相邻点失去约束，误差向四周扩散，最后整片失效。

做法是让子区随形变调整：大小、形状、姿态都可以变。压缩初期用小一点的子区守住分辨率，进入坍塌阶段自动放大、跟随局部畸变，让方框始终“罩住”同一块材料。结果差异很直接：同一次试验，不开这个策略，曲线在-30%附近断掉；开了，能一路连到-70%，中间没有空洞。

**动态参考帧**解决的是“累积变形太大，首帧参考已经失效”。相关就是拿当前帧跟参考帧比。变形累积到一定程度，当前帧和首帧的差异超出算法能接受的范围，再怎么改子区也匹配不上。这时有效的办法是换基准：把中途某一帧设为新参考，后续帧跟它比。

换了基准之后，前后两段的位移相对于不同参考算出来，直接拼在一起会出现台阶，跨段比较必须先对齐坐标。所以更新节点必须记录：第几帧、第几个加载步换的参考，换的时候试样是什么状态。没有这份记录，半年后没人能解释曲线上那个小台阶是材料行为还是换基准造成的。

**ROI区域平均**解决的是泡孔破裂带来的锯齿噪声。海绵云图近看是花的：坍塌区里每隔几个泡孔就有一个坏点，应变值忽高忽低，曲线跟着抖。空间平均把ROI内所有点的应变做统计平均，用空间换稳定，曲线立刻平滑可读，阶段的起止也清楚了。

代价同样清楚：空间分辨率下降。ROI画得越大，平均得越狠，局部差异被抹得越平。如果试样真的一侧先塌、另一侧还完好，一个横跨全宽的大ROI会把这个差别平均掉，报告上就成了“整体均匀受压”。所以ROI边界要贴着有效变形区画，宁可小一点、分区域多算几条曲线。

三项策略放在一起对照，关系会更清楚。

| 功能 | 解决的操作困境 | 结果上的表现 | 代价与注意 |
| --- | --- | --- | --- |
| 大变形迭代匹配 | 固定子区深度压缩时跟不住 | 曲线云图全程连续 | 计算量上升，子区上限过大反糊细节 |
| 动态参考帧 | 累积变形过大，首帧参考失效 | 后半程重新获得有效数据 | 跨段比较需重新对齐，更新节点必须记录 |
| ROI区域平均 | 泡孔随机破裂造成锯齿噪声 | 平均应变曲线平滑，阶段清晰 | 分辨率下降，ROI过大抹平局部差异 |

## 三、全场输出与报告：空间和时间两个维度

算完之后，软件给出的结果可以归成四类：云图、曲线、文本、视频。

云图是空间的。某一加载步下，整个表面的应变分布画成一张图，应变集中区、坍塌条带、边缘效应都在。它回答“这一刻试样长什么样”。

曲线是时间的。ROI平均应变随加载步变化，或者某个关注点的应变时程。它回答“这个试样一路怎么走过来”。

文本是给下游用的。节点坐标、应变值、载荷、步号导成表格，可以直接进仿真做本构参数标定，也可以进统计脚本做批次比对。

视频是把整个加载过程连起来看。静态云图容易漏掉“条带从哪一侧开始、往哪个方向扩”这类过程信息，放一遍就清楚了。

完整的报告应当同时给出空间和时间两个维度：一条平均应变曲线说明整体走到了哪一步，一组关键步的云图说明每一步的变形长什么样，再附上参数记录和参考帧更新节点。只给曲线，读者不知道变形是否均匀；只给云图，不知道这些图处在什么阶段。

## 四、四条参数经验，以及什么时候该换硬件

参数不是越“高级”越好。四条经验覆盖常见情形。

第一条，ROI覆盖有效变形区，但不跨越夹持边界。压盘压住的区域、夹具边缘、试样与压盘的接触带，都不该算进ROI。这些位置的图像被遮挡或严重畸变，算出来的应变没有物理意义，还会把平均值拉偏。宁可ROI小一圈。

第二条，参考帧更新节点与加载阶段对齐，并写进记录。更新点最好落在阶段分界上，比如平台段起点，这样换基准带来的台阶正好与一个真实的物理拐点重合，解释起来不别扭。同时写明帧号和步号，让别人能复现。

第三条，平滑强度以不掩盖阶段拐点为限。平滑是压噪声，不是画一条好看的曲线。拐点被磨圆了，屈服位置就判断不准，本构标定也跟着偏。判断方法很简单：把平滑前后的曲线叠在一起，拐点位置移动超过一两个加载步就是过了。

第四条，色标在整段试验内统一，跨批次比较时也要固定。色标随帧自动缩放看着舒服，但两张图颜色一样深、实际应变差一倍的情况很常见。

那什么时候该停下来，承认问题不在软件？有几条界线比较明确。

视场不够，试样在压缩后期出画，软件救不回来——出画的部分没有像素。分辨率不够，子区覆盖的尺寸小于几个泡孔，云图呈颗粒状，调平滑只会更糊。帧率不够，泡孔成片坍塌发生在一两帧之间，采到的图像直接跨过那个瞬间，事后无法插值。对比度不够，大片区域是无效点，那不是算法保守，是图像里真的没有信息。离面位移明显却只有一台相机，面外鼓出被算成面内应变，这个错误靠参数改不掉。

共同点是所需的信息没有进入图像。软件能做的是把已有的信息榨干，不能凭空补出没有的。原始图像上看不出特征，就别在参数上折腾，换视场、换镜头、加光源、加一台相机。

功能清楚了，下一步是把设备真正跑起来：先定试样与工装，再定视场与光路，然后才是参数。

## 五、常见问题

**1. 迭代匹配是不是就是把子区开大一点？**

不是。子区开大只是覆盖面积变大、细节变少，仍然跟不了旋转和剪切。迭代匹配是在试验过程中改变子区几何：前段小一点保分辨率，后段放大并跟随姿态变化。换来的是始终锁住同一块材料，而不是看得更宽。

**2. 参考帧多久更新一次？**

能少则少，而且必须记录在案。每更新一次就多一次对齐、多一道需要解释的接缝。如果单一参考能让曲线连续到试验结束，就没有理由更新。如果跟踪在某个位置反复失效，把更新点放在它前面一点，并与加载阶段对齐。

**3. ROI平均会不会把真实的缺陷抹掉？**

会，如果ROI画得随意。平均压掉局部尖峰的同时，也压掉了指示薄弱区的那些尖峰。预期存在不均匀时，把一个ROI拆成几块小的分区，比较各自的曲线，而不是整面做一个大平均。

**4. 曲线很平滑，云图上却有条带，哪个是对的？**

两个都对，尺度不同。曲线是区域平均，一条局部条带只贡献它所占比例的那部分幅值；云图显示的是被平均掩盖掉的分布。只报平均会隐藏局部化，只报云图会丢掉整体趋势。两者一起读，并写清楚曲线取自哪个ROI。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Half the System Beyond the Hardware: Four Software Capabilities of XTDIC in Extreme Foam Compression

> **Abstract:** At compression levels near seventy percent, foam speckle is crushed along with the cells, and conventional correlation loses track halfway through a test. Three software strategies address this: large-deformation iterative matching lets subsets adapt to the deformation, dynamic reference frames replace an expired baseline mid-test, and ROI averaging suppresses the jagged noise left by cell rupture. Full-field output and reporting complete the picture. This article explains each in terms of the operational problem it solves, the difference it makes in results, and when to enable it, followed by four parameter rules and the point at which hardware, not software, is the answer.

> **Keywords:** XTDIC; digital image correlation; large-deformation matching; dynamic reference frame; ROI averaging; foam compression

## Contents

- [1. Half the capability sits in software](#1-half-the-capability-sits-in-software)
- [2. Three strategies: keep tracking, keep a baseline, keep it smooth](#2-three-strategies-keep-tracking-keep-a-baseline-keep-it-smooth)
- [3. Full-field output and reporting: space and time](#3-full-field-output-and-reporting-space-and-time)
- [4. Four parameter rules, and when to change hardware](#4-four-parameter-rules-and-when-to-change-hardware)
- [5. FAQ](#5-faq)

## 1. Half the capability sits in software

Cameras, lenses, sources and mounts only solve capturing an image. Hand the same sequence to different settings and the maps can differ by an order of magnitude: one run stays continuous, another goes blank halfway. The difference is not hardware but how the software treats those images.

Foam compression is hard because three things happen at once. The deformation is enormous — seventy percent is well outside linear elasticity, and the speckle is squeezed, rotated and distorted with the cells. The texture changes violently, with local grey levels rearranging within a frame or two so correlation decays fast. And the noise is structured: bad points from ruptured cells cluster in collapsed regions rather than spreading as white noise, so they look like genuine strain bands.

These conditions map onto three strategies: keep tracking, keep a baseline, keep it smooth.

## 2. Three strategies: keep tracking, keep a baseline, keep it smooth

**Large-deformation iterative matching** addresses the loss of tracking late in compression. Conventional correlation fixes subset size and shape and allows translation only. Foam follows this to about thirty percent; beyond that the surface inside the subset is flattened, sheared and rotated, the content no longer matches the reference, correlation falls below threshold and the calculation stops. The failure spreads: neighbouring points lose constraint, error propagates and the region goes invalid.

Iterative matching lets the subset adapt — in size, shape and orientation. Early on a small subset preserves resolution; once collapse begins it grows and follows the local distortion, so it keeps enclosing the same material. Without the strategy the same test stops near minus thirty percent; with it, the record runs to minus seventy percent without gaps.

**Dynamic reference frames** address the case where accumulated deformation has outgrown the original baseline. Correlation compares the current image with a reference, and once the difference exceeds what the algorithm can absorb, no subset adjustment recovers a match. The remedy is to promote a mid-sequence frame to the new baseline.

The cost is real: the two segments are measured against different references, joining them produces a step, and cross-segment comparison needs re-alignment. The update point must therefore be recorded — which frame, which step, what state the specimen was in — or nobody can later tell material behaviour from a baseline change.

**ROI averaging** addresses the jagged noise from cell rupture. Up close a foam map is mottled: a bad point every few cells, strain jumping up and down. Averaging over the region trades space for stability, and the curve smooths at once.

The cost here is resolution. The larger the ROI, the harder the averaging, and the flatter genuine local differences become. If one side collapses first, a single ROI across the full width averages that away and the report reads as uniform compression. Draw the ROI against the effective deformation zone and prefer smaller regions.

The three strategies compare more easily side by side.

| Capability | Operational problem solved | Effect on results | Cost and caution |
| --- | --- | --- | --- |
| Large-deformation iterative matching | Fixed subsets lose track under deep compression | Curve and maps stay continuous throughout | More computation; an oversized subset blurs detail |
| Dynamic reference frames | Accumulated deformation invalidates the first reference | Valid data returns in the second half | Cross-segment alignment needed; updates recorded |
| ROI averaging | Cell rupture produces jagged noise | Averaged curve is smooth, stages are clear | Resolution drops; an oversized ROI erases local variation |

## 3. Full-field output and reporting: space and time

Once the calculation is done, results fall into four categories: maps, curves, text and video.

Maps are spatial: the surface strain distribution at one load step, drawn as an image, showing concentrated zones, collapse bands and edge effects — what the specimen looked like at that instant.

Curves are temporal: ROI-averaged strain against load step, or the history at a point of interest. They answer how the specimen got there.

Text is for downstream use: coordinates, strain, load and step number exported for constitutive calibration or statistics.

Video ties the sequence together: static maps hide which side a band started from and which way it spread.

A complete report carries both: one averaged curve stating how far the test progressed, maps at key steps, and the parameter records with reference-update points. A curve alone leaves uniformity unknown; maps alone leave their stage unknown.

## 4. Four parameter rules, and when to change hardware

Settings are not better for being more elaborate. Four rules cover most foam work.

First, the ROI covers the effective deformation zone without crossing the grip boundary. Regions under the platen, fixture edges and the contact band stay outside: images there are occluded or distorted, the strain has no physical meaning and it pulls the average off.

Second, reference updates align with loading stages and are written into the record. Put the update at a stage boundary, such as the start of the plateau, so the step coincides with a real transition, and record frame and step numbers so the run can be reproduced.

Third, smoothing stops short of masking stage knees. Smoothing suppresses noise rather than producing a pleasant curve. Round off the knee and the yield point can no longer be located, which propagates into calibration. A knee that moves by more than a loading step or two between smoothed and unsmoothed curves means the setting has gone too far.

Fourth, the colour scale stays fixed across the whole test and across batches. A per-frame scale is comfortable to watch, but two maps that look equally dark can differ by a factor of two in strain.

When should you stop and accept that software is not the problem? A few lines are clear.

If the field of view is too small and the specimen leaves the frame, no setting recovers it: there are no pixels outside. If resolution is too low and a subset already spans less than a few cells, the map turns granular and smoothing only blurs it. If the frame rate is too low and a collapse front passes between two frames, the instant was never sampled. If contrast is too low, the information is genuinely absent, not conservatively rejected. If out-of-plane motion is significant with one camera, the bulge is recorded as in-plane strain and no parameter change removes it.

What these cases share is that the needed information never entered the image. Software extracts what is there; it cannot supply what is not. If the raw images do not show the feature, change the field of view, the lens, the lighting, or add a camera.

With the functions understood, the next step is to run a system end to end: specimen and fixturing first, then field of view and light path, parameters last.

## 5. FAQ

**1. Is iterative matching the same as using a large subset?**

No. A large fixed subset covers more area but resolves less, and still cannot follow rotation or shear. Iterative matching changes subset geometry through the test: small early for resolution, larger and reoriented later, which keeps it locked onto the same material patch.

**2. How often should the reference frame be updated?**

As rarely as the data allows, and always at a recorded point. Each update costs a re-alignment and adds a seam to explain. If one reference keeps the curve continuous to the end, there is no reason to update; if tracking fails at a repeatable location, update just before it.

**3. Does ROI averaging hide real defects?**

It can, if the ROI is drawn carelessly. Averaging removes local spikes, including those that indicate a weak zone. Where non-uniformity is expected, split the region into smaller ROIs.

**4. The curve looks smooth but the maps show stripes. Which is right?**

Both, at different scales. The curve averages the region, so a localized band contributes only a fraction of its magnitude; the map shows what the average conceals. Read them together and state which ROI the curve came from.

</details>
