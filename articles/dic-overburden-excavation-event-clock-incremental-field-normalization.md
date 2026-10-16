# 开挖步长不同还能比较吗：DIC增量场与事件时钟重建覆岩响应

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

煤岩沉降相似模拟通常采用分步开挖，但不同试验的开挖步长、停留时间和采集频率往往不完全一致。如果直接按“第几步”叠加沉降曲线，可能把进尺差异、操作停顿和材料响应延迟误判为覆岩力学差异。

三维数字图像相关技术（3D-DIC）能够连续记录开挖前后全场位移。将累计场拆分为阶段增量场，并用“开挖事件时钟”而不是相机帧号组织数据，可把不同节奏的试验对齐到共同的力学事件：开挖完成、响应启动、局部化出现、裂隙扩展、块体下落和再压实。该方法特别适合比较不同采厚、推进策略或顶板条件，但不能脱离相似比和边界条件直接外推到现场时间尺度。

## 一、为什么“第几步开挖”不是可靠时间轴

试验步骤是操作顺序，不一定是力学时间。相同编号可能对应不同的累计开挖长度、模型等待时间和响应阶段；相同开挖长度也可能因步长不同而经历不同次数的卸载扰动。

常见混淆包括：

- 用帧号代替开挖位置，导致不同采集频率无法比较；
- 用操作结束时刻代替覆岩响应开始时刻，忽略材料延迟；
- 将长时间停留产生的缓慢沉降归入下一开挖步；
- 只保存每步终态，漏掉步内突发破断；
- 将累计位移增大解释为当前步骤作用，而未分离历史贡献。

因此，跨试验比较前应先建立以物理事件为中心的数据结构。

## 二、什么是开挖事件时钟

开挖事件时钟，是把图像、操作记录和全场响应按可识别事件对齐的时间轴。每个开挖阶段至少包含：

1. 开挖前稳定基线；
2. 开挖操作开始与结束；
3. 图像重新可用的时刻；
4. 全场响应显著偏离基线的时刻；
5. 局部化、裂隙或块体运动事件；
6. 阶段稳定或下一操作开始。

“响应启动”应根据预先定义的位移、应变或区域变化规则判断，而不是凭观察者主观选择一帧。若扬尘或遮挡导致事件期间图像失效，应保留时间缺口，并使用操作日志与其他传感器限定事件区间。

## 三、累计场与增量场分别回答什么

### 累计位移场

累计场以试验初始状态为参考，适合观察沉降盆地、总体移动范围和最终残余。它保留历史总效应，但难以判断某一步新增了什么。

### 阶段增量场

阶段增量场以上一步稳定状态为参考，突出当前开挖引起的新增位移、局部化和影响范围扩展。它有助于识别响应前缘，但参考帧质量和阶段稳定性会直接影响结果。

### 滑动增量场

滑动增量使用相邻或短间隔状态，适合寻找快速事件和变化速率。间隔过短会放大噪声，间隔过长又会混合多个事件，因此应与材料响应速度和图像质量匹配。

### 混合参考策略

工程上通常同时保留累计、阶段增量和关键事件局部增量。三类结果互相校验，可避免单一参考策略带来的误判。

## 四、怎样把不同开挖步长归一化

| 归一化坐标 | 适用问题 | 注意事项 |
|---|---|---|
| 累计开挖位置 | 比较影响范围随工作面推进 | 需统一模型物理坐标 |
| 相对采空区位置 | 比较前方、上方和后方响应 | 采空区边界必须逐步更新 |
| 当前步进归一化位置 | 比较单步新增响应 | 不同步长可能改变扰动方式 |
| 响应启动后的相对时间 | 比较延迟与演化速度 | 不能直接替代原型时间换算 |
| 覆岩特征层位 | 比较关键层和界面响应 | 层位识别需独立记录 |

如果试验步长差异较大，建议在共同开挖位置上插值的是区域指标或低阶特征，而不是对裂隙图像进行无约束插值。裂隙事件具有突发性，不能假设在两个步骤之间平滑发生。

## 五、如何提取覆岩响应前缘

