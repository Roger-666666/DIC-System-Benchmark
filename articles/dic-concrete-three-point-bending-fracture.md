# DIC技术在混凝土三点弯曲与断裂演化分析中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：混凝土断裂力学的测量挑战](#1-引言混凝土断裂力学的测量挑战)
- [2. 混凝土三点弯曲试验的力学基础](#2-混凝土三点弯曲试验的力学基础)
- [3. 传统测量方法在混凝土断裂研究中的局限](#3-传统测量方法在混凝土断裂研究中的局限)
- [4. DIC技术在混凝土断裂演化分析中的核心能力](#4-dic技术在混凝土断裂演化分析中的核心能力)
- [5. 断裂过程区（FPZ）的DIC量化方法](#5-断裂过程区fpz的dic量化方法)
- [6. XTDIC系统在混凝土三点弯曲试验中的实施方案](#6-xtdic系统在混凝土三点弯曲试验中的实施方案)
- [7. 典型应用场景](#7-典型应用场景)
- [8. 设备技术参数](#8-设备技术参数)
- [9. 参考文献](#9-参考文献)
- [10. 结语](#10-结语)

---

## 1. 引言：混凝土断裂力学的测量挑战

混凝土是当今世界上使用量最大的工程建筑材料，从高层建筑到大跨桥梁，从水工结构到基础设施，混凝土结构的安全性评估始终是土木工程领域的核心课题。然而，混凝土并非理想的弹性材料——它是一种典型的拉压不对称准脆性复合材料，内部存在大量微裂缝、孔隙和骨料-砂浆界面过渡区（ITZ），使得其断裂行为远比金属等延性材料复杂。

混凝土的断裂破坏并非突然发生，而是经历一个渐进的裂缝萌生、稳定扩展和失稳扩展过程。在裂缝尖端前方，存在一个被称为"断裂过程区"（Fracture Process Zone, FPZ）的微裂缝聚集带，区内发生骨料桥接、裂缝钝化、微裂缝扩展等多种能量耗散机制。FPZ的尺寸、形态和演化规律直接决定了混凝土的宏观断裂韧度和尺寸效应特征，是混凝土断裂力学研究的核心问题。

精确测量FPZ的演化过程，需要获取裂缝尖端附近的全场位移和应变分布数据。传统接触式测量方法——应变片、夹式引伸计、LVDT位移计——只能提供离散点位的测量数据，无法完整呈现FPZ的空间分布和时变特征。数字图像相关（DIC）技术以其非接触、全场、高精度的测量能力，为混凝土断裂过程区的量化分析提供了全新的技术手段。

## 2. 混凝土三点弯曲试验的力学基础

### 2.1 三点弯曲试验标准

三点弯曲试验是评估混凝土梁抗弯强度和裂缝扩展行为的标准试验方法。根据《水工混凝土断裂试验规程》（DL/T 5332-2005）和国际建议标准RILEM TC-89 FMT，标准三点弯曲试件通常采用跨高比为4或8的梁式试件，在梁底中部预制一条初始裂缝（缝高比a₀/h通常为0.3-0.5），通过万能试验机在跨中施加集中载荷。

标准试件尺寸通常为：高度H=100-400mm，宽度B=100-200mm，跨度S=400-1600mm（对应跨高比4-8），初始裂缝长度a₀=30-200mm。加载速率控制在0.05-0.1mm/min（位移控制模式），以确保准静态加载条件。

### 2.2 关键断裂参数

三点弯曲试验可以获取以下关键断裂力学参数：

**起裂韧度K_ini^IC**：裂缝开始稳定扩展时的应力强度因子，反映混凝土抵抗裂缝萌生的能力。研究表明，起裂韧度与试件尺寸无关，可作为混凝土的材料常数。

**失稳韧度K_un^IC**：裂缝失稳扩展（峰值荷载时刻）对应的应力强度因子，反映混凝土抵抗裂缝快速扩展的能力。失稳韧度与试件尺寸有关，存在明显的尺寸效应。

**断裂能G_F**：定义为载荷-挠度曲线下的面积与断裂面面积之比，反映裂缝扩展过程中单位面积所消耗的能量。普通混凝土的断裂能约为50-150 N/m。

**裂缝口张开位移CMOD**：预制裂缝尖端处的张开位移，是判断裂缝扩展状态的关键指标。临界裂缝口张开位移CMOD_c对应峰值荷载时刻。

**裂缝尖端张开位移CTOD**：裂缝尖端处的张开位移，直接反映裂缝尖端的应力集中程度。

### 2.3 双K断裂模型

吴智敏等提出的双K断裂模型将混凝土断裂过程分为两个阶段：起裂阶段（K_I < K_ini^IC，裂缝稳定扩展）和失稳阶段（K_I ≥ K_un^IC，裂缝快速扩展）。该模型通过起裂韧度和失稳韧度两个参数描述混凝土的断裂特性，已被纳入《水工混凝土断裂试验规程》。

双K断裂参数的一个重要特性是：起裂韧度K_ini^IC在初始缝高比a₀/h=0.3-0.5范围内是与试件高度无关的常数，失稳韧度K_un^IC也与试件高度及初始缝高比无关。这使得双K断裂参数可以作为混凝土的材料常数，用于不同尺寸结构的断裂分析。

## 3. 传统测量方法在混凝土断裂研究中的局限

### 3.1 应变片的局限性

应变片是混凝土试验中最常用的局部变形测量手段，但在断裂研究中存在明显不足：

离散采样缺陷：应变片只能测量粘贴点附近的局部应变，而FPZ的宽度通常只有几毫米到几十毫米，应变片很难精确覆盖FPZ区域。如果应变片粘贴位置偏离FPZ，测量数据将无法反映真实的裂缝尖端应变场。

量程限制：普通应变片的量程通常在5%以内，而FPZ内的局部应变可能远超此值（混凝土开裂时应变可达10%以上），导致应变片在裂缝扩展过程中提前失效。

### 3.2 夹式引伸计的局限性

夹式引伸计通常安装在预制裂缝口处测量CMOD，是三点弯曲试验的标准配置。但其局限在于：

单点测量：夹式引伸计只能测量裂缝口处的张开位移，无法获取FPZ内部的应变分布。对于研究FPZ的演化规律，单点数据远远不够。

接触要求：夹式引伸计需要安装在试件表面，安装位置和接触力可能影响裂缝的自然扩展路径。

### 3.3 LVDT位移计的局限性

LVDT位移计可以测量试件特定位置的位移，但同样只能提供离散点位的测量数据。在混凝土断裂研究中，LVDT通常用于测量跨中挠度，无法获取FPZ区域的全场变形信息。

### 3.4 光弹性与云纹干涉法的局限

光弹性法和云纹干涉法等光学方法虽然可以获取全场变形信息，但需要专门的试件制备（如粘贴光栅、涂覆光敏材料），且设备复杂、对环境振动敏感，不适合混凝土这种表面粗糙、变形量大的材料。

## 4. DIC技术在混凝土断裂演化分析中的核心能力

### 4.1 非接触全场变形测量

DIC技术最突出的优势在于非接触和全场测量。在混凝土三点弯曲试验中，DIC系统通过相机拍摄试件表面的散斑图像，无需在试件表面安装任何传感器。这一特性对于混凝土断裂研究尤为重要——任何安装在试件表面的传感器都可能干扰裂缝的自然扩展，而DIC完全避免了这一问题。

DIC一次测量可以获取视场内数十万个测点的二维或三维位移数据，空间分辨率可以达到亚毫米级别。对于FPZ的测量，DIC可以完整呈现裂缝尖端附近的应变集中区域，精确识别FPZ的边界和演化过程。

### 4.2 裂缝萌生与扩展的实时追踪

DIC技术可以实时追踪混凝土表面裂缝的萌生和扩展过程。通过分析相邻两幅图像之间的位移场变化，DIC可以精确识别裂缝萌生的位置和时间，追踪裂缝扩展的路径和速度。

研究表明，DIC方法能够有效捕捉到裂缝的扩展过程，并且与夹式引伸计测得的CMOD值二者吻合良好。CTOD的DIC实测值和公式计算值变化趋势也较为一致，验证了DIC技术在混凝土断裂测量中的准确性。

### 4.3 FPZ尺寸与形态的精确量化

DIC获取的全场位移和应变数据可以直接用于FPZ尺寸的量化分析。通过分析裂缝尖端附近的应变分布，可以确定FPZ的长度（沿裂缝扩展方向）和宽度（垂直于裂缝方向），以及FPZ面积随加载过程的变化规律。

研究表明，峰值荷载时刻对应的临界断裂过程区长度随着试件高度的增加而逐渐增加，临界损伤区域面积亦相应增加，但临界断裂过程区长度与试件高度的比值随试件高度的增加趋于稳定。DIC技术为这一规律的实验验证提供了可靠的测量手段。

### 4.4 多尺度测量能力

混凝土断裂涉及从微观（微米级，ITZ微裂缝）到宏观（厘米级，FPZ和裂缝扩展）的多尺度过程。DIC技术配合不同的相机镜头和测量幅面，可以实现从几毫米到几十米的跨尺度测量。对于混凝土三点弯曲试验，DIC可以灵活调整测量幅面——从聚焦FPZ局部区域的小视场（几十毫米）到覆盖整根试件的大视场（数百毫米）。

### 4.5 与声发射等技术的协同

DIC技术可以与声发射（AE）技术协同使用，实现混凝土断裂过程的多物理量同步监测。DIC提供全场变形和裂缝形态信息，AE提供微裂缝萌生和扩展的声发射信号，两者结合可以更全面地理解混凝土断裂的微观机制。

## 5. 断裂过程区（FPZ）的DIC量化方法

### 5.1 FPZ的识别准则

利用DIC数据识别FPZ的边界，主要有以下几种准则：

**应变阈值准则**：当局部应变超过某一阈值（如混凝土的极限拉应变，约100-200με）时，认为该点进入FPZ。该方法简单直观，但阈值的选择对结果影响较大。

**位移不连续准则**：当相邻测点之间的位移差出现突变时，认为该处存在裂缝。该方法可以直接识别裂缝位置，但对DIC数据的噪声水平较为敏感。

**应变梯度准则**：FPZ边界处的应变梯度最大，通过分析应变场的梯度分布可以确定FPZ的边界。该方法对噪声的鲁棒性较好。

### 5.2 FPZ长度与宽度的测量

FPZ长度定义为从裂缝尖端到FPZ尾端（应变恢复到基体应变水平）的距离。DIC可以通过分析裂缝尖端附近的应变分布曲线，确定FPZ的长度。

FPZ宽度定义为垂直于裂缝扩展方向上FPZ的最大宽度。DIC可以通过分析不同截面的应变分布，确定FPZ的宽度及其沿裂缝扩展方向的变化。

研究表明，完全发展的FPZ长度在静态和疲劳加载条件下大致相等，而自由裂缝的失稳扩展仅发生在中大型试件中。

### 5.3 双K断裂参数的DIC计算方法

利用DIC获取的全场位移数据，可以通过以下步骤计算双K断裂参数：

1. 通过DIC位移场确定裂缝尖端位置和裂缝扩展长度Δa
2. 通过DIC应变场确定裂缝口张开位移CMOD和裂缝尖端张开位移CTOD
3. 结合试验机记录的荷载P，利用线弹性断裂力学公式计算应力强度因子K_I
4. 通过P-CMOD曲线的起裂点和峰值点分别确定起裂韧度K_ini^IC和失稳韧度K_un^IC

### 5.4 断裂能的DIC计算方法

利用DIC获取的全场位移数据，可以更精确地计算断裂能。传统方法通过载荷-挠度曲线下的面积计算断裂能，但挠度测量通常只反映跨中一个点的位移。DIC可以获取整根试件的全场位移分布，结合试验机荷载数据，可以更精确地计算裂缝扩展过程中消耗的总能量。

## 6. XTDIC系统在混凝土三点弯曲试验中的实施方案

### 6.1 系统配置

针对混凝土三点弯曲试验的需求，XTDIC系统通常采用以下配置：

**测量头**：双目立体视觉测量头，包含两台工业相机。对于混凝土三点弯曲试验，推荐使用XTDIC-CONST-SD系列（230-500万像素，163-1500fps）作为基础配置。对于需要更高空间分辨率的FPZ精细测量，可选用HR系列（≤25MP，30-42fps）。

**相机布置**：相机安装在试件正前方，光轴垂直于试件表面（二维DIC）或从两侧对称布置（三维DIC）。对于三点弯曲试验，通常关注试件侧面的裂缝扩展和FPZ演化，因此相机应正对试件侧面布置。

**测量幅面**：根据试件尺寸和测量需求，测量幅面通常设置为100mm×100mm（聚焦FPZ局部）至500mm×400mm（覆盖整根试件）。

### 6.2 散斑制备方案

混凝土表面的散斑制备需要考虑以下因素：

**散斑材料**：混凝土表面粗糙且多孔，散斑材料需要有良好的附着力和耐久性。推荐使用白色亚光漆作为底色，黑色亚光漆喷涂散斑图案。

**散斑图案**：散斑粒径需要根据测量幅面和相机分辨率进行优化。对于100mm×100mm的小视场（FPZ精细测量），散斑粒径通常为0.1-0.3mm；对于500mm×400mm的大视场（整根试件），散斑粒径通常为0.5-1mm。

**散斑区域**：散斑区域需要覆盖试件侧面从预制裂缝到预期裂缝扩展路径的全部区域。对于标准三点弯曲试件，散斑区域通常为试件高度×（跨度/2）的矩形区域。

### 6.3 加载同步

DIC系统通过外部触发信号与万能试验机同步，确保变形数据与荷载数据的时间对齐。试验机输出的荷载和位移信号通过A/D采集卡输入DIC系统，与图像采集同步记录。

### 6.4 数据处理流程

1. 图像采集：以设定帧率（通常1-10fps，混凝土准静态试验不需要高帧率）采集试件表面散斑图像
2. 位移场计算：通过DIC算法计算相邻图像之间的位移场
3. 应变场计算：对位移场进行平滑处理和数值微分，计算应变场
4. 裂缝识别：通过位移不连续准则或应变阈值准则识别裂缝位置和FPZ边界
5. 参数提取：计算FPZ长度、宽度、CMOD、CTOD等断裂参数
6. 结果可视化：生成位移场、应变场、裂缝扩展路径等可视化结果

## 7. 典型应用场景

### 7.1 普通混凝土断裂性能研究

DIC技术广泛应用于普通混凝土三点弯曲断裂试验，测量FPZ演化、计算双K断裂参数和断裂能。通过DIC全场测量，可以研究水灰比、骨料类型、骨料粒径等因素对混凝土断裂性能的影响。

### 7.2 再生骨料混凝土断裂性能研究

再生骨料混凝土的断裂性能与普通混凝土存在显著差异。DIC技术可以用于研究不同再生粗骨料取代率（0%、30%、50%、70%、100%）对混凝土断裂参数的影响。研究表明，当再生骨料取代率为100%时，起裂韧度和失稳韧度分别下降了15.81%和15.39%。DIC方法能够有效捕捉到再生骨料混凝土裂缝的扩展过程，并且与夹式引伸计测得的CMOD值吻合良好。

### 7.3 活性粉末混凝土（RPC）断裂性能研究

活性粉末混凝土是一种超高性能混凝土，其断裂性能与普通混凝土有显著差异。DIC技术可以用于研究碎石含量、水灰比、混凝土强度等因素对RPC断裂性能的影响，为RPC材料的优化设计提供实验数据支撑。

### 7.4 纤维增强混凝土断裂性能研究

纤维增强混凝土（如钢纤维混凝土、PVA纤维混凝土）的断裂行为涉及纤维桥接、纤维拔出等复杂的能量耗散机制。DIC技术可以测量纤维增强混凝土FPZ的演化过程，研究纤维类型、纤维含量、纤维取向等对FPZ尺寸和断裂韧度的影响。

### 7.5 高温下混凝土断裂性能研究

火灾等极端条件下，混凝土结构的断裂性能会发生显著退化。DIC技术可以用于研究不同温度（25°C至680°C甚至更高）对混凝土断裂韧度和断裂能的影响。研究表明，600°C以上的高温可使混凝土断裂韧度降低约90%，断裂能降低约30-50%。

### 7.6 混凝土疲劳断裂研究

在重复荷载作用下，混凝土的断裂性能会逐渐退化。DIC技术可以用于监测疲劳加载条件下FPZ的演化过程，研究疲劳裂缝扩展速率与应力强度因子之间的关系（Paris定律），为混凝土结构的疲劳寿命预测提供实验数据。

## 8. 设备技术参数

| 参数项 | XTDIC-CONST-SD | XTDIC-CONST-HR |
|--------|---------------|---------------|
| 相机像素 | 230万-500万 | ≤2500万 |
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
| 试验机接口 | 支持荷载、位移信号同步采集 |

## 9. 参考文献

[1] Sutton M A, et al. Image Correlation for Shape, Motion and Deformation Measurements. Springer, 2009.

[2] Lecompte D, et al. DIC-based fracture criteria for concrete. Eng Fract Mech, 2015, 141: 1-15.

[3] 李等. 基于DIC的混凝土断裂过程区演化规律. 工程力学, 2022, 39(4): 112-120.

[4] Xu M L, et al. Multiscale DIC for concrete interfacial transition zone. Cem Concr Res, 2023, 169: 107189.

[5] Smith J, et al. 3D fracture network reconstruction with X-ray tomography. Acta Mater, 2021, 215: 117053.

[6] Yu Q, et al. Energy-based failure prediction of concrete. Constr Build Mater, 2024, 411: 134444.

[7] Chen等. Deep Crack U-Net for damage segmentation. Autom Constr, 2025, 142: 104589.

[8] Frost & Sullivan. Structural Health Monitoring Market Outlook. 2025.

[9] MarketsandMarkets™. DIC in Civil Engineering, 2024.

[10] 刘倩. Automation in Construction, 2025.

[11] Pijaudier-Cabot. Journal of Mechanics and Physics of Solids, 2022.

## 10. 结语

混凝土三点弯曲试验中的断裂过程区演化分析，是理解混凝土断裂破坏机理和建立断裂准则的基础。DIC技术以其非接触、全场、高精度的测量能力，克服了传统接触式传感器在混凝土断裂研究中离散采样、量程有限、干扰裂缝扩展等局限，为FPZ的精确量化提供了全新的技术手段。

从普通混凝土的双K断裂参数测量到再生骨料混凝土的裂缝扩展追踪，从活性粉末混凝土的断裂性能研究到高温下混凝土断裂韧度的退化评估，DIC技术可以在不干扰试件自然断裂过程的前提下，同步获取裂缝尖端附近的全场位移和应变分布数据。随着国产DIC设备在测量精度、软件功能和工程适应性方面的持续提升，这项技术有望在混凝土断裂力学研究和工程结构安全评估中发挥越来越重要的作用。

---

</details>

---

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

# DIC Technology in Concrete Three-Point Bending and Fracture Evolution Analysis

> [!TIP]
> **Language / 请选择语言:** [中文版](#chinese-version)

## Table of Contents

- [1. Introduction: Measurement Challenges in Concrete Fracture Mechanics](#1-introduction-measurement-challenges-in-concrete-fracture-mechanics)
- [2. Mechanical Fundamentals of Concrete Three-Point Bending Tests](#2-mechanical-fundamentals-of-concrete-three-point-bending-tests)
- [3. Limitations of Traditional Measurement Methods in Concrete Fracture Research](#3-limitations-of-traditional-measurement-methods-in-concrete-fracture-research)
- [4. Core Capabilities of DIC in Concrete Fracture Evolution Analysis](#4-core-capabilities-of-dic-in-concrete-fracture-evolution-analysis)
- [5. DIC Quantification Methods for Fracture Process Zone (FPZ)](#5-dic-quantification-methods-for-fracture-process-zone-fpz)
- [6. XTDIC System Implementation in Concrete Three-Point Bending Tests](#6-xtdic-system-implementation-in-concrete-three-point-bending-tests)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
- [8. Device Technical Specifications](#8-device-technical-specifications)
- [9. References](#9-references)
- [10. Conclusion](#10-conclusion)

---

## 1. Introduction: Measurement Challenges in Concrete Fracture Mechanics

Concrete is the most widely used construction material in the world, from high-rise buildings to long-span bridges, from hydraulic structures to infrastructure. The safety assessment of concrete structures has always been a core topic in civil engineering. However, concrete is not an ideal elastic material—it is a typical quasi-brittle composite with asymmetric tension-compression behavior, containing numerous microcracks, pores, and interfacial transition zones (ITZ) between aggregate and mortar, making its fracture behavior far more complex than ductile materials like metals.

Concrete fracture failure does not occur suddenly but progresses through a gradual process of crack initiation, stable propagation, and unstable propagation. Ahead of the crack tip, there exists a microcrack concentration zone known as the Fracture Process Zone (FPZ), where various energy dissipation mechanisms occur including aggregate bridging, crack blunting, and microcracking. The size, morphology, and evolution of the FPZ directly determine the macroscopic fracture toughness and size effect characteristics of concrete, making it a central topic in concrete fracture mechanics research.

Precise measurement of FPZ evolution requires full-field displacement and strain distribution data near the crack tip. Traditional contact measurement methods—strain gauges, clip gauges, LVDT displacement transducers—can only provide discrete point measurements, failing to capture the spatial distribution and temporal evolution of the FPZ. Digital Image Correlation (DIC), with its non-contact, full-field, and high-precision measurement capabilities, provides an entirely new technical approach for quantitative analysis of the concrete fracture process zone.

## 2. Mechanical Fundamentals of Concrete Three-Point Bending Tests

### 2.1 Three-Point Bending Test Standards

The three-point bending test is a standard method for evaluating the flexural strength and crack propagation behavior of concrete beams. According to the "Hydraulic Concrete Fracture Test Code" (DL/T 5332-2005) and the international recommendation RILEM TC-89 FMT, standard three-point bending specimens typically use beam specimens with span-to-depth ratios of 4 or 8, with an initial notch precut at the bottom center (notch-to-depth ratio a₀/h typically 0.3-0.5), and a concentrated load applied at midspan through a universal testing machine.

Standard specimen dimensions are typically: height H=100-400mm, width B=100-200mm, span S=400-1600mm (corresponding to span-to-depth ratios of 4-8), initial crack length a₀=30-200mm. Loading rate is controlled at 0.05-0.1mm/min (displacement control mode) to ensure quasi-static loading conditions.

### 2.2 Key Fracture Parameters

The three-point bending test can obtain the following key fracture mechanics parameters:

**Initiation Toughness K_ini^IC**: The stress intensity factor at which cracks begin stable propagation, reflecting the concrete's resistance to crack initiation. Research shows that initiation toughness is independent of specimen size and can be used as a material constant for concrete.

**Unstable Toughness K_un^IC**: The stress intensity factor corresponding to unstable crack propagation (peak load moment), reflecting the concrete's resistance to rapid crack propagation. Unstable toughness is related to specimen size, showing significant size effects.

**Fracture Energy G_F**: Defined as the ratio of the area under the load-deflection curve to the fracture surface area, reflecting the energy consumed per unit area during crack propagation. The fracture energy of normal concrete is approximately 50-150 N/m.

**Crack Mouth Opening Displacement (CMOD)**: The opening displacement at the precut notch tip, a key indicator for assessing crack propagation state. Critical crack mouth opening displacement CMOD_c corresponds to the peak load moment.

**Crack Tip Opening Displacement (CTOD)**: The opening displacement at the crack tip, directly reflecting the stress concentration at the crack tip.

### 2.3 Double-K Fracture Model

The double-K fracture model proposed by Wu Zhimin and colleagues divides the concrete fracture process into two stages: the initiation stage (K_I < K_ini^IC, stable crack propagation) and the unstable stage (K_I ≥ K_un^IC, rapid crack propagation). This model describes concrete fracture characteristics through two parameters—initiation toughness and unstable toughness—and has been incorporated into the "Hydraulic Concrete Fracture Test Code."

An important characteristic of the double-K fracture parameters is that the initiation toughness K_ini^IC is a constant independent of specimen height within the initial notch-to-depth ratio range a₀/h=0.3-0.5, and the unstable toughness K_un^IC is also independent of specimen height and initial notch-to-depth ratio. This makes the double-K fracture parameters suitable as material constants for concrete, applicable to fracture analysis of structures with different sizes.

## 3. Limitations of Traditional Measurement Methods in Concrete Fracture Research

### 3.1 Strain Gauge Limitations

Strain gauges are the most commonly used local deformation measurement tools in concrete testing, but they have obvious shortcomings in fracture research:

Discrete sampling deficiency: Strain gauges can only measure local strain near the attachment point, while the FPZ width is typically only a few millimeters to tens of millimeters. Strain gauges struggle to precisely cover the FPZ area. If the gauge attachment position deviates from the FPZ, the measurement data will not reflect the true strain field at the crack tip.

Range limitation: Normal strain gauges have a range of typically less than 5%, while local strains within the FPZ can far exceed this value (concrete cracking strains can reach over 10%), causing strain gauges to fail prematurely during crack propagation.

### 3.2 Clip Gauge Limitations

Clip gauges are typically installed at the precut notch mouth to measure CMOD and are standard equipment in three-point bending tests. However, their limitations include:

Single-point measurement: Clip gauges can only measure the opening displacement at the notch mouth and cannot obtain strain distribution within the FPZ. For studying FPZ evolution, single-point data is far from sufficient.

Contact requirement: Clip gauges need to be installed on the specimen surface, and the installation position and contact force may affect the natural crack propagation path.

### 3.3 LVDT Displacement Transducer Limitations

LVDT displacement transducers can measure displacement at specific positions of the specimen but similarly only provide discrete point measurements. In concrete fracture research, LVDTs are typically used to measure midspan deflection and cannot obtain full-field deformation information in the FPZ region.

### 3.4 Limitations of Photoelastic and Moiré Interferometry Methods

Photoelastic and moiré interferometry methods can obtain full-field deformation information but require specialized specimen preparation (such as attaching gratings or coating photosensitive materials). The equipment is complex and sensitive to environmental vibration, making them unsuitable for concrete, which has rough surfaces and large deformations.

## 4. Core Capabilities of DIC in Concrete Fracture Evolution Analysis

### 4.1 Non-Contact Full-Field Deformation Measurement

DIC's most prominent advantage is its non-contact, full-field measurement capability. In concrete three-point bending tests, the DIC system captures speckle images of the specimen surface through cameras without requiring any sensors on the specimen surface. This characteristic is particularly important for concrete fracture research—any sensors installed on the specimen surface may interfere with natural crack propagation, while DIC completely avoids this problem.

A single DIC measurement can obtain 2D or 3D displacement data for hundreds of thousands of measurement points within the field of view, with spatial resolution reaching sub-millimeter levels. For FPZ measurement, DIC can completely present the strain concentration zone near the crack tip, precisely identifying the FPZ boundary and evolution process.

### 4.2 Real-Time Crack Initiation and Propagation Tracking

DIC technology can track the initiation and propagation of concrete surface cracks in real time. By analyzing displacement field changes between adjacent images, DIC can precisely identify the location and timing of crack initiation, tracking the path and velocity of crack propagation.

Research shows that DIC methods can effectively capture the crack propagation process, and the CMOD values measured by DIC agree well with those from clip gauges. The CTOD values measured by DIC also show consistent trends with calculated values, verifying the accuracy of DIC technology in concrete fracture measurement.

### 4.3 Precise Quantification of FPZ Size and Morphology

The full-field displacement and strain data obtained by DIC can be directly used for quantitative analysis of FPZ size. By analyzing the strain distribution near the crack tip, the FPZ length (along the crack propagation direction) and width (perpendicular to the crack direction) can be determined, along with the evolution of FPZ area during loading.

Research shows that the critical FPZ length at peak load increases gradually with specimen height, and the critical damage area increases correspondingly, but the ratio of critical FPZ length to specimen height tends to stabilize with increasing specimen height. DIC technology provides a reliable measurement means for experimental verification of this law.

### 4.4 Multi-Scale Measurement Capability

Concrete fracture involves multi-scale processes from microscopic (micrometer scale, ITZ microcracks) to macroscopic (centimeter scale, FPZ and crack propagation). DIC technology, with different camera lenses and measurement fields of view, can achieve cross-scale measurements from a few millimeters to tens of meters. For concrete three-point bending tests, DIC can flexibly adjust the measurement field of view—from small fields (tens of millimeters) focusing on the local FPZ region to large fields (hundreds of millimeters) covering the entire specimen.

### 4.5 Synergy with Acoustic Emission and Other Techniques

DIC technology can be used in conjunction with Acoustic Emission (AE) technology to achieve multi-physical quantity synchronous monitoring of concrete fracture processes. DIC provides full-field deformation and crack morphology information, while AE provides acoustic emission signals from microcrack initiation and propagation. Combining both techniques provides a more comprehensive understanding of the microscopic mechanisms of concrete fracture.

## 5. DIC Quantification Methods for Fracture Process Zone (FPZ)

### 5.1 FPZ Identification Criteria

Using DIC data to identify FPZ boundaries, there are mainly the following criteria:

**Strain threshold criterion**: When local strain exceeds a certain threshold (such as the ultimate tensile strain of concrete, approximately 100-200 με), the point is considered to have entered the FPZ. This method is simple and intuitive, but the choice of threshold significantly affects the results.

**Displacement discontinuity criterion**: When a sudden change in displacement difference occurs between adjacent measurement points, a crack is considered to exist at that location. This method can directly identify crack positions but is sensitive to the noise level of DIC data.

**Strain gradient criterion**: The strain gradient is maximum at the FPZ boundary, and analyzing the gradient distribution of the strain field can determine the FPZ boundary. This method has better robustness against noise.

### 5.2 FPZ Length and Width Measurement

FPZ length is defined as the distance from the crack tip to the FPZ tail (where strain returns to the matrix strain level). DIC can determine the FPZ length by analyzing the strain distribution curve near the crack tip.

FPZ width is defined as the maximum width of the FPZ perpendicular to the crack propagation direction. DIC can determine the FPZ width and its variation along the crack propagation direction by analyzing strain distributions at different cross-sections.

Research shows that the fully developed FPZ length is approximately equal under static and fatigue loading conditions, while free crack unstable propagation occurs only in medium and large-sized specimens.

### 5.3 DIC Calculation Method for Double-K Fracture Parameters

Using full-field displacement data obtained by DIC, the double-K fracture parameters can be calculated through the following steps:

1. Determine crack tip position and crack extension length Δa from DIC displacement fields
2. Determine crack mouth opening displacement CMOD and crack tip opening displacement CTOD from DIC strain fields
3. Calculate stress intensity factor K_I using linear elastic fracture mechanics formulas combined with load P recorded by the testing machine
4. Determine initiation toughness K_ini^IC and unstable toughness K_un^IC from the initiation point and peak point of the P-CMOD curve, respectively

### 5.4 DIC Calculation Method for Fracture Energy

Using full-field displacement data obtained by DIC, fracture energy can be calculated more precisely. Traditional methods calculate fracture energy from the area under the load-deflection curve, but deflection measurements typically reflect displacement at only one point (midspan). DIC can obtain full-field displacement distribution across the entire specimen, and combined with testing machine load data, can more precisely calculate the total energy consumed during crack propagation.

## 6. XTDIC System Implementation in Concrete Three-Point Bending Tests

### 6.1 System Configuration

For concrete three-point bending test requirements, the XTDIC system typically employs the following configuration:

**Measurement Head**: Binocular stereo vision measurement head containing two industrial cameras. For concrete three-point bending tests, the XTDIC-CONST-SD series (2.3-5 MP, 163-1500 fps) is recommended as the basic configuration. For FPZ fine measurement requiring higher spatial resolution, the HR series (≤25 MP, 30-42 fps) can be selected.

**Camera Arrangement**: Cameras are installed directly in front of the specimen, with the optical axis perpendicular to the specimen surface (2D-DIC) or symmetrically arranged from both sides (3D-DIC). For three-point bending tests, attention is typically focused on crack propagation and FPZ evolution on the specimen side, so cameras should be arranged facing the specimen side.

**Measurement Field of View**: Depending on specimen size and measurement requirements, the measurement field of view is typically set to 100mm×100mm (focusing on local FPZ) to 500mm×400mm (covering the entire specimen).

### 6.2 Speckle Preparation Scheme

Speckle preparation on concrete surfaces must consider the following factors:

**Speckle Material**: Concrete surfaces are rough and porous, requiring speckle materials with good adhesion and durability. White matte paint is recommended as the base coat, with black matte paint sprayed for the speckle pattern.

**Speckle Pattern**: Speckle particle size must be optimized based on measurement field of view and camera resolution. For a 100mm×100mm small field of view (FPZ fine measurement), speckle particle size is typically 0.1-0.3mm; for a 500mm×400mm large field of view (entire specimen), speckle particle size is typically 0.5-1mm.

**Speckle Area**: The speckle area must cover the entire region on the specimen side from the precut notch to the expected crack propagation path. For standard three-point bending specimens, the speckle area is typically a rectangular region of specimen height × (span/2).

### 6.3 Loading Synchronization

The DIC system synchronizes with the universal testing machine via external trigger signals, ensuring temporal alignment of deformation data with load data. The load and displacement signals output by the testing machine are input to the DIC system through an A/D acquisition card, recorded synchronously with image acquisition.

### 6.4 Data Processing Workflow

1. Image acquisition: Capture specimen surface speckle images at a set frame rate (typically 1-10 fps; concrete quasi-static tests do not require high frame rates)
2. Displacement field calculation: Calculate displacement fields between adjacent images through DIC algorithms
3. Strain field calculation: Smooth the displacement field and perform numerical differentiation to calculate strain fields
4. Crack identification: Identify crack positions and FPZ boundaries through displacement discontinuity criteria or strain threshold criteria
5. Parameter extraction: Calculate FPZ length, width, CMOD, CTOD, and other fracture parameters
6. Result visualization: Generate displacement fields, strain fields, crack propagation paths, and other visualization results

## 7. Typical Application Scenarios

### 7.1 Normal Concrete Fracture Performance Research

DIC technology is widely used in normal concrete three-point bending fracture tests, measuring FPZ evolution, calculating double-K fracture parameters and fracture energy. Through DIC full-field measurement, the effects of water-cement ratio, aggregate type, aggregate size, and other factors on concrete fracture performance can be studied.

### 7.2 Recycled Aggregate Concrete Fracture Performance Research

The fracture performance of recycled aggregate concrete differs significantly from normal concrete. DIC technology can be used to study the effects of different recycled coarse aggregate replacement ratios (0%, 30%, 50%, 70%, 100%) on concrete fracture parameters. Research shows that when the recycled aggregate replacement ratio is 100%, the initiation toughness and unstable toughness decrease by 15.81% and 15.39%, respectively. DIC methods can effectively capture the crack propagation process in recycled aggregate concrete, and the CMOD values agree well with clip gauge measurements.

### 7.3 Reactive Powder Concrete (RPC) Fracture Performance Research

Reactive Powder Concrete is an ultra-high-performance concrete whose fracture performance differs significantly from normal concrete. DIC technology can be used to study the effects of crushed stone content, water-cement ratio, concrete strength, and other factors on RPC fracture performance, providing experimental data support for RPC material optimization design.

### 7.4 Fiber-Reinforced Concrete Fracture Performance Research

The fracture behavior of fiber-reinforced concrete (such as steel fiber concrete, PVA fiber concrete) involves complex energy dissipation mechanisms including fiber bridging and fiber pullout. DIC technology can measure the FPZ evolution process of fiber-reinforced concrete, studying the effects of fiber type, fiber content, fiber orientation, and other factors on FPZ size and fracture toughness.

### 7.5 High-Temperature Concrete Fracture Performance Research

Under extreme conditions such as fire, the fracture performance of concrete structures degrades significantly. DIC technology can be used to study the effects of different temperatures (from 25°C to 680°C and higher) on concrete fracture toughness and fracture energy. Research shows that high temperatures above 600°C can reduce concrete fracture toughness by approximately 90% and fracture energy by approximately 30-50%.

### 7.6 Concrete Fatigue Fracture Research

Under repeated loading, the fracture performance of concrete gradually degrades. DIC technology can be used to monitor the FPZ evolution process under fatigue loading conditions, studying the relationship between fatigue crack propagation rate and stress intensity factor (Paris law), providing experimental data for fatigue life prediction of concrete structures.

## 8. Device Technical Specifications

| Parameter | XTDIC-CONST-SD | XTDIC-CONST-HR |
|-----------|---------------|---------------|
| Camera Resolution | 2.3-5 MP | ≤25 MP |
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
| Testing Machine Interface | Supports synchronous load and displacement signal acquisition |

## 9. References

[1] Sutton M A, et al. Image Correlation for Shape, Motion and Deformation Measurements. Springer, 2009.

[2] Lecompte D, et al. DIC-based fracture criteria for concrete. Eng Fract Mech, 2015, 141: 1-15.

[3] Li et al. FPZ evolution in concrete based on DIC. Engineering Mechanics, 2022, 39(4): 112-120. (in Chinese)

[4] Xu M L, et al. Multiscale DIC for concrete interfacial transition zone. Cem Concr Res, 2023, 169: 107189.

[5] Smith J, et al. 3D fracture network reconstruction with X-ray tomography. Acta Mater, 2021, 215: 117053.

[6] Yu Q, et al. Energy-based failure prediction of concrete. Constr Build Mater, 2024, 411: 134444.

[7] Chen et al. Deep Crack U-Net for damage segmentation. Autom Constr, 2025, 142: 104589.

[8] Frost & Sullivan. Structural Health Monitoring Market Outlook. 2025.

[9] MarketsandMarkets™. DIC in Civil Engineering, 2024.

[10] Liu Q. Automation in Construction, 2025.

[11] Pijaudier-Cabot. Journal of Mechanics and Physics of Solids, 2022.

## 10. Conclusion

Fracture Process Zone evolution analysis in concrete three-point bending tests is fundamental to understanding concrete fracture failure mechanisms and establishing fracture criteria. DIC technology, with its non-contact, full-field, and high-precision measurement capabilities, overcomes the limitations of traditional contact sensors in concrete fracture research—including discrete sampling, limited range, and interference with crack propagation—providing an entirely new technical approach for precise FPZ quantification.

From double-K fracture parameter measurement in normal concrete to crack propagation tracking in recycled aggregate concrete, from fracture performance research in reactive Powder Concrete to degradation assessment of concrete fracture toughness at high temperatures, DIC technology can synchronously acquire full-field displacement and strain distribution data near the crack tip without interfering with the natural fracture process. As domestic DIC equipment continues to improve in measurement precision, software functionality, and engineering adaptability, this technology is expected to play an increasingly important role in concrete fracture mechanics research and engineering structural safety assessment.

---

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D concrete fracture testing application documentation*
