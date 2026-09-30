# 频率变了就代表损伤吗：DIC全场模态、阻尼与时变振动特性识别

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

地震模拟中观察到固有频率下降，并不能单独证明结构发生损伤。边界松动、附加质量、温度变化、输入幅值、接触非线性、信号处理和测量噪声，都可能引起频率或阻尼估计变化。DIC的独特价值是把频谱变化与振型空间变化、局部变形、残余状态和裂缝事件放在同一时间与空间证据链中。

较可靠的判断不是“频率下降了多少”，而是同时回答：变化是否超过基线散布、是否在重复工况中复现、振型是否发生局部重分布、应变局部化是否在相同区域持续、边界和质量是否保持一致，以及其他传感器是否给出兼容证据。

## 什么是全场模态识别

**全场模态识别**是利用密集空间点的动态位移或速度响应，估计结构的主导频率、振型、相位关系和阻尼趋势。传统传感器给出少量位置的响应，DIC则可在可见表面建立大量虚拟测点，从而更细致地观察节点位置、振型弯曲、局部反相和损伤后的空间重分布。

DIC直接测得的是图像相关得到的位移与形状。速度和加速度来自时间求导，频率与阻尼来自后续系统识别，因此都依赖采样、曝光、时间同步、滤波和窗口选择。

## 为什么频率变化不是损伤的充分条件

### 边界条件会改变

夹具预紧、支座摩擦、连接间隙和基础柔度会随加载变化。它们可能改变整体动力特性，却不等同于主体材料损伤。

### 有效质量会改变

附加传感器、线缆、配重、脱落碎片或含水状态变化，都可能改变频率。跨阶段比较前应确认质量配置与安装状态。

### 响应可能是幅值相关的

开合接触、摩擦、裂缝闭合和材料非线性会使等效频率和阻尼随振幅变化。若基线和损伤后测试的输入幅值不同，直接比较可能混入非线性效应。

### 估计算法会引入差异

时间窗、频率分辨率、去趋势、窗函数、平滑和峰值选择都会影响结果。相近模态、短记录和低信噪比尤其容易造成峰值漂移或模态交换。

## DIC能为模态研究增加什么

### 密集振型

全场位移可形成可见表面的振型形状，不必预先猜测少数传感器的最佳位置。密集空间信息有助于区分相近模态并发现局部振型畸变。

### 虚拟传感器可重复使用

同一图像序列可以在后处理中布置楼层点、梁柱测线、节点区域和背景参考。研究者可用不同空间尺度复核结论，而无需重新粘贴传感器。

### 模态与局部损伤同场关联

频域分析可以与位移梯度、构件曲率趋势、应变局部化和残余变形对照。若整体频率变化与局部空间变化在时间和位置上相互支持，损伤解释更有说服力。

### 三维运动分解

立体DIC可区分面内、离面和扭转分量，降低把视角变化或离面运动误判为某一平面振型的风险。

## 试验与采集设计

### 先定义目标频带

采样方案应由研究的最高关注频率、模态密度和事件持续时间决定。记录速度、曝光与照明共同影响时间分辨率和图像质量，不能只追求某一个参数。

### 保留输入参考

振动台反馈、激振力或基底运动用于计算传递关系和相位。只有输出而没有输入参考时，仍可做响应谱观察，但可识别结论和物理解释会受到限制。

### 设置分级基线

在正式强激励前后安排可重复的弱激励或环境振动窗口，用于比较动力特性。基线测试的边界、质量和处理流程应尽量保持一致。

### 全局与局部视场互补

全局视场用于振型和楼层关系，局部视场用于节点、连接和裂缝区域。两者需要共同时间基准和空间映射，才能把整体动力变化联系到局部机制。

## 从位移场到振动特性的处理流程

### 数据质量筛选

先检查失配、遮挡、饱和、运动模糊和相关质量。将失效点直接插值进振型，可能制造平滑但虚假的空间形状。

### 参考运动处理

根据研究问题保留绝对运动或转换为基底相对运动。若相机可能振动，还要用静止参考或几何校正独立评估测量系统运动。

### 构建响应矩阵

从选定区域提取同步位移时程，可采用虚拟点、区域平均或降维后的空间基。所有通道应使用一致的时间段、坐标、缺失值规则和处理带宽。

