# 大型吊臂在室外怎样布置三维 DIC？XTDIC-STROBE 大视场测试方案

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 大型吊臂在室外怎样布置三维 DIC？XTDIC-STROBE 大视场测试方案</b></summary>

<a id="chinese-version"></a>

大型吊臂在相机前运动时，最难拍的地方常常不是离得最远的端头，而是回转到边缘、即将被其他臂节挡住的那个位置。外场选用 XTDIC-STROBE，首先要确认同一标记在整个目标动作里都能被两台相机识别，其次才有条件讨论三维坐标和可分辨位移。本文从场地踏勘、光学配置、标定和验证四个环节，说明怎样把产品资料中的“大视场动态跟踪”落实到一项具体的吊臂试验。 [参考试验](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**本文目录**

- [从运动范围反推机位](#chinese-section-1)
- [标记大小、视场与曝光要一起试](#chinese-section-2)
- [小标定板能解决哪一部分问题](#chinese-section-3)
- [把支架运动和吊臂运动分开](#chinese-section-4)
- [缺点、错点与真实突变怎样区分](#chinese-section-5)
- [现场条件变化，哪些设置可以沿用](#chinese-section-6)
- [让外场配置可以重复使用](#chinese-section-7)

<a id="chinese-section-1"></a>

## 从运动范围反推机位

场地勘察图上需要画出吊臂起始姿态、到位姿态和中间可能经过的区域，还应标出预计回摆的方向。只按静止时的一张全景照片选镜头，常会漏掉制动后越过目标的那段运动。若试验任务是测末端精准到位，优先考虑端头在越位和回摆时的共同视野；若要比较多节臂的运动，则要把近端基准和中间臂节也纳入两路画面。这样才能确定需要覆盖整机，还是只需要观察端部的一段空间。

在图上分别画出两台相机的视线。某个测点在左相机一直清楚，右相机却可能在姿态变化时被油缸、软管或相邻结构遮住。此时加长焦距不会恢复缺失的第二个视角。可在试验场允许的区域内调整观察方向，或选择对研究问题等效而更容易保持可见的位置。机位、供电和走线均应遵守现场隔离要求，靶标布置在设备已按现场程序停稳时完成。方案的可行性取决于这些实际位置能否使用。

<a id="chinese-section-2"></a>

## 标记大小、视场与曝光要一起试

同一块传感器要同时容纳长臂的大幅运动和远端标记的小幅振动。视场扩大时，一个标记在画面上占用的像素通常减少；盲目把标记做大，又可能跨越活动接缝、覆盖不平整表面，或改变要跟踪的位置。适合的靶标应稳定地随指定构件移动，在最远、最斜和最暗的姿态下仍可辨认。可先用与正式标记相同的样片在代表位置试拍，把原始画面按实际分析尺寸查看，而非只看监视器缩小后的预览。

景深关系到靠近与远离相机的测点能否同时成像清楚。缩小光圈可能改善可用景深，却会减少进光量；延长曝光补亮时，快速扫过画面的标记又可能拖影。原文介绍了大景深成像与标识点跟踪，可把这两项作为试拍对象。在接近最不利的动作阶段分别查看左右图像：边界能否辨认、亮区是否饱和、点号是否稳定，比静止照片看起来有多亮更能说明问题。户外日照改变后，也要复查阴影与强反射区域。

<a id="chinese-section-3"></a>

## 小标定板能解决哪一部分问题

双目标定至少涉及两组关系。相机内部参数描述成像尺度、主点和镜头畸变；两台相机之间的相对位置与朝向则决定怎样从两个观测方向恢复空间位置。参考方案将相机内参与外参分开处理，使用较小的标定板求解内部参数，这对大型场地很实际。把内参标好以后，还需确定双目几何、物理尺度及工程坐标方向，之后导出的轨迹才有清晰的长度单位与轴向含义。

验证可以分成“已知尺寸”和“已知运动”。将尺寸已知的参考件放在有代表性的距离与视场位置，检查重建长度是否稳定；在条件允许时，让一个参考目标沿已知方向移动，检查测得的方向、符号与幅值。两项关注点不同。长度检验良好时，工程坐标仍可能左右颠倒；画面中心的平移重建良好，也不能代替视场边缘的检查。独立复核最好使用未参与标定的特征，否则容易把拟合表现误当作现场测量能力。

<a id="chinese-section-4"></a>

## 把支架运动和吊臂运动分开

设备架在硬地面并不自动意味着镜头在整个试验中保持不动。工程车辆经过、风或支架连接松动，都可能使画面中的点产生共同运动。可在作业机构之外选择稳定参考，保留其完整时间序列。如果臂端和场外固定物在同一时刻同向跳动，先检查相机支架和三角重建关系；若固定参考保持稳定而臂上多个点按位置表现出差异，再着手解释结构响应。用装在车体上的点作外部静止基准，会把车体运动一并扣除，须与研究目的对应。

| 试拍阶段 | 要回看的画面或数据 | 它决定的配置 |
| --- | --- | --- |
| 初始静止 | 外部参考点和臂端点的表观波动 | 能否分辨预期最小位移 |
| 臂端靠近视场边界 | 两路标记是否同时完整、是否易与邻点混淆 | 镜头、机位与标记间距 |
| 最快动作附近 | 原图是否拖影，轨迹是否跳点 | 曝光、照明和采集节奏 |
| 到位后的回摆 | 目标有无出画，静止背景是否同步跳动 | 视场余量与支架稳定性 |

<a id="chinese-section-5"></a>

## 缺点、错点与真实突变怎样区分

跟踪丢失通常表现为某一段没有结果；点号对错则可能给出一条看似连续、实际上从一处材料跳到另一处的曲线。后者更容易误导。布点时应留一份点位照片并记录所属臂节。出现尖峰时，用时间戳回查前后双目照片，分别核对点号、局部形状和附近标记的相对位置。若标记跨过遮挡后重现，应确认恢复了同一物理点，再决定能否接续两段记录。跨越制动极值的缺口尤其应保留，自动插值不能证明漏拍期间的最大位移。

有些任务不适合只靠预设的一对机位完成。例如测点从正面转到背面，在某个阶段完全不可见，这属于几何遮挡。若该段运动决定测试结论，可分开设计观察区域，评估新增视角的共同标定与时间对应，或者调整测点任务。若该阶段本来不在研究范围内，则事先规定有效分析区间即可。把这项决定放在方案阶段，比试验结束后才发现关键帧无法重建更经济。


<a id="chinese-section-6"></a>

## 现场条件变化，哪些设置可以沿用

同一场地早晚光照不同，不一定需要重做整套几何标定，但必须确认现有曝光下两路标记仍然可辨。若为了消除过曝而改变镜头焦距、对焦或相机位置，则应记录改变并复查相关几何关系。相反，软件中改变图像显示亮度未必改变已采集的原始像素。交接时把采集设置与屏幕显示设置分开保存，另一位操作人员才知道观察到的变化发生在哪一步。

正式试验日可先运行一个较缓的代表动作，再在获准的目标工况下检验最不利阶段。前者有助于发现遮挡和点号问题，后者用于判断曝光、采样与储存过程能否跟上。低速试拍完整，并不保证快速阶段也完整；快速动作没有丢帧，也不意味停后的微动高于静止噪声。可把两段试验与静止基线放在同一份现场核查记录中，各自回答一个问题。

若环境限制只允许相机从几乎相同的方向看臂端，双目深度对像点定位误差会更敏感。此时扩大两机间距可能改善几何条件，也可能缩小共同视野、加剧一侧遮挡。选择机位要回到用户最关心的方向：只关心侧向分量和必须追踪深度位移，对几何条件的要求不同。拿一个已知方向的位移做现场验证，比凭两台相机之间看起来相隔很远就判断“深度一定够准”更可靠。

<a id="chinese-section-7"></a>

## 让外场配置可以重复使用

交接时保存机位示意、镜头与曝光设置、目标编号、工程坐标方向和校核结果，并留下一段最不利姿态的原始图像。下次移机或改变焦距时，就能确定需要重新验证的环节。若视场相同而支架位置变化，要重新检查双目相对几何与坐标方向；若镜头焦距或对焦设置发生改变，则连内部成像关系也应复核。

采购前最有判断力的演示，是让设备在预定机位上完成一次真实工作范围内的轨迹交付，并把有效与缺失的区间都标在结果里。XTDIC-STROBE 的远距离双目采集、畸变校正和多点跟踪在这样的工况下各自承担明确任务。一套被验证过的现场布置，还能让不同试验班组在同一条件下复测，避免把机位改变带来的差别误判为吊臂结构变化。

**设备与案例资料**

- [XTDIC-STROBE 动态测量系统与应用范围](https://www.xtop3d.com/products/xtdic-strobe.html)
- [起重机吊臂偏摆实测图与曲线（英文）](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**延伸阅读**

- [230 · 吊臂动态位移测量设备怎么选？XTDIC-STROBE 与位移计、加速度计及视频的任务对比](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-displacement-equipment-selection.md#chinese-version)
- [228 · 起重机回转停止后，吊臂还会摆多久？XTDIC 三维动态位移测量案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-slew-sway-case.md#chinese-version)

</details>

<details>
<summary><b>English · Planning an Outdoor Large-Field Stereo DIC Test for a Crane Boom with XTDIC-STROBE</b></summary>

<a id="english-version"></a>

# Planning an Outdoor Large-Field Stereo DIC Test for a Crane Boom with XTDIC-STROBE

The hardest location to measure outdoors may be the point where a boom passes behind another section at the edge of the image. For an XTDIC-STROBE installation, first establish whether both cameras can identify each required marker throughout the event. The practical design then follows from motion envelope, optical configuration, calibration and independent checks on reconstructed motion. [Reference tests, in Chinese](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**Contents**

- [Work backwards from the motion envelope](#english-section-1)
- [Choose markers, field of view and exposure together](#english-section-2)
- [What a small calibration board establishes](#english-section-3)
- [Distinguish support movement from boom motion](#english-section-4)
- [Missing targets, wrong identities and real jumps](#english-section-5)
- [What changes when the site changes?](#english-section-6)
- [Deliver a repeatable installation](#english-section-7)

<a id="english-section-1"></a>

## Work backwards from the motion envelope

Draw the initial and final poses, the region swept between them and the expected return swing. A lens selected from a stationary panoramic photograph can miss overshoot after braking. For positioning, prioritise shared coverage of the tip during crossing and return. For comparisons along the structure, include base references and intermediate sections in both views. This determines whether the whole machine or just an end volume needs coverage.

Draw the sight line from each camera. A marker clear in the left image may pass behind a cylinder, hose or another section in the right image. More magnification cannot restore a missing view. Consider another permitted observation direction or an equivalent location on the part. Camera stations, power and cables must fit site segregation arrangements. Targets are installed during the site's stationary setup procedure.

<a id="english-section-2"></a>

## Choose markers, field of view and exposure together

The sensor must cover large excursions while resolving small residual motion. Widening the view typically allocates fewer pixels to a target. Enlarging a marker indiscriminately can make it span a moving joint or an uneven surface. Test representative markers at the farthest, most oblique and darkest positions. Inspect raw images at analysis size, including the second camera.

Depth of field determines whether near and far markers stay recognisable. Stopping down can increase useful depth but reduces light. A longer exposure can then blur a fast marker. The reference describes large-depth imaging and target tracking. Examine both under near-worst motion for distinct outlines, saturation and stable identifiers. Outdoor shadows and reflections warrant a repeat check when lighting changes.

<a id="english-section-3"></a>

## What a small calibration board establishes

Camera intrinsics describe image scale, principal point and lens distortion. Relative camera pose determines how two sight lines reconstruct a spatial point. The reference separates intrinsic from extrinsic calibration so that a small board can be used for intrinsics in a large installation. Stereo geometry, physical scale and engineering-axis orientation still need to be established for the measurement volume.

Use independent known lengths at representative depths and image positions. Where feasible, also move a reference target in a known direction and check sign, direction and magnitude. Lengths can be correct with an inverted engineering axis. Successful reconstruction near the centre does not establish performance near the edge. Features withheld from calibration provide the more informative check.

<a id="english-section-4"></a>

## Distinguish support movement from boom motion

Wind, nearby vehicles and support movement can produce a common apparent motion. Retain histories for stable references outside the operating mechanism. A simultaneous jump of the boom and a fixed object calls for checking supports and stereo geometry. Stable external references alongside different motions at boom stations give a basis for structural interpretation. A chassis marker instead removes chassis motion and answers a different question.

| Trial stage | Evidence to inspect | Decision it supports |
| --- | --- | --- |
| Initially stationary | Apparent movement of fixed and boom targets | Smallest useful displacement |
| Near image boundaries | Simultaneous visibility and identity | Lens, stations and spacing |
| Fastest movement | Blur and jumps in raw images | Exposure, lighting and cadence |
| Post-stop swing | Loss of view or common background jumps | Coverage margin and support stability |

<a id="english-section-5"></a>

## Missing targets, wrong identities and real jumps

A lost target produces a gap. A swapped identity can produce an apparently complete curve from two different pieces of metal. Retain a numbered layout and section identity. At a spike, inspect consecutive stereo frames for identifier, local outline and neighbouring markers. After occlusion, establish that the same physical point returned. Interpolating across braking cannot establish an unobserved extreme.

A section turning completely away presents a visibility problem. If the hidden interval is essential, evaluate additional observation volumes with common calibration and timing, or revise the target arrangement. If it lies outside the question, define the valid interval in advance. Solving this at setup is more effective than discovering missing peak frames after the run.


<a id="english-section-6"></a>

## What changes when the site changes?

Different sunlight may require new exposure checks without changing geometric calibration. Moving cameras or changing focal length or focus to address image problems warrants checking the affected geometry. Adjusting display brightness alone need not alter original pixels. Record acquisition settings separately from viewing settings.

Begin with a slow representative movement for visibility and target identity, then check the authorised intended motion for exposure, cadence and recording continuity. A complete slow run does not establish performance at higher speed. A complete fast run does not establish that residual motion exceeds stationary noise. Keep these trials alongside the stationary baseline.

Two nearly parallel views can leave depth particularly sensitive to image-location error. More camera separation can improve geometry while reducing overlap or worsening occlusion. Select stations for the direction the user actually needs. A known movement along that direction provides firmer evidence than the apparent separation between the cameras.

<a id="english-section-7"></a>

## Deliver a repeatable installation

Preserve the station diagram, optical settings, marker IDs, axes, checks and original frames from the least favourable pose. Moving supports requires checking stereo pose and axes. Changing focus or focal length also warrants verification of internal geometry.

A strong pre-purchase demonstration delivers trajectories over the intended envelope from actual permitted stations, with valid and missing intervals marked. Long-range stereo acquisition, distortion correction and multipoint tracking can then be evaluated for their separate contributions. A documented configuration also allows another shift to repeat the test without confusing a camera change with a structural difference.

**Equipment and case documentation**

- [XTDIC-STROBE dynamic measurement system and applications](https://www.xtop3d.com/products/xtdic-strobe.html)
- [Crane boom test images and displacement curves](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**Related articles**

- [230 · Choosing Equipment for Crane Boom Motion: XTDIC-STROBE, Displacement Sensors, Accelerometers and Video](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-displacement-equipment-selection.md#english-version)
- [228 · Measuring Crane Boom Sway After Slew Stops with XTDIC Stereo Tracking](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-slew-sway-case.md#english-version)

</details>