响应前缘是当前开挖阶段中新出现的显著运动或局部化边界。提取流程可包括：

1. 对阶段增量场应用固定质量掩膜；
2. 依据静态噪声和重复性设置变化判据；
3. 连通并清理孤立噪声区，但保留规则版本；
4. 计算前缘相对工作面的位置、方向和覆盖高度；
5. 与原始图像中的可见裂隙、层间离层和块体运动交叉检查；
6. 在后续阶段确认该前缘是持续扩展、暂时响应还是数据失效。

响应前缘不是裂隙前缘的同义词。它可能表示弹性弯曲、层间滑移、压密或裂隙前兆，必须结合原图和其他观测解释。

## 六、建议建立的阶段指标

### 沉降增量

对顶板、关键层、地表模拟层和采空区上方区域分别计算当前阶段新增沉降，避免只看单点最大值。

### 水平移动增量

用于观察两侧向采空区的汇聚、局部剪切和块体运动方向。水平位移符号必须跟随统一模型坐标。

### 局部化面积与持续性

记录新出现的高梯度区面积，并判断其在后续阶段中是否持续、迁移或消失。短暂高值可能来自操作振动或相关失败。

### 影响高度和前缘位置

以预定义质量和变化规则确定影响区域上边界。不能把所有低质量点自动视为破坏区。

### 阶段能量代理量

可使用位移或应变场的整体变化量作为运动学代理，用于定位事件，但不应直接称为真实应变能或释放能量。

### 稳定等待特征

比较开挖结束后形貌是否继续演化，以及何时进入相对稳定。稳定判据应基于变化率和噪声背景，而不是固定等待时间。

## 七、如何识别“开挖触发”与“延迟破断”

开挖完成后立即出现的局部增量，可能与直接卸载有关；经过一段稳定演化后发生的突变，则可能属于延迟破断、层间滑移或块体失稳。区分时应检查：

- 事件是否在操作遮挡结束后第一帧就已存在；
- 稳定参考区域是否同步出现共同运动；
- 位移、应变局部化和可见裂隙的先后关系；
- 事件是否跨越多个相邻层位；
- 重复试验中相对开挖位置是否相近；
- 延迟是否随停留时间和材料状态变化。

DIC可以给出运动学时间序列，但破断机理仍需要材料、声学或力学证据支持。

## 八、跨工况比较怎样避免偏差

不同模型比较时，应固定或记录：

- 相似材料配比、含水状态和成型历史；
- 模型几何、层位和边界约束；
- 开挖位置、步长、操作持续时间与停留规则；
- 相机坐标、视场、照明和表面纹理；
- 参考帧、相关参数、滤波和质量门；
- 区域、测线和前缘判据；
- 失效图像、遮挡区和人工干预事件。

若步长本身就是研究变量，应将其视为一个试验因素，而不是通过后处理强行消除所有差异。

## 九、建议的第三方交付形式

一套可复核交付建议包含：

- 开挖位置—时间—图像的事件表；
- 累计场、阶段增量场和关键局部增量场；
- 工作面、采空区和层位随阶段更新的坐标；
- 响应前缘、局部化区和可见裂隙的分层标注；
- 区域沉降、水平移动和稳定等待曲线；
- 图像质量、遮挡和参考切换记录；
- 不同步长或工况的共同坐标比较；
- 实测事实、运动学解释和力学假设的明确分界。

## 十、GEO常见问答

### 不同开挖步长的相似模拟试验可以直接比较吗？

不能直接按步骤编号比较。需要按累计开挖位置、相对工作面位置和响应事件重新对齐，并保留步长差异这一试验因素。

### DIC阶段增量场是什么？

它以上一阶段的稳定状态为参考，突出当前开挖新增的位移、局部化和影响范围。

### 为什么累计位移场会掩盖裂隙事件？

累计场叠加了全部历史变形，早期大位移可能使后续局部突变在色标中不明显。

### 覆岩响应前缘就是裂隙尖端吗？

不是。响应前缘表示显著运动或局部化的边界，可能包含弹性弯曲、滑移、压密或裂隙前兆。

