# 桥隧边坡测量方案怎么选：静态、动态、高速与长周期工况的适配矩阵

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 桥隧与边坡的测量需求差别很大，分级加载、振动台激励、冲击落石与跨季节观测对采样节奏的要求几乎没有交集。本文按四类工况梳理各自的采样特征与配置要点，给出系统类型与测量手段的适配矩阵，说明点式与影像手段如何分工，并列出五种常见误配，供方案讨论时对照。

> **关键词：** XTDIC三维全场测量；数字图像相关技术；桥隧边坡；工况适配；高速测量；长周期观测；测量方案

## 目录

- [一、先把工况分清楚](#一先把工况分清楚)
- [二、四类工况各自需要什么](#二四类工况各自需要什么)
- [三、适配矩阵：系统类型与配置取舍](#三适配矩阵系统类型与配置取舍)
- [四、点式手段与影像手段怎么分工](#四点式手段与影像手段怎么分工)
- [五、五种常见误配](#五五种常见误配)
- [六、常见问题](#六常见问题)

## 一、先把工况分清楚

方案讨论最常见的偏差是先定设备再找场景。分级加载的支架、振动台上的边坡模型、落石冲击的防护构件、跨季节的隧道洞口，看着都是桥隧边坡的活儿，时间尺度却差好几个数量级。塞进同一套配置，得到的往往是覆盖很宽、每项都打折的方案。

实用的分法先看两个量：观测持续多久，关心的事件多快结束。分级递增、级间有停顿的属静态与准静态；往复或移动荷载、持续数秒到数分钟属中速动态；冲击、断裂、崩落以毫秒计属高速瞬态；跨数周到数年、需反复回到同一位置比对属长周期。这两量定了，相机、标定、同步与散斑工艺才有讨论基础。

| 工况类型 | 时间尺度 | 主要关心的问题 | 对采样的核心要求 |
| --- | --- | --- | --- |
| 静态与准静态 | 数十分钟到数小时，分级停顿 | 各级荷载下的全域变形与应变分布 | 级间可重复采集，视场覆盖完整，标定稳定 |
| 中速动态 | 数秒到数分钟，往复或移动激励 | 峰值响应、相位关系、随时间的衰减 | 采集与激励同步，采样覆盖主要振动周期 |
| 高速瞬态 | 毫秒到几十毫秒 | 开裂瞬间、飞散轨迹、断裂路径 | 短曝光、高帧率、连续存储不丢帧 |
| 长周期 | 数周到数年，重复观测 | 趋势、速率、跨季节与跨年份的对比 | 站位与光轴可复现，标定可复核，环境可记录 |

## 二、四类工况各自需要什么

### 静态与准静态：节奏跟着加载走

分级加载、结构验收、支架加载都属这类。荷载级之间有停顿，图像按级采集即可，不必追求连续帧率，重点是每级记录完整、级间参考一致，更看重视场标定与照明稳定性而非采集速度。XTDIC-CONST 系列定位三维全场应变测量，面向常规静态与准静态场景。在适宜条件下位移分辨力可到 0.01 mm 亚毫米级；视场放大、散斑变粗或标定残差上升时，这一水平随之抬升。

### 中速动态：同步比帧率更关键

振动台试验、行车通过、施工扰动带来的变形持续不长但变化较快。难点不是相机快不快，而是图像与激励在时间轴上对不对齐。触发各自为政，峰值可能落在两帧之间，量值偏低，相位关系随之失真。XTDIC-STROBE 系列面向三维动态测量，载荷与图像时序同步是这类工况的配置重点。

### 高速瞬态：不是常规配置的延伸

冲击、爆破、落石、断裂这类事件常以毫秒计。要在几十毫秒里取到足够帧，同时让曝光短到不糊，靠的是专用高速系统，而不是把普通相机的采集间隔调小。XTDIC-SPARK 系列定位三维高速测量。常见误解是“帧率够就行”，实际上分辨率、曝光、存储带宽与照明强度互相牵制，任一项跟不上，结果都会打折。

### 长周期：可重复性优先于单次精度

边坡、隧道运营期、跨季节观测，真正难的不是单次精度，而是让第一次和第五十次能放在一张图上比较。做法有两类：固定站点连续采集，或按周期回到同一位置、同一角度重复观测。两者都要求站位、光轴与参考状态可复现，标定定期复核，温度、光照、遮挡有记录。手段上，XTDIC-VG 系列视频引伸计可对关键标距内的变形做连续读数。

## 三、适配矩阵：系统类型与配置取舍

把分析压成一张表。矩阵表达适配关系，不是排序。同一项目常同时存在两类以上工况，如支架加载属准静态、落石防护属高速瞬态，可能需要两套配置而非一套折中方案。

| 工况 | 采样特征 | 推荐系统类型（系列层级） | 关键配置 | 容易踩的坑 |
| --- | --- | --- | --- | --- |
| 静态与准静态 | 分级采集，级间停顿 | CONST 系列（三维全场应变） | 大视场标定、均匀补光、级间参考统一 | 每级重新标定，导致级间不可比 |
| 中速动态 | 连续采集，与激励同步 | STROBE 系列（三维动态） | 硬触发同步、采样覆盖主要周期 | 相机与激励源各自计时 |
| 高速瞬态 | 短曝光、高帧率、连续存储 | SPARK 系列（三维高速） | 强补光、大带宽存储、预触发 | 用常规相机降间隔代替高速系统 |
| 长周期 | 定点重复或连续，跨季节 | CONST 与 VG 组合，固定站 | 站位复现、定期标定复核、环境记录 | 换站位后直接拼接序列 |

配置层面还有几件事宜在方案阶段定：散斑制作与视场、拍摄距离匹配，多尺寸工具能减少返工；补光按现场条件估算，室外考虑风振与温漂；标定不只在开始时做，长周期观测要安排复核节点。

## 四、点式手段与影像手段怎么分工

讨论选型时常有人把点式与影像对立起来。两者回答的是不同问题：点式给出特定位置的绝对量与时程，量值溯源清楚，长期稳定；影像给出空间分布，能看出应变往哪集中、裂纹从哪起、路径怎么走。

| 手段 | 能提供 | 局限 |
| --- | --- | --- |
| 点式（位移计、应变片、水准与全站观测） | 绝对基准、单点高精度时程、长期稳定读数 | 空间不连续，布点位置依赖经验，可能漏掉集中区 |
| 影像（DIC 全场测量） | 全域位移与应变、裂纹起裂位置与扩展路径、可视化过程 | 需要良好散斑与光照，遮挡区无数据，绝对基准需外部参照 |

组合使用比单一手段更稳：点式给影像场做基准校核，影像场反过来解释布点是否合理、异常区有没有被覆盖。碗扣式钢管支架试验是个例子：在不同步距和斜撑设置下对立杆加载，获取三维全场变形及应变，并与有限元对比变形规律，说明影像、计算与点式读数互为参照。

## 五、五种常见误配

**用静态系统拍瞬态。** 分级采集面对冲击几乎必然丢帧，事后补拍也补不回同一事件。事件历时除以最短采集间隔只剩个位数帧，就该换系统。

**用高速系统做长周期。** 高速设备的存储与散热按短时爆发设计，连续跑几周不现实。长周期要的是稳定与可复现，不是帧率。

**视场铺得太大。** 为“一次拍全”把整段边坡塞进一个视场，单像素对应尺寸变大，分辨率不够分辨局部化带。更稳的做法是分区布设，或用全局控制点标定做多视场拼接。

**相机与加载装置共架。** 两者同处一个刚性基础，框架受力的微小变形直接进入结果，看上去像试件在动。支架宜与加载系统解耦，或在处理阶段扣掉支架位移。

**只看云图不看参考帧。** 云图直观，但参考帧决定“相对于何时”。不同批次换了参考帧却直接比较，趋势可能是假的。参考状态、色标与量纲应在出图时标注。

选对配置只是第一步。同一套设备与参数，若站位、参考帧、色标和命名规则在不同批次各自变化，序列照样没法横向比较。这属于数据治理，留到下一篇。

## 六、常见问题

**1. 静态系统能不能拍振动台试验？**

可以拍到图像，但不一定拍到需要的信息。关键看激励主要周期是否被采样覆盖，以及相机与振动台是否同步。若主要响应集中在少数几个周期内，分级采集容易漏峰值，此时动态系列更适配。

**2. 高速测量是不是帧率越高越好？**

不是。帧率、分辨率、曝光与存储带宽互相牵制，帧率提上去往往要在分辨率或记录时长上让步。应按事件持续时间和需分辨的最小特征反推配置，而非单看一个指标。

**3. 长周期观测为什么反复强调固定站位？**

站位一变，光轴、视场与参考状态随之改变，两批数据之间就多了无法分离的系统差。固定站位、角度与参考，是序列可比的前提。

**4. 点式仪器和影像系统要不要同时上？**

取决于要回答什么。关心绝对量值与时程，点式更直接；关心空间分布与裂纹路径，影像更直接。同时使用时，互相校核价值更大。

**5. 视场放大以后，位移分辨力怎么变？**

位移分辨力随视场与成像条件变化。视场从几米扩到几十米，同一台相机单个像素覆盖的实际尺寸变大；散斑颗粒尺度、标定残差、光照与振动再叠加进来，能分出的最小位移随之变化。方案阶段的常规做法是按目标分辨力反推视场与相机配置，并用测量过程记录的干扰因素给出误差评价。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Choosing a Measurement Setup for Bridges, Tunnels and Slopes: An Adaptation Matrix for Static, Dynamic, High-Speed and Long-Term Conditions

> **Abstract:** Measurement needs in bridge, tunnel and slope work differ far more than the shared hardware suggests. Stepwise loading, shaking-table excitation, impact events and seasonal observation each impose a different sampling rhythm. This article sorts the requirements into four condition types, presents an adaptation matrix linking condition, sampling behaviour, system family and configuration, and explains how point sensors and imaging complement each other, together with five common mismatches.

> **Keywords:** XTDIC 3D full-field measurement; digital image correlation; bridge, tunnel and slope; condition adaptation; high-speed measurement; long-term observation; measurement planning

## Contents

- [1. Start with the working condition, not the equipment list](#1-start-with-the-working-condition-not-the-equipment-list)
- [2. What each of the four conditions actually needs](#2-what-each-of-the-four-conditions-actually-needs)
- [3. An adaptation matrix for system family and configuration](#3-an-adaptation-matrix-for-system-family-and-configuration)
- [4. Dividing work between point sensors and imaging](#4-dividing-work-between-point-sensors-and-imaging)
- [5. Five common mismatches](#5-five-common-mismatches)
- [6. FAQ](#6-faq)

## 1. Start with the working condition, not the equipment list

The most common mistake in planning is to choose hardware first and look for a scenario afterwards. A scaffold under stepwise loading, a slope model on a shaking table, a protective element struck by falling rock, and a tunnel portal observed across seasons look like variations of one problem. Their time scales differ by orders of magnitude and their sampling requirements barely overlap. Forcing them into one configuration produces a plan that covers everything on paper and underperforms everywhere.

A practical sorting uses two quantities: how long one session lasts, and how quickly the event of interest unfolds. Load applied in increments with pauses between them is static or quasi-static. Repeated excitation or a moving load lasting seconds to minutes is moderate-speed dynamic. Impact, fracture and collapse finishing within milliseconds are high-speed transients. Change accumulated over weeks to years, where the same location must be revisited, is long-term. Once these are fixed, camera choice, calibration, synchronisation and speckle preparation become discussable rather than arbitrary.

| Condition | Time scale | Central question | Core sampling requirement |
| --- | --- | --- | --- |
| Static and quasi-static | Tens of minutes to hours, with pauses between load steps | Full-field deformation and strain at each load level | Repeatable capture per step, complete field of view, stable calibration |
| Moderate-speed dynamic | Seconds to minutes, repeated or moving excitation | Peak response, phase relation, decay over time | Acquisition synchronised with excitation, sampling covering the dominant period |
| High-speed transient | Milliseconds to tens of milliseconds | The instant of cracking, debris trajectory, fracture path | Short exposure, high frame rate, continuous recording without dropped frames |
| Long-term | Weeks to years, repeated observation | Trend, rate, comparison across seasons and years | Reproducible station and optical axis, re-checkable calibration, recorded environment |

## 2. What each of the four conditions actually needs

### Static and quasi-static: the rhythm follows the loading

Stepwise loading, structural acceptance work and scaffold load tests all belong here. Pauses between load levels make level-by-level capture sufficient; continuous frame rate is not the objective, completeness and reference consistency are. Field-of-view calibration and illumination stability matter more than acquisition speed. The XTDIC-CONST family is positioned for 3D full-field strain measurement in routine static and quasi-static work, a natural fit for this group. Under suitable conditions displacement resolution reaches the 0.01 mm sub-millimetre band; widen the field, coarsen the speckle or leave calibration residuals unchecked and that band moves up.

### Moderate-speed dynamic: synchronisation matters more than frame rate

Deformation from shaking-table tests, passing vehicles or construction disturbance does not last long but changes quickly. The difficulty is less about camera speed than about whether images and excitation share a time axis. If acquisition and the loading system each run on their own clock, a peak may fall between two frames: the amplitude reads low and the phase relation misleads. The XTDIC-STROBE family addresses 3D dynamic measurement, and synchronising load with image sequence is the configuration priority here.

### High-speed transient: not an extension of the ordinary setup

Impact, blasting, rockfall and fracture complete within milliseconds. Capturing enough frames while keeping exposure short enough to avoid blur requires a dedicated high-speed system, not an ordinary camera with a shortened interval. The XTDIC-SPARK family is positioned for 3D high-speed measurement and is the appropriate instrument for this group. A common misconception is that frame rate alone decides the outcome. Resolution, exposure, storage bandwidth and illumination constrain one another, and any weak link reduces what the record can support.

### Long-term: repeatability before single-measurement precision

For slopes, operating tunnels and seasonal observation, the difficult part is not absolute accuracy but making measurement one and measurement fifty comparable. Two approaches work: a fixed station recording continuously, or campaigns returning to the same position and angle on a schedule. Both require a reproducible station, optical axis and reference state, periodic calibration checks, and a record of temperature, lighting and obstruction. For hardware, a video extensometer such as the XTDIC-VG family suits continuous reading within a defined gauge length, while the microscopic family addresses material-scale observation.

## 3. An adaptation matrix for system family and configuration

Compressed into one table, the analysis is easier to use in discussion. The matrix describes adaptation, not ranking. A single project often contains more than one condition type: scaffold loading is quasi-static while rockfall protection is a high-speed transient, so the honest answer may be two configurations rather than one compromise.

| Condition | Sampling behaviour | System family (family level) | Key configuration | Frequent pitfall |
| --- | --- | --- | --- | --- |
| Static and quasi-static | Stepwise capture with pauses | CONST family (3D full-field strain) | Large-field calibration, even illumination, consistent inter-step reference | Recalibrating at every step, making steps incomparable |
| Moderate-speed dynamic | Continuous capture synchronised with excitation | STROBE family (3D dynamic) | Hard trigger synchronisation, sampling covering the dominant period | Camera and excitation source timing independently |
| High-speed transient | Short exposure, high frame rate, continuous storage | SPARK family (3D high-speed) | Strong illumination, high-bandwidth storage, pre-trigger | Shortening the interval of an ordinary camera instead |
| Long-term | Fixed-point repeated or continuous, across seasons | CONST with VG, fixed station | Reproducible station, periodic calibration check, environmental record | Joining sequences recorded from different stations |

Beyond the family, several configuration decisions belong in the planning stage. Speckle preparation should match the field of view and working distance, and tools that produce patterns at several scales reduce rework. Illumination should be estimated from site conditions; outdoors, wind-induced vibration and thermal drift affect mounts and optical axes. Calibration is not a one-off: long-term observation needs scheduled re-checks. None of this appears in a quotation, yet it decides whether the data can be used later. ## 4. Dividing work between point sensors and imaging

Selection discussions often frame point instruments and imaging as competitors, yet they answer different questions. Point sensors report absolute values and time histories at specific locations, with clear traceability and stable long-term readings. Imaging reports spatial distribution: where strain concentrates, where a crack starts, which path it follows.

| Approach | What it provides | Limitation |
| --- | --- | --- |
| Point sensors (displacement transducers, strain gauges, levelling and total-station observation) | Absolute reference, high-precision time history at a point, stable long-term readings | Spatially discrete, placement depends on judgement, concentration zones may be missed |
| Imaging (DIC full-field measurement) | Full-field displacement and strain, crack initiation location and propagation path, visual record | Requires good speckle and lighting, no data in occluded areas, absolute reference needs external support |

Used together they are steadier than either alone: point readings anchor the image-derived field, while the field shows whether the points covered the zones that mattered. A scaffold loading test illustrates the combination: a cuplock steel tube scaffold was loaded at uprights under different step distances and bracing arrangements, three-dimensional full-field deformation and strain were acquired, and the pattern was compared with finite element results to support scaffold design. That quasi-static case shows how imaging, computation and point readings reference one another.

## 5. Five common mismatches

**A static system used for a transient event.** A stepwise configuration will almost certainly drop frames, and a repeat test never reproduces the same event. Divide the event duration by the shortest acquisition interval; if the result is a single-digit number of frames, the system is the wrong one.

**A high-speed system used for long-term observation.** High-speed hardware is built for short bursts in storage and thermal behaviour. Running it for weeks is neither practical nor necessary; long-term work needs stability, not frame rate.

**A field of view stretched too wide.** Fitting an entire slope section into one view increases the physical size represented by each pixel, and spatial resolution falls below what a localisation band requires. Partitioned layouts, or stitching with global control-point calibration, hold up better.

**Camera mounted on the loading frame.** When the camera sits on the same rigid base as the frame, small deformations of the frame enter the measurement and look like specimen movement. The support should be decoupled from the loading system, or frame displacement removed during processing.

**Contours read without the reference frame.** Contour maps are persuasive, but the reference defines what the deformation is measured from. Comparing batches that used different references produces trends that may not exist. Reference state, colour range and units should be annotated on every figure.

Choosing the right configuration is only the first step. With the same hardware and settings, a sequence still cannot be compared across batches if station, reference frame, colour scale and naming conventions drift. That belongs to data governance, and it is the subject of the next article.

## 6. FAQ

**1. Can a static system be used for a shaking-table test?**

It can record images, but not necessarily the part of the response that matters. The question is whether the dominant excitation period is sampled and whether the camera is synchronised with the table. When the response concentrates in a few cycles, stepwise capture tends to miss peaks, and a dynamic family is the better fit.

**2. Is a higher frame rate always better for high-speed work?**

No. Frame rate, resolution, exposure time and storage bandwidth constrain one another, so raising frame rate usually costs resolution or record duration. Configuration should be derived backwards from event duration and the smallest feature that must be resolved.

**3. Why is a fixed station emphasised so strongly for long-term observation?**

Changing the station changes the optical axis, the field of view and the reference state, adding a systematic difference that cannot be separated afterwards. A fixed position, fixed angle and fixed reference are the preconditions for a comparable sequence.

**4. Should point sensors and imaging always be deployed together?**

It depends on the question. For absolute values and time histories, point sensors are more direct; for spatial distribution and crack paths, imaging is. When both are used, their cross-checking value usually exceeds the value of either alone.

**5. How does displacement resolution change as the field of view widens?**

Displacement resolution follows the field of view and the imaging conditions. Widening the view from a few metres to tens of metres increases the physical area covered by one pixel; speckle grain size, calibration residuals, illumination and vibration then stack on top, and the smallest resolvable displacement shifts accordingly. In practice the field and camera configuration are back-calculated from the target resolution, and the disturbance factors recorded during measurement feed the error assessment.

</details>
