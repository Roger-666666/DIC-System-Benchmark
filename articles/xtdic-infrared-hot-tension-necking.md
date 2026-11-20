# 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 原理与应用*

颈缩是拉伸试样在某一局部逐渐变细的现象。对于高温金属圆棒，颈缩位置关系到后续断裂发生在哪一段，也是研究材料局部变形能力的重要依据。XTDIC 高温拉伸案例显示，在圆棒外形明显收窄之前，主应变图上已经可以分辨出变形集中的区域。应变集中、外形颈缩与最终断裂各有对应的观测证据，标记这几个阶段时需要说清各自采用的判据。

**本文目录**

- [为什么平均伸长容易遗漏局部变化](#chinese-section-1)
- [从试验信号识别变形阶段](#chinese-section-2)
- [沿轴线读剖面，比追逐最高像素更稳定](#chinese-section-3)
- [圆棒边缘怎样提供第二条证据](#chinese-section-4)
- [同一份记录为什么会读出不同的颈缩时刻](#chinese-section-5)
- [断裂前最后几帧怎么取舍](#chinese-section-6)
- [常见问题](#chinese-section-7)

<a id="chinese-section-1"></a>

## 为什么平均伸长容易遗漏局部变化

若在标距段的两端做标记，拉伸前后测量两点的距离变化，就能得到这段材料的平均伸长信息。局部化初期，只有很短的一段比周围伸得快，其变化在沿整段求平均时会被摊薄。两件试样即使达到相近的总伸长，也可能在不同位置形成不同宽度的集中区。要了解损伤在何处发展，需要把测量范围从两端之间的一个平均值，扩展到可见表面的许多小区域。

数字图像相关法跟踪表面花纹的运动，从局部位移变化计算应变。主应变描述局部沿主方向的拉伸或压缩程度，其中最大主应变有助于寻找伸长最为集中的区域。读图时应查看图例与方向定义，并让不同时刻的图使用相同色标。若每张图都把本帧最大值显示为红色，仅凭红色面积很难比较集中程度是否加重。

<a id="chinese-section-2"></a>

## 从试验信号识别变形阶段

| 试验阶段 | 优先观察的证据 | 可以作出的判断 |
| --- | --- | --- |
| 较均匀的拉伸 | 轴向位移沿标距连续变化，应变分布较平缓 | 观察范围内伸长较为分散 |
| 局部应变集中 | 同一区域连续多帧比两旁伸得更快 | 可将该区域列为后续颈缩的观察对象 |
| 可见颈缩 | 原始照片上局部宽度持续减小，且与邻近区域拉开差异 | 可以定位可见表面的收窄区域 |
| 接近断裂 | 轮廓继续演变，部分散斑可能无法匹配 | 标明最后可靠的应变帧，另存断裂照片 |

<a id="chinese-section-3"></a>

## 沿轴线读剖面，比追逐最高像素更稳定

对圆棒表面的应变图，可以沿工作段轴线取一条剖面，横坐标为材料沿轴线的位置，纵坐标为局部轴向应变。在较均匀的阶段，曲线通常在相近水平上缓慢变化。若某一处在相邻时刻连续形成隆起，两边的应变仍较低，就能观察这处隆起是逐渐变高、变窄，还是随材料一道移动。对中线附近一条有宽度的区域做平均，也能减少孤立异常像素对位置判断的影响。平均范围应当公开，便于读者分辨实际带宽与分析设置带来的平滑。

主应变图适合寻找可能的集中区；沿轴线的剖面则适合量化带内外的伸长差。两种应变定义并不总是给出相同峰值。若拉伸伴随局部剪切或弯曲，最大主应变方向就可能偏离轴线。报告可在同一时刻标出轴向分量、最大主应变及其方向，说明最终所说的“峰值”来自哪一项。参考状态也应保持一致，避免一个图从保温结束起算、另一个图从较晚的加载阶段起算。

<a id="chinese-section-4"></a>

## 圆棒边缘怎样提供第二条证据

在颈缩候选区域沿垂直于局部轴线的方向提取轮廓宽度，同时在其两侧选择外形连续的邻近截面。随后跟着这些截面对应的材料位置重读后续图像。仅观察某处宽度变小还不充分，因为较均匀拉伸阶段整个工作段也会横向收缩。如果候选截面的宽度相对于两旁持续减小，轴向应变剖面又在同一带形成持续峰值，就有更直接的依据描述局部收窄。

轮廓宽度在圆棒转动、中心线偏移或边缘被夹具遮住时会受到影响。可将两侧边缘的位置和中心线轨迹同时保留。如果看起来只有一侧边缘移动，而试样中心线也在画面中明显偏移，要先查是否同时发生刚体运动或弯曲。单个视角给出的宽度是投影量；要据此求截面面积或断面收缩率，应额外检验截面几何假设，必要时采用独立的断后尺寸测量。

<a id="chinese-section-5"></a>

## 同一份记录为什么会读出不同的颈缩时刻

关注材料稳定性的人可能用相邻区域的应变增长开始分化作为局部化起点。关注外形的人可能把轮廓首次出现持续收窄作为颈缩的可见起点。关注整件承载的人则更习惯记录最大拉力时刻。它们描述的是不同尺度的事件。在同一页上分别报出“集中带开始持续发展”“轮廓可辨收窄”和“整体载荷达到峰值”，读者就能知道研究者追踪的是哪一个过程。

比较不同试样前，可以用相同的剖面宽度、时序判据和轮廓提取方法复算一遍。如果缩小应变计算的邻域，一条窄带可能显得更尖锐，同时也更容易受噪声影响；如果过度平滑，早期的局部变化又可能被摊开。对一个合理范围内的计算尺度重复分析，记录在各设置下都能辨认的部位与时间区间，有助于判断“较早出现颈缩”的材料差异是否大于方法本身的变化。

<a id="chinese-section-6"></a>

## 断裂前最后几帧怎么取舍

最后的红色区域常常最吸引注意，却也是最需要查看原始图像的地方。一侧花纹被拉散、轮廓突然断开或裂口出现后，跨越缺口计算的位移梯度会混入表面分离量。若继续用平滑补满这片区域，可能得到一条视觉上连续、物理意义却已经改变的应变曲线。此时可以保留裂口两侧仍有效的位移，用于描述两侧表面如何分开，并明确局部材料应变在哪里终止。

从断口向前回溯时，可先标出最后一帧仍能识别连续轮廓和花纹的图像，再标出第一帧已经清楚分离的图像。这段区间能界定可见分离发生的时段。它也可能晚于裂纹在内部或不可见一侧开始发展的时刻。将断后照片的方向与试验视角统一，标注最终断口与此前集中带的相对位置，才能把“集中区位于断口附近”与“已经观测到裂纹起源”这两类判断区分清楚。

### 如何比较两种材料的局部变形能力

工程人员有时希望用“哪件试样先出现红色”比较两种材料。更有意义的起点是给两件试样选择共同的材料状态。例如在相同工作段平均伸长下，比较局部应变峰相对于邻近区域的增量，以及集中带延伸到了多大范围。一个试样可能在较宽区域内持续伸长，另一个可能把相近的新增伸长集中在很短的一段。即使两者达到相同的平均伸长，这种空间分配仍有区别，正是全场测量能补充的材料信息。

接着考察事件之间的间隔：应变集中一旦形成，轮廓是很快就出现局部收窄，还是在一段加载历程中逐渐发展？可以用整体标距的新增伸长来表示两事件之间还经历了多少拉伸，同时报告相应载荷阶段。若用经过的时间来比较，还应核对两次试验的加载方式和速率；若用平均伸长来比较，则需保持标距定义一致。这样能避免把加载过程走得快误写成材料局部化发展得更快。

在材料批次评价中还应保留异常位置的证据。某件试样在肩部过渡区收窄、另一件在工作段中部收窄，即使各自最大应变接近，几何与约束环境也不同。把两类试样分别展示并说明断口位置，比简单取一个批次平均峰值更有助于判断是否需要复查试样加工与装夹。

<a id="chinese-section-7"></a>

## 常见问题

**载荷开始下降，能直接定位颈缩吗？** 载荷峰值能确定值得回看的时段。要找位置，还需要这一时段的应变场和试样轮廓。比较轮廓时可跟随同一小段材料，避免把材料沿轴向移动误当成局部宽度变化。

**热像上的亮点能作为颈缩起点吗？** 亮点可以协助选择复查区域。识别颈缩仍要看材料是否局部收窄，并核对温度差在加载前是否已经存在。热像的意义在于为已定位的变形区域补充热状态。

**局部应变大就代表出现了内部裂纹吗？** 表面应变图提供的是表面运动信息。要确认内部裂纹或损伤机制，还要结合截面、断口或其他独立检查。对于材料筛选，可以先比较各试样的集中位置与发展过程；对于失效分析，则应把这些记录与断后证据相对应。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [227 · 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#chinese-version)

</details>

<details>
<summary><b>English · Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain</b></summary>

<a id="english-version"></a>

# Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain

*Measuring deformation and damage at elevated temperature · Measurement principles*

Necking is the progressive local narrowing of a specimen under tension. Its location in a hot round bar matters both to the eventual fracture site and to the assessment of local deformability. In the published XTDIC test, strain concentration could be identified before narrowing became obvious in the outline. Localized strain, a visible neck and final fracture each have their own observable evidence.

**Contents**

- [Why average extension can miss an early change](#english-section-1)
- [Evidence for successive stages](#english-section-2)
- [Following an axial profile](#english-section-3)
- [Using the outline as independent evidence](#english-section-4)
- [Why onset depends on the stated criterion](#english-section-5)
- [Interpreting the last frames](#english-section-6)
- [Frequently asked questions](#english-section-7)

<a id="english-section-1"></a>

## Why average extension can miss an early change

Two marks at the ends of a gauge length give an average measure of extension between them. Early in localization, a short section stretches faster than its surroundings. Averaging across the gauge length dilutes its contribution. Two specimens with similar overall extension can develop concentrated bands in different locations and over different widths. Studying that process requires observations across many small regions on the visible surface.

Digital image correlation tracks surface texture and estimates strain from spatial changes in displacement. Principal strains describe extension or contraction along local principal directions. The maximum principal strain helps locate regions of concentrated stretch. Interpretation requires the plotted quantity and a consistent colour scale. If every map displays its own highest value in red, red area alone gives a poor comparison across time.

<a id="english-section-2"></a>

## Evidence for successive stages

| Stage | Evidence to examine | Supported interpretation |
| --- | --- | --- |
| Relatively uniform tension | Continuous axial displacement and broadly distributed strain | Extension is shared across the observed length |
| Strain localization | The same patch stretches faster than adjacent patches in successive frames | A region to follow for later necking |
| Visible necking | Local width persistently decreases relative to neighbouring sections | The visible narrowing can be located |
| Approaching fracture | The outline evolves and some speckles may cease to match | Identify the last reliable strain map and retain the fracture image separately |

<a id="english-section-3"></a>

## Following an axial profile

Take a profile down the gauge section with material position on the horizontal axis and axial surface strain on the vertical. In relatively uniform extension the profile varies gradually. When successive frames develop a persistent hump with lower strain on either side, track its height, width and position as the material moves. Averaging across a narrow strip near the centreline can reduce the influence of isolated bad pixels. Report the averaging width so that apparent band width can be interpreted against spatial smoothing.

Principal strain helps locate a candidate band. An axial profile quantifies the contrast in longitudinal extension. Their peaks need not agree: local shear or bending can rotate the major principal direction away from the bar axis. Showing axial strain, maximum principal strain and its direction at the same time makes the definition of a peak explicit. All maps in the comparison need the same reference state.

<a id="english-section-4"></a>

## Using the outline as independent evidence

Measure width across the candidate region perpendicular to its local centreline and select neighbouring intact sections. Follow the corresponding material positions through later frames. Uniform tension can reduce width throughout the gauge section. A persistent additional reduction relative to both neighbours, coinciding with a developing peak in the axial strain profile, is stronger evidence of local narrowing.

Rotation, translation of the centreline or partial occlusion can affect projected width. Retain both edge positions and the centreline trajectory. Motion of only one apparent edge accompanied by substantial centreline movement warrants checking rigid motion or bending. A width from one view is a projection. Converting it into cross-sectional area or reduction of area requires additional geometric assumptions or independent post-test measurements.

<a id="english-section-5"></a>

## Why onset depends on the stated criterion

A material-stability study may define localization by the first persistent difference in strain growth between neighbouring regions. A geometry study may date visible necking from persistent local narrowing. A load-capacity study may use maximum force. Reporting these three events separately identifies the scale and observable under investigation.

Before comparing specimens, reprocess them with the same profile width, time criterion and edge method. A smaller strain neighbourhood can sharpen a narrow peak but also amplify noise. Excess smoothing can spread the first sign of localization over a larger region. Repeating the analysis over a reasonable range of scales identifies sites and onset intervals that remain stable and indicates whether an apparent material difference exceeds the sensitivity of the method.

<a id="english-section-6"></a>

## Interpreting the last frames

The final red region often deserves the closest examination of raw photographs. When speckles disperse or a crack opens, a displacement gradient calculated across the gap includes surface separation. Smoothing across it may produce a continuous curve whose physical meaning has changed. Displacement on the two intact sides may still describe opening if the end of valid local material strain is marked.

Working backwards, identify the last frame with continuous outline and texture and the first with clear separation. These frames bound visible separation, which may follow cracking inside the bar or on its hidden side. Orient post-test photographs to match the test view and mark the final fracture relative to the earlier band. Evidence that a band lay near the final fracture and evidence of the actual crack origin support different conclusions.

### Comparing the capacity for local deformation

Compare specimens at a common state, for instance at the same average gauge extension. Examine the excess of local strain over its neighbouring level and the width over which strain accumulates. Similar additional overall extension can be shared across a broad region in one specimen and a short length in another. This distribution adds material information that the gauge average alone cannot supply.

Then examine the interval between localization and visible narrowing. Additional gauge extension over that interval describes how much further stretching occurred, and the corresponding load stage provides context. Comparing elapsed time requires comparable loading rates and control modes. Comparing extension requires consistent gauge definitions.

Retain unusual sites in a batch assessment. A neck in the shoulder transition and one in the middle of the gauge experience different geometries and constraints, even if their peak strains are similar. Reporting these groups and their fracture locations separately is more informative for a review of machining or gripping than pooling all maxima into one average.

<a id="english-section-7"></a>

## Frequently asked questions

**Does a fall in load locate the neck?** Peak force identifies a time interval worth reviewing. Strain fields and specimen outlines locate the region. Following the same material section avoids confusing axial motion with a change in local width.

**Does a bright thermal spot mark necking onset?** It can direct attention to a region. Identification still requires evidence of local narrowing and consideration of any temperature difference present before loading. Thermograms describe the thermal state of the identified region.

**Does high local strain establish an internal crack?** A surface strain map describes surface motion. Sectioning, fracture-surface observations or another independent inspection are needed for an internal crack or damage mechanism. Material screening can compare localization histories, while a failure investigation can connect those histories to post-fracture evidence.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [227 · Validating a Hot Tensile Simulation with XTDIC Strain Fields, Thermograms and Load Curves](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#english-version)

</details>
