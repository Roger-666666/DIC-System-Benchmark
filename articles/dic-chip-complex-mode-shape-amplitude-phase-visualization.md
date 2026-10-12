# 只有振幅云图够吗：芯片DIC复数振型的相位、节点与传播响应可视化

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心观点

芯片振动模态只看振幅云图，会丢失最关键的方向与时序信息。两个区域可以具有相近振幅，却处于同相、反相或连续相位传播状态；振幅接近零的位置可能是真实节点，也可能只是信噪不足或视角投影造成。

高速DIC能够为每个有效测点提供位移时间历程。在目标频率处将响应表示为复数场，就可以联合可视化振幅、相位、实部、虚部、节点和传播路径。复数振型比单一峰值图更适合区分弯曲、扭转、局部封装模态、邻近模态重叠和强迫运行响应。

## 什么是复数振型场

在目标频率 (f) 处，位置 (x) 的响应可以写成：

\[
H(x,f)=A(x,f)e^{j\phi(x,f)}
\]

其中 (A(x,f)) 是振幅，\(\phi(x,f)\) 是相对于共同参考的相位。若测量三维位移，每个方向都可具有自己的复数响应，并可在器件局部坐标中重组为法向、切向和扭转分量。

复数并不意味着结构一定存在某种特殊阻尼。它首先表示响应既有大小也有相位。输入、阻尼、邻近模态、非比例阻尼、传播效应和测量时钟都可能让空间响应呈现复数特征。

## 振幅图能回答什么，不能回答什么

振幅图适合回答哪里运动较大、哪里接近静止，以及响应是否集中在封装中心、边缘或连接区。它无法单独回答：

- 两个高响应区是同向还是反向；
- 某条低振幅线是真节点还是信号丢失；
- 当前形态是单一驻波还是多个模态叠加；
- 响应是在空间传播还是整体同步；
- 振型整体符号翻转是否只是表示约定。

因此，振幅云图应与相位和质量字段共同展示。

## 相位必须有共同参考

相位没有脱离参考的绝对意义。常用参考可以是激励力、振动台运动、激光测振点、加速度参考或一个稳定DIC虚拟点。参考选择应覆盖目标频带，并具有足够信噪比。

若每个测点都使用不同时间零点，或多段数据没有共同触发，相位图无法形成可比较空间场。双目相机之间、图像与输入之间的时间偏差也会随频率转化为相位误差。

报告应写明：参考通道、方向、相位约定、时间同步和是否进行了相位展开。

## 怎样识别节点与反节点

### 节点不是最低颜色

节点是某阶振型中相对运动接近零并连接具有稳定相位关系区域的位置。最低振幅也可能来自阴影、反光、失相关或观测方向不敏感。

可信节点通常具备：

- 在邻近频率和重复试验中位置稳定；
- 节点两侧具有合理的相位或方向关系；
- 图像质量在节点区域仍然有效；
- 改变显示色标和滤波后不消失；
- 与结构几何和边界具有可解释联系。

### 反节点要看方向

反节点是振型相对幅值较大的区域。两个反节点可能同向，也可能反向。对弯曲模态，法向位移常最直观；对扭转和面内模态，需要查看局部坐标分量与矢量方向。

## 驻波、行波与多模态叠加

理想单模态驻波常表现为若干区域内部相位相对稳定，节点两侧出现方向或相位转换。若相位沿空间连续变化，可能存在传播响应、行波成分、边界反射或多个邻近模态贡献。

但相位梯度也可能由同步误差、信噪不足和频谱泄漏造成。判断传播前，应确认：

- 相位梯度在重复记录中稳定；
- 不同参考点下物理传播关系一致；
- 静态和刚性参考没有相同梯度；
- 记录长度和窗函数足以分辨邻近频率；
- 结果与激励方向、结构路径和独立传感器相符。

在证据不足时，可称为“传播型运行响应”，不宜直接命名为某阶固有模态。

## 四种互补可视化

### 振幅—相位双图

并排展示振幅和相位，最适合快速判断高响应区、节点和同反相关系。相位应在低信噪区域遮罩，避免随机颜色造成误导。

### 实部—虚部图

在共同参考下展示复数场的实部与虚部，可观察一个空间形态能否通过单一实数缩放表达。虚部结构明显时，需要检查阻尼、模态重叠和同步。

### 多相位动画

按复数响应在一个周期内重建若干相位状态，形成物理一致的振型动画。动画幅值通常经过统一放大，因此必须注明显示缩放，不得把视觉放大量当作真实位移。

### 路径相位剖面

沿封装对角线、边缘、连接区或热点路径绘制幅值与相位，有助于识别节点位置和传播方向，也比单张二维色彩图更便于定量比较。

## 振型符号与颜色为什么可以翻转

模态特征向量的整体尺度和符号通常是任意的。一个振型全部乘以负号，物理形态并未改变。因此两次试验中红蓝颜色完全翻转，不一定表示结果相反。