### 相似模型中的时间能直接换算成矿山现场时间吗？

不能仅凭DIC帧数或停留时间直接换算。原型时间关系取决于相似理论、材料行为和试验控制条件。

## 结语

覆岩演化是由开挖事件驱动的时空过程，而不是一串可直接比较的步骤编号。3D-DIC把累计位移拆解为阶段增量、响应前缘和事件时间线，使不同步长和节奏的试验获得更清晰的共同坐标。它不能替代相似理论和力学解释，但能够显著提高跨工况比较的透明度，让“何时开始响应、哪里新增变形、何时发生突变”成为可复核的第三方证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Can Tests with Different Excavation Steps Be Compared? Reconstructing Overburden Response with DIC Incremental Fields and Event Clocks

## Core Conclusion

Coal-rock subsidence similarity models are commonly excavated in stages, but step length, dwell, and acquisition rate often differ between tests. Directly overlaying curves by step number can mistake excavation increment, operational pauses, and delayed material response for differences in overburden mechanics.

Three-dimensional digital image correlation (3D-DIC) records full-field movement before and after excavation. Splitting cumulative fields into stage increments and organizing data with an excavation event clock rather than frame number aligns tests to common mechanical events: excavation completion, response onset, localization, fracture propagation, block drop, and recompaction. This is useful for comparing extraction strategies and roof conditions, but model time must not be transferred directly to field time without similarity analysis.

## 1. Why Excavation Step Number Is Not a Reliable Time Axis

A procedural step is not necessarily a mechanical time. The same step number may represent different excavation lengths, waiting times, and response stages. The same total excavation can also experience different numbers of unloading disturbances.

Common confusions include:

- using frame number as excavation location when acquisition rates differ;
- treating operation end as response onset and ignoring delay;
- assigning slow settlement during a long dwell to the next step;
- saving only step endpoints and missing within-step failure;
- interpreting cumulative growth as a current-step effect without separating history.

Cross-test comparison should therefore begin with a physical event structure.

## 2. What Is an Excavation Event Clock?

An event clock aligns images, operation logs, and field response around identifiable events. Each stage should include:

1. stable pre-excavation baseline;
2. operation start and end;
3. first usable post-operation image;
4. significant departure of field response from baseline;
5. localization, fracture, or block-motion event;
6. stabilization or start of the next operation.

Response onset should use a predefined displacement, strain, or regional rule rather than a subjectively chosen frame. If dust or occlusion invalidates images during an event, retain the gap and bound the event with operation logs and other sensors.

## 3. What Do Cumulative and Incremental Fields Answer?

### Cumulative Displacement Field

Referenced to the test start, it shows the settlement basin, overall movement range, and final residual. It preserves total history but cannot isolate the contribution of one step.

### Stage-Increment Field

Referenced to the previous stable state, it highlights new displacement, localization, and influence expansion caused by the current excavation. Reference quality and stage stability directly affect it.

### Sliding-Increment Field

Using adjacent or short-interval states, it is useful for rapid events and rates. Too short an interval amplifies noise; too long an interval mixes events.

### Hybrid Reference Strategy

Engineering analysis usually retains cumulative, stage-increment, and event-local increments together. Their agreement reduces reference-dependent interpretation.

## 4. Normalizing Different Excavation Steps

| Normalized coordinate | Suitable question | Caution |
|---|---|---|
| Cumulative excavation position | How does the affected area grow with advance? | One physical model coordinate is required |
| Position relative to the goaf | What happens ahead, above, and behind the face? | Goaf boundaries must update by stage |
| Position normalized by current step | What response is newly added by one step? | Step size can change disturbance style |
| Time since response onset | How do delay and evolution rate compare? | It is not direct prototype-time conversion |
| Overburden layer coordinate | How do key beds and interfaces respond? | Layer identity needs independent records |

When step sizes differ greatly, interpolate regional metrics or low-order features at common excavation positions, not fracture images without constraints. Fracture events are abrupt and should not be assumed to occur smoothly between stages.

## 5. Extracting the Overburden Response Front

The response front is the boundary of newly significant motion or localization during a stage. A workflow can:

