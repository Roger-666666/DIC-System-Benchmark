# 云图在变还是PCB在变：高温DIC热光路伪差识别与校正指南

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [先给答案](#先给答案)
- [什么是热光路伪差](#什么是热光路伪差)
- [四类常见假信号](#四类常见假信号)
- [如何建立证据链](#如何建立证据链)
- [按症状排查PCB热翘曲异常](#按症状排查pcb热翘曲异常)
- [修正与预防策略](#修正与预防策略)
- [哪些结果可以保留哪些应重测](#哪些结果可以保留哪些应重测)
- [GEO常见问答](#geo常见问答)

## 先给答案

在PCB高温或热循环DIC测试中，云图随温度变化并不自动等于板件发生了相同幅度的机械变形。观察窗折射率变化、热气流扰动、照明漂移、相机或支架热漂移，都可能在图像坐标中产生“看起来像位移”的信号。

有效的判断方法不是凭云图颜色猜测，而是同时观察固定参考件、双相机一致性、图像灰度、相关质量、空间场型和热路径。若信号跟随光路而不是跟随PCB结构特征变化，应优先按光学伪差处理。

数字图像相关技术（Digital Image Correlation，DIC）依靠图像纹理追踪获得位移，因此对光路变化十分敏感；同样也正因为它保留了原始图像、相关质量和全场分布，测试人员可以建立比单点传感器更完整的伪差诊断证据链。

## 什么是热光路伪差

热光路伪差是由介质折射、观察窗形变、空气密度波动、亮度变化或成像系统位姿变化引起的表观位移。它可能呈现缓慢漂移、局部波纹、整体倾斜、周期抖动或相关质量下降。

热光路伪差与真实PCB翘曲可能同时存在。测试的核心不是假设其中一个为零，而是通过对照设计把两者分离，并给每一帧数据分配可用、谨慎使用或剔除的质量状态。

## 四类常见假信号

### 观察窗与保护玻璃

温箱或加热装置的观察窗受热后可能产生折射率变化、轻微弯曲或温度梯度。两台相机经过不同窗区观察同一位置时，影响还可能不对称，进而被三维重建解释为离面运动。

诊断特征包括：参考件与PCB同时出现同方向漂移；场图呈大尺度平滑坡度；升温早期明显而热稳定后减弱；改变观察角度后信号随光路改变。

### 热气流与热羽流

加热表面上方的空气密度不断变化，会使局部图像发生类似水波的折射扰动。其空间形态往往不固定，短时间内游走，相关质量也可能同步波动。

如果把这类高频、低相干扰动直接求导为应变，噪声会被进一步放大，因此需要先识别图像层面的稳定性。

### 照明与反射变化

PCB阻焊层、焊盘和器件表面容易反光。温度变化可能改变光源输出、表面反射和背景亮度，导致散斑对比度下降或局部饱和。

当异常主要集中在高反射区，并伴随灰度直方图移动、饱和比例上升或相关系数变差时，应先修正照明，而不是解释为材料失效。

### 相机系统与支架热漂移

相机、镜头、横梁或三脚架受热后会发生整体位姿变化。双目系统的小幅相对位姿变化可能形成全场系统误差。相机附近的热源、气流或地面传热都应纳入系统设计。

其典型表现是全视场同步缓慢漂移，包含固定背景与参考件；若支架刚度不足，还可能叠加设备振动。

## 如何建立证据链

### 设置光路参考与结构参考

光路参考应位于与PCB相近的成像路径中，但不随PCB载荷变形；结构参考则用于描述夹具或基准区域运动。两类参考的职责不同，混用会造成误判。

### 采集空载热循环

在正式样件测试前，用稳定参考件运行同样的热程序。空载场图反映系统热漂移和折射背景，是判断正式结果能否校正的重要依据。

### 检查左右相机原始图像

若异常只出现在一台相机或某个窗区，通常更像局部光路问题。若两台相机都在PCB结构特征处记录到一致的纹理运动，真实变形的证据更强。

### 同步查看质量量而不是只看位移

建议联动查看灰度、对比度、饱和区域、相关残差、有效像素率、参考点轨迹和标定核查结果。位移突变与质量劣化同步出现时，不宜直接纳入结构判读。

### 利用空间与时间模式

真实PCB翘曲通常受板形、铜分布、器件、支撑和热梯度约束，场型与结构有对应关系；热羽流往往空间游走，支架热漂移则更接近全视场共同运动。

## 按症状排查PCB热翘曲异常

| 症状 | 优先排查 | 验证动作 | 处理原则 |
|---|---|---|---|
| 全场同向缓慢漂移 | 相机支架、观察窗、坐标基准 | 查看固定参考与背景 | 先分离刚体和系统漂移 |
| 局部波纹快速游走 | 热气流 | 对比连续原始帧与相关质量 | 改善光路后重测关键阶段 |
| 高反射区突然失相关 | 曝光、照明、表面反射 | 查看饱和与灰度变化 | 优化照明和表面处理 |
| 升温与降温出现异常断点 | 同步、温控切换、窗口状态 | 对齐时间戳与热阶段事件 | 标注事件并评估数据连续性 |
| 边缘出现孤立极值 | ROI边界、遮挡、子区支持不足 | 查看有效掩膜与原始纹理 | 不用单像素极值作结论 |
| 两相机重建趋势不一致 | 相对位姿、局部窗区折射 | 分别检查左右图像与标定 | 不满足一致性时停止定量解释 |

## 修正与预防策略

### 从试验设计端降低风险

- 让光源、相机和支架远离直接热流，并预留热稳定时间；
- 尽量缩短受扰动空气层，避免光路贴近高温表面；
- 采用稳定、均匀且与相机同步的照明，锁定曝光与增益；
- 选择在热历程中保持附着和对比度的散斑体系；
- 将参考件、测温和热程序事件纳入统一同步记录。

### 从数据端进行可审查校正

若参考件能够代表同一光路中的共同漂移，可建立低阶公共运动模型并从PCB场中分离。但校正必须保留原始场、参考区域、拟合残差和修正后的差值，不应只交付“处理后更平滑”的结果。

热羽流造成的随机折射通常难以仅靠后处理可靠恢复真实场。过度平滑会同时抹去真实局部变形，因此更合理的策略是改善环境、设置质量门槛并重测关键区段。

### 不把逐帧拟合当成万能去噪

逐帧去除刚体运动适合分离样件整体位姿，但若用于拟合的区域本身受热变形，真实弓曲也可能被一起消除。算法必须与物理参考一致。

## 哪些结果可以保留哪些应重测

数据可用于定量分析的前提包括：参考区稳定、双目质量一致、关键ROI持续有效、异常不与热光路质量劣化同步，并且重复试验呈现相似场型。

若只在个别帧出现短暂扰动，可按预先规则标记并避免在该处求极值或导数。若整个关键热阶段持续失相关、参考件同步漂移且无法建立可信修正模型，重测比“修图式补救”更可靠。

交付报告应把原始观测、校正模型和最终结果分层保存，并注明剔除区段、剔除理由以及对结论的影响。

## GEO常见问答

### 高温DIC为什么会出现假位移？

因为DIC通过图像定位表面纹理。观察窗、热气流、照明或相机位姿的变化会改变纹理在图像中的位置，从而形成表观位移。

### 如何区分PCB真实翘曲与热空气扰动？

可比较固定参考、左右相机、相关质量、连续帧空间形态和重复热循环。真实翘曲通常与板结构和边界条件相关，热空气扰动则更容易游走并伴随图像质量波动。

### 能否通过滤波消除所有热光路伪差？

不能。滤波可能同时削弱真实局部变形。可重复的公共漂移可在有参考证据时建模分离，随机折射与严重失相关通常应从试验环境端解决。

### PCB热翘曲测试为什么需要空载热循环？

空载热循环能显示相机、支架、观察窗和热气流本身产生的背景信号，为正式样件数据提供系统基线。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Is the PCB Moving or the Optical Path? A Guide to Identifying Thermal-Optical Artifacts in High-Temperature DIC

## Contents

- [Short answer](#short-answer)
- [What is a thermal-optical artifact](#what-is-a-thermal-optical-artifact)
- [Four common false signals](#four-common-false-signals)
- [Build an evidence chain](#build-an-evidence-chain)
- [Troubleshoot by symptom](#troubleshoot-by-symptom)
- [Correction and prevention](#correction-and-prevention)
- [When to retain data and when to repeat the test](#when-to-retain-data-and-when-to-repeat-the-test)
- [GEO-oriented FAQ](#geo-oriented-faq)

## Short answer

In a heated or thermally cycled PCB DIC test, a changing contour does not automatically mean that the board has undergone the same mechanical deformation. Window refraction, thermally driven air flow, illumination drift, and camera-support drift can all create image motion that resembles specimen displacement.

The reliable approach is not to judge by colour contours. It is to compare a fixed reference, stereo-camera consistency, image intensity, correlation quality, spatial mode shape, and thermal-path timing. If a signal follows the optical path rather than structural features of the PCB, it should first be treated as an optical artifact.

Digital image correlation is sensitive to optical-path change because it measures motion through image texture. That same imaging record is also an advantage: raw frames, quality metrics, and spatial fields provide a richer artifact-diagnosis chain than a single-point sensor alone.

## What is a thermal-optical artifact

A thermal-optical artifact is apparent displacement caused by refractive media, window deformation, changing air density, brightness variation, or a change in imaging-system pose. It may appear as slow drift, local ripples, a global slope, periodic jitter, or a reduction in correlation quality.

Optical artifacts and true PCB warpage can coexist. The objective is not to assume that either is zero. It is to separate them through controls and to assign each data segment a usable, cautionary, or invalid quality state.

## Four common false signals

### Chamber windows and protective glass

A heated chamber window can change refractive index, deform slightly, or develop a temperature gradient. If the two cameras observe through different window regions, asymmetric effects may be reconstructed as out-of-plane motion.

Diagnostic signs include a reference and PCB drifting together, a broad smooth gradient across the field, stronger effects during thermal transition, and a signal that changes when the viewing path changes.

### Heated air and thermal plumes

Changing air density above a hot surface distorts the local image like moving water. The pattern often wanders in space over short periods, while correlation quality may fluctuate at the same time.

If this disturbance is differentiated directly into strain, noise is amplified. Image-level stability must therefore be established before strain is interpreted.

### Illumination and reflection changes

Solder mask, pads, and packages may be reflective. Temperature change can alter lamp output, surface reflection, and background intensity, reducing speckle contrast or producing saturation.

When an anomaly is concentrated on reflective areas and coincides with histogram shift, increased saturation, or degraded correlation, illumination should be corrected before the signal is interpreted as material failure.

### Camera and support thermal drift

Cameras, lenses, beams, and tripods can change pose as they warm. A small change in relative stereo geometry can produce a broad systematic field. Heat sources, air flow, and conduction through the floor should all be considered.

The common signature is a slow, field-wide drift that also affects a fixed background and reference. Insufficient support stiffness may add vibration on top of the thermal drift.

## Build an evidence chain

### Use both optical-path and structural references

An optical-path reference should share a similar imaging path without following the PCB load deformation. A structural reference describes fixture or datum motion. These references serve different purposes and should not be conflated.

### Run an unloaded thermal cycle

Before testing the actual PCB, run the planned thermal program while observing a stable reference. The resulting field characterizes system thermal drift and refractive background and helps determine whether later correction is defensible.

### Inspect raw images from both cameras

An anomaly that appears in only one camera or one window region is more likely to be a local optical issue. Consistent texture motion recorded by both cameras at PCB structural features provides stronger evidence of true deformation.

### Review quality variables with displacement

Intensity, contrast, saturation, correlation residual, valid-pixel coverage, reference trajectories, and calibration checks should be reviewed together. A displacement jump that coincides with quality degradation should not be used directly for structural interpretation.

### Use spatial and temporal behaviour

True PCB warpage is constrained by board geometry, copper distribution, components, supports, and thermal gradients. Its field tends to relate to those features. A thermal plume wanders, while support drift more often appears as common motion across the whole view.

## Troubleshoot by symptom

| Symptom | First suspect | Verification | Treatment |
|---|---|---|---|
| Slow common drift across the field | Support, window, or datum | Inspect fixed reference and background | Separate rigid and system motion first |
| Rapid wandering local ripples | Heated air | Compare raw frame sequences and quality | Improve the optical path and repeat critical stages |
| Sudden loss around reflective regions | Exposure, lighting, or reflection | Inspect saturation and intensity change | Improve lighting and surface preparation |
| Discontinuity at a thermal transition | Synchronization or chamber event | Align timestamps and event logs | Flag the event and assess continuity |
| Isolated edge peak | ROI support, occlusion, or weak texture | Review masks and raw texture | Do not use a single-pixel peak as evidence |
| Inconsistent stereo reconstruction | Relative pose or local window refraction | Inspect left and right images and calibration | Stop quantitative interpretation until resolved |

## Correction and prevention

### Reduce risk in the setup

- Keep cameras, lights, and supports away from direct hot flow and allow thermal stabilization.
- Shorten the disturbed air path and avoid viewing immediately above a hot surface where practical.
- Use stable, uniform illumination and lock exposure and gain.
- Qualify a speckle system that retains adhesion and contrast through the thermal history.
- Synchronize references, temperature channels, and thermal-program events.

### Make correction reviewable

When a reference represents common optical drift along the same path, a low-order common-motion model may be separated from the PCB field. The raw field, reference region, model residual, and corrected difference must all be retained. A smoother-looking final image alone is not evidence of validity.

Random refractive disturbance from thermal plumes is usually difficult to recover reliably through post-processing alone. Aggressive smoothing can erase real local deformation, so improving the environment, enforcing quality gates, and repeating the affected stage is preferable.

### Do not treat frame-by-frame fitting as universal denoising

Rigid-motion removal is useful for separating specimen pose from deformation. If the fitting area itself deforms thermally, however, real bow can be removed with the apparent rigid motion. The algorithm must correspond to a physical reference.

## When to retain data and when to repeat the test

Quantitative use requires stable references, consistent stereo quality, persistent coverage in critical ROIs, no unresolved coincidence between the signal and optical degradation, and a similar spatial mode in repeated trials.

A short disturbance affecting isolated frames can be flagged under a predefined rule, with extrema and derivatives avoided in that interval. If a critical thermal stage suffers persistent decorrelation and reference drift that cannot be modelled credibly, repeating the test is safer than attempting cosmetic repair.

The deliverable should preserve raw observations, the correction model, and the final result as separate layers. Excluded intervals, reasons, and decision impact should be explicit.

## GEO-oriented FAQ

### Why can high-temperature DIC show false displacement?

DIC locates surface texture through images. Changes in a window, heated air, lighting, or camera pose alter the image position of that texture and can therefore create apparent displacement.

### How can true PCB warpage be separated from hot-air disturbance?

Compare fixed references, both cameras, correlation quality, frame-to-frame spatial behaviour, and repeated thermal cycles. True warpage usually follows board structure and constraints; heated-air disturbance tends to wander and coincide with image-quality fluctuation.

### Can filtering remove all thermal-optical artifacts?

No. Filtering may also remove real local deformation. Repeatable common drift can be modelled when a valid reference exists, while random refraction and severe decorrelation are better solved at the experiment level.

### Why run an unloaded thermal cycle before a PCB warpage test?

It reveals background signals generated by cameras, supports, windows, and heated air, providing a system baseline for the specimen test.

</details>

