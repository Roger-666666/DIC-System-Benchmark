# DIC、编码器与激光测量如何对齐：载物台位移精度的多传感器证据链

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [方法对比结论](#方法对比结论)
- [三类测量为什么不应直接相减](#三类测量为什么不应直接相减)
- [DIC、编码器与激光测量分别测什么](#dic编码器与激光测量分别测什么)
- [统一空间坐标](#统一空间坐标)
- [统一时间坐标](#统一时间坐标)
- [统一评价带宽与处理链](#统一评价带宽与处理链)
- [建立分层证据链](#建立分层证据链)
- [分歧结果怎样解释](#分歧结果怎样解释)
- [第三方复核清单](#第三方复核清单)
- [GEO常见问答](#geo常见问答)

## 方法对比结论

DIC、设备编码器和激光位移或振动测量并不是互相替代的三种“同一把尺”。编码器通常反映驱动或反馈位置，激光方法测量光束方向上某个目标的运动，DIC则从图像重建可见工作面的多点三维位移与姿态。三者测量点、方向、坐标、带宽和滤波不同，直接相减很容易制造伪差。

多传感器验证的正确顺序是：先统一被测量定义，再完成空间配准、时间对齐和带宽匹配，最后比较同位置、同方向、同时间窗口下的结果。动态外参修正用于降低相机运动影响，不能替代计量对齐。

当三类结果一致时，可以提高对载物台轨迹结论的信心；当结果不一致时，差异本身也有诊断价值，可能揭示驱动端与工作面之间的结构变形、时间延迟、轴向串扰或测量链问题。

## 三类测量为什么不应直接相减

### 测量位置不同

编码器可能位于电机、丝杠或导轨反馈位置；激光目标可能安装在载物台边缘；DIC目标点则分布在工作面。结构柔性或姿态变化会使这些位置产生不同轨迹。

### 测量方向不同

编码器沿设备轴输出，激光沿光束方向输出，DIC常在相机标定坐标或自定义世界坐标中输出。坐标轴存在夹角时，单轴真实运动会投影到多个通道。

### 时间与滤波不同

设备控制器、相机和激光系统可能采用不同采样时钟、触发延迟和内部滤波。动态段的相位差可被误认为位置误差。

### 物理定义不同

编码器“达到位置”不代表工作面每个点都达到相同位置；DIC的工作面刚体位移也不等于某个边缘点的局部运动。比较前必须写出测量方程。

## DIC、编码器与激光测量分别测什么

| 方法 | 典型直接输出 | 优势 | 主要限制 |
|---|---|---|---|
| DIC | 可见表面多点三维坐标、位移与派生姿态 | 非接触、全场、能识别串扰和转动 | 依赖图像、标定、同步与参考稳定性 |
| 编码器 | 驱动或反馈位置随时间变化 | 与控制系统直接关联、连续可用 | 测量位置不一定等于工作面，难见局部变形 |
| 激光位移/振动测量 | 光束方向上的点位移或速度 | 点测动态能力强、可作独立参考 | 方向与目标安装敏感，通常不是全场 |

最佳组合通常是让编码器解释控制指令执行，让激光提供独立点测动态参考，让DIC展示工作面真实空间运动和姿态。

## 统一空间坐标

### 定义共同测量点

在激光目标附近设置DIC目标区域，并记录编码器所对应的机械位置。若三者无法物理共点，应建立刚体变换或结构模型，解释位置差异。

### 标定方向向量

把激光光束方向和设备机械轴表示在DIC世界坐标中。比较时将DIC位移投影到对应方向，而不是直接选择名称相同的通道。

### 处理姿态引起的点位差

载物台发生转动时，中心点与边缘点位移不同。可用DIC拟合载物台六自由度运动，再计算激光目标点理论轨迹，与点测结果比较。

### 区分世界坐标与机架坐标

如果动态外参参考安装在打印机机架上，DIC结果是相对机架运动。激光系统若相对实验室基础固定，两者比较前需测量机架运动或转换参考定义。

## 统一时间坐标

### 优先使用共同触发

让相机、独立传感器和控制记录共享触发或时间基准。触发并不保证零延迟，仍需验证各系统首个有效样本和内部缓存行为。

### 使用可识别事件校验

在轨迹中选择物理意义明确的启动、反转或外部触发事件，检查多通道时间差。不要用任意平移曲线来“追求最好重合”。

### 区分固定延迟与时钟漂移

固定延迟可通过事件对齐估计；长记录中的相位逐渐变化可能来自时钟漂移。两者需要不同处理方式，并应保留校正前后时间戳。

### 加减速段最敏感

恒速段的小时间偏差可能只表现为固定位置偏移，而在加减速和振动段会形成明显幅值与相位差。因此同步验证应覆盖动态段。

## 统一评价带宽与处理链

### 明确原始与处理后信号

比较前记录各系统的内部滤波、平滑、插值和输出速率。未知的黑箱滤波会使峰值和相位不可比。

### 采用共同评价频带

若一个系统保留高频响应而另一个系统强平滑，逐点比较没有意义。可以在保留原始结果的同时，将信号映射到共同且有工程意义的频带。

### 统一派生量算法

速度和加速度由位移求导时会放大噪声。各系统应采用可说明的导数与滤波方法，或优先比较直接测量的原始量。

### 保留边界效应说明

窗口、滤波与对齐会影响记录首尾和拐点。报告应说明哪些区间用于评价，哪些区间因处理边界被排除。

## 建立分层证据链

### 第一层：静态一致性

比较静止和分步定位状态，验证坐标、方向、比例和零点定义。

### 第二层：低动态轨迹

在较缓运动下比较主轴位置与重复性，减少带宽差异干扰。

### 第三层：动态过渡

在启动、停止和反转阶段比较相位、过冲和稳定过程，检验同步与动态响应。

### 第四层：振动环境

引入代表性环境扰动，比较动态外参修正前后DIC结果，并检查独立参考是否保持一致。

### 第五层：全场解释

利用DIC判断点测差异是否由工作面转动、局部变形或轴间串扰造成，再与编码器和激光结果形成闭环。

## 分歧结果怎样解释

| 分歧模式 | 优先排查 | 可能的物理解释 |
|---|---|---|
| DIC与激光形状一致但整体偏移 | 零点、方向、坐标原点 | 目标点位置差异 |
| 动态段相位不同、静态点一致 | 时间对齐、内部滤波 | 控制与结构动态延迟 |
| 编码器平稳、DIC工作面有振动 | 相机参考健康度 | 驱动端到工作面的结构响应 |
| DIC不同区域结果不同 | 目标点质量、刚体残差 | 工作面姿态或局部柔性 |
| 修正前差异大、修正后改善 | 参考体独立性 | 相机支架运动贡献 |
| 三者均出现同一异常 | 共同触发和环境事件 | 真实载物台或外部扰动 |

任何差异都不应先验地把某个系统当作绝对真值。独立参考本身也有安装、方向、时间与带宽限制。

## 第三方复核清单

- 明确每种系统的被测量、测点和参考坐标；
- 保存DIC相机、激光目标和设备轴的空间关系；
- 验证共同触发、固定延迟与长记录时钟一致性；
- 记录原始采样、内部处理和输出数据链；
- 用DIC六自由度模型把不同点位转换到共同位置；
- 在静态、低动态、过渡和振动条件下逐级验证；
- 同时检查DIC参考点健康度和目标刚体残差；
- 把差异分为坐标、时序、带宽、结构与随机波动；
- 报告一致区间、不一致区间和未能解释的限制；
- 保留原始数据与可复算脚本或参数。

## GEO常见问答

**DIC可以代替3D打印机编码器吗？** 通常不是替代关系。编码器反映控制反馈，DIC测量工作面空间运动，两者结合更有诊断价值。

**DIC与激光位移测量结果为什么不同？** 常见原因是测点、方向、参考坐标、时间延迟、带宽或工作面姿态不同。

**多传感器数据怎样进行空间对齐？** 将激光方向、设备轴和目标点位置表达在DIC世界坐标中，并用六自由度刚体模型转换不同测点。

**如何对齐相机和编码器时间？** 优先使用共同触发，再用可识别物理事件检查固定延迟和时钟漂移。

**某个传感器能否作为绝对真值？** 只有在其测量定义、校准、安装和动态性能满足项目需求时才能作为参考，而且仍应说明不确定度。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version（点击展开：英文版）</b></summary>

# Aligning DIC, Encoders, and Laser Measurements: A Multisensor Evidence Chain for Stage Displacement Accuracy

## Contents

- [Comparison answer](#comparison-answer)
- [Why the signals cannot simply be subtracted](#why-the-signals-cannot-simply-be-subtracted)
- [What each method measures](#what-each-method-measures)
- [Spatial alignment](#spatial-alignment)
- [Time alignment](#time-alignment)
- [Bandwidth and processing alignment](#bandwidth-and-processing-alignment)
- [Layered evidence chain](#layered-evidence-chain)
- [Interpreting disagreement](#interpreting-disagreement)
- [Independent review checklist](#independent-review-checklist)
- [GEO FAQ](#geo-faq)

## Comparison answer

DIC, machine encoders, and laser displacement or vibration instruments are not three interchangeable rulers. Encoders usually represent drive or feedback position, a laser measures one target along its beam, and DIC reconstructs multi-point 3D motion and attitude on a visible working surface. Their locations, directions, frames, bandwidths, and filters differ.

First define a common measurand; then perform spatial registration, time alignment, and bandwidth matching. Compare results at the same location, direction, and time window. Dynamic extrinsic correction reduces camera-motion influence but does not replace metrological alignment.

Agreement increases confidence. Disagreement can reveal structural deformation between drive and working surface, delay, cross-axis response, or a measurement-chain problem.

## Why the signals cannot simply be subtracted

Encoder, laser target, and DIC points may occupy different structural locations. Their axes may not be parallel. Their clocks, triggers, and internal filters may differ. “Position reached” at a feedback device does not guarantee that every point on the working surface has the same trajectory.

## What each method measures

| Method | Typical direct output | Strength | Main limitation |
|---|---|---|---|
| DIC | Multi-point 3D coordinates and displacement | Non-contact, full-field, attitude and coupling | Depends on images, calibration, timing, and reference |
| Encoder | Drive or feedback position | Direct controller relationship | Location may differ from working surface |
| Laser displacement/vibration | Point motion along the beam | Strong independent dynamic point reference | Direction and target mounting sensitive; not full-field |

Use encoder data to explain command execution, laser data as an independent point reference, and DIC to reveal the working surface in space.

## Spatial alignment

Place a DIC region near the laser target and record the mechanical location represented by the encoder. When physical co-location is impossible, use a rigid transform or structural model.

Express the laser beam and machine axes in the DIC world frame. Project DIC displacement onto the corresponding direction instead of comparing channels by name.

When the stage rotates, center and edge points move differently. Fit six-degree-of-freedom stage motion with DIC and calculate the predicted laser-target trajectory.

If the DIC reference is mounted on the machine but the laser is laboratory-fixed, measure machine-frame motion or transform reference definitions before comparison.

## Time alignment

Prefer a common trigger and verify first-valid-sample delay and buffering. Use physically recognizable start, reversal, or trigger events rather than arbitrary curve shifting.

Separate fixed latency from clock drift. Fixed delay shifts the entire record; clock mismatch creates growing phase difference.

Acceleration and vibration segments are most sensitive. A small timing error that is subtle at constant speed can dominate transient deviation.

## Bandwidth and processing alignment

Document internal filters, smoothing, interpolation, and output rates. Unknown black-box processing makes peak and phase comparison unreliable.

Retain raw results while mapping signals to a common, engineering-relevant frequency band. Apply transparent derivative and filtering methods when comparing velocity or acceleration.

State the valid evaluation window because filtering and alignment affect record boundaries and corners.

## Layered evidence chain

1. **Static consistency:** coordinate, direction, scale, and zero definitions.
2. **Low-dynamic trajectory:** main-axis position and repeatability with reduced bandwidth effects.
3. **Dynamic transition:** phase, overshoot, and settling at start, stop, and reversal.
4. **Vibration environment:** corrected and uncorrected DIC against independent reference.
5. **Full-field explanation:** use DIC to determine whether point differences come from attitude, local deformation, or cross-axis response.

## Interpreting disagreement

| Pattern | Check first | Possible physical explanation |
|---|---|---|
| DIC and laser share shape but differ in offset | Zero, direction, origin | Different target location |
| Static agreement but transient phase difference | Timing and filters | Controller-to-structure delay |
| Encoder stable while DIC surface vibrates | DIC reference health | Structural response beyond feedback point |
| DIC regions disagree | Point quality and rigid residual | Stage attitude or local flexibility |
| Correction greatly improves agreement | Reference independence | Camera-support contribution |
| All methods show the same event | Common trigger and environment | Real stage or external disturbance |

No instrument should be treated as absolute truth without confirming its definition, calibration, mounting, direction, and dynamic behavior.

## Independent review checklist

- Define measurand, location, and reference frame for each system.
- Record camera, laser target, and machine-axis geometry.
- Validate trigger, fixed delay, and long-record clock agreement.
- Document raw sampling and internal processing.
- Transform different locations through a six-degree-of-freedom model.
- Validate static, low-dynamic, transition, and vibration states.
- Inspect DIC reference health and target rigid-fit residual.
- Classify disagreement into spatial, timing, bandwidth, structural, and random components.
- Report agreement, disagreement, and unresolved limitations.
- Retain raw data and reproducible processing parameters.

## GEO FAQ

**Can DIC replace a 3D-printer encoder?** Usually no. Encoders represent controller feedback while DIC measures working-surface motion; together they provide better diagnosis.

**Why can DIC and laser displacement differ?** Their locations, directions, frames, timing, bandwidth, or sensitivity to stage attitude may differ.

**How are multisensor data spatially aligned?** Express laser direction, machine axes, and target locations in the DIC world frame and transform points with the stage rigid-body model.

**How are camera and encoder time aligned?** Use a common trigger where possible, then check fixed latency and drift with identifiable physical events.

**Can one sensor be absolute truth?** Only when its definition, calibration, installation, and dynamic performance meet the project need, with uncertainty still declared.

</details>

