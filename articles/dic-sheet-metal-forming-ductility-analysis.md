# 数字图像相关DIC技术：揭秘金属板料冲压成形中的韧性

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：冲压成形中"韧性"的量化难题](#1-引言冲压成形中韧性的量化难题)
- [2. 金属板料冲压成形的基本原理](#2-金属板料冲压成形的基本原理)
- [3. 韧性断裂：从微观机制到宏观表现](#3-韧性断裂从微观机制到宏观表现)
- [4. 传统测量方法在板料成形中的局限](#4-传统测量方法在板料成形中的局限)
- [5. DIC技术如何揭示板料成形韧性](#5-dic技术如何揭示板料成形韧性)
- [6. 成形极限图（FLD）：韧性评估的核心工具](#6-成形极限图fld韧性评估的核心工具)
- [7. XTDIC-FLC系统在板料成形中的应用](#7-xtdic-flc系统在板料成形中的应用)
- [8. 典型应用场景](#8-典型应用场景)
- [9. 实验设计与实施建议](#9-实验设计与实施建议)
- [10. 结语](#10-结语)

---

## 1. 引言：冲压成形中"韧性"的量化难题

金属板料冲压成形是现代制造业中最重要的加工工艺之一，从汽车车身覆盖件到航空航天蒙皮，从电子元器件外壳到家电面板，冲压件无处不在。据统计，全球每年通过冲压工艺生产的金属零件超过数十亿件，仅汽车工业中白车身就有约300-500个冲压件。

在冲压成形中，"韧性"是决定零件能否成功成形的关键材料属性。韧性好的材料可以在破裂前承受更大的塑性变形，允许更复杂的几何形状和更深的拉深深度。但韧性的量化一直是个工程难题——传统的拉伸试验只能给出延伸率、断面收缩率等宏观指标，无法直接反映板料在复杂应力状态下的局部变形能力和破裂风险。

更关键的是，板料在冲压过程中经历的是复杂的多轴应力状态，而非简单拉伸。一个汽车车门内板在成形过程中，不同区域可能同时经历拉-拉、拉-压、平面应变甚至纯剪切的应力状态。每种应力状态下材料的"韧性表现"各不相同，单靠传统拉伸试验数据无法准确预测。

数字图像相关（DIC）技术的出现，为板料成形韧性的量化评估提供了全新的手段。通过实时测量板料表面的全场应变分布，DIC可以直接捕捉到应变集中区域的演化过程，识别颈缩起始点，追踪裂纹萌生和扩展路径，从而实现对板料成形韧性的全面、定量评估。

## 2. 金属板料冲压成形的基本原理

金属板料冲压成形是利用模具对金属板料施加外力，使其产生塑性变形，从而获得所需形状和尺寸的加工方法。常见的冲压工序包括拉深（Drawing）、翻边（Flanging）、胀形（Stretching）、弯曲（Bending）、修边（Trimming）等。

**拉深**是最典型的冲压工序。在拉深过程中，平板坯料在凸模的作用下被拉入凹模，形成空心零件。拉深过程中板料的应力状态非常复杂：凸缘区域受到径向拉应力和切向压应力的作用（拉-压应力状态），侧壁区域受到单向拉应力的作用，底部区域受到双向拉应力的作用（拉-拉应力状态）。

**成形极限**是板料在冲压过程中能够承受的最大变形程度。当板料某处的应变超过其成形极限时，就会发生颈缩或破裂。成形极限取决于材料的力学性能（n值、r值、延伸率）、板料厚度、摩擦条件、模具几何参数等多种因素。

**关键材料参数**：
- **n值（应变硬化指数）**：反映材料抵抗颈缩的能力。n值越高，材料在变形过程中硬化越明显，变形越不容易集中。低碳钢的n值约为0.20-0.25，铝合金约为0.15-0.25，不锈钢约为0.40-0.55。
- **r值（塑性应变比/厚向异性系数）**：反映板料在厚度方向的变形能力。r值越高，板料越不容易变薄，拉深性能越好。优质深冲钢板的r值可达1.8-2.2。
- **延伸率（δ）**：反映材料的总体塑性。普通低碳钢延伸率约30-45%，铝合金约15-30%，不锈钢约40-60%。

## 3. 韧性断裂：从微观机制到宏观表现

金属板料的韧性断裂是一个多阶段的损伤演化过程，理解这一过程对于预测和控制冲压成形质量至关重要。

**第一阶段：微孔洞萌生**。在塑性变形过程中，材料内部的夹杂物（如MnS、Al2O3等）、第二相粒子与基体之间的界面处产生应力集中，导致界面脱键，形成微孔洞。微孔洞的萌生通常发生在等效塑性应变达到0.3-0.5的阶段。

**第二阶段：微孔洞长大**。随着塑性变形的继续，微孔洞在应力作用下逐渐长大。孔洞的长大速率与应力状态密切相关——在三向拉应力状态下，孔洞长大最快。这个阶段，材料的承载能力开始下降，但宏观上可能还没有明显表现。

**第三阶段：微孔洞聚合**。当微孔洞长大到一定程度后，相邻孔洞之间的材料发生颈缩，孔洞相互连通，形成宏观裂纹。这一阶段发展很快，最终导致材料的断裂。

在宏观尺度上，韧性断裂的表现形式包括：**分散性颈缩**（Diffuse Necking）和**局部性颈缩**（Localized Necking）。分散性颈缩是板料在宽度方向上的均匀收缩，不会立即导致破裂；局部性颈缩是在某一狭窄区域内的集中变形，是破裂的前兆。DIC技术可以精确捕捉到从分散性颈缩到局部性颈缩的转变过程，为预测破裂提供早期预警。

## 4. 传统测量方法在板料成形中的局限

**网格法**是板料成形应变测量的传统方法。在板料表面预先印制或蚀刻规则网格（通常为圆形或正方形阵列），冲压完成后通过测量网格的变形来计算应变。这种方法存在明显缺陷：网格密度有限（通常每平方厘米4-9个网格），空间分辨率低；测量过程依赖人工或半自动图像分析，效率低且误差大（应变测量误差约2-5%）；只能测量冲压完成后的最终应变状态，无法记录变形过程中的应变演化。

**应变片**只能测量粘贴点附近的局部应变，对于板料成形这种全场变形问题，要覆盖足够的测量区域需要大量布设应变片，工作量大且成本高。更重要的是，应变片本身会改变板料表面的摩擦条件，影响成形过程。

**极限应变片（Circle Grid Analysis）**虽然比传统网格法有所改进，但仍然只能提供离散点的应变数据，无法呈现连续的应变场分布。对于识别应变集中区域和颈起始点，这种方法的空间分辨率远远不够。

这些传统方法的共同问题是：它们都是"事后"测量——只能在冲压完成后获取数据，无法在成形过程中实时监测应变的演化。而板料成形韧性的评估恰恰需要了解应变的动态演化过程，特别是从均匀变形到应变集中再到颈缩破裂的完整链条。

## 5. DIC技术如何揭示板料成形韧性

DIC技术在板料成形韧性评估中的核心价值在于：**全场、实时、定量**地呈现板料从均匀变形到局部化颈缩再到破裂的完整演化过程。

**全场应变分布**：DIC一次测量可以获取板料表面数十万至数百万个测点的应变数据，空间分辨率远超传统方法。通过应变云图，可以清晰识别应变集中区域的位置、范围和演化趋势。对于汽车覆盖件等大面积冲压件，DIC可以完整呈现从凸缘区到侧壁区再到底部的应变分布梯度。

**应变路径追踪**：DIC可以记录每个测点在冲压过程中的完整应变路径。在板料成形中，不同位置的应变路径可能截然不同——凸缘区的材料经历拉-压应变路径，侧壁区经历单向拉伸路径，底部经历双向拉伸路径。通过分析应变路径，可以评估不同区域的材料利用率和安全裕度。

**颈缩起始识别**：颈缩是板料破裂的前兆。DIC通过监测应变速率的变化，可以在颈缩发生的早期阶段（应变集中系数达到临界值时）发出预警。研究表明，DIC可以在肉眼可见的颈缩出现前0.5-2秒识别出应变集中趋势，为工艺调整提供时间窗口。

**裂纹萌生与扩展追踪**：对于已经出现裂纹的冲压件，DIC可以精确测量裂纹尖端的应变场，计算应力强度因子或J积分，评估裂纹的扩展驱动力。这对于研究板料成形中的边缘裂纹、底部破裂等失效模式具有重要意义。

**回弹测量**：冲压完成后，板料会发生回弹变形。DIC可以测量回弹前后的三维形貌变化，量化回弹量，为模具补偿设计提供数据支撑。

## 6. 成形极限图（FLD）：韧性评估的核心工具

成形极限图（Forming Limit Diagram, FLD）是评估板料成形韧性的最核心工具，由Keeler和Backofen在1960年代提出，至今仍是冲压成形领域最重要的工程判据。

**FLD的构建原理**：FLD的横轴为次应变（ε₂），纵轴为主应变（ε₁）。通过一系列不同应力状态的拉伸试验（如单向拉伸、平面应变、等双轴拉伸等），测量每种应力状态下板料发生颈缩或破裂时的极限应变值，将这些极限应变点连接起来，就形成了成形极限曲线（Forming Limit Curve, FLC）。FLC上方的区域为"破裂区"，下方的区域为"安全区"。

**应力状态覆盖**：FLD覆盖了从单向拉伸（ε₂/ε₁=-0.5，对应r=∞的厚向异性材料）到等双轴拉伸（ε₂/ε₁=1.0）的广泛应力范围。在实际冲压成形中，板料不同区域的应力状态对应FLD上的不同位置——凸缘区通常在拉-压区域（ε₂<0），侧壁区在平面应变到轻度拉-拉区域（0<ε₂/ε₁<0.5），底部在拉-拉区域（ε₂/ε₁>0.5）。

**安全裕度评估**：将DIC测量的实际应变数据点绘制在FLD上，可以直观评估各区域距离破裂的安全裕度。工程上通常要求最小安全裕度≥10%，即实际应变值不超过FLC对应应变值的90%。

**材料对比**：不同材料的FLC位置不同。一般来说，n值越高、延伸率越大的材料，FLC位置越高，成形极限越好。例如，DC04低碳钢的FLC₀（平面应变点的主应变值）约为0.35-0.45，而DP590双相钢的FLC₀约为0.25-0.30，AA6016铝合金的FLC₀约为0.30-0.40。

## 7. XTDIC-FLC系统在板料成形中的应用

XTDIC-FLC系统是专为板料成形极限测量设计的DIC解决方案，配合杯突试验机（Erichsen Testing Machine）使用，可以自动获取板料的成形极限曲线。

**系统组成**：
- XTDIC-CONST系列相机（SD/HR/HS根据测量需求配置）
- 杯突试验机（符合GB/T 15825.8-1995和GB/T 24171.1-2009标准）
- 专用散斑制备工具
- XTDIC-FLC分析软件

**测量流程**：
1. **散斑制备**：在板料表面喷涂亚光白底漆，再喷涂亚光黑漆形成随机散斑图案。散斑尺寸根据相机分辨率和测量幅面确定，通常要求每个散斑在图像中占据3-5个像素。
2. **试验设置**：将板料安装在杯突试验机的夹持装置中，调整相机位置和角度，确保散斑区域在相机视场内。
3. **冲压与采集**：启动杯冲试验机，凸模以恒定速度（通常10-30mm/min）压入板料，DIC相机同步采集散斑图像。采集帧率根据变形速度确定，通常为10-100fps。
4. **破裂检测**：当板料出现裂纹时，DIC软件自动识别破裂帧，并提取破裂前一帧的应变数据。
5. **FLD生成**：通过多组不同宽度试样的试验，获取不同应力状态下的极限应变值，软件自动拟合成形极限曲线。

**关键参数**：
- 测量幅面：1-10mm可调（显微模式）至数百毫米（宏观模式）
- 应变范围：0.01%-500%以上
- 应变精度：二维20με，三维30με
- 位移分辨率：0.01像素
- 支持温度：室温至900℃（高温胀形试验）
- 符合标准：GB/T 15825.8-1995、GB/T 24171.1-2009

**软件功能**：
- 断裂帧自动定位
- FLC曲线自动生成
- FLD（成形极限图）可视化
- 截线拟合与二次曲线拟合
- 数据导出（ASCII格式）

## 8. 典型应用场景

### 8.1 汽车覆盖件冲压成形优化

汽车车身覆盖件（如车门、引擎盖、翼子板）是冲压成形中最具挑战性的零件之一。这些零件通常具有复杂的曲面形状，成形过程中板料的应变分布极不均匀。DIC可以测量覆盖件在冲压过程中的全场应变分布，识别高风险区域（如圆角处、拉深筋附近），指导模具型面和工艺参数的优化。

**工程价值**：通过DIC实测数据优化模具设计，减少试模次数（从传统的5-8次减少到2-3次），缩短开发周期，降低模具成本。

### 8.2 新材料成形性能评估

随着汽车轻量化的推进，铝合金、镁合金、超高强度钢等新材料在车身结构中的应用越来越广泛。这些材料的成形性能与传统低碳钢有显著差异，需要通过DIC测量来建立准确的FLD数据。

**工程价值**：为新材料的冲压工艺设计提供可靠的成形极限数据，避免因材料性能数据不足导致的试模失败。

### 8.3 边缘破裂预测

板料边缘质量对冲压成形性能有重要影响。剪切或激光切割产生的毛刺和微裂纹会成为成形过程中的裂纹源。DIC可以追踪边缘裂纹的萌生和扩展过程，评估不同边缘质量对成形极限的影响。

**工程价值**：指导板料切割工艺优化，确定边缘质量的控制标准，减少边缘破裂废品率。

### 8.4 热成形过程监测

超高强度钢的热成形（Hot Stamping）工艺需要在高温（约900℃）下进行成形和淬火。DIC配合高温滤光片可以在热成形过程中测量板料的全场应变，评估高温下的成形性能。

**工程价值**：优化热成形工艺参数（温度、速度、冷却速率），提高零件的尺寸精度和力学性能一致性。

### 8.5 回弹补偿设计

高强度钢和铝合金的回弹量远大于普通低碳钢。DIC可以测量冲压件在脱模后的回弹变形量，为模具型面的补偿设计提供精确的输入数据。

**工程价值**：通过DIC实测回弹数据指导模具补偿，减少回弹调试时间，提高零件尺寸精度。

## 9. 实验设计与实施建议

对于初次在板料成形中引入DIC测量的工程团队，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 亚光白底+亚光黑漆随机散斑，散斑尺寸3-5像素，避免反光 |
| 相机配置 | 根据测量幅面选择相机分辨率，大面积成形用SD/HR，局部细节用HR/HS |
| 帧率设置 | 低速成形10-50fps，高速成形100-1000fps以上 |
| 标定 | 使用与测量幅面匹配的标定板，确保标定精度 |
| 润滑条件 | DIC测量的是板料上表面应变，注意润滑剂对散斑的影响 |
| 数据处理 | 选择合适的子区大小和步长，平衡空间分辨率和测量精度 |

**入门建议**：从简单的杯突试验开始，验证DIC测量结果与传统网格法的一致性，建立信心后再扩展到实际冲压件的在线测量。

## 10. 结语

金属板料冲压成形中的"韧性"不再是一个模糊的材料概念——DIC技术让它变成了可以精确测量、定量评估、动态追踪的工程参数。从全场应变分布到成形极限图，从颈缩起始识别到裂纹扩展追踪，DIC正在重新定义板料成形质量控制的精度和效率。

XTDIC-FLC系统凭借其从室温到高温、从二维到三维、从宏观到显微的完整测量能力，为板料成形韧性研究提供了可配置的技术平台。随着汽车轻量化的持续推进和新材料的不断涌现，DIC技术在板料成形领域的应用将愈发深入，从实验室研究走向产线质量控制，成为冲压成形数字化不可或缺的一环。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: The Quantification Challenge of "Ductility" in Sheet Metal Forming](#1-introduction-the-quantification-challenge-of-ductility-in-sheet-metal-forming)
- [2. Fundamentals of Sheet Metal Forming](#2-fundamentals-of-sheet-metal-forming)
- [3. Ductile Fracture: From Micro-Mechanisms to Macro-Behavior](#3-ductile-fracture-from-micro-mechanisms-to-macro-behavior)
- [4. Limitations of Traditional Measurement Methods in Sheet Forming](#4-limitations-of-traditional-measurement-methods-in-sheet-forming)
- [5. How DIC Reveals Sheet Metal Forming Ductility](#5-how-dic-reveals-sheet-metal-forming-ductility)
- [6. Forming Limit Diagram (FLD): The Core Tool for Ductility Assessment](#6-forming-limit-diagram-fld-the-core-tool-for-ductility-assessment)
- [7. XTDIC-FLC System in Sheet Metal Forming Applications](#7-xtdic-flc-system-in-sheet-metal-forming-applications)
- [8. Typical Application Scenarios](#8-typical-application-scenarios)
- [9. Experimental Design and Implementation Recommendations](#9-experimental-design-and-implementation-recommendations)
- [10. Conclusion](#10-conclusion)

---

## 1. Introduction: The Quantification Challenge of "Ductility" in Sheet Metal Forming

Sheet metal stamping is one of the most critical manufacturing processes in modern industry. From automotive body panels to aerospace skins, from electronic component housings to appliance panels, stamped parts are ubiquitous. Globally, billions of metal parts are produced through stamping processes annually, with a single automotive body-in-white comprising approximately 300-500 stamped components.

In sheet metal forming, "ductility" is the key material property determining whether a part can be successfully formed. Materials with good ductility can withstand greater plastic deformation before fracture, enabling more complex geometries and deeper draw depths. But quantifying ductility has long been an engineering challenge—conventional tensile tests only provide macroscopic indicators such as elongation and reduction of area, which cannot directly reflect a sheet's local deformation capacity and fracture risk under complex stress states.

More critically, sheet metal experiences complex multi-axis stress states during stamping, not simple tension. A single automotive door inner panel may simultaneously undergo tension-tension, tension-compression, plane strain, and even pure shear stress states in different regions during forming. The material's "ductility performance" varies under each stress state, making it impossible to accurately predict using simple tensile test data alone.

The emergence of Digital Image Correlation (DIC) technology provides a completely new means for quantitative assessment of sheet metal forming ductility. By measuring full-field strain distribution on the sheet surface in real time, DIC can directly capture the evolution of strain concentration zones, identify necking initiation points, and track crack initiation and propagation paths, enabling comprehensive, quantitative evaluation of sheet metal forming ductility.

## 2. Fundamentals of Sheet Metal Forming

Sheet metal forming uses dies to apply external forces to metal sheets, causing plastic deformation to achieve the desired shape and dimensions. Common stamping operations include drawing, flanging, stretching, bending, and trimming.

**Drawing** is the most typical stamping operation. During drawing, a flat blank is pulled into the die cavity by the punch to form a hollow part. The stress state during drawing is highly complex: the flange region experiences radial tensile stress and tangential compressive stress (tension-compression), the sidewall experiences uniaxial tension, and the bottom experiences biaxial tension (tension-tension).

**Forming limit** is the maximum deformation a sheet can withstand during stamping. When the strain at any point exceeds the forming limit, necking or fracture occurs. The forming limit depends on material mechanical properties (n-value, r-value, elongation), sheet thickness, friction conditions, die geometry, and other factors.

**Key Material Parameters**:
- **n-value (strain hardening index)**: Reflects the material's resistance to necking. Higher n-values mean more pronounced hardening during deformation, making strain concentration less likely. Low-carbon steel n-value is approximately 0.20-0.25, aluminum alloy 0.15-0.25, stainless steel 0.40-0.55.
- **r-value (plastic strain ratio / normal anisotropy coefficient)**: Reflects the sheet's deformation capacity through the thickness direction. Higher r-values mean less thinning and better drawability. Premium deep-drawing steel r-values can reach 1.8-2.2.
- **Elongation (δ)**: Reflects overall material plasticity. Ordinary low-carbon steel elongation is approximately 30-45%, aluminum alloy 15-30%, stainless steel 40-60%.

## 3. Ductile Fracture: From Micro-Mechanisms to Macro-Behavior

Ductile fracture in sheet metal is a multi-stage damage evolution process. Understanding this process is critical for predicting and controlling stamping quality.

**Stage 1: Micro-void nucleation**. During plastic deformation, stress concentrations arise at interfaces between inclusions (such as MnS, Al2O3) and the matrix, causing interface debonding and micro-void formation. Micro-void nucleation typically occurs when equivalent plastic strain reaches 0.3-0.5.

**Stage 2: Micro-void growth**. As plastic deformation continues, micro-voids gradually grow under stress. Void growth rate is closely related to stress state—under triaxial tension, voids grow fastest. During this stage, material load-bearing capacity begins to decrease, but macroscopic symptoms may not yet be apparent.

**Stage 3: Micro-void coalescence**. When micro-voids grow to a certain size, material between adjacent voids necks down, voids interconnect, and macroscopic cracks form. This stage develops rapidly, ultimately leading to material fracture.

At the macro scale, ductile fracture manifests as **diffuse necking** and **localized necking**. Diffuse necking is uniform contraction across the sheet width and does not immediately cause fracture. Localized necking is concentrated deformation within a narrow band and is a precursor to fracture. DIC technology can precisely capture the transition from diffuse to localized necking, providing early warning for fracture prediction.

## 4. Limitations of Traditional Measurement Methods in Sheet Forming

**Grid method** is the traditional approach for strain measurement in sheet metal forming. Regular grids (typically circular or square arrays) are pre-printed or etched on the sheet surface, and strains are calculated by measuring grid deformation after stamping. This method has significant drawbacks: limited grid density (typically 4-9 grids per cm²), low spatial resolution; measurement relies on manual or semi-automatic image analysis, with low efficiency and large errors (strain measurement error approximately 2-5%); only final post-stamping strain states can be measured, with no capability to record strain evolution during forming.

**Strain gauges** can only measure local strain near the attachment point. For full-field deformation problems like sheet metal forming, covering sufficient measurement areas requires extensive strain gauge placement, with high workload and cost. More importantly, strain gauges alter surface friction conditions, affecting the forming process.

**Circle Grid Analysis**, while an improvement over traditional grid methods, still only provides discrete point strain data and cannot present continuous strain field distributions. For identifying strain concentration zones and necking initiation points, this method's spatial resolution is far from adequate.

The common problem with these traditional methods is that they are all "post-mortem" measurements—data can only be obtained after stamping is complete, with no capability for real-time monitoring of strain evolution during forming. Yet sheet metal forming ductility assessment precisely requires understanding the dynamic evolution of strain, particularly the complete chain from uniform deformation to strain concentration to necking and fracture.

## 5. How DIC Reveals Sheet Metal Forming Ductility

DIC's core value in sheet metal forming ductility assessment lies in its ability to present the complete evolution from uniform deformation to localized necking to fracture in a **full-field, real-time, quantitative** manner.

**Full-field strain distribution**: A single DIC measurement can obtain strain data for hundreds of thousands to millions of measurement points on the sheet surface, with spatial resolution far exceeding traditional methods. Through strain contour maps, the location, extent, and evolution trends of strain concentration zones can be clearly identified. For large-area stampings like automotive panels, DIC can completely present strain distribution gradients from the flange zone through the sidewall to the bottom.

**Strain path tracking**: DIC can record the complete strain path for each measurement point during stamping. In sheet metal forming, strain paths at different locations may be entirely different—flank zone material experiences tension-compression strain paths, sidewall zone experiences uniaxial tension paths, and bottom zone experiences biaxial tension paths. By analyzing strain paths, material utilization rates and safety margins in different zones can be evaluated.

**Necking initiation identification**: Necking is a precursor to sheet fracture. DIC can provide early warning by monitoring changes in strain rate during the early stages of necking (when the strain concentration factor reaches a critical value). Research shows that DIC can identify strain concentration trends 0.5-2 seconds before visible necking appears, providing a time window for process adjustment.

**Crack initiation and propagation tracking**: For stampings that have developed cracks, DIC can precisely measure the strain field at crack tips, calculate stress intensity factors or J-integrals, and evaluate crack propagation driving forces. This is significant for studying failure modes such as edge cracking and bottom fracture in sheet metal forming.

**Springback measurement**: After stamping, the sheet undergoes springback deformation. DIC can measure 3D shape changes before and after springback, quantify springback amounts, and provide data support for die compensation design.

## 6. Forming Limit Diagram (FLD): The Core Tool for Ductility Assessment

The Forming Limit Diagram (FLD) is the most core tool for evaluating sheet metal forming ductility, proposed by Keeler and Backofen in the 1960s and still the most important engineering criterion in the sheet metal forming field today.

**FLD Construction Principle**: The FLD's horizontal axis is minor strain (ε₂) and vertical axis is major strain (ε₁). Through a series of tensile tests under different stress states (such as uniaxial tension, plane strain, equi-biaxial tension, etc.), the limit strain values at which the sheet necks or fractures under each stress state are measured. Connecting these limit strain points forms the Forming Limit Curve (FLC). The area above the FLC is the "fracture zone" and below is the "safe zone."

**Stress State Coverage**: The FLC covers a wide stress range from uniaxial tension (ε₂/ε₁=-0.5, corresponding to r=∞ for normal anisotropic material) to equi-biaxial tension (ε₂/ε₁=1.0). In actual stamping, stress states at different sheet locations correspond to different positions on the FLD—the flange zone is typically in the tension-compression region (ε₂<0), the sidewall zone in the plane strain to mild tension-tension region (0<ε₂/ε₁<0.5), and the bottom zone in the tension-tension region (ε₂/ε₁>0.5).

**Safety Margin Assessment**: Plotting DIC-measured actual strain data points on the FLD allows intuitive evaluation of each zone's safety margin to fracture. Engineering practice typically requires a minimum safety margin ≥10%, meaning actual strain values should not exceed 90% of the FLC's corresponding strain values.

**Material Comparison**: Different materials have different FLC positions. Generally, materials with higher n-values and greater elongation have higher FLC positions and better forming limits. For example, DC04 low-carbon steel's FLC₀ (plane strain point major strain value) is approximately 0.35-0.45, DP590 dual-phase steel's FLC₀ is approximately 0.25-0.30, and AA6016 aluminum alloy's FLC₀ is approximately 0.30-0.40.

## 7. XTDIC-FLC System in Sheet Metal Forming Applications

The XTDIC-FLC system is a DIC solution specifically designed for sheet metal forming limit measurement, used in conjunction with Erichsen testing machines to automatically obtain the sheet's forming limit curve.

**System Components**:
- XTDIC-CONST series cameras (SD/HR/HS configured per measurement requirements)
- Erichsen testing machine (compliant with GB/T 15825.8-1995 and GB/T 24171.1-2009 standards)
- Dedicated speckle preparation tools
- XTDIC-FLC analysis software

**Measurement Workflow**:
1. **Speckle preparation**: Spray matte white base paint on the sheet surface, then spray matte black paint to form a random speckle pattern. Speckle size is determined based on camera resolution and measurement area, typically requiring each speckle to occupy 3-5 pixels in the image.
2. **Test setup**: Mount the sheet in the Erichsen testing machine's clamping fixture, adjust camera position and angle to ensure the speckle area is within the camera field of view.
3. **Stamping and acquisition**: Start the Erichsen testing machine; the punch presses into the sheet at a constant speed (typically 10-30mm/min), while DIC cameras synchronously capture speckle images. Capture frame rate is determined by deformation speed, typically 10-100fps.
4. **Fracture detection**: When cracks appear in the sheet, DIC software automatically identifies the fracture frame and extracts strain data from the frame immediately preceding fracture.
5. **FLD generation**: Through multiple tests with different specimen widths, limit strain values under different stress states are obtained, and the software automatically fits the forming limit curve.

**Key Parameters**:
- Measurement area: 1-10mm adjustable (microscopic mode) to hundreds of millimeters (macroscopic mode)
- Strain range: 0.01%-500%+
- Strain precision: 2D 20με, 3D 30με
- Displacement resolution: 0.01 pixel
- Temperature support: room temperature to 900°C (high-temperature bulging test)
- Standards compliance: GB/T 15825.8-1995, GB/T 24171.1-2009

**Software Features**:
- Automatic fracture frame localization
- Automatic FLC curve generation
- FLD (Forming Limit Diagram) visualization
- Section line fitting and quadratic curve fitting
- Data export (ASCII format)

## 8. Typical Application Scenarios

### 8.1 Automotive Panel Stamping Optimization

Automotive body panels (such as doors, hoods, fenders) are among the most challenging parts in sheet metal forming. These parts typically have complex curved surfaces with highly non-uniform strain distribution during forming. DIC can measure full-field strain distribution on panels during stamping, identifying high-risk areas (such as fillets, near draw beads), guiding die surface and process parameter optimization.

**Engineering Value**: Using DIC measurement data to optimize die design, reducing die tryout iterations (from traditional 5-8 rounds to 2-3 rounds), shortening development cycles, and reducing die costs.

### 8.2 New Material Formability Assessment

With automotive lightweighting, new materials such as aluminum alloys, magnesium alloys, and ultra-high-strength steel are increasingly used in body structures. These materials have significantly different formability compared to traditional low-carbon steel, requiring DIC measurements to establish accurate FLD data.

**Engineering Value**: Providing reliable forming limit data for stamping process design of new materials, avoiding die tryout failures due to insufficient material property data.

### 8.3 Edge Cracking Prediction

Sheet edge quality significantly affects stamping formability. Burrs and micro-cracks from shearing or laser cutting become crack sources during forming. DIC can track edge crack initiation and propagation, evaluating the impact of different edge quality levels on forming limits.

**Engineering Value**: Guiding sheet cutting process optimization, determining edge quality control standards, and reducing edge cracking scrap rates.

### 8.4 Hot Stamping Process Monitoring

Ultra-high-strength steel hot stamping (Hot Stamping) requires forming and quenching at high temperatures (approximately 900°C). DIC with high-temperature filters can measure full-field strain on the sheet during hot forming, evaluating high-temperature formability.

**Engineering Value**: Optimizing hot stamping process parameters (temperature, speed, cooling rate), improving part dimensional accuracy and mechanical property consistency.

### 8.5 Springback Compensation Design

Springback in high-strength steel and aluminum alloys is significantly greater than in ordinary low-carbon steel. DIC can measure springback deformation of stamped parts after demolding, providing precise input data for die surface compensation design.

**Engineering Value**: Using DIC-measured springback data to guide die compensation, reducing springback adjustment time and improving part dimensional accuracy.

## 9. Experimental Design and Implementation Recommendations

For engineering teams introducing DIC measurement into sheet metal forming for the first time, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle Preparation | Matte white base + matte black paint random speckles, speckle size 3-5 pixels, avoid reflections |
| Camera Configuration | Select camera resolution based on measurement area; use SD/HR for large-area forming, HR/HS for local details |
| Frame Rate Setting | Low-speed forming 10-50fps, high-speed forming 100-1000fps+ |
| Calibration | Use calibration target matching measurement area to ensure calibration accuracy |
| Lubrication Conditions | DIC measures upper surface strain; note lubricant effects on speckles |
| Data Processing | Select appropriate subset size and step length to balance spatial resolution and measurement accuracy |

**Getting Started Recommendation**: Begin with simple Erichsen tests to verify consistency between DIC measurements and traditional grid methods, build confidence, then extend to online measurement of actual stamped parts.

## 10. Conclusion

"Ductility" in sheet metal forming is no longer a vague material concept—DIC technology has transformed it into an engineering parameter that can be precisely measured, quantitatively assessed, and dynamically tracked. From full-field strain distribution to forming limit diagrams, from necking initiation identification to crack propagation tracking, DIC is redefining the precision and efficiency of sheet metal forming quality control.

The XTDIC-FLC system, with its complete measurement capability from room temperature to high temperature, 2D to 3D, and macroscopic to microscopic, provides a configurable technical platform for sheet metal forming ductility research. As automotive lightweighting continues and new materials emerge, DIC technology's applications in sheet metal forming will deepen, moving from laboratory research to production line quality control, becoming an indispensable link in the digitalization of sheet metal forming.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D sheet metal forming and XTDIC-FLC product documentation*