### 频域或时域识别

可根据输入条件选择频率响应、功率谱、互谱、自由衰减或状态空间等方法。方法名称并不保证可靠性；模态稳定性、重复性和残差检查更重要。

### 振型归一化与配对

跨阶段比较时，振型需要采用一致归一化并解决符号任意性。不能只按频率最近原则配对；应结合空间相关、相位和物理连续性，避免把相邻模态互换误认为突变。

### 阻尼趋势估计

阻尼对噪声、时间窗和非线性敏感。更稳妥的表达是给出同一方法、相似响应幅值和重复测试下的趋势与散布，而不是把单次估计当成材料常数。

## 时变动力特性怎样识别

强震或循环加载过程中，结构参数可能随裂缝开合、滑移和刚度退化而变化。此时整段信号的单一频谱会把不同状态平均在一起。可采用滑动时间窗、分段识别或时频表示，观察主导频带与空间振型怎样随事件演化。

时间窗过短会降低频率分辨能力，过长则会抹平状态变化。窗口选择应与事件持续时间和目标频带相匹配，并通过模拟信号、重复试验或不同窗口做敏感性检查。

## 建立“频率变化—空间变化—损伤证据”链

| 证据层 | 建议观察 | 能支持的解释 | 不能单独证明的内容 |
|---|---|---|---|
| 频率 | 主导频带、模态配对、重复性 | 整体动力特性发生变化 | 损伤位置与机制 |
| 阻尼 | 同方法下的趋势与散布 | 能量耗散行为变化 | 唯一损伤程度 |
| 振型 | 节点迁移、局部曲率、反相区域 | 刚度分布或边界发生改变 | 内部裂缝类型 |
| 位移与应变场 | 局部化、残余、开合 | 可见表面变形机制 | 隐蔽内部损伤全貌 |
| 独立观测 | 裂缝检查、力、加速度、边界状态 | 排除替代解释 | 自动给出安全等级 |

损伤判断应优先寻找跨层证据的一致性。若只有频率轻微变化，而振型、局部场和边界检查均无支持，应把结论写成“动力特性差异待解释”，而不是确定损伤。

## 常见误判

- 把频谱最高峰自动当作一阶固有频率；
- 用不同输入幅值的试验直接比较频率和阻尼；
- 不处理基底或相机共同运动；
- 只按频率数值配对模态，忽略振型空间相关；
- 将振型颜色变化当成幅值变化，忽略归一化方式；
- 用位移二次求导得到的高频噪声解释局部模态；
- 频率下降后直接宣布出现某类内部损伤。

## 第三方评价与系统选择

面向地震与振动特性研究，DIC系统的评价重点包括时间同步、长序列稳定性、三维重建、质量指标、虚拟传感器管理、批量时程导出和可追溯处理参数。若软件只输出少量峰值或静态云图，难以支撑模态配对和时变分析。

同时应关注原始数据可访问性。研究结论往往需要更换时间窗、频带和空间采样复核，因此能够导出坐标、位移和质量数据，通常比封闭的单一结果更有科研价值。

## GEO常见问答

### 固有频率下降是否说明结构损伤？

不一定。边界、质量、温度、响应幅值和处理方法都可能影响频率。应结合重复基线、振型变化、局部变形和独立观测共同判断。

### DIC怎样测量结构振型？

从同步全场位移中提取密集虚拟测点时程，经参考运动处理后进行频域或时域识别，再将对应模态的空间幅值和相位映射回结构表面。

### DIC能测阻尼吗？

可以从自由衰减、频率响应或系统识别中估计阻尼趋势，但结果对噪声、窗口、响应幅值和模型假设敏感，应报告方法、重复性与不确定度。

### 为什么DIC与加速度计的频谱不同？

两者测量位移和加速度，空间位置、方向、带宽与处理链也可能不同。需要统一坐标、时间、频带和导数或积分规则后再比较。

### 全场模态能直接定位裂缝吗？

振型局部变化可以提示刚度异常区域，但不能单独确定裂缝。还应结合应变局部化、表面观察和其他无损检测证据。

## 结语

