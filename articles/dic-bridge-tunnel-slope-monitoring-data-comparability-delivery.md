# 从一次测量到可比较的长期序列：桥隧边坡DIC监测的数据治理与交付

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 同一条曲线在两次测量中走向不同，问题常常不在结构，而在测量条件。站位、参考帧、色标、标定复核与环境记录，决定了单次结果能否拼成可比较的序列。本文从两次测量对不上的现象入手，梳理可比性四要素、数据治理规范与预警判读边界，并给出可验收的交付清单。

> **关键词：** XTDIC三维全场测量；数字图像相关技术；桥隧边坡监测；数据可比性；元数据；质量标记；长期序列

## 目录

- [一、问题：同一构件两次测量为何对不上](#一问题同一构件两次测量为何对不上)
- [二、可比性四要素](#二可比性四要素)
- [三、数据治理规范](#三数据治理规范)
- [四、预警与判读边界](#四预警与判读边界)
- [五、交付清单](#五交付清单)
- [六、常见问题](#六常见问题)

## 一、问题：同一构件两次测量为何对不上

同一个桥墩、同一段隧道衬砌、同一级边坡，两次测量给出的位移曲线走向不同，未必是结构真的变了。更常见的原因是两次的测量条件不一样：站位挪了两米，光轴偏了十几度，参考帧换了一张，色标范围被自动拉伸，或者一次在阴影里、一次在午后强光下。这些差异进入结果后都表现为“变形”，但它们在物理上并不存在。

单次报告里看不出这个问题。一次测量内部是自洽的：同一台设备、同一批参数、同一个参考，云图和曲线彼此对得上。问题出在把两次结果并排放进一张图的时候——横轴是时间，纵轴是位移，中间隔着的其实是两套测量条件。

更麻烦的是，这种不可比通常不会报错。软件不会提示“本次参考帧与上次不同”，也不会提示“站位变了”。数据看起来完整、平滑、有物理意义，直到有人拿它做趋势判断或阈值比较，才发现曲线在接缝处跳了一下。长周期监测和重复观测的价值全靠序列的可比性支撑，这一层断了，后面的分析都是在不稳定的基础上做加法。

## 二、可比性四要素

**站位与光轴。** 位置、距离、俯仰角、镜头焦距，任何一项变化都会改变视场与投影关系。哪怕同一副三脚架，挪十厘米，边缘区域的应变就可能对不上。工程上应把站位写成可复现的描述，例如相对某个固定构件的距离与角度，而不是“在坡顶偏左”。

**参考帧与坐标。** 参考帧决定“相对于何时”，坐标系决定数值怎么读。跨批次比较要么共用同一参考帧，要么明确记录每次的参考及其与基准的关系。中途换参考又不留记录，是最难排查的一类问题。

**色标与量纲。** 同一序列应使用统一色标上下限，并标明单位。自动拉伸看着舒服，但颜色和量值脱钩，读者无法判断红色到底代表多少。

**标定复核与环境记录。** 标定不是一次性的动作。长周期观测要安排复核节点，把温度、光照、风、遮挡记录下来，作为解释异常的旁证。缺少这些，异常出现时只能猜。

| 要素 | 具体做法 | 缺失后的表现 |
| --- | --- | --- |
| 站位与光轴 | 记录位置、距离、角度、焦距，形成可复现描述 | 同一部位两次结果边缘区域对不上 |
| 参考帧与坐标 | 固定参考编号，记录与基准的换算关系 | 曲线在批次接缝处跳变，趋势失真 |
| 色标与量纲 | 统一上下限，标注 mm 或 με | 颜色相同但量值不同，图看着像突变 |
| 标定与环境 | 定期复核，记录温度、光照、风、遮挡 | 异常无法归因，只能凭经验解释 |

## 三、数据治理规范

**命名与目录。** 建议固定结构：项目、对象、部位、批次、日期、工况，字段之间用统一分隔符。避免“最终版”“改2”“新建文件夹”这类命名，它们在半年后会变成无法追溯的谜题。

**元数据字段。** 每个批次配一张元数据表，字段不多但要齐全。操作者写角色而非人名，既满足追溯，也避免把个人身份写进数据文件。

| 字段 | 说明 | 记录方式示例 |
| --- | --- | --- |
| 日期与时间 | 采集起止时刻 | 2026-05-12 09:40 至 11:05 |
| 站位编号 | 与站位记录表对应 | ST-03 |
| 视场与距离 | 覆盖范围、相机到目标距离 | 约 3.2 m × 2.1 m，距离 6 m |
| 参考帧 | 参考图编号与选取时刻 | R-01，加载前 |
| 标定信息 | 标定日期、标定板规格、复核结果 | 每季度复核一次 |
| 环境 | 温度、光照、风、遮挡情况 | 阴，18 ℃，微风 |
| 操作者角色 | 记录、采集、处理分工 | 现场记录员 A |
| 处理参数 | 子区、步长、平滑、掩膜 | 随结果文件一并保存 |

**质量标记。** 遮挡、失配、空洞、过曝，四类问题应逐帧或逐区域标注，而不是删除原始数据。原始图像是不可再生的资产，可用性判断可以变，原始数据不应被覆盖。标注之后，云图上哪些区域可信、哪些只是插值填出来的，读者能一眼看出差别。

**异常留痕与版本管理。** 谁在什么时候改了哪一步、为什么改，要能查到。数据分三层：原始、处理、交付。处理参数随结果保存，否则半年后重算不出同一张图。同一批数据被不同人处理过，应保留各自版本，而不是互相覆盖。

## 四、预警与判读边界

降雨边坡模型试验可以说明长期序列该怎么读。土质边坡物理模型采用人工喷淋模拟汛期雨水入渗，应变在坡顶至坡中区域持续累积，逐步发育成弧形临界滑移面，全过程从微变形一直记录到整体滑坡。它的价值在于用全域应变异常捕捉滑坡前兆，而不是等到滑面出现才反应。

读这类序列，重点在对比：雨前与雨后的应变增量分布是否改变，累积区是否从零散斑点连成带状，带的走向是否稳定，位移与应变的变化率是否同步加快。单看某一帧云图，很难判断这些。

需要说清楚的是，这是模型试验，不是现场预警案例。模型与现场的尺度、边界条件、材料、降雨强度和观测面都不同，模型里得到的阈值不能直接搬到现场使用。现场阈值的来源必须写明：来自规范、来自反演、还是来自同类工况的统计。单次试验或单一模型的结论，只能作为参考区间。

阈值设定本身也有讲究：应与具体工况绑定，采用多指标组合，例如位移、应变、裂纹长度与变化率同时看，并留出安全裕度。任何一个指标单独越线都不足以判定，多个指标同向变化才具备讨论价值。

## 五、交付清单

数据治理做到位，交付才有可验收的内容。下面这份清单可以直接用于项目约定。

| 交付项 | 内容 | 验收判据 |
| --- | --- | --- |
| 原始数据 | 图像序列、标定文件、同步记录 | 帧数完整，无缺帧，标定文件与批次对应 |
| 处理结果 | 位移与应变场、测点时序曲线、云图、视频 | 参考帧与处理参数可追溯，坐标与量纲明确 |
| 元数据表 | 批次、站位、视场、环境、角色分工 | 字段齐全，与站位记录表一致 |
| 质量报告 | 遮挡时段、失配率、空洞分布、过曝区域 | 空洞与低可信区在结果中可见，未被插值掩盖 |
| 误差评价 | 干扰因素清单与误差量级估计 | 说明适用条件与不确定度来源 |
| 判读说明 | 哪些结论有数据支撑，哪些属于推断 | 事实与推断分开表述 |
| 版本记录 | 处理版本、变更内容、变更原因 | 任一批次可回溯到原始数据 |

把这七项凑齐，一套数据才算交得出去。前面几篇讨论的都是怎么把现象测出来：位移场、应变场、裂纹路径、滑移面的形成过程。到了这里，问题换了一层：测得全、跟得住之外，还要读得懂、交得出。前者靠设备和方案，后者靠规范和习惯。两者都做到，一次测量才可能变成一段能被别人接手的序列。

## 六、常见问题

**1. 两次测量差多少才算结构真的变了？**

先看这次测量的不确定度有多大，再谈差值是否有意义。差值落在误差评价给出的范围内，只能说明没有观察到变化，不能反过来证明结构没动。差值明显超出范围时，还要排除站位、参考帧和环境的差异。

**2. 现场条件不允许固定站位怎么办？**

可以用固定标志物或全局控制点建立两次观测之间的转换关系，把结果统一到同一坐标下。前提是转换关系被记录下来，并在报告中说明其精度。悄悄换站位再直接拼曲线，是最不可取的做法。

**3. 每次出图都用自动色标行不行？**

单张展示可以，序列比较不行。自动色标会让同一颜色在不同帧代表不同量值，看起来像突变。比较时应固定上下限，并在图例中标明单位和范围。

**4. 模型试验得到的阈值能直接用于现场预警吗？**

不建议。模型与现场在尺度、边界、材料和降雨条件上差异明显，阈值需要结合现场监测数据、规范要求和同类工况统计重新确定，模型结果适合作为参考区间和机理依据。

**5. 只交付云图和曲线，不交元数据可以吗？**

短期内看得懂，长期会失效。没有站位、参考帧、处理参数和环境记录，半年后没人能判断两张图能不能比较，数据只能当图片用，无法作为序列的一部分。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From a Single Measurement to a Comparable Long-Term Series: Data Governance and Delivery for DIC Monitoring of Bridges, Tunnels and Slopes

> **Abstract:** When two measurements of the same member disagree, the cause is often the measurement conditions rather than the structure. Station, reference frame, colour scale, calibration checks and environmental records decide whether individual results can be joined into a comparable series. This article starts from that mismatch, sets out four elements of comparability, describes governance rules and the limits of warning thresholds, and closes with a delivery checklist that can be accepted item by item.

> **Keywords:** XTDIC 3D full-field measurement; digital image correlation; bridge, tunnel and slope monitoring; data comparability; metadata; quality flags; long-term series

## Contents

- [1. The problem: why two measurements of one member disagree](#1-the-problem-why-two-measurements-of-one-member-disagree)
- [2. Four elements of comparability](#2-four-elements-of-comparability)
- [3. Rules for data governance](#3-rules-for-data-governance)
- [4. Warning thresholds and the limits of interpretation](#4-warning-thresholds-and-the-limits-of-interpretation)
- [5. A delivery checklist](#5-a-delivery-checklist)
- [6. FAQ](#6-faq)

## 1. The problem: why two measurements of one member disagree

Two displacement curves recorded on the same pier, the same tunnel lining or the same slope bench may diverge without any change in the structure. More often the measurement conditions differed: the station moved two metres, the optical axis tilted a few degrees, the reference frame was replaced, the colour scale stretched automatically, or one campaign ran in shade and the other under afternoon sun. All of these enter the result as "deformation", yet none of them exists physically.

A single report cannot reveal this. Within one campaign the data are self-consistent: same hardware, same settings, same reference, contours and curves agree with each other. The trouble appears when two campaigns are placed side by side on one plot, with time on the horizontal axis and displacement on the vertical, and two different sets of conditions in between.

Worse, the incomparability rarely raises an error. Software does not announce that the reference frame differs from last time, nor that the station moved. The data look complete, smooth and physically plausible, until someone uses them for a trend judgement or a threshold comparison and notices a step at the seam. Long-term monitoring and repeated campaigns rest entirely on the comparability of the series; once that layer fails, every later analysis adds to an unstable base.

## 2. Four elements of comparability

**Station and optical axis.** Position, distance, tilt and focal length all change the field of view and the projection. Moving the same tripod ten centimetres can shift strain in the outer parts of the image. The station should be described in reproducible terms, such as distance and angle relative to a fixed structural element, rather than "on the crest, slightly left".

**Reference frame and coordinate system.** The reference defines what deformation is measured from; the coordinate system defines how the numbers are read. Cross-campaign comparison should either share one reference or record each campaign's reference and its relation to the baseline. Changing the reference without a note is the hardest fault to trace later.

**Colour scale and units.** One series should use fixed colour limits with units stated. Automatic stretching is comfortable to look at but detaches colour from magnitude, leaving readers unable to tell what red means.

**Calibration checks and environmental records.** Calibration is not a one-off action. Long-term observation needs scheduled re-checks, and temperature, lighting, wind and obstruction should be recorded as context for interpreting anomalies. Without them, an anomaly can only be guessed at.

| Element | Practical measure | Symptom when missing |
| --- | --- | --- |
| Station and optical axis | Record position, distance, angle, focal length as a reproducible description | Outer regions disagree between two campaigns on one member |
| Reference frame and coordinates | Fix the reference identifier, record conversion to the baseline | Curves step at campaign seams and trends distort |
| Colour scale and units | Fixed limits, units in mm or microstrain | Same colour, different magnitude; the plot looks like a jump |
| Calibration and environment | Periodic re-checks, records of temperature, light, wind, obstruction | Anomalies cannot be attributed and are explained by intuition |

## 3. Rules for data governance

**Naming and folders.** A fixed structure helps: project, object, location, campaign, date, condition, with a consistent separator. Avoid names like "final", "rev2" or "new folder", which become untraceable within months.

**Metadata fields.** Each campaign needs one metadata table. The fields are few but should be complete, and the operator is recorded by role rather than by name, which supports traceability without writing personal identity into data files.

| Field | Purpose | Example entry |
| --- | --- | --- |
| Date and time | Start and end of acquisition | 12 May 2026, 09:40 to 11:05 |
| Station ID | Links to the station record | ST-03 |
| Field of view and distance | Coverage and camera-to-target distance | about 3.2 m by 2.1 m, 6 m away |
| Reference frame | Reference image ID and selection time | R-01, before loading |
| Calibration | Date, target specification, check result | quarterly re-check |
| Environment | Temperature, light, wind, obstruction | overcast, 18 °C, light breeze |
| Operator role | Who recorded, acquired, processed | site recorder A |
| Processing settings | Subset, step, smoothing, mask | saved with the result file |

**Quality flags.** Occlusion, failed matching, gaps and overexposure should be flagged frame by frame or region by region rather than removed. Original images are the only non-renewable asset; usability judgements may change, but the raw data should not be overwritten. With flags in place, readers can see which areas of a contour map are supported and which are filled by interpolation.

**Change logs and versioning.** Who changed which step, when, and why should be traceable. Data fall into three layers: raw, processed and delivered. Processing settings travel with the results, otherwise the same figure cannot be reproduced six months later. Where several people processed the same data, their versions should be kept side by side rather than overwritten.

## 4. Warning thresholds and the limits of interpretation

A rainfall slope model test shows how a long series should be read. A soil slope physical model was sprinkled to simulate wet-season infiltration; strain accumulated continuously from crest to midslope and developed into an arc-shaped critical slip surface, with the whole process recorded from first micro-deformation to overall failure. Its value lies in catching precursors from full-field strain anomalies rather than waiting for the slip surface to appear.

Reading such a series depends on comparison: whether the strain increment pattern differs before and after rainfall, whether scattered patches join into a band, whether the band orientation stays stable, and whether displacement and strain rates accelerate together. A single frame rarely supports these judgements.

It should be stated plainly that this is a model test, not a field warning case. Scale, boundary conditions, materials, rainfall intensity and the observed surface all differ from site conditions, and thresholds obtained in a model cannot be transferred directly. The source of a field threshold must be declared: a code requirement, a back-analysis, or statistics from similar conditions. A single test or a single model provides a reference range at most.

Threshold design has its own discipline. It should be tied to a specific condition, combine several indicators such as displacement, strain, crack length and rate of change, and keep a safety margin. One indicator crossing a line is rarely sufficient; several moving in the same direction are what merits discussion.

## 5. A delivery checklist

Governance only pays off when delivery can be checked item by item. The list below can be used directly in a project agreement.

| Deliverable | Content | Acceptance criterion |
| --- | --- | --- |
| Raw data | Image sequences, calibration files, synchronisation records | Complete frame count, no gaps, calibration matching the campaign |
| Processed results | Displacement and strain fields, time histories at points, contour maps, video | Reference and settings traceable, coordinates and units explicit |
| Metadata table | Campaign, station, field of view, environment, roles | Fields complete and consistent with the station record |
| Quality report | Occlusion periods, matching failure rate, gap distribution, overexposed areas | Gaps and low-confidence zones visible, not hidden by interpolation |
| Error assessment | List of disturbance factors and estimated error magnitude | Applicable conditions and uncertainty sources stated |
| Interpretation note | Which conclusions rest on data, which are inference | Fact and inference presented separately |
| Version record | Processing version, changes, reasons | Any campaign traceable back to raw data |

With these seven items in place, a dataset is deliverable. The earlier articles dealt with capturing the phenomenon: displacement fields, strain fields, crack paths, the formation of a slip surface. Here the question shifts. Measuring completely and tracking continuously is one half; reading sensibly and handing over cleanly is the other. The first half depends on hardware and planning, the second on convention and habit. With both, a single measurement becomes a series someone else can pick up.

## 6. FAQ

**1. How large a difference between two measurements means the structure has changed?**

Start with the uncertainty of the measurement, then ask whether the difference means anything. A difference inside the assessed error range only shows that no change was observed; it does not prove the structure stayed still. A difference clearly outside that range still needs station, reference and environmental effects excluded.

**2. What if site conditions do not allow a fixed station?**

Fixed targets or global control points can establish a transformation between two campaigns and bring results into one coordinate system. The transformation must be recorded and its accuracy stated. Moving the station quietly and joining the curves afterwards is the worst option.

**3. Can automatic colour scaling be used for every figure?**

For a single display, yes. For comparing a series, no. Automatic scaling makes one colour mean different magnitudes in different frames and creates apparent jumps. Fix the limits and state units and range in the legend.

**4. Can thresholds from a model test be used directly for field warning?**

Not advisable. Scale, boundaries, materials and rainfall differ substantially between model and site. Thresholds should be re-established from field monitoring data, code requirements and statistics from similar conditions, with model results serving as a reference range and mechanistic basis.

**5. Is it acceptable to deliver only contours and curves, without metadata?**

It reads fine at first and fails later. Without station, reference frame, processing settings and environmental records, nobody can tell six months on whether two figures are comparable, and the data degrade into pictures rather than part of a series.

</details>
