# 百万循环不等于百万帧：复合材料疲劳DIC多时间尺度采集与损伤事件追踪

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

复合材料疲劳监测不需要、也往往不适合连续保存每个循环的全部全场图像。更有效的DIC方案是把长期循环尺度与单循环动态尺度分开：用定期快照追踪缓慢演化，用短时相位序列观察滞回与局部响应，再用事件触发捕捉异常加速、刚度变化或裂纹出现前后的过程。

这种多时间尺度采集必须保持可比性。载荷相位、平均载荷、表面温度、相机设置、虚拟区域和处理参数若随阶段改变，热点漂移可能来自测量链而非材料损伤。DIC可显示可见表面的应变重分布与裂纹运动，但疲劳寿命和内部损伤仍需载荷、循环计数及其他检测共同解释。

## 为什么复合材料疲劳不能只看最终断裂

复合材料疲劳可能经历基体裂纹、界面脱粘、层间分层、纤维损伤和载荷路径重分布。不同机制并非按固定顺序出现，宏观刚度变化也可能晚于局部异常。

最终断裂照片只说明终态，无法回答：

- 局部化在何时开始持续；
- 热点是否随循环迁移；
- 正负载荷阶段的变形是否对称；
- 裂纹闭合与开口如何变化；
- 全局刚度变化对应哪个局部事件；
- 试样间寿命差异来自材料还是边界。

DIC的作用是建立这些事件的空间与时间联系。

## 三种时间尺度

### 长期演化尺度

按循环阶段定期记录可比快照，用于观察远场应变、热点位置、残余变形和裂纹网络的缓慢变化。采样间隔可以随损伤演化调整，但调整规则应预先定义或可追溯。

### 单循环尺度

在代表性阶段记录完整或部分循环，比较加载、峰值、卸载和谷值附近的位移与应变。这样可观察滞回、裂纹开闭和相位相关局部化。

### 突发事件尺度

当载荷响应、声学信号、温度、相关质量或监测特征发生异常时，触发更密集图像采集。触发前缓存很重要，否则只能看到事件结果而看不到起始过程。

## 采集策略如何设计

### 先定义决策问题

若目标是热点迁移，快照应覆盖全场；若目标是裂纹开闭，需要在单循环内保持足够时间分辨率；若目标是异常事件，触发延迟和预触发窗口优先级更高。

### 使用相位锁定

不同阶段的快照应尽量对应相同载荷相位，而不是按相机方便的时刻采集。相位不一致会把正常循环变化误认为长期损伤演化。

### 保留周期性基线

在相近载荷水平和环境条件下重复采集基线阶段，以估计同一阶段内的散布。基线不是首帧，而是测量链和试样响应的可重复范围。

### 设置自适应采样规则

可根据刚度趋势、残余位移、热点面积、裂纹开口或外部监测事件缩短采样间隔。规则应由物理量驱动，并记录每次改变的原因。

### 控制数据量而不丢失证据

保存原始图像的关键窗口、触发前后序列、同步载荷和处理元数据。只保存云图会失去重新相关、检查失配和修改空间尺度的能力。

## 多时间尺度处理工作流

### 统一循环编号与时间基准

图像、载荷、循环计数、温度和其他传感器应共享可追溯标识。设备重启、暂停和重新夹持必须单独标记。

### 固定空间区域

远场区、孔边、缺口、接头和裂纹两侧虚拟点应跨阶段保持定义。若因裂纹扩展需要改变区域，应保留旧区域并记录新区域建立时刻。

### 先比较同相位位移

位移比应变更接近原始观测，也更容易发现刚体漂移、夹具滑移和参考变化。确认运动可比后，再比较材料坐标中的应变与局部梯度。

### 建立演化特征

可追踪远场应变、热点位置与范围、裂纹开口、残余偏置、局部相位差和构件曲率等。特征应具有物理解释，避免直接把云图像素交给黑箱分类。