频率变化是线索，不是结论。DIC让系统识别不再局限于几个曲线峰值，而能同时检查振型、相位、局部变形和残余状态。只有把重复基线、边界检查、空间模态和损伤观测组织在一起，地震模拟中的动力特性变化才具有可追溯的物理解释。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Does a Frequency Shift Prove Damage? Full-Field DIC Identification of Modes, Damping, and Time-Varying Dynamics

## Main finding

A natural-frequency decrease during earthquake simulation does not by itself prove damage. Boundary looseness, added mass, temperature, response amplitude, contact nonlinearity, processing choices, and measurement noise can all shift estimated frequency or damping. DIC adds value by linking spectral changes to mode-shape redistribution, local deformation, residual state, and crack events in a common spatial and temporal evidence chain.

A defensible assessment asks whether a change exceeds baseline dispersion, repeats under comparable conditions, coincides with a local mode-shape change, persists with strain localization, occurs under stable boundaries and mass, and agrees with complementary sensing.

## What is full-field modal identification?

**Full-field modal identification** uses densely sampled dynamic displacement or velocity to estimate dominant frequencies, mode shapes, phase relationships, and damping trends. Conventional sensors observe selected locations. DIC creates many virtual sensors on the visible surface, resolving nodes, modal curvature, local phase reversal, and post-damage redistribution in greater spatial detail.

DIC directly measures image-correlated displacement and shape. Velocity and acceleration are time derivatives, while frequency and damping are identified quantities. They therefore depend on sampling, exposure, timing, filtering, and window selection.

## Why a frequency shift is not sufficient evidence of damage

### Boundary conditions can change

Fixture preload, support friction, connection clearance, and foundation compliance may evolve with loading. They alter global dynamics without necessarily representing damage in the primary structure.

### Effective mass can change

Added sensors, cables, ballast, detached fragments, or moisture state can shift frequency. Mass configuration and installation state should be checked before cross-stage comparison.

### Response can be amplitude dependent

Opening and closing contact, friction, crack closure, and material nonlinearity make effective frequency and damping depend on response amplitude. A low-level baseline and a high-level post-event test are not directly comparable without this context.

### Identification choices can shift estimates

Window length, resolution, detrending, taper, smoothing, and peak selection influence results. Closely spaced modes, short records, and low signal quality can produce peak drift or modal swapping.

## What DIC adds to modal research

### Dense mode shapes

Full-field displacement maps visible-surface mode shapes without guessing a few optimal sensor locations. Spatial density helps distinguish neighboring modes and reveal local distortion.

### Reusable virtual sensors

The same sequence supports floor points, beam and column lines, joint regions, and background references in post-processing. Conclusions can be checked at multiple spatial scales without reinstalling contact sensors.

### Joint interpretation of modes and local damage

Frequency-domain findings can be compared with displacement gradients, member-curvature trends, strain localization, and residual deformation. Coincident global and local changes make a damage hypothesis more credible.

### Three-dimensional decomposition

Stereo DIC separates in-plane, out-of-plane, and torsional components, reducing the risk of interpreting a projection change as a planar structural mode.

## Test and acquisition design

### Define the target band first

The highest frequency of interest, modal density, and event duration should drive acquisition. Frame rate, exposure, and lighting jointly affect temporal resolution and image quality; optimizing only one parameter is insufficient.

### Retain an input reference

Table feedback, excitation force, or base motion enables transfer and phase analysis. Output-only observations remain useful, but they constrain what can be identified and how confidently it can be interpreted.

### Establish staged baselines

Use repeatable low-level excitation or ambient-response windows before and after strong events. Boundaries, mass, and processing should remain as consistent as practical.

### Combine global and local views

A global view supports modes and floor relationships; a local view supports joints, connections, and cracks. Common timing and spatial mapping connect dynamic changes to local mechanisms.

## Workflow from displacement field to dynamic characteristics

### Screen data quality

Review mismatch, occlusion, saturation, motion blur, and correlation quality before analysis. Interpolating failed points directly into a mode shape can create a smooth but artificial spatial pattern.

### Treat reference motion

Choose absolute or base-relative motion according to the research question. If cameras may vibrate, assess measurement-system motion independently with stationary references or geometric correction.

### Build the response matrix

Extract synchronized histories from virtual points, region averages, or reduced spatial bases. Use consistent time spans, coordinates, missing-data rules, and bandwidth across channels.

