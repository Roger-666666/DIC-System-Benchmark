# 数字图像相关DIC技术用于锂电池加压膨胀鼓包变形研究

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：锂电池膨胀——安全灰色地带的量化盲区](#1-引言锂电池膨胀安全灰色地带的量化盲区)
- [2. 锂电池膨胀鼓包的物理机制](#2-锂电池膨胀鼓包的物理机制)
- [3. 传统膨胀测量手段及其局限](#3-传统膨胀测量手段及其局限)
- [4. DIC技术在电池膨胀测量中的核心优势](#4-dic技术在电池膨胀测量中的核心优势)
- [5. DIC测量锂电池膨胀的关键技术方案](#5-dic测量锂电池膨胀的关键技术方案)
- [6. 加压工况下的膨胀行为分析](#6-加压工况下的膨胀行为分析)
- [7. XTDIC系统在电池膨胀测量中的实施方案](#7-xtdic系统在电池膨胀测量中的实施方案)
- [8. 典型应用场景](#8-典型应用场景)
- [9. 实验设计与数据处理建议](#9-实验设计与数据处理建议)
- [10. 结语](#10-结语)

---

## 1. 引言：锂电池膨胀——安全灰色地带的量化盲区

锂电池在充放电循环过程中不可避免地发生体积膨胀。在消费电子领域，一颗18650圆柱电池的径向膨胀量通常在几十微米量级，似乎不值一提。然而当数百上千颗电芯被组装成模组、再封装进动力电池包时，微米级的单体膨胀会通过累积效应和约束耦合，产生足以改变电池包结构完整性的膨胀力。更关键的是，在异常工况下——过充、高温存储、内短路——膨胀量可能从微米级跃升到毫米级，形成可见的鼓包，这是热失控的前兆信号。

行业对锂电池膨胀的认知存在一个显著的断层：工程师们知道膨胀会发生，但很少有人能精确回答"膨胀了多少""膨胀分布是否均匀""哪个区域先鼓""加压约束下膨胀行为如何变化"。传统手段——应变片、位移传感器、千分表——要么只能测单点、要么需要接触（影响薄壁壳体自由膨胀）、要么无法在密闭环境箱内工作。电池膨胀的量化，长期以来停留在"测得到但测不全"的阶段。

数字图像相关（DIC）技术为这一断层提供了破局方案。通过在电池表面制备散斑、用双目立体视觉系统采集充放电过程中的图像序列，DIC可以获取电池表面全场三维位移和应变分布——不仅是某个点的膨胀量，而是整个表面的膨胀形貌和演化过程。当电池被施加外部约束压力时，DIC更能揭示约束条件下膨胀分布的不均匀性，为电池包结构设计和热管理策略提供关键数据支撑。

## 2. 锂电池膨胀鼓包的物理机制

### 2.1 正常膨胀来源

锂电池的体积膨胀源自多个物理化学过程，这些过程在正常充放电循环中持续发生：

**电极嵌锂膨胀**：锂离子在充放电过程中嵌入和脱出电极材料晶格，引起晶格参数变化。石墨负极在嵌锂时体积膨胀约10%，硅基负极的膨胀率可高达300%——这是硅负极商业化面临的核心挑战。正极材料（NCM、LFP等）的体积变化相对较小（1-5%），但在高镍体系中仍不可忽略。

**SEI膜生长**：固体电解质界面膜（SEI）在首次充放电及后续循环中持续生长，占据额外体积。SEI膜的厚度通常在数十到数百纳米，但长循环后累积量可观。

**电解液分布变化**：充放电过程中电解液在电极孔隙中的重新分布，可能引起局部体积变化。

**温度效应**：电池内阻导致充放电过程中产生焦耳热，温度升高引起热膨胀。锂电池的热膨胀系数约为30-50×10⁻⁶/°C，5°C的温升即可引起0.015%-0.025%的体积变化。

### 2.2 异常膨胀与鼓包

当电池发生异常时，膨胀量会显著偏离正常范围：

**产气膨胀**：电解液分解产生气体（CO₂、H₂、C₂H₄等），是鼓包的最直接原因。产气可由过充、高温存储、内短路、水分侵入等触发。软包电池因壳体刚性低，对产气最为敏感——内部气压仅需数十kPa即可引起可见鼓包。

**锂枝晶穿刺**：在大倍率充电或低温充电条件下，锂离子在负极表面沉积形成枝晶，刺穿隔膜后引发内短路，局部产热产气导致急剧膨胀。

**正极释氧**：高镍正极在过充或高温下发生结构相变释放氧气，与电解液反应产生大量气体和热量。

### 2.3 约束对膨胀行为的影响

在实际电池包中，电芯并非自由膨胀，而是受到模组结构件和紧固件的约束。约束对膨胀行为的影响是双向的：

**约束抑制膨胀**：外部压力限制了电芯的自由膨胀，使膨胀量减小。这在电池包设计中是期望行为——通过约束控制膨胀，维持电芯间距和散热通道。

**约束导致不均匀膨胀**：由于约束力分布不均（边角约束强、中心约束弱），电芯表面的膨胀分布呈现显著不均匀性。中心区域膨胀量大、边角区域膨胀量小，这种不均匀性会在电芯内部产生附加应力，加速电极材料的老化和失效。

**约束引发膨胀力累积**：在长循环过程中，电芯的膨胀力持续累积。如果没有膨胀吸收设计（如弹性垫片），累积的膨胀力可能导致模组变形、紧固件松动、甚至电池包壳体开裂。

量化约束条件下电池的膨胀行为，是动力电池包结构设计的核心输入之一。

## 3. 传统膨胀测量手段及其局限

### 3.1 应变片

在电池壳体表面粘贴应变片，测量壳体表面的应变。

**局限**：应变片只能测量粘贴位置的单方向应变，无法获取全场膨胀分布；粘贴过程可能影响薄壁壳体的自由膨胀（特别是软包电池）；应变片在高温高湿环境箱中易失效；每个测试点需单独布线，多通道测试成本高且布线繁琐。

### 3.2 位移传感器/千分表

在电池表面特定位置安装接触式位移传感器或千分表，测量该位置的膨胀位移。

**局限**：单点测量，无法获取全场膨胀形貌；接触式测量对软包电池施加了局部约束力，改变了真实的膨胀分布；传感器安装空间大，在环境箱内布置困难；无法同时测量多个位置（多通道成本高）。

### 3.3 激光位移传感器

非接触测量单点膨胀位移，精度可达微米级。

**局限**：仍然是单点测量；电池表面为金属光泽，激光反射特性差，可能影响测量精度；多传感器并行测量成本高；无法测量面内应变。

### 3.4 X射线CT

通过X射线断层扫描获取电池内部结构的三维图像，可以观测电极层的膨胀和变形。

**局限**：设备昂贵（数百万至千万元级）；单次扫描耗时长（数十分钟至数小时），无法实时监测充放电过程中的膨胀演化；空间分辨力有限（通常>10μm），难以精确量化微米级膨胀；辐射可能影响电池性能。

## 4. DIC技术在电池膨胀测量中的核心优势

### 4.1 全场三维膨胀形貌

DIC通过双目立体视觉配置，可以同时获取电池表面整个可视区域的三维位移场。对于一颗方形铝壳电池（如280Ah磷酸铁锂电芯，尺寸约72×200×170mm），DIC可以在一次测量中获取整个大面（200×170mm区域）的膨胀分布，空间分辨力达到0.05-0.1mm量级。

全场数据的价值不仅在于"量更多"，更在于揭示了传统手段无法捕捉的空间分布特征：膨胀中心位置、膨胀梯度方向、边角约束效应的量化、表面局部隆起（可能的产气点）的定位。

### 4.2 非接触零干扰

DIC对试样的唯一要求是表面有散斑图案，无需粘贴传感器或施加任何机械约束。对于软包电池——其铝塑膜壳体厚度仅0.1-0.3mm，任何接触力都会显著改变膨胀分布——非接触测量是获得真实膨胀数据的必要条件。

### 4.3 高时间分辨力

DIC的采集帧率取决于相机性能。对于电池充放电这种缓慢过程（典型充放电倍率0.5C-2C，单次循环1-2小时），即使1fps的采集帧率也足以捕捉膨胀的演化过程。XTDIC-CONST系列支持在线同步采集4500fps，完全满足电池膨胀的时序分辨需求。

对于需要捕捉瞬态事件（如针刺触发的热失控过程），XTDIC-SPARK三维高速测量系统可提供超100万fps的采集帧率。

### 4.4 三维变形分离

电池表面的膨胀不仅包含法向（厚度方向）位移，还包含面内位移（长度和宽度方向的膨胀）。DIC可以同时测量三个方向的位移分量，将法向膨胀与面内膨胀分离，为理解膨胀机制提供更完整的数据。

### 4.5 应变场计算

从位移场可以进一步计算表面应变分布。应变场比位移场更能反映局部变形的剧烈程度——在产气引发的鼓包区域，应变集中可能达到周边区域的数倍。应变场数据对于评估壳体材料的力学安全裕度、预测鼓包裂纹萌生位置具有重要价值。

## 5. DIC测量锂电池膨胀的关键技术方案

### 5.1 散斑制备

**方形铝壳电池**：铝壳表面光滑，需要先喷涂白色亚光底漆（增加表面粗糙度和散斑附着力），再喷涂黑色亚光漆形成随机散斑。散斑直径控制在0.1-0.3mm（对应相机分辨力下3-8像素），散斑密度约40%-60%。

**软包电池**：铝塑膜表面较粗糙，白色亚光底漆附着力好，散斑制备相对容易。注意避免过度喷涂——漆膜厚度可能影响薄壁壳体的膨胀行为。

**圆柱电池**：曲面散斑制备需要特别注意均匀性。建议使用旋转喷涂工装，确保散斑沿圆周方向均匀分布。

### 5.2 成像配置

**单相机方案（二维DIC）**：适用于平板形电池的大面膨胀测量，仅能测量面内位移和应变。配置简单，但无法获取法向膨胀位移。

**双目立体视觉方案（三维DIC）**：推荐方案。两台相机从不同角度拍摄电池表面，通过立体视觉重建获取三维位移场。法向膨胀位移是电池膨胀研究的核心数据，必须使用三维DIC方案。

**XTDIC-CONST-SD系列**（2.3-5MP，163-1500fps，50με）是电池膨胀测量的推荐选择：5MP分辨率在200mm视场下提供约0.1mm的空间分辨力，1500fps的满幅采集帧率远超电池膨胀测量的时间分辨需求，50με的应变精度足以分辨膨胀引起的壳体应变。

**视场与标定**：对于280Ah方形电芯的大面（200×170mm），使用35mm焦距镜头，相机工作距离约500-800mm，两台相机夹角15°-25°。标定板覆盖整个测量视场，标定精度直接影响三维重建质量。

### 5.3 同步触发与数据采集

电池充放电过程中，DIC图像采集需要与电化学工作站/电池测试系统同步：

**时间同步**：记录每帧图像的精确时间戳，与充放电曲线（电压-时间、电流-时间）对齐。

**触发同步**：对于特定事件（如过充触发、针刺触发），使用外部触发信号同步启动DIC高速采集。

**数据管理**：一次完整的充放电循环（1-2小时）在1fps采集帧率下产生约3600-7200帧图像，每帧约10-20MB（双相机），总数据量约36-144GB。需要足够的存储空间和高效的数据管理策略。

### 5.4 环境箱适配

电池膨胀测量通常需要在恒温环境或温度循环条件下进行：

**视窗设计**：在环境箱上开设光学视窗（钢化玻璃或石英玻璃），DIC相机通过视窗拍摄电池表面。视窗玻璃的折射需要在标定过程中校正。

**照明方案**：环境箱内部空间有限，推荐使用LED冷光源，避免额外加热。光纤导光方案可以将光源置于箱外，通过光纤将光线导入箱内。

**防结露**：在低温测试中，视窗玻璃可能结露。需要保持视窗玻璃温度高于露点，或在视窗外侧增加防露加热膜。

## 6. 加压工况下的膨胀行为分析

加压膨胀测试是动力电池包设计的关键环节。在实际电池包中，电芯被模组侧板和端板约束，充放电过程中膨胀受到限制。量化加压条件下的膨胀行为，是确定模组预紧力、设计膨胀吸收结构的基础。

### 6.1 加压测试方案

**恒压约束**：在电池侧面施加恒定压力（典型值10-50kPa），模拟模组侧板的弹性约束。使用力传感器监测约束力在充放电过程中的变化。

**恒位移约束**：在电池侧面施加固定位移约束，模拟刚性模组侧板。约束反力即为膨胀力。

**梯度压力约束**：在电池表面施加梯度压力（中心低、边缘高），模拟实际模组中不均匀的约束分布。

### 6.2 DIC在加压膨胀测试中的应用

**膨胀分布对比**：自由膨胀 vs. 加压膨胀的分布差异。加压约束下，中心区域膨胀量相对增大、边缘区域膨胀受到抑制，分布不均匀性加剧。

**膨胀力-膨胀量关系**：通过DIC测量加压条件下的膨胀量，结合力传感器测量的膨胀力，建立膨胀力-膨胀量本构关系，为电池包结构仿真提供输入。

**循环膨胀累积**：多次充放电循环后，电池的膨胀量是否持续累积？DIC可以追踪整个循环过程中的膨胀演化，量化累积速率。

**局部鼓包检测**：加压约束可能掩盖整体的膨胀，但局部产气引发的鼓包仍会表现为应变集中。DIC的应变场分析可以检测加压条件下的局部鼓包。

### 6.3 加压膨胀的量化指标

| 指标 | 定义 | 工程意义 |
|------|------|---------|
| 最大法向膨胀量 | 电池表面法向位移的最大值 | 壳体变形安全裕度 |
| 膨胀均匀度 | 最大膨胀量/平均膨胀量 | 约束设计合理性 |
| 膨胀中心偏移 | 膨胀中心相对几何中心的偏移 | 电极均匀性评估 |
| 面内膨胀量 | 长度/宽度方向的膨胀位移 | 模组间距设计输入 |
| 膨胀力密度 | 单位面积的膨胀力 | 紧固件设计输入 |
| 循环膨胀增量 | 单次循环的膨胀量增量 | 预测长循环累积膨胀 |

## 7. XTDIC系统在电池膨胀测量中的实施方案

### 7.1 推荐配置

| 组件 | 规格 | 说明 |
|------|------|------|
| 相机 | XTDIC-CONST-SD (5MP) | 2048×2448像素，空间分辨力0.1mm@200mm视场 |
| 镜头 | 35mm焦距 | 工作距离500-800mm |
| 照明 | LED冷光源 | 双侧45°照射，避免镜面反射 |
| 标定板 | 标准网格标定板 | 覆盖200×170mm视场 |
| 采集帧率 | 1-5fps | 准静态充放电过程 |
| 同步 | 外部触发+时间戳 | 与电池测试系统同步 |

### 7.2 测量流程

1. **电池准备**：选择待测电芯，确认初始状态（SOC、温度）。
2. **散斑制备**：在电池大面喷涂白色亚光底漆+黑色亚光散斑。
3. **安装定位**：将电池固定在测试台上，安装加压约束装置（如需要）。
4. **DIC系统架设**：安装双目相机系统，调整视场覆盖整个电池大面。
5. **系统标定**：使用标定板进行系统标定，校正环境箱视窗折射（如在箱内测试）。
6. **基准采集**：采集初始状态（SOC 0%）的基准图像。
7. **充放电测试**：按预定充放电制度执行测试，DIC全程采集图像。
8. **数据处理**：对DIC图像进行分析，计算全场三维位移和应变。
9. **结果提取**：提取最大膨胀量、膨胀分布、膨胀-时间曲线等关键指标。

### 7.3 关键参数

| 参数 | 典型值 | 说明 |
|------|--------|------|
| 测量视场 | 200×170mm | 覆盖280Ah电芯大面 |
| 空间分辨力 | 0.05-0.1mm | 取决于相机分辨率和视场 |
| 位移精度 | ≤0.01像素 | 亚像素算法 |
| 法向膨胀测量范围 | 0-10mm | 覆盖正常膨胀和异常鼓包 |
| 法向膨胀分辨力 | 2-10μm | 取决于空间分辨力和子区大小 |
| 应变精度 | 50με | SD系列 |
| 采集帧率 | 1-5fps | 准静态测试 |

## 8. 典型应用场景

### 8.1 动力电池膨胀本构关系建立

动力电池包的结构仿真需要电芯的膨胀本构关系作为输入——即在不同SOC、温度和约束条件下，电芯的膨胀力-膨胀量关系。DIC全场测量可以精确量化加压约束下的膨胀量分布，结合力传感器数据，建立膨胀本构模型。

**工程价值**：膨胀本构关系的精度直接影响电池包结构仿真的可靠性。基于DIC全场数据的本构关系，比基于单点测量的本构关系更准确地反映电芯的真实膨胀行为。

### 8.2 软包电池鼓包检测与安全预警

软包电池对产气鼓包最为敏感。DIC可以实时监测电池表面的三维形貌变化，当局部区域出现异常隆起时（应变集中超过阈值），触发安全预警。

**工程价值**：在电池安全测试中，DIC全场监测可以替代多个离散分布的位移传感器，提供更全面的鼓包检测覆盖。应变场分析可以识别鼓包的早期阶段——在肉眼可见之前即检测到应变异常。

### 8.3 电池循环寿命与膨胀累积

长循环过程中电池的膨胀量持续累积，最终可能导致电池包结构失效。DIC可以追踪数百甚至数千次循环过程中的膨胀演化，量化膨胀累积速率，预测电池包的设计寿命。

**工程价值**：膨胀累积数据是电池包维护策略（何时更换模组、何时调整预紧力）的关键输入。

### 8.4 不同化学体系膨胀行为对比

不同化学体系的电池膨胀行为差异显著：LFP电池膨胀量小（约0.1%-0.3%厚度变化）、NCM811电池膨胀量大（约0.5%-2%）、硅基负极电池膨胀量更大（可达5%以上）。DIC可以精确量化不同化学体系的膨胀差异，为电池选型和包体设计提供数据支撑。

**工程价值**：从LFP转向高镍NCM或硅负极体系时，膨胀控制是电池包设计的首要挑战。DIC数据帮助工程师在化学体系选型阶段即评估膨胀风险。

### 8.5 热失控膨胀监测

在针刺、过充等热失控触发试验中，电池表面在热失控发生前和发生过程中会产生剧烈的膨胀变形。DIC高速测量（使用XTDIC-SPARK系统，超100万fps）可以捕捉热失控过程中的瞬态膨胀行为，为理解热失控机制和开发热失控预警算法提供数据。

**工程价值**：热失控过程中的膨胀变形是热失控早期检测的潜在信号。DIC高速测量数据可以用于训练基于膨胀特征的热失控预警模型。

## 9. 实验设计与数据处理建议

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 亚光漆，散斑0.1-0.3mm，密度40%-60%，避免过度喷涂 |
| 相机配置 | 双目三维DIC，法向膨胀是核心数据 |
| 环境箱视窗 | 石英玻璃，标定时校正折射，防结露 |
| 加压装置 | 力传感器+位移约束，记录约束力变化 |
| 同步 | DIC时间戳与电池测试系统对齐 |
| 基准图像 | SOC 0%状态下采集，作为变形计算参考 |
| 数据量 | 1fps×2h≈7200帧×2相机≈144GB，需预留存储 |
| 温度控制 | 恒温或程序温控，温度波动影响膨胀测量 |
| 多循环测试 | 注意散斑耐久性，长循环后可能需重新制备 |

**入门建议**：从单颗方形铝壳电池的自由膨胀测试开始，验证DIC测量结果与传统位移传感器的一致性。确认系统精度后，逐步引入加压约束和多循环测试。

## 10. 结语

锂电池的膨胀鼓包不是"会不会发生"的问题，而是"膨胀多少、分布如何、在约束条件下如何演化"的量化问题。传统测量手段在这个问题上留下了显著的盲区——单点、接触、低时间分辨力，无法满足动力电池包结构设计对膨胀数据的精度和全面性要求。

DIC技术以其全场三维测量、非接触零干扰、高时序分辨力的特性，为锂电池膨胀研究提供了全新的技术范式。从自由膨胀形貌到加压约束行为，从正常循环累积到异常鼓包检测，从稳态膨胀本构到瞬态热失控变形，DIC正在成为电池膨胀测量领域的关键工具。

XTDIC-CONST系列凭借其5MP分辨率、50με应变精度和灵活的双目立体视觉配置，为电池膨胀测量提供了完整的解决方案。随着动力电池能量密度持续提升和化学体系不断迭代，膨胀控制的重要性将持续增加——DIC全场测量数据，将在电池包结构优化和安全设计中发挥不可替代的作用。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: Battery Swelling—The Quantification Blind Spot in Safety Assessment](#1-introduction-battery-swellingthe-quantification-blind-spot-in-safety-assessment)
- [2. Physical Mechanisms of Lithium Battery Swelling and Bulging](#2-physical-mechanisms-of-lithium-battery-swelling-and-bulging)
- [3. Limitations of Traditional Swelling Measurement Methods](#3-limitations-of-traditional-swelling-measurement-methods)
- [4. Core Advantages of DIC for Battery Swelling Measurement](#4-core-advantages-of-dic-for-battery-swelling-measurement)
- [5. Key Technical Approaches for DIC Battery Swelling Measurement](#5-key-technical-approaches-for-dic-battery-swelling-measurement)
- [6. Swelling Behavior Analysis Under Pressurized Conditions](#6-swelling-behavior-analysis-under-pressurized-conditions)
- [7. XTDIC System Implementation for Battery Swelling Measurement](#7-xtdic-system-implementation-for-battery-swelling-measurement)
- [8. Typical Application Scenarios](#8-typical-application-scenarios)
- [9. Experimental Design and Data Processing Recommendations](#9-experimental-design-and-data-processing-recommendations)
- [10. Conclusion](#10-conclusion)

---

## 1. Introduction: Battery Swelling—The Quantification Blind Spot in Safety Assessment

Lithium batteries inevitably undergo volume changes during charge-discharge cycles. In consumer electronics, the radial swelling of an 18650 cylindrical cell typically measures in tens of micrometers—seemingly negligible. However, when hundreds or thousands of cells are assembled into modules and packaged into a battery pack, micrometer-level individual swelling accumulates and couples with structural constraints to generate expansion forces sufficient to compromise pack integrity. More critically, under abnormal conditions—overcharge, high-temperature storage, internal short circuit—swelling can escalate from micrometers to millimeters, forming visible bulges that serve as precursors to thermal runaway.

The industry's understanding of battery swelling has a significant gap: engineers know swelling occurs, but few can precisely answer "how much swelling," "is the swelling distribution uniform," "which region bulges first," or "how does swelling behavior change under compressive constraints." Traditional methods—strain gauges, displacement sensors, dial gauges—either measure single points, require contact (interfering with free expansion of thin-walled casings), or cannot operate inside sealed environmental chambers. Battery swelling quantification has long remained at the stage of "measurable but incomplete."

Digital Image Correlation (DIC) technology provides a breakthrough solution. By preparing speckle patterns on battery surfaces and acquiring image sequences during charge-discharge using binocular stereo vision, DIC captures full-field 3D displacement and strain distributions—not just the swelling at one point, but the entire surface swelling topology and its evolution. When batteries are subjected to external constraint pressures, DIC further reveals the non-uniformity of swelling distribution under constraint, providing critical data for battery pack structural design and thermal management strategies.

## 2. Physical Mechanisms of Lithium Battery Swelling and Bulging

### 2.1 Normal Swelling Sources

**Electrode lithiation expansion**: Lithium ions intercalate into and deintercalate from electrode crystal lattices during cycling, causing lattice parameter changes. Graphite anodes swell approximately 10% during lithiation; silicon-based anodes can reach 300%—the core challenge for silicon anode commercialization. Cathode materials (NCM, LFP) exhibit smaller volume changes (1-5%) but remain non-negligible in high-nickel systems.

**SEI film growth**: The solid electrolyte interphase (SEI) continuously grows during initial formation and subsequent cycling, occupying additional volume. SEI thickness typically ranges from tens to hundreds of nanometers, but accumulates significantly over long cycling.

**Temperature effects**: Internal resistance causes Joule heating during cycling, and temperature increases induce thermal expansion. Battery thermal expansion coefficients are approximately 30-50×10⁻⁶/°C; a 5°C temperature rise causes 0.015%-0.025% volume change.

### 2.2 Abnormal Swelling and Bulging

**Gas generation**: Electrolyte decomposition produces gases (CO₂, H₂, C₂H₄), the most direct cause of bulging. Gas generation can be triggered by overcharge, high-temperature storage, internal short circuits, or moisture intrusion. Pouch cells are most sensitive to gas generation due to low casing rigidity—internal pressures of only tens of kPa can cause visible bulging.

**Lithium dendrite penetration**: Under high-rate charging or low-temperature conditions, lithium ions deposit on anode surfaces forming dendrites that pierce separators, causing internal short circuits with localized heating and gas generation leading to rapid swelling.

**Cathode oxygen release**: High-nickel cathodes undergo structural phase transitions under overcharge or high temperature, releasing oxygen that reacts with electrolyte to produce large volumes of gas and heat.

### 2.3 Constraint Effects on Swelling Behavior

In actual battery packs, cells do not expand freely but are constrained by module structural components and fasteners. Constraint effects on swelling behavior are bidirectional:

Constraint suppresses swelling (external pressure limits free expansion), but causes non-uniform swelling distribution (edges strongly constrained, center weakly constrained), generating additional internal stress that accelerates electrode aging and failure. Over long cycling, expansion forces accumulate continuously—without expansion absorption designs (such as elastic pads), accumulated forces may cause module deformation, fastener loosening, or even pack casing cracking.

Quantifying battery swelling behavior under constraint conditions is a core input for battery pack structural design.

## 3. Limitations of Traditional Swelling Measurement Methods

**Strain gauges**: Single-point, single-direction measurement; attachment may interfere with thin-walled casing free expansion (especially pouch cells); failure-prone in high-temperature high-humidity environmental chambers; complex multi-channel wiring.

**Displacement sensors/dial gauges**: Single-point contact measurement; local constraint on pouch cells alters true swelling distribution; large sensor footprint; difficult to install inside environmental chambers.

**Laser displacement sensors**: Non-contact single-point measurement; poor laser reflection from metallic surfaces; high cost for multi-sensor parallel measurement; cannot measure in-plane strain.

**X-ray CT**: Expensive equipment; long scan times preventing real-time monitoring; limited spatial resolution (>10μm typically); radiation may affect battery performance.

## 4. Core Advantages of DIC for Battery Swelling Measurement

### 4.1 Full-Field 3D Swelling Topography

Through binocular stereo vision configuration, DIC simultaneously captures 3D displacement fields across the entire visible battery surface. For a 280Ah LFP prismatic cell (approximately 72×200×170mm), DIC can obtain swelling distribution across the entire large face (200×170mm area) with spatial resolution of 0.05-0.1mm.

### 4.2 Non-Contact Zero Interference

DIC requires only speckle patterns on the surface—no sensor attachment or mechanical constraints. For pouch cells with aluminum-laminate film casings only 0.1-0.3mm thick, non-contact measurement is essential for obtaining true swelling data.

### 4.3 High Temporal Resolution

For battery charge-discharge processes (typical rates 0.5C-2C, single cycle 1-2 hours), even 1fps acquisition sufficiently captures swelling evolution. XTDIC-CONST series supports online synchronous acquisition at 4500fps, far exceeding battery swelling temporal resolution needs. For transient events (e.g., nail penetration triggered thermal runaway), XTDIC-SPARK provides over 1 million fps.

### 4.4 3D Deformation Separation

Battery surface swelling includes not only normal (thickness direction) displacement but also in-plane displacement (length and width expansion). DIC simultaneously measures all three displacement components, separating normal swelling from in-plane expansion for more complete mechanistic understanding.

### 4.5 Strain Field Calculation

Surface strain distributions calculated from displacement fields better reflect local deformation intensity—in gas-induced bulging regions, strain concentration may reach several times the surrounding area. Strain field data is valuable for evaluating casing material mechanical safety margins and predicting bulge crack initiation locations.

## 5. Key Technical Approaches for DIC Battery Swelling Measurement

### 5.1 Speckle Preparation

**Prismatic aluminum-shell cells**: Spray white matte base coat on smooth aluminum surface, then black matte spray for random speckle pattern. Speckle diameter 0.1-0.3mm (3-8 pixels at camera resolution), density 40%-60%.

**Pouch cells**: Aluminum-laminate film surface has adequate roughness for speckle adhesion. Avoid over-spraying—coating thickness may affect thin-walled casing swelling behavior.

**Cylindrical cells**: Curved surface speckle requires attention to uniformity; recommend rotary spraying fixtures.

### 5.2 Imaging Configuration

**Binocular stereo vision (3D DIC)**: Recommended approach. Two cameras capture battery surface from different angles, reconstructing 3D displacement fields through stereo vision. Normal swelling displacement is core data—3D DIC is mandatory.

**XTDIC-CONST-SD series** (2.3-5MP, 163-1500fps, 50με): Recommended for battery swelling measurement—5MP resolution provides approximately 0.1mm spatial resolution at 200mm field of view, 1500fps full-frame acquisition far exceeds temporal resolution needs, 50με strain precision resolves casing strain from swelling.

### 5.3 Synchronization and Data Acquisition

DIC image acquisition must synchronize with electrochemical workstation/battery test systems: time synchronization (precise timestamps aligned with charge-discharge curves), trigger synchronization (external trigger for specific events like overcharge or nail penetration), and data management (complete charge-discharge cycle at 1fps produces approximately 3600-7200 frames × 2 cameras ≈ 36-144GB).

### 5.4 Environmental Chamber Adaptation

Optical viewport on environmental chamber (tempered or quartz glass), LED cold light source to avoid additional heating, anti-condensation measures for low-temperature testing.

## 6. Swelling Behavior Analysis Under Pressurized Conditions

Pressurized swelling testing is a critical step in battery pack design. In actual packs, cells are constrained by module side plates and end plates—swelling during cycling is restricted. Quantifying swelling behavior under constraint is fundamental for determining module preload force and designing expansion absorption structures.

### 6.1 Pressurization Test Schemes

**Constant pressure constraint**: Apply constant pressure to cell sides (typically 10-50kPa), simulating elastic constraint from module side plates.

**Constant displacement constraint**: Apply fixed displacement constraint to cell sides, simulating rigid module side plates. Constraint reaction force equals expansion force.

**Gradient pressure constraint**: Apply gradient pressure across cell surface (low center, high edges), simulating actual module non-uniform constraint distribution.

### 6.2 DIC Applications in Pressurized Swelling Testing

Free vs. pressurized swelling distribution comparison, expansion force-swelling constitutive relationship establishment, cyclic swelling accumulation tracking, and local bulge detection under constraint.

### 6.3 Pressurized Swelling Quantification Metrics

| Metric | Definition | Engineering Significance |
|--------|-----------|------------------------|
| Maximum normal swelling | Maximum normal displacement on battery surface | Casing deformation safety margin |
| Swelling uniformity | Maximum swelling / average swelling | Constraint design rationality |
| Swelling center offset | Deviation of swelling center from geometric center | Electrode uniformity assessment |
| In-plane swelling | Expansion displacement in length/width directions | Module spacing design input |
| Expansion force density | Expansion force per unit area | Fastener design input |
| Cyclic swelling increment | Swelling increment per cycle | Predict long-cycle accumulated swelling |

## 7. XTDIC System Implementation for Battery Swelling Measurement

### 7.1 Recommended Configuration

| Component | Specification | Notes |
|-----------|--------------|-------|
| Camera | XTDIC-CONST-SD (5MP) | 2048×2448 pixels, 0.1mm spatial resolution @200mm FOV |
| Lens | 35mm focal length | Working distance 500-800mm |
| Lighting | LED cold light source | Dual 45° illumination, avoid specular reflection |
| Calibration board | Standard grid calibration board | Cover 200×170mm FOV |
| Acquisition rate | 1-5fps | Quasi-static charge-discharge |
| Synchronization | External trigger + timestamp | Sync with battery test system |

### 7.2 Measurement Workflow

1. Battery preparation, speckle fabrication, installation and positioning, DIC system setup, system calibration, reference acquisition (SOC 0%), charge-discharge testing with DIC acquisition, data processing, key metric extraction.

### 7.3 Key Parameters

| Parameter | Typical Value | Notes |
|-----------|--------------|-------|
| Measurement FOV | 200×170mm | Covers 280Ah cell large face |
| Spatial resolution | 0.05-0.1mm | Depends on camera resolution and FOV |
| Displacement precision | ≤0.01 pixel | Sub-pixel algorithm |
| Normal swelling range | 0-10mm | Covers normal swelling and abnormal bulging |
| Normal swelling resolution | 2-10μm | Depends on spatial resolution and subset size |
| Strain precision | 50με | SD series |
| Acquisition rate | 1-5fps | Quasi-static testing |

## 8. Typical Application Scenarios

### 8.1 Battery Expansion Constitutive Relationship Development

Battery pack structural simulation requires cell expansion constitutive relationships as input—expansion force-swelling relationships under different SOC, temperature, and constraint conditions. DIC full-field measurement precisely quantifies swelling distribution under pressurized constraints, combined with force sensor data to establish expansion constitutive models.

### 8.2 Pouch Cell Bulge Detection and Safety Warning

DIC can continuously monitor battery surface 3D topography changes. When abnormal local protrusion appears (strain concentration exceeding threshold), safety warnings can be triggered before visual bulging is apparent.

### 8.3 Cycling Life and Swelling Accumulation

DIC tracks swelling evolution over hundreds or thousands of cycles, quantifying accumulation rates and predicting pack design life.

### 8.4 Chemistry System Swelling Behavior Comparison

LFP cells swell approximately 0.1%-0.3% thickness change, NCM811 cells approximately 0.5%-2%, silicon-anode cells can exceed 5%. DIC precisely quantifies differences across chemistry systems for cell selection and pack design support.

### 8.5 Thermal Runaway Swelling Monitoring

During thermal runaway trigger tests (nail penetration, overcharge), DIC high-speed measurement (using XTDIC-SPARK system, >1M fps) captures transient swelling behavior for thermal runaway mechanism understanding and early warning algorithm development.

## 9. Experimental Design and Data Processing Recommendations

| Key Factor | Considerations |
|------------|---------------|
| Speckle preparation | Matte paint, speckle 0.1-0.3mm, density 40%-60%, avoid over-spraying |
| Camera configuration | Binocular 3D DIC, normal swelling is core data |
| Environmental chamber viewport | Quartz glass, correct refraction during calibration, anti-condensation |
| Pressurization device | Force sensor + displacement constraint, record constraint force changes |
| Synchronization | DIC timestamps aligned with battery test system |
| Reference image | Acquire at SOC 0%, serve as deformation calculation reference |
| Data volume | 1fps×2h≈7200 frames×2 cameras≈144GB, reserve storage |
| Temperature control | Constant or programmed temperature, fluctuations affect swelling measurement |
| Multi-cycle testing | Monitor speckle durability, may need re-preparation after long cycling |

**Getting Started Recommendation**: Begin with single prismatic aluminum-shell cell free-swelling testing, verify DIC measurement consistency with traditional displacement sensors, then progressively introduce pressurized constraints and multi-cycle testing.

## 10. Conclusion

Battery swelling is not a question of "whether it happens" but a quantification problem of "how much, how distributed, and how it evolves under constraint." Traditional measurement methods leave significant blind spots—single-point, contact-based, low temporal resolution—unable to meet the precision and comprehensiveness requirements of battery pack structural design for swelling data.

DIC technology, with its full-field 3D measurement, non-contact zero-interference, and high temporal resolution characteristics, provides a new technical paradigm for lithium battery swelling research. From free-swelling topography to pressurized constraint behavior, from normal cyclic accumulation to abnormal bulge detection, from steady-state expansion constitutive relationships to transient thermal runaway deformation, DIC is becoming a key tool in battery swelling measurement.

The XTDIC-CONST series, with 5MP resolution, 50με strain precision, and flexible binocular stereo vision configuration, provides a complete solution for battery swelling measurement. As battery energy density continues to increase and chemistry systems continue to evolve, the importance of swelling control will only grow—DIC full-field measurement data will play an irreplaceable role in battery pack structural optimization and safety design.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D XTDIC system documentation and lithium battery swelling measurement application notes*