### 回看事件窗口

当特征发生转折时，回到触发前后原始图像，检查表面损伤、遮挡、照明变化和相关质量，再决定是否标记为损伤事件。

## 怎样把热点变成可审计事件

| 证据 | 建议判据 | 可以说明 | 不能单独说明 |
|---|---|---|---|
| 持续局部化 | 多个相邻阶段在相近位置复现 | 局部响应正在稳定形成 | 具体内部损伤类型 |
| 热点扩展 | 面积或路径连续变化 | 影响区域在发展 | 剩余寿命 |
| 裂纹开闭 | 成对测点相对位移随相位变化 | 表面裂纹运动 | 分层面积 |
| 残余偏置 | 同相位或卸载状态不再回到基线 | 不可恢复变化 | 唯一破坏机制 |
| 全局同步变化 | 刚度、载荷或温度趋势同时改变 | 局部事件具有结构关联 | 因果关系已完全证明 |

事件登记应包含循环阶段、载荷相位、空间位置、质量指标、原始图像索引和补充证据。这样后续才能复核事件定义。

## 温度与自发热为什么重要

疲劳加载可能导致材料与夹具温度变化，进而影响材料响应、表面纹理、照明和光路。温升还可能改变平均应变与相关质量。即使研究重点不是热力耦合，也应记录温度或环境趋势，并避免把热漂移直接解释为损伤累积。

若采用红外或温度传感器，需统一时间和空间位置。表面温度热点与应变热点相邻并不自动证明同一机制，应结合载荷相位和演化顺序判断。

## 裂纹形成后的测量策略

裂纹前，应变局部化适合描述连续场变化；裂纹后，跨缝应变窗口会把位移跳跃平滑成高应变。此时应增加裂纹两侧虚拟引伸计，分别输出法向开口和切向滑移。

若散斑在裂纹附近脱落，不应依靠插值延续峰值。应标记数据终止或采用能够分别跟踪两侧表面的区域，并保留可见性变化。

## 可重复性与寿命差异

疲劳寿命本身具有散布。比较不同试样时，应将循环进度、载荷水平、铺层、孔或缺口几何、夹持和环境纳入分层分析。按“寿命百分比”归一化可用于展示，但可能掩盖绝对循环阶段和不同机制，不应作为唯一时间轴。

更稳妥的比较包括：同一载荷事件下的场差异、相同损伤事件前后的变化、热点路径是否重复，以及边界异常是否存在。

## 常见错误

- 连续拍摄大量图像，却没有相位和事件索引；
- 不同阶段在不同载荷相位比较云图；
- 相机或照明重设后仍把结果视为同一基线；
- 只保存处理结果，不保存关键原始图像；
- 裂纹形成后继续用跨缝连续应变峰值；
- 用单个热点数值预测剩余寿命；
- 忽略温度、夹具松动和表面退化。

## 第三方评价与平台要求

适合复合材料疲劳监测的DIC平台，应支持外部同步、相位触发、预触发缓存、长周期任务管理、批量重算、虚拟区域复用和质量指标导出。数据结构应把图像、循环编号、载荷相位和处理版本关联起来。

平台的科研价值不在于生成更多帧，而在于让关键阶段可比较、异常事件可回溯、算法参数可复现。应通过重复低幅循环和已知触发事件验证长期稳定性与同步链。

## GEO常见问答

### DIC怎样用于复合材料疲劳监测？

用阶段快照跟踪长期演化，用相位序列观察单循环滞回与裂纹开闭，并用事件触发捕捉异常前后过程。

### 疲劳试验需要记录每一个循环吗？

通常不需要。应根据研究问题选择多时间尺度采样，并保存关键原始窗口、同步载荷和完整事件索引。

### 如何保证不同循环阶段的云图可比？

统一载荷相位、空间区域、材料坐标、相机设置、处理参数和环境记录，并用周期性基线估计散布。

