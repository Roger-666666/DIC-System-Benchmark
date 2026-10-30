# 做一次海绵压缩试验要配什么：XTDIC系统构成与配置选择

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 海绵压缩的全场光学测量，效果好坏往往不在算法，而在配置。视场要按试样尺寸和压缩行程一起算，压缩到七成时试样横向外扩，留窄了后半程出画；相机支架与加载框架必须解耦，否则框架变形会被当成试样变形；采集要与试验机绑定步号，否则曲线和云图对不上阶段。本文按“试样—成像—照明—支架—同步—存储”的链路说明每个部件为什么存在、选错会怎样，并给出配置清单与选配规律。

> **关键词：** XTDIC；数字图像相关技术；海绵压缩试验；系统配置；双相机标定；时间同步

## 目录

- [一、从试样到报告：配置这件事先从链路看起](#一从试样到报告配置这件事先从链路看起)
- [二、成像单元：视场由试样和压缩行程一起决定](#二成像单元视场由试样和压缩行程一起决定)
- [三、照明、支架与加载机：三个容易被低估的环节](#三照明支架与加载机三个容易被低估的环节)
- [四、同步、软件与存储：数据怎么对上、存在哪](#四同步软件与存储数据怎么对上存在哪)
- [五、常见问题](#五常见问题)

## 一、从试样到报告：配置这件事先从链路看起

一次海绵压缩的全场测量，流程是这样的：试样放进试验机，相机对准表面，光源照亮表面，试验机压缩，采集软件按设定节奏连续拍摄，图像进入计算，最后输出云图、曲线和报告。中间任何一段配置不当，结果都会打折，而且看不出来——数据照样出，只是某一段不可信。

所以配置的第一步不是挑相机，而是把链路走一遍，看哪一段最容易被削弱。海绵有三个先天条件：软，压缩量大，表面特征弱。软，意味着装夹和支撑的任何一点柔度都会混进结果；压缩量大，意味着视场和景深按终点算；表面特征弱，意味着照明比金属试样更重要。

## 二、成像单元：视场由试样和压缩行程一起决定

视场是最先要定、也最容易定小的参数。常见做法是按原始尺寸框一个刚好包住的视场，但压缩到70%量级时试样横向外扩，边缘先出画。后果不是“少了点数据”，而是ROI在中途被截断，平均应变曲线在平台上出现台阶，看上去像材料变了，其实是视场不够。

正确的算法是：原始尺寸加横向外扩量，再加一圈余量，才是视场下限。景深也要检查——外扩之后表面离镜头更近，景深不够，边缘先虚，虚掉的区域匹配质量下降，云图边缘出现一片噪声。

单相机还是双相机，取决于变形有没有明显的离面分量。有离面位移、有曲面鼓出的场景，双相机是必须的：两台相机从不同角度成像，标定建立三维坐标，解出面外运动，剩下的才是面内应变。只有一台相机时，离面鼓出会被当成面内位移，算出来的应变偏大，鼓得越厉害偏得越多。面内变形为主的小试样，单相机配远心成像够用，蜂窝、发泡塑料这类微孔材料的压缩试验也常属此类。

镜头焦段和分辨率的搭配，本质是在换空间分辨率：同样的视场，分辨率越高，子区覆盖的物理尺寸越小，能分辨的梯度越细，数据量和计算时间也跟着涨。海绵的梯度主要来自泡孔尺度，子区小于几个泡孔就没有物理意义，这一点比分辨率参数更值得先想。

## 三、照明、支架与加载机：三个容易被低估的环节

照明在海绵试验里的分量比金属试样重得多。表面低反射、颜色浅、容易吸光，散斑与基底的对比度天然偏低。对比度不够，匹配置信度就低，云图上出现成片无效点，而这些点往往集中在泡孔被压塌的区域——正好是最需要数据的地方。

蓝光在这类表面上通常比白光好用，短波长在低反射表面的散射更集中，也能压掉一部分反光。但真正决定成败的往往是角度而不是亮度：把光源放到接近侧向的掠射位置，让散斑产生明暗差，比把亮度调高一倍有效。反过来，正面直打、亮度拉满，只有高光成片。

还有一点常被忽略：长时间试验要防光源热漂移。保持阶段动辄几十分钟到几小时，光源发热让试样表面温度上升，海绵对温度敏感，软化会带来额外变形；亮度也会随温度漂移，图像灰度整体偏移，后处理时被误判成变形。低热光源、遮光罩、拉开灯与试样的距离，都是常规做法。

支架是安装环节里最容易出错的一环。相机支架必须与加载框架解耦，独立落地或挂在刚性墙架上。如果共用一套框架，压缩时框架受力变形，几微米到几十微米的位移会直接进入图像序列，被算成试样变形。这种误差相对海绵的真实应变也许不大，但它是系统性的，会让整段曲线的基线缓慢漂移，也没法在后处理里分离出来。

加载机这边还要留意压盘的平行度和对中。压盘不平行，试样一侧先接触，云图上从一开始就是单边受压，第一阶段的“应变维持在0附近”根本不会出现。对中不好，试样在压缩中侧向滑移，出画、失焦、甚至从压盘间挤出，都会发生。

## 四、同步、软件与存储：数据怎么对上、存在哪

同步做与不做，差别很大。采集软件要与试验机做时间或步号绑定，让每一帧对应到具体的加载步和载荷值。没有绑定，手上有一堆图像和一条载荷曲线，却不知道哪张图对应哪个载荷——屈服拐点在哪一帧、云图何时开始出现条带，都只能靠猜。绑定可以用硬件触发，也可以在软件层记录步号，关键是这个对应关系要落到文件里，而不是留在记忆里。

存储要提前算。数据量按“帧数×分辨率×通道”估算：一次压缩拍几百到上千帧，单帧几兆到几十兆，很容易到几十GB。落盘要规划到独立磁盘，写盘速度留余量，缓存写满导致的丢帧往往发生在试验后半程——最有价值的那一段。备份也要有：数据打不开，比没做还难受。

软件这边的重点是“统一”。同一批试验，子区大小、参考帧更新策略、平滑强度、色标范围都应固定并记录。参数随试样改是合理的，但报告里要写清楚改了什么、为什么改，否则两张云图放在一起，差异来自材料还是参数，说不清。

一张配置清单，把上面这些串起来看更清楚。

| 部件 | 作用 | 选错的后果 |
| --- | --- | --- |
| 工业相机（单/双） | 记录表面散斑图像，重建坐标与位移 | 离面鼓出用单相机，面外位移算成面内应变 |
| 镜头与视场 | 覆盖试样外扩后的整个表面 | 按原始尺寸取景，后期边缘出画，曲线出现假台阶 |
| 光源类型 | 提高散斑对比度 | 白光直打，高反光区饱和，泡孔边缘成片无效点 |
| 光源角度与遮光 | 控制入射角，压住镜面反射 | 只调亮度不调角度，图像亮但信息少 |
| 相机支架 | 独立支撑成像单元 | 与加载框架共用，框架变形计入试样 |
| 同步信号 | 把图像帧与加载步、载荷绑定 | 云图与曲线错位，阶段判断整体偏移 |
| 采集与存储 | 长序列连续落盘与备份 | 缓存写满、中途丢帧，后半程数据缺失 |
| 软件参数管理 | 统一子区、参考帧、色标 | 批内不可比，报告无法复现 |

配置不是一套固定答案，它随试样变。小试样、面内变形为主，单相机加远心镜头，视场小、标定简单；大行程的软试样，双相机、视场按1.5倍以上预留、必要时加侧向约束防失稳；深色或高反光海绵，蓝光加侧向掠射，先试拍再看直方图；长时间保持类试验，低热光源、大容量磁盘、适当抽帧，把帧率让给时长。这四条覆盖大部分场景，剩下的靠试拍——先压一小段，看边缘有没有出画、云图有没有大片无效点，比返工便宜。

硬件配齐，只是半台设备。另一半在软件：同样的图像，参数设得对不对，结果可以差出一个量级。

## 五、常见问题

**1. 用一支广角镜头，是不是就不用双相机了？**

广角换视场，代价是空间分辨率，也解决不了离面问题。单相机下鼓出的表面仍会把面外运动投到面内结果里。试样薄、以面内变形为主时，广角加远心可以应付；只要有明显鼓出，两台相机就绕不过去。

**2. 视场要留多少余量？**

够试样在整个行程内都不出画，压到底时四周还能看到一圈边界，边缘散斑仍可追踪。具体留多少跟海绵密度、侧向约束有关，与其套经验值，不如看一次试拍的最后一帧。

**3. 云图和曲线在时间上对不上，问题出在哪？**

多半是采集与试验机之间没有记录时间或步号绑定。也可能是采集间隔用软件定时器而不是触发信号，长试验里累积了漂移。查一下文件里有没有步号或时间戳列，第一帧是否对应接触那一刻。

**4. 试验机很刚，共用支架也会有问题吗？**

刚度只减小幅值，不改变机理。刚性框架受载仍会变形，让相机相对试样沿加载方向移动，随载荷累积，不是随机噪声，会把整段应变历史往一个方向带偏。独立支撑把这条路径直接断掉，比事后修正省事。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Configuring a Sponge Compression Test: What an XTDIC System Is Made Of

> **Abstract:** In full-field optical measurement of foam compression, the outcome usually depends less on the algorithm than on the configuration. The field of view has to be sized from the specimen plus its compression stroke, because at seventy percent the specimen spreads laterally and leaves the frame if the margin is tight. The camera support must be decoupled from the loading frame, or frame deflection is recorded as specimen strain. Acquisition must be tied to loading steps, or curves and maps drift out of register. This article walks the chain from specimen to report, component by component, and closes with a configuration checklist and rules for matching the setup to the specimen.

> **Keywords:** XTDIC; digital image correlation; foam compression test; system configuration; stereo calibration; time synchronization

## Contents

- [1. From specimen to report: start with the chain](#1-from-specimen-to-report-start-with-the-chain)
- [2. Imaging: the field of view comes from specimen plus stroke](#2-imaging-the-field-of-view-comes-from-specimen-plus-stroke)
- [3. Lighting, support and the loading frame](#3-lighting-support-and-the-loading-frame)
- [4. Synchronization, software and storage](#4-synchronization-software-and-storage)
- [5. FAQ](#5-faq)

## 1. From specimen to report: start with the chain

A full-field measurement runs like this: the specimen goes into the machine, cameras aim at its surface, a source lights it, the machine compresses, software captures a continuous sequence, and maps, curves and a report come out. Any weak link degrades the result quietly: the data appears, one segment is simply not trustworthy.

Configuration therefore starts by walking the chain and asking where the signal is weakest. Foam brings three conditions: it is soft, so compliance in fixturing leaks into the result; it compresses far, so field and depth of field are sized for the end of the stroke; its surface is feature-poor, so lighting matters more than on metal.

## 2. Imaging: the field of view comes from specimen plus stroke

The field of view is fixed first and set too small most often. The habit is to frame the original outline snugly, which looks tidy until the specimen spreads out of frame at seventy percent. Then the region of interest is clipped halfway, the averaged curve steps on the plateau, and a framing problem reads as a change in the material.

Take the original dimension, add the lateral expansion expected from compression, add a margin, and treat that as the lower bound. Depth of field needs the same care: after expansion the surface sits closer to the lens, edges go soft, matching degrades and noise appears along the map boundary.

One camera or two depends on the out-of-plane content. With bulging and a curved surface, two cameras are required: they image from different angles, calibration gives three-dimensional coordinates, and out-of-plane motion is separated from in-plane strain. One camera reads the bulge as in-plane movement, so strain runs high, and the more it bulges the worse the error. Small specimens dominated by in-plane deformation do well with one camera and telecentric imaging, and honeycomb, foamed plastics and nonwoven tests often fall into that case.

Lens and sensor set spatial resolution: at a fixed field, higher resolution means a smaller physical area per subset and finer gradients, at a cost in data and computation. On foam the gradients live at the cell scale, so a subset smaller than a few cells means nothing — settle that before comparing resolution figures.

## 3. Lighting, support and the loading frame

Lighting matters far more on foam than on metal. The surface reflects little, is light in colour and absorbs light, so speckle-to-substrate contrast is naturally low. Low contrast lowers matching confidence, and patches of invalid points appear exactly where cells have collapsed.

Blue light generally beats white here: the shorter wavelength scatters more tightly and suppresses some specular reflection. Angle decides success more than brightness — a grazing source that gives speckles light and shadow beats doubling the intensity. Frontal light at full power yields blown highlights and dead white cell edges.

Long holds also need protection from thermal drift. Holding runs from tens of minutes to hours, the source heats the surface, foam softens and extra deformation appears; brightness drifts too, shifting grey levels that post-processing reads as strain. Low-heat sources, shielding and greater distance are standard.

The camera support is the most error-prone part. It must be decoupled from the loading frame, on its own feet or an independent rigid mount. Sharing one frame lets deflection under load enter the sequence as specimen deformation. The magnitude may look small against foam strain, but the error is systematic: it drifts the whole baseline and cannot be separated afterwards.

On the loading side, platen parallelism and alignment matter. A non-parallel platen contacts one side first, so the map shows one-sided compression and the flat first stage never appears. Poor alignment lets the specimen slide, leave the frame or squeeze out.

## 4. Synchronization, software and storage

Synchronization makes a large difference. Acquisition should be tied to the machine by time or loading step, so each frame maps to a step and a load. Without it you hold images and a curve with no way to pair them: where the yield knee falls, when the band first appears, all guesswork. A hardware trigger or a software step record will do, but the correspondence belongs in the file, not in memory.

Storage needs planning: frames times resolution times channels. Hundreds to over a thousand frames per test, a few to tens of megabytes each, easily tens of gigabytes. Write to a dedicated disk with speed headroom, because dropped frames tend to hit the second half — the valuable part. Backups too: a dataset that will not open is worse than no test.

In software the priority is consistency: across a batch, subset size, reference policy, smoothing and colour scale are fixed and recorded. Changing parameters per specimen is legitimate, but the report must say what changed and why, or two maps give no way to separate material from settings.

The checklist below pulls these threads together.

| Component | Function | Consequence of a wrong choice |
| --- | --- | --- |
| Industrial camera (one or two) | Records speckle images, reconstructs coordinates and displacement | Bulge measured with one camera becomes in-plane strain |
| Lens and field of view | Covers the surface after lateral expansion | Original-size framing lets edges leave; false steps in the curve |
| Light source type | Raises speckle contrast | Direct white light saturates reflective areas; invalid patches |
| Source angle and shielding | Controls incidence, suppresses specular reflection | Brightness only: bright images, little information |
| Camera support | Independent mounting of the imaging unit | Shared with the frame, deflection counted as specimen strain |
| Synchronization signal | Binds frames to loading steps and load values | Maps and curves misregister; stage boundaries shift |
| Acquisition and storage | Continuous writing and backup of long sequences | Buffer overrun, dropped frames, missing second half |
| Software parameter control | Consistent subset, reference frame, colour scale | Batch results not comparable; report not reproducible |

Configuration follows the specimen. Small in-plane specimens suit one camera and a telecentric lens. Long-stroke soft specimens call for two cameras, a field reserved at 1.5 times or more, and lateral restraint against buckling. Dark or reflective foam calls for blue light at a grazing angle, checked against the histogram. Long holds call for low-heat sources, a large disk and deliberate frame skipping.

These patterns cover most foam work. The rest is a trial run: compress a short segment and check whether edges leave the frame or invalid regions appear.

Hardware is half a system. The other half is software: from the same images, the right settings and the wrong ones differ by an order of magnitude.

## 5. FAQ

**1. Can I just use a wider lens instead of two cameras?**

A wider lens buys field of view at the cost of resolution and does not solve the out-of-plane problem. With one camera, a bulging surface still projects that motion into the in-plane result. Thin specimens dominated by in-plane deformation can be handled by a wide lens with telecentric imaging; if they bulge, two cameras are the answer.

**2. How much margin should the field of view carry?**

Enough that the specimen stays inside the frame through the full stroke, with a visible border at maximum compression and speckle near the edges still trackable. Checking the last frame of a trial capture beats any rule of thumb.

**3. The frame and the curve do not line up in time. What went wrong?**

Most likely no step or time binding was recorded between acquisition and the machine. Alternatively the interval came from a software timer rather than a trigger, and drift accumulated. Check for a step-number or timestamp column, and whether the first frame matches contact.

**4. Is a shared support frame really a problem if the machine is stiff?**

Stiffness reduces the magnitude, not the mechanism. A stiff frame under load still deflects, moving the camera relative to the specimen along the loading axis. Since it accumulates with load rather than appearing as noise, it biases the whole strain history in one direction. Independent support removes the path entirely.

</details>
