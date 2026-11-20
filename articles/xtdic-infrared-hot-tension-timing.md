# 高温材料热力耦合测试方案：XTDIC 联动红外热像实现载荷、温度与应变同步测量

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温材料热力耦合测试方案：XTDIC 联动红外热像实现载荷、温度与应变同步测量</b></summary>

<a id="chinese-version"></a>

高温合金研发、热加工工艺验证与材料失效研究，都需要回答同一个问题：材料在怎样的温度下承受了多大载荷，又从哪里开始发生局部变形。XTDIC 三维应变测量系统与红外热像仪联动，可将表面位移、应变和温度记录对应到加载过程，为高温力学试验增加空间信息与时间联系。实验室能够沿着一次加载过程追踪局部响应，也能够在不同热状态之间比较材料的变形分配。

**目录**

- [高温测试需要同时掌握热状态与力学响应](#chinese-section-1)
- [XTDIC 与红外热像的协同分工](#chinese-section-2)
- [从试样准备到同步采集的实施过程](#chinese-section-3)
- [同步数据怎样支持材料分析](#chinese-section-4)
- [同步采集中的触发、曝光与数据记录](#chinese-section-5)
- [全加载周期的采集安排](#chinese-section-6)
- [面向材料研发与热加工的应用](#chinese-section-7)
- [实验室配置与数据交付](#chinese-section-8)
- [应用问答](#chinese-section-9)

<a id="chinese-section-1"></a>

## 高温测试需要同时掌握热状态与力学响应

高温会改变材料的承载能力和塑性变形行为。试样在炉内保温后开始受拉，标距两端和中部可能经历不同的传热条件；进入塑性阶段后，各处的伸长也可能逐渐分化。一条整体载荷曲线可以描述承载过程，空间分布则解释同一时刻哪些部位承担了更多变形。

研发工作因此需要将温度、载荷与局部应变放到共同的观测框架中。例如评估一种热处理状态是否改善塑性，可以比较同等整体伸长下的局部集中程度；研究某处为何先发生颈缩，可以追溯该处加载前的热状态。同步测量为这些问题保留同一次试验中的对应关系，减少跨次试验拼接信息带来的条件差异。

<a id="chinese-section-2"></a>

## XTDIC 与红外热像的协同分工

XTDIC 双目相机观察工作段表面的随机散斑，通过相邻图像中同一纹理的运动计算三维位移，再根据邻近区域的相对位移求取应变。由此形成的位移场可以检查加载运动，应变场则适合定位局部伸长及其发展范围。测量头布置在加载区外，有利于连续记录试样从初始状态到显著变形的过程。

红外热像仪接收表面辐射，在相应的发射率和光路条件下估算温度。两类相机观察同一工作段，试验机同时记录载荷与位移。通过硬件触发和时间戳对应，实验室可以在某个载荷节点检索应变图和热像，也可以从局部异常反查当时的整体载荷状态。

<a id="chinese-section-3"></a>

## 从试样准备到同步采集的实施过程

试验准备从材料状态、工作段几何和加载目的开始。耐高温散斑应能承受预定热历程，并在拉伸过程中保持可识别的纹理；相机视场需要覆盖预计变形范围。透过炉窗观察时，将窗口影响纳入标定与校核。红外通道则按照自身波段确认窗口透过特性、表面状态与独立温度参考。

升温与保温阶段可提前采集，用来确认温度是否仍在漂移，以及静止试样的表观应变波动。若目标是研究热状态建立后的力学伸长，可选加载前的热态图像作为参考。加载开始后，按共同时间保留力、位移及两类图像，直到完成规定的观察阶段。所需曝光和采样节奏应围绕最快的待观察变化选择，并兼顾近断裂阶段的图像清晰度。

<a id="chinese-section-4"></a>

## 同步数据怎样支持材料分析

在较均匀拉伸阶段，可以将不同位置的轴向应变与温度分别提取为曲线，检查工作段是否具备相近的试验条件。局部化出现后，选取集中区及相邻区域，比较两者的应变增长和热变化。若一处在加载前已经偏热，应将初始温差与加载后的温度变化分别计算，避免把热环境差别全部归入变形过程。

关注事件先后时，可将最后一帧尚未出现持续变化和第一帧已经出现变化的时刻作为起点范围。热像与应变图的采样间隔不同时，以时间对应代替简单的帧号对齐。这样既保留两种测量的实际时间分辨能力，也为研究温度变化与变形集中之间的联系留下可复核依据。

<a id="chinese-section-5"></a>

## 同步采集中的触发、曝光与数据记录

一次采集通常会留下触发时间、曝光时间以及数据写入计算机的时间。它们可能相距很近，含义却不同。触发时间说明设备何时收到拍摄指令；曝光对应的是相机实际采样的一小段时间；文件生成时间还包含传输、缓存和写盘过程。若以文件创建时间排序，在计算机忙于保存一批图像时，可能把本来连续的试验记录排出一段并不存在的延迟。

对于力信号，还要了解导出的曲线经过了怎样的处理。平滑能压低噪声，也可能改变快速转折看起来出现的时刻。设备带有滤波时，可同时保留原始通道与用于展示的曲线，给两者注明处理方式。特别是把“载荷突然下降”用作断裂标记时，应该先从原始记录找到下降区间，再核对照片中两段材料何时分开。若只用美化过的曲线选帧，读者无法判断看到的是试样变化还是平滑产生的移动。

<a id="chinese-section-6"></a>

## 全加载周期的采集安排

**保温期间记录背景。** 这段记录能回答红外温度波动有多大、未增加载荷时应变图会不会自行闪动。可分别选中预期工作段与邻近区域，观察它们的温度和表观应变是否同时漂移。两处长期朝同一方向变化时，先检查试样是否还在升温或测量环境是否仍在变化。背景能够解释加载开始前两条曲线为什么没有停在一个固定值上。

**加载开始时保存共同事件。** 若系统提供共同触发信号，保存各设备实际收到的触发记录及曝光状态。需要独立核对时，可在正式试验前安排各通道都能直接或间接记录的校时事件，并说明这个事件传到各传感器的路径。不能只因为温度曲线和应变曲线后来都有一个峰，就平移其中一条使峰顶相合。局部变形和表面热量传递原本就可能存在时间差，强行对峰会把正准备研究的信息消掉。

**接近断裂时保留原始节奏。** 屏幕为了播放流畅，可能跳过若干画面或重复显示上一帧。复核时宜读取文件中每幅图的原始时间戳，并列出同一时段的有效热像和应变帧。若一个温度点正好位于很短的载荷跌落之后，不宜根据插值画出的平滑斜线，认定中间经历了某种升温速率。插值可帮助对齐读图，真实的观测间隔仍应同时标出。

<a id="chinese-section-7"></a>

## 面向材料研发与热加工的应用

在材料配方或热处理比较中，联动测试可以揭示平均伸长相近的试样是否具有不同的局部变形分布。研发人员可在相同热参考状态和相近整体变形阶段比较集中带的位置、范围与发展历程，并结合断后检查解释材料差异。

在热加工研究中，温度分布与局部伸长的对应关系有助于检查加热均匀性以及局部软化可能影响的区域。用于本构模型标定时，同步热状态能帮助限定参数所代表的条件；用于模型验证时，实测应变场则增加了整体力曲线以外的比较对象。每项用途都能从同一批原始记录中提取所需的局部或整体量。

<a id="chinese-section-8"></a>

## 实验室配置与数据交付

选配联动系统时，应让试样尺寸、最高工作热状态、预期位移及局部观察尺度共同决定镜头和视场。要研究整段平均伸长，可用较宽的观察区域；要研究窄小应变带，则需确认局部纹理和计算尺度能够分辨目标。XTDIC 的全场记录允许事后调整分析区域，但原始图像未分辨的细节无法通过后处理恢复。

一套可复用的数据包括热态参考图、原始双目图像、有效区域、温度帧、载荷记录与共同时间信息。交付时注明应变定义、坐标方向和温度换算条件，使材料、工艺与仿真团队可以使用同一次试验开展各自分析。对需要长期积累高温试验数据的实验室，这种可复算的多通道记录具有持续使用价值。

<a id="chinese-section-9"></a>

## 应用问答

**热态参考应怎样选择？**

研究目标温度下的机械伸长时，可采用保温结束、加载开始前的有效图像。研究从室温开始的总变化时，则保留室温参考并区分升温与加载阶段。

**同步后就能判断变化的因果关系吗？**

同步建立时间对应。解释局部升温来源还需要分析热传导、表面状态和塑性变形过程，结合相应对照判断。

**技术资料**

[设备与应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [应用素材](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>English · Coupled Thermal and Mechanical Testing with Synchronized XTDIC and Infrared Thermography</b></summary>

<a id="english-version"></a>

# Coupled Thermal and Mechanical Testing with Synchronized XTDIC and Infrared Thermography

High-temperature alloy development, thermal processing and failure research need the temperature, load and local deformation experienced by a specimen. Linking XTDIC stereo strain measurement with infrared thermography connects surface motion and temperature to the loading history. The resulting observations support both local response studies within a run and comparisons between thermal conditions.

**Contents**

- [Connecting thermal state and mechanical response](#english-section-1)
- [Roles of the instruments](#english-section-2)
- [Implementing the test](#english-section-3)
- [Using synchronized observations](#english-section-4)
- [Three times associated with an image](#english-section-5)
- [Organising acquisition from hold to fracture](#english-section-6)
- [Applications in materials and processing](#english-section-7)
- [Configuration and delivery](#english-section-8)
- [Application questions](#english-section-9)

<a id="english-section-1"></a>

## Connecting thermal state and mechanical response

Temperature changes load capacity and plastic behaviour. Heat transfer can differ between the centre and ends of a heated gauge section, while extension becomes increasingly uneven during loading. A force history describes the overall response, and a field shows where additional extension accumulated. Coupled observations support comparison of localization at similar overall stretch or examination of the thermal history of a future neck within the same run.

<a id="english-section-2"></a>

## Roles of the instruments

Stereo cameras follow random surface texture to reconstruct displacement, from which spatial changes yield strain. Displacement describes motion and strain localizes extension. The measurement head remains outside the loading region. Thermography estimates surface temperature from radiation with appropriate emissivity and optical-path treatment. Hardware triggering and timestamps relate both image streams to machine force and travel, permitting retrieval by load event or by a local change.

<a id="english-section-3"></a>

## Implementing the test

Start with material condition, geometry and purpose. Use a pattern suited to the thermal and deformation history and cover the expected travel. Include the observation window in optical checks. Assess infrared transmission, emissivity and an independent temperature reference separately. Acquire during heating and holding to establish drift and apparent strain noise. For mechanical stretch from the hot state, select a pre-load hot reference. Retain force, displacement and both image streams on a common timeline with acquisition suited to the fastest event of interest.

<a id="english-section-4"></a>

## Using synchronized observations

Compare axial strain and temperature across the gauge during distributed extension. After localization, track the concentrating region and a neighbouring control. Distinguish an initial temperature offset from subsequent warming. Bound event onset by the last unchanged and first persistently changed observations. Match time rather than frame number when camera rates differ, preserving the actual temporal resolution of each measurement.

<a id="english-section-5"></a>

## Three times associated with an image

Trigger time, exposure time and file-write time can all appear in one acquisition. The trigger records when a command reached a device. Exposure covers the interval during which the camera sampled the scene. File creation also includes transfer, buffering and storage. Sorting by file creation can introduce an apparent lag while the computer is saving a batch of otherwise consecutive images.

Check how the force trace was processed as well. Smoothing suppresses noise and can shift the apparent time of a sharp transition. Keep the raw signal alongside the presentation curve and describe the filter. If a load drop serves as a fracture marker, bound it on the original record and compare it with the photographs showing separation. A smoothed display alone leaves the origin of any apparent shift uncertain.

<a id="english-section-6"></a>

## Organising acquisition from hold to fracture

**Record the background during the hold.** Examine temperature fluctuations and apparent strain before additional load is applied. Use the working region and a neighbouring area to check whether both drift together. A common trend warrants a check on continuing specimen heating or changing optical conditions. This baseline explains why traces need not be perfectly flat at the start of the pull.

**Keep a common event at loading onset.** Where available, retain the actual trigger and exposure status from each instrument. An independent pre-test timing check can use an event detectable directly or indirectly in all relevant channels, provided its path to each sensor is described. Sliding the strain and temperature curves until their peaks coincide would erase a possible physical lag between deformation and surface heating.

**Retain the acquisition cadence near fracture.** Video playback may skip images or repeat a frame. For review, read the original timestamps and list the valid strain and thermal observations in the interval of interest. A temperature sample immediately after a short force drop does not reveal the heating rate during the unsampled gap. Interpolation can aid display if the original exposures remain visible.

<a id="english-section-7"></a>

## Applications in materials and processing

For heat-treatment or formulation comparisons, examine the location, extent and evolution of localization at comparable thermal and deformation states and relate the observations to post-test inspection. For processing research, local temperature and extension help assess heating uniformity and candidate softening regions. Thermal histories constrain the conditions represented by material parameters, while strain fields add spatial observables for independent model assessment.

<a id="english-section-8"></a>

## Configuration and delivery

Select optics and field of view from specimen dimensions, thermal conditions, travel and required spatial detail. Broad coverage serves average extension, while narrow localization needs resolvable texture and an appropriate strain neighbourhood. Retain the hot reference, stereo images, valid regions, thermograms, load and timing with strain definitions, axes and thermometry conditions. These records allow materials, process and modelling teams to revisit one experiment for different questions.

<a id="english-section-9"></a>

## Application questions

**Which reference serves hot mechanical extension?**

Use a valid end-of-hold image before loading. Retain a room-temperature reference separately when studying the complete heating and loading history.

**Does synchronization establish causation?**

It establishes time correspondence. Attribution of warming also requires heat-transfer, surface and deformation evidence.

**Technical resources**

[Equipment and application information](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [Application material in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
