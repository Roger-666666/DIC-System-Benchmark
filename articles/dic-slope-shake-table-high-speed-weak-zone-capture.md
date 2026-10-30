# 振动台边坡试验怎么拍才有效：XTDIC高速采集、标记点与薄弱部位定位

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 振动台边坡试验的成败，往往在开机前就定了：相机放哪、采多少帧、标记点怎么布、参考区选在哪，决定了事后能不能从位移场里读出滑移与薄弱部位。本文结合岩质边坡缩尺模型的振动台试验条件，拆解采样节奏、标记点与散斑的分工、相机基准的处理方式，并说明临界加速度阈值能用到什么程度。

> **关键词：** XTDIC三维全场测量；数字图像相关技术；边坡变形监测；振动台试验；高速采集；薄弱部位定位

## 目录

- [一、先看试验条件，再定拍摄方案](#一先看试验条件再定拍摄方案)
- [二、50 Hz 到底够不够](#二50-hz-到底够不够)
- [三、标记点与全场散斑怎么分工](#三标记点与全场散斑怎么分工)
- [四、相机固定在哪，决定了数据怎么算](#四相机固定在哪决定了数据怎么算)
- [五、结果怎么读：滑移、薄弱部位与临界阈值](#五结果怎么读滑移薄弱部位与临界阈值)
- [六、常见问题](#六常见问题)

## 一、先看试验条件，再定拍摄方案

岩质边坡的振动台试验，对象是缩尺模型，输入是不同峰值加速度的地震波。该试验的振动台条件可作为量级参考：最大负载 4.0×10^4 kg，满载水平向与竖向加速度分别为 1.5 g 与 1.0 g，满载峰值水平速度 1.5 m/s、竖向速度 1.2 m/s，最大水平位移与竖向位移分别为 300 mm 和 150 mm。

这几个数字定了拍摄方案的基本盘：300 mm 的位移量级要求视场不能太小，否则模型一摆就出画；1.5 m/s 的峰值速度意味着帧间位移不小；秒级持续时间让数据量可控。若对象换成落石冲击或爆破振动，时间尺度掉到毫秒，同一套方案立刻不成立。

先挑相机参数再回头找场景，顺序是反的。合理顺序是先定关心的物理过程及其时间、空间尺度，再倒推视场、分辨率与采样频率。振动台试验关心不同烈度下的响应差异、失稳从哪开始、滑移量多大，空间尺度是米级、时间尺度是秒级，方案就该围着这两个量做。

## 二、50 Hz 到底够不够

该试验的采集配置是两台约 200 万像素的高速相机，采集频率 50 Hz。高速相机为什么只采 50 Hz？

回答它要回到采样定理与试验目的。50 Hz 意味着帧间隔 20 ms。按峰值水平速度 1.5 m/s 估算，两帧之间坡面最大移动约 30 mm。这个量对散斑匹配是可接受的——子区尺寸通常在数十像素量级，对应的物理尺寸足以覆盖 30 mm 的位移，前提是视场划分得当、子区不要设得太小。

更关键的是频率成分。振动台输入的地震波，主要能量集中在较低频段，坡体的整体响应也以低频摆动和累积滑移为主。对这类过程，50 Hz 的采样能够刻画位移时程的主干形态；它抓不住的是高频细节，比如局部开裂瞬间的应变突变。

所以“够不够”要看：关心的现象里有多少能量落在采样频率的一半以上？如果关注的是整体滑移、残余位移、不同烈度下的响应差异，50 Hz 够用；如果要看裂纹起裂的那一瞬间，或者输入本身含高频成分，就得提高帧率，代价是分辨率、记录时长和照明的连锁让步。

采样率还影响判读方式。帧率低，帧间位移大，匹配的搜索范围与初值估计就变得重要；若沿用静态试验那套“小位移、小搜索窗”的设置，很容易失配，表现为零散的错误矢量，而不是连续变形场。

不同观测对象对采样的要求差别很大，可用一张表对照：

| 观测对象 | 时间尺度 | 采样需求 | 主要限制 |
| --- | --- | --- | --- |
| 振动台整体滑移 | 秒级 | 数十赫兹，覆盖主要振动周期 | 视场覆盖与空间分辨率的平衡 |
| 局部开裂瞬间 | 毫秒级 | 数百至数千赫兹 | 存储带宽与照明强度 |
| 长期边坡观测 | 天到年 | 按周期重复观测 | 站位与光轴复现 |

## 三、标记点与全场散斑怎么分工

这套配置里同时用到了散斑全场测量和标记点追踪：坡面布设标记点，通过标记点的识别与立体匹配重建表面点的三维坐标和位移，用于计算多期地震作用下的变形过程。

两者不是重复劳动，分工很清楚。标记点是稀疏但可靠的控制点：位置已知、形状可辨、匹配不容易错，适合给出关键部位的绝对位移参照，也适合在图像质量下降时提供退路。全场散斑给的是空间连续分布，能看出滑移从哪个区域开始、往哪个方向扩展、影响范围多大。

布标记点有几条经验。第一，不要共线。所有标记点排在一条直线上，无法约束面内旋转。第二，覆盖视场边缘。标记点全挤在中间，边缘区域的解算缺少约束。第三，附着要刚性。贴在松散的土体表面，标记点自己会动，测出来的位移就掺了假。第四，编号要与物理位置对应，事后能从数据文件回溯到坡面上的哪个点。

散斑方面，岩质模型表面往往有天然纹理，能不能直接用要先试采集。纹理足够时省去制斑工序；不足或对比度低时需人工散斑，颗粒尺度与子区、视场匹配。最常见失误是散斑做得太细：远景拍摄时细颗粒糊成噪声，相关性反而下降。

## 四、相机固定在哪，决定了数据怎么算

振动台试验有个绕不开的问题：相机固定在台外，还是固定在台面上？

固定在台外，视场稳定，但台面运动全部计入模型响应——测到的位移里包含了台面的刚体位移。固定在台面上，相机随台一起动，模型相对相机的位移才是纯变形，但相机自身的振动会引入噪声，且支架必须足够刚，否则台面加速度会让支架产生附加变形。

两种做法都能用，前提是把刚体分量说清楚。台外固定的方案，需要在视场内保留一个随台面运动的参考区，用它的位移估计整体平移与转动，再从模型区域的结果中扣除；台面固定的方案，则需要确认支架在试验频段内不发生共振变形。

还有一个细节常被忽略：参考状态取哪一帧。取激振前的静止帧，得到的是累积位移；取每一级输入的起始帧，得到的是该级的相对位移。两种口径对应的结论不同，报告里必须写明。混用两种口径，曲线会出现无法解释的跳变。

## 五、结果怎么读：滑移、薄弱部位与临界阈值

这组试验得到的结论有三条：一是可获得不同地震烈度下的边坡滑移幅度；二是能定位最先发生失稳的薄弱部位；三是可得到抗震临界加速度阈值。这三条的可信度并不相同，读法也不一样。

滑移幅度是最直接的一条。它来自位移场在关键区域的空间平均，本身受参考状态和区域选取影响，报告里要同时给出区域范围和取值方式。

薄弱部位定位的可信度取决于空间覆盖。若视场只覆盖坡面中部，坡顶或坡脚的早期异常就看不到，“最先失稳”的判断会偏向视场中心。这也是为什么多视角或大视场覆盖在这类试验里格外重要。

临界加速度阈值最需要谨慎。它是在特定模型、特定材料配比、特定输入波形下得到的结果，换一组条件，数值就变。它的价值在于揭示机理——坡体在什么响应水平下开始出现不可恢复的变形，而不在于给出一个可以套用到现场的数字。把它当作现场预警阈值，是把模型结论外推到了它支撑不了的范围。

该试验的分析里还提到加速度放大效应：地震惯性力是边坡变形失稳的重要原因，坡面形态影响地震波在坡内的传播，进而改变地震动响应。这条提示了一个联合判读的思路——把加速度响应与位移场放在一起看，坡顶加速度放大明显而位移响应滞后的部位，往往是后续滑移的起点。

试验做完，位移场、标记点轨迹、加速度响应都齐了，接下来要回答的是工程问题：这套配置放到真实边坡上，采样节奏、供电、防护、数据回传怎么安排。那是另一套逻辑。

## 六、常见问题

**1. 高速相机采 50 Hz 是不是浪费？**

不矛盾。所谓高速是相对常规工业相机的能力上限，实际取多少帧要看试验的时间尺度。振动台试验以低频大位移为主，50 Hz 足以刻画位移时程主干，同时保留较高分辨率与较长记录时长。

**2. 只布标记点、不做全场散斑行不行？**

可以，但拿到的只是稀疏点位移。标记点适合做控制与参照，无法给出应变分布和滑移区域的空间形态。要判断薄弱部位在哪，仍需要全场数据。

**3. 相机固定在台外，测到的位移包含台面运动怎么办？**

在视场内保留随台面运动的参考区，用它的位移估计刚体分量并扣除。参考区不能选在正在滑移的坡体上，否则真实变形会被一并扣掉。

**4. 临界加速度阈值能用于现场预警吗？**

不能直接用。该数值对应特定模型、材料与输入波形，换条件即失效。它的价值在于机理认识，现场阈值需要结合真实地质条件与独立监测资料确定。

**5. 散斑是不是越细越好？**

不是。颗粒尺度要与视场、拍摄距离和子区尺寸匹配。远景拍摄时过细的散斑在图像上退化为噪声，反而降低相关性。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Shooting a Shaking-Table Slope Test Properly: High-Speed Capture, Markers, and Weak-Zone Localization with XTDIC

> **Abstract:** The outcome of a shaking-table slope test is often decided before acquisition starts: camera placement, frame count, marker layout, and reference-region choice determine whether the displacement field can later reveal sliding and weak zones. Using a scaled rock-slope model on a shaking table, this article examines sampling rhythm, the division of labour between markers and full-field speckle, treatment of camera reference, and the defensible use of a critical acceleration threshold.

> **Keywords:** XTDIC full-field 3D measurement; digital image correlation; slope deformation monitoring; shaking-table test; high-speed acquisition; weak-zone localization

## Contents

- [1. Read the test conditions before designing the capture](#1-read-the-test-conditions-before-designing-the-capture)
- [2. Is 50 Hz enough?](#2-is-50-hz-enough)
- [3. Markers and full-field speckle: a division of labour](#3-markers-and-full-field-speckle-a-division-of-labour)
- [4. Where the cameras sit determines how data are computed](#4-where-the-cameras-sit-determines-how-data-are-computed)
- [5. Reading the results: sliding, weak zones, thresholds](#5-reading-the-results-sliding-weak-zones-thresholds)
- [6. FAQ](#6-faq)

## 1. Read the test conditions before designing the capture

A shaking-table test on a rock slope uses a scaled model and inputs seismic waves at different peak accelerations. The test setup defines the order of magnitude: maximum payload 4.0×10^4 kg; full-load horizontal and vertical acceleration of 1.5 g and 1.0 g; full-load peak horizontal and vertical velocity of 1.5 m/s and 1.2 m/s; maximum horizontal and vertical displacement of 300 mm and 150 mm.

These numbers set the baseline. A 300 mm displacement range means the field of view cannot be small, or the model leaves the frame as soon as it swings. A 1.5 m/s peak velocity means substantial motion between frames. A duration measured in seconds means the data volume is manageable and storage bandwidth is not the constraint. Reverse the object—rockfall impact or blasting vibration, with timescales in milliseconds—and the same plan collapses immediately.

Plans often start with camera specifications and then look for a scenario, which reverses the logic. The workable order is: identify the physical process and its temporal and spatial scales, derive field of view, resolution, and sampling rate, and only then select hardware. In a shaking-table test the questions concern response differences between intensities, where failure begins, and how far the slope slides; the spatial scale is metres and the temporal scale is seconds, so the plan should be built around those two quantities.

## 2. Is 50 Hz enough?

The test configuration uses two high-speed cameras of roughly 2 megapixels each at 50 Hz. The number invites a fair question: why would a high-speed camera run at 50 Hz?

The answer lies in sampling theory and test purpose. At 50 Hz the frame interval is 20 ms. Taking the peak horizontal velocity of 1.5 m/s, the surface can move about 30 mm between frames. That is acceptable for speckle matching—subset sizes are typically tens of pixels, and the corresponding physical size covers 30 mm provided the field is divided sensibly and subsets are not set too small.

Frequency content matters more. Ground motion from a shaking table concentrates energy at lower frequencies, and the slope's global response is dominated by low-frequency sway and cumulative sliding. At 50 Hz the backbone of the displacement history is captured; what is lost is high-frequency detail, such as the strain jump at the instant of local cracking.

So "enough" depends on how much of the energy of interest lies above half the sampling rate. For global sliding, residual displacement, and intensity-to-intensity differences, 50 Hz suffices. To resolve the instant of crack initiation, or when the input itself carries high-frequency content, frame rate must rise—at the cost of resolution, record duration, and illumination.

Sampling rate also shapes interpretation. At low frame rates, inter-frame displacement is large, so search range and initial estimates in the matching step become important. Reusing the small-displacement, small-window settings of a static test invites mismatches, which appear as scattered erroneous vectors rather than a continuous deformation field.

Different observation targets impose very different sampling requirements:/n/n| Target | Time scale | Sampling need | Main constraint |
| --- | --- | --- | --- |
| Global slope sliding on a shaking table | Seconds | Tens of hertz, covering the dominant period | Balance between coverage and spatial resolution |
| Instant of local cracking | Milliseconds | Hundreds to thousands of hertz | Storage bandwidth and illumination |
| Long-term slope observation | Days to years | Repeat surveys at intervals | Repeatable station and optical axis |

## 3. Markers and full-field speckle: a division of labour

This configuration uses both speckle-based full-field measurement and marker tracking: markers are placed on the slope surface, and marker identification with stereo matching reconstructs the 3D coordinates and displacements of surface points, which yields the deformation history across successive seismic events.

The two are not redundant. Markers are sparse but dependable control points: their positions are known, their shapes are recognizable, and mismatch is unlikely. They provide absolute displacement references at key locations and a fallback when image quality degrades. Full-field speckle provides spatial continuity, showing where sliding begins, in which direction it propagates, and how far it extends.

A few marker rules are worth stating. First, do not place them collinearly; a single row cannot constrain in-plane rotation. Second, cover the frame edges; markers clustered at the centre leave peripheral areas poorly constrained. Third, attach rigidly; a marker glued to loose soil moves on its own, and the measured displacement absorbs that motion. Fourth, number markers to match physical positions so that data files can be traced back to specific points on the slope.

On the speckle side, rock-like model surfaces often carry natural texture, and whether it can be used directly should be verified with a trial acquisition. Sufficient texture removes the patterning step; insufficient or low-contrast texture requires artificial speckle, with particle size matched to subset size and field of view. The most common error is making the pattern too fine: at long working distances, fine particles blur into noise and correlation drops.

## 4. Where the cameras sit determines how data are computed

A shaking-table test cannot avoid one question: are the cameras mounted off the table, or on it?

Mounted off the table, the field of view is stable, but table motion enters the model response, so measured displacement includes rigid-body motion of the table. Mounted on the table, the cameras move with it, and displacement relative to the cameras is pure deformation—but camera vibration adds noise, and the mount must be stiff enough that table acceleration does not deform it.

Both arrangements work, provided the rigid-body component is handled explicitly. With off-table mounting, keep a reference region inside the frame that moves with the table, estimate global translation and rotation from it, and subtract that from the model region. With on-table mounting, confirm that the mount does not resonate within the test frequency band.

One detail is frequently overlooked: which frame serves as the reference state. Using the pre-shaking still frame yields cumulative displacement; using the start of each input level yields per-level relative displacement. The two conventions support different conclusions and must be stated in the report. Mixing them produces jumps in the curves that cannot be explained.

## 5. Reading the results: sliding, weak zones, thresholds

The test results make three claims: sliding amplitude can be obtained for different seismic intensities; the weak zone that fails first can be located; and a critical acceleration threshold for seismic resistance can be derived. The three do not carry equal weight, and they should not be read the same way.

Sliding amplitude is the most direct. It comes from spatial averaging of the displacement field over a key region, so it depends on the reference state and the region chosen; both the region extent and the averaging method belong in the report.

Weak-zone localization depends on spatial coverage. If the field covers only the mid-slope, early anomalies at the crest or toe are invisible, and the "first to fail" conclusion drifts toward the centre of the frame. This is why multi-view or wide-field coverage matters so much in these tests.

The critical acceleration threshold demands the most caution. It was obtained for a particular model, material mix, and input waveform; change any of them and the number changes. Its value lies in mechanism—at what response level the slope begins to accumulate irrecoverable deformation—not in producing a figure transferable to a site. Treating it as a field warning threshold extends a model result beyond what it can support.

The analysis also notes acceleration amplification: seismic inertia is a major cause of slope deformation and failure, and slope geometry alters wave propagation within the slope, which in turn changes ground response. This suggests a joint reading—where crest acceleration amplifies strongly while displacement response lags, sliding often starts later.

Once displacement fields, marker trajectories, and acceleration responses are in hand, the engineering question becomes how such a configuration would be deployed on a real slope: sampling rhythm, power, protection, and data return. That follows a different logic, involving long-term observation and operating-mode selection.

## 6. FAQ

**1. Is running a high-speed camera at 50 Hz wasteful?**

No. "High speed" describes the capability ceiling relative to ordinary industrial cameras; the actual rate follows the test timescale. Shaking-table tests are dominated by low-frequency, large displacement, where 50 Hz captures the backbone of the history while preserving resolution and record duration.

**2. Can markers alone replace full-field speckle?**

They can, but the result is sparse point displacement. Markers serve as control and reference and cannot provide strain distribution or the spatial shape of a sliding zone. Locating a weak zone still requires full-field data.

**3. With off-table cameras, how is table motion removed?**

Keep a reference region inside the frame that moves with the table, estimate the rigid-body component from it, and subtract it. The reference must not sit on the sliding mass, or real deformation is removed along with the rigid motion.

**4. Can the critical acceleration threshold be used for field warning?**

Not directly. The value corresponds to a specific model, material, and waveform, and changes when conditions change. Its value is mechanistic; field thresholds require real geological conditions and independent monitoring data.

**5. Is finer speckle always better?**

No. Particle size must match field of view, working distance, and subset size. At long working distances, an overly fine pattern degrades into noise and reduces correlation.

</details>
