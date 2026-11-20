# 吊臂动态位移测量设备怎么选？XTDIC-STROBE 与位移计、加速度计及视频的任务对比

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 吊臂动态位移测量设备怎么选？XTDIC-STROBE 与位移计、加速度计及视频的任务对比</b></summary>

<a id="chinese-version"></a>

准备给臂架试验台配置测量设备时，最容易写出的需求是“既能测大位移，又能测振动”。这句话还不足以选型。需要知道的是固定方向的行程、若干位置的空间轨迹、端头停止后的微小振动，还是结构局部的应变？它们的原始测量量与参考基准不同。XTDIC-STROBE 最有针对性的任务，是在可见区域内同时得到多个特征点有尺度的三维位置，并从同一批记录提取分向位移、相对距离和轨迹。 [参考试验](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**本文目录**

- [从最终要交给谁的结果开始](#chinese-section-1)
- [四种方法的原始证据](#chinese-section-2)
- [什么时候单目够用，什么时候值得上双目](#chinese-section-3)
- [把设备演示改成可比较的样题](#chinese-section-4)
- [采购评审中的两个典型取舍](#chinese-section-5)
- [选型结论如何写进采购需求](#chinese-section-6)

<a id="chinese-section-1"></a>

## 从最终要交给谁的结果开始

负责回转机构的人可能只需要知道某一固定方向的行程何时到达极限。控制开发人员则可能需要每次制动时端头向哪边越过目标、越过之后怎样返回，以及动作时间有没有变长。结构设计人员更关注不同臂节的相对运动，试图分辨底座转动、关节运动与臂段弯曲。把这些需求都归入“测摆幅”，各方最终可能拿到同一个最大值，却没法用来作出各自的决定。

把需求改写成一个可验收的句子会更有效。例如“在同一回转动作中，记录臂端和中间臂节相对车体基准的带时间三维坐标，并能追溯峰值处的原始画面”。读到这里，供应方就知道需要共同时间、可见目标、车体参考和数据导出；而只要“验证液压缸沿自身轴线的行程”，则已有的直线位移通道可能已经适用。下面的对照基于测量原理，不涉及不同厂家的性能排名。

<a id="chinese-section-2"></a>

## 四种方法的原始证据

| 方法 | 直接获得的证据 | 适合的问题 | 实施前要核实 |
| --- | --- | --- | --- |
| 拉线或直线位移计 | 传感器测量方向上的长度变化 | 固定基准到目标的单向行程 | 安装点、行程、运动中方向变化和布线 |
| 加速度计 | 安装点沿敏感方向的加速度信号 | 局部振动、瞬态冲击、频率成分 | 方向、固定方式、重力影响与同步 |
| 单目视频 | 图像平面中的位置、轮廓与事件顺序 | 平面内运动、工况回放 | 标尺所在平面及出平面运动 |
| XTDIC-STROBE 双目跟踪 | 共同可见特征点的空间坐标与时序 | 多点三维轨迹、带方向的偏摆、相对运动 | 双目几何、标记可见性和现场实际分辨能力 |

### 有可用的固定基准时，单向测量很直接

测绳两端的距离变化具有明确的几何含义。若目标沿同一直线运动且锚点稳定，利用这种变化描述行程十分直观。若端头绕锚点画弧，测绳长度可能变化很小，即使端头已经横向移动较远。还有一种情形是绳长在变，但变化同时包含水平与竖向运动。这些都不是传感器读错了，而是测得的距离与需要的坐标分量不同。采购时最好先在布置图上画出测量方向，再判断该通道能否代表目标量。

### 有清晰振动信号时，为什么还要看位移

加速度计适合观察某个位置的快速响应。要由加速度推回位移，需要处理初始速度、基线和积分漂移；端臂姿态改变时，敏感轴和重力的相对方向也会变化。对停稳后的高频局部响应，加速度记录可能更有辨识力；对端头从何处经过、最终停在哪里，光学坐标的物理含义更直接。若两类问题都重要，可在同一位置附近布点，统一方向与时间，保留各自原始通道。再比较由光学位移导出的加速度时，须注意求导会放大图像噪声，两种信号的有效带宽也可能不同。

<a id="chinese-section-3"></a>

## 什么时候单目够用，什么时候值得上双目

若目标始终在已知平面内移动，镜头固定、成像几何经过核查，单目视频可以给出有尺度的平面轨迹。对泵车这种端头会朝镜头接近或远离的工况，同样一段真实移动投影到图像中的长度会随深度改变。此时即使画面很清晰，人眼能看出“在晃”，一张照片里的标尺也难把整个动作换算成可靠的空间轨迹。双目系统增加一个观察方向，可以用匹配的视线重建深度，并将已记录的轨迹转换到作业坐标系中。

三维重建仍受视角、距离与特征质量约束。如果采购任务是辨认很小的面外位移，应在计划的远距离机位上沿该方向做独立检验。如果只展示横向大位移的流畅轨迹，无法证明同一系统也能分辨较小的深度变化。原文的吊臂和泵车案例为设备能交付什么提供了实例。不同机位、不同臂长、不同速度下的能力则应通过用户现场试拍确定。

<a id="chinese-section-4"></a>

## 把设备演示改成可比较的样题

可请各候选方法面对同一组动作，分别交付开始时刻、最大侧偏、端头路径和停止后的记录，然后把每项结果标为直接测得、经计算得到或当前布置无法提供。这样一来，单向位移计在职责范围内的优势很清楚，单目视频能高效记录的现场上下文也得到保留。对于 XTDIC-STROBE，演示的核心是能否从同一份坐标文件恢复三条分量曲线、追溯极值帧，并说明缺失数据落在哪一段。在真实工作距离上完成这组任务，比展示仪器在近距离跟踪清晰标记更有参考价值。

再问一句“以后换机型需要重新做什么”。相机机位、镜头、标定关系、点位编号以及外部方向基准能否复现，决定同一设备在后续试验中的使用成本。接触通道的成本可能主要来自安装与走线，光学通道则可能来自布置视场、维护可见性和处理数据。把首套配置的建立工时和后续每次复测的工作分别评估，比简单比较产品功能数量更贴近实验室实际。


<a id="chinese-section-5"></a>

## 采购评审中的两个典型取舍

一种任务是现有试验台已经有加速度与控制日志，缺的是端头最终停在哪里。若再增加一个同类加速度通道，可能更清楚地看到局部振动，但对最终位置仍需积分与初始条件。此时用光学系统补充绝对或相对坐标，并以已有日志标记动作阶段，可以让各仪器覆盖彼此薄弱的部分。是否值得增加该配置，取决于独立位置观测能否改变设计判断，例如能否发现程序显示到位而实体端头仍处于目标外侧。

另一种任务是每台成品只检查同一方向上的一个行程，并且机器已有稳定、易于校核的测量基准。如果结果只用于判断是否达到既定位置，研发阶段使用的多点三维方案未必需要复制到每个工位。可以在样机试验时用 XTDIC-STROBE 核对这个简化指标是否对不同姿态都有效，再决定日常检查保留哪些通道。这样评价仪器时，讨论的是它能支持哪一次决策，以及这项决策多久需要重复。

两类用户在验收时还可以提出同一个问题：更换镜头或调整安装位置后，怎样知道新旧结果仍能比较？直线位移计要检查锚点与测量方向，加速度计要检查安装朝向，单目要核对标尺和平面，双目则要验证尺度、相对几何与任务坐标。让仪器交付方演示一次独立校核，并把可复算的数据和方法交给使用团队，比仅接受一张测试结束时的漂亮曲线更能降低后续使用的不确定性。

<a id="chinese-section-6"></a>

## 选型结论如何写进采购需求

单一轴向行程有稳定基准时，可优先保留现有位移通道；局部快速振动是主要指标时，应保留有合适频带的振动传感器。若任务跨多个可见位置、需要区分横向与竖向回摆，或要把实测轨迹交给控制和仿真团队，XTDIC-STROBE 更值得安排现场验证。需要焊趾或板件的局部应变时，则应另行设计散斑观测区、空间尺度和加载方案，稀疏标记的轨迹不足以给出臂架连续应变场。

可在需求书里约定实物演示、数据样件和复算方法：采购方指定典型动作，供方在可用机位交付带点号与时间的坐标、坐标系说明、有效区间和原始图像，再由实验室独立计算一个约定的偏摆指标。这样的设备推荐有清楚的适用条件，也能在交付时检验。

**设备与案例资料**

- [XTDIC-STROBE 动态测量系统与应用范围](https://www.xtop3d.com/products/xtdic-strobe.html)
- [起重机吊臂偏摆实测图与曲线（英文）](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**延伸阅读**

- [229 · 大型吊臂在室外怎样布置三维 DIC？XTDIC-STROBE 大视场测试方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-outdoor-stereo-setup.md#chinese-version)
- [232 · 吊臂抑摆控制改进如何验证？用 XTDIC 多点轨迹对标制动策略与动力学仿真](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-anti-sway-validation.md#chinese-version)

</details>

<details>
<summary><b>English · Choosing Equipment for Crane Boom Motion: XTDIC-STROBE, Displacement Sensors, Accelerometers and Video</b></summary>

<a id="english-version"></a>

# Choosing Equipment for Crane Boom Motion: XTDIC-STROBE, Displacement Sensors, Accelerometers and Video

A request to measure both large travel and vibration is too broad to select equipment. Fixed-axis travel, spatial trajectories, small residual vibrations and local strain are different quantities. XTDIC-STROBE is a strong candidate when the required evidence is a time history of scaled spatial coordinates for several visible features, from which directional displacement, relative distances and paths can be obtained. [Reference tests, in Chinese](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**Contents**

- [Start with the person using the result](#english-section-1)
- [What each method observes](#english-section-2)
- [When a second camera earns its place](#english-section-3)
- [Give competing methods the same task](#english-section-4)
- [Two common procurement decisions](#english-section-5)
- [A purchase specification with a meaningful acceptance test](#english-section-6)

<a id="english-section-1"></a>

## Start with the person using the result

A mechanism engineer may need to know when a travel limit is reached. A controls engineer may need overshoot direction, return path and cycle duration. A structural engineer may need relative movement between boom sections to investigate base rotation, joint motion and bending. A single maximum called “sway amplitude” cannot serve all three.

Specify a verifiable output. For example, request time-stamped three-dimensional coordinates of the tip and an intermediate station relative to the chassis, with original images at the extreme. This implies common timing, chassis references and exportable coordinates. For hydraulic cylinder travel along its own axis, an existing linear channel may suffice. The comparison below concerns measurement principles.

<a id="english-section-2"></a>

## What each method observes

| Method | Direct evidence | Good application | Installation question |
| --- | --- | --- | --- |
| Draw-wire or linear sensor | Length change along its measurement geometry | Travel between a stable reference and a point | Anchoring, range, cable route and changing angle |
| Accelerometer | Acceleration at its mounting point along sensitive axes | Local vibration, impacts and frequency content | Mounting, gravity, orientation and timing |
| Single-camera video | Image-plane position, outline and event order | Planar movement and visual review | Calibration plane and out-of-plane motion |
| XTDIC-STROBE stereo tracking | Spatial coordinates of jointly visible features over time | Multipoint trajectories, signed sway and relative motion | Stereo geometry, visibility and site resolution |

A cable measures end-to-end distance. It works naturally for straight motion from a stable anchor. A target moving around an arc centred on that anchor can travel laterally with almost no change in cable length. Other paths mix vertical and horizontal movements into one length. Draw the measurement geometry before treating length change as a displacement component.

An accelerometer can resolve fast local responses. Recovering displacement by integration requires initial conditions and control of drift. Changes in boom orientation also change gravity projection. For local high-frequency vibration an accelerometer may be the better channel. For the route of a tip and its final position, optical coordinates have a direct interpretation. When both matter, measure near a common location with matched axes and timing. Differentiating optical displacement amplifies noise, and any comparison with acceleration needs a common effective bandwidth.

<a id="english-section-3"></a>

## When a second camera earns its place

With a fixed camera, verified scale and a target confined to a known plane, monocular video can deliver a scaled planar path. When a pump outlet moves toward or away from the camera, projection scale changes. Even excellent footage and a ruler in one plane may leave the spatial route ambiguous. Stereo observations provide depth from corresponding sight lines and allow the recorded path to be expressed in task coordinates.

Depth resolution depends on geometry, distance and feature quality. If a small depth displacement matters, test a known movement in that direction from the intended stations. A smooth demonstration of large transverse travel cannot establish sensitivity to a much smaller depth change. Published boom and pump cases illustrate deliverables. The proposed installation still needs its own demonstration.

<a id="english-section-4"></a>

## Give competing methods the same task

Ask each method to report a motion start, maximum lateral displacement, tip path and post-stop response for the same cycle. Identify results observed directly, obtained through calculation or unavailable with that installation. For stereo tracking, request component histories reconstructed from an exported coordinate file, an original image at the extreme and clearly marked gaps. Run the demonstration at the intended working distance.

Then ask what must be repeated for the next machine. Camera stations, focal settings, calibration, identifiers and axis references affect repeatability. Contact methods require installation and cabling. Optical methods need shared visibility and processing. Evaluate first-time setup separately from the work required for routine repeat tests.


<a id="english-section-5"></a>

## Two common procurement decisions

A rig may already have acceleration and controller logs but no independent final tip position. Another acceleration channel could improve local vibration coverage while leaving final position dependent on integration. Optical coordinates and existing event logs would answer complementary questions. Their purchase value depends on whether measured position can change a decision, such as detecting an outlet outside its target when the controller reports arrival.

A production station may instead check one stroke along an established axis on every machine. A full development installation need not be duplicated at every station. Stereo measurements on prototypes can establish whether the simpler production indicator remains meaningful across relevant poses. The choice then reflects the decision and how frequently it is needed.

For both cases, ask how results remain comparable after remounting. Check anchors and direction for linear sensors, orientation for accelerometers, scale and plane for monocular views, and scale, pose and task axes for stereo. An independent verification exercise and reusable data give the receiving team a stronger basis than a finished curve alone.

<a id="english-section-6"></a>

## A purchase specification with a meaningful acceptance test

Retain an existing linear channel for a well-defined single-axis stroke, or a suitably band-limited vibration channel for high-frequency local response. Arrange a site demonstration of XTDIC-STROBE when the decision needs several visible stations, horizontal and vertical recoil or measured paths for control and simulation teams. Local strain at a weld or panel requires its own patterned area, spatial resolution and loading arrangement. Sparse target trajectories do not establish a continuous boom strain field.

Specify the representative event, available stations, named targets, time-stamped coordinates, frame definition, valid intervals and raw images. Have the receiving laboratory recompute one agreed sway measure independently. This makes the case for buying an instrument depend on the question it can demonstrably answer.

**Equipment and case documentation**

- [XTDIC-STROBE dynamic measurement system and applications](https://www.xtop3d.com/products/xtdic-strobe.html)
- [Crane boom test images and displacement curves](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**Related articles**

- [229 · Planning an Outdoor Large-Field Stereo DIC Test for a Crane Boom with XTDIC-STROBE](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-outdoor-stereo-setup.md#english-version)
- [232 · Validating Crane Boom Sway Control with XTDIC Multipoint Trajectories and Dynamic Models](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-anti-sway-validation.md#english-version)

</details>
