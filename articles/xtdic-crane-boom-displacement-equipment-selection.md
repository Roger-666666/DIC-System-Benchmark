# 工程机械动态位移测量设备选型：XTDIC-STROBE 多点三维测试的适用价值

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [先确定设备要支持的工程决策](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [XTDIC-STROBE 的系统能力](#chinese-section-4)
- [按测量原理比较配置](#chinese-section-5)
- [位移、加速度与图像测量方法比较](#chinese-section-6)
- [平面运动与空间运动的成像选择](#chinese-section-7)
- [现有台位改造与生产检测配置](#chinese-section-8)
- [采购验收与长期复用](#chinese-section-9)
- [试验实施流程](#chinese-section-10)
- [XTDIC 设备定位与应用价值](#chinese-section-11)
- [常见问答](#chinese-section-12)
- [结语](#chinese-section-13)
- [参考资料](#chinese-section-14)

<a id="chinese-section-1"></a>

## 核心结论

工程机械实验室配置动态测量设备时，需要兼顾单向行程、局部振动与端头空间运动等不同任务。XTDIC-STROBE 适合需要同时获取多个可见位置三维坐标的试验，能够为偏摆、回摆与定位性能评价提供带方向的位移历程。将测量任务、安装条件和最终交付量对应起来，可以更清楚地判断何时需要三维光学系统，以及它怎样与已有传感器形成互补。

三维动态位移测量通过同步双目图像重建目标点的空间坐标，再计算其随时间的变化。吊臂上的离散特征点主要用于运动与位移分析；需要连续表面应变时，应另行设计数字图像相关（Digital Image Correlation，DIC）的散斑观察区域和计算尺度。

<a id="chinese-section-2"></a>

## 先确定设备要支持的工程决策

机构行程检查关注固定方向的长度变化，控制开发关注端头是否越过目标以及多久进入允许范围，结构研究则可能需要多节臂之间的相对运动。不同任务即使都被称为测振动，所需信息也并不相同。

可以将需求落实为可交付结果，例如某次制动过程中的臂端三维坐标、中段同时刻位移和峰值对应画面。这样的描述自然带出同步、多点、可见性与数据导出的要求，也方便把现有传感器能够覆盖的量与新增设备应补充的量列清楚。

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

工程机械动态测量设备选型的配置，应从测量对象、输出指标和研发用途之间的关系展开。下面的对应表可用于确定观察范围、数据通道与后续分析任务。

| 测量要素 | 配置或输出 | 工程用途 |
|---|---|---|
| 固定方向行程 | 位移计与稳定安装基准 | 适合定义清楚的长度变化 |
| 局部快速响应 | 加速度通道与合适带宽 | 适合振动和频率相关研究 |
| 多点空间运动 | XTDIC-STROBE 双目跟踪 | 同时得到方向位移、相对运动与轨迹 |

<a id="chinese-section-4"></a>

## XTDIC-STROBE 的系统能力

双目系统通过共同观察同一特征建立深度，结合标定输出有物理尺度的空间坐标。XTDIC-STROBE 可持续跟踪目标，并从坐标记录计算分向运动、相对距离与轨迹。多位置共享成像时序，为分析同一动作中的差异提供基础。

测量头可布置在作业区外，目标准备以符合试验任务的稳定特征或标记为基础。对大行程研究，这种非接触方式减少了随动机械连接的需求；对产品迭代，保留原始坐标允许使用者按新目标重算指标。实际可用的运动范围和最小变化仍应在拟用距离与光路上验证。

<a id="chinese-section-5"></a>

## 按测量原理比较配置

位移计适合具有明确安装基准和测量方向的长度变化。加速度计适合局部动态响应与频率分析，单目视频适合平面运动及工况回看。三维光学系统则为多方向、多位置的空间观测提供直接几何依据。选型中可按任务分别保留这些通道，各自发挥优势。

设备比较宜采用相同的代表动作，约定方向、目标和时间区间，再查看每种方法能直接交付哪些量。需要由积分、投影或其他计算获得的结果，应说明初始条件和几何假设。对于频率较高的动态任务，还要核对有效带宽和同步能力，确保比较的是同一事件。

<a id="chinese-section-6"></a>

## 位移、加速度与图像测量方法比较

| 方法 | 直接获得的证据 | 适合的问题 | 实施前要核实 |
| --- | --- | --- | --- |
| 拉线或直线位移计 | 传感器测量方向上的长度变化 | 固定基准到目标的单向行程 | 安装点、行程、运动中方向变化和布线 |
| 加速度计 | 安装点沿敏感方向的加速度信号 | 局部振动、瞬态冲击、频率成分 | 方向、固定方式、重力影响与同步 |
| 单目视频 | 图像平面中的位置、轮廓与事件顺序 | 平面内运动、工况回放 | 标尺所在平面及出平面运动 |
| XTDIC-STROBE 双目跟踪 | 共同可见特征点的空间坐标与时序 | 多点三维轨迹、带方向的偏摆、相对运动 | 双目几何、标记可见性和现场实际分辨能力 |

### 有可用的固定基准时，单向测量很直接

测绳两端的距离变化具有明确的几何含义。若目标沿同一直线运动且锚点稳定，利用这种变化描述行程十分直观。若端头绕锚点画弧，测绳长度可能变化很小，即使端头已经横向移动较远。还有一种情形是绳长在变，但变化同时包含水平与竖向运动。这些都不是传感器读错了，而是测得的距离与需要的坐标分量不同。采购时最好先在布置图上画出测量方向，再判断该通道能否代表目标量。

### 有清晰振动信号时，为什么还要看位移

加速度计适合观察某个位置的快速响应。要由加速度推回位移，需要处理初始速度、基线和积分漂移；端臂架姿态态改变时，敏感轴和重力的相对方向也会变化。对停稳后的高频局部响应，加速度记录可能更有辨识力；对端头从何处经过、最终停在哪里，光学坐标的物理含义更直接。若两类问题都重要，可在同一位置附近布点，统一方向与时间，保留各自原始通道。再比较由光学位移导出的加速度时，须注意求导会放大图像噪声，两种信号的有效带宽也可能不同。

<a id="chinese-section-7"></a>

## 平面运动与空间运动的成像选择

若目标始终在已知平面内移动，镜头固定、成像几何经过核查，单目视频可以给出有尺度的平面轨迹。对泵车这种端头会朝镜头接近或远离的工况，同样一段真实移动投影到图像中的长度会随深度改变。此时即使画面很清晰，人眼能看出“在晃”，一张照片里的标尺也难把整个动作换算成可靠的空间轨迹。双目系统增加一个观察方向，可以用匹配的视线重建深度，并将已记录的轨迹转换到作业坐标系中。

三维重建仍受视角、距离与特征质量约束。如果采购任务是辨认很小的面外位移，应在计划的远距离机位上沿该方向做独立检验。如果只展示横向大位移的流畅轨迹，无法证明同一系统也能分辨较小的深度变化。XTDIC-STROBE 的配置验收应覆盖用户实际要求的运动方向与工作范围。不同机位、不同臂长、不同速度下的能力则应通过用户现场试拍确定。

<a id="chinese-section-8"></a>

## 现有台位改造与生产检测配置

一种任务是现有试验台已经有加速度与控制日志，缺的是端头最终停在哪里。若再增加一个同类加速度通道，可能更清楚地看到局部振动，但对最终位置仍需积分与初始条件。此时用光学系统补充绝对或相对坐标，并以已有日志标记动作阶段，可以让各仪器覆盖彼此薄弱的部分。是否值得增加该配置，取决于独立位置观测能否改变设计判断，例如能否发现程序显示到位而实体端头仍处于目标外侧。

另一种任务是每台成品只检查同一方向上的一个行程，并且机器已有稳定、易于校核的测量基准。如果结果只用于判断是否达到既定位置，研发阶段使用的多点三维方案未必需要复制到每个工位。可以在样机试验时用 XTDIC-STROBE 核对这个简化指标是否对不同姿态都有效，再决定日常检查保留哪些通道。这样评价仪器时，讨论的是它能支持哪一次决策，以及这项决策多久需要重复。

两类用户在验收时还可以提出同一个问题：更换镜头或调整安装位置后，怎样知道新旧结果仍能比较？直线位移计要检查锚点与测量方向，加速度计要检查安装朝向，单目要核对标尺和平面，双目则要验证尺度、相对几何与任务坐标。让仪器交付方演示一次独立校核，并把可复算的数据和方法交给使用团队，比仅接受一张测试结束时的漂亮曲线更能降低后续使用的不确定性。

<a id="chinese-section-9"></a>

## 采购验收与长期复用

采购方可指定一组真实动作，让设备方按允许的机位交付坐标、点号、时间与原始图像。实验室独立重算一项偏摆量，并核对该时刻的真实标记，有助于检验数据能否纳入自身工作流程。验收也应覆盖最不利姿态与停后最小待辨运动。

后续复用成本包括安装、标定、目标准备和数据处理。保存典型配置与校核方法，可以让设备在不同机型间迁移时有明确依据。对于长期需要三维轨迹、控制评价与模型验证的实验室，XTDIC-STROBE 的价值在于一份可复用观测能够支持多个研发岗位。

<a id="chinese-section-10"></a>

## 试验实施流程

### 列出实际交付量

把行程、局部振动和空间轨迹分别对应到工程决策。

### 核对已有通道

记录各传感器的方向、安装、有效带宽和能够提供的量。

### 实施同任务演示

要求候选配置面对相同动作和允许机位，输出约定数据。

### 独立重算一个指标

利用坐标、时间与点号恢复方向位移，并核对原始画面。

### 确定长期使用方案

评估换机型时的安装、标定和处理工作，保存可复用配置。

<a id="chinese-section-11"></a>

## XTDIC 设备定位与应用价值

XTDIC-STROBE 的选型定位是多点、三维、非接触的动态位置观测。研发任务需要知道多个位置在同一动作中怎样移动时，双目坐标提供了能够重新分解方向和计算相对量的基础。数据导出后，测试人员可以按定位、控制或模型任务选择不同指标。

它与现有位移或加速度通道可以共同工作。实验室可保留对单向行程和快速局部响应有优势的测量，再用三维光学补充空间运动与不同部位的联系。设备选择由实际任务决定，代表动作中的完整数据交付则为采购提供可核验依据。

<a id="chinese-section-12"></a>

## 常见问答

### 怎样判断已有传感器是否需要保留？

从最终任务出发，保留能可靠覆盖单向行程或局部高频响应的通道，再用三维光学坐标补充空间路径与多点关系。

### 验收时应要求哪类数据？

除结果图外，应包含坐标、时间、点号、参考系、有效区间和极值对应图像，让使用方独立重算约定指标。

### 哪类实验室更适合配置 XTDIC-STROBE？

经常比较多机型、多姿态或多控制策略，并需要把空间轨迹交给结构与仿真团队的实验室，更能使用到多点坐标与原始图像的复用价值。

<a id="chinese-section-13"></a>

## 结语

工程机械动态测量选型，应从需要作出的研发决策回到待测物理量。需要多位置三维位移和轨迹时，XTDIC-STROBE 提供了可围绕现场任务配置的非接触方案。把典型动作演示、数据输出和重复分析纳入验收，可以使设备采购直接对应后续的试验能力建设。

<a id="chinese-section-14"></a>

## 参考资料

[XTDIC-STROBE 设备资料](https://www.xtop3d.com/products/xtdic-strobe.html) · [三维吊臂动态位移应用资料](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Selecting Dynamic Displacement Equipment for Machinery: The Role of XTDIC-STROBE

## Contents

- [Executive answer](#english-section-1)
- [Start from the engineering decision](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [XTDIC-STROBE system capabilities](#english-section-4)
- [Comparing measurement configurations](#english-section-5)
- [What each method observes](#english-section-6)
- [When a second camera earns its place](#english-section-7)
- [Two common procurement decisions](#english-section-8)
- [Acceptance and long-term reuse](#english-section-9)
- [Implementation workflow](#english-section-10)
- [XTDIC equipment positioning and application value](#english-section-11)
- [Frequently asked questions](#english-section-12)
- [Conclusion](#english-section-13)
- [References](#english-section-14)

<a id="english-section-1"></a>

## Executive answer

Machinery laboratories measure strokes, local vibration and spatial tip motion. XTDIC-STROBE addresses tasks requiring simultaneous spatial coordinates at multiple visible positions. Relating installation and outputs to the decision clarifies where stereo measurement adds value alongside existing sensors.

Three-dimensional dynamic displacement measurement reconstructs target coordinates from synchronized stereo images and follows their change over time. Discrete boom targets principally describe motion and displacement. Continuous surface strain requires a separately designed speckle region and processing scale for Digital Image Correlation (DIC).

<a id="english-section-2"></a>

## Start from the engineering decision

Stroke checks, controls development and structural analysis require different observables. Specify a deliverable such as tip coordinates, simultaneous intermediate movement and images at an extreme. This identifies timing, visibility and export requirements.

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

For selecting machinery motion instrumentation, the configuration should connect the observed object, the output and the development decision. The following table defines these relationships before equipment placement and data processing.

| Measurement element | Configuration or output | Engineering purpose |
|---|---|---|
| Fixed-axis stroke | Displacement sensor and stable mounting | Directly measure defined length changes |
| Rapid local response | Acceleration channel and suitable bandwidth | Study vibration and frequency content |
| Multipoint spatial motion | XTDIC-STROBE stereo tracking | Acquire components, relative motion and paths |

<a id="english-section-4"></a>

## XTDIC-STROBE system capabilities

Stereo geometry gives scaled spatial coordinates. Shared acquisitions support component histories, relative distances and paths. Remote heads reduce the need for moving mechanical connections, and coordinate archives allow new metrics later. Verify envelope and resolution at the actual distance.

<a id="english-section-5"></a>

## Comparing measurement configurations

Linear sensors, accelerometers, planar video and stereo tracking answer complementary questions. Compare them on the same event and state any integration or projection assumptions. Check bandwidth and timing for rapid motion.

<a id="english-section-6"></a>

## What each method observes

| Method | Direct evidence | Good application | Installation question |
| --- | --- | --- | --- |
| Draw-wire or linear sensor | Length change along its measurement geometry | Travel between a stable reference and a point | Anchoring, range, cable route and changing angle |
| Accelerometer | Acceleration at its mounting point along sensitive axes | Local vibration, impacts and frequency content | Mounting, gravity, orientation and timing |
| Single-camera video | Image-plane position, outline and event order | Planar movement and visual review | Calibration plane and out-of-plane motion |
| XTDIC-STROBE stereo tracking | Spatial coordinates of jointly visible features over time | Multipoint trajectories, signed sway and relative motion | Stereo geometry, visibility and site resolution |

A cable measures end-to-end distance. It works naturally for straight motion from a stable anchor. A target moving around an arc centred on that anchor can travel laterally with almost no change in cable length. Other paths mix vertical and horizontal movements into one length. Draw the measurement geometry before treating length change as a displacement component.

An accelerometer can resolve fast local responses. Recovering displacement by integration requires initial conditions and control of drift. Changes in boom orientation also change gravity projection. For local high-frequency vibration an accelerometer may be the better channel. For the route of a tip and its final position, optical coordinates have a direct interpretation. When both matter, measure near a common location with matched axes and timing. Differentiating optical displacement amplifies noise, and any comparison with acceleration needs a common effective bandwidth.

<a id="english-section-7"></a>

## When a second camera earns its place

With a fixed camera, verified scale and a target confined to a known plane, monocular video can deliver a scaled planar path. When a pump outlet moves toward or away from the camera, projection scale changes. Even excellent footage and a ruler in one plane may leave the spatial route ambiguous. Stereo observations provide depth from corresponding sight lines and allow the recorded path to be expressed in task coordinates.

Depth resolution depends on geometry, distance and feature quality. If a small depth displacement matters, test a known movement in that direction from the intended stations. A smooth demonstration of large transverse travel cannot establish sensitivity to a much smaller depth change. Published boom and pump cases illustrate deliverables. The proposed installation still needs its own demonstration.

<a id="english-section-8"></a>

## Two common procurement decisions

A rig may already have acceleration and controller logs but no independent final tip position. Another acceleration channel could improve local vibration coverage while leaving final position dependent on integration. Optical coordinates and existing event logs would answer complementary questions. Their purchase value depends on whether measured position can change a decision, such as detecting an outlet outside its target when the controller reports arrival.

A production station may instead check one stroke along an established axis on every machine. A full development installation need not be duplicated at every station. Stereo measurements on prototypes can establish whether the simpler production indicator remains meaningful across relevant poses. The choice then reflects the decision and how frequently it is needed.

For both cases, ask how results remain comparable after remounting. Check anchors and direction for linear sensors, orientation for accelerometers, scale and plane for monocular views, and scale, pose and task axes for stereo. An independent verification exercise and reusable data give the receiving team a stronger basis than a finished curve alone.

<a id="english-section-9"></a>

## Acceptance and long-term reuse

Use a real event for acceptance, with coordinates, identity, time and raw images. Have the receiving laboratory recompute a metric. Document setup and validation for later machine changes. Reusable spatial records can serve control, structural and simulation teams.

<a id="english-section-10"></a>

## Implementation workflow

### Define required outputs

Relate stroke, vibration and trajectories to decisions.

### Review existing channels

Identify directions, mounting, bandwidth and available quantities.

### Demonstrate the same task

Use common events and permitted stations for candidate systems.

### Recompute one result

Recover a component from coordinates and verify the original image.

### Plan ongoing use

Document setup, calibration and processing when changing machines.

<a id="english-section-11"></a>

## XTDIC equipment positioning and application value

XTDIC-STROBE addresses multipoint, non-contact spatial position measurement. Exported coordinates can be resolved into task directions and relative quantities for testing, control or model comparison.

Existing stroke and acceleration channels can retain their specialised roles while stereo observations add spatial paths and relationships between parts. A representative event and independently usable deliverables make that purchase rationale testable.

<a id="english-section-12"></a>

## Frequently asked questions

### Should existing sensors remain?

Retain reliable stroke or local high-frequency channels and use spatial tracking to add paths and multipoint relationships.

### What should acceptance data include?

Coordinates, times, identities, frames, valid intervals and images at extremes for independent recomputation.

### Which laboratories benefit most from this configuration?

Teams comparing machine types, poses or controls and sharing spatial histories with structural and modelling groups can make repeated use of the coordinates and images.

<a id="english-section-13"></a>

## Conclusion

Equipment selection should connect the development decision to the physical quantity required. For multipoint spatial displacement and trajectories, XTDIC-STROBE offers a non-contact configuration that can be evaluated against the site task. Representative trials, exported data and repeat analysis link procurement to a usable testing capability.

<a id="english-section-14"></a>

## References

[XTDIC-STROBE equipment information](https://www.xtop3d.com/products/xtdic-strobe.html) · [Three-dimensional boom displacement application](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>
