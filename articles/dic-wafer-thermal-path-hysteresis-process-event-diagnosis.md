# 同一温度为何晶圆弯得不同：DIC追踪热滞后、形貌翻转与不可逆残余

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 摘要

在晶圆热弯曲测试中，“同一温度对应同一形貌”并不是必然成立的前提。升温、保温、降温和再次循环时，即便设备显示的温度相同，晶圆的实际温度场、层间应力释放程度、支撑接触状态和材料历史也可能不同。因此，只记录几个温度点的最大翘曲量，容易漏掉热滞后、形貌翻转、局部突变和冷却后的不可逆残余。

三维数字图像相关技术（3D-DIC）能够连续记录晶圆表面的三维位移与形貌变化，并将时间、温度路径和全场空间特征放在同一条证据链中。它的关键价值不是给出一个更醒目的峰值，而是回答：形貌在何时开始变化、变化从哪里出现、升降温路径是否重合、异常事件能否复现，以及回到初始环境后是否仍存在残余变形。

## 一、先给结论：温度相同，不代表热状态相同

热台、炉腔或环境传感器给出的温度，通常只是系统中的一个观测量。晶圆真正经历的状态还取决于：

- 温度正在上升、保持还是下降；
- 晶圆中心、边缘和支撑区是否已经达到热平衡；
- 薄膜、衬底、金属层和封装材料的热响应是否同步；
- 接触、摩擦、吸附或夹持边界是否发生变化；
- 前一阶段是否已经引发黏弹松弛、塑性变形、界面滑移或损伤。

所以，晶圆热弯曲应被视为一个与路径有关的动态过程，而不是一张“温度—翘曲量”静态对照表。对于工艺验证而言，升温支路、保温阶段、降温支路以及冷却后的残余状态都应单独识别。

## 二、为何同一温度点会出现不同形貌

### 1. 晶圆内部存在热滞后

环境先变化，晶圆再响应。薄晶圆、厚膜层、局部金属化区域或不对称叠层的热时间常数并不一致。设备显示温度相同，并不意味着晶圆各处温度分布相同。若只依据设定值配对形貌，可能把尚未稳定的过渡态误认为平衡态。

### 2. 材料行为具有历史依赖性

聚合物层、黏结层、钝化层或复合介质可能发生时间相关松弛。部分材料在升温与降温时表现不同，局部应力释放后也未必完全回到原路径。DIC观测到的滞回可能包含材料效应，但不能仅凭一条位移曲线就指定具体机理。

### 3. 曲率方向可能发生翻转

当不同层的热膨胀竞争关系随温度变化时，晶圆可能由凹转凸，或由一种鞍形模式切换到另一种模式。此时，单一“最大高度差”会丢失曲率符号和空间方向信息，甚至在翻转附近给出看似较小、实际却处于模式转换中的结果。

### 4. 边界条件会随热循环改变

支撑点微滑移、真空吸附变化、接触区域迁移或热盘平整度漂移，都可能改变测得形貌。若异常总是跟随设备坐标而不是晶圆坐标，它更可能来自边界或光路，而非晶圆本体。

### 5. 初始状态并不总能复现

装样方向、初始翘曲、表面纹理、静置时间和前序热历史都会影响基线。因此，“同批晶圆”不能自动等同于“同一初始状态”。可比性需要由记录和重复试验建立。

## 三、DIC测试应怎样标记热路径

一个可审计的数据点不应只有温度和翘曲量，还应至少关联以下状态标签：

| 状态标签 | 作用 | 缺失后的风险 |
|---|---|---|
| 时间戳与同步基准 | 对齐图像、温度和设备事件 | 把事件先后关系判断错误 |
| 实际测温位置 | 区分环境温度与晶圆状态 | 将温差误判为材料滞回 |
| 路径方向 | 标识升温、保温或降温 | 同温度数据被错误合并 |
| 阶段与循环序号 | 区分首次响应和重复响应 | 看不到训练效应或累积残余 |
| 支撑与吸附状态 | 解释边界变化 | 把接触变化归因于材料 |
| 图像质量状态 | 排查热流、反光和失相关 | 把光学伪差当成形貌事件 |

如果条件允许，温度应尽量在与晶圆状态相关的位置获得，并与图像采集使用同一时间轴。设备设定值可以保留，但不宜替代实际状态量。

## 四、连续全场测试流程

### 步骤一：建立可回查的初始基线

记录晶圆方向、有效测量区域、支撑方式、参考平面、表面纹理和初始三维形貌。初始基线应在系统稳定后获取，并保存双相机原始图像，而不只是彩色云图。

