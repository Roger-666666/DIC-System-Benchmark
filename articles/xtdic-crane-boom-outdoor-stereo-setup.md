# 大视场吊臂测量如何落地？XTDIC-STROBE 户外非接触动态测试方案

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 大视场吊臂测量如何落地？XTDIC-STROBE 户外非接触动态测试方案</b></summary>

<a id="chinese-version"></a>

工程机械的动态测试正在从试验台走向实际作业场地。长臂、大幅回转、远距离观察和户外光照变化，使测量系统需要同时具备足够的运动覆盖和可用的局部识别能力。XTDIC-STROBE 结合双目三维重建、标识点跟踪与镜头畸变校正，可围绕现场允许的机位建立动态位移测量配置，为起重机与泵车臂架的多工况测试提供光学观测手段。

**目录**

- [户外测试为什么需要专门配置](#chinese-section-1)
- [从现场任务确定测量系统](#chinese-section-2)
- [大视场三维测量实施路线](#chinese-section-3)
- [标记、视场与曝光的协同配置](#chinese-section-4)
- [内外参数标定与现场尺度验证](#chinese-section-5)
- [观测稳定性与运动参考](#chinese-section-6)
- [环境变化下的配置维护](#chinese-section-7)
- [面向多机型实验室的配置价值](#chinese-section-8)
- [应用问答](#chinese-section-9)

<a id="chinese-section-1"></a>

## 户外测试为什么需要专门配置

静止时能拍全吊臂，意味着初始视野满足要求；运动中能持续识别关键位置，还取决于目标是否靠近边缘、是否改变朝向以及两机是否同时可见。户外风、车辆运动与地面支撑状态又可能改变相机稳定性，因此需要把有效运动空间作为配置对象。

实验室通常同时关心最大回摆和到位后的微小运动。这两项要求对视场与细节提出不同需求。选型时把预计最大运动范围、最小待辨位移与允许机位交给系统配置人员，有助于提前评估镜头、标记和双目几何是否适配。

<a id="chinese-section-2"></a>

## 从现场任务确定测量系统

系统可由双目测量头、适配视场的镜头、稳定支撑、编码标记和采集分析工作站构成。关键标记设置在指定构件上，外部参考用于检查观测稳定性，车体参考用于描述底座运动。数据分析中各类点的角色明确后，轨迹才能按作业目标或结构坐标解释。

相机内参描述成像与畸变，双目外部关系描述两台相机的相对位姿。分开处理内外参数有利于大型场地的部署，但仍需在最终工作体积内校核尺度与方向。XTDIC-STROBE 的大视场应用应围绕实际安装关系验收，让设备功能与现场测量量直接对应。

<a id="chinese-section-3"></a>

## 大视场三维测量实施路线

布置前绘制动作包络和遮挡关系，在机位允许范围内调整共同视野。采用代表标记检查最远、最斜和较暗的目标姿态，随后选择曝光与采样节奏。在静止阶段记录背景波动，在代表性运动中检查点号连续性，并沿最关心的位移方向安排独立校核。

正式采集后同时保留轨迹和原图。若点在遮挡后重新出现，需要核对其物理身份；若相机或镜头设置发生变化，应更新相应标定和验证。按照这一流程建立的配置，可以清楚说明哪些工况已经验证、哪些动作仍需调整视野。

<a id="chinese-section-4"></a>

## 标记、视场与曝光的协同配置

同一块传感器要同时容纳长臂的大幅运动和远端标记的小幅振动。视场扩大时，一个标记在画面上占用的像素通常减少；盲目把标记做大，又可能跨越活动接缝、覆盖不平整表面，或改变要跟踪的位置。适合的靶标应稳定地随指定构件移动，在最远、最斜和最暗的姿态下仍可辨认。可先用与正式标记相同的样片在代表位置试拍，把原始画面按实际分析尺寸查看，而非只看监视器缩小后的预览。

景深关系到靠近与远离相机的测点能否同时成像清楚。缩小光圈可能改善可用景深，却会减少进光量；延长曝光补亮时，快速扫过画面的标记又可能拖影。XTDIC-STROBE 的大景深成像与标识点跟踪配置，需要与目标运动条件相匹配。在接近最不利的动作阶段分别查看左右图像：边界能否辨认、亮区是否饱和、点号是否稳定，比静止照片看起来有多亮更能说明问题。户外日照改变后，也要复查阴影与强反射区域。

<a id="chinese-section-5"></a>

## 内外参数标定与现场尺度验证

双目标定至少涉及两组关系。相机内部参数描述成像尺度、主点和镜头畸变；两台相机之间的相对位置与朝向则决定怎样从两个观测方向恢复空间位置。采用相机内参与外参分开标定的方式，可以用较小的标定板求解内部参数，适应大型场地的部署。把内参标好以后，还需确定双目几何、物理尺度及工程坐标方向，之后导出的轨迹才有清晰的长度单位与轴向含义。

验证可以分成“已知尺寸”和“已知运动”。将尺寸已知的参考件放在有代表性的距离与视场位置，检查重建长度是否稳定；在条件允许时，让一个参考目标沿已知方向移动，检查测得的方向、符号与幅值。两项关注点不同。长度检验良好时，工程坐标仍可能左右颠倒；画面中心的平移重建良好，也不能代替视场边缘的检查。独立复核最好使用未参与标定的特征，否则容易把拟合表现误当作现场测量能力。

<a id="chinese-section-6"></a>

## 观测稳定性与运动参考

设备架在硬地面并不自动意味着镜头在整个试验中保持不动。工程车辆经过、风或支架连接松动，都可能使画面中的点产生共同运动。可在作业机构之外选择稳定参考，保留其完整时间序列。如果臂端和场外固定物在同一时刻同向跳动，先检查相机支架和三角重建关系；若固定参考保持稳定而臂上多个点按位置表现出差异，再着手解释结构响应。用装在车体上的点作外部静止基准，会把车体运动一并扣除，须与研究目的对应。

| 试拍阶段 | 要回看的画面或数据 | 它决定的配置 |
| --- | --- | --- |
| 初始静止 | 外部参考点和臂端点的表观波动 | 能否分辨预期最小位移 |
| 臂端靠近视场边界 | 两路标记是否同时完整、是否易与邻点混淆 | 镜头、机位与标记间距 |
| 最快动作附近 | 原图是否拖影，轨迹是否跳点 | 曝光、照明和采集节奏 |
| 到位后的回摆 | 目标有无出画，静止背景是否同步跳动 | 视场余量与支架稳定性 |

<a id="chinese-section-7"></a>

## 环境变化下的配置维护

同一场地早晚光照不同，不一定需要重做整套几何标定，但必须确认现有曝光下两路标记仍然可辨。若为了消除过曝而改变镜头焦距、对焦或相机位置，则应记录改变并复查相关几何关系。相反，软件中改变图像显示亮度未必改变已采集的原始像素。交接时把采集设置与屏幕显示设置分开保存，另一位操作人员才知道观察到的变化发生在哪一步。

正式试验日可先运行一个较缓的代表动作，再在获准的目标工况下检验最不利阶段。前者有助于发现遮挡和点号问题，后者用于判断曝光、采样与储存过程能否跟上。低速试拍完整，并不保证快速阶段也完整；快速动作没有丢帧，也不意味停后的微动高于静止噪声。可把两段试验与静止基线放在同一份现场核查记录中，各自回答一个问题。

若环境限制只允许相机从几乎相同的方向看臂端，双目深度对像点定位误差会更敏感。此时扩大两机间距可能改善几何条件，也可能缩小共同视野、加剧一侧遮挡。选择机位要回到用户最关心的方向：只关心侧向分量和必须追踪深度位移，对几何条件的要求不同。拿一个已知方向的位移做现场验证，比凭两台相机之间看起来相隔很远就判断“深度一定够准”更可靠。

<a id="chinese-section-8"></a>

## 面向多机型实验室的配置价值

同一套测量系统可以服务不同臂长与试验动作，但每次复用应有清楚的配置记录。保存机位示意、镜头设置、点号与参考系，实验室可以将首次部署形成的经验转化为后续试验的准备依据，减少每次重新摸索的工作。

对于需要持续开展产品开发的单位，设备交付可以包含一套代表性动作的数据样件和独立复算方法。使用者能从坐标文件恢复约定方向的位移，并找到对应原始画面，就具有将设备输出纳入日常报告的基础。最终评价应落在目标动作的有效覆盖、可辨位移和数据可追溯性上。

<a id="chinese-section-9"></a>

## 应用问答

**远距离测量先验证哪一个方向？**

优先验证工程上最关心且预计变化最小的方向。几何条件对各方向的影响不同，应在实际机位检查。

**户外阴影变化怎样处理？**

在代表性光照下确认标记对比度与曝光，保存原始图像。若几何或镜头设置变化，复核对应标定。

**技术资料**

[设备与应用资料](https://www.xtop3d.com/products/xtdic-strobe.html) · [应用素材](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>

<details>
<summary><b>English · Implementing Large-Field Outdoor Boom Measurement with XTDIC-STROBE</b></summary>

<a id="english-version"></a>

# Implementing Large-Field Outdoor Boom Measurement with XTDIC-STROBE

Outdoor machinery tests combine long structures, large motion, remote observation and changing illumination. XTDIC-STROBE combines stereo reconstruction, target tracking and distortion correction to establish motion measurements from available site stations for crane and concrete pump booms.

**Contents**

- [Why outdoor testing needs a planned configuration](#english-section-1)
- [Defining the measurement system](#english-section-2)
- [Implementing large-field stereo measurements](#english-section-3)
- [Choose markers, field of view and exposure together](#english-section-4)
- [What a small calibration board establishes](#english-section-5)
- [Distinguish support movement from boom motion](#english-section-6)
- [What changes when the site changes?](#english-section-7)
- [Value across machine types](#english-section-8)
- [Application questions](#english-section-9)

<a id="english-section-1"></a>

## Why outdoor testing needs a planned configuration

Initial coverage does not establish visibility during motion. Attitude, image edges and shared views matter, as do supports and environmental disturbance. Specify the largest envelope and smallest relevant movement together.

<a id="english-section-2"></a>

## Defining the measurement system

A configuration includes cameras, lenses, supports, targets and acquisition software. External and chassis references have different roles. Separate intrinsic and relative-pose calibration still requires independent scale and direction checks in the working volume.

<a id="english-section-3"></a>

## Implementing large-field stereo measurements

Map motion and occlusion, trial representative targets in difficult poses and choose exposure and cadence. Establish stationary variability, verify identity through motion and check a known movement in the important direction. Retain images and revalidate after optical or geometric changes.

<a id="english-section-4"></a>

## Choose markers, field of view and exposure together

The sensor must cover large excursions while resolving small residual motion. Widening the view typically allocates fewer pixels to a target. Enlarging a marker indiscriminately can make it span a moving joint or an uneven surface. Test representative markers at the farthest, most oblique and darkest positions. Inspect raw images at analysis size, including the second camera.

Depth of field determines whether near and far markers stay recognisable. Stopping down can increase useful depth but reduces light. A longer exposure can then blur a fast marker. Configure depth of field and target tracking for the motion envelope. Examine both under near-worst motion for distinct outlines, saturation and stable identifiers. Outdoor shadows and reflections warrant a repeat check when lighting changes.

<a id="english-section-5"></a>

## What a small calibration board establishes

Camera intrinsics describe image scale, principal point and lens distortion. Relative camera pose determines how two sight lines reconstruct a spatial point. Separate intrinsic and extrinsic calibration allows a small board to establish internal camera parameters for a large installation. Stereo geometry, physical scale and engineering-axis orientation still need to be established for the measurement volume.

Use independent known lengths at representative depths and image positions. Where feasible, also move a reference target in a known direction and check sign, direction and magnitude. Lengths can be correct with an inverted engineering axis. Successful reconstruction near the centre does not establish performance near the edge. Features withheld from calibration provide the more informative check.

<a id="english-section-6"></a>

## Distinguish support movement from boom motion

Wind, nearby vehicles and support movement can produce a common apparent motion. Retain histories for stable references outside the operating mechanism. A simultaneous jump of the boom and a fixed object calls for checking supports and stereo geometry. Stable external references alongside different motions at boom stations give a basis for structural interpretation. A chassis marker instead removes chassis motion and answers a different question.

| Trial stage | Evidence to inspect | Decision it supports |
| --- | --- | --- |
| Initially stationary | Apparent movement of fixed and boom targets | Smallest useful displacement |
| Near image boundaries | Simultaneous visibility and identity | Lens, stations and spacing |
| Fastest movement | Blur and jumps in raw images | Exposure, lighting and cadence |
| Post-stop swing | Loss of view or common background jumps | Coverage margin and support stability |

<a id="english-section-7"></a>

## What changes when the site changes?

Different sunlight may require new exposure checks without changing geometric calibration. Moving cameras or changing focal length or focus to address image problems warrants checking the affected geometry. Adjusting display brightness alone need not alter original pixels. Record acquisition settings separately from viewing settings.

Begin with a slow representative movement for visibility and target identity, then check the authorised intended motion for exposure, cadence and recording continuity. A complete slow run does not establish performance at higher speed. A complete fast run does not establish that residual motion exceeds stationary noise. Keep these trials alongside the stationary baseline.

Two nearly parallel views can leave depth particularly sensitive to image-location error. More camera separation can improve geometry while reducing overlap or worsening occlusion. Select stations for the direction the user actually needs. A known movement along that direction provides firmer evidence than the apparent separation between the cameras.

<a id="english-section-8"></a>

## Value across machine types

Document stations, optics, identifiers and frames for reuse across machines. Include a representative dataset and independent recomputation in handover. Acceptance should establish valid coverage, useful resolution and traceability for the intended event.

<a id="english-section-9"></a>

## Application questions

**Which direction deserves an early site check?**

The important direction with the smallest required change, using the intended camera stations.

**How should changing shadows be handled?**

Check contrast and exposure under representative lighting and retain images. Recheck calibration after optical or geometric changes.

**Technical resources**

[Equipment and application information](https://www.xtop3d.com/products/xtdic-strobe.html) · [Application material in Chinese](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>
