# 岩土相似模型散斑怎么做？3D-XTDIC制斑、子区选择与数据空洞控制

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 岩土相似材料表面非均质、粗糙且可能剥落，金属表面的制斑与子区经验不能直接照搬。本文给出随机高对比散斑、灰度与清晰度检查清单，区分子区大小和计算间距的作用，并说明裂隙边缘、观测窗反光及数据空洞的处理边界，强调局部补算不等于恢复真实测量。

> **关键词：** 3D-XTDIC；数字图像相关技术；相似材料模型；散斑制作；子区选择；数据空洞

## 目录

- [一、直接答案：先让表面可追踪，再讨论计算参数](#一直接答案先让表面可追踪再讨论计算参数)
- [二、公开依据：试验条件用于确定观测约束](#二公开依据试验条件用于确定观测约束)
- [三、参数表：子区大小与间距分别控制什么](#三参数表子区大小与间距分别控制什么)
- [四、适用场景与数据空洞检查清单](#四适用场景与数据空洞检查清单)
- [五、常见问题](#五常见问题)

## 一、直接答案：先让表面可追踪，再讨论计算参数

岩土相似模型的散斑制作，核心不是把斑点做得越密越好，而是在不显著改变表面响应的前提下，形成随机、高对比、尺度合适且附着稳定的纹理。数字图像相关技术依赖子区内的灰度模式进行匹配，若纹理随颗粒剥落、开裂或受潮发生变化，算法可能把纹理变化误识别为变形，也可能直接失配。

金属表面常见的均匀底漆与细喷点流程，不能不加判断地移植到分层岩土材料。模型表面可能存在孔隙、松散颗粒、层理和局部凸起，过厚涂层可能桥接细小裂隙或改变剥落形态，过强按压又可能扰动表层。因此，3D-XTDIC制斑应先做小范围工艺试验，观察附着、干燥和加载后的纹理状态，再确定正式处理方式。

### 1.1 制斑与拍摄检查清单

制斑后可按以下顺序检查，而不是只凭肉眼判断“斑点够不够多”：

- **随机性：** 斑点大小和分布避免规则排列，子区内不应只有单一方向条纹。
- **对比度：** 亮暗差异清晰，但亮部不过曝、暗部仍有层次，不能以极高对比牺牲灰度信息。
- **尺度与覆盖率：** 斑点相对子区不能过粗或过细，关注区内应有连续可追踪纹理，边界和层理附近也要覆盖。
- **清晰度：** 双相机图像均需检查对焦、运动模糊与视角差异，不能只观察其中一幅。
- **附着状态：** 加载前及各级加载后检查起皮、脱落、掉粉和新遮挡，保留对应阶段的原始图像。
- **光照稳定性：** 避免曝光随工序变化，透明观测窗还要检查反射光斑是否覆盖关键区域。

## 二、公开依据：试验条件用于确定观测约束

分层岩土地铁隧道相似模型的观测对象具有非均质、层理明显和局部易损等特点。此类表面需要同时照顾整体变形追踪与裂隙附近的不连续性：整体区域希望匹配稳定，裂隙区域则要避免把两侧独立运动强行计算成连续位移。制斑与子区设置应围绕这两个目标协调，而不是追求单一参数。

另一个公开的大尺寸模型加载试验，可用于说明观测尺度对准备工作的影响。该模型为2 m×3 m，观测视场约2 m，采用液压逐级加载和双相机采集。这些条件意味着制斑检查需要覆盖较大的表面，并在逐级加载之间持续关注纹理与光照状态。观测尺度扩大后，制斑结论仍应限定在该模型的表面材料和加载条件内。

### 2.1 大视场下仍要保留局部纹理判断

视场扩大后，图像中同样大小的物理斑点会占用更少像素，局部离焦、照明不均和表面倾角的影响也更容易被忽视。可在中心、边缘、层理交界和预期裂隙区分别截取图像检查，而不是仅查看全图缩略图。若调整喷涂尺度或补光，应记录调整发生的加载阶段，避免跨阶段比较时遗漏成像条件变化。

## 三、参数表：子区大小与间距分别控制什么

子区大小决定一次相关计算使用多少局部灰度信息，计算间距决定相邻计算位置相隔多远。二者是独立参数：缩小间距会增加测点密度，但不会自动提高单点匹配的稳定性；增大子区可能改善灰度匹配，却会把更大的物理区域纳入同一次位移估计。

| 参数或状态 | 主要作用 | 可能出现的迹象 | 调整与复核方向 |
| --- | --- | --- | --- |
| 较大的子区 | 纳入更多灰度特征，通常有助于稳定匹配 | 裂隙边缘位移被平滑，局部集中区变宽 | 在连续区评估是否过平滑，与较小子区结果对照 |
| 较小的子区 | 提高局部变化的空间分辨能力 | 弱纹理区更易失配，位移噪声可能增加 | 检查子区内有效斑点与灰度层次，不宜只追求更小 |
| 较小的计算间距 | 增加输出点密度，细化云图表达 | 数据量和计算量增加，相邻点仍可能高度相关 | 与关注尺度配合，不能把点密等同于独立信息增多 |
| 较大的计算间距 | 减少计算位置，便于快速检查整体趋势 | 细小集中区可能被跳过，边界表达变粗 | 检查裂隙和层理附近是否需要更密计算 |
| 裂隙或剥落边缘 | 表面连续性及纹理可能发生变化 | 相关失配、异常矢量、局部空洞 | 分区计算或屏蔽无效区，保留裂隙两侧的不连续性 |

参数选择宜通过同一图像序列的对照计算完成。可选取整体连续区、弱纹理区和裂隙邻近区，比较匹配状态、位移连续性及空洞分布。对于不同尺度区域，也可采用分区参数，但需在结果中保留区域边界和设置记录，避免把参数差异误当成材料响应差异。

## 四、适用场景与数据空洞检查清单

数据空洞是观测或计算状态的结果，不应默认用插值填满。常见原因包括纹理脱落、遮挡、反光、离焦、裂隙导致的不连续匹配，以及点超出有效视场。处理前先按原因分类：成像问题应回查图像和光照，表面破坏应保留其物理位置，算法失配则可通过参数对照判断是否改善。

### 4.1 局部插值补算的边界

在已判定为连续变形的区域内，对少量孤立无效点进行局部插值补算，可用于改善云图连续性或后续显示。补算值来自邻近有效数据，不是新观测，也不等于恢复了真实测量。原始空洞掩膜、补算范围和后续导出数据应一并保留。裂隙两侧、剥落区、遮挡区或大面积连续失配区，不宜直接跨区插值，否则可能抹去位移间断或制造不存在的变形路径。

透明观测窗还会引入反光、附着和表面状态差异。窗面反射可能随加载或光线变化移动，使匹配纹理并非完全来自模型；窗与模型之间若出现脱开、局部空隙或附着颗粒，也可能改变可见表面。可调整照明与视角、检查反射区域，并区分窗面纹理和模型纹理。若无法确认图像特征来自模型，应将相关区域标记为受限数据，而非强行计算。

### 4.2 全流程复核顺序

正式分析前，可依次核对原始图像、散斑覆盖、灰度与清晰度、相关状态、子区和间距设置、空洞掩膜及补算记录。全场应变测量由位移场进一步计算，对局部噪声和空间平滑较敏感，因此位移空洞的处理方式还应与应变解释保持一致。裂隙附近的应变集中可用于定位关注区，但不能仅凭一条高应变带就判定完整裂纹形态。

当散斑、子区和空洞处理都有明确记录后，全过程数据才适合用于阶段分析。下一篇将以混凝土缩尺梁四点弯曲为对象，把位移、剪应变和裂纹演化放到同一时间轴解读。

## 五、常见问题

**1. 岩土模型表面的散斑越密越好吗？**

不是。斑点尺度应与图像分辨率、子区大小和关注变形尺度协调。过密可能在成像后失去灰度层次，过疏则可能减少子区内的有效特征。

**2. 缩小计算间距能否弥补子区过大？**

不能。间距只改变计算位置密度，子区内被平均的物理区域并不会因此缩小。两个参数需要分别检查。

**3. 裂隙边缘出现空洞，是否说明试验数据不可用？**

不一定。空洞可能反映裂隙引起的不连续，也可能来自失配、反光或剥落。应先分类，并保留裂隙两侧有效数据及其边界。

**4. 插值后的空洞区域可以用于定量分析吗？**

应谨慎。补算值依赖邻近数据，并非独立测量。用于显示或后续计算时，应标明范围，且不宜跨裂隙或大失配区补算。

**5. 透明观测窗内的反光可以直接当作散斑吗？**

不宜。反光可能随视角和光照移动，不一定跟随模型表面变形，应优先改善照明与观测条件并核查纹理来源。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Speckle Preparation for Geotechnical Similar-Material Models: 3D-XTDIC Patterning, Subset Selection, and Data-Gap Control

> **Abstract:** Geotechnical similar-material surfaces are heterogeneous, rough, and sometimes friable, so speckle and subset practices used on metal specimens cannot simply be transferred. This article provides a practical checklist for random, high-contrast patterns, gray-level quality, focus, coverage, adhesion, and illumination. It separates the roles of subset size and subset spacing, explains why denser output points do not necessarily add independent information, and reviews crack edges, spalling, reflective observation windows, and correlation loss. It also defines narrow conditions for local interpolation, emphasizing that filled values are derived estimates rather than recovered measurements. The workflow is intended to keep full-field displacement and strain interpretation traceable to image quality and processing decisions.

> **Keywords:** 3D-XTDIC; digital image correlation; similar-material model; speckle pattern; subset selection; data gaps

## Contents

- [1. Direct answer: make the surface trackable before tuning the analysis](#1-direct-answer-make-the-surface-trackable-before-tuning-the-analysis)
- [2. What the available test conditions establish](#2-what-the-available-test-conditions-establish)
- [3. Parameter guide: subset size and spacing do different jobs](#3-parameter-guide-subset-size-and-spacing-do-different-jobs)
- [4. Application checklist and the limits of gap filling](#4-application-checklist-and-the-limits-of-gap-filling)
- [5. FAQ](#5-faq)

## 1. Direct answer: make the surface trackable before tuning the analysis

Speckling a geotechnical similar-material model should create a random, high-contrast texture with suitable feature scale and stable adhesion, not simply the densest pattern. Digital image correlation tracks gray-scale patterns inside subsets. Particle loss, cracking, moisture, or coating failure can make texture changes look like deformation or cause matching loss.

A metal-specimen primer-and-spray routine should not be transferred automatically to layered soil or rock analogues containing pores, loose grains, and bedding interfaces. Thick coatings may bridge fine cracks or alter spalling, while pressing may disturb the surface. A small preparation trial should be checked after application, drying, and representative loading for adhesion and trackability.

### 1.1 A practical pattern and image checklist

A visual impression that the surface contains “enough dots” is not an adequate inspection. The following checks are more useful:

- **Randomness:** avoid regularly spaced dots or one-directional stripes that leave subsets with ambiguous patterns.
- **Contrast:** retain distinct dark and bright features without saturating the highlights or crushing the dark regions into a single level.
- **Feature scale and coverage:** features should be compatible with the subset size and image scale. Coverage should extend across layer boundaries, edges, and likely crack zones.
- **Focus:** inspect images from both cameras, since acceptable sharpness in one view does not establish sharpness in the other.
- **Adhesion:** inspect peeling, powder loss, detached texture, and new occlusions before loading and between load stages.
- **Illumination:** keep exposure conditions consistent and check whether reflections from a transparent observation window cover areas of interest.

These checks should be documented by stage. A later comparison of displacement fields is difficult to interpret if the surface texture or lighting changed without a corresponding record.

## 2. What the available test conditions establish

A layered geotechnical model used for metro-tunnel research presents two competing measurement needs. Continuous regions require stable tracking of the overall deformation, while crack neighborhoods require the analysis to retain possible displacement discontinuities. A pattern and subset arrangement should support both aims rather than optimize one contour map at the expense of the other.

A separate, publicly described large-model test provides scale context. The model was 2 m by 3 m, the observed field approximately 2 m, hydraulic loading was staged, and two cameras acquired images. Pattern inspection therefore needed to cover a broad surface, with repeated lighting and texture checks. Pattern preparation conclusions should remain bounded by that model's surface material and loading conditions.

### 2.1 A large field of view still requires local inspection

In a larger field of view, each physical speckle occupies fewer pixels, and local defocus or uneven illumination is harder to see in a thumbnail. Inspect patches at the center, edges, layer interfaces, and anticipated crack zones. Log any spray-scale or lighting change by load stage so comparisons do not cross an unrecorded imaging change.

## 3. Parameter guide: subset size and spacing do different jobs

Subset size controls how much local gray-scale information contributes to one correlation calculation. Subset spacing controls the distance between neighboring evaluation locations. They are not interchangeable. Reducing spacing produces more output points but does not make each match more stable. Increasing subset size can add useful texture to a match, but it also averages the estimated motion over a larger physical area.

| Parameter or condition | Primary effect | Possible symptom | Review and adjustment |
| --- | --- | --- | --- |
| Larger subset | Includes more gray-scale features and can improve matching stability | Crack-edge motion appears smoother or a concentration appears broader | Compare with a smaller subset in continuous and discontinuous regions |
| Smaller subset | Resolves more local spatial variation | More matching loss in weak texture and potentially noisier displacement | Check the number of useful features and gray-level variation inside the subset |
| Smaller spacing | Produces a denser output grid | More computation and more points that may still be strongly correlated | Use a density suited to the feature scale; do not equate density with independent information |
| Larger spacing | Reduces the number of evaluations and supports an overview | Narrow concentrations or boundaries may be skipped | Review crack and layer-interface neighborhoods for adequate sampling |
| Crack or spalling edge | Surface continuity and texture may change | Matching loss, outliers, or local gaps | Analyze valid regions separately and preserve the discontinuity |

Compare candidate settings on the same image sequence, using continuous, weak-texture, and crack-adjacent patches to reveal different failure modes. Zones may justify different settings, but their boundaries and parameters should remain attached to the results so that an analysis change is not mistaken for material response.

## 4. Application checklist and the limits of gap filling

A data gap is a measurement or processing state, not a region that must automatically be filled. Common causes include detached texture, occlusion, glare, defocus, a discontinuity at a crack, and points leaving the valid field. The first step is to classify the cause. Imaging problems call for an image and lighting review; physical damage should remain visible in the data mask; and algorithmic matching loss can be investigated through parameter comparisons.

### 4.1 Local interpolation has a narrow role

For a small number of isolated invalid points inside a region already judged to be continuously deforming, local interpolation can make a contour display or a subsequent operation more manageable. Interpolated values are derived from neighboring valid points. They are not new observations and do not restore the real measurement. The original gap mask, the filled region, and any exported dataset should retain that distinction.

Interpolation across a crack, a spalling zone, an occlusion, or a large region of failed correlation is a different matter. It can erase a displacement jump or create a deformation path that was never observed. Such regions should generally remain masked unless a separate, clearly stated analysis assumption justifies another treatment.

Transparent observation windows add reflection and adhesion risks. Glare can move with lighting or view angle, while separation or attached particles can change the visible surface. Lighting and viewing adjustments may reduce reflections, but the texture origin still needs checking. Features that cannot be associated with the model should be marked as limited-quality data rather than forced through correlation.

### 4.2 Review the chain before interpreting strain

Before analysis, review original images, pattern coverage, gray-scale quality, focus, correlation status, subset settings, gap masks, and interpolation records. Full-field strain measurement derives from displacement and is sensitive to local noise and smoothing, so gap treatment should match the strain interpretation. A high-strain band can locate a region of interest but does not define the complete crack geometry.

Once pattern quality, subset settings, and gap treatment are traceable, stage-by-stage interpretation becomes more meaningful. The next article applies this process view to a scaled concrete beam in four-point bending, placing displacement, shear strain, and crack evolution on one timeline.

## 5. FAQ

**1. Is a denser speckle pattern always better for a geotechnical model?**

No. Feature scale should be coordinated with image resolution, subset size, and the deformation features of interest. Very fine features may lose gray-scale definition in the acquired image, while very sparse features may leave too little texture inside a subset.

**2. Can smaller subset spacing compensate for an oversized subset?**

No. Spacing changes the density of evaluation locations, but each result still represents motion estimated over the full subset area.

**3. Do gaps near a crack make the entire dataset unusable?**

Not necessarily. A gap may represent a real discontinuity, matching loss, glare, or spalling. Classify the cause and preserve valid measurements on both sides where possible.

**4. Can interpolated regions be used for quantitative interpretation?**

Only with caution and explicit identification. Interpolated values depend on neighboring measurements and are not independent observations. They should not be created across cracks or large failed-correlation zones.

**5. Can reflections on a transparent window serve as speckles?**

They should not be assumed to do so. Reflections may move with the lighting or camera view rather than with the model surface, so their origin and behavior need to be checked.

</details>