### 步骤二：做空载与边界检查

在正式测量前，可通过稳定参考件、空载热循环或边界对照检查热光路漂移、支撑热变形和相机相对运动。该步骤用于建立测试系统自身的背景响应。

### 步骤三：同步采集温度与三维形貌

采集频率应覆盖预期变化速度，同时避免因过度追求帧数而牺牲曝光、景深和相关质量。对于缓慢热过程，连续、稳定、可同步往往比孤立的高频片段更重要。

### 步骤四：统一坐标、基准和有效口径

升温与降温数据必须使用相同的坐标定义、去刚体规则、参考面和有效区域。若每个时刻重新选择“最好看的”区域或独立拟合基准，真实的路径差异可能被人为压平。

### 步骤五：同时提取全局与局部特征

建议至少保留：

- 全场面外位移与三维形貌；
- Bow、Warp或项目约定的全局翘曲指标；
- 主曲率及其方向；
- 中心、边缘、缺口附近和工艺敏感区的局部变化；
- 相邻时刻的形貌差分与变化速率；
- 有效点覆盖率、相关残差和异常区域掩膜。

### 步骤六：冷却后复测并安排重复循环

回到初始环境后，应等待系统与样品达到可比状态，再用相同基准复测。重复循环用于判断现象是一次性调整、逐步累积还是稳定可复现。

## 五、四类响应怎样区分

| 响应类型 | 全场表现 | 需要的证据 | 可支持的谨慎结论 |
|---|---|---|---|
| 可逆热弯曲 | 升降温路径大致回合，冷却后接近基线 | 多阶段连续形貌、冷却复测 | 该边界与循环条件下响应以可逆成分为主 |
| 热滞回 | 同温度下升降温形貌不同 | 同步温度、路径标签、重复循环 | 存在路径相关响应，机理需其他证据确认 |
| 形貌翻转 | 曲率符号或主方向发生变化 | 有符号曲率、全场模式、事件前后原图 | 测试中出现稳定的形貌模式转换 |
| 不可逆残余 | 冷却并稳定后仍偏离初始形貌 | 同一基准下的前后对比与重复装样 | 该流程后存在残余几何变化 |

这四类响应可能同时出现。例如，整体翘曲大部分可逆，但某个局部区域在一次热事件后留下残余；也可能全局幅值相近，而主曲率方向已经改变。

## 六、怎样识别“工艺事件”而不过度解释

全场时间序列通常比终点图片更容易发现事件。可从以下特征交叉判断：

1. **时间一致性**：形貌变化是否与温度变化、保温开始或设备动作同步；
2. **空间连续性**：变化是从局部扩展，还是整幅图同时漂移；
3. **曲率变化**：主曲率大小、符号或方向是否发生稳定转换；
4. **形貌相似度**：事件前后是否属于不同空间模式；
5. **残余性**：冷却和稳定后变化是否仍保留；
6. **可复现性**：重复循环或重复样品是否出现相似事件。

DIC可以定位异常发生的时刻和区域，但“界面滑移”“材料相变”或“薄膜开裂”等机理性结论仍需显微观察、材料表征、电学测试或其他独立证据支持。第三方报告应把观测事实、计算结果和机理推断分开书写。

## 七、伪差排查：先证明不是系统在变化

### 热光路扰动

热空气折射率变化可能让整幅图像产生缓慢漂移或局部波动。稳定参考区、空载测试、合理光路和热流隔离有助于识别这一问题。

### 镜面反射与图像饱和

晶圆表面高反射会随角度和温度改变亮斑。应检查原始图像、灰度直方图、双视角一致性和有效点覆盖，而不能只看平滑后的三维云图。

### 支撑滑移或吸附变化

若突变从接触区开始，或异常位置固定在设备坐标中，应优先检查支撑、吸附和摩擦状态。改变装样方向或支撑布局，是区分样品特征与设备特征的有效对照。

### 时间轴未对齐

温度记录与图像记录的延迟会人为制造滞回。同步触发、统一时钟或事后校准必须在解释材料行为之前完成。

### 相关失效被平滑掩盖

热反光、纹理退化或局部遮挡可能使相关失效。若软件用插值填补缺失区域，云图仍可能“完整”，但不再代表可靠测量。质量掩膜应与结果同时输出。

## 八、从热路径数据到工艺决策

完整的DIC热路径数据可用于比较不同叠层、膜系、退火流程、支撑方案或升降温策略。比较时，应保持基准、有效口径、路径定义和质量门槛一致，并关注以下问题：