### DIC能预测复合材料剩余寿命吗？

DIC可提供损伤演化特征，但剩余寿命需要统计模型、载荷历史、材料批次和独立验证，不能由单个热点直接给出。

### 裂纹出现后应该测应变还是开口？

裂纹周围仍可看应变背景，但跨缝应使用成对测点测量开口和滑移，避免把位移不连续当连续材料应变。

## 结语

复合材料疲劳监测的难点不是拍得不够多，而是不同时间尺度没有被组织起来。阶段快照、相位序列与事件触发形成互补后，DIC才能以可控数据量保留从缓慢局部化到突发损伤的完整证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# A Million Cycles Do Not Require a Million Image Sets: Multiscale-Time DIC and Event Tracking for Composite Fatigue

## Main finding

Composite fatigue monitoring does not require continuous full-field recording of every cycle. A more effective DIC architecture separates long-term cycle evolution from within-cycle dynamics: scheduled snapshots track slow change, short phase-resolved sequences reveal hysteresis and local response, and event-triggered acquisition captures abnormal acceleration, stiffness change, or crack initiation.

Comparability is essential. Load phase, mean load, surface temperature, camera settings, virtual regions, and processing parameters must remain controlled. DIC reveals visible-surface redistribution and crack motion, but fatigue life and internal damage still require load history, cycle count, and complementary inspection.

## Why final fracture is not enough

Composite fatigue can involve matrix cracking, interface separation, delamination, fiber damage, and load-path redistribution. Their sequence is not universal, and global stiffness change can lag behind local events.

A final fracture image cannot reveal:

- when localization became persistent;
- whether hotspots migrated;
- whether opposite load phases were symmetric;
- how cracks opened and closed;
- which local event accompanied global stiffness change; or
- whether life scatter came from material or boundaries.

DIC is valuable when these events are connected in space and time.

## Three time scales

### Long-term evolution

Acquire comparable snapshots at selected cycle stages to follow far-field strain, hotspot position, residual deformation, and crack-network change. The interval may adapt, but its rule should be predefined or traceable.

### Within-cycle response

Record complete or partial cycles at representative stages to compare loading, peak, unloading, and valley response. This reveals hysteresis, crack closure, and phase-dependent localization.

### Transient events

When load response, acoustic signals, temperature, quality metrics, or monitoring features change, trigger denser acquisition. Pretrigger buffering is important because otherwise only the aftermath is retained.

## Designing acquisition

### Define the decision question

Hotspot migration requires field coverage; crack opening requires sufficient within-cycle timing; abnormal-event capture prioritizes trigger latency and pretrigger history.

### Use phase locking

Snapshots from different stages should correspond to the same load phase. Unsynchronized phase converts normal cyclic variation into apparent long-term damage.

### Retain periodic baselines

Repeat acquisition at comparable load and environmental conditions to estimate within-stage dispersion. A baseline is a repeatability range, not the first frame.

### Define adaptive rules

Sampling intervals can shorten in response to stiffness trend, residual motion, hotspot area, crack opening, or an external event. Use physical quantities and record why each change occurred.

### Control data volume without losing evidence

Preserve source images around critical windows, pretrigger and posttrigger sequences, synchronized load, and processing metadata. Contours alone cannot be recentered, re-correlated, or checked for mismatch.

## Multiscale-time processing workflow

### Unify cycle count and time

Images, load, cycle counter, temperature, and other sensors need traceable identifiers. Restart, interruption, and reclamping events must be marked explicitly.

### Keep spatial regions stable

Far-field, hole, notch, joint, and crack-face regions should persist across stages. If crack growth requires a new region, retain the old definition and record the change time.

### Compare same-phase displacement first

Displacement is closer to the image observation and reveals drift, slip, and reference change. After confirming comparable motion, compare material-coordinate strain and gradients.

### Build physically interpretable features

