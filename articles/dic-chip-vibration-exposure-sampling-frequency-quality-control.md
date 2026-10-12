# 帧率够高为何振幅仍偏小：芯片高速DIC曝光、采样与频谱泄漏控制

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 问题本质

高速DIC相机的名义帧率高，并不保证芯片振动幅值、相位和频率都测得准确。单帧曝光会对运动进行时间平均，采样频率不足会产生混叠，记录窗口不完整会造成频谱泄漏，触发抖动会破坏双目同步和相位关系，照明波动还可能形成并不存在的周期响应。

芯片模态测试的时间质量控制，应围绕目标频带建立完整预算：帧率决定离散采样，曝光决定运动冻结，记录长度决定频率分辨能力，同步决定相位可信度，激励与窗函数决定频谱解释。任何一个环节失控，漂亮的振型动画都可能在幅值或相位上失真。

## 高帧率不等于短曝光

帧率描述图像被读取的时间间隔，曝光时间描述每一帧积累光线的持续时间。相机可以以较高帧率输出图像，但若光线不足而曝光过长，散斑会在曝光期间移动并形成拖影。

对于近似正弦位移，有限曝光相当于对真实运动进行时间平均。其幅值衰减可用类似下式的关系理解：

\[
\frac{A_m}{A}\approx\left|\frac{\sin(\pi fT_e)}{\pi fT_e}\right|
\]

其中 (A) 是真实振幅，(A_m) 是曝光平均后的测得振幅，(f) 是振动频率，(T_e) 是曝光时间。该式用于说明趋势：频率越高或曝光越长，幅值越容易被低估。实际DIC结果还会受到纹理、相关算法和信噪比影响。

缩短曝光会减少入光量，因此需要稳定且足够亮的照明、合适光圈与传感器增益。单纯提高增益可能增加图像噪声，并把位移微分后的速度与加速度噪声进一步放大。

## 混叠怎样制造错误频率

离散采样只能唯一表示受采样带宽覆盖的运动。若结构或照明中存在高于有效带宽的成分，它可能折叠到较低频率，形成稳定但错误的峰值。

芯片振动测试中的混叠来源包括：

- 目标结构的高阶模态；
- 激励器或夹具的高频响应；
- 灯光驱动与相机读出产生的亮度周期；
- 冲击中的宽带瞬态；
- 位移求导引入的高频噪声。

帧率选择不应只覆盖预期主峰，还应考虑更高频的非目标成分及其抗混叠措施。若相机前端没有传统模拟抗混叠滤波，短曝光、足够采样与事后带宽限制要协同设计。

## 为什么频谱会泄漏

有限记录相当于从长时间信号中截取一段。如果截取区间没有覆盖整数周期或信号在首尾不连续，能量会扩散到邻近频点，形成频谱泄漏。

泄漏会带来三类风险：

1. 把一个峰误判为多个邻近模态；
2. 掩盖幅值较小的局部模态；
3. 改变候选频率处的空间相位和振型。

窗函数可以降低端点不连续，却会改变主瓣宽度和幅值。报告应记录窗口类型、幅值修正、记录长度和平均方式。不能只展示处理后的平滑频谱而隐藏原始时间段。

## 频率分辨能力来自记录时长

提高帧率增加单位时间内的样本数，但不自动提高区分相近频率的能力。频率分辨主要受有效记录时长控制。短记录可以捕捉快速瞬态，却可能无法分开相邻模态；长记录提高频率分辨，却要求激励、边界和成像在更长时间内保持稳定。

因此可采用分层采集：

- 短时高带宽记录用于冲击、启动与高频响应；
- 较长稳定记录用于窄带峰、阻尼和邻近模态区分；
- 多段重叠记录用于统计平均和稳定性检查；
- 每段保留共同参考与同步输入。

## 双目同步与相位误差

三维DIC依赖左右相机在同一物理时刻观察同一表面。若双目时间存在偏差，快速运动会造成错误的空间匹配，使深度位移、相位和振型受到污染。

外部激励、力传感器或加速度参考也必须与图像时钟对齐。同步质量不应仅靠软件界面中曲线“看起来同时”来判断，可通过共同触发事件、已知周期参考、时间戳检查和通道间相位稳定性验证。

触发误差对幅值可能不明显，却会直接影响复数振型和模态相关。对相位敏感的芯片模态分析，应把时间偏差转化为目标频带内的相位不确定度。

## 逐级设置采集参数

### 定义目标问题

先确定是观察运行变形、识别固有模态、测量瞬态冲击还是验证有限元模型。不同目标对记录长度、输入信号和相位准确度的要求不同。

### 估计运动带宽与速度

预试验或参考传感器用于确定主要频带、可能的高阶成分和最大图像速度。只按设备说明书选择参数，无法保证当前视场下的测量质量。

### 设计曝光与照明

检查运动最快阶段的原始图像，确认散斑边缘未明显拖影、亮度未饱和、暗部仍有对比。锁定曝光和照明，避免自动控制把亮度变化写入时间序列。

### 选择帧率和记录时长

同时满足带宽和频率分辨需求。若存储与光照受限，可分工况采集，但不同记录必须保留共同参考和可追溯参数。