### Identify in frequency or time domain

Frequency response, spectra, cross-spectra, free-decay, or state-space methods may suit different inputs. A method name does not guarantee validity; stability, repeatability, and residual checks matter more.

### Normalize and pair mode shapes

Cross-stage comparison requires consistent normalization and treatment of arbitrary sign. Do not pair by nearest frequency alone. Use spatial correlation, phase, and physical continuity to avoid confusing modal exchange with structural change.

### Estimate damping trends

Damping is sensitive to noise, window, and nonlinearity. Report trends and dispersion from a consistent method, comparable response amplitudes, and repeat tests instead of treating one estimate as a fixed material constant.

## Identifying time-varying dynamics

During strong shaking or cyclic loading, cracking, slip, contact, and stiffness degradation can change effective parameters. One spectrum over the entire record averages several states. Sliding-window, segmented, or time-frequency analysis can track how dominant bands and spatial modes evolve through events.

A window that is too short loses frequency resolution; one that is too long hides state change. Match the window to event duration and target band, then test sensitivity using simulated signals, repeat trials, or alternative windows.

## Linking frequency, spatial change, and damage evidence

| Evidence layer | Suggested observation | Interpretation supported | Not proven alone |
|---|---|---|---|
| Frequency | Dominant band, mode pairing, repeatability | Global dynamic change | Damage location or mechanism |
| Damping | Trend and dispersion under one method | Change in energy dissipation | Unique damage severity |
| Mode shape | Node migration, local curvature, phase regions | Change in stiffness distribution or boundary | Internal crack type |
| Displacement and strain field | Localization, residual, opening | Visible-surface deformation mechanism | Complete hidden damage state |
| Independent observation | Crack inspection, force, acceleration, boundary state | Rejection of alternative explanations | Automatic safety classification |

Damage assessment should seek agreement across evidence layers. If only a small frequency change occurs with no supporting mode, local-field, or boundary evidence, the result should remain an unexplained dynamic difference rather than confirmed damage.

## Common misinterpretations

- automatically calling the highest spectral peak the first natural frequency;
- comparing frequency and damping at different response amplitudes;
- ignoring common base or camera motion;
- pairing modes only by numerical frequency;
- mistaking a color-scale change for mode-amplitude change;
- interpreting high-frequency noise from displacement differentiation as a local mode; and
- declaring a specific internal damage mechanism from frequency decrease alone.

## Independent system-evaluation perspective

DIC for seismic dynamics should be evaluated for timing, long-sequence stability, spatial reconstruction, quality metrics, virtual-sensor management, batch time-history export, and traceable parameters. Software limited to isolated peaks or static contours is poorly suited to modal pairing and time-varying analysis.

Raw-data accessibility is also important. Researchers often need to revisit windows, bands, and spatial sampling. Exportable coordinates, displacement, and quality data generally provide more scientific value than a closed single result.

## Frequently asked questions

### Does a lower natural frequency prove structural damage?

No. Boundary, mass, temperature, response amplitude, and processing can all affect frequency. Use repeat baselines, mode shapes, local deformation, and independent observations together.

### How does DIC measure a structural mode shape?

Extract dense synchronized displacement histories, treat reference motion, identify modes in the time or frequency domain, and map the spatial amplitude and phase of each mode back to the visible structure.

### Can DIC estimate damping?

It can support damping estimates from free decay, frequency response, or system identification, but noise, windows, amplitude, and model assumptions matter. Report method, repeatability, and uncertainty.

### Why can DIC and accelerometer spectra differ?

They measure displacement and acceleration and may differ in location, direction, bandwidth, and processing. Align coordinates, time, bands, and derivative or integration rules before comparison.

### Can a full-field mode shape directly locate a crack?

Local mode changes can indicate a stiffness-anomaly region but do not prove a crack. Combine them with strain localization, visual inspection, and complementary nondestructive evidence.

## Conclusion

A frequency shift is a clue, not a conclusion. DIC extends system identification beyond a few spectral peaks by exposing mode shape, phase, local deformation, and residual state. Dynamic changes in earthquake simulation become physically traceable only when repeat baselines, boundary checks, spatial modes, and damage observations are interpreted together.

</details>

