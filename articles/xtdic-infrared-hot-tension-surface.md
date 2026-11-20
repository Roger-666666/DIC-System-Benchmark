# 高温炉内非接触应变测量：XTDIC 光学测试系统的配置与应用

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [实验室对高温光学测量的需求](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [XTDIC 系统构成与工作方式](#chinese-section-4)
- [从成像质量到可靠应变结果](#chinese-section-5)
- [高温散斑的制备与适用性验证](#chinese-section-6)
- [炉窗与双通道光路校核](#chinese-section-7)
- [有效区域与试验结果的完整性](#chinese-section-8)
- [适用场景与配置选择](#chinese-section-9)
- [试验实施流程](#chinese-section-10)
- [XTDIC 设备定位与应用价值](#chinese-section-11)
- [常见问答](#chinese-section-12)
- [结语](#chinese-section-13)
- [参考资料](#chinese-section-14)

<a id="chinese-section-1"></a>

## 核心结论

高温炉内的材料试验需要同时满足加热、加载和观察要求。观察窗折射、热辐射、表面纹理变化以及试样运动，都会影响光学测量的有效范围。XTDIC 三维应变测量方案通过双目成像、适配高温的散斑和实际光路校核，将非接触测量引入炉内拉伸与变形研究；联合红外热像时，还能为力学响应补充表面温度条件。

数字图像相关（Digital Image Correlation，DIC）通过跟踪试样表面散斑的图像变化计算位移，并由位移的空间变化求取应变。红外热像补充表面温度信息，载荷则来自试验机或力传感器；这些通道建立时间与空间对应后，才构成可分析的热力耦合记录。

<a id="chinese-section-2"></a>

## 实验室对高温光学测量的需求

材料进入高温加载阶段后，观测条件会随时间改变。保温时对比度良好的花纹，拉伸后可能变稀；静止时完整的工作段，显著伸长后可能接近视野边缘。设计测试系统时，需要把初始图像和最终待观察状态一起考虑，确保所关心的过程具备连续的观测条件。

非接触方案的优势在于测量头可以布置在加载区外，虚拟标距和局部选区通过软件定义。材料研发人员既可以获得平均伸长，也可以研究同一工作段内不同位置的变形分配。对断前失稳研究，原始图像还保留了轮廓变化和表面特征，方便与计算结果相互核对。

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

高温炉内非接触测量的配置，应从测量对象、输出指标和研发用途之间的关系展开。下面的对应表可用于确定观察范围、数据通道与后续分析任务。

| 测量要素 | 配置或输出 | 工程用途 |
|---|---|---|
| 表面图像 | 双目测量头、镜头与照明 | 保留可计算的纹理与观察范围 |
| 高温适配 | 耐温散斑与实际炉窗光路校核 | 使测量条件覆盖保温及加载阶段 |
| 试验输出 | 虚拟标距、区域应变与三维位移 | 兼顾整体伸长与局部分析 |

<a id="chinese-section-4"></a>

## XTDIC 系统构成与工作方式

典型配置包括双目测量头、镜头与照明、稳定支架、图像采集和分析软件，并与试验机的加载记录建立时间联系。采用红外通道时，根据相机波段规划独立的辐射观测路径。可见光几何标定与红外温度校核各自服务于不同测量量，都应落实到最终使用的观察条件。

XTDIC 对表面纹理进行匹配并重建位移，随后计算应变。为了适应炉窗观测，应将窗口位置、相机朝向和视场纳入校核。工作段使用能够经历预定温度与变形过程的散斑，使纹理稳定附着于材料。配置的完整性体现在加载前、加载中和临近失效时都能说明哪些区域可靠。

<a id="chinese-section-5"></a>

## 从成像质量到可靠应变结果

试验可按室温检查、热态保温和正式加载逐段实施。室温阶段确认尺度、几何与花纹可辨性，热态阶段检查光路扰动和表观应变，加载阶段关注目标是否出画、拖影或局部失配。每个阶段保留原始图像，便于定位异常是从何时出现的。

计算时依据材料变形程度和花纹质量选择适当的相关与应变范围。较大的空间平均可能使图像更平稳，同时会摊开窄小局部化；更细的分析也需要足够清晰的原始纹理。设备评估因此应使用接近真实工况的试样，检查目标区域所能分辨的细节，而不只比较最终云图是否平滑。

<a id="chinese-section-6"></a>

## 高温散斑的制备与适用性验证

制备散斑时，实验室容易先看涂层在肉眼下是否黑白分明。真正参与计算的却是相机在工作距离和曝光条件下拍到的小片图案。斑点太密，缩小到最终图像后可能连成一片灰色；斑点太稀，软件用于比对的一小块图像里又缺少足够独特的特征。可以先用与正式试样表面处理一致的留样试做，在实际镜头、视场和照明下拍摄，放大检查中部和弧面两侧是否都能辨认局部花纹。

耐温也不只意味着涂层在保温后仍然看得见。试样受拉时，涂层还要随基体延展。若涂层像薄壳一样整体滑移，图像可能十分清晰，计算也能跟到图案，但跟到的运动属于涂层。复核时可同时查看涂层边界、裸露可辨特征和试样轮廓，检查三者的运动趋势是否协调。若要比较两种表面处理，应在相近热历程与拍摄条件下分别观察附着状态、花纹稳定性和热像读数，再决定正式试验使用哪种处理。

<a id="chinese-section-7"></a>

## 炉窗与双通道光路校核

**可见光一侧。** 窗口的厚度、安装角度和相机观察方向共同影响折射路径。若更换窗口或重新装夹相机，应在正式观察路径下检验测量尺度和重建结果。一个便于理解的检查是让带有稳定纹理的对象整体移动，观察计算出的位移是否与已知运动一致，并查看本应接近零的应变是否出现固定的空间图案。这种试验能发现光路或标定问题。它和高温保温下的稳定性检查各自针对不同干扰。

**红外一侧。** 需确认热像仪对应波段的窗口材料、表面状态和当前温度。窗口污染会改变实际透过的信号，炉壁和周围发热部件还可能在金属表面形成反射。可在可行的位置放置独立温度参考，并尽量保证它和目标区域处于可比的热环境。接触式参考与试样的接触状况、位置和响应速度也会引入差异，所以出现读数偏差时，应先确定两种方法实际观察的是不是同一位置和同一热状态。

<a id="chinese-section-8"></a>

## 有效区域与试验结果的完整性

局部失去跟踪是否影响整件试验，取决于研究问题。若只考察某一均匀阶段的平均轴向伸长，而有效选区仍覆盖定义好的标距两端，可对该阶段保留结果，并说明剔除了哪些位置。若目的是确定颈缩带的最大局部应变，缺失区域又正好位于带中心，则周围仍有数据也无法补足该量。应先确定失效源，再调整布光、窗口或散斑工艺，使用可比较的新试样复测。

交付时把有效区域叠在照片上比单独列出剔除比例更清楚。失去一小片与研究目标无关的边缘，和失去同样大小的颈缩中心，对结论的影响截然不同。写明失效位置、开始时刻和仍能回答的问题，读者就能判断这次测量还适合支持哪项工程决定。

### 从一次试拍决定调整哪一项

当高温图像不够清晰时，先把问题按出现的阶段分开。室温下已经模糊，优先检查对焦、景深和曲面对视角的影响。升温后才逐渐消失的纹理，需分别检查热辐射造成的亮度变化、热空气扰动以及涂层本身是否发生变化。只有加载后迅速恶化，则需查看曝光期间运动造成的拖影、散斑随拉伸变稀和试样移出原焦面等因素。根据阶段选择复查对象，可以避免每次同时改变光源、涂层和曝光，最后无法确定哪项调整起了作用。

例如想判断换用另一种可见光照明是否有帮助，可以先保留试样和相机位置，以相近热状态比较新旧照明下的原始散斑图像，观察亮部是否饱和、暗部是否仍有纹理以及两台相机的共享区域是否变小。随后单独复核热像，因为照明改善了可见光对比度，并不能自动修正红外反射或窗口辐射。应把调整前后的原始帧与处理设置成对保存，供之后的试验复用。

完整的选型依据还包括实验室需要什么结果。若只追踪较宽工作段的平均伸长，适合该任务的光学配置未必能分辨窄小颈缩带；若要定量描述颈缩中心附近的温升，哪怕全幅热像视觉上很清楚，也要核实该处的有效覆盖和表面状态。在方案阶段把最终要读的量写清楚，更容易决定下一次试拍是扩大视野、提高局部采样，还是安排独立温度核查。

<a id="chinese-section-9"></a>

## 适用场景与配置选择

该配置适用于高温金属拉伸、热处理状态对照以及材料局部失稳研究。需要表面温度与应变联系时，可以加入红外记录；需要更细局部尺度时，应根据视场与可见性重新选择光学配置。相同设备用于不同任务，其镜头、标距与分析区也应跟随研究目标调整。

实验室交付可以同时包含平均伸长、局部应变历程、位移场和对应照片。保留有效区域及参考状态后，同一组记录能够服务材料比较、模型验证和失效复盘。XTDIC 的应用价值由此落在可复用的测量信息上，使高温试验从单一整体曲线扩展到可定位的表面变形过程。

<a id="chinese-section-10"></a>

## 试验实施流程

### 确定任务与光学范围

围绕平均伸长或局部化任务选择工作段、视场和预期运动范围。

### 准备耐温表面纹理

检查散斑在室温和预定热历程下的可辨性及附着状态。

### 建立实际光路标定

将窗口、镜头和相机位置纳入几何验证，并核查红外路径。

### 按阶段实施测试

依次保存室温检查、热态基线与加载记录，跟踪图像质量变化。

### 输出有效结果

交付标距伸长、区域应变和对应原图，标明分析区域与有效时段。

<a id="chinese-section-11"></a>

## XTDIC 设备定位与应用价值

XTDIC 的设备角色是将炉内表面运动转化为可分析的三维位移与应变。测量头放在加载区域之外，分析区域和标距通过软件定义，便于在相同图像上同时观察整体伸长与局部变形。对试样装夹空间有限的场景，这种外置光学观察具有布置上的优势。

高温配置的有效性来自测量头、镜头、照明、散斑与观察窗共同适配。面向实验室建设，代表性试样上的热态验证可以形成可复用配置，后续在相近几何与热条件下开展材料对比，并根据新的目标区域调整分析尺度。

<a id="chinese-section-12"></a>

## 常见问答

### 更换炉窗后怎样继续使用系统？

根据新窗口及相机安装关系复核可见光几何，并按红外波段检查透过与辐射条件。保温阶段的基线有助于评价实际热态稳定性。

### 设备能否同时提供平均与局部伸长？

在有效图像范围内，可设置虚拟标距获得整体伸长，也可提取不同区域的局部应变。两类结果宜保留各自的空间范围与参考状态。

### 高温配置的设备验收应覆盖哪些阶段？

应覆盖室温几何检查、热态保温基线和代表性加载过程，确认目标区域在需要的阶段仍有可用图像与可靠重建结果。

<a id="chinese-section-13"></a>

## 结语

高温 DIC 配置应围绕实际试样、炉窗和热历程建立。散斑能否保留、光路是否稳定、有效区域能否覆盖关键阶段，共同决定可交付的结果。把这些工作纳入 XTDIC 的应用配置与方法交付，有助于实验室建立能够持续使用的高温全场测量能力。

<a id="chinese-section-14"></a>

## 参考资料

[XTDIC 高温变形应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC 与红外热像联测应用资料](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Configuring XTDIC for Non-Contact Strain Measurement Inside High-Temperature Furnaces

## Contents

- [Executive answer](#english-section-1)
- [Laboratory requirements](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [System configuration and operation](#english-section-4)
- [From images to strain results](#english-section-5)
- [Testing the pattern before installing a specimen](#english-section-6)
- [Checks after a window change](#english-section-7)
- [Deciding whether to repeat a test](#english-section-8)
- [Applications and configuration choices](#english-section-9)
- [Implementation workflow](#english-section-10)
- [XTDIC equipment positioning and application value](#english-section-11)
- [Frequently asked questions](#english-section-12)
- [Conclusion](#english-section-13)
- [References](#english-section-14)

<a id="english-section-1"></a>

## Executive answer

Furnace testing combines heating, loading and observation. Window refraction, radiation, changing texture and specimen motion affect optical measurements. Stereo imaging, heat-resistant patterns and checks through the actual optical path allow XTDIC to measure deformation without a contact extensometer at the gauge section. Thermography adds surface thermal conditions.

Digital Image Correlation (DIC) tracks changes in a surface speckle pattern to calculate displacement, then obtains strain from its spatial variation. Thermography supplies surface temperature, while the testing machine or a force transducer supplies load. Time and spatial correspondence connect these channels into a coupled thermal and mechanical record.

<a id="english-section-2"></a>

## Laboratory requirements

Conditions evolve from the hot hold to large extension. Plan coverage for both the initial specimen and its expected final state. Remote cameras and software-defined gauges support average extension and local deformation analysis, while photographs preserve shape and texture evidence.

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

For non-contact measurement in furnaces, the configuration should connect the observed object, the output and the development decision. The following table defines these relationships before equipment placement and data processing.

| Measurement element | Configuration or output | Engineering purpose |
|---|---|---|
| Surface images | Stereo cameras, optics and lighting | Preserve resolvable texture and coverage |
| Thermal adaptation | Suitable patterns and window-path checks | Cover holding and loading conditions |
| Outputs | Virtual gauges, regional strain and displacement | Support global and local analysis |

<a id="english-section-4"></a>

## System configuration and operation

A typical installation combines stereo cameras, optics, illumination, stable supports, acquisition and analysis with machine timing. An infrared channel has its own wavelength-dependent path. Calibrate visible geometry through the intended window and prepare a pattern that remains attached during heating and stretching.

<a id="english-section-5"></a>

## From images to strain results

Use room-temperature, hot-hold and loading checks to establish scale, optical stability and tracking continuity. Select correlation and strain neighbourhoods for the texture and deformation. Broad averaging smooths narrow features, while fine analysis requires sufficiently resolved images. Assess actual specimen conditions.

<a id="english-section-6"></a>

## Testing the pattern before installing a specimen

A pattern can look crisp to the eye and still be unsuitable at the actual working distance and exposure. Dense dots can merge into grey in the recorded image. Sparse dots may leave a correlation patch with too little distinctive texture. A witness piece with the same surface preparation allows a trial using the intended lens, field of view and lighting. Inspect recognisable patterns at the centre and along both curved sides.

Surviving the hold is only part of the requirement. The coating must deform with the substrate during pulling. A coating that slips as a shell can produce sharp, readily tracked images of the wrong motion. Compare coating boundaries, any recognisable exposed features and the specimen outline for compatible movement. When evaluating two treatments, compare adhesion, pattern stability and thermograms under similar thermal and imaging conditions.

<a id="english-section-7"></a>

## Checks after a window change

**Visible-light path.** Window thickness, mounting angle and camera orientation affect refraction. After replacing a window or moving a camera, check the measurement scale and reconstruction through the actual optical path. A rigid translation of a textured target offers a practical check. Compare measured and known movement and inspect the nominally zero strain field for fixed spatial patterns. This check addresses geometry. A stability check during the hot hold addresses disturbances under operating conditions.

**Infrared path.** Confirm the window material and its condition and temperature for the camera’s wavelength band. Deposits can alter transmission, and hot furnace surfaces can be reflected by the metal. Where feasible, use an independent temperature reference in a comparable thermal environment. A contact reference has its own contact, location and response-time effects. A disagreement warrants checking that both methods sampled a comparable place and thermal state.

<a id="english-section-8"></a>

## Deciding whether to repeat a test

The consequence of lost tracking depends on the question. Average extension during uniform tension may remain available if both ends of the defined gauge length are observed. Report the usable interval and excluded locations. For peak local strain at the neck, loss of its centre leaves that quantity unresolved even with good surrounding data. Identify the cause, adjust the lighting, window or pattern and repeat using a comparable specimen if that quantity matters.

An overlay of valid regions communicates more than a percentage of discarded pixels. A small loss at a remote edge and an equal loss in the middle of the neck have different implications. Report where a signal failed, when it failed and which engineering question the remaining observations can still answer.

### Choosing the next adjustment from a trial exposure

Classify a loss of image quality by its onset. Blur already visible at room temperature points first to focus, depth of field and viewing angle. Texture that fades during heating warrants separate checks on changing brightness, disturbed air and coating condition. Degradation during loading calls for inspection of motion blur, dilution of the pattern and movement out of focus. Changing one relevant setting at a time makes it possible to identify which adjustment helped.

To evaluate a different visible light source, hold specimen and camera positions fixed. Compare raw images at similar thermal states for saturated bright areas, remaining dark texture and common stereo coverage. Check the thermograms separately: improved visible contrast does not correct infrared reflections or window emission. Retain paired exposures and settings for the next run.

Tie the final choice to the required result. Optics suitable for average extension over a broad gauge may not resolve a narrow neck. A thermal view that looks clear overall still needs adequate local coverage and a characterised surface at the neck centre. Defining the target quantity helps select a wider view, finer local sampling or an independent temperature check.

<a id="english-section-9"></a>

## Applications and configuration choices

Applications include hot tensile tests, heat-treatment comparisons and localization studies. Add thermography for thermal context or change optics for finer regions. Deliver average extension, local histories, fields, images, valid areas and reference states so one run can support material comparison and model assessment.

<a id="english-section-10"></a>

## Implementation workflow

### Define the optical task

Select coverage and travel for average extension or localization.

### Prepare the pattern

Check visibility and attachment through the thermal history.

### Calibrate the actual path

Include window and installation geometry and inspect the infrared path.

### Test in stages

Retain ambient, hot baseline and loading records.

### Deliver valid responses

Provide gauge extension, regional strain and images with spatial and temporal validity.

<a id="english-section-11"></a>

## XTDIC equipment positioning and application value

XTDIC converts furnace-surface motion into displacement and strain with the head outside the loading region. Software gauges and regions support average extension and local analysis in the same images, with practical value where gripping space is limited.

A usable hot configuration combines optics, lighting, pattern and window treatment. Thermal verification on representative specimens establishes a reusable setup for comparable conditions and new analysis regions.

<a id="english-section-12"></a>

## Frequently asked questions

### What follows a window replacement?

Recheck visible geometry and infrared transmission and radiation conditions, including a hot-hold baseline.

### Can average and local extension be obtained together?

Virtual gauges and regional strain can be extracted from valid images with their own spatial definitions and references.

### Which stages belong in acceptance of a hot configuration?

Room-temperature geometry checks, the hot-hold baseline and representative loading, verifying usable images and reconstruction in the required region.

<a id="english-section-13"></a>

## Conclusion

A high-temperature DIC setup must be designed around the specimen, window and thermal history. Pattern survival, optical stability and valid coverage determine the usable result. Including these checks in the XTDIC application configuration and method handover supports a reusable laboratory capability.

<a id="english-section-14"></a>

## References

[XTDIC high-temperature application](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC and thermography application](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