- 哪种方案降低了稳定阶段的全局翘曲；
- 哪种方案减少了局部曲率集中；
- 哪个阶段出现形貌翻转或速率突变；
- 降温后是否留下可重复的残余形貌；
- 首次循环与后续循环是否趋于一致；
- 结果对装样、支撑和光学条件是否稳健。

这种比较方式比单纯排列峰值更接近制造与可靠性问题，因为它保留了“何时变化、怎样变化、是否恢复”的过程信息。

## 九、建议的交付清单

一份可复核的晶圆热弯曲报告，建议包含：

- 样品结构、方向、前序历史与表面处理说明；
- 温控、测温、支撑和光学布置示意；
- 坐标系、参考面、有效口径与刚体去除规则；
- 升温、保温、降温和冷却复测的时间轴；
- 关键时刻的三维形貌、位移、曲率及局部路径；
- 升降温同温度状态的配对比较；
- 事件检测依据、图像质量指标与排除伪差过程；
- 重复循环或重复样品的一致性说明；
- 明确区分观测、计算、推断和待验证事项。

## 十、常见问题

### 只测最高温和室温前后是否足够？

通常不足以识别热滞回、形貌翻转和中途事件。终点可以用于快速筛查，但工艺诊断更需要连续或高密度的路径数据。

### 同温度下升降温形貌不同，就能证明材料发生相变吗？

不能。温度不同步、热梯度、边界变化、黏弹松弛和光学漂移都可能造成路径差异。机理判断需要独立证据。

### 翘曲量恢复了，是否说明完全可逆？

不一定。全局幅值恢复时，局部曲率、主方向或残余应变分布仍可能改变，因此要比较完整空间形貌。

### DIC最适合在这一问题中回答什么？

它最适合回答形貌变化发生的时间、位置、方向和空间模式，并为热路径比较提供连续全场证据。材料机理仍需结合其他测试确认。

## 结语

晶圆热“弯”不是一个只由温度决定的静态结果，而是材料、结构、边界与时间共同作用的路径响应。把升温、保温、降温和冷却后的形貌放进同一坐标系，才能真正区分可逆弯曲、热滞回、模式翻转与不可逆残余。3D-DIC的价值正在于把这些过程从几个离散峰值扩展为可追溯的全场证据，使晶圆工艺比较和可靠性判断建立在更完整的事实基础上。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Why Does a Wafer Bend Differently at the Same Temperature? DIC Tracking of Thermal Lag, Shape Reversal, and Irreversible Residual

## Abstract

In wafer thermal-bending tests, the same displayed temperature does not necessarily correspond to the same shape. During heating, dwell, cooling, and repeated cycling, the actual wafer temperature field, degree of stress relaxation, support contact, and material history may differ even when the instrument reports an identical temperature. A test based only on a few temperature checkpoints and a peak warpage value can therefore miss thermal hysteresis, shape reversal, local events, and irreversible residual deformation after cooling.

Three-dimensional digital image correlation (3D-DIC) continuously records surface displacement and shape while placing time, thermal path, and spatial features on one evidence chain. Its main value is not a more dramatic peak. It is the ability to determine when a change begins, where it starts, whether heating and cooling paths coincide, whether an event repeats, and whether a residual shape remains after the initial environment is restored.

## 1. Direct Answer: Equal Temperature Does Not Mean Equal Thermal State

A chamber, stage, or environmental sensor measures only one part of the system. The state actually experienced by the wafer also depends on:

- whether temperature is rising, dwelling, or falling;
- whether the center, edge, and support regions have reached thermal equilibrium;
- whether the film, substrate, metallization, and package materials respond at the same rate;
- whether contact, friction, vacuum, or clamping boundaries have changed;
- whether an earlier stage has already caused relaxation, plasticity, interface slip, or damage.

Wafer thermal bending should therefore be treated as a path-dependent process rather than a static temperature-to-warpage lookup table. The heating branch, dwell period, cooling branch, and post-cooling residual state should be identified separately.

## 2. Why Can the Same Temperature Produce Different Shapes?

### 2.1 Thermal Lag Inside the Wafer System

The environment changes first and the wafer responds afterward. Thin substrates, thick films, local metallization, and asymmetric stacks can have different thermal time constants. An equal instrument reading does not prove an equal temperature distribution across the wafer. Pairing shapes by setpoint alone may compare a transient state with an equilibrium state.

### 2.2 History-Dependent Material Behavior

Polymer layers, adhesives, passivation, and composite dielectrics may relax over time. Some materials follow different paths during heating and cooling, and a released local stress may not fully return to its earlier state. Hysteresis observed by DIC may include a material contribution, but one displacement curve alone cannot identify a specific mechanism.

