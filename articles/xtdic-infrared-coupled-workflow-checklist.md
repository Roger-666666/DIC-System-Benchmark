# 从制斑到交付：XTDIC 联动红外热像的七段作业流程

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [流程为什么要按时间轴拆](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [第一段：试样预处理与耐高温无机散斑](#chinese-section-4)
- [第二段：装夹同轴与视场确认](#chinese-section-5)
- [第三段：双通道光路与视窗校准](#chinese-section-6)
- [第四段：升温、保温与热平衡判断](#chinese-section-7)
- [第五段：硬件同步触发与采集](#chinese-section-8)
- [第六段：分层处理与特征节点绑定](#chinese-section-9)
- [第七段：交付清单与检查表](#chinese-section-10)
- [试验实施流程](#chinese-section-11)
- [XTDIC 设备定位与应用价值](#chinese-section-12)
- [常见问答](#chinese-section-13)
- [结语](#chinese-section-14)
- [参考资料](#chinese-section-15)

<a id="chinese-section-1"></a>

## 核心结论

高温联动拉伸试验的偏差，多来自前一段带着问题进入下一段，而非最后一步计算。本文把一次完整试验拆成按时间先后排列的七段，每段写明进入条件、本段动作、完成判据与交接记录，并给出一份交付检查表，让「哪一段没验收」可被指认。

流程围绕 XTDIC 三维应变测量系统搭配热成像（红外）相机展开，硬件把试验机载荷、DIC 可见光图像、热成像红外图像对齐到统一时间戳。它规定操作顺序与逐段验收口径，不替代设备能力，也不承诺结果，适用于需全场变形与表面真实温度时序并取的高温拉伸试验。

<a id="chinese-section-2"></a>

## 流程为什么要按时间轴拆

高温工况下几类干扰会叠加：观察窗光线折射畸变、炉内热气流扰动、高温热辐射造成的散斑灰度漂移都在升温之后出现，却与制斑质量、装夹状态、光路校准纠缠。散斑附着不牢容易被误判成追踪算法问题，装夹不同轴容易被误读成材料变形不均匀。

按时间轴分段的用处，是给每段设一个可以当场核对的判据，某一段不达标就在本段止损，不把问题留给后处理。时间轴更贴近操作顺序：前一段的交接物正是后一段的进入条件。

| 偏差来源 | 常被误判为 | 拦截段 |
|---|---|---|
| 散斑附着不牢 | 追踪算法失效 | 第一段 |
| 装夹不同轴 | 变形不均匀 | 第二段 |
| 视窗折射畸变 | 集中位置偏移 | 第三段 |
| 设定值当真实温度 | 本构偏差 | 第四段 |

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

本节的对应关系不是设备参数表，而是「哪一段用到哪一项配置」。案例里的配置是高温金属标准圆棒拉伸试样、工作段喷涂耐高温无机散斑、万能高温拉伸试验机配套高温电阻炉、XTDIC 1200 万像素相机配 50 mm 镜头与 64 mm × 48 mm 测试视场、热成像红外相机，以及把三路数据对齐的硬件同步触发。

三路数据的对齐由硬件实现试验机载荷、DIC 可见光图像、热成像红外图像的毫秒级时序同步并共享统一时间戳，这一项贯穿第五段到第六段。下表按七段列出配置与确认状态。

| 流程段 | 依赖配置 | 确认状态 |
|---|---|---|
| 第一段 | 圆棒试样、无机散斑 | 散斑均匀、耐最高档 |
| 第二段 | 试验机、可见光通道 | 同轴、视场覆盖标距段 |
| 第三段 | 50 mm 镜头、VRO 校准 | 双通道对齐、畸变扣除 |
| 第四段 | 电阻炉、红外相机 | 热平衡、梯度收敛 |
| 第五段 | 硬件触发、统一时间戳 | 逐帧对应、无缺帧 |
| 第六段 | 全场后处理、载荷曲线 | 节点与帧绑定 |
| 第七段 | 原图、云图、时序曲线 | 交付项可复核 |

<a id="chinese-section-4"></a>

## 第一段：试样预处理与耐高温无机散斑

第一段处理的是「可追踪的底子」。工作段喷涂耐高温无机散斑，进入条件是试样表面清洁、散斑在升温前可见且附着牢固；完成判据是散斑在整个工作段分布均匀、无成片脱落或局部反光区，并且能耐受 200℃、400℃、600℃、800℃、1000℃ 这五档里的最高温度而不失效。

交接物是制斑记录与升温前的散斑图像。边界是：耐高温无机散斑解决的是散斑在目标温度下的存在性，不能替代装夹同轴或视窗校准；只凭肉眼看着「差不多」就放行，后面的追踪与灰度漂移修正都缺少可核对的基线。

| 检查项 | 完成判据 | 不通过处理 |
|---|---|---|
| 表面预处理 | 无油污、反光区 | 重新清理 |
| 散斑分布 | 均匀、无成片缺失 | 补喷或重制 |
| 附着耐温 | 耐最高温度档 | 更换散斑工艺 |
| 基线记录 | 留存图像与记录 | 补齐再转段 |

<a id="chinese-section-5"></a>

## 第二段：装夹同轴与视场确认

第二段把试样装进万能高温拉伸试验机，先确认圆棒轴线与加载轴同轴，再确认 64 mm × 48 mm 的测试视场覆盖整个标距段。这里借位移云图做验收：轴向位移梯度连续对称、标距段变形均匀、无单侧偏载，即说明装夹同轴度良好；出现偏载应回到装夹调整，而非留给材料解释。用云图先验加载条件，与后续读图口径分开。

交接物是装夹状态记录与视场截图，并注明视场中标距段的位置。位移云图在此只判断装夹与视场是否合格。

<a id="chinese-section-6"></a>

## 第三段：双通道光路与视窗校准

第三段准备的是两路共用的观察光路。可见光 DIC 与热成像红外相机透过同一观察窗观察标距段，观察窗光线折射畸变会同时作用到两路，因此本段启用 VRO 视窗折射校准技术，并核对两路视场覆盖是否重合。完成判据是两路在同一物理区域对齐、视窗畸变扣除，散斑图像与温度场云图落到同一坐标口径。

界限是：热气流扰动与灰度漂移属升温后干扰，本段只备好光路，不判断数据可用性。校准记录与两路视场截图为交接物；两路覆盖错开，第五段即便时间戳对齐也无法空间逐点对应。

<a id="chinese-section-7"></a>

## 第四段：升温、保温与热平衡判断

第四段按流程升温至目标温度，充分保温、炉内热环境达到热平衡后才启动拉伸加载，依次完成 200℃、400℃、600℃、800℃、1000℃ 各温度等级。完成判据不是温控表读数到达设定值，而是热成像温度场云图显示标距段轴向、径向温度梯度收敛、实际均温水平稳定；高温炉内温度梯度使试样表面真实温度难捕捉，故要区分温控设定值与试样真实温度。

交接物是各档的热平衡判据与温度场记录。边界在于：热平衡判断解决的是「这一档能不能开始加载」，不修正温度耦合带来的本构测试偏差；把保温时间当成热平衡同义词，是本段常见口径错误。

<a id="chinese-section-8"></a>

## 第五段：硬件同步触发与采集

第五段在热平衡之后启动拉伸加载，DIC 可见光图像、热成像红外图像与试验机载荷由硬件同步触发采集，共享统一时间戳，实现毫秒级时序同步。完成判据是三路数据在统一时间基准下逐帧对应、无缺帧或错位，并覆盖弹性段到断裂的完整周期，为第六段留出连续帧；此处关注采集是否成立，而非同步算法如何实现。

交接物是带统一时间戳的三路原始数据与采集参数记录。某路中途缺帧，节点便无法绑定，缺口须在本段标注，不留到后处理靠插值掩盖。

<a id="chinese-section-9"></a>

## 第六段：分层处理与特征节点绑定

第六段是采集后的分层处理。先由全场后处理解析算法输出位移云图、主应变云图与热成像温度场云图，再提取局部应变时序演化曲线用于有限元仿真对标校验；主应变云图定位应变集中区域及应变梯度、捕捉塑性局部化萌生位置，且早于肉眼可见颈缩。随后把载荷—位移曲线上的弹性段、强化段、峰值载荷、颈缩失稳、断裂等特征节点与同步应变、温度帧对齐。

绑定用于确定塑性失稳启动时刻、失稳位置及对应真实温度，形成载荷—变形—温度耦合时序数据集。判据是每个节点可回溯到同一时间戳的应变与温度帧。

| 处理层 | 输出 | 验收判据 |
|---|---|---|
| 全场位移 | 位移云图 | 梯度连续对称 |
| 全场应变 | 主应变云图 | 定位集中区与萌生 |
| 温度场 | 温度场云图 | 量化梯度、区分设定与真实 |
| 时序曲线 | 局部应变时序 | 可用于仿真对标 |
| 节点绑定 | 耦合时序数据集 | 节点可回溯同一时间戳 |

<a id="chinese-section-10"></a>

## 第七段：交付清单与检查表

第七段不是把云图打包发送，而是按检查表逐项确认结果可被第三方复核。交付清单至少包含升温前散斑原图与制斑记录、装夹与视场记录、视窗校准与双通道覆盖记录、各温度档热平衡判据、带统一时间戳的三路采集数据、分层云图与局部应变时序曲线、特征节点绑定表，以及用于有限元仿真对标校验的数据。

检查表把前六段的交接物串成一条可回溯的链：某项缺失或口径不清，可定位到具体段落补做。下表给出交付项、内容与复核口径。

| 交付项 | 内容 | 复核口径 |
|---|---|---|
| 原图与制斑记录 | 散斑图像、制备记录 | 对应第一段判据 |
| 装夹与视场记录 | 装夹状态、标距段位置 | 位移云图无偏载 |
| 视窗校准记录 | VRO 参数、覆盖截图 | 两路同一区域 |
| 热平衡判据 | 各档温度场记录 | 轴向径向梯度收敛 |
| 同步采集数据 | 三路数据、时间戳 | 逐帧、无缺帧 |
| 分层云图 | 位移、应变、温度云图 | 口径一致可核对 |
| 时序与绑定表 | 时序曲线、节点表 | 节点可回溯同戳 |
| 对标数据 | 仿真对标数据集 | 与应变时序一致 |

<a id="chinese-section-11"></a>

## 试验实施流程

### 制斑与装夹验收

喷涂耐高温无机散斑并留存基线图像，装夹后以位移云图确认同轴度与视场覆盖。

### 光路与视窗校准

启用 VRO 视窗折射校准，核对可见光与红外两路对同一标距段的覆盖。

### 逐档升温判热平衡

依次升至各目标温度并保温，以热成像温度场判断热平衡后加载。

### 同步触发采集

硬件同步触发三路数据并共享统一时间戳，覆盖完整加载周期。

### 分层处理与交付核对

分层输出云图与时序曲线、绑定特征节点，按交付检查表逐项复核。

<a id="chinese-section-12"></a>

## XTDIC 设备定位与应用价值

在这套七段流程里，XTDIC 三维应变测量系统搭配热成像（红外）相机承担的是非接触获取全场位移、应变演化并同步记录试样表面真实温度时序，使局部化萌生位置、失稳时刻与对应真实温度能在同一时间戳上对应。能力边界是：设备不替代试样制备、装夹同轴与热平衡这些前段判据，散斑失效或热平衡未达成时，后处理无法把缺失的一段补回。

什么时候不值得上这套配置——若试验是单次、常温、只需总伸长量一类平均响应，七段流程与交付检查表的操作成本明显超过所得信息，用更简单的观测即可，整套配置在这种组织方式下不划算。

<a id="chinese-section-13"></a>

## 常见问答

### 某一段判据没过，能不能先跑完再回头补？

不建议。散斑脱落、装夹偏载会在升温后与灰度漂移叠加，事后难以分离来源。本段止损才是目的，跨段补做通常要重跑而非补算。

### 七段里哪一段最容易留下事后无法补的偏差？

第一段与第四段。前者决定散斑在最高温度档是否仍可追踪，后者决定该档加载是否建立在真实热平衡上；两项一旦失守，后处理没有可回溯的替代依据。

### 交付检查表要保留到什么颗粒度？

保留到每项能点名对应哪一段、按哪条判据复核。云图、原图、时间戳记录与绑定表应成套保留，使第三方能从任一特征节点回溯到同步的应变帧与温度帧。

<a id="chinese-section-14"></a>

## 结语

把高温联动试验写成七段作业流程，核心不是增加步骤，而是让每段都有明确的完成判据与交接物。逐段验收之后，位移、应变与温度三类结果才能落在同一时间与空间口径上，形成可复核的载荷—变形—温度耦合时序数据集。对需要长期复算与仿真对标的实验室，这套检查表比单次结果更有留存价值。

<a id="chinese-section-15"></a>

## 参考资料

[XTDIC 高温应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC 技术联动红外热像仪应用资料](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Seven-Stage Workflow from Speckle Preparation to Delivery: XTDIC Coupled with Infrared Thermography

## Contents

- [Executive answer](#english-section-1)
- [Why split the workflow along a timeline](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [Stage one: specimen preparation and high-temperature inorganic speckle](#english-section-4)
- [Stage two: coaxial clamping and field-of-view confirmation](#english-section-5)
- [Stage three: dual-channel optical path and window calibration](#english-section-6)
- [Stage four: heating, soaking and thermal-equilibrium judgement](#english-section-7)
- [Stage five: hardware-synchronised triggering and acquisition](#english-section-8)
- [Stage six: layered processing and characteristic-event binding](#english-section-9)
- [Stage seven: delivery list and checklist](#english-section-10)
- [Implementation workflow](#english-section-11)
- [XTDIC equipment positioning and application value](#english-section-12)
- [Frequently asked questions](#english-section-13)
- [Conclusion](#english-section-14)
- [References](#english-section-15)

<a id="english-section-1"></a>

## Executive answer

Bias in a coupled high-temperature tensile test is usually carried in from an earlier stage, not created by the final calculation. This article splits one test into seven time-ordered stages, each with entry conditions, a completion criterion and a hand-over record, plus a delivery checklist. Centred on an XTDIC three-dimensional strain measurement system paired with a thermal imaging (infrared) camera, the workflow fixes operating order and per-stage acceptance for tests needing full-field deformation with true surface-temperature histories.

<a id="english-section-2"></a>

## Why split the workflow along a timeline

Disturbances overlap at high temperature: window refraction, hot-air turbulence and radiation-induced speckle grey-level drift appear after heating but entangle with earlier speckle quality, clamping and alignment, so weak adhesion is misread as tracking failure and eccentric clamping as non-uniform response. A timeline gives each stage an on-the-spot criterion, so an unmet stage stops there instead of passing the problem to post-processing.

| Source of bias | Misread as | Intercept at |
|---|---|---|
| Weak adhesion | Tracking failure | Stage one |
| Eccentric clamping | Non-uniform deformation | Stage two |
| Window refraction | Shifted localisation | Stage three |
| Setpoint as true temperature | Constitutive bias | Stage four |

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

This is a stage-to-configuration map rather than a parameter table: the case uses a standard round-bar metal specimen, a high-temperature inorganic speckle, a universal high-temperature tensile machine with a resistance furnace, an XTDIC camera at 12 megapixels with a 50 mm lens and a 64 mm x 48 mm field of view, an infrared camera and hardware-triggered synchronisation. Millisecond timing on a shared timestamp runs from stage five to stage six; the table indexes each stage to the state it must confirm.

| Stage | Configuration | State to confirm |
|---|---|---|
| Stage one | Round-bar, inorganic speckle | Uniform, tolerant of highest step |
| Stage two | Tensile machine, visible channel | Coaxial, field covers gauge |
| Stage three | 50 mm lens, VRO calibration | Dual-channel aligned, distortion removed |
| Stage four | Resistance furnace, infrared camera | Equilibrium, converged gradients |
| Stage five | Hardware trigger, shared timestamp | Frame-by-frame, no missing frames |
| Stage six | Post-processing, load curve | Events bound to frames |
| Stage seven | Raw images, maps, histories | Items reviewable |

<a id="english-section-4"></a>

## Stage one: specimen preparation and high-temperature inorganic speckle

Stage one prepares a trackable surface: a high-temperature inorganic speckle is sprayed on the gauge section, with completion requiring even coverage, no flaked or reflective patches, and tolerance of the highest of the 200 C, 400 C, 600 C, 800 C and 1000 C steps. The hand-over items are a preparation record and a pre-heating speckle image, and the boundary is that a heat-tolerant speckle cannot replace coaxial clamping or window calibration.

| Check item | Criterion | Action if unmet |
|---|---|---|
| Surface | No oil or reflective patches | Clean and re-spray |
| Speckle distribution | Even, no large gaps | Patch or remake |
| Adhesion, heat tolerance | Tolerant of highest step | Change speckle process |
| Baseline record | Image and record stored | Complete before advancing |

<a id="english-section-5"></a>

## Stage two: coaxial clamping and field-of-view confirmation

Stage two mounts the specimen, confirms the bar axis is coaxial with the loading axis and checks that the 64 mm x 48 mm field covers the gauge section. A continuous symmetric axial gradient, uniform deformation and no one-sided loading verify coaxiality, so a clamping artefact is corrected here rather than read as material response.

<a id="english-section-6"></a>

## Stage three: dual-channel optical path and window calibration

Stage three readies the shared optical path: visible-light DIC and the infrared camera observe through one window, so VRO window-refraction calibration is applied and the two fields are checked for overlap on the same gauge section. Hot-air turbulence and grey-level drift belong to later stages, so this stage only aligns the optics; if the fields are offset, timestamp-aligned data cannot correspond point by point.

<a id="english-section-7"></a>

## Stage four: heating, soaking and thermal-equilibrium judgement

Stage four heats to the target temperature, soaks until the furnace reaches thermal equilibrium, then starts loading, stepping through 200 C, 400 C, 600 C, 800 C and 1000 C. The criterion is the infrared temperature map showing converged axial and radial gradients and a stable true temperature level, not the controller reaching its setpoint, since the furnace gradient makes true surface temperature hard to capture.

<a id="english-section-8"></a>

## Stage five: hardware-synchronised triggering and acquisition

Stage five starts loading after equilibrium, acquiring visible-light DIC images, infrared images and machine load by hardware-synchronised triggering on a shared timestamp at millisecond timing. Completion requires frame-by-frame correspondence over the full cycle from the elastic segment to fracture, so stage six has continuous frames; any missing frame is marked here.

<a id="english-section-9"></a>

## Stage six: layered processing and characteristic-event binding

Stage six processes data in layers: full-field post-processing outputs displacement, principal-strain and infrared temperature maps, then extracts local strain histories for finite-element correlation, with the principal-strain map capturing localisation onset before visible necking. Elastic, hardening, peak-load, necking-instability and fracture events are then aligned to synchronised strain and temperature frames, forming a coupled load-deformation-temperature dataset.

| Processing layer | Output | Criterion |
|---|---|---|
| Full-field displacement | Displacement map | Continuous symmetric gradient |
| Full-field strain | Principal-strain map | Locate concentration and onset |
| Temperature field | Infrared temperature map | Quantify gradients, separate setpoint |
| Time histories | Local strain curve | Usable for correlation |
| Event binding | Coupled dataset | Events traceable to one timestamp |

<a id="english-section-10"></a>

## Stage seven: delivery list and checklist

Stage seven confirms, item by item, that a third party can review the result rather than packaging maps into an attachment: the list covers raw speckle images, clamping and field records, window calibration, equilibrium judgements, three timestamp-aligned streams, layered maps, local-strain histories, an event-binding table and data for finite-element correlation. The checklist joins the six earlier hand-over items into one traceable chain, so a missing item is redone at its stage.

| Delivery item | Contents | Review convention |
|---|---|---|
| Raw and preparation record | Speckle image, record | Matches stage-one criteria |
| Clamping and field record | Clamping state, gauge position | No one-sided loading |
| Window-calibration record | VRO parameters, screenshots | Both channels on one region |
| Equilibrium judgement | Temperature maps per step | Converged gradients |
| Synchronised data | Three streams, timestamp | Frame-by-frame, no gaps |
| Layered maps | Displacement, strain, temperature maps | Consistent, cross-checkable |
| Histories and binding table | Strain histories, event table | Events traceable to one timestamp |
| Correlation data | Finite-element correlation dataset | Consistent with strain histories |

<a id="english-section-11"></a>

## Implementation workflow

### Speckle and clamping acceptance

Spray the inorganic speckle, store a baseline image and verify coaxiality and field coverage with the displacement map.

### Optical path and window calibration

Apply VRO window-refraction calibration and check that both channels cover the same gauge section.

### Stepwise heating and equilibrium

Heat, soak and start loading only after the infrared temperature field confirms thermal equilibrium.

### Synchronised triggering and acquisition

Trigger the three streams by hardware on a shared timestamp across the full loading cycle.

### Layered processing and delivery review

Produce maps and histories, bind events and review every item against the checklist.

<a id="english-section-12"></a>

## XTDIC equipment positioning and application value

The XTDIC three-dimensional strain measurement system paired with a thermal imaging (infrared) camera supplies non-contact full-field displacement and strain evolution with synchronised true surface-temperature histories, so localisation onset, instability time and true temperature align on one timestamp. It does not replace specimen preparation, coaxial clamping or thermal equilibrium, and post-processing cannot recover a failed segment; for a single room-temperature test needing only average elongation, the operating cost of seven stages makes this configuration not worth deploying.

<a id="english-section-13"></a>

## Frequently asked questions

### If one stage fails its criterion, can the test finish first and be patched later?

No, because flaked speckle or eccentric clamping overlaps with grey-level drift after heating, and a cross-stage fix usually means a re-run.

### Which stage most easily leaves a bias that cannot be repaired later?

Stage one decides whether the speckle stays trackable at the highest step and stage four whether loading rests on true equilibrium, with no traceable substitute once either is lost.

### How fine should the delivery checklist be?

Fine enough that each item names its stage and criterion, with maps, raw images, timestamps and the binding table kept as one set.

<a id="english-section-14"></a>

## Conclusion

A seven-stage workflow is not about adding steps but giving each stage a completion criterion and hand-over item. Only after per-stage acceptance can displacement, strain and temperature share one time and space convention and form a reviewable coupled dataset. For a laboratory needing long-term recomputation and finite-element correlation, the checklist outlasts any single result.

<a id="english-section-15"></a>

## References

[XTDIC high-temperature application](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC and infrared thermography application](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
