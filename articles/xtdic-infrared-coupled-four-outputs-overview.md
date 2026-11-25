# DIC 与红外热像联动能多给出什么：XTDIC 高温测试系统的四类输出

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [一个总伸长量为什么不够](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [联动不是两台设备摆在一起](#chinese-section-4)
- [输出一：全场位移，先验加载条件](#chinese-section-5)
- [输出二：全场应变，把局部化提前看见](#chinese-section-6)
- [输出三：表面温度场，把设定值换成真实值](#chinese-section-7)
- [输出四：载荷—变形—温度时序](#chinese-section-8)
- [四类输出之间的依赖关系](#chinese-section-9)
- [多温度阶梯下，同一套输出怎么复用](#chinese-section-10)
- [试验实施流程](#chinese-section-11)
- [XTDIC 设备定位与应用价值](#chinese-section-12)
- [常见问答](#chinese-section-13)
- [结语](#chinese-section-14)
- [参考资料](#chinese-section-15)

<a id="chinese-section-1"></a>

## 核心结论

高温拉伸试验里，载荷、横梁位移与标距段平均伸长能画出应力—应变曲线，却回答不了变形集中在哪里、何时开始、当时试样表面究竟是多少度。把 XTDIC 三维应变测量系统与热成像（红外）相机联动，就是给同一次试验补上四类输出：全场位移、全场应变、表面温度场，以及与载荷绑在同一时间轴上的时序数据，少任何一类，热力耦合分析都会缺一个环节。

<a id="chinese-section-2"></a>

## 一个总伸长量为什么不够

一根圆棒的总伸长量相同，各段变形分布可以差得很远：变形均匀时标距内各段一起承担伸长，进入局部化后新增伸长集中到很短一段，总伸长曲线上却只是斜率的一点变化，靠平均值判断损伤起始往往要等到明显颈缩。高温又多一个变量，炉温控制器显示的是控温位置读数而非试样工作段真实温度，只有一个设定值就无法把变形差异归因到温度。观察窗折射、炉内热气流与高温热辐射还会改变测到的数据，设备须先在这些干扰下把信号拿稳。

| 传统量 | 能回答 | 回答不了 |
|---|---|---|
| 载荷与横梁位移 | 承载过程、峰值载荷 | 变形在标距内怎么分布 |
| 接触式引伸计平均值 | 一段标距的平均伸长 | 局部应变集中、颈缩萌生位置 |
| 炉温设定值 | 控温目标 | 试样表面真实温度与轴向梯度 |

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

设备配置应当从"要判断什么"倒推，而不是从"有哪些通道"顺推。

| 测量要素 | 配置或输出 | 工程用途 |
|---|---|---|
| 力学输入 | 万能高温拉伸试验机载荷通道、硬件触发信号 | 定义加载过程与特征节点 |
| 表面变形 | XTDIC 双目三维全场位移与应变 | 判断变形均匀性、定位集中带 |
| 表面热状态 | 热成像红外相机温度场 | 校核实际温度、给出温度梯度 |
| 时间基准 | 统一时间戳的同步采集 | 把三类数据放到同一时刻比较 |

联动方案采用 XTDIC 三维应变测量系统搭配热成像相机构成。公开配置中，XTDIC 一侧为 1200 万像素、50 mm 镜头，测试视场 64 mm × 48 mm；力学设备为万能高温拉伸试验机配套高温电阻炉；试样为高温金属标准圆棒拉伸试样，工作段喷涂耐高温无机散斑。试验机载荷、DIC 可见光图像、热成像红外图像通过硬件实现毫秒级时序同步，共享统一时间戳。

<a id="chinese-section-4"></a>

## 联动不是两台设备摆在一起

把一台可见光 DIC 和一台热像仪同时架在炉前、各采各的，得到的仍是两套数据；联动的门槛有三条：共同的时间轴、可对应的空间位置、可互相校验的判据。时间轴靠硬件触发，空间位置靠视场与坐标对应，判据靠互相校验。

| 通道 | 观察对象 | 在联动中的角色 |
|---|---|---|
| 试验机 | 载荷、横梁位移 | 提供加载历程与特征节点 |
| XTDIC 可见光 | 表面散斑的位移与应变 | 提供力学响应与局部化位置 |
| 热成像红外 | 表面辐射温度分布 | 提供真实热状态与温度梯度 |
| 同步单元 | 触发与时间戳 | 把三者约束到同一时刻 |

少掉同步单元，剩下三路数据只能做"事后对照"，无法做"同一时刻的耦合分析"。

<a id="chinese-section-5"></a>

## 输出一：全场位移，先验加载条件

位移场是最先该看的一张图，价值不在"变形多少"，而在"这次加载有没有问题"。高温金属圆棒拉伸的位移云图上，若轴向位移梯度连续、对称且无单侧偏载特征，说明装夹同轴度良好、加载条件有效；这个判断是应变结论的前提，装夹偏心易被误读成材料局部化。位移场还能圈出有效区域，先划出可信范围再做梯度计算。

| 位移场特征 | 说明 | 后续动作 |
|---|---|---|
| 轴向梯度连续对称 | 装夹同轴、加载有效 | 进入应变分析 |
| 单侧梯度偏大 | 疑似偏心或单侧受热 | 检查装夹与炉内均温 |
| 局部突变或断层 | 散斑失效或匹配中断 | 剔除该区域，重做制样 |

<a id="chinese-section-6"></a>

## 输出二：全场应变，把局部化提前看见

主应变云图是四类输出里最贴近材料判断的一张，能直接定位应变集中区域及梯度，捕捉塑性局部化萌生位置，且这个位置在时间上早于肉眼可见的颈缩。难点在高温下把图出稳：热辐射与热气流造成散斑灰度波动，颈缩阶段又出现大梯度应变，高温散斑亚像素鲁棒追踪算法让局部化带从萌生到发展连续记录。设备还能提取局部应变时序用于仿真对标，但感兴趣区域在各次试验里应保持一致，否则曲线不可比。

| 应变场读法 | 得到什么 | 常见误判 |
|---|---|---|
| 集中带位置 | 局部化萌生在哪一段 | 把装夹偏心当成集中带 |
| 集中带梯度 | 局部化发展快慢 | 用统一色标掩盖真实差异 |
| 局部应变时序 | 该区域的演化曲线 | 区域边界中途改动导致不可比 |

<a id="chinese-section-7"></a>

## 输出三：表面温度场，把设定值换成真实值

热成像温度场云图补上的是"试样到底多热"这个此前只能靠推测的量，能量化标距段轴向、径向温度梯度，校核实际均温水平，并区分温控设定值与试样真实温度。这不只是精度问题：高温本构测试里温度是材料参数的输入，用设定值代替真实值会让参数带系统性偏差。红外测温还受发射率、表面涂层与观察窗影响，需与表面实际状态一起解读。

| 温度场用途 | 具体作用 | 前置条件 |
|---|---|---|
| 校核均温水平 | 判断是否达到热平衡再加载 | 充分保温 |
| 量化轴向/径向梯度 | 判断标距段是否等温 | 视场覆盖整个标距段 |
| 修正本构测试偏差 | 用真实温度替代设定值 | 发射率与表面状态一致 |

<a id="chinese-section-8"></a>

## 输出四：载荷—变形—温度时序

前三类是"场"，第四类是把场串起来的"时间"。依托统一时间戳，弹性段、强化段、峰值载荷、颈缩失稳、断裂等特征节点可分别与同步应变帧、温度帧绑定，确定塑性失稳启动时刻、失稳位置及对应真实温度，形成载荷—变形—温度耦合时序数据集。没有时间轴只能看到"某时刻的云图"，有了时间轴才能回答失稳是在哪个载荷、哪个温度、从哪个位置开始。设备在这一层通常输出一条载荷—位移曲线加若干局部时序曲线，建议把特征节点单独列成表，记下时间、载荷、局部应变、局部温度四项，跨温度阶梯比较时才比的是同一类节点。

| 特征节点 | 绑定的数据 | 用于判断 |
|---|---|---|
| 弹性段末端 | 载荷、均匀应变、温度 | 温度对弹性响应的影响 |
| 峰值载荷 | 载荷、集中带应变、温度 | 承载极限对应的热状态 |
| 颈缩失稳启动 | 时间、位置、应变梯度、温度 | 塑性失稳的起始条件 |
| 断裂 | 时间、局部应变、温度 | 失效前的演化终点 |

<a id="chinese-section-9"></a>

## 四类输出之间的依赖关系

四类输出有先后顺序，不是并列摆盘：位移场先验证加载与有效区域，应变场在此基础上给出局部化，温度场说明局部化发生在什么热状态下，时序数据把三者与载荷绑到同一时刻，前一层的结论不成立，后一层就没有解释力。例如位移场若显示单侧偏载，应变集中带便不能直接归因于材料局部化；标距段轴向温差明显时，"200℃ 工况"也不是单一温度下的结果。

| 层级 | 输出 | 依赖上一层 | 出问题时的影响 |
|---|---|---|---|
| 1 | 全场位移 | — | 后续全部不可信 |
| 2 | 全场应变 | 装夹与有效区域有效 | 集中带归因错误 |
| 3 | 表面温度场 | 视场与表面状态一致 | 温度输入偏差 |
| 4 | 耦合时序 | 三路共享时间戳 | 节点与帧错位 |

<a id="chinese-section-10"></a>

## 多温度阶梯下，同一套输出怎么复用

公开案例中，温度阶梯设为 200℃、400℃、600℃、800℃、1000℃，每一档都按"升温至目标温度 → 充分保温、炉内热环境达到热平衡 → 启动拉伸加载"的顺序执行，DIC、热成像相机与试验机硬件同步触发采集。多阶梯的价值在于同一套输出反复复用：每档只更换温度条件，数据处理口径与设备配置保持不变，可比性就容易维持。

| 温度阶梯 | 该档重点核对 | 与设备相关的注意点 |
|---|---|---|
| 200℃ | 基准响应与散斑初始状态 | 建立统一参考帧 |
| 400℃ | 灰度漂移是否开始出现 | 检查散斑追踪稳定性 |
| 600℃ | 轴向温差与热平衡 | 用温度场判断保温是否充分 |
| 800℃ | 大梯度应变的追踪能力 | 关注颈缩段匹配连续性 |
| 1000℃ | 热辐射与视窗影响 | 复核折射校准与有效区域 |

<a id="chinese-section-11"></a>

## 试验实施流程

### 试样预处理与制斑

在圆棒工作段喷涂耐高温无机散斑，先做静态序列检查斑点对比度与附着力，确认目标温区内特征稳定可追踪。

### 装夹与光路确认

调整试样同轴度，确认双目公共视场覆盖标距段，检查高温炉玻璃观察窗是否清洁、是否在两路光路上引入可见畸变。

### 温度与热平衡

按温度阶梯升温至目标值并充分保温，用热像仪温度场判断标距段是否达到均温，再决定是否启动加载。

### 同步触发与采集

由硬件触发源统一驱动试验机载荷、DIC 可见光图像与热成像红外图像，确认三路数据带统一时间戳后开始拉伸。

### 数据处理与交付

先出位移场核对加载，再出应变场与温度场，最后绑定特征节点形成耦合时序；数值曲线、云图与原始图像一并交付。

<a id="chinese-section-12"></a>

## XTDIC 设备定位与应用价值

XTDIC 三维应变测量系统在这套联动方案中承担表面力学响应通道：透过玻璃视窗输出全场位移与应变，把均匀塑性、应变局部化、颈缩损伤直至断裂记录为可复核的场数据，与热像仪各自补上对方没有的那一维。这套配置适合高温新材料机理研究、热处理工艺优化与热—力耦合仿真对标。它不替代接触式引伸计做常温拉伸的常规验收，温度超出散斑与光学件承受范围、试样移出视场时数据可用性会下降。

<a id="chinese-section-13"></a>

## 常见问答

### 只加一台热像仪，能不能算联动？

仅有热像仪可以补充温度信息，但若三路数据没有统一时间戳，变形与温度只能做事后对照，无法把峰值载荷、颈缩失稳这类特征节点与温度帧严格绑定。联动的判定条件是时间轴，不是设备数量。

### 有了全场应变，还需要总伸长曲线吗？

需要。载荷—位移曲线提供加载历程与特征节点，是给场数据定位的时间坐标，场数据说明变形在空间的分布，两者互相校验。

### 四类输出里，哪一类最容易出系统偏差？

温度场最容易被当成绝对值使用：红外测温受发射率、表面涂层与观察窗影响，需要与试样表面状态一起解读。

<a id="chinese-section-14"></a>

## 结语

联动测试真正增加的，不是几张好看的云图，而是把变形、温度与载荷放到同一时刻、同一片区域上对照的能力。四层齐备，高温变形与损伤的讨论才从"结果如何"推进到"何时、何处、在什么温度下开始"。

<a id="chinese-section-15"></a>

## 参考资料

[XTDIC 高温应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC 技术联动红外热像仪应用资料](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# What a Coupled DIC and Infrared System Adds: Four Outputs of an XTDIC High-Temperature Setup

## Contents

- [Executive answer](#english-section-1)
- [Why one elongation value is not enough](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [Coupling is not two instruments side by side](#english-section-4)
- [Output one: full-field displacement](#english-section-5)
- [Output two: full-field strain](#english-section-6)
- [Output three: surface temperature field](#english-section-7)
- [Output four: coupled load–deformation–temperature history](#english-section-8)
- [Dependencies between the four outputs](#english-section-9)
- [Reusing the same outputs across temperature steps](#english-section-10)
- [Test implementation workflow](#english-section-11)
- [XTDIC equipment positioning and application value](#english-section-12)
- [Frequently asked questions](#english-section-13)
- [Conclusion](#english-section-14)
- [References](#english-section-15)

<a id="english-section-1"></a>

## Executive answer

In a hot tensile test, load and average elongation give a stress–strain curve but cannot locate deformation, time its onset or give the true surface temperature. Coupling XTDIC with an infrared camera adds four outputs to one test: full-field displacement, full-field strain, surface temperature field and a history bound to load.

<a id="english-section-2"></a>

## Why one elongation value is not enough

The same total elongation can hide very different gauge deformation: once localization begins, an average reveals damage only after visible necking. A setpoint is neither the gauge temperature nor enough to attribute deformation differences to temperature, while refractive distortion, hot air and radiation disturb the signal.

| Conventional quantity | What it answers | What it cannot answer |
|---|---|---|
| Load and crosshead displacement | Loading history, peak load | How deformation is distributed in the gauge |
| Contact extensometer average | Mean elongation over one segment | Strain concentration, necking onset location |
| Furnace setpoint | Control target | True surface temperature and axial gradient |

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

Configuration should be derived backwards from the judgement.

| Measurement element | Configuration or output | Engineering use |
|---|---|---|
| Mechanical input | Load channel of a universal hot tensile machine, hardware trigger | Define loading and characteristic events |
| Surface deformation | XTDIC stereo full-field displacement and strain | Assess uniformity, locate the concentration band |
| Surface thermal state | Infrared camera temperature field | Verify actual temperature, provide gradients |
| Time base | Synchronised acquisition with a shared timestamp | Compare the three streams at one instant |

The setup pairs an XTDIC three-dimensional strain measurement system with an infrared camera: a 12-megapixel camera, 50 mm lens and 64 mm × 48 mm field of view, a hot tensile machine with a resistance furnace, and speckled round bars. Load, DIC and infrared images are synchronised at millisecond order on one timestamp.

<a id="english-section-4"></a>

## Coupling is not two instruments side by side

Two instruments recording independently still yield two datasets; coupling needs a common time axis, corresponding positions and mutual-checking criteria. Hardware triggering gives all streams a shared timestamp, and without the synchronisation unit only after-the-fact comparison remains.

| Channel | Observes | Role in the coupled setup |
|---|---|---|
| Tensile machine | Load, crosshead displacement | Loading history and characteristic events |
| XTDIC visible light | Speckle displacement and strain | Mechanical response and localization position |
| Infrared thermography | Surface radiative temperature | True thermal state and gradients |
| Synchronisation unit | Trigger and timestamp | Constrains all three to one instant |

<a id="english-section-5"></a>

## Output one: full-field displacement

The displacement map is read first for whether loading was valid, not how much deformation occurred: a continuous symmetric gradient with no one-sided bias confirms coaxiality. It also marks the usable region before gradients are computed.

| Displacement feature | Indicates | Next action |
|---|---|---|
| Continuous symmetric axial gradient | Coaxial clamping, valid loading | Proceed to strain analysis |
| Larger gradient on one side | Possible eccentricity or one-sided heating | Check clamping and furnace uniformity |
| Local jump or gap | Speckle failure or matching dropout | Exclude the region, reprepare the surface |

<a id="english-section-6"></a>

## Output two: full-field strain

The principal strain map locates the concentration band and plastic localization earlier than visible necking. Stability at temperature is the difficulty, addressed by robust high-temperature sub-pixel tracking; local strain histories serve simulation correlation provided the region of interest stays fixed across steps.

| Reading of the strain field | What it gives | Common misjudgement |
|---|---|---|
| Position of the band | Where localization begins | Clamping eccentricity read as a band |
| Gradient of the band | How fast localization develops | A shared colour scale hiding real differences |
| Local strain history | Evolution curve of that region | Region moved mid-series, breaking comparability |

<a id="english-section-7"></a>

## Output three: surface temperature field

The infrared map gives the true specimen temperature, quantifying axial and radial gradients and separating the setpoint from the real value. Since temperature is a material-parameter input, a setpoint biases the curve and an axial gradient spans a temperature range.

| Use of temperature field | Effect | Prerequisite |
|---|---|---|
| Verify uniformity | Decide whether equilibrium was reached before loading | Adequate soaking |
| Quantify axial/radial gradients | Judge whether the gauge is isothermal | Field covers the whole gauge |
| Correct constitutive bias | Replace setpoint with measured temperature | Consistent emissivity and surface state |

<a id="english-section-8"></a>

## Output four: coupled load–deformation–temperature history

The fourth output is the time axis linking the three fields: a shared timestamp binds elastic, hardening, peak-load, necking and fracture events to synchronous strain and temperature frames, fixing the onset instant, location and true temperature of instability. Deliverables include a load–displacement curve and local histories.

| Characteristic event | Bound data | Judgement supported |
|---|---|---|
| End of elastic range | Load, uniform strain, temperature | Temperature effect on elastic response |
| Peak load | Load, band strain, temperature | Thermal state at the load limit |
| Necking onset | Time, position, strain gradient, temperature | Initiation condition of plastic instability |
| Fracture | Time, local strain, temperature | End point of pre-failure evolution |

<a id="english-section-9"></a>

## Dependencies between the four outputs

The four outputs follow an order: displacement validates loading, strain locates localization, temperature states the thermal state and the history binds all three to load. One-sided bias prevents attributing a strain band to localization, and a clear axial gradient means a "200℃" curve is not a single-temperature result.

| Layer | Output | Depends on | Consequence if faulty |
|---|---|---|---|
| 1 | Full-field displacement | — | Everything downstream unreliable |
| 2 | Full-field strain | Valid clamping and usable region | Wrong attribution of the band |
| 3 | Surface temperature field | Matching field and surface state | Biased temperature input |
| 4 | Coupled history | Shared timestamp across three streams | Events and frames misaligned |

<a id="english-section-10"></a>

## Reusing the same outputs across temperature steps

The reported steps are 200℃, 400℃, 600℃, 800℃ and 1000℃, each heated, soaked to equilibrium and loaded with DIC, thermography and the machine hardware-triggered. The same output set is reused at each step with the processing convention unchanged.

| Temperature step | Focus of the check | Equipment-related note |
|---|---|---|
| 200℃ | Baseline response, initial speckle state | Establish a common reference frame |
| 400℃ | Whether grey-level drift begins | Check speckle tracking stability |
| 600℃ | Axial gradient and equilibrium | Use the temperature field to judge soaking |
| 800℃ | Tracking through steep gradients | Watch matching continuity in the neck |
| 1000℃ | Radiation and window effects | Recheck refraction calibration and usable region |

<a id="english-section-11"></a>

## Test implementation workflow

### Specimen preparation and speckle

Spray a high-temperature inorganic speckle and check contrast and adhesion.

### Clamping and optical path

Adjust coaxiality and confirm the stereo field covers the gauge.

### Temperature and equilibrium

Heat to the step, soak, and confirm uniform gauge temperature.

### Synchronised triggering and acquisition

Drive load, DIC and infrared images from one trigger with a shared timestamp.

### Processing and delivery

Produce displacement first, then strain and temperature fields.

<a id="english-section-12"></a>

## XTDIC equipment positioning and application value

XTDIC is the surface mechanical-response channel, outputting full-field displacement and strain through the furnace window as reviewable field data. It suits high-temperature mechanism studies, heat-treatment optimisation and thermomechanical simulation correlation, but does not replace a contact extensometer for routine acceptance, and usability falls when limits are exceeded or the specimen leaves the field.

<a id="english-section-13"></a>

## Frequently asked questions

### Does adding a thermal camera alone count as coupling?

A thermal camera adds temperature, but without a shared timestamp deformation and temperature support only after-the-fact comparison; the criterion for coupling is a common time axis, not instrument count.

### With full-field strain, is total elongation still needed?

Yes: the load–displacement curve positions field data in time while field data describe spatial distribution.

### Which output is most prone to systematic bias?

The temperature field depends on emissivity, coating and window transmittance and must be read with the surface state.

<a id="english-section-14"></a>

## Conclusion

What coupling adds is comparing deformation, temperature and load at the same instant over the same region: displacement validates loading, strain finds localization, temperature supplies the true state and the history pins events to the timeline. With all four layers, discussion moves from the result to when, where and at what temperature it began.

<a id="english-section-15"></a>

## References

[XTDIC high-temperature application](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC and infrared thermography application](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