### 2.3 Curvature Can Reverse Direction

As the competition among layer expansions changes, a wafer may switch from concave to convex or from one saddle-like mode to another. A single maximum height range loses curvature sign and spatial direction. Near reversal, it may even report a modest value while the wafer is actually changing mode.

### 2.4 Boundaries Can Change During a Thermal Cycle

Small support slips, changes in vacuum contact, migration of contact areas, or thermal-stage drift can modify the measured shape. If an anomaly follows the equipment coordinates rather than the wafer coordinates, it is more likely to originate from the boundary or optical path than from the wafer itself.

### 2.5 The Initial State Is Not Automatically Repeatable

Loading orientation, initial bow, surface texture, settling time, and prior thermal history all affect the baseline. Wafers from the same batch are not automatically in the same initial state. Comparability must be established through records and repeats.

## 3. How Should a DIC Test Label the Thermal Path?

An auditable data point needs more than temperature and warpage. It should be linked to the following state labels:

| State label | Purpose | Risk when omitted |
|---|---|---|
| Timestamp and synchronization reference | Align images, temperature, and equipment events | Incorrect event ordering |
| Actual sensing location | Separate environment reading from wafer state | Thermal difference mistaken for material hysteresis |
| Path direction | Identify heating, dwell, or cooling | Data at equal temperature incorrectly merged |
| Stage and cycle index | Separate first response from repeats | Training or accumulated residual goes unseen |
| Support and vacuum state | Explain boundary changes | Contact change attributed to material behavior |
| Image-quality state | Screen heat flow, glare, and decorrelation | Optical artifact treated as a shape event |

Where practical, temperature should be measured at a location relevant to the wafer state and placed on the same time base as image acquisition. The equipment setpoint can be retained, but it should not replace a state measurement.

## 4. Continuous Full-Field Test Workflow

### Step 1: Establish a Traceable Initial Baseline

Record wafer orientation, valid measurement area, support method, reference plane, surface texture, and initial 3D shape. Acquire the baseline after the system has stabilized, and preserve the raw stereo images rather than only colored contour plots.

### Step 2: Check the Empty System and Boundaries

Before the formal test, use a stable reference, an unloaded thermal cycle, or a boundary control to assess thermal optical drift, support deformation, and relative camera movement. This establishes the background response of the measurement chain.

### Step 3: Synchronize Temperature and 3D Shape Acquisition

The acquisition rate should resolve the expected change without sacrificing exposure, depth of field, or correlation quality. For a slow thermal process, stable continuous synchronization is often more valuable than an isolated burst at very high rate.

### Step 4: Keep Coordinates, Datum, and Valid Aperture Fixed

Heating and cooling data must use the same coordinate definition, rigid-body removal rule, reference surface, and valid area. Re-selecting a visually convenient region or independently fitting the datum at every instant can artificially flatten a real path difference.

### Step 5: Extract Global and Local Features Together

Recommended outputs include:

- full-field out-of-plane displacement and 3D shape;
- bow, warp, or another project-defined global metric;
- principal curvatures and their directions;
- local changes near the center, edge, notch, and process-sensitive regions;
- shape difference and rate of change between adjacent states;
- valid coverage, correlation residual, and anomaly masks.

### Step 6: Recheck After Cooling and Repeat the Cycle

After returning to the initial environment, allow the system and specimen to reach a comparable state and repeat the measurement with the same datum. Repeated cycles help distinguish one-time seating, progressive accumulation, and stable repeatable behavior.

## 5. Distinguishing Four Response Types

| Response type | Full-field signature | Evidence required | Defensible conclusion |
|---|---|---|---|
| Reversible thermal bending | Heating and cooling paths approximately close; cooled state approaches baseline | Continuous multi-stage shape and cooled recheck | Reversible response dominates under the tested boundary and cycle |
| Thermal hysteresis | Heating and cooling shapes differ at equal temperature | Synchronized temperature, path labels, and repeated cycles | A path-dependent response exists; mechanism needs other evidence |
| Shape reversal | Curvature sign or principal direction changes | Signed curvature, full-field modes, and raw images around the event | A repeatable shape-mode transition occurred during the test |
| Irreversible residual | Shape remains offset after cooling and stabilization | Before-and-after comparison under one datum and repeated mounting | A residual geometric change remains after the tested process |

These responses can coexist. Most global warpage may be reversible while a local region retains residual deformation. Conversely, the global amplitude may look similar even though the principal curvature direction has changed.