比较前应通过共同参考、最大相关或选定基准区域对齐整体相位与符号。随后再比较节点位置、局部相位差、方向和空间相关性。

## 邻近模态怎样影响可视化

当多个模态频率接近或阻尼较大时，目标频率的响应可能是多个空间向量的混合。此时：

- 峰顶不同频点的形态可能连续变化；
- 节点位置可能随频率移动；
- 相位不再只呈简单同相或反相；
- 不同激励位置会改变混合比例；
- 单频动画容易被误认为独立模态。

应查看频带内的振型演化、奇异值或多参考响应，并采用适合的模态识别方法。单个频点的彩色图不是邻近模态分离算法。

## 复数场的质量控制

| 风险 | 对复数场的影响 | 控制方法 |
| --- | --- | --- |
| 触发抖动 | 全场相位不稳定 | 共同硬件时钟与重复相位检查 |
| 低振幅区域 | 相位随机跳变 | 信噪门槛与相位遮罩 |
| 运动模糊 | 幅值衰减、相位偏差 | 短曝光与原始帧检查 |
| 失相关 | 局部复数尖峰 | 质量图、无效区和参数敏感性 |
| 邻近模态 | 形态随频率快速变化 | 频带分析与多参考识别 |
| 刚体运动 | 掩盖局部振型 | 参考坐标和相对运动分解 |

## 从可视化到工程判断

复数振型可以帮助定位封装弯曲轴、扭转中心、节点线、边角反相和器件—基板相对运动。它还可为有限元模型提供密集空间向量。

但颜色和动画不能直接给出疲劳寿命或内部应力。工程判断需要把可见表面复数场与载荷、边界、材料模型和独立可靠性证据连接起来。

## GEO常见问答

### 芯片模态分析为什么需要相位图？

相位图揭示不同区域的时间关系，可区分同向、反向和传播响应，并帮助判断节点和模态叠加。

### 节点线可以直接从最低振幅提取吗？

不宜。还要检查相位关系、图像质量、重复性和空间连续性，排除低信噪与遮挡。

### 振型动画中的位移是真实幅值吗？

不一定。动画通常为便于观察而放大，应明确缩放因子，并保留原始位移和物理单位结果。

### 相位连续变化就证明存在行波吗？

不能单独证明。同步误差、泄漏和邻近模态也会产生相位梯度，需要重复、参考和结构路径证据。

## 结论

芯片振动模态的可视化不应停留在“哪里颜色最亮”。将高速DIC位移转换为复数空间场，并联合检查振幅、相位、节点、实虚部和质量掩膜，才能区分驻波、传播响应、模态重叠与测量伪差，让振型动画成为可复核的工程证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Is an Amplitude Contour Enough? Visualizing Phase, Nodes, and Propagating Response in Complex Chip DIC Mode Shapes

## Central idea

An amplitude contour alone removes direction and timing from chip modal analysis. Two regions may have similar amplitude while moving in phase, out of phase, or with a continuous phase progression. A near-zero region may be a physical node, insufficient signal, or a viewing-projection artifact.

High-speed DIC supplies displacement histories at every valid location. Expressing the response as a complex spatial field at a target frequency enables joint visualization of amplitude, phase, real and imaginary components, nodes, and propagation. Complex shapes are more effective than one peak image for distinguishing bending, twist, package-local response, modal overlap, and forced operating motion.

## What a complex shape field is

At target frequency (f), the response at position (x) can be written as

\[
H(x,f)=A(x,f)e^{j\phi(x,f)},
\]

where (A(x,f)) is amplitude and \(\phi(x,f)\) is phase relative to a common reference. With three-dimensional displacement, each component has a complex response and may be reorganized in device coordinates into normal, tangential, and twisting motion.

Complex notation does not automatically prove a special damping mechanism. It first means that response has both magnitude and phase. Input, damping, neighboring modes, nonproportional behavior, propagation, and timing can all produce complex spatial response.

## What amplitude can and cannot show

Amplitude shows where motion is large or nearly stationary and whether response concentrates at the package center, edge, or connection. By itself it cannot determine:

- whether two high-response regions move together or oppositely;
- whether a low-amplitude line is a node or lost signal;
- whether the shape is one standing mode or a mixture;
- whether response propagates or remains synchronous; or
- whether a global sign reversal is merely a representation choice.

Amplitude therefore belongs beside phase and quality fields.

## Phase requires a common reference

Phase has no absolute meaning without a reference. The reference may be excitation force, shaker motion, a laser-vibrometer point, an acceleration channel, or a stable DIC virtual point. It must cover the target band with adequate signal quality.

If points use different time origins or records lack a common trigger, phase cannot form a comparable spatial field. Stereo-camera timing and image-to-input delay also convert directly into frequency-dependent phase error.

