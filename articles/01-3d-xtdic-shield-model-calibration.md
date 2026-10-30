# 3D-XTDIC在大尺度盾构相似模型试验中的标定与同步：从视场划分到时序对齐

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 大尺度盾构相似模型的测量难点，往往先出现在坐标、覆盖范围和时间轴，而非沉降曲线本身。本文围绕多机位组网、分区联合标定、重叠视场、物理隔振与硬件脉冲触发，梳理掘进和后退工序的同步方法，并给出标定复核与数据质量检查思路。

> **关键词：** 3D-XTDIC；数字图像相关技术；相似材料模型；多机位标定；时序对齐；全场应变测量

## 目录

- [一、工程标定矛盾：大视场不等于统一基准](#一工程标定矛盾大视场不等于统一基准)
- [二、系统方案：把空间与时间基准分开处理](#二系统方案把空间与时间基准分开处理)
- [三、实施步骤：从组网到时序对齐](#三实施步骤从组网到时序对齐)
- [四、质量检查与沉降解释](#四质量检查与沉降解释)
- [五、常见问题](#五常见问题)

## 一、工程标定矛盾：大视场不等于统一基准

在轨道交通隧道研究中，大尺度盾构相似材料模型可用于观察掘进、后退等工序下的表面变形。模型范围扩大后，单组立体视觉视场可能无法同时覆盖隧道轴线、地表关注区和构筑物周边。增加机位扩展了覆盖范围，也带来三个关联问题：各机位坐标系是否一致，分区边界能否衔接，图像帧是否对应同一工序时刻。

数字图像相关技术通过匹配变形前后的图像子区估计位移，立体系统再结合标定关系重建三维坐标。如果各组相机各自使用局部坐标，单区云图可能看似连续，拼接后却会出现方向不一致或边界跳变。因此解释沉降前，应先建立可复核的时空基准，而非先调整色标。

### 1.1 先明确测量坐标与工序事件

方案宜先规定模型坐标轴、地表参考面、隧道轴线方向与位移正负号，并确定掘进开始、阶段暂停、后退开始及结束等事件。坐标定义服务于全场数据拼接，事件定义服务于曲线分段，两者不能互相替代。下穿构筑物模型还应明确关注区相对位置，避免后期凭图像外观选择比较区域。

## 二、系统方案：把空间与时间基准分开处理

3D-XTDIC多机位方案可分为空间层和时间层。空间层通过分区联合标定与重叠视场建立统一三维基准；时间层通过共同触发和事件记录建立统一帧序列。两层均需独立检查，因为图像时间一致并不代表坐标已经统一，反之亦然。

### 2.1 多机位组网与重叠视场

机位布置应从关注区域和遮挡关系出发，而非平均分割模型表面。相邻分区保留适量重叠区域，使同一物理位置能被两组立体系统观察。重叠区可用于检查位移方向、变化趋势及拼接连续性，也可帮助发现局部标定偏差。分区数量增加时，还需记录各机位与物理区域的对应关系，避免数据文件与现场位置错配。

标定过程中，各分区既要建立本组双相机的相对关系，也要接入共同的模型坐标基准。联合标定的重点不是让所有机位获得相同图像，而是使同一空间点在不同视场中的坐标表达可比较。若标定板无法覆盖整个大模型，可按分区采集，但应保持基准传递路径清晰，并在完成后进行跨区复核。

### 2.2 物理隔振与硬件脉冲触发

模型加载、人员走动或邻近设备可能引起相机支撑与模型之间的相对振动。隔振的重点是保持系统外部几何关系稳定：支撑独立稳固，减少相机支架与加载装置的接触，并检查线缆牵拉。隔振不能替代静态段检查；若静止图像仍有同步波动，应回查支撑与环境变化。

多机位采集可采用同一硬件脉冲源触发，并保存帧号、时间戳和触发记录。相比仅依据各设备软件时钟对齐，共同脉冲更便于识别漏帧和序列偏移。若机位无法全部共用触发，应至少保留可交叉核对的时间事件，并检查采集期间是否发生累积偏移。

## 三、实施步骤：从组网到时序对齐

实施顺序直接影响后续排查效率。建议先固定机械状态和坐标定义，再标定，随后验证同步，最后进入正式工序。机位移动、支撑碰撞或焦距调整后，都应重新评估原标定是否适用。

| 步骤 | 主要操作 | 检查证据 | 需要回查的情形 |
| --- | --- | --- | --- |
| 坐标与机位规划 | 定义坐标轴、关注区、重叠区和遮挡边界 | 机位图、区域编号、位移方向约定 | 区域漏覆盖或编号无法对应现场 |
| 分区联合标定 | 建立组内立体关系并传递共同基准 | 标定图像、残差分布、跨区公共点 | 局部残差异常或重叠区方向不一致 |
| 静态与隔振检查 | 在模型静止时连续采集并观察漂移 | 静态位移序列、支架与线缆状态 | 无工序变化却出现同步波动 |
| 同步验证 | 检查共同脉冲、帧号、时间戳和漏帧 | 触发日志、帧序列、事件记录 | 各机位帧数不符或事件位置偏移 |
| 工序采集 | 记录掘进、暂停、后退等事件并持续复核 | 工序日志、图像质量与相关性状态 | 遮挡、失配或时间轴中断 |

### 3.1 掘进与后退的时序对齐

时序对齐宜同时依据共同触发和工序事件。共同触发解决图像帧之间的对应关系，工序日志解决图像序列与物理过程的对应关系。正式采集前可用一个可识别事件检查各机位响应位置；试验中记录阶段切换对应的帧号，避免用文件创建时间推断工序。

掘进和后退应保留清晰的阶段边界。若个别机位存在漏帧，可依据帧号重新匹配有效数据，但不宜直接把缺失区间当作连续变形。跨阶段插值也应谨慎，因为阶段切换附近的位移变化可能包含真实工序响应。对齐后的基本检查是：同一事件在各机位序列中的位置一致，静止段没有伪造的阶跃，阶段切换处能够追溯原始记录。

### 3.2 标定复核不是一次性的前置动作

正式试验前的标定结果只能代表当时的相机几何关系。长过程采集中，可在不改变模型的条件下安排静态复核，并利用重叠区观察跨机位一致性。若试验后复核显示关系发生变化，应先界定受影响的时间段，再决定哪些数据可进入比较，而不是用后期标定直接替代前期标定。

## 四、质量检查与沉降解释

质量检查覆盖图像、相关计算、三维重建与时间连续性。图像层面关注曝光、清晰度、遮挡和散斑状态；计算层面关注相关失配、异常矢量及空洞；三维层面关注重叠区一致性和静态漂移；时间层面关注漏帧、重复帧与事件错位。异常时应保留原始图像与处理记录，以区分表面变化、图像变化与标定变化。

### 4.1 用多类证据判断异常

重叠区的差异不一定意味着某一组数据错误，也可能来自视角、遮挡或局部表面质量。排查时可回到公共区域的原始图像，比较同一时段的相关状态，再检查标定和触发日志。对孤立突跳，不宜只做平滑处理；对连续偏移，则应检查支撑稳定性或坐标基准变化。只有异常来源被记录，后续曲线筛选才有依据。

公开案例呈现的规律可说明解释顺序：地表沉降极值集中在隧道轴线正上方，掘进阶段位移持续增大，后退阶段出现小幅回弹。这些描述适用于该模型及其工序，不宜直接推广为所有地层或构筑物的共同规律。分析时可沿轴线和横向剖面比较位移场，并与已对齐的阶段对应。

此外，数字图像相关技术给出的是可观测表面位移及其计算的应变，不直接给出内部应力或承载状态。全场应变测量有助于定位变形集中区，但相似材料响应还受模型配比、边界条件和工序控制影响。因此结论宜表述为“在该模型中观察到”，并说明数据覆盖区、有效时段与异常处理原则。

当时空基准得到统一，下一阶段影响数据有效性的关键就转到被测表面：散斑是否稳定、子区是否合适，以及裂隙附近的数据空洞如何处理。下一篇将围绕这些问题展开。

## 五、常见问题

**1. 多机位采集后，直接拼接各组位移云图可以吗？**

不建议。应先检查组内立体标定、共同坐标基准和重叠区一致性，再判断能否拼接。仅统一色标不能消除坐标或标定差异。

**2. 有共同硬件触发后，还需要工序日志吗？**

需要。触发记录用于对齐采集帧，工序日志用于确定帧序列对应的掘进、暂停或后退事件，两者作用不同。

**3. 重叠区数据不完全重合，应如何处理？**

先检查视角、遮挡、散斑、相关状态和标定复核结果，再判断差异来源。未查明原因前，不宜用强制平滑掩盖边界差异。

**4. 后退阶段的小幅回弹能否直接解释为内部应力恢复？**

不能。表面位移回弹是该模型中的观测现象，内部机制还需结合边界、材料和工序信息分析，不能由位移场单独推出。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Calibration and Synchronization for 3D-XTDIC in Large-Scale Shield Tunneling Similar-Material Models: From Field Partitioning to Timeline Alignment

> **Abstract:** In a large shield-tunneling similar-material model, the first measurement challenges are often coordinate registration, field coverage, and timeline consistency rather than the settlement curves themselves. This article presents a practical 3D-XTDIC workflow for multi-camera layout, joint zonal calibration, overlapping fields of view, physical vibration isolation, and hardware-pulse triggering. It separates spatial registration from temporal synchronization, explains how excavation and retreat events can be aligned with image sequences, and summarizes checks for calibration drift, dropped frames, static displacement, and overlap consistency. The aim is to establish traceable surface-deformation evidence before interpreting settlement patterns or discussing possible mechanisms.

> **Keywords:** 3D-XTDIC; digital image correlation; similar-material model; multi-camera calibration; timeline alignment; full-field strain measurement

## Contents

- [1. The calibration problem behind a large field of view](#1-the-calibration-problem-behind-a-large-field-of-view)
- [2. A system layout with separate spatial and temporal controls](#2-a-system-layout-with-separate-spatial-and-temporal-controls)
- [3. Implementation from camera networking to event alignment](#3-implementation-from-camera-networking-to-event-alignment)
- [4. Quality checks before settlement interpretation](#4-quality-checks-before-settlement-interpretation)
- [5. FAQ](#5-faq)

## 1. The calibration problem behind a large field of view

A large similar-material model can be used in rail-transit research to observe surface deformation during shield excavation and retreat. As the model grows, one stereo pair may no longer cover the tunnel axis, the ground-surface region of interest, and the area around an overlying structure at the same time. Adding camera pairs expands coverage, but it also introduces three questions: do all pairs share one coordinate system, can adjacent zones be reconciled at their boundaries, and does every image frame correspond to the same physical stage?

Digital image correlation estimates displacement by matching image subsets before and after deformation. A stereo system then reconstructs three-dimensional coordinates using its calibration. If every camera pair retains an independent local frame, an individual displacement map may look plausible while the assembled map contains inconsistent directions or discontinuities. The first task is therefore to establish a traceable spatial and temporal reference, not to make the color maps look continuous.

### 1.1 Define coordinates and process events together

The test plan should state model axes, the surface reference, tunnel-axis direction, displacement signs, and events such as excavation, pauses, and retreat. Coordinates support spatial registration, while events support curve segmentation; neither replaces the other. Observation zones around an overlying structure should be tied to physical locations, not selected later from contour appearance.

## 2. A system layout with separate spatial and temporal controls

A multi-camera 3D-XTDIC configuration can be managed in two layers. The spatial layer uses zonal calibration and overlapping views to express measurements in a common three-dimensional frame. The temporal layer uses common triggering and event records to construct a consistent frame sequence. Each layer needs its own verification: synchronized images can still have incompatible coordinates, and registered cameras can still acquire frames at different process events.

### 2.1 Camera zones need useful overlap

Camera placement should follow regions of interest and occlusions rather than equal surface divisions. Adjacent zones need useful overlap so two stereo pairs observe the same area, providing checks for displacement direction, trend, boundary continuity, and local calibration. A camera-to-region map prevents files from being assigned to the wrong model area.

Each stereo pair needs its own relative geometry and a traceable relationship to the common model frame, so that coordinates for the same physical point are comparable across views. A target may be applied zone by zone when it cannot cover the model, but reference transfer must remain explicit and be checked across adjacent zones.

### 2.2 Isolate the supports and synchronize the triggers

Loading equipment, foot traffic, or nearby machinery can introduce relative camera-to-model motion. Stable supports, no unintended loading-frame contact, and control of cable pull can reduce this effect. Isolation does not replace a static test: apparent motion while the model is stationary still requires investigation.

Where the acquisition architecture permits, all camera pairs can receive pulses from the same hardware source. Frame numbers, timestamps, and trigger logs should be retained. A common pulse train makes dropped frames and sequence offsets easier to detect than alignment based only on separate software clocks. If some cameras cannot share the trigger, the acquisition record should at least contain cross-checkable events and a check for drift during the test.

## 3. Implementation from camera networking to event alignment

The order of work matters. Fix the mechanical arrangement and coordinate conventions first, perform calibration second, verify synchronization third, and only then begin the process sequence. Camera movement, a support impact, or a focus change can invalidate the previous geometric relationship and should trigger a calibration review.

| Workflow step | Main action | Evidence to retain | Reason to revisit the setup |
| --- | --- | --- | --- |
| Coordinate and camera planning | Define axes, observation zones, overlaps, and occlusion limits | Camera map, zone identifiers, sign convention | Missing coverage or ambiguous zone identity |
| Joint zonal calibration | Establish stereo geometry and transfer the common reference | Calibration images, residual distribution, shared points | Local residual anomalies or inconsistent overlap response |
| Static and isolation check | Acquire a stationary sequence and inspect apparent drift | Static displacement record, support and cable condition | Coherent motion without a process change |
| Synchronization check | Compare pulses, frame numbers, timestamps, and dropped frames | Trigger log, frame sequence, event record | Unequal sequences or displaced event positions |
| Process acquisition | Log excavation, pauses, and retreat while monitoring quality | Process log, image state, correlation status | Occlusion, matching loss, or timeline interruption |

### 3.1 Align both frames and excavation stages

Frame alignment and stage alignment are different tasks. Common triggering establishes correspondence among image frames, while the process log links those frames to excavation and retreat. Before the formal test, an identifiable event can be used to check whether every camera records the same sequence position. During the test, the frame numbers associated with stage transitions should be logged instead of inferred later from file creation times.

Excavation and retreat need explicit boundaries. Dropped frames can be matched by frame number, but missing intervals are not continuously observed deformation. Interpolation across a stage change also requires caution because the boundary response may be meaningful. Aligned data should have consistent event positions, no artificial steps in stationary intervals, and traceable stage-transition records.

### 3.2 Calibration review continues during the test

Calibration describes camera geometry at one point in time. Static and overlap checks during a long test can indicate whether it remains applicable. If the geometry changes, the affected interval should be identified; a later calibration cannot simply replace the earlier one.

## 4. Quality checks before settlement interpretation

Quality control should cover four kinds of evidence. Image review addresses exposure, focus, occlusion, and speckle condition. Correlation review addresses matching loss, outliers, and gaps. Three-dimensional review addresses overlap consistency and static drift. Timeline review addresses missing frames, duplicates, and event offsets. When an anomaly appears, the original images and processing history should be retained so that a surface change can be distinguished from an imaging or calibration change.

An overlap difference does not identify which camera pair is wrong; view angle, occlusion, or texture may also contribute. Review the shared-region images and correlation status before checking calibration and triggers. Isolated jumps should not merely be smoothed, while sustained offsets require a review of supports and coordinate registration.

The available observations illustrate the interpretation order. In that model, settlement extrema were concentrated directly above the tunnel axis; displacement increased during excavation, followed by a small rebound during retreat. These are model-specific observations, not universal rules. Axis and transverse sections should be compared only after their curves share the excavation-and-retreat timeline.

### 4.1 Keep measurement and mechanism separate

Digital image correlation measures the observable surface and derives displacement and strain from image sequences. It does not directly measure internal stress or the structural condition of the model. Full-field strain measurement can help locate concentrations, but interpretation still depends on material similarity, boundary conditions, and process control. Conclusions should therefore be bounded by the observed model, the valid coverage, the usable time intervals, and the documented treatment of anomalies.

Once the spatial and temporal references are consistent, attention shifts to the measured surface itself. The next article examines speckle quality, subset selection, and the control of data gaps around cracks and boundaries.

## 5. FAQ

**1. Can displacement maps from different camera pairs be stitched directly?**

Not without checks. Stereo calibration, the shared coordinate frame, and overlap consistency should be reviewed first. A common color scale alone does not remove registration differences.

**2. Is a process log still necessary with common hardware triggering?**

Yes. Trigger records align acquisition frames, while the process log identifies which frames correspond to excavation, pauses, or retreat.

**3. What should be done when overlap-zone measurements differ?**

Review viewing conditions, occlusion, speckle quality, correlation status, and calibration evidence. Smoothing the boundary before identifying the cause can hide a real acquisition problem.

**4. Does rebound during retreat demonstrate recovery of internal stress?**

No. It is an observed surface-displacement response in that model. An internal mechanism requires additional evidence from the material, boundaries, and process conditions.

</details>