## 6. Detecting a Process Event Without Over-Interpreting It

A full-field time history is often more informative than an endpoint image. Event detection can combine:

1. **Temporal consistency:** Does the shape change align with a temperature change, dwell start, or equipment action?
2. **Spatial continuity:** Does the change propagate from a local region, or does the entire image drift together?
3. **Curvature behavior:** Does principal curvature magnitude, sign, or direction undergo a stable change?
4. **Shape similarity:** Do the states before and after the event belong to different spatial modes?
5. **Residual behavior:** Does the change remain after cooling and stabilization?
6. **Repeatability:** Does a similar event appear in repeated cycles or specimens?

DIC can locate when and where an event occurs. Mechanistic labels such as interface slip, phase transition, or film cracking still require microscopy, material characterization, electrical testing, or other independent evidence. A third-party report should separate observations, calculations, interpretations, and unverified hypotheses.

## 7. Artifact Screening: First Prove That the System Did Not Change

### Thermal Optical Disturbance

Changes in the refractive index of heated air can cause slow image drift or local fluctuations. A stable reference region, unloaded test, controlled optical path, and heat-flow isolation help identify this effect.

### Specular Reflection and Saturation

A reflective wafer can develop moving highlights as angle and temperature change. Review raw images, gray-level distributions, stereo consistency, and valid coverage rather than relying only on a smoothed 3D contour.

### Support Slip or Vacuum Change

If a jump starts near contact or remains fixed in equipment coordinates, inspect support, vacuum, and friction first. Rotating the wafer or changing the support layout provides a useful control for separating specimen features from equipment features.

### Misaligned Time Axes

A delay between temperature logging and image acquisition can manufacture apparent hysteresis. Common triggering, a shared clock, or verified post-alignment must precede any interpretation of material behavior.

### Correlation Failure Hidden by Smoothing

Thermal glare, texture degradation, or occlusion can break correlation. Interpolation may leave a visually complete contour, but the filled region is no longer reliable measurement evidence. Quality masks must accompany the reported result.

## 8. From Thermal-Path Data to Process Decisions

Complete DIC path data can compare stack designs, film systems, annealing processes, support configurations, or heating and cooling strategies. The datum, valid aperture, path definition, and quality threshold should remain consistent. Useful questions include:

- Which option reduces stable-stage global warpage?
- Which option reduces local curvature concentration?
- At what stage does a shape reversal or rate change occur?
- Does a repeatable residual shape remain after cooling?
- Do the first and later cycles converge?
- Is the result robust to mounting, support, and optical conditions?

This approach is more relevant to manufacturing and reliability than ranking peaks alone because it preserves when, how, and whether the shape recovers.

## 9. Recommended Deliverables

An auditable wafer thermal-bending report should include:

- specimen stack, orientation, prior history, and surface preparation;
- thermal control, sensing, support, and optical setup;
- coordinate system, datum, valid aperture, and rigid-body removal rule;
- timelines for heating, dwell, cooling, and post-cooling recheck;
- 3D shape, displacement, curvature, and local paths at key states;
- paired comparisons at equal temperature on heating and cooling;
- event-detection evidence, image-quality metrics, and artifact exclusions;
- repeatability across cycles or specimens;
- explicit separation of observation, calculation, inference, and pending validation.

## 10. Frequently Asked Questions

### Is it enough to measure only the highest temperature and before-versus-after room condition?

Usually not for identifying hysteresis, shape reversal, or intermediate events. Endpoints are useful for screening, while process diagnosis needs continuous or sufficiently dense path data.

### Does a heating-cooling difference at equal temperature prove a material phase transition?

No. Temperature mismatch, gradients, boundary changes, relaxation, and optical drift can all create a path difference. A mechanistic conclusion requires independent evidence.

### If the warpage value recovers, is the response fully reversible?

Not necessarily. Local curvature, principal direction, or residual strain distribution may still change even when one global amplitude returns. Compare the full spatial shape.

### What is DIC best suited to answer in this problem?

It is particularly effective for identifying the time, location, direction, and spatial mode of shape change and for providing continuous full-field evidence across a thermal path. Material mechanisms still require corroborating tests.

## Conclusion

Wafer thermal bending is not a static result controlled by temperature alone. It is a path response produced by material, structure, boundary, and time. Placing heating, dwell, cooling, and post-cooling shapes in one coordinate system is essential for separating reversible bending, thermal hysteresis, mode reversal, and irreversible residual. The value of 3D-DIC is its ability to turn a few isolated peak values into a traceable full-field history, giving process comparison and reliability assessment a more complete factual basis.

</details>