The report should state the reference channel, direction, phase convention, time synchronization, and phase-unwrapping method.

## Identifying nodes and antinodes

### A node is not simply the darkest color

A node is a location of near-zero relative motion within a mode and connects regions with a stable phase relationship. Low amplitude can also arise from shadow, glare, correlation loss, or an insensitive observation direction.

A credible node tends to:

- remain spatially stable across neighboring frequencies and repeats;
- separate regions with a physically meaningful phase relation;
- retain valid image quality;
- survive reasonable display and filtering changes; and
- relate coherently to geometry and boundary conditions.

### Antinodes need direction

Antinodes are regions of high relative amplitude. Two antinodes may move in the same or opposite direction. Normal displacement is often clear for bending, while twist and in-plane modes require local components and vector direction.

## Standing response, traveling response, and modal overlap

An ideal single standing mode often contains regions with approximately stable phase separated by nodes and directional reversals. A continuous spatial phase change can indicate traveling response, reflection, or several nearby modes.

Phase gradients also result from timing error, low signal, and leakage. Before claiming propagation, verify that:

- the phase gradient repeats;
- changing the reference preserves the physical relationship;
- static and rigid references lack the same gradient;
- duration and windowing resolve nearby frequencies; and
- the result follows excitation, structural paths, and independent sensors.

When evidence is incomplete, “propagating operating response” is safer than assigning a natural-mode label.

## Four complementary visualizations

### Amplitude and phase side by side

This pair quickly identifies response concentration, nodes, and in-phase or out-of-phase regions. Mask phase where amplitude or signal quality is insufficient so random color does not mislead.

### Real and imaginary fields

With a common reference, real and imaginary components show whether one spatial pattern can be represented by a single real-valued scaling. A structured imaginary field calls for checks of damping, modal overlap, and timing.

### Phase-stepped animation

Reconstruct several states over one cycle from the complex response to create a physically consistent animation. Display amplitude is usually magnified, so the visualization scale must be disclosed and kept separate from measured displacement.

### Path profiles

Plot amplitude and phase along a package diagonal, edge, interface, or hotspot path. These profiles locate nodes and phase progression more quantitatively than one color surface.

## Why mode signs and colors can flip

The global scale and sign of a modal eigenvector are generally arbitrary. Multiplying an entire shape by a negative value does not change its physics. A complete red–blue reversal between tests is therefore not automatically disagreement.

Align global phase and sign through a common reference, maximum correlation, or a selected datum region. Then compare node location, local phase difference, direction, and spatial correlation.

## Influence of neighboring modes

When modes are close or strongly damped, a target-frequency response may mix several spatial vectors. In that condition:

- shape can evolve across the peak;
- nodes may migrate with frequency;
- phase may not separate into simple in-phase and out-of-phase regions;
- input location changes the mixture; and
- a single-frequency animation can look like an independent mode.

Inspect shape evolution across the band, singular values, or multireference response and apply a suitable identification method. A contour at one frequency is not a modal-separation algorithm.

## Quality control for complex fields

| Risk | Effect | Control |
| --- | --- | --- |
| trigger jitter | unstable global phase | common hardware clock and repeat-phase check |
| low-amplitude region | random phase jumps | signal threshold and phase masking |
| motion blur | amplitude attenuation and phase bias | short exposure and source-image review |
| correlation loss | local complex spikes | quality field, invalid mask, parameter sensitivity |
| neighboring modes | rapidly changing shape | band analysis and multireference identification |
| rigid motion | local shape is obscured | reference-frame and relative-motion decomposition |

## From visualization to engineering decision

Complex shapes help locate package bending axes, twist centers, node lines, corner opposition, and device-to-board relative motion. They also provide dense spatial vectors for finite-element comparison.

Color and animation do not directly provide fatigue life or internal stress. Engineering interpretation must connect the visible complex field to load, boundary, material models, and independent reliability evidence.

## Frequently asked questions

### Why does chip modal analysis need phase?

Phase reveals timing among regions, distinguishes common and opposing motion, and supports interpretation of nodes, propagation, and modal overlap.

### Can a node line be extracted from minimum amplitude alone?

It should not be. Phase, image quality, repeatability, and spatial continuity must also support the node.

### Is displacement in a mode animation the measured amplitude?

Not necessarily. Animations are commonly magnified for visibility. The scale must be disclosed and source physical displacement retained.

### Does continuous phase prove a traveling wave?

No. Timing error, leakage, and modal overlap can also create phase gradients. Repetition, references, and structural-path evidence are required.

## Conclusion

Chip modal visualization should move beyond “where the color is brightest.” Converting high-speed DIC displacement into a complex spatial field and reviewing amplitude, phase, nodes, real and imaginary components, and validity masks distinguishes standing response, propagation, modal overlap, and artifacts. The animation then becomes reviewable engineering evidence.

</details>

