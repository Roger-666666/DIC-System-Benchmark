# 数字图像相关DIC技术在高速振动与材料疲劳场测量中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：高速振动与疲劳测量的技术背景](#1-引言高速振动与疲劳测量的技术背景)
- [2. 高速振动的物理特征与测量挑战](#2-高速振动的物理特征与测量挑战)
- [3. DIC技术应对高速振动测量的核心能力](#3-dic技术应对高速振动测量的核心能力)
- [4. 疲劳场测量的原理与应用价值](#4-疲劳场测量的原理与应用价值)
- [5. 裂纹扩展的定量表征方法](#5-裂纹扩展的定量表征方法)
- [6. XTDIC系统在振动与疲劳测试中的实施方案](#6-xtdic系统在振动与疲劳测试中的实施方案)
- [7. 典型应用领域](#7-典型应用领域)
- [8. 设备技术参数](#8-设备技术参数)
- [9. 实验设计与数据处理流程](#9-实验设计与数据处理流程)
- [10. 国产DIC设备在疲劳测试领域的发展现状](#10-国产dic设备在疲劳测试领域的发展现状)
- [11. 结语](#11-结语)

---

## 1. 引言：高速振动与疲劳测量的技术背景

高速振动与材料疲劳是现代工业中两类典型的动态力学问题，分别对应瞬态冲击载荷和循环载荷作用下的结构响应。从航空发动机叶片的共振分析到在役桥梁的疲劳裂纹监测，从汽车制动盘的摩擦振动到变压器铁芯的磁致伸缩，振动和疲劳现象贯穿于各类工程结构的全生命周期。

传统接触式测量方法在这两类问题上均存在明显局限：加速度传感器的附加质量会改变被测结构的动力学特性，单点测量无法反映全场应变分布，高温或腐蚀环境下的传感器安装更是困难重重。数字图像相关（DIC）技术以其非接触、全场、高精度的测量特性，为高速振动与疲劳场测量提供了全新的技术路径。

本文聚焦DIC技术在高速振动与材料疲劳场测量中的应用，探讨其工作原理、典型应用场景及国产设备在该领域的技术现状。

## 2. 高速振动的物理特征与测量挑战

### 2.1 高速振动的典型特征

高速振动通常指频率在数百Hz至数十kHz范围内的动态载荷响应。与静态或准静态变形不同，高速振动具有以下显著特征：

**瞬态性**：振动过程持续时间极短，从毫秒级到微秒级不等，单次激励后的响应衰减过程往往只有几十到几百个振动周期。

**高频性**：振动频率可达数千甚至数十kHz，传统的每秒百帧量级的相机无法捕捉振动过程中的位移变化细节。根据奈奎斯特采样定理，测量系统需要至少2倍于振动频率的采样率才能准确重建振动波形。

**全场性**：结构在高速振动时并非整体同步运动，高阶模态下不同区域的相位和振幅存在显著差异，单点或少数几点的测量数据无法反映完整的振型分布。

### 2.2 传统测量方法的局限性

| 方法 | 高速振动测量能力 | 主要局限 |
|------|----------------|---------|
| 加速度传感器 | 可测高频振动 | 附加质量效应，改变结构动力学特性；布线复杂，多点同步困难 |
| 激光测振仪 | 非接触高频测量 | 单点测量，扫描耗时长；光路敏感性高，不适合有遮挡的复杂结构 |
| 应变片 | 成本低，可靠性高 | 附加刚度影响；粘贴工作量大；无法获取全场数据；应变片易在循环载荷下脱粘 |
| 传统DIC | 非接触全场 | 低帧率无法捕捉kHz级振动细节 |

对于航空发动机叶片、制动盘、风电叶片等典型高速振动部件，传统方法要么引入测量干扰，要么无法获取足够的空间分辨率，要么无法满足时间分辨率要求。

## 3. DIC技术应对高速振动测量的核心能力

### 3.1 高速成像与全场位移同步获取

现代高速DIC系统通过配置帧率从数千fps到超过百万fps的高速相机，结合双目立体视觉配置，可以在单次高速事件中同步获取全场三维位移数据。相比单点测振仪的逐点扫描方式，DIC在一次采集即可获得整个视场内所有测点的位移、速度和加速度信息。

具体而言，当DIC系统以超过10万fps的帧率采集时，对于频率在5kHz以下的振动信号可以完整重建位移时程曲线。对于更高频率的振动，可以结合频闪触发技术，通过在振动周期的固定相位点采集图像，重建完整的振动响应。

### 3.2 振型识别与模态分析

通过快速傅里叶变换（FFT）对DIC测量的位移数据进行频域分析，可以识别结构的各阶固有频率和对应的振型分布。这种基于全场数据的模态分析方法相比传统的加速度传感器网络具有以下优势：

**空间分辨率高**：DIC测量点的密度可达数十万至百万量级，可以捕捉到局部振型细节和高阶模态下的节点线分布，这是传统加速度传感器网络由于测点数量限制所无法实现的。

**无附加质量影响**：非接触测量方式不改变被测结构的动力学特性，测量结果更真实反映结构在实际约束条件下的振动行为。

**振型可视化直观**：DIC可以直接输出全场振型云图和动画，帮助工程师直观理解结构的振动行为，识别应力集中区域和潜在的疲劳损伤萌生位置。

### 3.3 振动疲劳的联合测量

DIC技术在振动疲劳测试中可以将振动响应测量与疲劳损伤评估同步进行。通过分析振动载荷下结构表面应变场的演化，可以识别应变集中区域并定量评估其对疲劳寿命的影响，这对于预测结构在长期振动载荷下的可靠性具有重要价值。

## 4. 疲劳场测量的原理与应用价值

### 4.1 疲劳场的基本概念

材料在循环载荷作用下，损伤逐渐累积并最终导致断裂的现象称为疲劳。与静强度破坏不同，疲劳破坏通常发生在远低于材料屈服强度的应力水平下，且没有明显的宏观塑性变形预兆，因此具有更大的安全隐患。

疲劳过程可以分为三个阶段：裂纹萌生阶段、裂纹扩展阶段和最终断裂阶段。传统的疲劳试验主要关注应力-循环次数（S-N）曲线和疲劳极限的测定，难以直接观测裂纹萌生和扩展的微观机制。DIC技术的全场测量能力使得在试样表面直接追踪疲劳裂纹的萌生位置和扩展路径成为可能。

### 4.2 DIC全场应变分析在疲劳监测中的价值

**应变集中区域识别**：在循环载荷作用下，应变场并非均匀分布。应力集中几何特征（如孔洞、缺口、焊缝等）附近会出现显著的应变集中。DIC全场应变测量可以精确识别这些应变集中区域，而应变集中系数正是评估疲劳裂纹萌生风险的关键参数。

**低周疲劳与高周疲劳的应变测量**：根据循环次数的范围，疲劳可分为低周疲劳（循环次数通常低于10^4-10^5次，应力水平接近屈服强度，存在明显的塑性变形）和高周疲劳（循环次数高达10^5-10^7次，应力水平低于屈服强度，塑性变形可忽略）。DIC测量的应变范围覆盖0.005%至2000%，可以同时满足两类疲劳测试的需求。

**滞后回线的精确测定**：在循环载荷作用下，材料的应力-应变曲线会形成滞后回线，其面积代表每次循环的能量耗散。DIC通过全场应变测量可以获得整个试样表面的滞后回线分布，帮助理解疲劳损伤的空间演化规律。

### 4.3 早期裂纹的精确检测

传统方法如目视检查或单点应变片难以捕捉微米级的早期裂纹萌生。DIC通过全场应变分析可以识别局部应变异常区域，这些应变异常往往是裂纹萌生的前兆。通过在疲劳试验过程中持续监测应变场的演化，可以实现对裂纹萌生时刻和位置的精确捕捉。

## 5. 裂纹扩展的定量表征方法

### 5.1 裂纹扩展速率的测量

在疲劳裂纹扩展阶段，裂纹长度随循环次数的增加而逐渐增大。裂纹扩展速率（da/dN，即每次载荷循环中裂纹长度的增加量）是评估材料疲劳裂纹扩展抗力和预测构件剩余寿命的关键参数。

DIC技术在裂纹扩展测量中具有独特优势：通过追踪裂纹尖端附近区域的应变场演化，可以精确确定裂纹尖端位置随循环次数的变化；通过全场应变数据，可以获得裂纹尖端的张开位移（CTOD）和裂纹尖端塑性区形态，为断裂力学分析提供实验依据。

### 5.2 Paris定律与DIC数据的关系

疲劳裂纹扩展速率与裂纹尖端应力强度因子幅值（ΔK）之间存在经典的Paris幂律关系：

da/dN = C·(ΔK)^m

其中C和m为材料常数。该定律描述了裂纹扩展的第II阶段——稳定扩展阶段的规律。DIC测量可以提供裂纹长度a随循环次数N的变化数据，通过微分处理得到da/dN，再结合有限元分析或经验公式计算ΔK，即可建立裂纹扩展的实验数据库。

### 5.3 裂纹扩展路径的三维表征

对于复杂载荷条件下的裂纹扩展问题，裂纹路径往往不是平直的，而是呈现三维空间中的弯曲和分叉特征。三维DIC系统可以完整记录裂纹扩展过程中裂纹尖端的三维轨迹，这对于理解多轴载荷下的断裂机理和评估结构安全性具有重要意义。

## 6. XTDIC系统在振动与疲劳测试中的实施方案

### 6.1 系统配置方案

XTDIC数字图像相关测量系统在高速振动与疲劳测试中的典型配置包括三个系列，分别针对不同的测试需求：

**XTDIC-CONST-SD系列**：标准型配置，230万至500万像素，帧率163至1500fps，应变精度50με。适用于振动频率在数百Hz范围内的通用振动测试和疲劳试验，性价比较高，适合常规材料疲劳性能评价。

**XTDIC-CONST-HR系列**：高分辨率型配置，最高2500万像素，帧率30至42fps，应变精度20με。适用于需要高空间分辨率的疲劳裂纹扩展精细观测和高阶模态振型分析，像素级分辨率可以捕捉更微观的应变场细节。

**XTDIC-CONST-HS系列**：超高速型配置，400万像素，帧率超过10万fps，应变精度50με。采用专用高速相机，帧率覆盖10万至百万fps量级，专为高速振动响应、冲击载荷下的瞬态变形以及高频疲劳试验设计。

**XTDIC-STROBE系列**：三维高速动态测量系统，支持Phantom、IDT等多品牌高速相机，帧率可达百万fps以上。6DoF轨迹姿态测量功能可以同时追踪结构的空间运动和姿态变化，适用于碰撞、跌落、旋转等复杂高速动力学场景。

### 6.2 频闪触发测量模式

对于频率在数kHz以上的稳态振动测试，直接依靠相机的最高帧率往往难以满足采样要求。XTDIC系统支持频闪触发测量模式，通过外触发信号在振动周期的固定相位点触发相机采集图像，多次采集后重建完整的位移时程。

这种频闪测量模式的优点在于：不依赖相机的超高帧率，普通的数千fps相机即可测量数十kHz的振动；相位触发精度高，可以精确重建振动的波形；多次测量累加可以有效降低随机噪声的影响。

### 6.3 疲劳试验机的同步集成

XTDIC系统支持与各类疲劳试验机的同步集成。通过读取试验机的载荷信号和位移信号，可以建立DIC全场应变数据与试验机加载条件之间的精确对应关系。这种同步数据对于分析应力-应变迟滞回线、评估循环硬化/软化行为、研究载荷顺序效应等疲劳力学问题至关重要。

## 7. 典型应用领域

### 7.1 航空发动机领域

航空发动机叶片、轮盘和机匣等关键部件在高速旋转过程中承受着复杂的振动载荷。DIC技术可以非接触式测量叶片在旋转状态下的振动响应，识别叶片与轮盘之间的模态耦合特征，评估叶片在气流激振力作用下的疲劳风险。对于发动机冷端部件的振动测试，可以结合高速DIC获取叶片在开机、加速、减速过程中的瞬态振动模态。

### 7.2 汽车制动系统

汽车制动盘和制动摩擦片在制动过程中承受高频摩擦振动和热疲劳载荷。DIC可以测量制动过程中制动盘表面的温度场和应变场演化，分析热力耦合作用下的裂纹萌生机制。对于制动卡钳的疲劳测试，可以利用DIC全场测量识别活塞密封圈的回弹特性和卡钳本体的疲劳变形模式。

### 7.3 电力变压器与电气设备

变压器铁芯在交变磁场作用下会产生磁致伸缩振动，长期运行可能导致铁芯紧固件松动和绝缘老化。DIC技术可以对运行中的变压器外壳振动进行非接触测量，结合频域分析识别特征频率，为变压器状态监测和剩余寿命评估提供数据支撑。

### 7.4 桥梁与土木结构

桥梁钢结构在车辆荷载、风荷载和地震作用下的疲劳问题直接关系结构安全。DIC可以测量桥梁关键节点和焊缝区域在循环载荷下的应变场演化，识别疲劳裂纹的萌生位置和扩展路径，为桥梁的预防性维护提供科学依据。

### 7.5 新能源电池

新能源汽车电池包在碰撞和振动工况下的结构完整性是其安全设计的关键。DIC可以测量电池包在振动台架试验中的全场应变响应，识别模态振型和振动节点分布，优化电池包的固定和防护设计。

## 8. 设备技术参数

### 8.1 XTDIC-CONST系列核心规格

| 型号 | 分辨率 | 帧率 | 应变精度 | 典型应用 |
|------|--------|------|---------|---------|
| CONST-SD | 2.3–5MP | 163–1500fps | 50με | 通用振动与疲劳测试 |
| CONST-HR | ≤25MP | 30–42fps | 20με | 高分辨率疲劳裂纹观测 |
| CONST-HS | 4MP | >100,000fps | 50με | 超高速振动与冲击 |

### 8.2 XTDIC-STROBE规格

| 参数 | 规格 |
|------|------|
| 帧率范围 | 30fps至百万fps以上 |
| 分辨率 | 1920×1440像素 |
| 测量维度 | 三维双目/三目立体视觉 |
| 轨迹测量 | 6DoF轨迹姿态测量 |
| 触发同步 | 支持外触发和频闪触发 |
| 高速相机兼容 | Phantom、IDT等多品牌 |

### 8.3 通用技术指标

**应变测量范围**：0.005%至2000%，覆盖低周疲劳和高周疲劳的全程应变范围。

**位移测量精度**：≤0.01像素，结合亚像素算法实现亚微米级的位移分辨能力。

**测量幅面**：50mm至10m，通过镜头配置灵活适应不同尺寸的试件和结构。

**数据输出**：支持实时UDP输出，可与试验机控制系统和数采系统集成。

**软件功能**：包含位移场/应变场计算、FFT频域分析、ODS振型显示、疲劳裂纹追踪、应变集中系数计算等功能模块。

## 9. 实验设计与数据处理流程

### 9.1 散斑制备

散斑质量是DIC测量精度的基础。振动与疲劳测试中的散斑制备应满足以下要求：散斑图案具有足够的对比度和随机性；散斑粒径与子区尺寸相匹配；散斑层在循环载荷下不发生脱落或开裂；对于高速振动测试，散斑还应具有足够的附着强度以承受惯性载荷而不产生相对滑动。

常用的散斑制备方法包括喷漆法（亚光白漆+亚光黑漆）、标记法和光刻法。对于金属试件，表面预处理（除油、打磨）和底漆涂覆是保证散斑附着可靠性的关键步骤。

### 9.2 相机标定

DIC系统的测量精度依赖于相机标定的准确性。在振动与疲劳测试中，由于测试周期较长，应在测试开始前和结束后分别进行标定，以监测标定参数是否发生漂移。对于高精度要求的测试，建议在测试过程中每4至8小时进行一次标定复核。

### 9.3 数据处理与分析

DIC测量得到的是随时间变化的全场位移和应变数据序列。典型的处理流程包括：

**时域分析**：提取指定测点的位移和应变时程曲线，计算峰值、均值、均方根值等统计参数。

**频域分析**：对位移数据进行FFT变换，获得频谱分布，识别各阶固有频率和对应的振型。

**疲劳参数提取**：对于疲劳试验数据，提取每次循环的应变幅值、应变均值，计算应变集中系数，追踪应变集中区域的演化。

**裂纹表征**：在检测到应变异常后，启动裂纹追踪算法，提取裂纹长度、裂纹尖端张开位移等断裂力学参数。

## 10. 国产DIC设备在疲劳测试领域的发展现状

### 10.1 技术进展

国内DIC技术在疲劳测试领域的应用已从早期的原理验证阶段进入工程实用化阶段。以XTDIC为代表的国产DIC系统在高帧率硬件集成、频闪触发同步、疲劳裂纹追踪算法等方面持续迭代改进，整体性能指标逐步接近国际主流产品水平。

在应变测量精度方面，国产高端型号已可实现20με的应变精度，与GOM ARAMIS等进口产品的标称指标处于同一量级。在测量幅面范围上，国产设备的覆盖范围从毫米级微观试件到10米级大型结构，适应性更广。

### 10.2 应用生态建设

国产DIC厂商在应用技术服务和行业解决方案方面的建设日趋完善。设备供应之外，还包括散斑制备工艺培训、测试方案设计咨询、数据分析和软件二次开发支持等服务。这种应用生态的完善有效降低了用户的使用门槛，推动了DIC技术在疲劳测试领域的普及。

### 10.3 发展方向

国产DIC设备在疲劳测试领域的后续发展重点可能集中在：更高帧率的超高速相机集成；基于深度学习的裂纹自动识别和追踪算法；DIC与红外热成像、声发射等多模态传感技术的融合测量；以及面向工业现场的便携式和在线监测型DIC系统。

## 11. 结语

高速振动与材料疲劳是工程结构可靠性评估中不可回避的两类核心问题，其测量方法直接影响结构安全设计的准确性和经济性。数字图像相关DIC技术以其非接触、全场、高精度、多维度的测量能力，为这两类问题提供了一套完整的光学测量解决方案。

从航空发动机叶片的高频振动模态分析到桥梁钢结构焊缝的疲劳裂纹追踪，从变压器铁芯的振动监测到新能源汽车电池包的碰撞响应测量，DIC技术的应用场景持续拓展。随着高速相机硬件性能的不断提升和DIC分析算法的持续优化，该技术在工程疲劳领域的渗透率有望进一步提高。

对于从事结构疲劳研究的科研人员和负责在役结构完整性评估的工程技术人员而言，建立DIC测量能力将是提升实验表征水平的重要方向。国产DIC设备的持续进步也为更多用户提供了高性价比的选择空间。

---

</details>

---

<a id="english-version"></a>

<details>
<summary><b>🇺🇸 Click to Expand: English Version</b></summary>

# Digital Image Correlation (DIC) Technology in High-Speed Vibration and Material Fatigue Field Measurement

> [!TIP]
> **Language / 请选择语言:** [中文版](#chinese-version)

## Table of Contents

- [1. Introduction: Technical Background of High-Speed Vibration and Fatigue Measurement](#1-introduction-technical-background-of-high-speed-vibration-and-fatigue-measurement)
- [2. Physical Characteristics and Measurement Challenges of High-Speed Vibration](#2-physical-characteristics-and-measurement-challenges-of-high-speed-vibration)
- [3. Core Capabilities of DIC Technology for High-Speed Vibration Measurement](#3-core-capabilities-of-dic-technology-for-high-speed-vibration-measurement)
- [4. Principles and Application Value of Fatigue Field Measurement](#4-principles-and-application-value-of-fatigue-field-measurement)
- [5. Quantitative Characterization of Crack Propagation](#5-quantitative-characterization-of-crack-propagation)
- [6. XTDIC System Implementation for Vibration and Fatigue Testing](#6-xtdic-system-implementation-for-vibration-and-fatigue-testing)
- [7. Typical Application Domains](#7-typical-application-domains)
- [8. Technical Specifications](#8-technical-specifications)
- [9. Experimental Design and Data Processing Workflow](#9-experimental-design-and-data-processing-workflow)
- [10. Development Status of Domestic DIC Equipment in Fatigue Testing](#10-development-status-of-domestic-dic-equipment-in-fatigue-testing)
- [11. Conclusion](#11-conclusion)

---

## 1. Introduction: Technical Background of High-Speed Vibration and Fatigue Measurement

High-speed vibration and material fatigue represent two categories of dynamic mechanical problems in modern industry, corresponding respectively to structural responses under transient impact loads and cyclic loading conditions. From resonance analysis of aerospace engine blades to fatigue crack monitoring of in-service bridges, from friction vibration of automotive brake discs to magnetostriction of transformer cores, vibration and fatigue phenomena permeate the entire life cycle of various engineering structures.

Traditional contact measurement methods have significant limitations for both problem categories: accelerometers' added mass alters the dynamic characteristics of structures under test, single-point measurements cannot capture full-field strain distributions, and sensor installation in high-temperature or corrosive environments is extremely challenging. Digital Image Correlation (DIC) technology, with its non-contact, full-field, and high-precision measurement characteristics, provides an entirely new technical pathway for high-speed vibration and fatigue field measurement.

This article focuses on the application of DIC technology in high-speed vibration and material fatigue field measurement, exploring its working principles, typical application scenarios, and the current technical status of domestic equipment in this field.

## 2. Physical Characteristics and Measurement Challenges of High-Speed Vibration

### 2.1 Typical Characteristics of High-Speed Vibration

High-speed vibration typically refers to dynamic load responses in the frequency range from hundreds of Hz to tens of kHz. Unlike static or quasi-static deformation, high-speed vibration exhibits the following distinctive characteristics:

**Transience**: Vibration processes have extremely short durations, ranging from milliseconds to microseconds. The response decay after a single excitation often contains only dozens to hundreds of vibration cycles.

**High Frequency**: Vibration frequencies can reach several thousand to tens of kHz. Conventional cameras with frame rates in the hundreds of fps range cannot capture displacement variation details during vibration. According to the Nyquist sampling theorem, a measurement system requires at least twice the vibration frequency in sampling rate to accurately reconstruct vibration waveforms.

**Full-Field Nature**: During high-speed vibration, structures do not move synchronously as a whole. Under higher-order modes, different regions exhibit significant phase and amplitude variations. Single-point or a few-point measurement data cannot reflect complete mode shape distributions.

### 2.2 Limitations of Traditional Measurement Methods

| Method | High-Speed Vibration Capability | Main Limitations |
|--------|------------------------------|-----------------|
| Accelerometer | Can measure high-frequency vibration | Added mass effect alters structural dynamics; complex wiring; difficult multi-point synchronization |
| Laser Doppler Vibrometer | Non-contact high-frequency measurement | Single-point measurement; time-consuming scanning; high optical path sensitivity; unsuitable for complex structures with obstructions |
| Strain Gauge | Low cost, high reliability | Added stiffness influence; labor-intensive installation; cannot obtain full-field data; strain gauges easily debond under cyclic loading |
| Conventional DIC | Non-contact full-field | Low frame rates cannot capture kHz-level vibration details |

For typical high-speed vibration components such as aerospace engine blades, brake discs, and wind turbine blades, traditional methods either introduce measurement interference, cannot provide sufficient spatial resolution, or cannot meet temporal resolution requirements.

## 3. Core Capabilities of DIC Technology for High-Speed Vibration Measurement

### 3.1 High-Speed Imaging with Synchronous Full-Field Displacement Acquisition

Modern high-speed DIC systems, configured with high-speed cameras ranging from thousands of fps to over one million fps combined with binocular stereo vision setups, can synchronously acquire full-field 3D displacement data during a single high-speed event. Compared to the point-by-point scanning approach of single-point vibrometers, DIC obtains displacement, velocity, and acceleration information for all measurement points across the entire field of view in a single acquisition.

Specifically, when a DIC system acquires at frame rates exceeding 100,000 fps, it can completely reconstruct displacement time-history curves for vibration signals below 5 kHz. For higher-frequency vibrations, strobe triggering techniques can be employed to capture images at fixed phase points in the vibration cycle, thereby reconstructing the complete vibration response.

### 3.2 Mode Shape Identification and Modal Analysis

By performing Fast Fourier Transform (FFT) on DIC-measured displacement data, the various natural frequencies and corresponding mode shapes of a structure can be identified through frequency domain analysis. This full-field data-based modal analysis method offers the following advantages over traditional accelerometer networks:

**High Spatial Resolution**: DIC measurement point density can reach hundreds of thousands to millions of points, enabling capture of local mode shape details and node line distributions under higher-order modes — something traditional accelerometer networks cannot achieve due to measurement point count limitations.

**No Added Mass Effect**: Non-contact measurement does not alter the dynamic characteristics of the structure under test. Measurement results more authentically reflect the actual vibration behavior of the structure under real boundary conditions.

**Intuitive Mode Shape Visualization**: DIC can directly output full-field mode shape contour plots and animations, helping engineers intuitively understand structural vibration behavior and identify stress concentration regions and potential fatigue damage initiation locations.

### 3.3 Combined Vibration Fatigue Measurement

DIC technology enables synchronous vibration response measurement and fatigue damage assessment during vibration fatigue tests. By analyzing the evolution of surface strain fields under cyclic loading, strain concentration regions can be identified and their impact on fatigue life quantitatively evaluated. This is critically valuable for predicting structural reliability under long-term vibration loading.

## 4. Principles and Application Value of Fatigue Field Measurement

### 4.1 Basic Concepts of Fatigue Fields

Fatigue refers to the phenomenon where materials gradually accumulate damage under cyclic loading and eventually fracture. Unlike static strength failure, fatigue failure typically occurs at stress levels far below the material's yield strength without obvious macroscopic plastic deformation precursors, posing greater safety hazards.

The fatigue process can be divided into three stages: crack initiation, crack propagation, and final fracture. Traditional fatigue tests primarily focus on stress-cycle (S-N) curves and fatigue limit determination, making it difficult to directly observe crack initiation and propagation mechanisms at the microscopic level. The full-field measurement capability of DIC technology makes it possible to directly track fatigue crack initiation locations and propagation paths on specimen surfaces.

### 4.2 Value of DIC Full-Field Strain Analysis in Fatigue Monitoring

**Strain Concentration Region Identification**: Under cyclic loading, strain fields are not uniformly distributed. Significant strain concentrations appear near stress concentration geometric features (such as holes, notches, welds, etc.). DIC full-field strain measurement can precisely identify these strain concentration regions, and the strain concentration factor is a key parameter for assessing fatigue crack initiation risk.

**Low-Cycle and High-Cycle Fatigue Strain Measurement**: Based on cycle count ranges, fatigue can be classified as low-cycle fatigue (typically below 10^4-10^5 cycles, stress levels near yield strength with obvious plastic deformation) and high-cycle fatigue (up to 10^5-10^7 cycles, stress levels below yield strength with negligible plastic deformation). DIC-measured strain ranges covering 0.005% to 2000% can simultaneously meet the requirements of both fatigue test categories.

**Precise Hysteresis Loop Measurement**: Under cyclic loading, material stress-strain curves form hysteresis loops whose area represents energy dissipation per cycle. DIC obtains hysteresis loop distributions across entire specimen surfaces through full-field strain measurement, helping understand spatial evolution patterns of fatigue damage.

### 4.3 Precise Detection of Early-Stage Cracks

Traditional methods such as visual inspection or single-point strain gauges struggle to capture micron-scale early crack initiation. DIC, through full-field strain analysis, can identify local strain anomaly regions that often serve as precursors to crack initiation. By continuously monitoring strain field evolution during fatigue tests, precise capture of crack initiation timing and location becomes possible.

## 5. Quantitative Characterization of Crack Propagation

### 5.1 Crack Growth Rate Measurement

During the fatigue crack propagation stage, crack length gradually increases with the number of cycles. The crack growth rate (da/dN — the increase in crack length per loading cycle) is a key parameter for evaluating material fatigue crack propagation resistance and predicting component residual life.

DIC technology offers unique advantages in crack propagation measurement: by tracking strain field evolution near the crack tip region over cycles, crack tip position changes can be precisely determined; through full-field strain data, crack tip opening displacement (CTOD) and crack tip plastic zone morphology can be obtained, providing experimental basis for fracture mechanics analysis.

### 5.2 Relationship Between Paris Law and DIC Data

A classical Paris power-law relationship exists between fatigue crack growth rate and crack tip stress intensity factor range (ΔK):

da/dN = C·(ΔK)^m

where C and m are material constants. This law describes the Stage II — stable crack propagation regime. DIC measurements provide crack length a as a function of cycle count N. By differentiation, da/dN is obtained; combined with finite element analysis or empirical formulas to calculate ΔK, experimental databases for crack propagation can be established.

### 5.3 Three-Dimensional Characterization of Crack Propagation Paths

For crack propagation under complex loading conditions, crack paths are often not straight but exhibit three-dimensional curvature and branching features. Three-dimensional DIC systems can completely record the 3D trajectory of crack tips during propagation, which is of great significance for understanding fracture mechanisms under multi-axial loading and assessing structural safety.

## 6. XTDIC System Implementation for Vibration and Fatigue Testing

### 6.1 System Configuration Options

Typical configurations of the XTDIC Digital Image Correlation measurement system for high-speed vibration and fatigue testing include three series, each targeting different testing requirements:

**XTDIC-CONST-SD Series**: Standard configuration, 2.3 to 5 megapixels, 163 to 1500 fps, 50 με strain accuracy. Suitable for general-purpose vibration testing and fatigue tests with vibration frequencies in the hundreds of Hz range. Cost-effective, ideal for routine material fatigue performance evaluation.

**XTDIC-CONST-HR Series**: High-resolution configuration, up to 25 megapixels, 30 to 42 fps, 20 με strain accuracy. Suitable for fine observation of fatigue crack propagation requiring high spatial resolution and high-order modal analysis. Pixel-level resolution captures more microscopic strain field details.

**XTDIC-CONST-HS Series**: Ultra-high-speed configuration, 4 megapixels, exceeding 100,000 fps, 50 με strain accuracy. Employing dedicated high-speed cameras with frame rates covering the 100,000 to 1,000,000+ fps range. Specifically designed for high-speed vibration response, transient deformation under impact loading, and high-frequency fatigue testing.

**XTDIC-STROBE Series**: 3D high-speed dynamic measurement system supporting multiple high-speed camera brands (Phantom, IDT, etc.) with frame rates exceeding 1,000,000 fps. 6DoF trajectory and attitude measurement capability simultaneously tracks structural spatial motion and attitude changes. Suitable for complex high-speed dynamics scenarios including collision, drop, and rotation.

### 6.2 Strobe Trigger Measurement Mode

For steady-state vibration testing with frequencies above several kHz, relying solely on camera maximum frame rates often cannot meet sampling requirements. The XTDIC system supports strobe trigger measurement mode, triggering camera acquisition at fixed phase points in the vibration cycle through external trigger signals, reconstructing complete displacement time histories through multiple acquisitions.

Advantages of this strobe measurement mode include: does not depend on ultra-high camera frame rates; ordinary cameras rated at thousands of fps can measure vibrations at tens of kHz; phase triggering precision is high, enabling accurate waveform reconstruction; multiple measurement accumulation effectively reduces random noise.

### 6.3 Synchronization Integration with Fatigue Testing Machines

The XTDIC system supports synchronized integration with various fatigue testing machines. By reading load and displacement signals from testing machines, precise correspondence between DIC full-field strain data and testing machine loading conditions is established. This synchronized data is critical for analyzing stress-strain hysteresis loops, evaluating cyclic hardening/softening behavior, and studying load sequence effects in fatigue mechanics.

## 7. Typical Application Domains

### 7.1 Aerospace Engine Field

Key components such as aerospace engine blades, disks, and casings bear complex vibration loads during high-speed rotation. DIC technology enables non-contact measurement of blade vibration response during operation, identifying modal coupling characteristics between blades and disks, and evaluating fatigue risk under aerodynamic excitation forces. For cold-section component vibration tests, high-speed DIC combined with blade transient vibration modal data during startup, acceleration, and deceleration provides comprehensive analysis.

### 7.2 Automotive Braking Systems

Automotive brake discs and friction pads bear high-frequency friction vibration and thermal fatigue loads during braking. DIC can measure temperature field and strain field evolution on brake disc surfaces during braking, analyzing crack initiation mechanisms under thermo-mechanical coupling. For brake caliper fatigue tests, DIC full-field measurement identifies piston seal ring rebound characteristics and caliper body fatigue deformation patterns.

### 7.3 Power Transformers and Electrical Equipment

Transformer cores generate magnetostriction vibration under alternating magnetic fields. Long-term operation may lead to core fastener loosening and insulation aging. DIC technology enables non-contact measurement of operating transformer housing vibration, identifying characteristic frequencies through frequency domain analysis, providing data support for transformer condition monitoring and residual life assessment.

### 7.4 Bridges and Civil Structures

Fatigue in bridge steel structures under vehicle loads, wind loads, and seismic action directly affects structural safety. DIC can measure strain field evolution at key bridge joints and weld regions under cyclic loading, identifying fatigue crack initiation locations and propagation paths, providing scientific basis for bridge preventive maintenance.

### 7.5 New Energy Batteries

Structural integrity of electric vehicle battery packs under collision and vibration conditions is critical to safety design. DIC can measure full-field strain response of battery packs during vibration bench tests, identifying modal振型 and vibration node distributions, optimizing battery pack fixation and protection design.

## 8. Technical Specifications

### 8.1 XTDIC-CONST Series Core Specifications

| Model | Resolution | Frame Rate | Strain Accuracy | Typical Application |
|-------|-----------|-----------|----------------|-------------------|
| CONST-SD | 2.3–5MP | 163–1500fps | 50με | General-purpose vibration and fatigue testing |
| CONST-HR | ≤25MP | 30–42fps | 20με | High-resolution fatigue crack observation |
| CONST-HS | 4MP | >100,000fps | 50με | Ultra-high-speed vibration and impact |

### 8.2 XTDIC-STROBE Specifications

| Parameter | Specification |
|-----------|--------------|
| Frame Rate Range | 30fps to >1,000,000fps |
| Resolution | 1920×1440 pixels |
| Measurement Dimension | 3D binocular/trinocular stereo vision |
| Trajectory Measurement | 6DoF trajectory and attitude |
| Trigger Sync | External trigger and strobe trigger support |
| High-Speed Camera Compatibility | Phantom, IDT, and other major brands |

### 8.3 Universal Technical Specifications

**Strain Measurement Range**: 0.005% to 2000%, covering the full range from low-cycle to high-cycle fatigue.

**Displacement Measurement Precision**: ≤0.01 pixels, achieving sub-micron displacement resolution through sub-pixel algorithms.

**Measurement Field of View**: 50mm to 10m, flexibly adapting to specimens and structures of different sizes through lens configuration.

**Data Output**: Real-time UDP output support, integrable with testing machine control systems and data acquisition systems.

**Software Functions**: Includes displacement/strain field calculation, FFT frequency domain analysis, ODS mode shape display, fatigue crack tracking, strain concentration factor calculation, and other functional modules.

## 9. Experimental Design and Data Processing Workflow

### 9.1 Speckle Preparation

Speckle quality is fundamental to DIC measurement accuracy. Speckle preparation for vibration and fatigue testing should meet the following requirements: speckle patterns must have sufficient contrast and randomness; speckle particle size must match subset size; speckle layer must not debond or crack under cyclic loading; for high-speed vibration tests, speckles must have sufficient adhesion strength to withstand inertial loads without relative sliding.

Common speckle preparation methods include spray painting (matte white + matte black paint), marking methods, and lithography. For metal specimens, surface pretreatment (degreasing, grinding) and primer coating are critical for ensuring speckle adhesion reliability.

### 9.2 Camera Calibration

DIC system measurement accuracy depends on camera calibration accuracy. Since fatigue tests involve long testing durations, calibration should be performed before and after each test to monitor calibration parameter drift. For high-precision requirements, calibration verification every 4 to 8 hours during testing is recommended.

### 9.3 Data Processing and Analysis

DIC measurements yield time-varying full-field displacement and strain data sequences. A typical processing workflow includes:

**Time Domain Analysis**: Extract displacement and strain time-history curves for specified measurement points, calculate statistical parameters including peak values, mean values, and root mean square values.

**Frequency Domain Analysis**: Perform FFT on displacement data to obtain frequency spectrum distributions, identifying various natural frequencies and corresponding mode shapes.

**Fatigue Parameter Extraction**: For fatigue test data, extract strain amplitude and mean strain for each cycle, calculate strain concentration factors, and track evolution of strain concentration regions.

**Crack Characterization**: Upon detecting strain anomalies, initiate crack tracking algorithms to extract fracture mechanics parameters including crack length and crack tip opening displacement.

## 10. Development Status of Domestic DIC Equipment in Fatigue Testing

### 10.1 Technical Progress

Domestic DIC technology application in fatigue testing has progressed from early-stage principle verification to engineering practicalization. Represented by XTDIC, domestic DIC systems continue iterative improvements in high frame-rate hardware integration, strobe trigger synchronization, and fatigue crack tracking algorithms, with overall performance indicators gradually approaching international mainstream product levels.

In strain measurement accuracy, domestic high-end models can achieve 20 με strain accuracy, on par with nominal specifications of imported products such as GOM ARAMIS. In measurement field of view range, domestic equipment coverage spans from millimeter-scale micro-specimens to 10-meter-scale large structures, offering broader adaptability.

### 10.2 Application Ecosystem Building

Domestic DIC manufacturers' construction of application technical services and industry solutions continues to mature. Beyond equipment supply, services include speckle preparation process training, testing scheme design consultation, data analysis and software customization support, effectively lowering user barriers and promoting DIC technology adoption in fatigue testing.

### 10.3 Development Directions

Future development priorities for domestic DIC equipment in fatigue testing may focus on: ultra-high-speed camera integration at higher frame rates; deep learning-based automatic crack identification and tracking algorithms; fused measurement combining DIC with infrared thermography, acoustic emission, and other multi-modal sensing technologies; and portable and online monitoring-type DIC systems for industrial field deployment.

## 11. Conclusion

High-speed vibration and material fatigue are two core issues in engineering structural reliability assessment that cannot be avoided, and their measurement methods directly impact the accuracy and economy of structural safety design. Digital Image Correlation (DIC) technology, with its non-contact, full-field, high-precision, and multi-dimensional measurement capabilities, provides a comprehensive optical measurement solution for both problem categories.

From high-frequency vibration modal analysis of aerospace engine blades to fatigue crack tracking of bridge steel structure welds, from transformer core vibration monitoring to electric vehicle battery pack collision response measurement, DIC technology application scenarios continue to expand. As high-speed camera hardware performance continuously improves and DIC analysis algorithms continue to optimize, technology penetration in engineering fatigue applications is expected to further increase.

For researchers engaged in structural fatigue studies and engineering technicians responsible for in-service structural integrity assessment, establishing DIC measurement capabilities represents an important direction for enhancing experimental characterization levels. The continuous progress of domestic DIC equipment also provides broader access for more users through cost-effective options.

---

</details>

---

*Published in DIC-System-Benchmark*  
*Reference: XTOP3D high-speed vibration and fatigue DIC application documentation*
