# 高温材料局部损伤监测：XTDIC 全场应变与红外温度场联合定位方案

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温材料局部损伤监测：XTDIC 全场应变与红外温度场联合定位方案</b></summary>

<a id="chinese-version"></a>

高温材料的局部变形往往隐藏在整体伸长之中。某一小段持续拉长时，试验机仍可能给出平滑的载荷曲线；局部温差也可能被单个控温读数掩盖。XTDIC 三维应变测量与红外热像相结合，可在可见工作段内定位变形集中区域，并追踪对应材料的表面温度，为局部损伤研究、热处理评价和试样结构优化提供空间依据。

**目录**

- [高温试样局部异常的识别需求](#chinese-section-1)
- [三维表面测量与温度定位协同](#chinese-section-2)
- [从整段热状态到局部材料历程](#chinese-section-3)
- [曲面试样的共同视野与三维对应](#chinese-section-4)
- [空间配准的独立验证](#chinese-section-5)
- [颈缩候选区的材料温度历程](#chinese-section-6)
- [局部热区的位置敏感性分析](#chinese-section-7)
- [测量结果在材料研发中的用途](#chinese-section-8)
- [应用问答](#chinese-section-9)

<a id="chinese-section-1"></a>

## 高温试样局部异常的识别需求

材料的组织状态、截面过渡、装夹约束和局部温度都可能影响变形分配。研究人员需要先找到异常区域，再判断它的形成过程。对于细长试样，沿轴线的平均值便于描述总体趋势；对于未来可能形成细颈的区域，还需要保持对同一片材料的连续观察。

全场应变测量可以在试验结束后回到原始图像，选择集中带以及带外的邻近区域进行对照。这种先记录整体、再提取局部的工作方式，适合集中位置事前无法准确预测的材料试验，也便于在同一批数据上检验不同的分析假设。

<a id="chinese-section-2"></a>

## 三维表面测量与温度定位协同

XTDIC 从双目图像恢复可见表面的空间运动，使目标区域具有随材料变化的位置。红外相机提供另一视角的温度分布。通过建立两种观测之间的空间对应，可把温度信息赋给所观察的材料区域，从而形成局部应变与温度随加载变化的联合记录。

这种配置的工程价值体现于位置可追溯。研究人员能够说明温度来自哪个表面区域，所取区域在拉伸后移动到哪里，以及热像实际覆盖了多少有效材料。对曲面试样，应结合表面形状和相机视角确定共同可见范围，以免把边缘背景或另一侧材料读入温度结果。

<a id="chinese-section-3"></a>

## 从整段热状态到局部材料历程

测试设计可以从宽到窄展开。保温阶段先比较工作段各区域的温度，确认材料的初始热状态；加载初期观察位移与应变是否平缓；局部化发展后，沿材料轨迹追踪集中区和对照区。三个阶段使用的尺度不同，但都依托同一坐标与时间记录。

若试样在运动中转出热像视野，应保留这一段的有效性标记。局部热区比热像分辨尺度更小时，可报告邻域温度及其变化，并继续保留应变场自身能够分辨的细节。对研发人员而言，知道每项结果覆盖的真实区域，比单纯叠加两张彩色图更方便进一步建模。

<a id="chinese-section-4"></a>

## 曲面试样的共同视野与三维对应

从正面看，圆棒的工作段像一条长方形色带。实际上，中线两侧的表面逐渐转向侧面。在一台相机里只占很窄的一列像素，放到圆棒曲面上却可能覆盖较宽的一片材料。另一台侧向布置的相机看过去，这片材料可能位于视野边缘，甚至被圆棒自身遮挡。因此，以两幅图中轮廓的左边和右边分别对齐，只能保证可见轮廓看起来接近；两个轮廓之间的材料仍可能一前一后。

做初步筛查时，可将研究范围限在两套设备都能清楚看到的工作段正面，把靠近切线方向的细窄边缘留在比较范围之外。对精细定位，可以利用双目 DIC 重建的表面形状，根据热像仪与这套坐标系的相对位置，将表面区域投影到热像中。若装置只对某一平面建立了映射，需要核对圆棒表面偏离该平面的程度。颈缩加深后曲面发生变化，加载前建立的平面对应关系也可能逐渐失去适用性。

<a id="chinese-section-5"></a>

## 空间配准的独立验证

校准时若用一组特征求得映射，再用完全相同的一组特征检查，得到的小偏差主要说明计算能解释这些点。为了知道它在真正关心的位置是否可用，可以留出一组没有参与拟合的可识别位置，分布在工作段中部、两端及实际要读数的区域附近。将其投影到热像后，记录预测位置和观察位置的距离，并用当地的图像比例估算它在试样上大约占多宽。

这些偏差的方向也值得保留。若所有点都朝相近方向偏移，可优先检查相机或支架位置是否有变化；若中间较准而越到边缘越偏，应审视曲面、镜头畸变或平面近似带来的影响。把偏差在图上画成带方向的小箭头，往往比只给出全幅平均误差更能说明哪里可以追踪窄带。图像边缘正好是结论所在的位置时，局部偏差比全幅平均更重要。

<a id="chinese-section-6"></a>

## 颈缩候选区的材料温度历程

假设希望比较颈缩区与附近完整区域的热历程。可以从轮廓仍完整、细颈已可辨认的一帧着手，沿着圆棒轴向圈定一小块目标材料。在 DIC 有效的前提下，把这个区域追溯至保温结束时，再将它在各时刻的位置映射到相应热像上。邻近对照区可选在相似视角、相似涂层但远离明显变形带的位置。这样比较起来，表面状态与观察方向的差异较小，判断更集中于材料经历的差别。

读取温度时，应同时记录选区内有效热像像素的覆盖情况。颈缩前宽裕的区域，颈缩后可能只剩少量像素可靠地落在试样上，边缘点还可能混入炉内背景。此时可收缩可用区域，但要在曲线上注明选区发生改变的时刻；如果保留下来的已不是同一片材料，则应结束原曲线，另列后续观察。整条曲线看起来连续，并不自动意味着被测对象一直相同。

<a id="chinese-section-7"></a>

## 局部热区的位置敏感性分析

对结论影响较大的热区，可以把选定区域按校核得到的配准偏差向周围小幅移动，重新读取温度趋势。若这些合理的位置变动都保留了“该区域较邻近区持续偏热”的判断，区域层面的结论就有较好的支撑。若仅把选区挪到另一侧，温度差便消失甚至反向，说明结果对边界很敏感，此时宜扩大报告的位置范围，并保留原始热像供复查。

还可以比较区域平均温度和局部最高温度。平均值有助于描述一片材料的整体变化，最高值则对单个异常像素、反射亮点或背景混入更加敏感。二者分歧时，回看热点是不是在材料移动时跟着表面走，是否始终对着炉内固定位置。这个动作能帮助区分材料相关的信号和观察条件相关的信号，也能说明为什么某些工况只适合报告区域温度。

### 在热像上画线时，选择哪条线

圆棒的温度剖面常沿轴向读取，但轴向与相机画面的竖直方向未必完全一致。如果在两幅图上都直接选取中央像素列，一条线可能沿着圆棒中线，另一条却从中线斜穿到边缘。此时后半段温度变化可能来自观察角度或背景混入。可以先在试样坐标中选取材料路径，在各自图像中画出这条路径的投影，再标明两种观测共同覆盖的起点与终点。沿路径报告物理距离，后来更换镜头或裁切图像时也能复现位置。

进一步比较两条剖面时，可先划分带内、带边和远离集中区的背景段。在带宽能够分辨的情况下，带内温度整体变化与单点变亮有不同含义：前者在一段连续位置上都能看出趋势，后者则需要回查反射、热像坏点或边界像素。若应变带的宽度已经小于热像可分辨尺度，应将整段热像读取视作邻域信息，保留应变场自身更细的带宽描述。两套仪器各自的分辨能力都能保留下来，读者也能知道叠图最细可以读到哪一层。

剖面图旁最好附一张原始轮廓与路径示意，标出圆棒朝向、坐标原点和共同可见范围。仅留下两条看起来起伏相似的曲线，试验交接后就很难追溯它们究竟来自同一块表面，还是来自两条恰好形状相似的取样线。

<a id="chinese-section-8"></a>

## 测量结果在材料研发中的用途

在热处理工艺筛选中，可比较不同状态下的集中带是否在相近热条件下形成，结合断后形貌研究变形分配。对于几何过渡或连接附近的试样，可用局部场判断异常是否始终伴随同一结构位置，为改进试样设计和加载方式提供依据。

XTDIC 联动热像的适用价值，是让材料团队在单次测试中同时获得位置、伸长与热状态，并能反复选区分析。设备配置应围绕实际试样的共同视野、曲率和最小目标区域验证，交付数据则保留坐标、时间、有效区域与处理参数，使不同批次的试验具有可比较的基础。

<a id="chinese-section-9"></a>

## 应用问答

**哪些试样适合联合定位？**

两套相机能够共同观察、表面具有可跟踪纹理且红外条件可校核的试样，更适合开展联合定位。曲面对象需要确认各时刻的共同可见区域。

**局部选区能否在试验后调整？**

原始图像和坐标保存完整时，可重新定义有效区域并提取历程。分析精细程度仍由原始采样和两种测量的空间分辨能力决定。

**技术资料**

[设备与应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [应用素材](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>English · Localizing High-Temperature Material Damage with XTDIC Strain Fields and Thermography</b></summary>

<a id="english-version"></a>

# Localizing High-Temperature Material Damage with XTDIC Strain Fields and Thermography

Local extension and temperature differences can be hidden within smooth global force records. Combining XTDIC stereo strain measurement with thermography locates concentrated deformation and follows the surface temperature of the corresponding material, supporting heat-treatment assessment, specimen development and damage research.

**Contents**

- [The need to locate local changes](#english-section-1)
- [Combining surface reconstruction and temperature](#english-section-2)
- [From gauge-section conditions to material histories](#english-section-3)
- [Why a round bar differs from a flat coupon](#english-section-4)
- [Checking the mapping independently](#english-section-5)
- [Example of a temperature history for the eventual neck](#english-section-6)
- [Testing sensitivity to location](#english-section-7)
- [Use in materials development](#english-section-8)
- [Application questions](#english-section-9)

<a id="english-section-1"></a>

## The need to locate local changes

Microstructure, section transitions, gripping and temperature can all affect the distribution of extension. Full-field acquisition allows a concentrating region and neighbouring control to be selected after the run, which is useful when the eventual site is unknown before testing.

<a id="english-section-2"></a>

## Combining surface reconstruction and temperature

Stereo reconstruction supplies the spatial motion of the visible surface. Registering the infrared view to that surface associates temperature with material regions. For curved specimens, shared visibility must be established so that an edge or background does not enter the temperature history.

<a id="english-section-3"></a>

## From gauge-section conditions to material histories

Begin with thermal zones during the hold, inspect distributed motion early in loading and then follow the concentrating patch. Preserve validity flags if it leaves the thermal view. When thermal resolution is coarser than the strain band, report neighbourhood temperature alongside the finer strain information.

<a id="english-section-4"></a>

## Why a round bar differs from a flat coupon

Viewed from the front, the gauge section resembles a rectangular strip. Away from the centreline, the surface turns away from the viewer. A narrow column of image pixels may then cover a relatively wide piece of the curved surface. In a second view that piece may be close to the edge or hidden by the bar. Matching the left and right silhouettes in both images can align the apparent outlines while leaving the material between them incorrectly paired.

For a screening comparison, restrict the study to a shared frontal region with clear views and exclude the narrow zones near tangency. Finer localization can use the surface reconstructed by stereo DIC and the thermal camera pose to project patches into the thermal image. If calibration established a mapping only for one plane, assess how far the observed surface departs from it. As a neck develops, its changing curvature can progressively invalidate an initial planar approximation.

<a id="english-section-5"></a>

## Checking the mapping independently

Small errors on the same features used to fit a mapping primarily show how well it fits those observations. Reserve identifiable locations near the centre, ends and intended measurement area. Project these independent locations into the thermogram, record each difference between prediction and observation and convert it to an approximate specimen distance using the local image scale.

Keep the direction as well as the magnitude of each error. A common offset suggests checking camera or support movement. Small central errors increasing toward the edges warrant examination of curvature, distortion or a planar approximation. Arrows plotted at the check locations give a better picture of where narrow-band comparisons are credible than a single average error. Local error matters particularly when the result of interest lies at the edge.

<a id="english-section-6"></a>

## Example of a temperature history for the eventual neck

Start from a frame in which narrowing is visible but the outline is intact. Select a material region along the bar. Where DIC tracking remains valid, trace that region back to the end of the hold and project its successive positions into the thermograms. Choose a control region away from the band with comparable viewing angle and coating. This limits differences attributable to surface condition or geometry when comparing the two histories.

Record the valid thermal coverage as well as the temperature. A region well sampled before necking can later cover few valid pixels, with background radiation contributing at the boundary. A reduced usable area may be reported if the change is marked. If what remains no longer represents the original material, end that history and report subsequent observations separately. A visually continuous curve alone does not establish material continuity.

<a id="english-section-7"></a>

## Testing sensitivity to location

Move a region slightly in directions and by distances consistent with measured registration error, then read the thermal history again. If all plausible placements retain a persistent temperature excess over the control, a regional conclusion has support. If a small shift removes or reverses the difference, report the spatial range and retain the thermograms for review.

Regional mean and local maximum answer different questions. A mean describes a patch as a whole. A maximum is more sensitive to an isolated pixel, reflected radiation or background near an edge. If they diverge, inspect whether the bright area follows the moving material or stays fixed in the furnace view. This helps decide whether a temperature can reasonably be attributed to a particular surface region.

### Selecting a line for a thermal profile

The bar axis may be tilted relative to the image vertical. Taking the central pixel column in each view can therefore sample the centreline in one image and drift toward the edge in the other. Define a material path on the specimen first, project it into each image and identify the ends of common coverage. Distance along that path remains reproducible after a change of lens or image crop.

Identify the band interior, its boundary and a remote reference region on the profiles. Where the band is resolved, warming across a continuous region carries different evidence from a lone bright pixel, which warrants checks for reflections, a bad pixel or an edge effect. Where the thermal resolution is coarser than the strain band, report the thermal profile as neighbourhood information and retain the finer strain width separately.

A specimen outline showing the sampled path, origin, orientation and common coverage lets a later analyst determine whether two similar profiles actually came from the same material.

<a id="english-section-8"></a>

## Use in materials development

Compare heat treatments at comparable thermal states, and investigate whether localization repeatedly follows a geometric transition. The combined record provides position, stretch and thermal state within one run. Configure shared coverage for the actual curvature and target size and deliver coordinates, timing, valid areas and processing settings.

<a id="english-section-9"></a>

## Application questions

**Which specimens support joint localization?**

Those with shared visibility, trackable texture and characterised infrared conditions. Curved surfaces require time-dependent visibility checks.

**Can regions be changed later?**

Retained images and coordinates allow new valid regions to be analysed within the original spatial resolution.

**Technical resources**

[Equipment and application information](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [Application material in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
