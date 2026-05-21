# DIC技术用于模拟火车过弯动载下铁轨及固定装置变形位移监测

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：铁路轨道动态变形监测的工程需求](#1-引言铁路轨道动态变形监测的工程需求)
- [2. 列车过弯动载下的轨道结构力学特征](#2-列车过弯动载下的轨道结构力学特征)
- [3. 传统轨道监测方法的局限](#3-传统轨道监测方法的局限)
- [4. DIC技术在轨道动态变形测量中的核心能力](#4-dic技术在轨道动态变形测量中的核心能力)
- [5. 轨道结构各组件的变形测量需求](#5-轨道结构各组件的变形测量需求)
- [6. XTDIC系统在轨道变形监测中的实施方案](#6-xtdic系统在轨道变形监测中的实施方案)
- [7. 模拟过弯动载实验设计](#7-模拟过弯动载实验设计)
- [8. 设备技术参数](#8-设备技术参数)
- [9. 典型应用场景](#9-典型应用场景)
- [10. 国产DIC在轨道交通监测领域的发展](#10-国产dic在轨道交通监测领域的发展)
- [11. 结语](#11-结语)

---

## 1. 引言：铁路轨道动态变形监测的工程需求

铁路是国家交通运输的大动脉。截至2025年底，我国铁路运营里程已突破16万公里，其中高速铁路超过4.6万公里，均居世界第一。随着列车运行速度的不断提高和轴重的持续增加，轨道结构在列车动载作用下的变形与稳定性问题日益突出。

列车在运行过程中对轨道施加的载荷是动态的、多维的。除了基本的竖向轮载外，列车过弯时产生的离心力会导致轨道横向位移加剧；制动和牵引过程中产生的纵向力会推动钢轨爬行；轮轨之间的冲击振动则会在轨枕和道床中传递衰减。这些力共同作用于轨道结构——由钢轨、扣件、轨枕、道床和路基组成的复杂力学体系——使各组件产生耦合变形。

传统的轨道变形监测方法以接触式传感器和人工巡检为主，存在测点稀疏、实时性差、受列车运行干扰大等固有局限。数字图像相关（DIC）技术作为一种非接触式全场光学测量手段，为轨道结构的动态变形监测提供了全新的实验手段。通过追踪轨道表面散斑图案在列车动载作用下的变形过程，DIC可以在不干扰轨道结构的前提下，同步获取全场三维位移数据和应变分布，将轨道动态变形这一复杂的力学过程以可视化数据的方式完整记录下来。

## 2. 列车过弯动载下的轨道结构力学特征

### 2.1 过弯工况下的受力分析

列车通过曲线段时，轨道结构的受力状态与直线段有本质区别。最主要的附加载荷是离心力——列车以速度v通过半径为R的曲线时，产生的离心加速度为v²/R。对于时速250km/h的高速列车通过半径为3000m的曲线，离心加速度可达约1.6m/s²，相当于在横向施加了约16%的重力加速度分量。

这一横向力通过轮轨接触面传递至钢轨，再经扣件系统传递至轨枕和道床。在直线上主要承受竖向力的轨道结构，在曲线上需要同时抵抗横向位移和扭转。外轨承受的横向力最大，是曲线段轨道结构设计的控制工况。

### 2.2 轨道结构的变形模式

在列车过弯动载作用下，轨道结构的变形可分为以下几个层次：

**钢轨横向位移**：车轮横向推力使钢轨产生横向弯曲变形，外轨向曲线外侧偏移。对于60kg/m钢轨，在标准扣件间距（约600mm）条件下，单轮横向力作用下的钢轨横向位移可达0.5-2mm量级。

**扣件系统变形**：扣件是钢轨与轨枕之间的弹性联结部件，在横向力作用下产生弹性变形。扣件的横向刚度（一般为10-40kN/mm）直接决定了钢轨横向位移的大小——刚度越小，位移越大，但过小的刚度会导致轨道几何形位难以保持。

**轨枕横移与扭转**：轨枕在横向力作用下产生横向位移，并通过轨枕底面与道床的摩擦力将力传递至道床。轨枕间距、轨枕类型和道床密实度是影响轨枕横移量的关键因素。

**道床累积变形**：道床在反复列车荷载作用下产生不可恢复的累积塑性变形，导致轨道几何形位逐渐劣化。曲线段道床的累积变形通常大于直线段，尤其是外轨侧的道床更容易出现沉降和横向位移。

### 2.3 速度等级与动载效应

不同速度等级下列车对轨道结构的动载效应差异显著。低速线路（v<120km/h）以准静态荷载为主，轨道变形以弹性变形为主，可恢复性好。中高速线路（120-250km/h）动载效应增大，轨道结构中的惯性力和振动效应不可忽略。高速铁路（v>250km/h）动载效应显著增强，轨道结构的动态变形和振动成为影响行车安全性和舒适性的关键因素。

## 3. 传统轨道监测方法的局限

### 3.1 接触式位移传感器

传统的轨道位移监测主要采用拉线式位移传感器、LVDT（线性可变差动变压器）等接触式传感器。这类传感器需要安装在轨道附近的固定基础上，测量轨道相对于基础点的位移。

主要局限：安装需要在轨道附近设置固定参考点，在运营线路上实施困难；单个传感器只能测量一个方向的位移，要获取三维位移需要布置多个传感器；传感器和信号线缆可能影响列车运行安全，需要额外的防护措施；长期监测中传感器容易受振动、温度变化和电磁干扰影响，数据稳定性差。

### 3.2 加速度传感器

加速度传感器（如MEMS加速度计）可以测量轨道的振动加速度，通过积分获得位移信息。但加速度积分求位移存在低频漂移问题，对于准静态和低速位移测量的精度有限。此外，加速度传感器测量的是传感器安装点附近的局部响应，无法获取全场变形信息。

### 3.3 轨道检测车

轨道检测车是目前铁路工务部门获取轨道几何状态的主要手段。检测车配备激光摄像、惯性导航等系统，可以测量轨距、高低、轨向等几何参数。但检测车运行间隔通常为10-30天一次，无法实现实时监测；检测车本身的重量和速度也会对被测轨道产生附加影响。

### 3.4 光纤光栅传感器

光纤光栅（FBG）传感器具有抗电磁干扰、可分布式测量的优点，近年来在结构健康监测中得到应用。但光纤光栅传感器本质上是单点测量，要覆盖大范围轨道结构需要大量布设，成本高昂；且光纤传感器对温度和应变的交叉敏感问题在室外轨道环境中尤为突出。

## 4. DIC技术在轨道动态变形测量中的核心能力

### 4.1 非接触全场测量

DIC技术最本质的优势在于非接触和全场测量。在轨道变形监测中，DIC系统安装在轨道附近的稳定基础上，通过工业相机拍摄轨道表面的散斑图像，无需在轨道上安装任何传感器或线缆。一次测量可以获取视场内数十万至数百万个测点的三维位移数据，空间分辨率远超传统点式传感器。

### 4.2 三维位移同步获取

三维DIC系统基于双目立体视觉原理，可以同步获取轨道表面三个方向的位移分量：竖向位移（轨道下沉）、横向位移（轨道横移）和纵向位移（钢轨爬行）。这三个方向的位移分量对于评估轨道结构的整体稳定性都至关重要——横向位移过大可能导致脱轨风险增加，竖向位移不均匀会影响行车平顺性，纵向位移累积会导致轨道应力分布异常。

### 4.3 动态测量能力

现代工业相机的帧率从数百fps到数十万fps不等，可以覆盖轨道变形的主要频率范围。列车轮轨冲击振动的主频通常在1-100Hz范围内，DIC系统配合中速相机（500-1000fps）即可完整记录轨道的动态变形过程。对于更高频的轮轨振动（如钢轨波磨引起的振动，频率可达数百Hz），可以配合高速相机进行测量。

### 4.4 全场应变与应力集中识别

位移场数据经过空间微分可以计算应变场。在轨道结构的螺栓孔、焊缝、截面突变等位置，应变集中现象最为显著。DIC全场应变数据可以直接识别这些应力集中区域的位置和程度，为轨道结构的疲劳寿命评估提供依据。

### 4.5 实时可视化与数据输出

DIC系统可以实时显示位移云图和应变云图，直观呈现轨道在列车动载作用下的变形状态。同时支持通过UDP等接口实时输出数据，便于与列车运行状态监测系统联动。

## 5. 轨道结构各组件的变形测量需求

### 5.1 钢轨

钢轨是轨道结构中直接承受列车荷载的部件。在过弯工况下，钢轨需要测量的关键变形参数包括：轨头横向位移（反映轨道横向稳定性）、轨腰竖向位移（反映轨道竖向刚度）、轨底纵向位移（反映钢轨爬行量）。

钢轨表面为金属光泽，直接进行DIC测量时散斑制备需要特别注意。通常采用喷砂处理增加表面粗糙度，再喷涂耐高温白色底漆和黑色散斑。对于短期实验测量，也可以利用钢轨表面的自然纹理（如轧制痕迹）作为变形信息载体。

### 5.2 扣件系统

扣件是连接钢轨和轨枕的关键部件，其力学性能直接影响轨道的整体稳定性。扣件在过弯动载下的关键变形参数包括：扣件横向位移（反映扣件横向刚度）、扣件竖向位移（反映扣件竖向弹性）、弹条变形（反映扣件扣压力变化）。

扣件系统结构紧凑、尺寸小，需要较高空间分辨率的DIC系统才能精确测量。推荐采用XTDIC-CONST-HR高分辨率系列（最高2500万像素），或配合远摄镜头缩小视场以提高空间分辨率。

### 5.3 轨枕

轨枕承受来自钢轨的各向压力，并弹性地传布于道床，同时有效保持轨道的几何形位。在过弯工况下，轨枕的关键变形参数包括：轨枕横向位移（反映道床横向阻力是否足够）、轨枕竖向位移（反映道床支承刚度）、轨枕扭转角（反映两侧扣件受力不均的程度）。

轨枕表面通常为混凝土材质，自身具有一定的粗糙度，有利于散斑制备。混凝土轨枕表面的自然纹理有时也可直接用于DIC计算。

### 5.4 道床与路基

道床是轨枕下方的碎石层，起到分散荷载、调整轨道几何形位和排水的作用。道床在反复动载下的累积变形是轨道沉降的主要来源。DIC可以测量道床表面的位移场，评估道床的密实度和变形趋势。

对于有砟道床，道床表面散粒体结构使得散斑制备具有挑战性。通常采用在道床表面嵌入标记点（如彩色石子或人工标志）的方式进行测量。

## 6. XTDIC系统在轨道变形监测中的实施方案

### 6.1 系统配置

针对轨道变形监测的需求，XTDIC系统通常采用以下配置：

**测量头**：双目立体视觉测量头，包含两台工业相机。对于轨道监测，推荐使用XTDIC-CONST-SD系列（230-500万像素，163-1500fps）作为基础配置。对于需要更高空间分辨率的扣件区域测量，可选用HR系列（最高2500万像素）。

**相机布置**：相机安装在轨道附近的稳定基础上（如专门设置的观测墩或三脚架），视场覆盖需要测量的轨道区域。对于模拟实验，相机可以布置在轨道侧面和上方，获取轨道的横向和竖向位移。对于现场监测，相机布置需要考虑列车运行安全距离和振动隔离。

**光源**：轨道监测通常在室外进行，环境光变化大。推荐使用LED主动光源（如蓝光LED）配合窄带滤光片，有效抑制环境光干扰。

**同步触发**：DIC系统支持外部触发信号，可以与列车模拟器或加载设备的控制系统同步，确保位移数据与载荷数据的时间对齐。

### 6.2 散斑制备方案

轨道结构各组件的表面特性差异较大，需要针对性地进行散斑制备：

| 组件 | 表面特性 | 散斑方案 |
|------|---------|---------|
| 钢轨 | 金属光泽、光滑 | 喷砂处理→白色底漆→黑色散斑喷涂 |
| 扣件 | 金属表面、尺寸小 | 白色底漆→精细散斑（粒径0.1-0.3mm） |
| 轨枕 | 混凝土粗糙面 | 直接喷涂黑白散斑或利用自然纹理 |
| 道床 | 散粒体结构 | 嵌入彩色标记点或人工标志 |

### 6.3 标定与坐标系统

相机标定是确保测量精度的关键步骤。在轨道监测中，标定需要考虑以下特殊因素：

测量距离通常较大（1-5米），需要使用大尺寸标定板；轨道结构沿线路方向延伸，需要考虑视场拼接的问题；对于长期监测，需要建立统一的坐标系，确保不同时期测量数据的可比性。

## 7. 模拟过弯动载实验设计

### 7.1 实验平台搭建

在实验室条件下模拟列车过弯动载对轨道结构的作用，通常采用以下方案：

**轨道模型**：根据实际轨道结构按比例缩尺或足尺搭建轨道模型，包括钢轨、扣件、轨枕和道床。足尺模型可以更真实地反映实际轨道结构的力学行为，但实验成本和空间需求更大。

**加载系统**：采用液压伺服作动器模拟列车轮载的竖向和横向分量。竖向加载模拟轮载，横向加载模拟离心力。加载频率和幅值根据实际列车运行参数确定。对于高速铁路，单轮竖向力可达100-150kN，横向力可达30-60kN。

**DIC测量系统**：在轨道模型侧面和上方布置DIC测量头，覆盖关键测量区域。对于扣件区域的局部变形测量，可以设置专门的近距离测量头。

### 7.2 实验工况设计

| 工况编号 | 竖向载荷（kN） | 横向载荷（kN） | 加载频率（Hz） | 模拟场景 |
|---------|-------------|-------------|-------------|---------|
| 工况1 | 120 | 0 | 2 | 直线段标准轮载 |
| 工况2 | 120 | 30 | 2 | 低速过弯（v=120km/h） |
| 工况3 | 150 | 50 | 5 | 高速过弯（v=250km/h） |
| 工况4 | 150 | 60 | 10 | 高速过弯+轨道不平顺冲击 |

### 7.3 数据采集与分析

实验过程中，DIC系统以设定帧率连续采集轨道表面图像，同时记录加载系统的力和位移数据。实验结束后，通过DIC软件计算全场位移场和应变场，分析轨道结构在不同工况下的变形特征。

关键分析内容包括：钢轨和轨枕的位移-载荷关系曲线、扣件系统的刚度特性、轨道结构各层之间的相对位移、应变集中区域的位置和程度。

## 8. 设备技术参数

| 参数项 | XTDIC-CONST-SD | XTDIC-CONST-HR |
|--------|---------------|---------------|
| 相机像素 | 230万-500万 | 最高2500万 |
| 帧率 | 163-1500fps | 30-42fps |
| 位移测量精度 | ≤0.01像素 | ≤0.01像素 |
| 应变测量精度 | 50με | 20με |
| 测量幅面 | 50mm-10m | 50mm-10m |
| 应变测量范围 | 0.005%-2000% | 0.005%-2000% |

| 系统功能 | 技术指标 |
|---------|---------|
| 相机同步 | 1-8测头同步采集，可扩展 |
| 实时计算 | 支持实时全场应变计算 |
| 数据输出 | UDP实时输出，支持外部系统联动 |
| 触发模式 | 内部触发/外部触发/同步触发 |
| 工作温度 | -10°C至50°C（标准型） |

## 9. 典型应用场景

### 9.1 轨道结构性能评估

在新建线路或大修后的轨道结构性能评估中，DIC可以测量轨道在列车通过时的全场变形，评估轨道结构的整体刚度和稳定性。通过对比设计值和实测值，可以评估施工质量和轨道结构的实际工作状态。

### 9.2 扣件系统性能测试

扣件是轨道结构中的薄弱环节之一。通过DIC测量扣件在动载下的变形，可以评估扣件的刚度特性和扣压力保持能力。对于新型扣件产品的研发，DIC全场测量可以提供传统方法无法获取的变形细节。

### 9.3 道床稳定性监测

道床在列车反复荷载作用下的累积变形是轨道沉降的主要原因。DIC可以定期测量道床表面的位移场，评估道床的密实度变化趋势，为道床维护决策提供数据支撑。

### 9.4 轨道疲劳损伤研究

轨道结构在长期列车荷载作用下会产生疲劳损伤。DIC可以检测轨道表面微裂纹的萌生和扩展，通过应变场异常识别疲劳损伤区域。结合Paris定律等裂纹扩展模型，可以评估轨道结构的剩余疲劳寿命。

### 9.5 新型轨道结构验证

对于减振轨道、浮置板轨道、弹性支承块轨道等新型轨道结构，DIC全场测量可以全面评估其减振效果和变形特性，为新型轨道结构的优化设计提供实验依据。

## 10. 国产DIC在轨道交通监测领域的发展

铁路轨道结构健康监测是结构健康监测（SHM）领域的重要分支。长期以来，高精度动态变形监测设备主要依赖进口，不仅采购成本高，而且后期维护和技术支持存在诸多不便。

国产DIC设备在轨道交通监测领域的应用起步相对较晚，但发展迅速。以XTDIC为代表的国产DIC系统，在测量精度、帧率和软件功能等方面已经能够满足轨道变形监测的工程需求。特别是在大视场、远距离测量方面，国产设备针对中国铁路的工程特点进行了优化，适应性更强。

随着中国高速铁路网络的持续扩大和运维要求的不断提高，轨道结构的动态变形监测需求将持续增长。国产DIC设备在这一领域具有广阔的应用前景，同时也需要在工程实践中不断积累经验，完善从数据采集到分析评估的完整技术链条。

## 11. 结语

铁路轨道在列车过弯动载下的变形位移监测，是评估轨道结构安全性和稳定性的重要手段。DIC技术以其非接触、全场、三维的测量能力，克服了传统接触式传感器测点稀疏、安装困难、受列车干扰大等局限，为轨道结构的动态变形监测提供了全新的技术路径。

从钢轨的横向位移到扣件的弹性变形，从轨枕的横移到道床的累积沉降，DIC技术可以在不干扰轨道结构的前提下，同步获取全场三维位移数据和应变分布。随着国产DIC设备在精度、可靠性和工程适应性方面的持续提升，这项技术有望在铁路轨道结构健康监测中发挥越来越重要的作用，为中国铁路的安全运营提供更加坚实的数据支撑。

---

</details>

---

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

# DIC Technology for Monitoring Deformation and Displacement of Rails and Fastening Systems Under Simulated Train Curving Dynamic Loading

> [!TIP]
> **Language / 请选择语言:** [中文版](#chinese-version)

## Table of Contents

- [1. Introduction: Engineering Requirements for Railway Track Dynamic Deformation Monitoring](#1-introduction-engineering-requirements-for-railway-track-dynamic-deformation-monitoring)
- [2. Mechanical Characteristics of Track Structure Under Train Curving Dynamic Loading](#2-mechanical-characteristics-of-track-structure-under-train-curving-dynamic-loading)
- [3. Limitations of Traditional Track Monitoring Methods](#3-limitations-of-traditional-track-monitoring-methods)
- [4. Core Capabilities of DIC in Track Dynamic Deformation Measurement](#4-core-capabilities-of-dic-in-track-dynamic-deformation-measurement)
- [5. Deformment Measurement Requirements for Track Structure Components](#5-deformation-measurement-requirements-for-track-structure-components)
- [6. XTDIC System Implementation for Track Deformation Monitoring](#6-xtdic-system-implementation-for-track-deformation-monitoring)
- [7. Simulated Curving Dynamic Loading Experimental Design](#7-simulated-curving-dynamic-loading-experimental-design)
- [8. Device Technical Specifications](#8-device-technical-specifications)
- [9. Typical Application Scenarios](#9-typical-application-scenarios)
- [10. Development of Domestic DIC in Rail Transit Monitoring](#10-development-of-domestic-dic-in-rail-transit-monitoring)
- [11. Conclusion](#11-conclusion)

---

## 1. Introduction: Engineering Requirements for Railway Track Dynamic Deformation Monitoring

Railways serve as the backbone of national transportation. By the end of 2025, China's railway operational mileage exceeded 160,000 kilometers, with high-speed rail exceeding 46,000 kilometers—both ranking first in the world. As train speeds continue to increase and axle loads grow, the deformation and stability of track structures under dynamic train loading have become increasingly critical concerns.

The loads exerted by trains on track structures are dynamic and multi-dimensional. Beyond the fundamental vertical wheel load, centrifugal forces generated during curving cause increased lateral displacement of the track; longitudinal forces from braking and traction drive rail creep; and impact vibrations between wheel and rail propagate and attenuate through the ballast and sleepers. These forces act collectively on the track structure—a complex mechanical system composed of rails, fasteners, sleepers, ballast, and subgrade—producing coupled deformations across all components.

Traditional track deformation monitoring methods rely primarily on contact sensors and manual inspections, which suffer from inherent limitations including sparse measurement points, poor real-time performance, and significant interference from train operations. Digital Image Correlation (DIC), as a non-contact full-field optical measurement technique, provides an entirely new experimental approach for dynamic deformation monitoring of track structures. By tracking the deformation of speckle patterns on track surfaces under dynamic train loading, DIC can synchronously capture full-field 3D displacement data and strain distributions without disturbing the track structure, completely recording the complex mechanical process of track dynamic deformation as visualized data.

## 2. Mechanical Characteristics of Track Structure Under Train Curving Dynamic Loading

### 2.1 Force Analysis Under Curving Conditions

When a train negotiates a curve, the force state of the track structure differs fundamentally from that on tangent track. The most significant additional load is centrifugal force—a train traveling at speed v through a curve of radius R generates a centrifugal acceleration of v²/R. For a high-speed train at 250 km/h negotiating a 3000m radius curve, the centrifugal acceleration reaches approximately 1.6 m/s², equivalent to roughly 16% of gravitational acceleration acting laterally.

This lateral force transmits through the wheel-rail contact interface to the rail, then through the fastening system to the sleepers and ballast. A track structure designed primarily for vertical loads on tangent track must simultaneously resist lateral displacement and torsion on curves. The outer rail experiences the maximum lateral force, making it the controlling design condition for curved track structures.

### 2.2 Deformation Modes of Track Structure

Under train curving dynamic loading, track structure deformation can be categorized into the following levels:

**Rail Lateral Displacement**: Lateral wheel forces cause rail bending deformation, with the outer rail deflecting toward the outside of the curve. For 60kg/m rail with standard fastener spacing (approximately 600mm), lateral rail displacement under a single wheel lateral force can reach 0.5-2mm.

**Fastening System Deformation**: Fasteners serve as the elastic connection between rail and sleeper, undergoing elastic deformation under lateral loads. Fastener lateral stiffness (typically 10-40 kN/mm) directly determines the magnitude of rail lateral displacement—lower stiffness means greater displacement, but excessively low stiffness makes it difficult to maintain track geometry.

**Sleeper Lateral Movement and Torsion**: Sleepers experience lateral displacement under lateral forces, transmitting loads to the ballast through friction at the sleeper-ballast interface. Sleeper spacing, sleeper type, and ballast compaction are key factors affecting sleeper lateral movement.

**Ballast Cumulative Deformation**: Under repeated train loading, ballast undergoes irrecoverable cumulative plastic deformation, leading to gradual deterioration of track geometry. Cumulative ballast deformation on curves typically exceeds that on tangent track, with the outer rail side particularly susceptible to settlement and lateral displacement.

### 2.3 Speed Effects on Dynamic Loading

Dynamic loading effects vary significantly across speed classes. Low-speed lines (v<120 km/h) are dominated by quasi-static loads, with primarily elastic and recoverable track deformation. Medium-speed lines (120-250 km/h) experience increased dynamic effects where inertial forces and vibrations in the track structure cannot be ignored. High-speed lines (v>250 km/h) exhibit significantly amplified dynamic effects, with dynamic deformation and vibration becoming critical factors affecting both safety and ride comfort.

## 3. Limitations of Traditional Track Monitoring Methods

### 3.1 Contact Displacement Sensors

Traditional track displacement monitoring primarily employs contact sensors such as draw-wire displacement transducers and LVDTs (Linear Variable Differential Transformers). These sensors require installation on stable foundations near the track, measuring displacement relative to a fixed reference point.

Key limitations: Installation requires establishing fixed reference points near the track, which is difficult to implement on operational lines; each sensor measures only one displacement direction, requiring multiple sensors for 3D measurement; sensors and signal cables may affect train safety and require additional protection; long-term monitoring is susceptible to vibration, temperature variations, and electromagnetic interference, resulting in poor data stability.

### 3.2 Acceleration Sensors

Accelerometers (such as MEMS accelerometers) can measure track vibration acceleration, with displacement obtained through integration. However, acceleration integration suffers from low-frequency drift, limiting accuracy for quasi-static and low-speed displacement measurements. Furthermore, accelerometers measure local response near the mounting point and cannot capture full-field deformation information.

### 3.3 Track Inspection Vehicles

Track inspection vehicles are currently the primary means for railway maintenance departments to assess track geometry. Equipped with laser cameras, inertial navigation, and other systems, they can measure gauge, profile, alignment, and other geometric parameters. However, inspection intervals are typically 10-30 days, preventing real-time monitoring; additionally, the weight and speed of the inspection vehicle itself impose additional effects on the track being measured.

### 3.4 Fiber Bragg Grating Sensors

Fiber Bragg Grating (FBG) sensors offer advantages of electromagnetic immunity and distributed measurement capability, and have been increasingly applied in structural health monitoring in recent years. However, FBG sensors are fundamentally single-point measurements—covering large track structures requires extensive deployment at high cost. Additionally, the cross-sensitivity of fiber sensors to both temperature and strain is particularly problematic in outdoor track environments.

## 4. Core Capabilities of DIC in Track Dynamic Deformation Measurement

### 4.1 Non-Contact Full-Field Measurement

DIC's most fundamental advantage lies in its non-contact and full-field measurement capability. For track deformation monitoring, the DIC system is installed on stable foundations near the track, capturing speckle images of track surfaces through industrial cameras without requiring any sensors or cables on the track itself. A single measurement can obtain 3D displacement data for hundreds of thousands to millions of measurement points within the field of view, with spatial resolution far exceeding that of conventional point sensors.

### 4.2 Simultaneous 3D Displacement Acquisition

3D-DIC systems based on binocular stereo vision principles can simultaneously acquire all three displacement components of the track surface: vertical displacement (track settlement), lateral displacement (track shifting), and longitudinal displacement (rail creep). All three components are critical for assessing overall track structure stability—excessive lateral displacement may increase derailment risk, uneven vertical displacement affects ride smoothness, and accumulated longitudinal displacement leads to abnormal stress distribution in the track.

### 4.3 Dynamic Measurement Capability

Modern industrial cameras offer frame rates ranging from hundreds to hundreds of thousands of fps, covering the primary frequency range of track deformation. The dominant frequencies of train wheel-rail impact vibrations typically fall within 1-100 Hz, and DIC systems with medium-speed cameras (500-1000 fps) can fully capture the dynamic deformation process. For higher-frequency wheel-rail vibrations (such as those caused by rail corrugation, reaching hundreds of Hz), high-speed cameras can be employed.

### 4.4 Full-Field Strain and Stress Concentration Identification

Displacement field data can be spatially differentiated to calculate strain fields. Stress concentration phenomena are most pronounced at locations such as bolt holes, welds, and section changes in track structures. DIC full-field strain data can directly identify the location and severity of these stress concentration zones, providing the basis for fatigue life assessment of track structures.

### 4.5 Real-Time Visualization and Data Output

DIC systems can display displacement contour maps and strain contour maps in real-time, intuitively presenting the deformation state of the track under dynamic train loading. Simultaneous support for real-time data output through interfaces such as UDP enables integration with train operation status monitoring systems.

## 5. Deformation Measurement Requirements for Track Structure Components

### 5.1 Rails

Rails are the components of the track structure that directly bear train loads. Under curving conditions, key deformation parameters requiring measurement include: rail head lateral displacement (reflecting lateral track stability), rail web vertical displacement (reflecting vertical track stiffness), and rail base longitudinal displacement (reflecting rail creep).

Rail surfaces are metallic and glossy, requiring special attention for speckle preparation. Typically, sandblasting is used to increase surface roughness, followed by application of high-temperature-resistant white primer and black speckle. For short-term experimental measurements, natural surface textures of the rail (such as rolling marks) can also serve as deformation information carriers.

### 5.2 Fastening Systems

Fasteners are critical components connecting rails and sleepers, with mechanical properties directly affecting overall track stability. Key deformation parameters of fasteners under curving dynamic loads include: fastener lateral displacement (reflecting lateral stiffness), fastener vertical displacement (reflecting vertical elasticity), and clip deformation (reflecting changes in fastening pressure).

Fastening systems are compact and small in size, requiring DIC systems with higher spatial resolution for precise measurement. The XTDIC-CONST-HR high-resolution series (up to 25 megapixels) is recommended, or telephoto lenses can be used to reduce the field of view and improve spatial resolution.

### 5.3 Sleepers

Sleepers bear multi-directional pressures from rails and elastically distribute them to the ballast while effectively maintaining track geometry. Under curving conditions, key sleeper deformation parameters include: sleeper lateral displacement (indicating whether ballast lateral resistance is sufficient), sleeper vertical displacement (reflecting ballast support stiffness), and sleeper torsion angle (indicating uneven loading on fasteners on both sides).

Sleeper surfaces are typically concrete with inherent roughness, facilitating speckle preparation. Natural textures on concrete sleeper surfaces can sometimes be used directly for DIC computation.

### 5.4 Ballast and Subgrade

Ballast is the granular layer beneath sleepers that distributes loads, adjusts track geometry, and provides drainage. Cumulative deformation of ballast under repeated dynamic loading is the primary source of track settlement. DIC can measure the displacement field of the ballast surface to evaluate ballast compaction and deformation trends.

For ballasted track, the granular surface structure makes speckle preparation challenging. Typically, embedded markers (such as colored stones or artificial targets) are used for measurement.

## 6. XTDIC System Implementation for Track Deformation Monitoring

### 6.1 System Configuration

For track deformation monitoring requirements, the XTDIC system typically employs the following configuration:

**Measurement Head**: Binocular stereo vision measurement head containing two industrial cameras. For track monitoring, the XTDIC-CONST-SD series (2.3-5 megapixels, 163-1500 fps) is recommended as the basic configuration. For fastener area measurements requiring higher spatial resolution, the HR series (up to 25 megapixels) can be selected.

**Camera Arrangement**: Cameras are installed on stable foundations near the track (such as purpose-built observation piers or tripods), with the field of view covering the track area requiring measurement. For simulation experiments, cameras can be positioned at the side and above the track to capture lateral and vertical displacement. For field monitoring, camera placement must consider safe distances from train operations and vibration isolation.

**Light Source**: Track monitoring is typically conducted outdoors with significant ambient light variation. Active LED light sources (such as blue LED) paired with narrow-band filters are recommended to effectively suppress ambient light interference.

**Synchronous Triggering**: The DIC system supports external trigger signals, enabling synchronization with train simulator or loading system controls to ensure temporal alignment between displacement data and load data.

### 6.2 Speckle Preparation Scheme

Surface characteristics of track structure components vary significantly, requiring targeted speckle preparation:

| Component | Surface Characteristics | Speckle Scheme |
|-----------|----------------------|----------------|
| Rail | Metallic gloss, smooth | Sandblasting → white primer → black speckle spraying |
| Fastener | Metallic surface, small size | White primer → fine speckle (0.1-0.3mm particles) |
| Sleeper | Concrete rough surface | Direct black/white speckle spraying or natural texture |
| Ballast | Granular structure | Embedded colored markers or artificial targets |

### 6.3 Calibration and Coordinate System

Camera calibration is a critical step for ensuring measurement accuracy. In track monitoring, calibration must account for the following special factors:

Measurement distances are typically large (1-5 meters), requiring large-format calibration targets; track structures extend along the line direction, requiring consideration of field-of-view stitching; for long-term monitoring, a unified coordinate system must be established to ensure comparability of measurements from different periods.

## 7. Simulated Curving Dynamic Loading Experimental Design

### 7.1 Experimental Platform Construction

Simulating train curving dynamic loading on track structures in laboratory conditions typically employs the following approach:

**Track Model**: A track model is constructed to scale or full-size based on actual track structure, including rails, fasteners, sleepers, and ballast. Full-scale models more accurately reflect the mechanical behavior of actual track structures but require greater experimental cost and space.

**Loading System**: Hydraulic servo actuators simulate the vertical and lateral components of train wheel loads. Vertical loading simulates wheel loads, while lateral loading simulates centrifugal forces. Loading frequency and amplitude are determined based to actual train operating parameters. For high-speed railways, single-wheel vertical forces can reach 100-150 kN, with lateral forces of 30-60 kN.

**DIC Measurement System**: DIC measurement heads are positioned at the sides and above the track model, covering critical measurement areas. For local deformation measurement of fastener areas, dedicated close-range measurement heads can be deployed.

### 7.2 Experimental Condition Design

| Condition | Vertical Load (kN) | Lateral Load (kN) | Loading Frequency (Hz) | Simulated Scenario |
|-----------|-------------------|-------------------|----------------------|-------------------|
| Condition 1 | 120 | 0 | 2 | Tangent track standard wheel load |
| Condition 2 | 120 | 30 | 2 | Low-speed curving (v=120 km/h) |
| Condition 3 | 150 | 50 | 5 | High-speed curving (v=250 km/h) |
| Condition 4 | 150 | 60 | 10 | High-speed curving + track irregularity impact |

### 7.3 Data Acquisition and Analysis

During experiments, the DIC system continuously captures track surface images at the set frame rate while the loading system records force and displacement data simultaneously. After experiments, full-field displacement and strain fields are calculated through DIC software to analyze track deformation characteristics under different conditions.

Key analysis contents include: displacement-load relationship curves for rails and sleepers, stiffness characteristics of fastening systems, relative displacement between track structure layers, and location and severity of strain concentration zones.

## 8. Device Technical Specifications

| Parameter | XTDIC-CONST-SD | XTDIC-CONST-HR |
|-----------|---------------|---------------|
| Camera Resolution | 2.3-5 MP | Up to 25 MP |
| Frame Rate | 163-1500 fps | 30-42 fps |
| Displacement Measurement Precision | ≤0.01 pixel | ≤0.01 pixel |
| Strain Measurement Accuracy | 50 με | 20 με |
| Measurement Field of View | 50mm-10m | 50mm-10m |
| Strain Measurement Range | 0.005%-2000% | 0.005%-2000% |

| System Function | Technical Specification |
|----------------|------------------------|
| Camera Synchronization | 1-8 measurement heads, expandable |
| Real-Time Computation | Supports real-time full-field strain calculation |
| Data Output | Real-time UDP output, supports external system integration |
| Trigger Mode | Internal trigger / External trigger / Synchronous trigger |
| Operating Temperature | -10°C to 50°C (standard type) |

## 9. Typical Application Scenarios

### 9.1 Track Structure Performance Assessment

In performance assessment of new or overhauled track structures, DIC can measure full-field track deformation during train passages to evaluate overall track stiffness and stability. Comparing design values with measured values enables assessment of construction quality and actual working conditions of the track structure.

### 9.2 Fastening System Performance Testing

Fasteners represent one of the weaker links in track structures. Measuring fastener deformation under dynamic loading through DIC enables evaluation of fastener stiffness characteristics and clamping force retention capability. For new fastener product development, DIC full-field measurement provides deformation details unattainable through traditional methods.

### 9.3 Ballast Stability Monitoring

Cumulative deformation of ballast under repeated train loading is the primary cause of track settlement. DIC can periodically measure the displacement field of the ballast surface to evaluate trends in ballast compaction changes, providing data support for ballast maintenance decision-making.

### 9.4 Track Fatigue Damage Research

Track structures develop fatigue damage under long-term train loading. DIC can detect initiation and propagation of micro-cracks on track surfaces and identify fatigue damage regions through strain field anomalies. Combined with crack propagation models such as Paris' law, the remaining fatigue life of track structures can be assessed.

### 9.5 New Track Structure Validation

For new track structures such as vibration-damping tracks, floating slab tracks, and elastic bearing block tracks, DIC full-field measurement can comprehensively evaluate vibration reduction effectiveness and deformation characteristics, providing experimental evidence for optimization of new track structure designs.

## 10. Development of Domestic DIC in Rail Transit Monitoring

Railway track structural health monitoring represents an important branch of the broader Structural Health Monitoring (SHM) field. For an extended period, high-precision dynamic deformation monitoring equipment relied primarily on imports, resulting not only in high procurement costs but also in significant inconveniences for maintenance and technical support.

Domestic DIC equipment applications in rail transit monitoring started relatively late but have developed rapidly. Domestic DIC systems represented by XTDIC have achieved the measurement precision, frame rate, and software functionality required for track deformation monitoring in engineering applications. Particularly in large field-of-view and long-distance measurements, domestic equipment has been optimized for the engineering characteristics of Chinese railways, providing stronger adaptability.

As China's high-speed railway network continues to expand and operational maintenance requirements increase, demand for dynamic deformation monitoring of track structures will continue to grow. Domestic DIC equipment has broad application prospects in this field, while also requiring continuous experience accumulation in engineering practice to improve the complete technical chain from data acquisition to analysis and assessment.

## 11. Conclusion

Monitoring deformation and displacement of railway tracks under train curving dynamic loading is an important means of assessing track structure safety and stability. DIC technology, with its non-contact, full-field, and three-dimensional measurement capabilities, overcomes the limitations of traditional contact sensors—including sparse measurement points, installation difficulties, and significant train interference—providing a new technical pathway for dynamic deformation monitoring of track structures.

From lateral rail displacement to elastic deformation of fasteners, from sleeper lateral movement to cumulative ballast settlement, DIC technology can synchronously acquire full-field 3D displacement data and strain distributions without disturbing the track structure. As domestic DIC equipment continues to improve in precision, reliability, and engineering adaptability, this technology is expected to play an increasingly important role in railway track structural health monitoring, providing more solid data support for the safe operation of China's railways.

---

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D railway track monitoring application documentation*
