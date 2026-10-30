# 0~150℃晶圆热翘曲测试系统怎么搭：从窗口到温度节点的配置逻辑

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 晶圆热翘曲测试系统看着就是“相机加高低温箱”，真搭起来，成败往往败在两个不起眼的环节：观察窗和温度节点。窗口决定你能不能隔着玻璃测准，温度节点决定这条曲线有没有物理意义。本文按选型与搭建顺序讲一套可落地的配置逻辑：先定需求、再拆系统七块、重点讲窗口与温控的取舍、标定怎么安排、样品怎么放、采集怎么同步，最后一页验收清单可以直接拿去核对。

> **关键词：** 晶圆翘曲测试；高低温试验箱；观察窗；温度节点；三维DIC；系统配置；标定

## 目录

- [一、先把三个需求定死](#一先把三个需求定死)
- [二、系统拆成七块](#二系统拆成七块)
- [三、观察窗：整套方案的分水岭](#三观察窗整套方案的分水岭)
- [四、温度曲线怎么设计](#四温度曲线怎么设计)
- [五、标定安排：冷态标、热态复核](#五标定安排冷态标热态复核)
- [六、样品放置与表面处理](#六样品放置与表面处理)
- [七、采集与同步](#七采集与同步)
- [八、配置清单与验收核对表](#八配置清单与验收核对表)
- [九、常见问题](#九常见问题)

## 一、先把三个需求定死

配置清单东拼西凑，通常是因为需求没定死就急着买设备。

**第一，测什么。** 只要一个翘曲标量，与要一张随温度演化的形貌序列，是完全两套配置。前者对视场与分辨率要求低，后者要求全温域连续、帧号与温度绑定。

**第二，温区到哪。** 0~150℃ 与 -40~300℃ 是两种系统。温区越宽，镜头、窗口、散斑、支架的选择余地越窄。用宽温区设备做窄温区任务，精度未必更高，成本一定更高。

**第三，要什么分辨率。** 待测量是几十到几百微米，系统分辨率至少要低一个量级；若还要反演 CTE，位移分辨率得进到亚微米，因为应变是位移对空间的梯度，误差会被放大。

| 需求维度 | 低配问法 | 高配问法 | 配置差异 |
| --- | --- | --- | --- |
| 输出 | 翘曲多少微米 | 形貌随温度怎么变、哪里最差 | 单点 vs 全场 |
| 温区 | 到 150℃ 够用 | 要覆盖回流峰值与循环 | 单箱 vs 双箱/分段 |
| 分辨率 | 看得见变形 | 要反演 CTE、对标仿真 | 毫米级 vs 亚微米级 |
| 节拍 | 一周几片 | 每天多片、多工况 | 手动 vs 半自动上下料 |

## 二、系统拆成七块

一套完整的热翘曲测试系统可拆成七块，每块都有职责和常见的坑。

| 模块 | 职责 | 常见坑 |
| --- | --- | --- |
| 成像单元（双目相机） | 采集左右图像对 | 分辨率与帧率选反，热场景不需要高帧率 |
| 光学镜头 | 成像与视场匹配 | 工作距离不足，塞不进窗口 |
| 照明 | 提供均匀对比度 | 直射反光，镜面晶圆过曝 |
| 相机支架 | 保持双目相对位姿稳定 | 支架热胀，视场漂移 |
| 高低温试验箱 | 提供温度载荷 | 腔内气流直吹样品，引起抖动 |
| 观察窗 | 隔热与透光 | 折射未校正、结露、高温软化 |
| 同步与采集 | 触发、记录、绑定温度 | 温度与帧号脱钩，CTE 反演失真 |

七块里，成像与镜头买得到，剩下五块是调出来的，延期十有八九卡在这五块。

支架直接连在试验箱外壳上，箱体升温时它跟着热胀，双目基线变化，等效于标定漂移；分离安装或隔热处理更省事。照明上，镜面晶圆正面打光会出现饱和高光，匹配精度骤降，常用掠射加漫射或用偏振片压制反射，匀光比亮度更重要。

## 三、观察窗：整套方案的分水岭

如果只能在一处花心思，就花在窗口上。

窗口的第一个问题是材料。普通浮法玻璃在 150℃ 尚可，温度再高会软化、折射率漂移；石英窗口耐温更好但成本高。选型时不要只看“耐多少度”，要看“在这个温度下光学性能还稳不稳”。

第二个问题是厚度。窗越厚，斜视时的折射偏移越大：视场边缘的视线斜着穿过窗口，等效光程被拉长，成像位置内缩，测出来的形貌在边缘被“压扁”。20 mm 厚的窗和 5 mm 厚的窗，边缘偏差不是一个量级。

第三个问题是结露与气流。低温段窗口内侧容易结露，图像直接糊掉；高温段窗内外温差大，空气对流在窗前形成折射率扰动层。前者靠吹扫或加热窗框，后者靠延长保温时间让腔内温度均匀。

| 窗口因素 | 影响 | 处理方式 |
| --- | --- | --- |
| 材质与耐温 | 高温软化、折射率漂移 | 按实际峰值温度选，留余量 |
| 厚度 | 斜视折射偏移 | 尽量薄，或纳入折射校准模型 |
| 镀膜 | 增透与反射控制 | 按波段选增透膜，减少鬼影 |
| 结露 | 低温段图像模糊 | 窗框加热、干燥气吹扫 |
| 内腔气流 | 图像抖动、噪声上升 | 加导流板、等温后再采集 |

不校正折射的后果很隐蔽：位移场光滑合理，只是整体偏了一点。判断办法很直接——同一片样品，关窗测一次、开箱测一次（在安全温区内），差值就是折射的贡献量级。

## 四、温度曲线怎么设计

温度曲线不是“从 0 升到 150”这么一句话，它决定了数据能不能用来做机理分析。

**节点密度。** 每 10℃ 一个节点、0~150℃ 共 16 个节点（S0~S15），这个密度既能看出曲率变化的拐点，又不至于让单个工况的等待时间堆成几天。

**保温时长。** 每个节点必须保温到样品温度稳定，而不是腔内空气温度到位。样品与空气之间有热滞后，1 mm 厚的硅片虽薄，叠层结构的热容仍不小。做法是看贴在样品附近的热电偶读数，连续若干分钟波动在设定范围内再采集。

**升降温速率。** 太快会让样品内部产生温度梯度，测出的形貌混着瞬时热应力。热翘曲关心准静态响应，速率通常控制在每分钟几度。

**往复还是单向。** 只做升温看到的是加热过程中的形貌；升温再加降温才能看到迟滞——同一温度下升降温形貌不重合，说明存在塑性或粘弹性。是否加降温段取决于要不要讨论残余变形。

| 参数 | 典型取值 | 设定依据 |
| --- | --- | --- |
| 节点间隔 | 10℃ | 兼顾拐点识别与工时 |
| 节点数 | 16（S0~S15） | 覆盖 0~150℃ 全区间 |
| 单节点保温 | 至样品温度稳定 | 消除热滞后 |
| 升降温速率 | 每分钟数度 | 避免内部温度梯度 |
| 采集时机 | 保温末段 | 准静态、气流最稳 |

## 五、标定安排：冷态标、热态复核

标定在热环境里有个绕不开的矛盾：标定件放不进高温腔，或放进去也难保精度。

常规做法是冷态标定加温态复核。冷态在室温下用标准标定板完成内参与外参标定；温态复核用一块已知尺寸的耐温标定件，在目标温度下拍一组，比较测量间距与设计间距。差值小说明光路在该温度下仍可信，差值大就要把温度纳入修正。

| 标定环节 | 时机 | 目的 | 判据 |
| --- | --- | --- | --- |
| 冷态内参 | 装调后 | 建立成像模型 | 重投影误差小 |
| 冷态外参 | 装调后 | 建立双目基线 | 多位置一致 |
| 温态复核 | 每个温区首次 | 验证光路稳定性 | 已知间距偏差在允许范围 |
| 参考面零点 | 每片样品 | 建立零位 | 初始形貌可复现 |

还有一个容易漏的动作：每换一片样品都要重新建立参考面。不同批次初始形貌本就不一样，沿用上一片零点等于把初始差异算进热变形。

## 六、样品放置与表面处理

放置方式会直接改变测出来的形貌。

三点支撑、环形支撑、整面平放，同一片晶圆能测出三个不同的翘曲值——支撑约束改变了自由变形的边界条件。环形卡盘吸附就模拟环形支撑，自由放置则用三点轻支撑。

表面处理的关键是散斑全程稳定：低温段防脆裂，高温段防流淌。太厚会形成一层“壳”，约束表面变形，位移偏小；太薄在高温下容易失效。做法是薄而致密，正式测试前先空跑一次，确认全程无脱落。

| 放置方式 | 边界条件 | 适用场景 |
| --- | --- | --- |
| 三点轻支撑 | 近自由，约束最小 | 材料本征行为研究 |
| 环形支撑 | 周向约束 | 模拟卡盘吸附工况 |
| 整面平放 | 摩擦约束 | 模拟实际放置状态 |
| 悬空夹持 | 边缘固定 | 特殊装夹工况 |

## 七、采集与同步

采集环节的核心只有一件事：让每一帧图像都能对应到一个确定的温度。

同步有三层含义。一是触发同步，温度记录仪与相机由同一信号源触发，或至少共用时间戳；二是节点对齐，在每个保温段的末段采集一组帧；三是命名规范，文件名里带工况号、温度、帧序，后期处理不靠记忆。

| 同步层级 | 实现方式 | 缺失后果 |
| --- | --- | --- |
| 触发同步 | 共用触发源 | 温度与图像错位 |
| 节点对齐 | 保温段末段采集 | 数据混入瞬态形貌 |
| 命名规范 | 工况-温度-帧序 | 后期无法追溯 |
| 元数据记录 | 速率、保温、环境 | 复现困难 |

## 八、配置清单与验收核对表

| 核对项 | 要点 | 通过标准 |
| --- | --- | --- |
| 视场覆盖 | 晶圆全貌在双目公共视场内 | 边缘不裁切 |
| 分辨率匹配 | 单像素对应尺寸低于待测量一个量级 | 亚微米级位移可分辨 |
| 窗口折射 | 有校准或开窗对照 | 边缘偏差可解释 |
| 温控稳定 | 样品温度波动受控 | 保温末段读数平稳 |
| 散斑稳定 | 空跑全程无脱落 | 首末帧匹配良好 |
| 同步完整 | 帧-温对应唯一 | 无孤儿帧 |
| 零点可复现 | 同片重复装夹 | 初始形貌差异可控 |

## 九、常见问题

**1. 用普通工业相机加高低温箱能不能做？**

硬件层面能搭起来，难点在光学与同步。隔窗成像的折射、腔内气流、支架热漂移这三项如果不处理，测出来的数据系统性偏差可能比待测量还大。设备不是关键，光路设计才是。

**2. 为什么不直接用箱内高温镜头？**

耐高温镜头解决的是“镜头不被烤坏”，解决不了“隔着窗看”的折射问题，也解决不了样品表面散斑在高低温下的稳定性。镜头只是七块里的一块。

**3. 温度节点一定要 10℃ 一档吗？**

不必。拐点密集的区间可以加密，平缓区间可以稀疏。但如果目标是找出转折温度，均匀加密是最省心的做法，避免先入为主地跳过关键区间。

**4. 一片晶圆测完要多久？**

取决于节点数与保温时长。16 个节点、每节点保温到稳定，加上升降温时间，通常是一天量级。这也是为什么强调“按节点采集”而不是全程录像。

**5. 能不能同时测多片？**

视场允许时可以，但要注意两片之间的热耦合与遮挡，且每片都要有独立的参考面与散斑区域。多片同测的收益是效率，代价是每片的有效像素数下降。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>点击展开：English Version (Click to Expand)</b></summary>

> **Abstract:** A wafer thermal warp system looks like a camera plus a thermal chamber. In practice, two unremarkable links decide whether it works: the observation window and the temperature nodes. The window determines whether you can measure accurately through glass; the nodes determine whether the curve means anything physically. This article gives a buildable configuration logic in selection order: define requirements, break the system into seven blocks, weigh the window and thermal control trade-offs, plan calibration, place the specimen, synchronise acquisition, and finish with an acceptance checklist.

> **Keywords:** wafer warp test; thermal chamber; observation window; temperature node; 3D DIC; system configuration; calibration

## Contents

- [1. Settle Three Requirements First](#1-settle-three-requirements-first)
- [2. Seven Blocks](#2-seven-blocks)
- [3. The Observation Window Decides Everything](#3-the-observation-window-decides-everything)
- [4. Designing the Temperature Profile](#4-designing-the-temperature-profile)
- [5. Calibration: Cold Setup, Hot Verification](#5-calibration-cold-setup-hot-verification)
- [6. Specimen Placement and Surface Preparation](#6-specimen-placement-and-surface-preparation)
- [7. Acquisition and Synchronisation](#7-acquisition-and-synchronisation)
- [8. Configuration and Acceptance Checklist](#8-configuration-and-acceptance-checklist)
- [9. FAQ](#9-faq)

## 1. Settle Three Requirements First

**What is being measured.** A single warp scalar and a shape sequence versus temperature need different systems: the first tolerates a small field and low resolution, the second demands continuous coverage with frames bound to temperature.

**How far the range goes.** 0–150℃ and −40–300℃ describe two systems; the wider the range, the narrower the choices of lens, window, speckle and fixture, and wide-range equipment always costs more.

**What resolution is needed.** A measurand of tens to hundreds of micrometres needs resolution an order finer; CTE inversion needs sub-micron displacement, because strain is a spatial gradient and errors amplify.

| Dimension | Modest requirement | Demanding requirement | Configuration difference |
| --- | --- | --- | --- |
| Output | Warp in micrometres | Shape versus temperature, worst location | Point vs full field |
| Range | Up to 150℃ | Cover reflow peak and cycling | Single chamber vs segmented |
| Resolution | Deformation visible | CTE inversion, simulation correlation | Millimetre vs sub-micron |
| Throughput | A few wafers weekly | Multiple wafers and conditions daily | Manual vs semi-automatic handling |

## 2. Seven Blocks

A complete system breaks into seven blocks, each with a duty and a familiar failure mode.

| Block | Duty | Common failure |
| --- | --- | --- |
| Imaging unit (stereo cameras) | Capture left/right image pairs | Resolution and frame rate chosen backwards |
| Lenses | Match imaging to field of view | Working distance too short |
| Illumination | Provide uniform contrast | Frontal light saturates the mirror surface |
| Camera mount | Hold stereo pose stable | Mount expands, field drifts |
| Thermal chamber | Apply the temperature load | Airflow on the specimen causes shimmer |
| Observation window | Insulate while transmitting light | Uncorrected refraction, condensation, softening |
| Synchronisation and acquisition | Trigger, record, bind temperature | Temperature decoupled from frame index, CTE inversion corrupted |

Imaging and lenses are bought; the other five are tuned, and delays come from them.

Mounts matter: bolted to the shell, a mount expands with heat, the stereo baseline shifts and the effect equals calibration drift — isolate or insulate it. A mirror wafer under frontal light saturates, so grazing plus diffuse light or polarisers are used; uniformity beats brightness.

## 3. The Observation Window Decides Everything

Material comes first. Ordinary float glass is adequate at 150℃; above that it softens and its index shifts, and fused silica tolerates more heat at higher cost. The question is not "what temperature does it survive" but "how stable its optics are at that temperature".

Thickness second: edge rays cross the glass obliquely, so the optical path lengthens, image positions shift inward and the measured shape compresses at the rim. A 20 mm window and a 5 mm window differ by more than a factor.

Condensation and airflow third. In the cold segment the inner surface fogs and the image is lost; in the hot segment a convective layer with fluctuating index forms. The first needs frame heating or dry-air purge, the second longer holds to reach equilibrium.

| Window factor | Effect | Remedy |
| --- | --- | --- |
| Material rating | Softening, index shift | Select for actual peak with margin |
| Thickness | Oblique refraction offset | Keep thin, or include in the refraction model |
| Coating | Transmission and reflection control | Band-matched anti-reflection coating |
| Condensation | Blurred image in cold segment | Frame heating, dry-air purge |
| Internal airflow | Image shimmer, higher noise | Baffles, acquire after equilibrium |

Uncorrected refraction is deceptive: the field looks smooth and merely offset. Measuring the same specimen with the window closed and the chamber open in a safe range gives the difference as the refraction contribution.

## 4. Designing the Temperature Profile

**Node density.** One node per 10℃ gives 16 nodes (S0–S15) across 0–150℃: enough to reveal inflections without stretching one condition into days.

**Hold duration.** Each node must hold until the specimen, not the chamber air, is stable. A 1 mm wafer is thin, but the stack carries real heat capacity, so watch a thermocouple near the specimen and acquire once it stays within a band for several minutes.

**Ramp rate.** Too fast builds an internal gradient, so the shape carries transient thermal stress rather than isothermal shape; a few degrees per minute is typical.

**One-way or cyclic.** Heating alone shows the shape during heating; adding cooling reveals hysteresis, since non-coincident shapes at one temperature mean plasticity or viscoelasticity. A cooling leg is worth it only if residual deformation matters.

| Parameter | Typical value | Rationale |
| --- | --- | --- |
| Node spacing | 10℃ | Balances inflection detection against duration |
| Node count | 16 (S0–S15) | Covers 0–150℃ |
| Hold per node | Until specimen stable | Removes thermal lag |
| Ramp rate | A few degrees per minute | Avoids internal gradients |
| Acquisition timing | End of hold | Quasi-static, most stable airflow |

## 5. Calibration: Cold Setup, Hot Verification

Calibration in a hot chamber carries an unavoidable tension: reference artefacts do not fit, or lose accuracy if they do.

The practice is cold calibration with hot verification: intrinsics and extrinsics at room temperature on a standard target, then a temperature-tolerant artefact imaged at the target temperature, its spacing compared against nominal. A small difference means the path stays trustworthy; a large one means temperature must enter the correction model.

| Step | Timing | Purpose | Criterion |
| --- | --- | --- | --- |
| Cold intrinsics | After installation | Build the imaging model | Low reprojection error |
| Cold extrinsics | After installation | Establish stereo baseline | Consistent across positions |
| Hot verification | First run of each range | Confirm optical stability | Known spacing within allowance |
| Reference zero | Every specimen | Establish datum | Initial shape reproducible |

One step is often skipped: the reference plane must be re-established for every specimen, because batches start with different shapes and carrying over the old zero folds that difference into the thermal deformation.

## 6. Specimen Placement and Surface Preparation

Three-point support, ring support and full-surface placement give three warp values for the same wafer, because the constraint on free deformation differs. Match the process: ring chuck means ring support, free seating means light three-point support.

Speckle must stay stable throughout: no cracking when cold, no flow when hot. Too thick and the pattern forms a shell that constrains deformation and biases displacement low; too thin and it fails at temperature. Thin and dense is the rule, plus a dry run to confirm no detachment.

| Placement | Boundary condition | Suitable for |
| --- | --- | --- |
| Light three-point | Near free, minimal constraint | Intrinsic material behaviour |
| Ring support | Circumferential constraint | Chuck-held process conditions |
| Full-surface placement | Friction constraint | Actual resting state |
| Edge clamping | Fixed at the rim | Specific fixture conditions |

## 7. Acquisition and Synchronisation

Synchronisation works on three levels: trigger, sharing a source or at least a timestamp between logger and cameras; node alignment, a frame set at the end of each hold; naming, embedding condition, temperature and frame index so post-processing does not rely on memory.

| Level | Implementation | Consequence if missing |
| --- | --- | --- |
| Trigger | Shared source | Temperature and image misaligned |
| Node alignment | Acquire at end of hold | Transient shape mixed in |
| Naming | Condition-temperature-frame | Traceability lost |
| Metadata | Rate, hold, environment | Hard to reproduce |

## 8. Configuration and Acceptance Checklist

| Item | Key point | Pass criterion |
| --- | --- | --- |
| Field coverage | Whole wafer inside the common stereo field | No cropping at the rim |
| Resolution match | Pixel footprint an order below the measurand | Sub-micron displacement resolvable |
| Window refraction | Calibrated or cross-checked open-chamber | Edge bias explainable |
| Thermal stability | Specimen temperature controlled | Stable reading at end of hold |
| Speckle stability | Dry run without detachment | Good match between first and last frame |
| Synchronisation | One-to-one frame-temperature binding | No orphan frames |
| Zero reproducibility | Repeat mounting of the same wafer | Initial shape difference bounded |

## 9. FAQ

**1. Can an ordinary industrial camera plus a thermal chamber do the job?**

The hardware can be assembled; the difficulty is optical and synchronisation-related. Uncorrected refraction through the window, internal airflow and mount thermal drift can together produce systematic bias larger than the measurand. Equipment is not the crux; optical design is.

**2. Why not simply use a high-temperature lens inside the chamber?**

A heat-tolerant lens solves "the lens does not get damaged", not "measuring through glass" and not "speckle stability across the range". The lens is one block of seven.

**3. Must nodes be spaced at exactly 10℃?**

No. Dense spacing where inflections cluster, sparser where the response is flat. If the goal is to locate a transition temperature, uniform density is the safest choice, since it avoids skipping the key interval on an assumption.

**4. How long does one wafer take?**

It depends on node count and hold length. Sixteen nodes, each held to stability, plus ramp time, typically amounts to about a day. This is why acquisition at nodes is preferred over continuous recording.

**5. Can several wafers be measured at once?**

Yes if the field allows, but note thermal coupling and occlusion between specimens, and give each wafer its own reference plane and speckled region. The gain is throughput; the cost is fewer effective pixels per wafer.

</details>