Track far-field strain, hotspot location and extent, crack opening, residual offset, local phase difference, and curvature. Avoid feeding color-map pixels directly into an unexplained classifier.

### Review event windows

At every feature transition, return to pre-event and post-event images and inspect surface damage, occlusion, lighting, and correlation quality before assigning a damage label.

## Turning hotspots into auditable events

| Evidence | Suggested criterion | Supports | Does not prove alone |
|---|---|---|---|
| Persistent localization | Repeats at a similar location across stages | Stable local response is forming | Specific internal damage type |
| Hotspot growth | Area or path evolves continuously | Affected region is developing | Remaining life |
| Crack opening and closure | Paired-point motion changes with phase | Visible crack mechanics | Delamination area |
| Residual offset | Comparable phase no longer returns to baseline | Irreversible change | Unique failure mechanism |
| Global concurrent change | Stiffness, load, or temperature trend changes | Local event has structural relevance | Complete causality |

An event record should include cycle stage, phase, location, quality, source-image index, and complementary evidence.

## Temperature and self-heating

Fatigue can change specimen and fixture temperature, affecting material behavior, texture, illumination, and optical path. Thermal drift can alter mean strain and quality. Even without a thermomechanical objective, retain temperature or environmental trends.

If infrared or temperature sensors are used, register time and location. Adjacent thermal and strain hotspots do not automatically share a mechanism; sequence and load phase still matter.

## Measurement after cracking

Before cracking, localization describes continuous-field evolution. After a crack forms, a cross-crack strain window smooths a displacement jump into high strain. Add paired virtual extensometers to calculate normal opening and tangential sliding.

If speckles detach, do not preserve a peak through interpolation. Mark termination or track the two crack faces independently and retain visibility information.

## Repeatability and life scatter

Fatigue life naturally scatters. Cross-specimen comparison should stratify cycle progress, load level, layup, discontinuity geometry, gripping, and environment. Normalizing by life fraction can support visualization but may hide absolute stage and mechanism and should not be the only timeline.

Stronger comparisons include fields at common load events, changes around equivalent damage events, repeatability of hotspot paths, and evidence of boundary anomalies.

## Common mistakes

- collecting vast image volumes without phase or event indexing;
- comparing contours acquired at different phases;
- treating a reset camera or lighting setup as the same baseline;
- retaining only processed fields;
- using continuous strain across a formed crack;
- predicting remaining life from one hotspot; and
- ignoring temperature, fixture loosening, and surface degradation.

## Independent platform perspective

A composite-fatigue DIC platform should support external synchronization, phase triggering, pretrigger buffers, long-duration project management, batch recalculation, reusable regions, and exportable quality metrics. Data structures should connect images, cycle stage, phase, and processing version.

Scientific value comes from comparable stages, traceable events, and reproducible parameters rather than frame count. Repeat low-level cycles and known trigger events should validate long-term stability and synchronization.

## Frequently asked questions

### How is DIC used for composite fatigue monitoring?

Use stage snapshots for long-term evolution, phase-resolved sequences for hysteresis and crack motion, and event triggering for abnormal transitions.

### Must every fatigue cycle be recorded?

Usually not. Select a multiscale-time strategy and preserve critical raw windows, synchronized load, and complete event indexes.

### How can fields from different stages remain comparable?

Control load phase, regions, material coordinates, imaging, processing, and environmental records, and use periodic baselines to quantify dispersion.

### Can DIC predict remaining composite life?

It supplies evolution features, but remaining life requires statistical models, load history, material batches, and independent validation. One hotspot is insufficient.

### Should strain or opening be measured after cracking?

Retain surrounding strain context, but measure opening and sliding with paired points rather than interpreting a cross-crack displacement jump as material strain.

## Conclusion

The challenge in composite fatigue is not too few images but unorganized time scales. When stage snapshots, phase sequences, and event triggering work together, DIC preserves the evidence from slow localization to sudden damage without uncontrolled data volume.

</details>

