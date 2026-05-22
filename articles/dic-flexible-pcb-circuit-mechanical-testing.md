# 柔性材料变形测量：DIC技术在柔性PCB电路材料力学研究中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：柔性电子时代的材料力学挑战](#1-引言柔性电子时代的材料力学挑战)
- [2. 柔性PCB的材料结构与力学特征](#2-柔性pcb的材料结构与力学特征)
- [3. 传统测量方法在柔性材料测试中的困境](#3-传统测量方法在柔性材料测试中的困境)
- [4. DIC技术用于柔性材料全场变形测量的核心优势](#4-dic技术用于柔性材料全场变形测量的核心优势)
- [5. 柔性PCB典型力学测试场景与DIC实施方案](#5-柔性pcb典型力学测试场景与dic实施方案)
- [6. XTDIC系统在柔性PCB测试中的技术方案](#6-xtdic系统在柔性pcb测试中的技术方案)
- [7. 典型应用场景](#7-典型应用场景)
- [8. 设备技术参数](#8-设备技术参数)
- [9. 结语](#9-结语)

---

## 1. 引言：柔性电子时代的材料力学挑战

柔性电子正在重新定义电子产品的形态边界。从可折叠手机到柔性显示屏，从智能穿戴设备到植入式医疗电子，柔性印刷电路板（Flexible Printed Circuit，FPC）作为柔性电子的核心载体，其力学可靠性直接决定了终端产品的使用寿命和安全性。

FPC之所以"柔性"，源于其独特的材料结构：以聚酰亚胺（PI）或聚酯（PET）薄膜为柔性基材，通过压合、蚀刻等工艺在基材表面形成铜箔导电层，构成可弯曲、可折叠、可卷曲的电路系统。这种结构赋予FPC优异的弯折性能——消费电子中的FPC（如手机屏幕排线）需承受5万次以上的180°反复弯折，汽车FPC则需承受10万次以上的动态弯折。

但柔性材料的力学测试面临一系列独特挑战。首先，FPC属于多层复合结构，各层材料（PI基材、铜箔、覆盖层、粘接层）的力学性能差异显著，在受力过程中各层的变形行为不同，传统的单点测量方法难以表征层间的变形协调性。其次，柔性材料在受力过程中可能经历大变形（延伸率可达15%-30%甚至更高），传统接触式传感器（如应变片）的量程和附着能力难以适应。第三，FPC的厚度通常只有几十到几百微米，传统引伸计的自重和夹持方式会对测试结果产生显著影响。

数字图像相关（Digital Image Correlation，DIC）技术为柔性材料的力学表征提供了全新的解决方案。作为一种非接触式全场光学测量方法，DIC可以在不接触试件表面的情况下，实时获取柔性材料在受力过程中的全场位移和应变分布，精确捕捉大变形行为、层间变形差异和局部应变集中，为柔性PCB的材料选型、结构设计和可靠性评估提供定量数据。

## 2. 柔性PCB的材料结构与力学特征

### 2.1 多层复合结构

典型FPC的结构从上到下依次为：覆盖层（Cover Layer）、铜箔层（Copper Foil）、基材（Substrate）、粘接层（Adhesive）。各层材料的力学性能差异显著：

**基材**：聚酰亚胺（PI）是目前最常用的FPC基材，厚度通常为12.5-50μm，弹性模量约2.5-3.5 GPa，拉伸强度约100-200 MPa，玻璃化转变温度（Tg）高于350°C，具有优异的耐热性和尺寸稳定性。聚酯（PET）基材成本较低，但耐热性较差（Tg约80-120°C），适用于对温度要求不高的应用场景。

**铜箔层**：FPC使用的铜箔主要有两种类型。压延铜（RA铜）通过轧制工艺制成，晶粒呈层状排列，具有优异的柔韧性和抗疲劳性能，延展性通常在15%-30%之间，适合需要多次弯折的应用场景。电解铜（ED铜）通过电沉积工艺制成，晶粒呈柱状排列，刚性更高但延展性较低（约10%-20%），成本更低。铜箔厚度通常为12-70μm。

**覆盖层**：通常为PI薄膜或感光型覆盖膜，厚度约12.5-50μm，用于保护铜箔线路和提供绝缘。

**粘接层**：用于各层材料之间的粘接，厚度约12.5-50μm，通常为环氧树脂或丙烯酸类粘接剂。

### 2.2 各向异性

FPC的各向异性来源于两个方面：一是铜箔线路的走向导致不同方向的力学性能差异；二是压延铜箔的轧制方向与垂直方向的力学性能不同。这种各向异性在弯折测试中表现尤为明显——沿铜箔线路方向的弯折寿命通常高于垂直方向。

### 2.3 大变形行为

柔性材料在受力过程中可能经历远超传统金属材料的变形量。压延铜的延伸率可达15%-30%，PI基材的断裂延伸率可达30%-80%，而PET基材的断裂延伸率甚至可达100%-150%。这种大变形行为要求测量方法具有足够大的量程和动态范围。

### 2.4 粘弹性行为

PI和PET高分子基材具有显著的粘弹性特征，其力学性能与加载速率、温度和时间相关。在循环加载过程中，FPC表现出明显的滞后效应和应力松弛行为。这种粘弹性特征使得FPC的力学测试需要考虑加载历史和环境条件的影响。

## 3. 传统测量方法在柔性材料测试中的困境

### 3.1 引伸计的接触干扰

传统引伸计是拉伸试验中测量标距段平均变形的标准设备，但在柔性材料测试中存在显著的接触干扰问题。引伸计需要夹持或粘贴在试件表面，对于厚度仅几十微米的FPC试件，引伸计的自重会对试件产生附加应力，影响测试结果。此外，引伸计的夹持力可能导致柔性试件在夹持点处产生局部变形或损伤，成为裂纹萌生的起始点。

XTDIC-VG视频引伸计的技术资料明确指出："传统的弹性模量和泊松比测试，常依赖引伸计或宽度规等设备。对于轻薄材料，引伸计的自重会对测试结果产生影响，而使用XTDIC-VG视频引伸计可以避免这个问题。"

### 3.2 应变片的量程与附着问题

应变片是材料力学性能测试中最常用的传感器，但在柔性材料测试中面临双重困境。量程方面，普通应变片的量程通常在5%以内，而柔性材料的变形量可能远超此值，导致应变片在试件断裂前提前失效。附着方面，应变片需要牢固粘贴在试件表面，而柔性材料的大变形可能导致应变片与试件表面脱粘，影响测量数据的连续性。

### 3.3 单点测量的局限性

柔性材料在受力过程中的变形往往是非均匀的。在拉伸试验中，由于材料各向异性、缺陷分布和边界效应的影响，应变并非均匀分布在标距段内。传统的单点测量方法只能获取局部信息，无法全面表征柔性材料的全场变形行为。

### 3.4 弯折测试的复杂性

FPC的弯折性能测试（如JIS C6471标准）需要同时监测弯折角度、弯折次数、电阻变化和表面损伤，传统方法需要使用专门的弯折试验机配合电气性能测试仪器，测试过程复杂且难以获取全场变形信息。

## 4. DIC技术用于柔性材料全场变形测量的核心优势

### 4.1 非接触测量消除附加影响

DIC技术最突出的优势在于非接触测量。在柔性材料的力学测试中，DIC系统通过相机拍摄试件表面的散斑图像，无需在试件表面安装任何传感器或施加任何接触力。这一特性对于柔性材料尤为重要——FPC试件厚度薄、刚度低，任何接触式测量方法都会对试件产生附加影响。DIC技术从根本上消除了接触干扰，确保测量结果反映的是材料本身的真实变形行为。

### 4.2 大变形全场测量能力

DIC技术具有超大的应变测量范围。XTDIC系统的应变测量范围为0.005%-2000%，完全覆盖柔性材料从弹性变形到断裂的全过程。在橡胶材料拉伸测试中，XTDIC系统配置1200万像素工业相机（4096×3000像素），以23fps的采样速率记录整个拉伸过程直至试样断裂，成功获取了橡胶材料在大变形条件下的全场应变分布。

### 4.3 全场应变分布揭示非均匀变形

DIC技术可以获取视场内数十万个测点的三维位移数据，空间分辨率可达微米级别。对于柔性材料的非均匀变形分析，DIC可以完整呈现试件表面的应变分布，精确识别应变集中的位置、范围和演化过程。在FPC的拉伸测试中，DIC可以揭示铜箔线路区域与基材区域的应变差异，识别层间变形不协调导致的局部应变集中。

### 4.4 多物理量同步测量

DIC技术可以同时测量位移、应变、速度、加速度等多种物理量。在柔性材料的动态测试中，DIC可以同步获取试件表面的全场变形数据和试验机的荷载数据，为分析柔性材料的动态力学行为提供完整的数据集。

### 4.5 微小试件测试能力

FPC试件通常尺寸较小（宽度5-20mm，标距段长度20-50mm），传统测量方法在微小试件上的安装和操作困难。DIC技术通过调整相机焦距和测量幅面，可以适应从几毫米到几十米的测量范围，特别适合微小试件的力学测试。XTDIC-VG视频引伸计的技术资料明确指出其适用于"微小试件测试（<5mm）"。

## 5. 柔性PCB典型力学测试场景与DIC实施方案

### 5.1 拉伸性能测试

拉伸试验是FPC材料力学性能测试的基础项目，用于测量弹性模量、泊松比、屈服强度、抗拉强度和断裂延伸率等参数。

**试样制备**：FPC拉伸试件通常裁切为长条形，宽度5-20mm，标距段长度20-50mm。试件表面需要制备散斑图案——对于FPC试件，可以使用亚光白漆作为底色，黑色亚光漆喷涂散斑图案，散斑粒径通常为0.05-0.2mm（根据测量幅面和相机分辨率优化）。

**测试过程**：将FPC试件安装在拉伸试验机的夹具上，调整DIC相机位置和焦距，使试件标距段清晰成像。设置拉伸速度（通常为1-10mm/min），同步启动试验机和DIC系统，记录整个拉伸过程的散斑图像和荷载数据。

**数据分析**：通过DIC软件计算全场位移和应变分布，绘制应力-应变曲线，提取弹性模量、泊松比、屈服强度、抗拉强度和断裂延伸率等参数。通过应变云图识别应变集中区域，分析应变集中与铜箔线路走向、缺陷分布的关系。

### 5.2 弯折疲劳测试

弯折疲劳测试是FPC可靠性评估的核心项目，用于评估FPC在反复弯折条件下的使用寿命。

**测试标准**：JIS C6471是FPC耐弯折测试的常用标准，规定了弯折角度、弯折速度、弯折次数和电阻变化等测试要求。消费电子中的FPC通常要求承受5万次以上的180°反复弯折，汽车FPC则要求10万次以上。

**DIC实施方案**：在弯折试验机的弯折区域布置DIC相机，实时拍摄FPC在弯折过程中的表面变形。通过DIC分析获取FPC在弯折过程中的全场应变分布，识别最大应变区域和应变幅值，建立应变幅值与弯折次数的关系曲线。

### 5.3 热-力耦合测试

FPC在实际应用中可能面临温度变化环境（如汽车电子中的-40°C至+125°C），热-力耦合条件下的力学性能是可靠性评估的重要内容。

**DIC实施方案**：将DIC系统与温控环境箱集成，在不同温度条件下进行拉伸或弯折测试。通过DIC获取FPC在不同温度下的全场变形数据，分析温度对FPC力学性能的影响。XTDIC系统支持高低温环境下的测量，技术资料明确指出其适用于"高温低温等复杂环境下的拉伸测试"。

### 5.4 焊盘拉力测试

FPC与刚性PCB的连接通常采用SMT焊接工艺，焊盘拉力是评估焊接质量的重要指标。行业标准通常要求焊盘拉力≥200gf（约1.96N）。

**DIC实施方案**：在焊盘拉力测试中，DIC可以测量焊盘周围FPC材料的全场变形，分析焊接区域的应力分布和变形模式，为焊接工艺优化提供数据。

## 6. XTDIC系统在柔性PCB测试中的技术方案

### 6.1 系统配置

针对柔性PCB力学测试的需求，XTDIC系统通常采用以下配置：

**常规拉伸/压缩测试**：XTDIC-CONST-SD系列（230-500万像素，163-1500fps），适用于FPC的常规拉伸、压缩和弯曲测试。

**微小试件测试**：XTDIC-CONST-HR系列（≤25MP，30-42fps），提供更高的空间分辨率，适用于微小FPC试件的精细变形测量。

**视频引伸计方案**：XTDIC-VG视频引伸计，专门用于材料拉伸模量与泊松比测试，支持塑料薄膜等柔性材料测试、微小试件测试（<5mm）、橡胶等材料大变形测试和疲劳测试。

### 6.2 散斑制备方案

FPC试件的散斑制备需要考虑以下因素：

**散斑粒径**：根据测量幅面和相机分辨率优化。对于标距段长度20-50mm的FPC拉伸试件，推荐散斑粒径0.05-0.2mm。

**散斑材料**：使用亚光白漆和亚光黑漆，避免反光影响图像质量。对于高温测试，需要使用耐高温散斑材料。

**散斑厚度**：散斑涂层应尽可能薄（<10μm），避免对FPC试件的刚度产生显著影响。

### 6.3 测量幅面与分辨率

FPC拉伸试件的典型测量幅面为20×15mm至50×40mm，需要根据试件尺寸和关注的变形区域进行调整。对于需要同时获取标距段全场变形和局部应变集中细节的测试，可以采用多相机组方案，一个相机覆盖全场，另一个相机聚焦局部区域。

### 6.4 加载同步

DIC系统通过外部触发信号与拉伸试验机同步，确保变形数据与荷载数据的时间对齐。试验机输出的荷载和位移信号通过A/D采集卡输入DIC系统，与图像采集同步记录。

## 7. 典型应用场景

### 7.1 手机屏幕排线FPC拉伸性能研究

手机屏幕排线FPC是消费电子中最典型的柔性电路应用，需要在极薄的空间内实现高密度布线和反复弯折。DIC技术可以用于研究排线FPC在拉伸过程中的全场变形行为，揭示铜箔线路区域与基材区域的应变差异，识别弯折寿命与应变幅值的关系。

### 7.2 汽车FPC热-力耦合可靠性评估

汽车电子中的FPC面临严苛的温度环境（-40°C至+125°C）和振动载荷。DIC技术可以用于评估FPC在热-力耦合条件下的变形行为，分析温度对FPC各层材料变形协调性的影响，为汽车FPC的可靠性设计提供数据。

### 7.3 柔性显示屏FPC弯折寿命预测

柔性显示屏的FPC需要在屏幕弯折区域承受反复的大角度弯折。DIC技术可以实时监测FPC在弯折过程中的全场应变分布，识别最大应变区域和应变幅值，建立应变幅值与弯折寿命的关系模型，为柔性显示屏的弯折寿命预测提供实验数据。

### 7.4 植入式医疗FPC力学安全性评估

植入式医疗电子中的FPC需要在人体内长期工作，其力学安全性至关重要。DIC技术可以用于评估FPC在模拟人体环境（37°C生理盐水）中的变形行为，分析长期浸泡对FPC各层材料力学性能的影响。

### 7.5 柔性传感器基底材料力学表征

柔性传感器的基底材料（如PDMS、PI薄膜）的力学性能直接影响传感器的灵敏度和可靠性。DIC技术可以用于测量柔性基底材料在拉伸、弯曲等载荷下的全场变形行为，分析基底材料与敏感层之间的变形协调性，为柔性传感器的结构优化提供数据。

### 7.6 覆盖层剥离强度测试

FPC覆盖层的剥离强度是评估层间粘接质量的重要指标。DIC技术可以测量剥离过程中覆盖层和基材的全场变形，分析剥离力与变形模式的关系，揭示层间失效的力学机理。

## 8. 设备技术参数

| 参数项 | XTDIC-CONST-SD | XTDIC-CONST-HR | XTDIC-VG |
|--------|---------------|---------------|----------|
| 相机像素 | 230万-500万 | ≤2500万 | 定制 |
| 帧率 | 163-1500fps | 30-42fps | 最高1000fps |
| 位移测量精度 | ≤0.01像素 | ≤0.01像素 | ≤0.01像素 |
| 应变测量精度 | 50με | 20με | 50με |
| 测量幅面 | 50mm-10m | 50mm-10m | 60/120/240mm |
| 应变测量范围 | 0.005%-2000% | 0.005%-2000% | 0.005%-2000% |

| 系统功能 | 技术指标 |
|---------|---------|
| 相机同步 | 1-8测头同步采集，可扩展 |
| 实时计算 | 支持实时全场应变计算 |
| 数据输出 | UDP实时输出，支持外部系统联动 |
| 触发模式 | 内部触发/外部触发/同步触发 |
| 试验机接口 | 支持荷载、位移信号同步采集 |
| 环境适配 | 支持高低温环境箱集成 |
| 微小试件 | 支持<5mm微小视场测量 |

## 9. 结语

柔性电子的快速发展对FPC材料的力学表征提出了前所未有的要求。多层复合结构、各向异性、大变形行为和粘弹性特征使得柔性PCB的力学测试远比传统刚性材料复杂。传统接触式测量方法在接触干扰、量程限制和单点采样等方面的局限，使其难以全面揭示柔性材料复杂的变形行为。

DIC技术以其非接触、全场、大变形量程的测量能力，为柔性PCB材料的力学表征提供了全新的技术手段。从拉伸性能测试到弯折疲劳评估，从热-力耦合分析到焊盘拉力测试，DIC技术可以在不干扰试件自然变形过程的前提下，同步获取试件表面的全场位移和应变分布，精确识别应变集中区域、揭示层间变形差异、表征各向异性空间分布。

随着柔性电子在消费电子、汽车、医疗、可穿戴设备等领域的深入应用，对FPC材料力学可靠性的要求将持续提高。DIC技术作为连接材料微观结构与宏观力学性能的桥梁，有望在柔性PCB的材料选型、结构设计、工艺优化和可靠性评估中发挥越来越重要的作用。

---

</details>

---

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

# Flexible Material Deformation Measurement: DIC Technology in Flexible PCB Circuit Material Mechanical Research

> [!TIP]
> **Language / 请选择语言:** [中文版](#chinese-version)

## Table of Contents

- [1. Introduction: Material Mechanics Challenges in the Flexible Electronics Era](#1-introduction-material-mechanics-challenges-in-the-flexible-electronics-era)
- [2. Material Structure and Mechanical Characteristics of Flexible PCB](#2-material-structure-and-mechanical-characteristics-of-flexible-pcb)
- [3. Dilemma of Traditional Measurement Methods in Flexible Material Testing](#3-dilemma-of-traditional-measurement-methods-in-flexible-material-testing)
- [4. Core Advantages of DIC for Flexible Material Full-Field Deformation Measurement](#4-core-advantages-of-dic-for-flexible-material-full-field-deformation-measurement)
- [5. Typical Flexible PCB Mechanical Testing Scenarios and DIC Implementation](#5-typical-flexible-pcb-mechanical-testing-scenarios-and-dic-implementation)
- [6. XTDIC System Technical Solution for Flexible PCB Testing](#6-xtdic-system-technical-solution-for-flexible-pcb-testing)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
- [8. Device Technical Specifications](#8-device-technical-specifications)
- [9. Conclusion](#9-conclusion)

---

## 1. Introduction: Material Mechanics Challenges in the Flexible Electronics Era

Flexible electronics is redefining the form boundaries of electronic products. From foldable phones to flexible displays, from smart wearable devices to implantable medical electronics, Flexible Printed Circuit (FPC) serves as the core carrier of flexible electronics, and its mechanical reliability directly determines the service life and safety of end products.

The "flexibility" of FPC stems from its unique material structure: using polyimide (PI) or polyester (PET) film as the flexible substrate, copper foil conductive layers are formed on the substrate surface through lamination, etching, and other processes, creating a circuit system that can be bent, folded, and rolled. This structure gives FPC excellent bending performance—FPCs in consumer electronics (such as phone screen cables) need to withstand over 50,000 cycles of 180° repeated bending, while automotive FPCs need to withstand over 100,000 cycles of dynamic bending.

However, mechanical testing of flexible materials faces a series of unique challenges. First, FPC is a multi-layer composite structure where the mechanical properties of each layer (PI substrate, copper foil, cover layer, adhesive layer) differ significantly. During loading, the deformation behavior of each layer varies, making it difficult for traditional single-point measurement methods to characterize interlayer deformation coordination. Second, flexible materials may experience large deformations during loading (elongation can reach 15%-30% or even higher), and the range and attachment capability of traditional contact sensors (such as strain gauges) are difficult to adapt. Third, FPC thickness is typically only tens to hundreds of micrometers, and the weight and clamping method of traditional extensometers can significantly affect test results.

Digital Image Correlation (DIC) technology provides a new solution for the mechanical characterization of flexible materials. As a non-contact, full-field optical measurement method, DIC can obtain the full-field displacement and strain distribution of flexible materials in real-time during mechanical testing without contacting the specimen surface, accurately capturing large deformation behaviors, interlayer deformation differences, and local strain concentrations, providing quantitative data for material selection, structural design, and reliability assessment of flexible PCB.

## 2. Material Structure and Mechanical Characteristics of Flexible PCB

### 2.1 Multi-Layer Composite Structure

The typical FPC structure from top to bottom is: Cover Layer, Copper Foil, Substrate, and Adhesive. The mechanical properties of each layer differ significantly:

**Substrate**: Polyimide (PI) is the most commonly used FPC substrate, typically 12.5-50μm thick, with elastic modulus of approximately 2.5-3.5 GPa, tensile strength of approximately 100-200 MPa, and glass transition temperature (Tg) above 350°C, offering excellent heat resistance and dimensional stability. Polyester (PET) substrates are lower cost but have poorer heat resistance (Tg approximately 80-120°C), suitable for applications with lower temperature requirements.

**Copper Foil Layer**: Two main types of copper foil are used in FPC. Rolled Annealed (RA) copper is made through rolling process, with layered grain structure, offering excellent flexibility and fatigue resistance, with elongation typically between 15%-30%, suitable for applications requiring multiple bending. Electrodeposited (ED) copper is made through electrodeposition process, with columnar grain structure, higher rigidity but lower elongation (approximately 10%-20%), and lower cost. Copper foil thickness is typically 12-70μm.

**Cover Layer**: Typically PI film or photosensitive cover film, approximately 12.5-50μm thick, used to protect copper foil traces and provide insulation.

**Adhesive Layer**: Used for bonding between layers, approximately 12.5-50μm thick, typically epoxy or acrylic adhesive.

### 2.2 Anisotropy

FPC anisotropy comes from two aspects: first, the routing direction of copper foil traces causes differences in mechanical properties in different directions; second, the rolling direction and perpendicular direction of rolled copper foil have different mechanical properties. This anisotropy is particularly evident in bending tests—the bending life along the copper foil trace direction is typically higher than the perpendicular direction.

### 2.3 Large Deformation Behavior

Flexible materials may experience deformations far exceeding those of traditional metallic materials during loading. Rolled copper can achieve elongation of 15%-30%, PI substrate fracture elongation can reach 30%-80%, and PET substrate fracture elongation can even reach 100%-150%. This large deformation behavior requires measurement methods with sufficient range and dynamic range.

### 2.4 Viscoelastic Behavior

PI and PET polymer substrates exhibit significant viscoelastic characteristics, with mechanical properties related to loading rate, temperature, and time. During cyclic loading, FPC exhibits obvious hysteresis effects and stress relaxation behavior. These viscoelastic characteristics require that FPC mechanical testing consider the effects of loading history and environmental conditions.

## 3. Dilemma of Traditional Measurement Methods in Flexible Material Testing

### 3.1 Contact Interference of Extensometers

Traditional extensometers are standard equipment for measuring average deformation within the gauge section during tensile tests, but they present significant contact interference issues in flexible material testing. Extensometers need to be clamped or attached to the specimen surface. For FPC specimens only tens of micrometers thick, the weight of the extensometer generates additional stress on the specimen, affecting test results. Additionally, the clamping force of the extensometer may cause local deformation or damage at the clamping points, becoming initiation sites for cracks.

XTDIC-VG video extensometer technical documentation clearly states: "Traditional elastic modulus and Poisson's ratio testing often relies on extensometers or width gauges. For lightweight materials, the weight of the extensometer affects test results, and using the XTDIC-VG video extensometer can avoid this problem."

### 3.2 Strain Gauge Range and Attachment Issues

Strain gauges are the most commonly used sensors in material mechanical property testing, but they face dual dilemmas in flexible material testing. Range-wise, normal strain gauges have a range of typically less than 5%, while flexible material deformations may far exceed this value, causing strain gauges to fail prematurely before specimen fracture. Attachment-wise, strain gauges need to be firmly bonded to the specimen surface, and the large deformations of flexible materials may cause debonding between the strain gauge and specimen surface, affecting measurement data continuity.

### 3.3 Limitations of Single-Point Measurement

Deformation of flexible materials during loading is often non-uniform. In tensile tests, due to material anisotropy, defect distribution, and boundary effects, strain is not uniformly distributed within the gauge section. Traditional single-point measurement methods can only obtain local information and cannot comprehensively characterize the full-field deformation behavior of flexible materials.

### 3.4 Complexity of Bending Tests

FPC bending performance testing (such as JIS C6471 standard) requires simultaneous monitoring of bending angle, bending cycles, resistance changes, and surface damage. Traditional methods require specialized bending testing machines combined with electrical performance testing instruments, making the test process complex and difficult to obtain full-field deformation information.

## 4. Core Advantages of DIC for Flexible Material Full-Field Deformation Measurement

### 4.1 Non-Contact Measurement Eliminates Additional Effects

DIC's most prominent advantage is non-contact measurement. In mechanical testing of flexible materials, the DIC system captures speckle images of the specimen surface through cameras without installing any sensors on the specimen surface or applying any contact force. This characteristic is particularly important for flexible materials—FPC specimens are thin and have low stiffness, and any contact measurement method generates additional effects on the specimen. DIC technology fundamentally eliminates contact interference, ensuring that measurement results reflect the true deformation behavior of the material itself.

### 4.2 Large Deformation Full-Field Measurement Capability

DIC technology has an ultra-large strain measurement range. The XTDIC system's strain measurement range is 0.005%-2000%, fully covering the entire process from elastic deformation to fracture of flexible materials. In rubber material tensile testing, the XTDIC system configured with a 12-megapixel industrial camera (4096×3000 pixels) recorded the entire tensile process at a sampling rate of 23fps until specimen fracture, successfully obtaining the full-field strain distribution of rubber material under large deformation conditions.

### 4.3 Full-Field Strain Distribution Reveals Non-Uniform Deformation

DIC technology can obtain three-dimensional displacement data for hundreds of thousands of measurement points within the field of view, with spatial resolution reaching the micrometer level. For non-uniform deformation analysis of flexible materials, DIC can completely present the strain distribution across the specimen surface, precisely identifying the location, range, and evolution of strain concentrations. In FPC tensile testing, DIC can reveal strain differences between copper foil trace areas and substrate areas, identifying local strain concentrations caused by interlayer deformation incoordination.

### 4.4 Multi-Physical Quantity Synchronous Measurement

DIC technology can simultaneously measure multiple physical quantities including displacement, strain, velocity, and acceleration. In dynamic testing of flexible materials, DIC can synchronously obtain full-field deformation data of the specimen surface and load data from the testing machine, providing a complete dataset for analyzing the dynamic mechanical behavior of flexible materials.

### 4.5 Small Specimen Testing Capability

FPC specimens are typically small in size (width 5-20mm, gauge section length 20-50mm), making traditional measurement methods difficult to install and operate on small specimens. DIC technology can adapt to measurement ranges from a few millimeters to tens of meters by adjusting camera focal length and measurement field of view, making it particularly suitable for mechanical testing of small specimens. XTDIC-VG video extensometer technical documentation clearly states its applicability to "small specimen testing (<5mm)."

## 5. Typical Flexible PCB Mechanical Testing Scenarios and DIC Implementation

### 5.1 Tensile Performance Testing

Tensile testing is the fundamental project for FPC material mechanical property testing, used to measure parameters such as elastic modulus, Poisson's ratio, yield strength, tensile strength, and fracture elongation.

**Specimen Preparation**: FPC tensile specimens are typically cut into strips, 5-20mm wide, with gauge section length of 20-50mm. The specimen surface needs speckle pattern preparation—for FPC specimens, matte white paint can be used as the base coat, with matte black paint sprayed for the speckle pattern. Speckle particle size is typically 0.05-0.2mm (optimized based on measurement field of view and camera resolution).

**Testing Process**: Mount the FPC specimen on the tensile testing machine fixture, adjust DIC camera position and focal length to clearly image the specimen gauge section. Set tensile speed (typically 1-10mm/min), synchronously start the testing machine and DIC system, and record speckle images and load data throughout the tensile process.

**Data Analysis**: Calculate full-field displacement and strain distribution through DIC software, plot stress-strain curves, and extract parameters such as elastic modulus, Poisson's ratio, yield strength, tensile strength, and fracture elongation. Identify strain concentration areas through strain contour maps and analyze the relationship between strain concentration and copper foil trace routing and defect distribution.

### 5.2 Bending Fatigue Testing

Bending fatigue testing is the core project for FPC reliability assessment, used to evaluate the service life of FPC under repeated bending conditions.

**Test Standard**: JIS C6471 is a common standard for FPC bending resistance testing, specifying test requirements such as bending angle, bending speed, bending cycles, and resistance changes. FPCs in consumer electronics typically need to withstand over 50,000 cycles of 180° repeated bending, while automotive FPCs require over 100,000 cycles.

**DIC Implementation**: Arrange DIC cameras in the bending area of the bending testing machine to capture surface deformation of FPC during bending in real-time. Obtain full-field strain distribution of FPC during bending through DIC analysis, identify maximum strain areas and strain amplitudes, and establish relationship curves between strain amplitude and bending cycles.

### 5.3 Thermal-Mechanical Coupling Testing

FPC in practical applications may face temperature variation environments (such as -40°C to +125°C in automotive electronics). Mechanical properties under thermal-mechanical coupling conditions are important for reliability assessment.

**DIC Implementation**: Integrate the DIC system with a temperature-controlled environmental chamber to perform tensile or bending tests at different temperatures. Obtain full-field deformation data of FPC at different temperatures through DIC and analyze the effect of temperature on FPC mechanical properties. The XTDIC system supports measurement in high and low-temperature environments, with technical documentation clearly stating its applicability to "high and low-temperature tensile testing in complex environments."

### 5.4 Pad Pull Testing

The connection between FPC and rigid PCB typically uses SMT soldering processes. Pad pull force is an important indicator for evaluating soldering quality. Industry standards typically require pad pull force ≥200gf (approximately 1.96N).

**DIC Implementation**: In pad pull testing, DIC can measure the full-field deformation of FPC material around the pad, analyze the stress distribution and deformation patterns in the soldering area, and provide data for soldering process optimization.

## 6. XTDIC System Technical Solution for Flexible PCB Testing

### 6.1 System Configuration

For the mechanical testing requirements of flexible PCB, the XTDIC system typically employs the following configurations:

**Conventional Tensile/Compression Testing**: XTDIC-CONST-SD series (2.3-5 MP, 163-1500 fps), suitable for conventional tensile, compression, and bending tests of FPC.

**Small Specimen Testing**: XTDIC-CONST-HR series (≤25 MP, 30-42 fps), providing higher spatial resolution, suitable for fine deformation measurements of small FPC specimens.

**Video Extensometer Solution**: XTDIC-VG video extensometer, specifically designed for material tensile modulus and Poisson's ratio testing, supporting flexible material testing such as plastic films, small specimen testing (<5mm), large deformation testing of rubber materials, and fatigue testing.

### 6.2 Speckle Preparation Scheme

Speckle preparation for FPC specimens needs to consider the following factors:

**Speckle Particle Size**: Optimized based on measurement field of view and camera resolution. For FPC tensile specimens with gauge section length of 20-50mm, recommended speckle particle size is 0.05-0.2mm.

**Speckle Material**: Use matte white and matte black paint to avoid reflections affecting image quality. For high-temperature testing, high-temperature resistant speckle materials are required.

**Speckle Thickness**: The speckle coating should be as thin as possible (<10μm) to avoid significant effects on FPC specimen stiffness.

### 6.3 Measurement Field of View and Resolution

The typical measurement field of view for FPC tensile specimens is 20×15mm to 50×40mm, which needs to be adjusted based on specimen size and areas of deformation interest. For tests that need to simultaneously obtain full-field deformation of the gauge section and local strain concentration details, a multi-camera approach can be used—one camera covering the full field and another focusing on local areas.

### 6.4 Loading Synchronization

The DIC system synchronizes with the tensile testing machine via external trigger signals, ensuring temporal alignment of deformation data with load data. The load and displacement signals output by the testing machine are input to the DIC system through an A/D acquisition card, recorded synchronously with image acquisition.

## 7. Typical Application Scenarios

### 7.1 Phone Screen Cable FPC Tensile Property Research

Phone screen cable FPC is the most typical flexible circuit application in consumer electronics, requiring high-density wiring and repeated bending in extremely thin spaces. DIC technology can be used to study the full-field deformation behavior of cable FPC during tensile testing, revealing strain differences between copper foil trace areas and substrate areas, and identifying the relationship between bending life and strain amplitude.

### 7.2 Automotive FPC Thermal-Mechanical Coupling Reliability Assessment

FPCs in automotive electronics face harsh temperature environments (-40°C to +125°C) and vibration loads. DIC technology can be used to evaluate the deformation behavior of FPC under thermal-mechanical coupling conditions, analyzing the effect of temperature on the deformation coordination of FPC layer materials, and providing data for automotive FPC reliability design.

### 7.3 Flexible Display FPC Bending Life Prediction

Flexible display FPC needs to withstand repeated large-angle bending in the screen bending area. DIC technology can monitor the full-field strain distribution of FPC during bending in real-time, identify maximum strain areas and strain amplitudes, establish relationship models between strain amplitude and bending life, and provide experimental data for flexible display bending life prediction.

### 7.4 Implantable Medical FPC Mechanical Safety Assessment

FPCs in implantable medical electronics need to work long-term in the human body, and their mechanical safety is critical. DIC technology can be used to evaluate the deformation behavior of FPC in simulated human body environments (37°C physiological saline) and analyze the effects of long-term immersion on the mechanical properties of FPC layer materials.

### 7.5 Flexible Sensor Substrate Material Mechanical Characterization

The mechanical properties of flexible sensor substrate materials (such as PDMS, PI film) directly affect sensor sensitivity and reliability. DIC technology can measure the full-field deformation behavior of flexible substrate materials under tensile, bending, and other loads, analyze the deformation coordination between the substrate and sensitive layers, and provide data for flexible sensor structural optimization.

### 7.6 Cover Layer Peel Strength Testing

The peel strength of the FPC cover layer is an important indicator for evaluating interlayer bonding quality. DIC technology can measure the full-field deformation of the cover layer and substrate during the peeling process, analyze the relationship between peel force and deformation patterns, and reveal the mechanical mechanisms of interlayer failure.

## 8. Device Technical Specifications

| Parameter | XTDIC-CONST-SD | XTDIC-CONST-HR | XTDIC-VG |
|-----------|---------------|---------------|----------|
| Camera Resolution | 2.3-5 MP | ≤25 MP | Custom |
| Frame Rate | 163-1500 fps | 30-42 fps | Up to 1000 fps |
| Displacement Measurement Precision | ≤0.01 pixel | ≤0.01 pixel | ≤0.01 pixel |
| Strain Measurement Accuracy | 50 με | 20 με | 50 με |
| Measurement Field of View | 50mm-10m | 50mm-10m | 60/120/240mm |
| Strain Measurement Range | 0.005%-2000% | 0.005%-2000% | 0.005%-2000% |

| System Function | Technical Specification |
|----------------|------------------------|
| Camera Synchronization | 1-8 measurement heads, expandable |
| Real-Time Computation | Supports real-time full-field strain calculation |
| Data Output | Real-time UDP output, supports external system integration |
| Trigger Mode | Internal trigger / External trigger / Synchronous trigger |
| Testing Machine Interface | Supports synchronous load and displacement signal acquisition |
| Environmental Adaptation | Supports high/low temperature environmental chamber integration |
| Small Specimen | Supports <5mm small field of view measurement |

## 9. Conclusion

The rapid development of flexible electronics has placed unprecedented demands on the mechanical characterization of FPC materials. Multi-layer composite structures, anisotropy, large deformation behavior, and viscoelastic characteristics make the mechanical testing of flexible PCB far more complex than traditional rigid materials. The limitations of traditional contact measurement methods in contact interference, range limitation, and single-point sampling make it difficult to fully reveal the complex deformation behavior of flexible materials.

DIC technology, with its non-contact, full-field, and large deformation range measurement capabilities, provides an entirely new technical approach for the mechanical characterization of flexible PCB materials. From tensile performance testing to bending fatigue assessment, from thermal-mechanical coupling analysis to pad pull testing, DIC technology can synchronously obtain full-field displacement and strain distributions across the specimen surface without interfering with the natural deformation process, precisely identifying strain concentration areas, revealing interlayer deformation differences, and characterizing the spatial distribution of anisotropy.

As flexible electronics finds deeper applications in consumer electronics, automotive, medical, wearable devices, and other fields, the requirements for FPC material mechanical reliability will continue to increase. DIC technology, serving as a bridge between material microstructure and macroscopic mechanical properties, is expected to play an increasingly important role in FPC material selection, structural design, process optimization, and reliability assessment.

---

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D flexible material testing application documentation*