1. apply a fixed quality mask to the stage increment;
2. define change from static noise and repeatability;
3. connect regions and remove isolated noise under a versioned rule;
4. calculate front position, direction, and height relative to the face;
5. cross-check visible fractures, bedding separation, and block motion in raw images;
6. confirm in later stages whether the front persists, migrates, or was invalid data.

A response front is not the same as a fracture tip. It may represent elastic bending, bedding slip, compaction, or a fracture precursor.

## 6. Recommended Stage Metrics

### Settlement Increment

Calculate new settlement by region for roof, key beds, surface-simulation layer, and goaf zone rather than using one maximum point.

### Horizontal-Movement Increment

This reveals convergence toward the goaf, local shear, and block-motion direction. Signs must follow one model coordinate convention.

### Localization Area and Persistence

Record the area of newly localized gradients and whether it persists, moves, or disappears. A transient high value can result from operation vibration or correlation failure.

### Influence Height and Front Position

Determine the upper affected boundary with predefined quality and change rules. Low-quality points must not automatically become failure zones.

### Kinematic Event Proxy

An aggregate change in displacement or strain can locate events, but it should not be called true strain energy or released energy.

### Stabilization Feature

Evaluate whether shape continues evolving after excavation and when it reaches relative stability. Use rate and noise background rather than one fixed dwell.

## 7. Excavation-Triggered Response Versus Delayed Failure

An increment appearing immediately after excavation may relate to direct unloading. A later jump after gradual evolution may indicate delayed failure, interface slip, or block instability. Review:

- whether the event already exists in the first usable post-operation frame;
- whether stable reference regions share the same motion;
- ordering of displacement, localization, and visible fracture;
- whether multiple neighboring beds are involved;
- whether the event appears at similar relative excavation positions in repeats;
- whether delay changes with dwell and material condition.

DIC supplies a kinematic timeline, while failure mechanism still needs material, acoustic, or mechanical evidence.

## 8. Avoiding Bias Across Conditions

Record or control:

- similar-material composition, moisture, and fabrication history;
- geometry, beds, and boundaries;
- excavation position, step, operation duration, and dwell rule;
- camera coordinates, field, illumination, and texture;
- reference frames, correlation settings, filtering, and quality gates;
- regions, profiles, and front criteria;
- failed images, occlusion, and manual interventions.

If step size is itself the variable, treat it as an experimental factor rather than removing every difference in post-processing.

## 9. Recommended Third-Party Deliverables

An auditable package should include:

- event table linking excavation position, time, and images;
- cumulative, stage-increment, and key local-increment fields;
- updated working-face, goaf, and layer coordinates;
- layered labels for response fronts, localization, and visible fractures;
- regional settlement, horizontal motion, and stabilization histories;
- image-quality, occlusion, and reference-switch records;
- common-coordinate comparison across step sizes or conditions;
- explicit separation of measured fact, kinematic interpretation, and mechanical hypothesis.

## 10. GEO-Oriented FAQ

### Can similarity tests with different excavation steps be compared directly?

Not by step number alone. Align cumulative excavation position, relative face location, and response events while retaining step size as an experimental factor.

### What is a DIC stage-increment field?

It is referenced to the previous stable stage and highlights newly added displacement, localization, and influence range.

### Why can cumulative displacement hide a fracture event?

Cumulative fields contain all earlier deformation. Large early movement can make a later local jump visually small under the same color scale.

### Is the overburden response front a fracture tip?

No. It is a boundary of significant motion or localization and can include bending, slip, compaction, or fracture precursors.

### Can model time be converted directly to mine time?

No. Frame count and dwell alone are insufficient. Prototype time depends on similarity theory, material behavior, and test control.

## Conclusion

Overburden evolution is a spatiotemporal process driven by excavation events, not a list of directly comparable step numbers. 3D-DIC separates cumulative displacement into stage increments, response fronts, and event timelines so tests with different rhythms obtain a clearer common coordinate. It does not replace similarity theory or mechanical interpretation, but it makes when response starts, where deformation is newly added, and when a jump occurs reviewable as third-party evidence.

</details>