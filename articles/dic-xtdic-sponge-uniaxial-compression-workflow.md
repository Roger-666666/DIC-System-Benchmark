# 从制斑到报告：XTDIC海绵单轴压缩试验的设备作业流程

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 海绵单轴压缩的变形量能到七成量级，散斑随泡孔坍塌剧烈挤压畸变，常规相关容易在中途失配断掉。本文按时间顺序拆开一套完整作业流程：制斑、装夹、光路、标定、同步采集、数据处理与出图报告，每一步说明做什么、为什么这样做、做错会在结果里留下什么痕迹，并附一份可直接使用的检查清单。

> **关键词：** XTDIC；数字图像相关技术；海绵压缩；散斑制备；标定；加载同步；应变云图

## 目录

- [一、作业总览](#一作业总览)
- [二、制斑与试样准备](#二制斑与试样准备)
- [三、装夹与光路](#三装夹与光路)
- [四、标定](#四标定)
- [五、同步与采集](#五同步与采集)
- [六、数据处理](#六数据处理)
- [七、出图与报告](#七出图与报告)
- [八、检查清单](#八检查清单)
- [九、常见问题](#九常见问题)

## 一、作业总览

海绵做单轴压缩，第一印象是“软”。真做起来难点在另一头：压缩量能到七成量级，方正的样件被压成薄片，表面泡孔成片坍塌，散斑跟着剧烈挤压。常规匹配走到中途容易跟丢，图像对不上，计算断在那里，前面的加载等于白做。

要拿到的不是一张压扁的照片，而是整个加载过程中连续的表面应变场，并且让不同加载步的数据接得上。XTDIC三维应变测量系统承担的正是这件事：大变形阶段靠迭代匹配跟着形变走，子区大小与姿态随形变调整；变形累积后更新参考基准，用动态参考帧分段承接；再对感兴趣区域做空间平均压掉局部噪点，输出全域应变分布。覆盖范围从初始接触、泡孔屈曲坍塌到致密化前期。

流程拆成七段，前后有依赖，前一段的输出就是后一段的输入：散斑做坏了，标定再准也救不回来；参考帧选错了，曲线再平滑也是错的起点；加载步号和图像帧没绑上，阶段划分只能靠猜。

| 步骤 | 这一步要解决的问题 | 留下的记录 |
| --- | --- | --- |
| 制斑 | 斑点随表面变形 | 加载前的静态序列 |
| 装夹 | 受压均匀、视场够用 | 试样尺寸与预压值 |
| 光路 | 两台相机看得清 | 站位与角度 |
| 标定 | 像素换成毫米 | 标定文件与复检 |
| 同步 | 帧与加载步对得上 | 加载步对照表 |
| 处理 | 图像变成应变场 | ROI、参考帧与参数 |
| 出图 | 结果能被复核 | 统一色标的图与曲线 |

## 二、制斑与试样准备

海绵表面软、反光低、还吸光，三条凑在一起，制斑的容错空间比金属件小得多。颗粒如果只浮在表面，压缩一开始就跟着泡孔一起裂、翘边、脱落，那些区域后面全是空洞。散斑要能随表面一起变形，这比斑点是否均匀更重要。

先把表面清理干净，脱模剂残留和浮尘都要去掉；喷涂时距离拉开，薄薄地分多层上，让颗粒嵌进表层而不是堆成一层壳。判断合格不看“看起来匀不匀”，看加载前的静态序列：对比度够不够，边缘清不清晰，有没有成片过曝或者死黑。

颗粒尺度要和视场、子区一起考虑。视场大、子区给得大，斑点也要跟着大；颗粒细到只有几个像素，压缩时泡孔一挤，斑点糊成噪声，匹配就退化成猜。试样切割面要平、上下平行，厚度留出余量，别让上下表面直接压到压盘。

## 三、装夹与光路

装夹看着是体力活，其实决定了后面数据好不好读。压盘与试样的接触面要平整、试样居中，初始偏心会让一侧先进入压密，云图上出现单边高应变。海绵有回弹，放上去先给一点预压让它贴合，再清零。

视场要预留横向外扩的余量。压缩中试样会明显变宽，按初始尺寸卡着取景，压到后半程边缘就跑出画面，应变场缺一块，那一侧的数据等于没有。

光路上，两台相机的光轴要垂直于试样表面，夹角按视场大小来定：视场大、距离远，夹角可以小些；视场小、距离近，夹角要相应打开，否则深度方向的解算精度不够。光源角度比亮度更值得花时间：表面随压缩起皱，高光位置一直在动，落在感兴趣区里就会让那片匹配变差。把灯压低、斜打，让高光避开测量区。

## 四、标定

标定决定图像里的像素怎么变成毫米。标定板要覆盖整个测量视场，四角和中心都进画面，还要包含实际工作的景深范围——压缩时表面会前后移动，单平面标定在深度方向会偏。

标定完不要立刻开压，先做复检：静止状态连续采一段，看位移场有没有漂移、边角残差是否偏大。有漂移先查相机有没有被碰、支架是否稳固、环境光是否在变，别先怀疑算法。标定文件按批次命名，与图像存在一起。

## 五、同步与采集

动作很简单：把加载步号或者触发信号和图像帧绑定，逐级记录。这是后面所有阶段划分的前提。没有绑定，你只知道拍了一堆图，不知道哪张对应哪一级荷载，划三段只能靠猜。

采集参数上，帧率要跟上加载节奏。屈服段来得快，应变在很短的加载区间里从接近零冲到三成，帧率不够就会漏掉拐点。采集时长和存储也要控制，全程密采文件很大，稳妥的是关键阶段密采、平稳段稀疏采，并写明每段间隔。

## 六、数据处理

处理的第一步不是点开始，而是定两件事：感兴趣区域和参考帧。ROI 贴住试样表面，避开夹持边缘和高光区；参考帧取加载前的静止状态，后面所有应变都相对于它。

海绵压缩的特殊性在于变形量太大。常规相关在子区形变超过一定比例后失相关，表现为计算中断、图上一片空洞。大变形迭代匹配让子区跟着泡孔挤压一起调整；变形累积较大时再更新基准，用动态参考帧把长过程切成几段承接。泡孔随机破裂带来离散噪点，单点跳变没有物理意义，用 ROI 区域平均做空间过滤，压掉局部噪点、保留整体趋势。

处理中要盯失配率和空洞分布，不只曲线顺不顺眼。某一段失配率突然升高，多半是那一帧有反光、遮挡或试样出画，这时候该回去查原始图像，而不是加大平滑把问题抹平。

## 七、出图与报告

出图有两件事容易出错：色标和配对。色标全程统一，同一批云图用同一个上下限。曲线和云图要成对出现：只给曲线看不出哪里先变形，只给云图看不出整体走到哪一步。

报告里至少交代清楚：参考状态、色标范围和单位、ROI 边界、阶段怎么划分、关键加载步各一张云图。这几项写清楚，别人拿到报告能自己复核。数据文件与处理参数一并归档，半年后重算还能复现同一张图。

## 八、检查清单

每一步最好留一个能勾选的检查点。

| 阶段 | 检查项 | 不通过时的典型表现 |
| --- | --- | --- |
| 制斑 | 静态序列的对比度与清晰度 | 斑点糊成一片，初期出现大片空洞 |
| 装夹 | 试样居中、接触面贴合、预压后清零 | 云图单边高应变，一侧先被压密 |
| 取景 | 横向预留外扩余量 | 后半程边缘出画，应变场缺角 |
| 光路 | 光轴垂直、夹角匹配视场、高光避开 ROI | 边缘匹配差，深度解算偏差偏大 |
| 标定 | 覆盖全视场与景深、复检无漂移 | 静止时位移场漂移，边角残差偏大 |
| 同步 | 加载步号与图像帧一一绑定 | 阶段划分只能猜，拐点位置说不清 |
| 处理 | 参考帧、ROI、失配率与空洞分布 | 曲线平滑但云图出现孤立极值 |
| 出图 | 色标统一、曲线与云图成对 | 颜色不可比，结论无法复核 |

这张表跑顺了，流程这一层就稳了。接下来难点换了位置：设备给出的是两类结果，一条 ROI 平均曲线、一组全场云图，怎么读成一句可靠的话，是另一件事。

## 九、常见问题

**1. 制斑能不能直接拿喷漆代替专用散斑？**

能用，但要先验证。喷漆容易在软表面形成一层连续的膜，压缩时整片开裂脱落，反而不如颗粒嵌进表层的做法稳。不管用什么材料，判断标准都是加载前那段静态序列的对比度与清晰度，以及压缩前几级有没有出现成片空洞。

**2. 压到后半程试样出画了，能补拍吗？**

补不了。压缩不可逆，卸载后再压一次，泡孔结构已变，两条曲线对不上。只能在取景阶段留出余量，把试样在画面里放小一点。

**3. 大变形阶段参考帧要频繁更新吗？**

不需要频繁，但要在匹配开始变差之前换一次。更新的节点要记录，否则前后两段的应变基准不一致，曲线会出现莫名的台阶。

**4. 曲线很平滑，是不是说明数据没问题？**

平滑只说明噪点少，不说明数据对。参考帧错、ROI 划到了背景、色标被拉伸，这些都能给出很平滑的曲线。要拿云图去交叉验证，看同一加载步的量级是否自洽。

**5. 一次试验采多少张图够用？**

不按张数定，按阶段定。屈服段要密，平台段可以稀，关键是让每个加载步都有对应的帧。采集前先按加载步列一张对照表。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From Speckle to Report: An Equipment Workflow for Uniaxial Compression Testing of Sponge with XTDIC

> **Abstract:** Sponge compresses by as much as seventy percent, and the speckle pattern is squeezed and distorted as cell walls collapse, so conventional correlation tends to lose the track halfway through. This article walks through the workflow in time order: speckle preparation, fixturing, optical layout, calibration, synchronised acquisition, processing and reporting. Each step covers what is done, why it matters and what a mistake leaves behind, followed by a checklist that can be used directly.

> **Keywords:** XTDIC; digital image correlation; sponge compression; speckle preparation; calibration; load synchronisation; strain contour

## Contents

- [1. Overview of the job](#1-overview-of-the-job)
- [2. Speckle and specimen preparation](#2-speckle-and-specimen-preparation)
- [3. Fixturing and optical layout](#3-fixturing-and-optical-layout)
- [4. Calibration](#4-calibration)
- [5. Synchronisation and acquisition](#5-synchronisation-and-acquisition)
- [6. Data processing](#6-data-processing)
- [7. Figures and reporting](#7-figures-and-reporting)
- [8. Checklist](#8-checklist)
- [9. FAQ](#9-faq)

## 1. Overview of the job

Compressing a sponge looks easy. It is not: compression reaches seventy percent or so, a squat specimen becomes a thin sheet, and the speckle is squeezed as cells collapse. Conventional matching loses the track halfway and the loading is wasted.

What the job delivers is a continuous surface strain field across the loading history, with load steps that connect. XTDIC, a three-dimensional strain measurement system, does this by iterative matching that adapts subset size and orientation, by renewing the reference so a dynamic reference frame carries the process in segments, and by averaging over a region of interest to suppress local noise. Coverage runs from first contact to early densification.

The workflow has seven parts, each depending on the one before: bad speckle defeats calibration, a wrong reference makes a smooth curve meaningless, unbound steps leave the stage division to guesswork.

| Step | What it settles | Record left behind |
| --- | --- | --- |
| Speckle | Pattern deforms with the surface | Static check sequence before loading |
| Fixturing | Even loading, enough field | Specimen size and preload value |
| Optics | Both cameras see clearly | Station and angle description |
| Calibration | Pixels become millimetres | Calibration file and re-check result |
| Synchronisation | Frames match load steps | Load-step mapping table |
| Processing | Images become a strain field | ROI, reference and settings |
| Figures | Results others can check | Plots and curves on one colour scale |

## 2. Speckle and specimen preparation

Sponge is soft, weakly reflective and absorptive, leaving less margin than metal. Particles that sit on the surface rather than in it crack, curl and flake off as cells collapse, and those areas become gaps. The pattern must deform with the surface, which matters more than evenness.

Clean the surface first, removing release agent residue and loose dust. Spray from further away in thin layers so particles settle in rather than forming a shell. Judge the result from a short static sequence before loading: contrast, edge sharpness, patches of blowout or dead black.

Particle size follows field of view and subset size: a large field means large subsets and larger dots, while dots a few pixels across blur into noise once cells are squeezed. Coarser dots are safer. Cut faces flat, top and bottom parallel, with enough thickness that the platens never meet early.

## 3. Fixturing and optical layout

Fixturing decides how readable the data will be. Platen and specimen meet on a flat face with the specimen centred; an offset lets one side densify first, producing a one-sided high-strain band that reads as material non-uniformity. Sponge springs back, so apply a small preload to seat it, then zero.

Leave lateral margin in the field: the specimen widens noticeably, and framing the initial outline pushes the edges out of frame later, leaving one side missing.

Both camera axes should be normal to the surface, and the angle between them follows the field: wide and distant allows a smaller angle, close and narrow needs a wider one or depth resolution suffers. Light angle matters more than level: the surface wrinkles and the highlight moves, and if it lands inside the ROI, matching degrades. Lower the lamps and rake the light away.

## 4. Calibration

Calibration converts pixels into millimetres. The target must cover the whole field, corners and centre included, and span the working depth of field, since the surface moves towards and away from the cameras. A single-plane calibration leaves a depth bias.

Do not start loading straight after calibration. Take a static sequence and check for drift in the displacement field and growing edge residuals. If it drifts, check for a bumped camera, a loose mount or changing ambient light before suspecting the algorithm.

## 5. Synchronisation and acquisition

The action is simple: bind the load step number or trigger signal to image frames and record it step by step. It is the precondition for every later stage division. Without it you know only that images exist, not which load each belongs to.

Frame rate has to keep up with the loading: the yield stage arrives quickly, with strain rising from near zero to about thirty percent, and a low rate misses the knee. Dense capture throughout makes very large files, so capture densely in critical stages, sparsely on the plateau, and record the intervals.

## 6. Data processing

Processing starts with two decisions, not with the run button: the region of interest and the reference frame. The ROI sits on the surface, clear of grips and specular zone; the reference is the static state before loading, and every strain is relative to it.

The difficulty with sponge is the size of the deformation. Conventional correlation decorrelates once subset distortion passes a certain level, showing up as interrupted computation and holes in the map. Iterative matching keeps subsets with the collapsing cells, and once distortion accumulates the reference is renewed. Random cell rupture adds discrete noise, so ROI averaging filters it while keeping the trend.

Watch the mismatch rate and gap distribution, not only whether the curve looks tidy. A sudden rise usually means glare, obstruction or the specimen leaving the frame: go back to the raw images.

## 7. Figures and reporting

Two things go wrong in figures: colour scale and pairing. Fix the scale across the dataset, with identical limits on every contour. Curves and contours belong together: a curve alone shows no location, a contour alone shows no stage.

A report should state the reference state, colour limits and units, the ROI boundary, the basis for the stage division, and one contour per key load step, so a reader can check the work rather than accept the conclusion. Archive data with the settings.

## 8. Checklist

A run is not finished when the last frame is saved. The table below works as a bench check.

| Stage | Check | Typical symptom when it fails |
| --- | --- | --- |
| Speckle | Contrast and edge sharpness | Pattern blurs, gaps appear early |
| Fixturing | Centred, flat contact, zeroed after preload | One-sided high strain, one side densifies first |
| Framing | Lateral margin reserved | Edges leave the frame, field truncated |
| Optics | Normal axes, angle matched to field, highlight outside ROI | Poor matching at edges, depth bias |
| Calibration | Full field and depth, clean re-check | Field drifts at rest, edge residuals large |
| Synchronisation | Load step bound to frame index | Stage division guessed, knee unclear |
| Processing | Reference, ROI, mismatch rate, gaps | Smooth curve but isolated extremes |
| Figures | Fixed scale, curve paired with contour | Colours incomparable, conclusions unverifiable |

With this table clean, the workflow layer is settled. The next difficulty is different: the system gives an ROI curve and a set of contours, and reading them into one defensible sentence is a separate skill.

## 9. FAQ

**1. Can ordinary spray paint replace a dedicated speckle pattern?**

It can, but verify it first. Paint tends to form a continuous film on a soft surface, which cracks and peels during compression and is less stable than particles settled into the surface. Whatever the material, the test is the same: contrast and sharpness in the static sequence, and whether gaps appear early.

**2. The specimen left the frame in the second half. Can the run be repeated and joined?**

No. Compression is irreversible; unloading and reloading changes the cell structure, and the two curves will not match. The only fix is at the framing stage, with the specimen made smaller in the image.

**3. Should the reference frame be updated often during large deformation?**

Not often, but once before matching starts to degrade. Record the point of update, otherwise the two segments rest on different baselines and the curve shows an unexplained step.

**4. The curve is very smooth. Does that mean the data are sound?**

Smoothness means low noise, not correctness. A wrong reference, an ROI that includes background, or a stretched colour scale all produce smooth curves. Cross-check against the contour at the same load step.

**5. How many images should one test capture?**

Decide by stage, not by count. Capture densely through yield and sparsely on the plateau, and make sure every load step has a frame. A load-step table prepared beforehand beats counting images afterwards.

</details>
