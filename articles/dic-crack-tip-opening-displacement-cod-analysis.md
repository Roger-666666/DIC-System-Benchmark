# DIC技术用于金属材料裂纹尖端张开位移（COD）分析

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：COD——断裂力学的安全密码](#1-引言cod断裂力学的安全密码)
- [2. COD的物理意义与理论基础](#2-cod的物理意义与理论基础)
- [3. 传统COD测量方法的局限](#3-传统cod测量方法的局限)
- [4. DIC技术测量COD的核心优势](#4-dic技术测量cod的核心优势)
- [5. DIC测量COD的关键技术环节](#5-dic测量cod的关键技术环节)
- [6. XTDIC系统在COD测量中的实施方案](#6-xtdic系统在cod测量中的实施方案)
- [7. 典型应用场景](#7-典型应用场景)
- [8. 实验设计与数据处理](#8-实验设计与数据处理)
- [9. 结语](#9-结语)

---

## 1. 引言：COD——断裂力学的安全密码

裂纹尖端张开位移（Crack Tip Opening Displacement，COD）是断裂力学中评估含裂纹结构安全性的核心参数之一。它的物理含义直观而深刻：当裂纹尖端在外载荷作用下发生塑性变形时，裂纹两侧表面之间的张开位移量——这个位移量直接反映了裂纹尖端的应力应变状态，是判断裂纹是否会发生失稳扩展的关键指标。

COD概念最早由Wells在1960年代提出，最初是为了解决传统线弹性断裂力学（LEFM）在弹塑性材料中的局限性。对于高强度低韧性材料，裂纹尖端的塑性区尺寸可能远小于裂纹长度，LEFM仍然适用；但对于工程中广泛使用的中低强度钢、铝合金、钛合金等材料，裂纹尖端的塑性区尺寸可能达到与裂纹长度相当的量级，此时LEFM的K因子判据不再适用，COD提供了一个更直接的弹塑性断裂判据。

在实际工程中，COD测量广泛应用于以下场景：焊接接头断裂韧性评估（焊缝及热影响区是裂纹萌生的典型位置）、压力容器安全评定（ASME和R6方法均使用COD作为评定参数）、管道完整性评估（油气管道中的腐蚀裂纹和疲劳裂纹）、航空航天结构损伤容限设计（含裂纹结构的剩余强度评估）。准确测量COD值，是建立材料断裂韧性数据库、制定结构安全评定标准、预测含裂纹结构服役寿命的基础。

然而，COD的精确测量一直是实验力学中的难点。裂纹尖端附近的应变场高度集中，应变梯度极大，传统测量方法难以捕捉裂纹尖端的完整位移场。数字图像相关（DIC）技术以其全场、非接触、高分辨的测量能力，为COD测量提供了全新的技术途径。

## 2. COD的物理意义与理论基础

### 2.1 COD的定义

裂纹尖端张开位移（COD）通常用符号δ表示，其定义为：在裂纹尖端位置，裂纹两侧表面之间的相对位移。根据定义方式的不同，COD可以分为以下几种：

**裂纹尖端张开位移（CTOD，δ_tip）**：直接在裂纹尖端测量的张开位移。这是COD最原始的定义，但在实验中难以精确确定裂纹尖端的准确位置。

**裂纹口张开位移（CMOD，δ_mouth）**：在裂纹口部（试样表面裂纹开口处）测量的张开位移。CMOD是实验中最容易测量的COD相关参数，通常通过夹式引伸计（clip gauge）测量。

**等效裂纹尖端张开位移（δ_5）**：在裂纹前方5mm处测量的等效张开位移。这是BS 7448标准中采用的COD定义，用于消除裂纹尖端位置不确定性的影响。

**J积分与COD的关系**：在弹塑性断裂力学中，J积分与COD之间存在以下关系：

J = m · σ_y · δ

其中，m为约束因子（通常取1.0-2.5，取决于试样几何和材料），σ_y为材料的屈服强度，δ为COD值。这一关系建立了COD与能量释放率之间的桥梁，使得COD可以作为弹塑性断裂判据使用。

### 2.2 COD在断裂判据中的应用

COD断裂判据的基本形式为：

δ ≥ δ_c

其中，δ为裂纹尖端的张开位移（工作COD），δ_c为材料的临界COD值（断裂韧性）。当工作COD达到或超过临界COD值时，裂纹将发生失稳扩展。

临界COD值δ_c是材料的固有属性，取决于材料的化学成分、微观组织、温度和加载速率。典型材料的临界COD值范围：

| 材料 | 临界COD值δ_c（mm） | 说明 |
|------|---------------------|------|
| 高强度钢（σ_y > 800MPa） | 0.01-0.10 | 低韧性，脆断倾向 |
| 中低强度钢（σ_y 300-600MPa） | 0.10-0.50 | 中等韧性 |
| 船用钢/压力容器钢 | 0.15-0.80 | 高韧性要求 |
| 铝合金（2xxx/7xxx系） | 0.05-0.30 | 取决于热处理状态 |
| 钛合金（Ti-6Al-4V） | 0.10-0.40 | 高强度高韧性 |
| 奥氏体不锈钢 | 0.30-1.00 | 极高韧性 |

### 2.3 COD测试标准体系

COD测量遵循一系列国际和国家标准：

**BS 7448**（英国标准）：断裂韧性测试的系列标准，Part 1规定了三点弯曲试样的COD测试方法，是目前国际上最广泛使用的COD测试标准。

**ASTM E1290**（美国标准）：裂纹尖端张开位移（CTOD）测试的标准试验方法，适用于金属材料的三点弯曲试样。

**ISO 12135**（国际标准）：金属材料准静态断裂韧性测试的统一方法，包含COD测试方法。

**GB/T 21143**（中国标准）：金属材料准静态断裂韧度的统一试验方法，等效采用ISO 12135。

**GB/T 19748**（中国标准）：钢材夏比摆锤冲击试验方法，包含COD测试相关内容。

这些标准对试样几何、加载速率、温度控制、COD测量方法和数据处理程序都有严格规定，确保不同实验室获得的COD数据具有可比性。

## 3. 传统COD测量方法的局限

### 3.1 夹式引伸计（Clip Gauge）

夹式引伸计是COD测量中最常用的传统工具，安装在裂纹口部的刀口上，直接测量裂纹口张开位移（CMOD）。

**优点**：结构简单、成本低、操作便捷、动态响应好。

**局限**：

**单点测量**：只能测量裂纹口一个位置的张开位移，无法获取裂纹尖端附近的完整位移场。对于非对称裂纹、三维裂纹或复杂几何试样，单一CMOD值可能无法准确反映裂纹尖端的实际张开位移。

**间接推算**：CTOD通常通过CMOD间接推算获得，推算公式依赖于试样几何和材料本构关系的假设。对于弹塑性材料，CTOD与CMOD之间的换算关系受塑性区尺寸影响，存在一定误差。

**安装要求高**：需要在试样裂纹口部安装刀口（knife edge），刀口的几何精度和安装质量直接影响测量结果。刀口安装不当可能引入附加约束，影响裂纹尖端的应力应变状态。

**量程限制**：夹式引伸计的量程有限（通常±2.5mm或±5mm），对于大变形试样可能超出量程。

**无法测量裂纹尖端应变场**：夹式引伸计只能测量位移，无法获得裂纹尖端的应变分布，而应变场信息对于理解裂纹尖端塑性变形机制至关重要。

### 3.2 电位法（DCPD）

电位法（Direct Current Potential Drop）通过测量裂纹扩展过程中电位差的变化来间接推算COD。

**局限**：需要通电、受温度影响大、只能间接推算裂纹长度和COD、无法获得位移场信息。

### 3.3 柔度法

柔度法通过测量试样的载荷-位移曲线，利用裂纹扩展前后的柔度变化来推算COD。

**局限**：间接测量、需要标定曲线、无法获得裂纹尖端附近的局部位移场信息。

### 3.4 光弹性法

光透明材料的光弹性法可以显示裂纹尖端的应力分布，但：

**局限**：仅适用于透明材料、无法直接测量COD、制样复杂、定量精度有限。

## 4. DIC技术测量COD的核心优势

### 4.1 全场位移测量：从"点"到"面"的跨越

DIC技术最根本的优势在于其全场测量能力。在COD测量中，DIC可以同时获取裂纹尖端附近整个区域的位移场，包括：

**裂纹面位移分布**：沿裂纹面的位移分布，直接反映裂纹的张开程度。通过分析裂纹面位移分布，可以精确确定裂纹尖端的张开位移（CTOD），无需间接推算。

**裂纹尖端塑性区**：裂纹尖端附近的塑性变形区域，其尺寸和形状反映了材料的塑性变形能力。DIC可以直观显示塑性区的尺寸和应变分布。

**远场位移**：远离裂纹区域的位移场，用于验证边界条件和分析试样的整体变形行为。

**三维位移**：通过双目立体视觉配置，DIC可以同时获取面内位移和面外位移，全面描述裂纹尖端的三维变形状态。

### 4.2 高空间分辨率：捕捉应变集中区

裂纹尖端的应变集中是COD测量的核心挑战。在裂纹尖端附近，应变梯度极大——从弹性应变（<0.2%）到塑性应变（>10%）的变化可能发生在亚毫米尺度内。

DIC通过以下方式应对这一挑战：

**亚像素位移分辨**：现代DIC算法的位移分辨力可达0.01像素甚至更高。对于典型的COD测量配置（视野20-50mm，相机分辨率2048×2048），空间分辨力可达1-2.5μm，足以分辨裂纹尖端的应变梯度。

**自适应子区尺寸**：在裂纹尖端附近使用较小的DIC子区（如15×15像素），提高空间分辨力；在远场区域使用较大的子区（如31×31像素），提高测量精度。

**多尺度测量**：对于需要极高空间分辨力的场景（如微裂纹、焊接接头微区），可以结合XTDIC-MICRO显微DIC系统，实现微米级空间分辨力。

### 4.3 直接CTOD测量：消除间接推算误差

DIC可以直接在裂纹尖端位置测量裂纹两侧的相对位移，获得真实的CTOD值，无需通过CMOD间接推算。这一优势消除了传统方法中因换算公式假设引入的误差，特别是在以下场景中尤为重要：

**弹塑性材料**：对于弹塑性材料，CTOD与CMOD之间的换算关系受塑性区尺寸和材料硬化行为影响，间接推算误差较大。DIC直接测量CTOD，避免了这一问题。

**非标准试样**：对于非标准几何的试样（如管道裂纹、焊接接头裂纹），CTOD与CMOD之间的换算关系可能没有标准公式，DIC直接测量是唯一可靠的方法。

**三维裂纹**：对于表面裂纹或角裂纹等三维裂纹，裂纹尖端不同深度位置的CTOD不同，DIC可以测量沿裂纹前缘的CTOD分布。

### 4.4 裂纹尖端定位与裂纹扩展追踪

DIC全场位移数据可以用于：

**精确裂纹尖端定位**：通过分析位移场的奇异性和应变集中特征，可以精确确定裂纹尖端的位置，精度可达微米级。

**裂纹扩展追踪**：在疲劳裂纹扩展试验中，DIC可以实时追踪裂纹尖端位置的变化，测量裂纹扩展速率（da/dN）。

**裂纹闭合效应分析**：在疲劳裂纹扩展过程中，裂纹在卸载阶段可能部分闭合。DIC可以测量裂纹闭合程度，分析裂纹闭合效应对有效应力强度因子范围的影响。

### 4.5 全场应变分析：深入理解断裂机制

DIC获得的位移场可以通过微分计算得到全场应变分布，为断裂机制分析提供丰富信息：

**塑性区尺寸测量**：通过应变场确定裂纹尖端塑性区的尺寸和形状，验证Irwin塑性区模型的适用性。

**应变集中系数**：裂纹尖端的应变集中系数反映了应力集中的程度，是评估材料断裂韧性的重要参考。

**裂纹尖端张开角（CTOA）**：除了COD，裂纹尖端张开角（CTOA）也是断裂力学中的重要参数。DIC可以同时测量COD和CTOA，提供更完整的裂纹尖端变形信息。

## 5. DIC测量COD的关键技术环节

### 5.1 试样准备与散斑制备

COD测试通常使用标准三点弯曲试样（SE(B)试样）或紧凑拉伸试样（CT试样）。DIC测量的散斑制备需要考虑以下因素：

**散斑区域**：散斑需要覆盖裂纹尖端附近的区域，通常以裂纹尖端为中心，向两侧各延伸10-20mm。对于标准三点弯曲试样（B×W=25×50mm），散斑区域约为20×40mm。

**散斑质量**：裂纹尖端的应变梯度极大，要求散斑具有高质量（高对比度、随机性好、散斑尺寸均匀）。推荐使用喷涂法或转印法制备散斑。

**裂纹尖端散斑**：裂纹尖端附近的散斑需要特别注意——散斑不能跨越裂纹面（否则会影响裂纹面的位移测量），但需要尽可能靠近裂纹尖端。推荐在裂纹两侧分别制备散斑，散斑边缘距离裂纹面约0.1-0.3mm。

**散斑尺寸**：散斑大小需要与相机分辨率和DIC子区尺寸匹配。对于COD测量，推荐散斑大小为3-5像素，DIC子区为15-21像素。

### 5.2 成像系统配置

**相机分辨率**：COD测量需要足够的空间分辨力来分辨裂纹尖端的应变梯度。推荐使用高分辨率相机（≥5MP），配合适当的镜头，使裂纹尖端附近的空间分辨力达到5-10μm。

**XTDIC-CONST-HR系列**（≤25MP，30-42fps，20με应变精度）是COD测量的理想选择——高像素密度提供足够的空间分辨力，20με的应变精度足以分辨裂纹尖端的应变集中。

**帧率选择**：对于准静态COD试验（加载速率通常为0.5-2mm/min），帧率不需要很高（1-10fps即可）。对于动态断裂试验，需要高速相机（>1000fps）。

**镜头选择**：根据试样尺寸和相机安装距离选择合适的镜头。对于标准三点弯曲试样，推荐使用50-100mm焦距镜头，确保裂纹尖端区域占据足够的像素。

**照明**：COD测量需要稳定的照明条件。推荐使用LED面光源或光纤光源，提供均匀、稳定的照明。避免使用可能产生热量影响试样温度的光源。

### 5.3 标定与精度验证

**系统标定**：使用标定板对成像系统进行标定，确定相机内外参数和畸变系数。标定精度直接影响COD测量精度。

**精度验证**：在正式试验前，使用已知位移的标定试样或刚性位移验证试验，验证系统的位移和应变测量精度。

**刚体位移消除**：COD测量中，试样的刚体位移（平移和转动）需要从总位移中消除，以获得纯变形位移。DIC软件通常提供刚体位移消除功能。

### 5.4 COD计算方法

DIC获得全场位移数据后，COD的计算方法主要有以下几种：

**直接测量法**：在裂纹尖端位置，直接测量裂纹两侧对应点之间的相对位移。这种方法简单直观，但需要精确确定裂纹尖端位置。

**拟合法**：对裂纹面位移数据进行拟合，外推到裂纹尖端位置，获得CTOD值。这种方法可以消除裂纹尖端位置不确定性的影响。

**J积分法**：利用DIC全场数据计算J积分，然后通过J-δ关系换算获得COD值。这种方法适用于弹塑性材料，且不需要精确确定裂纹尖端位置。

**δ_5法**：在裂纹前方5mm处测量等效张开位移，这是BS 7448标准推荐的方法。

## 6. XTDIC系统在COD测量中的实施方案

### 6.1 设备配置

**相机系统**：
- 推荐使用XTDIC-CONST-HR系列（≤25MP，30-42fps，20με应变精度）
- 高分辨率确保裂纹尖端附近的空间分辨力
- 单目或双目配置（单目用于二维COD测量，双目用于三维COD测量）

**镜头**：50-100mm焦距镜头，根据试样尺寸选择

**照明**：LED面光源，均匀照明裂纹尖端区域

**加载设备**：万能试验机，配备三点弯曲试验装置或紧凑拉伸试验装置

**数据采集**：DIC软件与试验机同步，记录载荷-位移-COD数据

### 6.2 测量流程

1. **试样准备**：加工标准三点弯曲试样或紧凑拉伸试样，预制疲劳裂纹（使用疲劳试验机在裂纹尖端预制尖锐裂纹）。
2. **散斑制备**：在裂纹尖端附近区域制备高质量散斑。
3. **系统安装**：安装相机、镜头和照明系统，调整成像参数。
4. **系统标定**：使用标定板进行系统标定。
5. **预试验**：进行小载荷预试验，验证系统工作状态。
6. **正式试验**：按标准规定的加载速率进行试验，同步采集DIC图像和载荷-位移数据。
7. **数据处理**：对DIC图像进行分析，计算全场位移和应变，提取COD值。
8. **结果分析**：绘制COD-载荷曲线、COD-裂纹扩展量曲线，确定临界COD值。

### 6.3 关键参数

| 参数 | 典型值 | 说明 |
|------|--------|------|
| 相机分辨率 | ≤25MP | HR系列，确保空间分辨力 |
| 采集帧率 | 1-10fps | 准静态试验 |
| 空间分辨力 | 5-10μm | 裂纹尖端附近 |
| 位移精度 | ≤0.01像素 | 亚像素算法 |
| 应变精度 | 20με | HR系列 |
| COD测量范围 | 0-5mm | 覆盖弹塑性断裂 |
| COD分辨力 | 5-20μm | 取决于空间分辨力 |
| 同步精度 | <1ms | DIC与试验机同步 |

## 7. 典型应用场景

### 7.1 焊接接头断裂韧性评估

焊接接头是工程结构中裂纹萌生的典型位置。焊缝金属、热影响区和母材的力学性能差异显著，裂纹尖端的COD值在不同区域可能有显著不同。

DIC全场测量可以同时获取焊缝区、热影响区和母材区的COD分布，揭示裂纹在不同区域的扩展行为。这对于评估焊接接头的断裂韧性、优化焊接工艺参数具有重要价值。

**工程价值**：传统的夹式引伸计只能测量裂纹口的平均张开位移，无法区分不同区域的COD差异。DIC全场测量提供了更丰富的信息，有助于深入理解焊接接头的断裂机制。

### 7.2 管道裂纹完整性评估

油气管道中的腐蚀裂纹和疲劳裂纹是管道安全的主要威胁。COD测量是管道完整性评估的核心内容，直接决定了管道的最大允许工作压力和剩余寿命。

DIC技术可以在全尺寸管道试验或实验室模拟试验中测量管道裂纹的COD，为管道完整性评估提供关键数据。特别是对于管道中的表面裂纹和穿透裂纹，DIC可以测量沿裂纹前缘的COD分布，揭示裂纹的三维扩展行为。

**工程价值**：管道裂纹的COD测量通常需要在模拟管道内压和轴向载荷的复合加载条件下进行。DIC的非接触测量特性使其特别适合这种复杂加载条件下的COD测量。

### 7.3 压力容器安全评定

压力容器的安全评定（如R6方法和BS 7910方法）使用COD作为评定参数。准确测量材料的临界COD值是安全评定的基础。

DIC技术可以精确测量压力容器材料（如SA-516 Gr.70、16MnR等）在不同温度下的COD值，建立材料的断裂韧性数据库。特别是对于低温工况（如LNG储罐），材料韧性降低，COD测量对于安全评定尤为重要。

**工程价值**：DIC全场测量可以揭示裂纹尖端的塑性变形行为，为理解材料的断裂机制提供实验依据，有助于改进安全评定方法。

### 7.4 航空航天结构损伤容限设计

航空航天结构的损伤容限设计要求准确评估含裂纹结构的剩余强度。COD是损伤容限设计中的关键参数，用于预测裂纹扩展寿命和剩余强度。

DIC技术可以在航空航天材料（如铝合金、钛合金、超高强度钢）的COD测量中提供高精度的全场数据，为损伤容限设计提供可靠的断裂韧性参数。

**工程价值**：航空航天材料的COD测量通常需要在极端温度（高温或低温）条件下进行。DIC的非接触测量特性使其适合在环境箱中进行COD测量。

### 7.5 疲劳裂纹扩展试验

在疲劳裂纹扩展试验中，COD的循环变化（ΔCOD）与裂纹扩展速率（da/dN）之间存在密切关系。DIC可以实时测量疲劳循环过程中COD的变化，分析裂纹闭合效应。

**工程价值**：DIC全场测量可以揭示疲劳裂纹尖端的循环塑性变形行为，为理解疲劳裂纹扩展机制提供实验依据。

## 8. 实验设计与数据处理建议

对于初次在COD测量中引入DIC的工程团队，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑区域 | 以裂纹尖端为中心，覆盖两侧各10-20mm |
| 散斑质量 | 高对比度、随机性好，散斑不跨越裂纹面 |
| 相机分辨率 | ≥5MP，确保裂纹尖端空间分辨力 |
| 裂纹尖端定位 | 通过位移场奇异性和应变集中特征精确定位 |
| COD计算方法 | 推荐使用拟合法或J积分法，消除尖端位置不确定性 |
| 刚体位移消除 | 消除试样刚体位移，获得纯变形位移 |
| 温度控制 | 在恒温环境中进行试验，避免温度波动影响 |
| 加载速率 | 按标准规定控制加载速率，通常0.5-2mm/min |

**入门建议**：从标准三点弯曲试样的准静态COD试验开始，验证DIC测量结果与夹式引伸计的一致性，然后逐步扩展到更复杂的试样和加载条件。

## 9. 结语

裂纹尖端张开位移（COD）是断裂力学中连接材料微观断裂机制与宏观结构安全评定的关键桥梁。精确测量COD值，是建立材料断裂韧性数据库、制定结构安全评定标准、预测含裂纹结构服役寿命的基础。

传统的COD测量方法（夹式引伸计、电位法、柔度法）虽然在某些场景中仍然有效，但其单点测量、间接推算的本质限制了测量精度和信息量。DIC技术通过全场位移测量、高空间分辨率和直接CTOD获取能力，从根本上改变了COD测量的技术范式——从"点"到"面"、从"间接"到"直接"、从"单一参数"到"全场信息"。

XTDIC-CONST-HR系列凭借其≤25MP的高分辨率和20με的应变精度，为COD测量提供了足够的空间分辨力和测量精度。从焊接接头断裂韧性评估到管道完整性评定，从压力容器安全设计到航空航天损伤容限分析，DIC技术正在成为COD测量领域不可替代的工具。

随着断裂力学理论的发展和安全评定方法的精细化，对COD测量精度和信息量的要求将持续提高。DIC技术以其全场、非接触、高分辨的测量能力，将在这一进程中发挥越来越重要的作用——为工程结构的安全设计和智能运维提供更可靠的数据支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: COD—The Safety Code of Fracture Mechanics](#1-introduction-codthe-safety-code-of-fracture-mechanics)
- [2. Physical Significance and Theoretical Foundation of COD](#2-physical-significance-and-theoretical-foundation-of-cod)
- [3. Limitations of Traditional COD Measurement Methods](#3-limitations-of-traditional-cod-measurement-measurement-methods)
- [4. Core Advantages of DIC for COD Measurement](#4-core-advantages-of-dic-for-cod-measurement)
- [5. Key Technical Aspects of DIC COD Measurement](#5-key-technical-aspects-of-dic-cod-measurement)
- [6. XTDIC System Implementation for COD Measurement](#6-xtdic-system-implementation-for-cod-measurement)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
- [8. Experimental Design and Data Processing](#8-experimental-design-and-data-processing)
- [9. Conclusion](#9-conclusion)

---

## 1. Introduction: COD—The Safety Code of Fracture Mechanics

Crack Tip Opening Displacement (COD) is one of the core parameters in fracture mechanics for evaluating the safety of cracked structures. Its physical meaning is intuitive yet profound: when the crack tip undergoes plastic deformation under external loading, the opening displacement between the two crack surfaces directly reflects the stress-strain state at the crack tip, serving as a key indicator for determining whether unstable crack propagation will occur.

The COD concept was first proposed by Wells in the 1960s, originally to address the limitations of Linear Elastic Fracture Mechanics (LEFM) in elastic-plastic materials. For high-strength low-toughness materials, plastic zone sizes at crack tips may be much smaller than crack lengths, and LEFM remains applicable. However, for widely used medium-low strength steels, aluminum alloys, and titanium alloys in engineering, plastic zone sizes at crack tips can reach magnitudes comparable to crack lengths. In such cases, LEFM's K-factor criterion is no longer applicable, and COD provides a more direct elastic-plastic fracture criterion.

In practical engineering, COD measurement is widely applied in: welded joint fracture toughness evaluation (weld seams and heat-affected zones are typical crack initiation locations), pressure vessel safety assessment (both ASME and R6 methods use COD as assessment parameters), pipeline integrity evaluation (corrosion cracks and fatigue cracks in oil and gas pipelines), and aerospace structural damage tolerance design (residual strength evaluation of cracked structures). Accurate COD measurement is fundamental for establishing material fracture toughness databases, developing structural safety assessment standards, and predicting service life of cracked structures.

However, precise COD measurement has always been a challenge in experimental mechanics. The strain field near the crack tip is highly concentrated with extreme strain gradients, making it difficult for traditional measurement methods to capture the complete displacement field at the crack tip. Digital Image Correlation (DIC) technology, with its full-field, non-contact, high-resolution measurement capabilities, provides a new technical pathway for COD measurement.

## 2. Physical Significance and Theoretical Foundation of COD

### 2.1 COD Definition

Crack Tip Opening Displacement (COD), typically denoted by δ, is defined as the relative displacement between the two crack surfaces at the crack tip position. Based on different definition methods, COD can be categorized as:

**Crack Tip Opening Displacement (CTOD, δ_tip)**: Opening displacement measured directly at the crack tip. This is the original COD definition, but experimentally determining the exact crack tip position is challenging.

**Crack Mouth Opening Displacement (CMOD, δ_mouth)**: Opening displacement measured at the crack mouth (surface crack opening on the specimen). CMOD is the easiest COD-related parameter to measure experimentally, typically using clip gauges.

**Equivalent Crack Tip Opening Displacement (δ_5)**: Equivalent opening displacement measured 5mm ahead of the crack. This COD definition is adopted in BS 7448 standard to eliminate crack tip position uncertainty effects.

**J-integral and COD Relationship**: In elastic-plastic fracture mechanics, the relationship between J-integral and COD is:

J = m · σ_y · δ

where m is the constraint factor (typically 1.0-2.5, depending on specimen geometry and material), σ_y is the material yield strength, and δ is the COD value. This relationship bridges COD and energy release rate, enabling COD to serve as an elastic-plastic fracture criterion.

### 2.2 COD in Fracture Criteria

The basic COD fracture criterion is:

δ ≥ δ_c

where δ is the working COD at the crack tip, and δ_c is the material's critical COD value (fracture toughness). When working COD reaches or exceeds the critical COD value, unstable crack propagation occurs.

The critical COD value δ_c is an intrinsic material property, dependent on chemical composition, microstructure, temperature, and loading rate. Typical critical COD value ranges:

| Material | Critical COD δ_c (mm) | Notes |
|----------|----------------------|-------|
| High-strength steel (σ_y > 800MPa) | 0.01-0.10 | Low toughness, brittle fracture tendency |
| Medium-low strength steel (σ_y 300-600MPa) | 0.10-0.50 | Moderate toughness |
| Ship steel/Pressure vessel steel | 0.15-0.80 | High toughness requirements |
| Aluminum alloy (2xxx/7xxx series) | 0.05-0.30 | Depends on heat treatment |
| Titanium alloy (Ti-6Al-4V) | 0.10-0.40 | High strength, high toughness |
| Austenitic stainless steel | 0.30-1.00 | Extremely high toughness |

### 2.3 COD Test Standard System

COD measurement follows international and national standards:

**BS 7448** (British Standard): Series standards for fracture toughness testing. Part 1 specifies COD testing methods for three-point bending specimens—the most widely used international COD test standard.

**ASTM E1290** (American Standard): Standard test method for Crack Tip Opening Displacement (CTOD) testing, applicable to three-point bending specimens of metallic materials.

**ISO 12135** (International Standard): Unified method for quasi-static fracture toughness testing of metallic materials, including COD test methods.

**GB/T 21143** (Chinese Standard): Unified test method for quasi-static fracture toughness of metallic materials, equivalently adopted from ISO 12135.

These standards strictly specify specimen geometry, loading rate, temperature control, COD measurement methods, and data processing procedures to ensure comparability of COD data from different laboratories.

## 3. Limitations of Traditional COD Measurement Methods

**Clip gauge**: Single-point measurement only (CMOD), indirect CTOD calculation dependent on assumptions, high installation requirements, limited range, cannot measure crack tip strain fields.

**Potential drop method (DCPD)**: Requires electrical current, highly temperature-dependent, indirect calculation only, no displacement field information.

**Compliance method**: Indirect measurement, requires calibration curves, no local displacement field information near crack tip.

**Photoelastic method**: Only applicable to transparent materials, cannot directly measure COD, complex specimen preparation, limited quantitative precision.

## 4. Core Advantages of DIC for COD Measurement

### 4.1 Full-Field Displacement Measurement: From "Point" to "Surface"

DIC's most fundamental advantage is its full-field measurement capability. In COD measurement, DIC simultaneously obtains displacement fields across the entire crack tip region, including crack surface displacement distribution, crack tip plastic zone, far-field displacement, and 3D displacement through binocular stereo vision.

### 4.2 High Spatial Resolution: Capturing Strain Concentration Zones

Strain concentration at crack tips is the core challenge of COD measurement. Strain gradients are extreme—changes from elastic strain (<0.2%) to plastic strain (>10%) can occur at sub-millimeter scales.

DIC addresses this through sub-pixel displacement resolution (up to 0.01 pixel or better), adaptive subset sizing (smaller subsets near crack tips for higher resolution, larger subsets in far fields for better precision), and multi-scale measurement with XTDIC-MICRO for micro-scale resolution.

### 4.3 Direct CTOD Measurement: Eliminating Indirect Calculation Errors

DIC directly measures relative displacement between crack surfaces at the crack tip, obtaining true CTOD values without indirect CMOD conversion. This eliminates errors from conversion formula assumptions, particularly important for elastic-plastic materials, non-standard specimens, and 3D cracks.

### 4.4 Crack Tip Location and Crack Propagation Tracking

DIC full-field displacement data enables precise crack tip location (through displacement field singularity and strain concentration characteristics, accuracy up to micrometer level), real-time crack tip tracking during fatigue crack propagation tests (measuring da/dN), and crack closure effect analysis.

### 4.5 Full-Field Strain Analysis: Deep Understanding of Fracture Mechanisms

DIC displacement fields can be differentiated to obtain full-field strain distribution, providing rich information for fracture mechanism analysis: plastic zone size measurement, strain concentration factor determination, and Crack Tip Opening Angle (CTOA) measurement alongside COD.

## 5. Key Technical Aspects of DIC COD Measurement

### 5.1 Specimen Preparation and Speckle Fabrication

COD testing typically uses standard three-point bending specimens (SE(B)) or compact tension (CT) specimens. DIC speckle preparation must consider: speckle area coverage (centered on crack tip, extending 10-20mm each side), speckle quality (high contrast, good randomness, uniform size), crack tip speckle (speckles on each side of crack surface without crossing), and speckle size matching camera resolution and DIC subset size.

### 5.2 Imaging System Configuration

**Camera resolution**: ≥5MP recommended for sufficient spatial resolution near crack tip. XTDIC-CONST-HR series (≤25MP, 30-42fps, 20με strain precision) is ideal—high pixel density provides sufficient spatial resolution, 20με strain precision resolves crack tip strain concentration.

**Frame rate**: 1-10fps for quasi-static COD tests (loading rate typically 0.5-2mm/min). High-speed cameras (>1000fps) for dynamic fracture tests.

**Lens**: 50-100mm focal length recommended based on specimen size and camera distance.

**Lighting**: LED panel or fiber optic light sources for uniform, stable illumination.

### 5.3 Calibration and Precision Verification

System calibration using calibration plates, precision verification using known displacement tests, and rigid body displacement elimination are essential for accurate COD measurement.

### 5.4 COD Calculation Methods

After obtaining DIC full-field displacement data, COD calculation methods include: direct measurement method (measuring relative displacement between corresponding points on crack surfaces at crack tip), fitting method (fitting crack surface displacement data and extrapolating to crack tip), J-integral method (calculating J-integral from DIC full-field data, then converting to COD), and δ_5 method (measuring equivalent opening displacement 5mm ahead of crack per BS 7448).

## 6. XTDIC System Implementation for COD Measurement

### 6.1 Equipment Configuration

**Camera system**: Recommended XTDIC-CONST-HR series (≤25MP, 30-42fps, 20με strain precision). High resolution ensures spatial resolution near crack tip. Monocular or binocular configuration (monocular for 2D COD, binocular for 3D COD).

**Lens**: 50-100mm focal length, selected based on specimen size.

**Lighting**: LED panel light source for uniform illumination of crack tip region.

**Loading equipment**: Universal testing machine with three-point bending or compact tension test fixtures.

**Data acquisition**: DIC software synchronized with testing machine, recording load-displacement-COD data.

### 6.2 Measurement Workflow

1. **Specimen preparation**: Process standard three-point bending or compact tension specimens, pre-crack fatigue cracks at crack tips.
2. **Speckle fabrication**: Prepare high-quality speckles in crack tip region.
3. **System installation**: Install camera, lens, and lighting system; adjust imaging parameters.
4. **System calibration**: Calibrate imaging system using calibration plates.
5. **Preliminary testing**: Conduct small-load preliminary tests to verify system operation.
6. **Formal testing**: Conduct tests at standard-specified loading rates, synchronously acquiring DIC images and load-displacement data.
7. **Data processing**: Analyze DIC images, calculate full-field displacement and strain, extract COD values.
8. **Result analysis**: Plot COD-load curves, COD-crack extension curves, determine critical COD values.

### 6.3 Key Parameters

| Parameter | Typical Value | Notes |
|-----------|--------------|-------|
| Camera resolution | ≤25MP | HR series, ensures spatial resolution |
| Acquisition frame rate | 1-10fps | Quasi-static testing |
| Spatial resolution | 5-10μm | Near crack tip |
| Displacement precision | ≤0.01 pixel | Sub-pixel algorithm |
| Strain precision | 20με | HR series |
| COD measurement range | 0-5mm | Covers elastic-plastic fracture |
| COD resolution | 5-20μm | Depends on spatial resolution |
| Synchronization precision | <1ms | DIC and testing machine |

## 7. Typical Application Scenarios

### 7.1 Welded Joint Fracture Toughness Evaluation

Welded joints are typical crack initiation locations in engineering structures. DIC full-field measurement can simultaneously obtain COD distributions in weld metal, heat-affected zone, and base metal, revealing crack propagation behavior in different zones.

**Engineering Value**: Traditional clip gauges can only measure average crack mouth opening displacement and cannot distinguish COD differences between zones. DIC full-field measurement provides richer information for understanding welded joint fracture mechanisms.

### 7.2 Pipeline Crack Integrity Evaluation

Corrosion cracks and fatigue cracks in oil and gas pipelines are major threats to pipeline safety. COD measurement is core content of pipeline integrity assessment, directly determining maximum allowable operating pressure and remaining life.

**Engineering Value**: Pipeline crack COD measurement typically requires simulated internal pressure and axial loading composite conditions. DIC's non-contact measurement characteristics make it particularly suitable for such complex loading conditions.

### 7.3 Pressure Vessel Safety Assessment

Pressure vessel safety assessment (such as R6 method and BS 7910 method) uses COD as an assessment parameter. Accurately measuring material critical COD values is the foundation of safety assessment.

**Engineering Value**: DIC full-field measurement can reveal plastic deformation behavior at crack tips, providing experimental basis for understanding material fracture mechanisms and improving safety assessment methods.

### 7.4 Aerospace Structural Damage Tolerance Design

Aerospace structural damage tolerance design requires accurate evaluation of cracked structure residual strength. COD is a key parameter in damage tolerance design for predicting crack propagation life and residual strength.

**Engineering Value**: Aerospace material COD measurement typically requires extreme temperature conditions (high or low temperature). DIC's non-contact measurement characteristics make it suitable for COD measurement in environmental chambers.

### 7.5 Fatigue Crack Propagation Testing

In fatigue crack propagation testing, the cyclic variation of COD (ΔCOD) is closely related to crack propagation rate (da/dN). DIC can measure COD changes during fatigue cycles in real-time, analyzing crack closure effects.

**Engineering Value**: DIC full-field measurement can reveal cyclic plastic deformation behavior at fatigue crack tips, providing experimental basis for understanding fatigue crack propagation mechanisms.

## 8. Experimental Design and Data Processing Recommendations

For engineering teams introducing DIC into COD measurement for the first time, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle area | Centered on crack tip, covering 10-20mm each side |
| Speckle quality | High contrast, good randomness, speckles not crossing crack surface |
| Camera resolution | ≥5MP, ensuring crack tip spatial resolution |
| Crack tip location | Precise location through displacement field singularity and strain concentration |
| COD calculation method | Recommend fitting method or J-integral method to eliminate tip position uncertainty |
| Rigid body displacement elimination | Eliminate specimen rigid body displacement to obtain pure deformation |
| Temperature control | Conduct tests in constant temperature environment to avoid temperature fluctuation effects |
| Loading rate | Control loading rate per standard specifications, typically 0.5-2mm/min |

**Getting Started Recommendation**: Begin with quasi-static COD tests on standard three-point bending specimens, verify consistency between DIC measurements and clip gauge data, then gradually expand to more complex specimens and loading conditions.

## 9. Conclusion

Crack Tip Opening Displacement (COD) is a key bridge in fracture mechanics connecting material micro-scale fracture mechanisms with macro-scale structural safety assessment. Precise COD measurement is fundamental for establishing material fracture toughness databases, developing structural safety assessment standards, and predicting service life of cracked structures.

Traditional COD measurement methods (clip gauges, potential drop, compliance methods) remain effective in certain scenarios, but their single-point measurement and indirect calculation nature limits measurement precision and information content. DIC technology, through full-field displacement measurement, high spatial resolution, and direct CTOD acquisition capability, has fundamentally changed the COD measurement technical paradigm—from "point" to "surface," from "indirect" to "direct," from "single parameter" to "full-field information."

The XTDIC-CONST-HR series, with ≤25MP high resolution and 20με strain precision, provides sufficient spatial resolution and measurement precision for COD measurement. From welded joint fracture toughness evaluation to pipeline integrity assessment, from pressure vessel safety design to aerospace damage tolerance analysis, DIC technology is becoming an indispensable tool in the COD measurement field.

As fracture mechanics theory develops and safety assessment methods become more refined, requirements for COD measurement precision and information content will continue to increase. DIC technology, with its full-field, non-contact, high-resolution measurement capabilities, will play an increasingly important role in this process—providing more reliable data support for engineering structure safety design and intelligent operation and maintenance.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D XTDIC system documentation and fracture mechanics COD testing application notes*
