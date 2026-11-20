# 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 试验方案*

高温炉中的同一根金属圆棒，对两套相机提出了不同要求。XTDIC 需要能随材料移动并持续辨认的表面纹理；热像仪需要知道有多少红外辐射由试样发出，又有多少来自反射或观察窗本身。配置联合试验时，要把散斑、可见光光路和红外光路分别核查，再决定哪些区域可以同时用于应变和温度分析。

**本文目录**

- [测试难点来自哪里](#chinese-section-1)
- [XTDIC 案例怎样建立可用的变形记录](#chinese-section-2)
- [同一表面怎样用于红外测温](#chinese-section-3)
- [入炉前怎样试做散斑](#chinese-section-4)
- [炉窗更换后，哪些检查必须重做](#chinese-section-5)
- [复核实例：一块亮斑跟不跟试样走](#chinese-section-6)
- [选区失效后怎样决定是否复测](#chinese-section-7)
- [方案适用边界](#chinese-section-8)

<a id="chinese-section-1"></a>

## 测试难点来自哪里

圆棒表面光滑，拉伸前后相邻位置在可见光照片里可能很相似。升温还会改变亮度和图案对比度，使原本可跟踪的区域变得模糊。炉窗的折射会影响双目重建时物点的位置；热像仪工作在不同于可见光的波段，一块肉眼透明的窗口，其红外透过率仍需按实际波段确认。这几种干扰作用在不同环节，单纯增加照明无法一并解决。

<a id="chinese-section-2"></a>

## XTDIC 案例怎样建立可用的变形记录

公开试验在圆棒工作段制备耐高温无机散斑，让双目相机在加载期间跟踪同一片表面。案例还说明了针对炉窗的折射校准。实际部署时，应在与试验一致的观察条件下检查标定和成像，保留保温阶段的照片作参考。若试样尚未加载，图像中却出现移动的波纹，应先排查热气流等光学因素。若只有一小块花纹开裂或剥落，则要在后续分析中单独标记这块区域。

<a id="chinese-section-3"></a>

## 同一表面怎样用于红外测温

热像仪把接收到的辐射换算成温度，需要考虑表面发射率，也就是材料表面在该波段发射热辐射的能力。涂层和裸露金属即使同温，也可能给出不同的辐射信号。若涂层边缘在加载前就呈现明显温差，加载后出现相似边界时，直接把它归因于塑性发热就缺少依据。

| 观察到的现象 | 可以安排的核查 | 对分析区域的处理 |
| --- | --- | --- |
| 保温时散斑局部脱落 | 回看原始照片，检查时间上的连续性 | 标记失去跟踪的区域和起始帧 |
| 热像明暗边界与涂层边缘一致 | 对照加载前热像，检查发射率设置和独立温度参考 | 单独评估该处测温可信度 |
| 两个镜头对圆棒边缘的可见范围不同 | 对照轮廓与相机视角 | 取两路都能可靠观测的表面范围 |

<a id="chinese-section-4"></a>

## 入炉前怎样试做散斑

制备散斑时，实验室容易先看涂层在肉眼下是否黑白分明。真正参与计算的却是相机在工作距离和曝光条件下拍到的小片图案。斑点太密，缩小到最终图像后可能连成一片灰色；斑点太稀，软件用于比对的一小块图像里又缺少足够独特的特征。可以先用与正式试样表面处理一致的留样试做，在实际镜头、视场和照明下拍摄，放大检查中部和弧面两侧是否都能辨认局部花纹。

耐温也不只意味着涂层在保温后仍然看得见。试样受拉时，涂层还要随基体延展。若涂层像薄壳一样整体滑移，图像可能十分清晰，计算也能跟到图案，但跟到的运动属于涂层。复核时可同时查看涂层边界、裸露可辨特征和试样轮廓，检查三者的运动趋势是否协调。若要比较两种表面处理，应在相近热历程与拍摄条件下分别观察附着状态、花纹稳定性和热像读数，再决定正式试验使用哪种处理。

<a id="chinese-section-5"></a>

## 炉窗更换后，哪些检查必须重做

**可见光一侧。** 窗口的厚度、安装角度和相机观察方向共同影响折射路径。若更换窗口或重新装夹相机，应在正式观察路径下检验测量尺度和重建结果。一个便于理解的检查是让带有稳定纹理的对象整体移动，观察计算出的位移是否与已知运动一致，并查看本应接近零的应变是否出现固定的空间图案。这种试验能发现光路或标定问题。它和高温保温下的稳定性检查各自针对不同干扰。

**红外一侧。** 需确认热像仪对应波段的窗口材料、表面状态和当前温度。窗口污染会改变实际透过的信号，炉壁和周围发热部件还可能在金属表面形成反射。可在可行的位置放置独立温度参考，并尽量保证它和目标区域处于可比的热环境。接触式参考与试样的接触状况、位置和响应速度也会引入差异，所以出现读数偏差时，应先确定两种方法实际观察的是不是同一位置和同一热状态。

<a id="chinese-section-6"></a>

## 复核实例：一块亮斑跟不跟试样走

设想保温时圆棒一侧有一块亮斑。开始拉伸后，圆棒上的材料向上移动，亮斑却仍停在画面里相近的位置。这个现象提示应检查反射源、窗口或背景。另一个可能的情况是亮斑始终贴着同一片散斑移动，且在加载前就已经存在。此时材料表面状态造成的辐射差异值得优先检查。只有在保温基线、表面处理和光路影响都得到解释以后，加载阶段新出现并随局部化发展的温度变化才适合进一步分析。这是故障排查示例，实际归因还需要相应对照。

若同一时间在应变图也出现了窄带，回查原始双目照片往往比同时调两套后处理参数更有效。两路可见光图像都能认出连续花纹，而热像读数只在涂层边界突变，应优先核查红外测温；若其中一台可见光相机拍到过曝白斑，双目重建在此处就可能失去有效匹配。分别标记哪个通道失效，仍可保留其他通道在该时段可靠的记录。

<a id="chinese-section-7"></a>

## 选区失效后怎样决定是否复测

局部失去跟踪是否影响整件试验，取决于研究问题。若只考察某一均匀阶段的平均轴向伸长，而有效选区仍覆盖定义好的标距两端，可对该阶段保留结果，并说明剔除了哪些位置。若目的是确定颈缩带的最大局部应变，缺失区域又正好位于带中心，则周围仍有数据也无法补足该量。应先确定失效源，再调整布光、窗口或散斑工艺，使用可比较的新试样复测。

交付时把有效区域叠在照片上比单独列出剔除比例更清楚。失去一小片与研究目标无关的边缘，和失去同样大小的颈缩中心，对结论的影响截然不同。写明失效位置、开始时刻和仍能回答的问题，读者就能判断这次测量还适合支持哪项工程决定。

### 从一次试拍决定调整哪一项

当高温图像不够清晰时，先把问题按出现的阶段分开。室温下已经模糊，优先检查对焦、景深和曲面对视角的影响。升温后才逐渐消失的纹理，需分别检查热辐射造成的亮度变化、热空气扰动以及涂层本身是否发生变化。只有加载后迅速恶化，则需查看曝光期间运动造成的拖影、散斑随拉伸变稀和试样移出原焦面等因素。根据阶段选择复查对象，可以避免每次同时改变光源、涂层和曝光，最后无法确定哪项调整起了作用。

例如想判断换用另一种可见光照明是否有帮助，可以先保留试样和相机位置，以相近热状态比较新旧照明下的原始散斑图像，观察亮部是否饱和、暗部是否仍有纹理以及两台相机的共享区域是否变小。随后单独复核热像，因为照明改善了可见光对比度，并不能自动修正红外反射或窗口辐射。应把调整前后的原始帧与处理设置成对保存，供之后的试验复用。

完整的选型依据还包括实验室需要什么结果。若只追踪较宽工作段的平均伸长，适合该任务的光学配置未必能分辨窄小颈缩带；若要定量描述颈缩中心附近的温升，哪怕全幅热像视觉上很清楚，也要核实该处的有效覆盖和表面状态。在方案阶段把最终要读的量写清楚，更容易决定下一次试拍是扩大视野、提高局部采样，还是安排独立温度核查。

<a id="chinese-section-8"></a>

## 方案适用边界

上述核查适用于透过观察口开展的高温拉伸，也适用于更换散斑工艺、窗口或热像仪之后的复测。交付结果时，保留一张加载前的可见光图、一张对应热像，以及可用于联合分析的区域说明，比只给出最后一幅彩色云图更方便复核。公开案例确认了散斑处理、炉窗校准及同步采集；表中的异常是方案设计时需要考虑的情形，不代表该案例实际发生过。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [226 · 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#chinese-version)

</details>

<details>
<summary><b>English · High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks</b></summary>

<a id="english-version"></a>

# High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks

*Measuring deformation and damage at elevated temperature · Test configuration*

The same hot round bar places different demands on its cameras. XTDIC needs a recognisable surface texture that moves with the material. A thermal camera needs information about radiation emitted by the specimen, reflected from its surroundings and transmitted or emitted by the window. A joint test therefore calls for checks on speckles and on each optical path before selecting an area for combined strain and temperature analysis.

**Contents**

- [Sources of difficulty](#english-section-1)
- [Establishing a deformation record](#english-section-2)
- [Using the surface for infrared thermometry](#english-section-3)
- [Testing the pattern before installing a specimen](#english-section-4)
- [Checks after a window change](#english-section-5)
- [Diagnostic example of a bright patch](#english-section-6)
- [Deciding whether to repeat a test](#english-section-7)
- [Scope of the arrangement](#english-section-8)

<a id="english-section-1"></a>

## Sources of difficulty

Adjacent points on a smooth bar can look alike in visible photographs. Heating changes brightness and contrast, and a trackable region can become indistinct. Window refraction affects the location reconstructed by the stereo system. A window transparent to the eye also needs a transmission check in the infrared camera’s wavelength band. These effects enter at different stages of the measurement.

<a id="english-section-2"></a>

## Establishing a deformation record

The published experiment used heat-resistant inorganic speckles on the gauge section and corrected for refraction through the furnace window. In an implementation, check calibration and image quality through the actual observation path and keep images from the hot hold as a reference. Ripples crossing a stationary, unloaded specimen warrant a check for optical disturbances such as moving hot air. Local cracking or loss of the speckle coating calls for marking the affected region and frames.

<a id="english-section-3"></a>

## Using the surface for infrared thermometry

Converting received radiation into temperature requires the surface emissivity in the relevant wavelength band. A coating and exposed metal can emit different amounts of radiation at the same temperature. If an apparent temperature step already follows a coating edge before loading, a similar boundary during pulling needs additional evidence before it can be attributed to plastic heating.

| Observation | Check | Treatment in analysis |
| --- | --- | --- |
| Local speckle loss during the hold | Inspect the original image sequence | Mark where and when tracking was lost |
| Thermal contrast follows a coating edge | Review the unloaded thermogram, emissivity and independent temperature reference | Assess local temperature reliability separately |
| The cameras see different portions of the curved edge | Compare outlines and viewing angles | Use the common observable surface |

<a id="english-section-4"></a>

## Testing the pattern before installing a specimen

A pattern can look crisp to the eye and still be unsuitable at the actual working distance and exposure. Dense dots can merge into grey in the recorded image. Sparse dots may leave a correlation patch with too little distinctive texture. A witness piece with the same surface preparation allows a trial using the intended lens, field of view and lighting. Inspect recognisable patterns at the centre and along both curved sides.

Surviving the hold is only part of the requirement. The coating must deform with the substrate during pulling. A coating that slips as a shell can produce sharp, readily tracked images of the wrong motion. Compare coating boundaries, any recognisable exposed features and the specimen outline for compatible movement. When evaluating two treatments, compare adhesion, pattern stability and thermograms under similar thermal and imaging conditions.

<a id="english-section-5"></a>

## Checks after a window change

**Visible-light path.** Window thickness, mounting angle and camera orientation affect refraction. After replacing a window or moving a camera, check the measurement scale and reconstruction through the actual optical path. A rigid translation of a textured target offers a practical check. Compare measured and known movement and inspect the nominally zero strain field for fixed spatial patterns. This check addresses geometry. A stability check during the hot hold addresses disturbances under operating conditions.

**Infrared path.** Confirm the window material and its condition and temperature for the camera’s wavelength band. Deposits can alter transmission, and hot furnace surfaces can be reflected by the metal. Where feasible, use an independent temperature reference in a comparable thermal environment. A contact reference has its own contact, location and response-time effects. A disagreement warrants checking that both methods sampled a comparable place and thermal state.

<a id="english-section-6"></a>

## Diagnostic example of a bright patch

Suppose a bright area appears during the hold. The bar moves upwards during loading but the bright patch stays near a fixed image location. Inspect reflections, the window and the background. If instead it follows the same speckles and already existed before loading, surface radiation properties merit attention. New warming associated with localization becomes more interpretable once pre-load contrast and optical effects have been considered. These are diagnostic scenarios requiring independent controls for attribution.

When a strain band appears at the same time, the original stereo photographs can help identify the affected channel. If both views retain continuous texture and the thermal step follows a coating edge, inspect the thermal measurement first. If one visible camera recorded a saturated patch, stereo matching there may be invalid. Marking each channel separately preserves the useful observations from the other instruments.

<a id="english-section-7"></a>

## Deciding whether to repeat a test

The consequence of lost tracking depends on the question. Average extension during uniform tension may remain available if both ends of the defined gauge length are observed. Report the usable interval and excluded locations. For peak local strain at the neck, loss of its centre leaves that quantity unresolved even with good surrounding data. Identify the cause, adjust the lighting, window or pattern and repeat using a comparable specimen if that quantity matters.

An overlay of valid regions communicates more than a percentage of discarded pixels. A small loss at a remote edge and an equal loss in the middle of the neck have different implications. Report where a signal failed, when it failed and which engineering question the remaining observations can still answer.

### Choosing the next adjustment from a trial exposure

Classify a loss of image quality by its onset. Blur already visible at room temperature points first to focus, depth of field and viewing angle. Texture that fades during heating warrants separate checks on changing brightness, disturbed air and coating condition. Degradation during loading calls for inspection of motion blur, dilution of the pattern and movement out of focus. Changing one relevant setting at a time makes it possible to identify which adjustment helped.

To evaluate a different visible light source, hold specimen and camera positions fixed. Compare raw images at similar thermal states for saturated bright areas, remaining dark texture and common stereo coverage. Check the thermograms separately: improved visible contrast does not correct infrared reflections or window emission. Retain paired exposures and settings for the next run.

Tie the final choice to the required result. Optics suitable for average extension over a broad gauge may not resolve a narrow neck. A thermal view that looks clear overall still needs adequate local coverage and a characterised surface at the neck centre. Defining the target quantity helps select a wider view, finer local sampling or an independent temperature check.

<a id="english-section-8"></a>

## Scope of the arrangement

These checks apply to tensile tests through furnace ports and to repeat tests after a change of coating, window or thermal camera. A pre-load photograph, its matching thermogram and a record of the valid common area make final maps easier to audit. The public case documents the speckle preparation, window calibration and synchronous acquisition. The anomalies in the table are implementation considerations, not reported events in that specimen.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [226 · Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#english-version)

</details>