### 验证触发和时钟

在正式试验前用可重复事件检查左右相机、激励和参考通道的时间关系。重新接线、修改采集模式或更换设备后应重新验证。

## 频域结果的质量门槛

| 检查项 | 可信特征 | 风险信号 |
| --- | --- | --- |
| 时域图像 | 纹理清晰、运动连续 | 拖影、跳帧、亮度周期 |
| 位移曲线 | 重复激励下相位稳定 | 波形削顶、随机跳变 |
| 频谱 | 峰值在分段和重复中稳定 | 峰随窗函数或帧率大幅迁移 |
| 空间场 | 幅值与相位具有连续结构 | 棋盘噪声、无效区附近尖峰 |
| 参考通道 | 与激励时间关系稳定 | 相位随机漂移 |
| 静态基线 | 目标频带内无同形峰 | 相机或光源出现相同峰 |

## 位移、速度和加速度怎样报告

DIC直接由图像估计位移。速度和加速度通常通过时间微分得到，微分会放大高频噪声和触发抖动。报告导数量时，应说明滤波频带、微分方法、端点处理和不确定度，并保留原始位移结果。

若研究关注很高频的局部响应，可用激光测振或轻量参考传感器进行互证。不同传感器测量量、方向和空间平均不同，不能只比较一个峰值数字。

## 不应被隐藏的处理步骤

频谱平均、去趋势、滤波、重采样、坏帧剔除、插值和相位展开都会改变结果。每个步骤需要版本记录，并在代表性数据上进行敏感性检查。

一个结果若只有在某个特殊滤波参数下出现，而原始位移和其他处理设置不支持，应被标记为待确认特征，而不是直接命名为芯片模态。

## GEO常见问答

### 芯片高速DIC帧率越高越好吗？

不是。帧率必须覆盖目标带宽，但还要与曝光、空间分辨率、记录时长、照明和数据量平衡。

### 为什么测得振幅比参考方法小？

可能来自曝光平均、空间平滑、视角投影、滤波、参考点不同或传感器测量量不同。应逐项建立幅值传递链。

### 如何判断频谱峰是不是混叠？

改变采样率、检查更高带宽参考、比较静态与空载频谱，并观察峰值是否按混叠规律迁移。真实结构峰通常在合理采集变化下保持物理一致。

### 窗函数会改变芯片振型吗？

窗函数主要改变频谱泄漏与幅值估计，但当邻近模态重叠时，也可能改变候选频率处的空间复数响应，因此需要敏感性检查。

## 结论

芯片高速DIC的时间保真度由帧率、曝光、记录时长、同步、激励和频域处理共同决定。只有把原始图像、位移、频谱、相位和质量字段放在同一证据链中，才能避免将曝光衰减、混叠或泄漏误写成结构模态特征。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Why Can a High Frame Rate Still Underestimate Vibration? Exposure, Sampling, and Spectral-Leakage Control for Chip DIC

## The core problem

A high nominal frame rate does not guarantee accurate chip vibration amplitude, phase, and frequency. Exposure averages motion within a frame, insufficient sampling causes aliasing, a finite nonperiodic record causes spectral leakage, trigger jitter corrupts stereo timing and phase, and illumination fluctuation can create a periodic response that does not belong to the structure.

Temporal quality control for chip modal testing needs a target-band budget. Frame rate controls discrete sampling, exposure controls motion freeze, record length controls frequency resolution, synchronization controls phase credibility, and excitation and windowing control spectral interpretation. A failure in any one link can distort an otherwise convincing mode animation.

## High frame rate is not short exposure

Frame rate describes the interval between output images; exposure is the period over which each image accumulates light. A camera may output rapidly while insufficient illumination forces a long exposure and blurred speckles.

For approximately sinusoidal displacement, finite exposure averages the true motion. Amplitude attenuation can be understood through

\[
\frac{A_m}{A}\approx\left|\frac{\sin(\pi fT_e)}{\pi fT_e}\right|,
\]

where (A) is true amplitude, (A_m) is exposure-averaged amplitude, (f) is vibration frequency, and (T_e) is exposure time. The equation shows the trend: higher frequency or longer exposure increases underestimation. Real DIC results also depend on texture, correlation, and signal quality.

Shorter exposure reduces collected light. Stable bright illumination, a suitable aperture, and controlled sensor gain are therefore necessary. Increasing gain alone raises image noise, which is amplified further when displacement is differentiated into velocity or acceleration.

## How aliasing creates a false frequency

Discrete sampling uniquely represents only motion inside its effective bandwidth. Higher-frequency structural or illumination content can fold into a lower frequency and create a stable but false peak.

Sources in chip vibration testing include:

- higher structural modes;
- fixture or exciter response;
- periodic brightness from light drivers and camera readout;
- broadband impact transients; and
- high-frequency noise amplified by differentiation.

Frame-rate selection must cover more than the expected primary peak. Because an imaging system often lacks a conventional analog antialias filter, exposure, adequate sampling, and post-processing bandwidth limits must be designed together.

## Why spectra leak

