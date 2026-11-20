# 高温拉伸热区定位：红外热像与 XTDIC 应变场的三种对照方法

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温拉伸热区定位：红外热像与 XTDIC 应变场的三种对照方法</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 方法比较*

分析高温金属圆棒时，“工作段中部偏热”“颈缩区附近偏热”和“温度最高点与最大应变点重合”是三种精细程度不同的结论。XTDIC 与红外相机分别从自己的视角观察圆棒。时间上同步以后，空间上选择哪一种对照方法，取决于需要把结论落实到整段、某一块材料，还是某一个局部峰值。

**本文目录**

- [三种方法分别适合回答什么问题](#chinese-section-1)
- [以圆棒中部的一条应变带为例](#chinese-section-2)
- [圆棒与平板的差别体现在哪里](#chinese-section-3)
- [建立对应关系后，怎样独立检查偏差](#chinese-section-4)
- [示例：围绕最终颈缩区提取温度历程](#chinese-section-5)
- [对读结果做一次位置敏感性检查](#chinese-section-6)
- [怎么判断“重合”这个词用得是否合适](#chinese-section-7)

<a id="chinese-section-1"></a>

## 三种方法分别适合回答什么问题

| 方法 | 读取对象 | 适合的任务 | 主要限制 |
| --- | --- | --- | --- |
| 按工作段分区 | 将两幅图各自分成靠近两端和中部的区域 | 检查保温后哪一段存在温差 | 难以确定窄带或峰值的位置 |
| 固定位置对照 | 在相机坐标下持续观察同一位置 | 分析炉内指定位置的温度随加载怎样变化 | 拉伸中经过此处的材料会改变 |
| 跟随材料区域 | 用 DIC 跟踪一块材料，把各时刻的位置对应到热像 | 研究最终颈缩区的温度与应变历程 | 需要空间配准，并验证跟踪有效性 |

<a id="chinese-section-2"></a>

## 以圆棒中部的一条应变带为例

当研究任务是确认试样是否已经均温，把工作段分区通常就能提供可读的结果。此时更有意义的是比较中部与端部各自的温度范围，并检查差异能否在保温期持续观察到。若问题转为“后来形成颈缩的材料，在开始集中伸长前是否已经偏热”，就需要改变取样方式。工作段会随拉伸伸长，屏幕中间的光标即使没动，经过它的表面材料也可能已经换了。

较细致的做法是先在 DIC 图像中跟踪材料区域，再给热像找到相应的位置。这一步称为空间配准。它需要让两套成像系统对同一物理位置建立对应，并用独立的可识别位置检验偏差。圆棒边缘弯曲，两台相机能同时看见的表面有限；如果目标区域转出其中一个镜头的有效视野，后续帧就应标记为无法比较。

<a id="chinese-section-3"></a>

## 圆棒与平板的差别体现在哪里

从正面看，圆棒的工作段像一条长方形色带。实际上，中线两侧的表面逐渐转向侧面。在一台相机里只占很窄的一列像素，放到圆棒曲面上却可能覆盖较宽的一片材料。另一台侧向布置的相机看过去，这片材料可能位于视野边缘，甚至被圆棒自身遮挡。因此，以两幅图中轮廓的左边和右边分别对齐，只能保证可见轮廓看起来接近；两个轮廓之间的材料仍可能一前一后。

做初步筛查时，可将研究范围限在两套设备都能清楚看到的工作段正面，把靠近切线方向的细窄边缘留在比较范围之外。对精细定位，可以利用双目 DIC 重建的表面形状，根据热像仪与这套坐标系的相对位置，将表面区域投影到热像中。若装置只对某一平面建立了映射，需要核对圆棒表面偏离该平面的程度。颈缩加深后曲面发生变化，加载前建立的平面对应关系也可能逐渐失去适用性。

<a id="chinese-section-4"></a>

## 建立对应关系后，怎样独立检查偏差

校准时若用一组特征求得映射，再用完全相同的一组特征检查，得到的小偏差主要说明计算能解释这些点。为了知道它在真正关心的位置是否可用，可以留出一组没有参与拟合的可识别位置，分布在工作段中部、两端及实际要读数的区域附近。将其投影到热像后，记录预测位置和观察位置的距离，并用当地的图像比例估算它在试样上大约占多宽。

这些偏差的方向也值得保留。若所有点都朝相近方向偏移，可优先检查相机或支架位置是否有变化；若中间较准而越到边缘越偏，应审视曲面、镜头畸变或平面近似带来的影响。把偏差在图上画成带方向的小箭头，往往比只给出全幅平均误差更能说明哪里可以追踪窄带。图像边缘正好是结论所在的位置时，局部偏差比全幅平均更重要。

<a id="chinese-section-5"></a>

## 示例：围绕最终颈缩区提取温度历程

假设希望比较颈缩区与附近完整区域的热历程。可以从轮廓仍完整、细颈已可辨认的一帧着手，沿着圆棒轴向圈定一小块目标材料。在 DIC 有效的前提下，把这个区域追溯至保温结束时，再将它在各时刻的位置映射到相应热像上。邻近对照区可选在相似视角、相似涂层但远离明显变形带的位置。这样比较起来，表面状态与观察方向的差异较小，判断更集中于材料经历的差别。

读取温度时，应同时记录选区内有效热像像素的覆盖情况。颈缩前宽裕的区域，颈缩后可能只剩少量像素可靠地落在试样上，边缘点还可能混入炉内背景。此时可收缩可用区域，但要在曲线上注明选区发生改变的时刻；如果保留下来的已不是同一片材料，则应结束原曲线，另列后续观察。整条曲线看起来连续，并不自动意味着被测对象一直相同。

<a id="chinese-section-6"></a>

## 对读结果做一次位置敏感性检查

对结论影响较大的热区，可以把选定区域按校核得到的配准偏差向周围小幅移动，重新读取温度趋势。若这些合理的位置变动都保留了“该区域较邻近区持续偏热”的判断，区域层面的结论就有较好的支撑。若仅把选区挪到另一侧，温度差便消失甚至反向，说明结果对边界很敏感，此时宜扩大报告的位置范围，并保留原始热像供复查。

还可以比较区域平均温度和局部最高温度。平均值有助于描述一片材料的整体变化，最高值则对单个异常像素、反射亮点或背景混入更加敏感。二者分歧时，回看热点是不是在材料移动时跟着表面走，是否始终对着炉内固定位置。这个动作能帮助区分材料相关的信号和观察条件相关的信号，也能说明为什么某些工况只适合报告区域温度。

### 在热像上画线时，选择哪条线

圆棒的温度剖面常沿轴向读取，但轴向与相机画面的竖直方向未必完全一致。如果在两幅图上都直接选取中央像素列，一条线可能沿着圆棒中线，另一条却从中线斜穿到边缘。此时后半段温度变化可能来自观察角度或背景混入。可以先在试样坐标中选取材料路径，在各自图像中画出这条路径的投影，再标明两种观测共同覆盖的起点与终点。沿路径报告物理距离，后来更换镜头或裁切图像时也能复现位置。

进一步比较两条剖面时，可先划分带内、带边和远离集中区的背景段。在带宽能够分辨的情况下，带内温度整体变化与单点变亮有不同含义：前者在一段连续位置上都能看出趋势，后者则需要回查反射、热像坏点或边界像素。若应变带的宽度已经小于热像可分辨尺度，应将整段热像读取视作邻域信息，保留应变场自身更细的带宽描述。两套仪器各自的分辨能力都能保留下来，读者也能知道叠图最细可以读到哪一层。

剖面图旁最好附一张原始轮廓与路径示意，标出圆棒朝向、坐标原点和共同可见范围。仅留下两条看起来起伏相似的曲线，试验交接后就很难追溯它们究竟来自同一块表面，还是来自两条恰好形状相似的取样线。

<a id="chinese-section-7"></a>

## 怎么判断“重合”这个词用得是否合适

热像上一个有效测量区域可能覆盖应变带和两侧材料。此时热像记录包含邻近表面的贡献，最亮位置也会受观察范围和分辨率影响。如果两个峰值之间的距离与配准偏差相当，较为稳妥的表述是“在同一局部区域观察到温度与应变变化”。要精确报告峰值间距，则应同时交代空间尺度、有效视野和定位偏差。

公开试验提供了同步位移、应变和温度记录。上面的三种方法是利用这类记录开展分析时可以选择的路径。做均温检查可以采用分区比较；追溯颈缩区的材料经历，应采用跟随材料的区域；评估细小热点时，则需要先确认现有热像能否分辨目标。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [225 · 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#chinese-version)

</details>

<details>
<summary><b>English · Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields</b></summary>

<a id="english-version"></a>

# Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields

*Measuring deformation and damage at elevated temperature · Method comparison*

“The middle of the gauge section was warmer,” “the neck region was warmer,” and “the temperature and strain peaks coincided” require different levels of spatial evidence. XTDIC and infrared cameras observe a round bar from their respective viewpoints. Once the records are synchronized, the choice of spatial comparison depends on whether the conclusion concerns a section, a particular material patch or a local maximum.

**Contents**

- [Comparing the available methods](#english-section-1)
- [Applying the distinction to a strain band](#english-section-2)
- [Why a round bar differs from a flat coupon](#english-section-3)
- [Checking the mapping independently](#english-section-4)
- [Example of a temperature history for the eventual neck](#english-section-5)
- [Testing sensitivity to location](#english-section-6)
- [Choosing the precision of the claim](#english-section-7)

<a id="english-section-1"></a>

## Comparing the available methods

| Method | What is sampled | Suitable question | Main limitation |
| --- | --- | --- | --- |
| Gauge-section zones | End and central regions defined in both views | Where does a temperature difference persist after the hold? | Limited localization of a narrow band |
| Fixed spatial region | The same location in camera coordinates | How does temperature at a furnace location evolve? | Material can pass through the region |
| Material-following region | A surface patch tracked by DIC and located in each thermogram | What history did the future neck experience? | Requires registration and valid tracking |

<a id="english-section-2"></a>

## Applying the distinction to a strain band

For a temperature-uniformity check, splitting the gauge length into zones can be sufficient. Compare the temperature ranges near the centre and ends and examine whether the difference persists during the hold. Asking whether the material that eventually necked was already warm requires another sampling strategy. During tension, the gauge section extends. A stationary cursor in the middle of the screen can sample a succession of different pieces of metal.

A material-following comparison tracks a patch in DIC and finds its counterpart in the thermal image. This spatial correspondence is called registration. Features at known common locations establish the mapping, and independent features can test its error. Curvature limits how much of the round bar both cameras can see. When a patch moves out of either usable view, the comparison ends for those frames.

<a id="english-section-3"></a>

## Why a round bar differs from a flat coupon

Viewed from the front, the gauge section resembles a rectangular strip. Away from the centreline, the surface turns away from the viewer. A narrow column of image pixels may then cover a relatively wide piece of the curved surface. In a second view that piece may be close to the edge or hidden by the bar. Matching the left and right silhouettes in both images can align the apparent outlines while leaving the material between them incorrectly paired.

For a screening comparison, restrict the study to a shared frontal region with clear views and exclude the narrow zones near tangency. Finer localization can use the surface reconstructed by stereo DIC and the thermal camera pose to project patches into the thermal image. If calibration established a mapping only for one plane, assess how far the observed surface departs from it. As a neck develops, its changing curvature can progressively invalidate an initial planar approximation.

<a id="english-section-4"></a>

## Checking the mapping independently

Small errors on the same features used to fit a mapping primarily show how well it fits those observations. Reserve identifiable locations near the centre, ends and intended measurement area. Project these independent locations into the thermogram, record each difference between prediction and observation and convert it to an approximate specimen distance using the local image scale.

Keep the direction as well as the magnitude of each error. A common offset suggests checking camera or support movement. Small central errors increasing toward the edges warrant examination of curvature, distortion or a planar approximation. Arrows plotted at the check locations give a better picture of where narrow-band comparisons are credible than a single average error. Local error matters particularly when the result of interest lies at the edge.

<a id="english-section-5"></a>

## Example of a temperature history for the eventual neck

Start from a frame in which narrowing is visible but the outline is intact. Select a material region along the bar. Where DIC tracking remains valid, trace that region back to the end of the hold and project its successive positions into the thermograms. Choose a control region away from the band with comparable viewing angle and coating. This limits differences attributable to surface condition or geometry when comparing the two histories.

Record the valid thermal coverage as well as the temperature. A region well sampled before necking can later cover few valid pixels, with background radiation contributing at the boundary. A reduced usable area may be reported if the change is marked. If what remains no longer represents the original material, end that history and report subsequent observations separately. A visually continuous curve alone does not establish material continuity.

<a id="english-section-6"></a>

## Testing sensitivity to location

Move a region slightly in directions and by distances consistent with measured registration error, then read the thermal history again. If all plausible placements retain a persistent temperature excess over the control, a regional conclusion has support. If a small shift removes or reverses the difference, report the spatial range and retain the thermograms for review.

Regional mean and local maximum answer different questions. A mean describes a patch as a whole. A maximum is more sensitive to an isolated pixel, reflected radiation or background near an edge. If they diverge, inspect whether the bright area follows the moving material or stays fixed in the furnace view. This helps decide whether a temperature can reasonably be attributed to a particular surface region.

### Selecting a line for a thermal profile

The bar axis may be tilted relative to the image vertical. Taking the central pixel column in each view can therefore sample the centreline in one image and drift toward the edge in the other. Define a material path on the specimen first, project it into each image and identify the ends of common coverage. Distance along that path remains reproducible after a change of lens or image crop.

Identify the band interior, its boundary and a remote reference region on the profiles. Where the band is resolved, warming across a continuous region carries different evidence from a lone bright pixel, which warrants checks for reflections, a bad pixel or an edge effect. Where the thermal resolution is coarser than the strain band, report the thermal profile as neighbourhood information and retain the finer strain width separately.

A specimen outline showing the sampled path, origin, orientation and common coverage lets a later analyst determine whether two similar profiles actually came from the same material.

<a id="english-section-7"></a>

## Choosing the precision of the claim

A thermally resolved area may include a narrow strain band and the surface on either side. Neighbouring radiation contributes to the reading, and the position of the apparent maximum depends on spatial resolution. When the separation between two peaks is comparable to registration error, the evidence supports changes in the same local region. Reporting a peak-to-peak distance also calls for the spatial scale, valid common field of view and localization error.

The published experiment provides synchronized displacement, strain and temperature records. The three methods above describe possible analyses of such records. Zonal comparison serves thermal uniformity studies. Tracking serves material histories. Investigating a small hot spot first requires evidence that the thermal view resolves the target.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [225 · High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#english-version)

</details>