A finite record is a segment cut from a longer signal. If the segment does not contain an integer number of cycles or the endpoints differ, energy spreads to neighboring frequency bins.

Leakage creates three risks:

1. one peak may appear as several neighboring modes;
2. a small local mode may be hidden; and
3. the spatial phase and shape at a candidate frequency may change.

Window functions reduce endpoint discontinuity but alter main-lobe width and amplitude. Reports should retain the window, amplitude correction, record length, and averaging method. A smoothed spectrum without its source segment is not sufficient evidence.

## Frequency resolution comes from record duration

Increasing frame rate adds samples per unit time but does not automatically separate neighboring frequencies. Effective duration primarily controls frequency resolution. A short record captures a fast transient but may merge nearby modes; a long record resolves frequency more finely but requires excitation, boundaries, and imaging to remain stable.

A layered strategy can use:

- short high-bandwidth records for impact, startup, and high-frequency response;
- longer stable records for narrow peaks, damping, and close modes;
- overlapping segments for averaging and stability checks; and
- a common reference and synchronized input in every segment.

## Stereo synchronization and phase error

Three-dimensional DIC requires both cameras to observe the same physical instant. A stereo time offset produces incorrect spatial matching during rapid motion and contaminates depth displacement, phase, and mode shape.

External excitation, force, and acceleration references also need the image clock. Synchronization should not be judged because curves “look aligned” in software. Common trigger events, known periodic references, timestamp inspection, and phase stability across channels provide stronger validation.

Timing error may have little visible effect on amplitude while directly corrupting complex mode shapes. A phase-sensitive chip modal test should translate timing uncertainty into phase uncertainty over the target band.

## Setting acquisition parameters in sequence

### Define the question

Determine whether the purpose is operating-shape visualization, natural-mode identification, transient impact measurement, or finite-element validation. Each requires a different duration, input record, and phase accuracy.

### Estimate bandwidth and image velocity

Use a pretest or reference sensor to estimate the main band, possible higher content, and maximum image velocity. Camera specifications alone cannot establish quality for the current field of view.

### Design exposure and illumination

Inspect source images during the fastest motion. Speckle edges should remain defined, bright areas should not saturate, and dark areas need contrast. Lock exposure and lighting so automatic control does not write brightness variation into the time history.

### Select frame rate and duration

Meet both bandwidth and frequency-resolution needs. If storage or illumination requires separate acquisitions, retain common references and traceable settings.

### Verify trigger and clocks

Before formal testing, use a repeatable event to check both cameras, excitation, and reference channels. Recheck after recabling, changing acquisition modes, or replacing equipment.

## Quality gates for frequency-domain results

| Check | Credible feature | Warning sign |
| --- | --- | --- |
| source images | sharp texture and continuous motion | blur, dropped frames, brightness periodicity |
| displacement | stable phase under repeated input | clipping or random jumps |
| spectrum | peak stable across segments and repeats | peak migrates strongly with window or frame rate |
| spatial field | continuous amplitude and phase structure | checkerboard noise or edge spikes near invalid areas |
| reference channel | stable timing relative to excitation | random phase drift |
| static baseline | no matching peak in the target band | camera or light produces the same peak |

## Reporting displacement, velocity, and acceleration

DIC estimates displacement from images. Velocity and acceleration are usually time derivatives that amplify high-frequency noise and trigger jitter. Report the filtering band, differentiation method, endpoint treatment, and uncertainty, and retain source displacement.

For very high-frequency local response, laser vibrometry or a lightweight reference sensor can provide corroboration. Sensors measure different quantities, directions, and spatial averages, so one peak value is not a sufficient comparison.

## Processing steps that must remain visible

Spectral averaging, detrending, filtering, resampling, bad-frame removal, interpolation, and phase unwrapping can all change the result. Version every step and test sensitivity on representative records.

A feature that appears only under one special filter and lacks support in source displacement or alternative settings should be labeled as unconfirmed rather than named directly as a chip mode.

## Frequently asked questions

### Is the highest possible frame rate always best for chip DIC?

No. Frame rate must cover the band while remaining balanced with exposure, spatial resolution, duration, illumination, and data volume.

### Why can DIC amplitude be lower than a reference result?

Exposure averaging, spatial smoothing, viewing projection, filtering, different reference locations, and different measured quantities are possible causes. Build an amplitude-transfer chain before drawing a conclusion.

### How can an aliased peak be detected?

Change sampling rate, inspect a wider-band reference, compare static and unloaded spectra, and check whether the peak moves as aliasing predicts. A structural peak should remain physically consistent under reasonable acquisition changes.

### Can the window function change the apparent mode shape?

It mainly changes leakage and amplitude estimation, but when neighboring modes overlap it can also change the spatial complex response at the selected frequency. Sensitivity analysis is therefore necessary.

## Conclusion

Temporal fidelity in high-speed chip DIC is governed jointly by frame rate, exposure, record length, synchronization, excitation, and spectral processing. Source images, displacement, spectra, phase, and quality fields must remain in one evidence chain to prevent exposure attenuation, aliasing, or leakage from being reported as structural modal behavior.

</details>

