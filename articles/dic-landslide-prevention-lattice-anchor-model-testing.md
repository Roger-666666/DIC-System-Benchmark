# DIC技术在滑坡防治格构锚固优化模型试验中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：滑坡防治中的"看见土体"难题](#1-引言滑坡防治中的看见土体难题)
- [2. 格构锚固：滑坡防治的主力结构](#2-格构锚固滑坡防治的主力结构)
- [3. 模型试验：从缩尺到真实的桥梁](#3-模型试验从缩尺到真实的桥梁)
- [4. 传统测量方法在岩土模型试验中的局限](#4-传统测量方法在岩土模型试验中的局限)
- [5. DIC技术如何赋能岩土模型试验](#5-dic技术如何赋能岩土模型试验)
- [6. XTDIC系统在滑坡模型试验中的配置方案](#6-xtdic系统在滑坡模型试验中的配置方案)
- [7. 典型应用场景](#7-典型应用场景)
- [8. 实验设计与实施建议](#8-实验设计与实施建议)
- [9. 结语](#9-结语)

---

## 1. 引言：滑坡防治中的"看见土体"难题

滑坡是世界上最严重的地质灾害之一。据中国地质调查局统计，我国每年因滑坡造成的直接经济损失超过200亿元，威胁着数万人的生命安全。在西南山区、黄土高原和东南沿海丘陵地带，滑坡隐患点超过30万处，防治任务极其艰巨。

滑坡防治工程中，格构锚固结构因其受力明确、施工方便、经济合理等优点，成为应用最广泛的加固措施之一。但格构锚固的设计仍然面临一个根本性挑战：我们很难"看见"土体内部的变形和破坏过程。

传统的设计方法依赖于简化假设和经验公式——假设滑面为圆弧形，假设土体为刚塑性材料，假设锚索力沿长度均匀分布。这些假设与实际情况往往存在显著差异。一个真实的滑坡体，其内部变形场是三维非均匀的，滑面形态是复杂的空间曲面，锚索与土体之间的相互作用是高度非线性的。

模型试验是揭示滑坡变形破坏机理的重要手段。通过在实验室中构建缩尺的滑坡模型，模拟真实的地质条件和加载过程，可以直观地观察滑坡的启动、滑动和破坏全过程。但模型试验的价值取决于测量手段——如果只能测量几个离散点的位移，就无法完整呈现土体内部的变形场演化。

数字图像相关（DIC）技术的出现，为岩土模型试验带来了革命性的变化。通过测量模型表面（甚至通过透明窗口测量内部剖面）的全场变形，DIC可以完整呈现滑坡从稳定到失稳的全过程变形场，揭示滑面的形成和发展规律，评估格构锚固的加固效果，为优化设计提供直接的实验依据。

## 2. 格构锚固：滑坡防治的主力结构

格构锚固是由钢筋混凝土格构梁和预应力锚索（或锚杆）组合而成的加固结构，广泛应用于公路边坡、水利水电边坡和城市边坡的滑坡防治工程中。

**结构组成**：
- **格构梁**：由纵梁和横梁交叉组成的网格状结构，通常采用C25-C30混凝土浇筑，截面尺寸一般为300mm×300mm至400mm×400mm。格构梁的作用是将锚索的集中力分散传递到更大范围的坡面上，同时提供坡面防护。
- **锚索（锚杆）**：穿过潜在滑面深入稳定地层的高强度钢绞线或钢筋。锚索通过注浆与周围土体或岩体粘结，提供抗拔力。单根锚索的设计拉力通常为100-1000kN，锚固段长度4-10m，自由段长度根据滑面深度确定。
- **锚具和垫板**：位于格构梁节点处，用于锚固钢绞线并将预应力传递到格构梁上。

**工作原理**：格构锚固通过两种机制发挥加固作用。一是锚索提供的抗滑力，直接抵抗滑坡推力；二是格构梁提供的坡面约束，防止坡面局部坍塌和浅层滑动。两者协同工作，形成一个整体的加固体系。

**设计关键参数**：
- 锚索间距：通常为3m×3m至5m×5m，根据滑坡推力和单根锚索承载力确定
- 格构梁间距：与锚索间距一致，形成规则的网格
- 锚索倾角：通常为15°-25°，以优化抗滑效果
- 预应力：通常为设计拉力的60%-80%，以预留安全裕度

**现有设计方法的局限**：目前格构锚固的设计主要基于极限平衡法，假设滑面已知且为圆弧形，无法考虑土体的渐进破坏过程和锚索-土体-格构梁之间的复杂相互作用。模型试验结合DIC测量，可以为改进设计方法提供实验基础。

## 3. 模型试验：从缩尺到真实的桥梁

滑坡模型试验是将真实滑坡按一定比例缩小，在实验室中重现滑坡的变形破坏过程，揭示其内在机理的实验方法。

**相似理论**：模型试验的基础是相似理论。根据Buckingham π定理，滑坡模型的相似准则包括几何相似（长度比尺C_L）、密度相似（密度比尺C_ρ=1）、应力相似（应力比尺C_σ=C_L）、应变相似（应变比尺C_ε=1）等。最常用的重力模型（Centrifugal Model）通过离心加速度补偿缩尺引起的应力降低，可以实现C_σ=1的完全应力相似。

**模型类型**：
- **重力模型**：在正常重力场（1g）下进行，模型尺寸较大（通常1-3m），适用于浅层滑坡和边坡稳定试验。
- **离心模型**：在离心机中进行，通过高速旋转产生数十倍至数百倍的重力加速度，补偿缩尺效应。离心加速度通常为50g-200g，对应的原型尺寸可达数十米。
- **底摩擦模型**：通过模型底部的运动皮带产生摩擦力模拟重力，适用于大型平面应变问题的定性研究。

**加载方式**：
- **重力加载**：通过增加模型高度或附加配重增加滑动力
- **液压加载**：通过液压千斤顶在模型后部施加水平推力
- **降水模拟**：通过喷淋系统模拟降雨入渗，降低土体强度
- **地震模拟**：通过振动台模拟地震荷载

**测量需求**：滑坡模型试验需要测量的关键参数包括：坡面位移场、内部剖面位移场、滑面位置和发展过程、锚索轴力分布、格构梁应变分布、孔隙水压力分布等。其中，位移场是最基础也是最重要的测量参数，因为它直接反映了滑坡的变形状态和发展趋势。

## 4. 传统测量方法在岩土模型试验中的局限

**位移传感器（LVDT/LDRT）**是岩土模型试验中最常用的位移测量工具。LVDT（线性可变差动变压器）的测量精度可达0.01mm，量程通常为50-200mm。但LVDT只能测量单个点的位移，要覆盖整个模型表面需要大量布设。在一个1m×1m的模型表面，即使每100mm布设一个测点，也需要100个LVDT，这在实际操作中几乎不可能。更少的测点意味着无法捕捉局部变形集中和滑面的精确位置。

**测斜仪**用于测量土体内部的水平位移，但它是侵入式的——需要在模型中预埋测斜管，测斜管本身会改变土体的变形特性。此外，测斜仪只能测量沿测斜管轴线方向的位移分布，无法提供二维或三维的位移场信息。

**土压力盒**用于测量土体内部的接触压力，但它只能提供单点压力数据，无法反映压力场的空间分布。在格构锚固模型试验中，土压力盒可以测量格构梁底部的接触压力，但无法呈现压力在格构梁上的分布梯度。

**标点法**：在模型表面布设人工标点，通过相机拍摄并追踪标点的位移。这种方法比LVDT覆盖范围大，但标点数量仍然有限（通常几十到几百个），空间分辨率远低于DIC。

这些传统方法的共同问题是：它们都是离散点测量，无法提供连续的变形场信息。而滑坡的变形破坏是一个空间连续的过程，滑面的形成和发展涉及整个土体内部的应变局部化，离散点测量可能错过关键的变形特征。

## 5. DIC技术如何赋能岩土模型试验

DIC技术在岩土模型试验中的核心价值在于：**全场、非接触、定量**地呈现土体从稳定到失稳的完整变形场演化过程。

**全场位移场测量**：DIC一次测量可以获取模型表面（或内部剖面）数十万至数百万个测点的位移数据。对于滑坡模型试验，这意味着可以完整呈现从坡顶到坡脚、从坡面到内部的位移分布，清晰识别位移梯度最大的区域——这往往就是潜在滑面的位置。

**滑面识别**：滑坡的滑面本质上是一个剪切应变局部化带。DIC通过计算全场应变分布，可以精确识别剪切应变集中带的位置、宽度和演化过程。在模型试验中，随着加载的增加，DIC可以追踪从初始微应变集中到宏观滑面形成的完整过程，揭示滑面的渐进发展规律。

**锚固效果评估**：通过对比有锚固和无锚固条件下模型的位移场和应变场，DIC可以直观评估格构锚固的加固效果。例如，有锚固模型的位移场在锚索位置处出现明显的"台阶"，表明锚索有效约束了土体的位移；应变集中带在锚索位置处被"切断"，表明锚索阻止了滑面的贯通。

**渐进破坏过程追踪**：滑坡的失稳是一个渐进过程——从局部剪切应变集中开始，逐步发展形成贯通的滑面，最终导致整体失稳。DIC可以记录这一全过程的变形场演化，为研究滑坡的渐进破坏机理提供直接的实验证据。

**三维变形测量**：对于离心模型试验，DIC可以配合透明侧窗测量模型内部剖面的二维变形场，或者通过双相机立体视觉测量模型表面的三维变形场。三维测量对于揭示滑坡的空间变形特征至关重要。

**与数值模拟对比验证**：DIC获取的全场变形数据可以直接与有限元（FEM）或离散元（DEM）数值模拟结果进行对比验证。这种对比不是几个测点的数值比较，而是整个变形场的空间分布对比，可以全面评估数值模型的准确性并指导模型参数标定。

## 6. XTDIC系统在滑坡模型试验中的配置方案

**重力模型试验配置**：
- XTDIC-CONST-SD相机（2.3-5MP，163-1500fps）
- 适用于1-3m尺寸的重力模型
- 工作距离：0.5m-3m
- 测量幅面：0.5m×0.4m至3m×2.4m（单相机）
- 多相机组网覆盖整个模型表面

**离心模型试验配置**：
- XTDIC-CONST-HR相机（≤25MP，30-42fps，20με）
- 高分辨率配置用于捕捉微小变形
- 通过离心机透明侧窗测量内部剖面变形
- 需要定制相机安装支架和光学窗口

**散斑制备**：
- 在模型表面喷涂亚光白底漆，再喷涂亚光黑漆形成随机散斑
- 散斑尺寸根据相机分辨率和测量幅面确定，通常要求每个散斑在图像中占据3-5像素
- 对于离心模型，散斑材料需要在高离心加速度下保持稳定

**关键参数**：
- 应变范围：0.005%-2000%
- 位移精度：≤0.01像素
- 应变精度：静态20με，动态50με
- 测量幅面：0.05m×0.04m至10m×8m
- 工作距离：0.3m至20m
- 1-8相机同步组网

## 7. 典型应用场景

### 7.1 格构锚固加固效果对比试验

在相同的滑坡模型中，分别进行无锚固、有锚固（不同锚索间距和预应力）的对比试验，利用DIC测量各工况下的全场位移和应变分布。通过对比分析，可以直观评估不同锚固方案的加固效果，优化锚索间距、预应力大小和格构梁尺寸。

**工程价值**：通过DIC实测数据优化格构锚固设计参数，提高加固效果，降低工程造价。

### 7.2 滑面形成与发展过程研究

通过DIC全程记录滑坡模型从加载到失稳的变形场演化，追踪剪切应变集中带从萌生、发展到贯通的全过程。分析滑面的位置、形态和发展速率，揭示滑坡的渐进破坏机理。

**工程价值**：为滑坡预警提供理论基础——如果能够在现场监测中识别出滑面形成的早期特征，就可以提前发出预警。

### 7.3 降雨入渗对边坡稳定性的影响

在滑坡模型中模拟降雨入渗过程，利用DIC测量边坡在不同降雨强度和持续时间下的变形场演化。分析降雨入渗引起的土体强度降低和孔隙水压力升高对边坡稳定性的影响。

**工程价值**：为降雨型滑坡的预警阈值确定提供实验依据。

### 7.4 地震荷载下边坡动力响应分析

在振动台上的边坡模型试验中，利用DIC测量地震过程中边坡表面的动态位移场。分析不同地震波类型、频率和幅值对边坡动力响应的影响，评估格构锚固在地震荷载下的加固效果。

**工程价值**：为地震区边坡的格构锚固设计提供动力响应数据。

### 7.5 锚索轴力与土体变形耦合分析

在模型试验中，将DIC测量的土体变形场与锚索轴力计测量的轴力数据进行耦合分析。研究锚索轴力与周围土体变形之间的关系，评估锚索-土体界面的荷载传递机制。

**工程价值**：为锚索设计中的锚固段长度和注浆参数优化提供实验依据。

## 8. 实验设计与实施建议

对于初次在岩土模型试验中引入DIC测量的工程团队，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 亚光白底+亚光黑漆随机散斑，散斑尺寸3-5像素，确保在试验过程中不脱落 |
| 相机安装 | 相机固定于独立支架上，避免模型振动传递到相机 |
| 光源配置 | 均匀稳定的LED光源，避免阴影和反光，光源色温5000-6500K |
| 标定 | 使用与测量幅面匹配的标定板，在试验前完成标定 |
| 图像采集频率 | 静态加载1-10fps，动态加载（地震）100-1000fps |
| 数据处理 | 选择合适的子区大小，土体变形较大时需要较大的子区 |

**入门建议**：从简单的重力模型试验开始（如均质土坡的稳定性试验），验证DIC测量结果与LVDT的一致性，建立信心后再扩展到复杂的格构锚固模型试验。

## 9. 结语

滑坡防治是一个"看不见的战场"——最大的挑战不在于我们能看见什么，而在于我们看不见什么。土体内部的变形和破坏过程隐藏在表面之下，传统的离散点测量只能管中窥豹。

DIC技术为岩土模型试验打开了"看见土体"的窗口。从全场位移场到滑面识别，从锚固效果评估到渐进破坏过程追踪，DIC正在帮助岩土工程师更深入地理解滑坡的变形破坏机理，为格构锚固的优化设计提供直接的实验依据。

XTDIC系统凭借其从静态到动态、从表面到内部、从单相机到多相机组网的完整测量能力，为滑坡模型试验提供了可配置的技术手段。随着地质灾害防治要求的不断提高和模型试验技术的持续发展，DIC技术在岩土工程领域的应用将持续深化，从实验室研究走向工程实践，为滑坡防治工程的安全性和经济性提供更有力的技术支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: The "Seeing Soil" Challenge in Landslide Prevention](#1-introduction-the-seeing-soil-challenge-in-landslide-prevention)
- [2. Lattice Anchor Systems: Primary Structures for Landslide Prevention](#2-lattice-anchor-systems-primary-structures-for-landslide-prevention)
- [3. Model Testing: The Bridge from Scale to Reality](#3-model-testing-the-bridge-from-scale-to-reality)
- [4. Limitations of Traditional Measurement Methods in Geotechnical Model Tests](#4-limitations-of-traditional-measurement-methods-in-geotechnical-model-tests)
- [5. How DIC Empowers Geotechnical Model Testing](#5-how-dic-empowers-geotechnical-model-testing)
- [6. XTDIC System Configuration for Landslide Model Testing](#6-xtdic-system-configuration-for-landslide-model-testing)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
- [8. Experimental Design and Implementation Recommendations](#8-experimental-design-and-implementation-recommendations)
- [9. Conclusion](#9-conclusion)

---

## 1. Introduction: "Seeing Soil" Challenge in Landslide Prevention

Landslides are among the most severe geological hazards worldwide. According to the China Geological Survey, annual direct economic losses from landslides in China exceed 20 billion yuan, threatening tens of thousands of lives. In southwestern mountainous regions, the Loess Plateau, and southeastern coastal hills, there are over 300,000 potential landslide sites, making prevention and control an extremely challenging task.

Among landslide prevention structures, lattice anchor systems have become one of the most widely used reinforcement measures due to their clear load transfer mechanisms, convenient construction, and economic rationality. However, lattice anchor design still faces a fundamental challenge: it is extremely difficult to "see" the deformation and failure processes within soil masses.

Traditional design methods rely on simplified assumptions and empirical formulas—assuming circular slip surfaces, assuming rigid-plastic soil behavior, assuming uniform anchor force distribution along the length. These assumptions often differ significantly from actual conditions. A real landslide mass has a three-dimensional, non-uniform internal deformation field, the slip surface is a complex spatial surface, and the interaction between anchors and soil is highly nonlinear.

Model testing is a critical means of revealing landslide deformation and failure mechanisms. By constructing scaled landslide models in the laboratory and simulating real geological conditions and loading processes, the entire process of landslide initiation, sliding, and failure can be observed intuitively. But the value of model testing depends on measurement capabilities—if only displacements at a few discrete points can be measured, the complete evolution of the internal deformation field cannot be fully captured.

The emergence of Digital Image Correlation (DIC) technology has brought revolutionary changes to geotechnical model testing. By measuring full-field deformation on model surfaces (or internal sections through transparent windows), DIC can present the complete displacement field evolution from stability to instability, reveal the formation and development patterns of slip surfaces, evaluate the reinforcement effectiveness of lattice anchor systems, and provide direct experimental evidence for design optimization.

## 2. Lattice Anchor Systems: Primary Structures for Landslide Prevention

Lattice anchor systems are composite reinforcement structures consisting of reinforced concrete lattice beams and prestressed anchors (or rock bolts), widely used in landslide prevention for highway slopes, water conservancy slopes, and urban slopes.

**Structural Components**:
- **Lattice beams**: Grid-shaped structures composed of longitudinal and cross beams, typically cast with C25-C30 concrete, with cross-sectional dimensions generally 300mm×300mm to 400mm×400mm. Lattice beams distribute concentrated anchor forces over a larger slope area while providing surface protection.
- **Anchors (rock bolts)**: High-strength steel strands or reinforcing bars passing through potential slip surfaces into stable strata. Anchors bond to surrounding soil or rock through grouting, providing pullout resistance. Single anchor design tension is typically 100-1000kN, anchor bond zone length 4-10m, and free section length determined by slip surface depth.
- **Anchorage devices and bearing plates**: Located at lattice beam nodes, used for anchoring steel strands and transmitting prestress to lattice beams.

**Working Principle**: Lattice anchor systems provide reinforcement through two mechanisms. First, anchors provide anti-sliding force directly resisting landslide thrust. Second, lattice beams provide surface constraint, preventing local slope collapse and shallow sliding. Both work together to form an integrated reinforcement system.

**Key Design Parameters**:
- Anchor spacing: typically 3m×3m to 5m×5m, determined by landslide thrust and single anchor capacity
- Lattice beam spacing: consistent with anchor spacing, forming a regular grid
- Anchor inclination: typically 15°-25°, optimized for anti-sliding effectiveness
- Prestress: typically 60%-80% of design tension, reserving safety margin

**Limitations of Current Design Methods**: Current lattice anchor design is primarily based on limit equilibrium methods, assuming known circular slip surfaces, unable to account for progressive soil failure and complex anchor-soil-beam interactions. Model testing combined with DIC measurement can provide experimental foundations for improving design methods.

## 3. Model Testing: The Bridge from Scale to Reality

Landslide model testing involves scaling down real landslides by a certain ratio and reproducing the deformation and failure processes in the laboratory to reveal intrinsic mechanisms.

**Similarity Theory**: The foundation of model testing is similarity theory. Per Buckingham π theorem, landslide model similarity criteria include geometric similarity (length scale factor C_L), density similarity (density scale factor C_ρ=1), stress similarity (stress scale factor C_σ=C_L), and strain similarity (strain scale factor C_ε=1). The most common centrifugal model compensates for stress reduction caused by scaling through centrifugal acceleration, achieving complete stress similarity with C_σ=1.

**Model Types**:
- **Gravity models**: Conducted under normal gravity (1g), with larger model sizes (typically 1-3m), suitable for shallow landslides and slope stability tests.
- **Centrifugal models**: Conducted in centrifuges, generating tens to hundreds of times gravitational acceleration through high-speed rotation to compensate for scaling effects. Centrifugal acceleration is typically 50g-200g, corresponding to prototype sizes of tens of meters.
- **Base friction models**: Use moving belts at the model base to generate friction simulating gravity, suitable for qualitative study of large plane strain problems.

**Loading Methods**:
- **Gravity loading**: Increasing sliding force by adding model height or additional counterweights
- **Hydraulic loading**: Applying horizontal thrust at the model rear through hydraulic jacks
- **Rainfall simulation**: Simulating rainfall infiltration through spray systems, reducing soil strength
- **Seismic simulation**: Simulating seismic loads through shaking tables

**Measurement Requirements**: Key parameters requiring measurement in landslide model tests include: slope surface displacement field, internal section displacement field, slip surface location and development process, anchor force distribution, lattice beam strain distribution, and pore water pressure distribution. Among these, displacement field is the most fundamental and important measurement parameter, as it directly reflects the deformation state and development trend of the landslide.

## 4. Limitations of Traditional Measurement Methods in Geotechnical Model Tests

**Displacement transducers (LVDT/LDRT)** are the most commonly used displacement measurement tools in geotechnical model tests. LVDT (Linear Variable Differential Transformer) measurement accuracy can reach 0.01mm, with typical ranges of 50-200mm. However, LVDTs can only measure displacement at individual points, and covering the entire model surface requires extensive installation. On a 1m×1m model surface, even with one transducer per 100mm, 100 LVDTs would be required—practically impossible. Fewer measurement points mean inability to capture local deformation concentrations and precise slip surface locations.

**Inclinometers** measure horizontal displacement within soil masses, but are invasive—requiring pre-installed inclinometer casings in the model, and the casings themselves alter soil deformation characteristics. Additionally, inclinometers can only measure displacement distribution along the casing axis, unable to provide 2D or 3D displacement field information.

**Earth pressure cells** measure contact pressure within soil masses, but only provide single-point pressure data, unable to reflect spatial distribution of pressure fields. In lattice anchor model tests, earth pressure cells can measure contact pressure at lattice beam bases, but cannot present pressure distribution gradients across the beam surfaces.

**Target point method**: Artificial targets are placed on the model surface, and cameras track target displacement. This method covers larger areas than LVDTs, but target numbers are still limited (typically tens to hundreds), with spatial resolution far below DIC.

The common problem with these traditional methods is that they are all discrete point measurements, unable to provide continuous deformation field information. Landslide deformation and failure is a spatially continuous process—slip surface formation and development involve strain localization throughout the soil mass, and discrete point measurements may miss critical deformation features.

## 5. How DIC Empowers Geotechnical Model Testing

DIC's core value in geotechnical model testing lies in its ability to present the complete deformation field evolution from stability to instability in a **full-field, non-contact, quantitative** manner.

**Full-field displacement measurement**: A single DIC measurement can obtain displacement data for hundreds of thousands to millions of measurement points on the model surface (or internal section). For landslide model testing, this means completely presenting displacement distribution from slope crest to toe, and from surface to interior, clearly identifying areas of maximum displacement gradient—often the location of potential slip surfaces.

**Slip surface identification**: A landslide slip surface is essentially a shear strain localization band. DIC calculates full-field strain distribution to precisely identify the location, width, and evolution of shear strain concentration zones. In model tests, as loading increases, DIC can track the complete process from initial micro-strain concentration to macroscopic slip surface formation, revealing progressive slip surface development patterns.

**Anchor reinforcement evaluation**: By comparing displacement and strain fields between models with and without reinforcement under identical conditions, DIC can intuitively evaluate lattice anchor reinforcement effectiveness. For example, reinforced model displacement fields show distinct "steps" at anchor locations, indicating effective constraint of soil displacement; strain concentration zones are "interrupted" at anchor locations, showing that anchors prevent slip surface coalescence.

**Progressive failure process tracking**: Landslide instability is a progressive process—starting from local shear strain concentration, gradually developing into a connected slip surface, ultimately leading to overall instability. DIC can record the complete deformation field evolution throughout this process, providing direct experimental evidence for studying landslide progressive failure mechanisms.

**3D deformation measurement**: For centrifugal model tests, DIC can measure 2D deformation fields on internal sections through transparent side windows, or measure 3D deformation fields on model surfaces through dual-camera stereo vision. Three-dimensional measurement is critical for revealing spatial deformation characteristics of landslides.

**Comparison with numerical simulation**: DIC-obtained full-field deformation data can be directly compared with FEM or DEM numerical simulation results. This comparison is not numerical comparison of a few measurement points but spatial distribution comparison of entire deformation fields, enabling comprehensive evaluation of numerical model accuracy and guiding model parameter calibration.

## 6. XTDIC System Configuration for Landslide Model Testing

**Gravity Model Test Configuration**:
- XTDIC-CONST-SD cameras (2.3-5MP, 163-1500fps)
- Suitable for 1-3m gravity models
- Working distance: 0.5m-3m
- Measurement area: 0.5m×0.4m to 3m×2.4m (single camera)
- Multi-camera networking to cover entire model surface

**Centrifugal Model Test Configuration**:
- XTDIC-CONST-HR cameras (≤25MP, 30-42fps, 20με)
- High-resolution configuration for capturing small deformations
- Measure internal section deformations through transparent centrifuge side windows
- Custom camera mounting brackets and optical windows required

**Speckle Preparation**:
- Spray matte white base paint on model surface, then spray matte black paint to form random speckle pattern
- Speckle size determined by camera resolution and measurement area, typically requiring each speckle to occupy 3-5 pixels
- For centrifugal models, speckle materials must remain stable under high centrifugal acceleration

**Key Parameters**:
- Strain range: 0.005%-2000%
- Displacement precision: ≤0.01 pixel
- Strain precision: static 20με, dynamic 50με
- Measurement area: 0.05m×0.04m to 10m×8m
- Working distance: 0.3m to 20m
- 1-8 camera synchronized networking

## 7. Typical Application Scenarios

### 7.1 Lattice Anchor Reinforcement Effect Comparison Tests

Under identical landslide model conditions, conduct comparative tests without reinforcement and with different reinforcement configurations (varying anchor spacing and prestress), using DIC to measure full-field displacement and strain distributions for each case. Through comparative analysis, reinforcement effectiveness of different anchor configurations can be intuitively evaluated, optimizing anchor spacing, prestress magnitude, and lattice beam dimensions.

**Engineering Value**: Using DIC measurement data to optimize lattice anchor design parameters, improving reinforcement effectiveness and reducing construction costs.

### 7.2 Slip Surface Formation and Development Process Research

Using DIC to record the complete deformation field evolution throughout the entire loading-to-failure process, tracking the complete progression of shear strain concentration zones from initiation, development, to coalescence. Analyzing slip surface location, morphology, and development rate to reveal progressive failure mechanisms.

**Engineering Value**: Providing theoretical foundations for landslide early warning—if early characteristics of slip surface formation can be identified in field monitoring, advance warning can be issued.

### 7.3 Effect of Rainfall Infiltration on Slope Stability

Simulating rainfall infiltration processes in landslide models, using DIC to measure slope deformation field evolution under different rainfall intensities and durations. Analyzing the impact of rainfall-induced soil strength reduction and pore water pressure increase on slope stability.

**Engineering Value**: Providing experimental basis for determining rainfall-induced landslide warning thresholds.

### 7.4 Slope Dynamic Response Analysis Under Seismic Loading

In shaking table tests of slope models, using DIC to measure dynamic displacement fields on slope surfaces during earthquake loading. Analyzing the influence of different seismic wave types, frequencies, and amplitudes on slope dynamic response, and evaluating lattice anchor reinforcement effectiveness under seismic loads.

**Engineering Value**: Providing dynamic response data for lattice anchor design in seismic zones.

### 7.5 Anchor Force-Soil Deformation Coupling Analysis

In model tests, coupling DIC-measured soil deformation fields with anchor force data from load cells. Studying the relationship between anchor force and surrounding soil deformation, evaluating load transfer mechanisms at the anchor-soil interface.

**Engineering Value**: Providing experimental evidence for optimizing anchor bond zone length and grouting parameters in anchor design.

## 8. Experimental Design and Implementation Recommendations

For engineering teams introducing DIC measurement into geotechnical model testing for the first time, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle Preparation | Matte white base + matte black paint random speckles, speckle size 3-5 pixels, ensure no detachment during testing |
| Camera Mounting | Cameras fixed on independent supports to prevent model vibration transmission to cameras |
| Light Source Configuration | Uniform stable LED light source, avoid shadows and reflections, color temperature 5000-6500K |
| Calibration | Use calibration target matching measurement area, complete calibration before testing |
| Image Acquisition Frequency | Static loading 1-10fps, dynamic loading (seismic) 100-1000fps |
| Data Processing | Select appropriate subset size; larger subsets needed for large soil deformations |

**Getting Started Recommendation**: Begin with simple gravity model tests (such as homogeneous slope stability tests) to verify consistency between DIC measurements and LVDT data, build confidence, then extend to complex lattice anchor model tests.

## 9. Conclusion

Landslide prevention is an "invisible battlefield"—the greatest challenge lies not in what we can see, but in what we cannot. Soil internal deformation and failure processes are hidden beneath the surface, and traditional discrete point measurements offer only a partial view.

DIC technology opens a "window to see soil" for geotechnical model testing. From full-field displacement measurement to slip surface identification, from anchor reinforcement evaluation to progressive failure process tracking, DIC is helping geotechnical engineers gain deeper understanding of landslide deformation and failure mechanisms, providing direct experimental evidence for lattice anchor design optimization.

The XTDIC system, with its complete measurement capability from static to dynamic, surface to interior, and single camera to multi-camera networking, provides configurable technical means for landslide model testing. As geological hazard prevention requirements continue to increase and model testing technology continues to develop, DIC technology applications in geotechnical engineering will continue to deepen—moving from laboratory research to engineering practice, providing stronger technical support for the safety and economy of landslide prevention projects.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D civil engineering and landslide prevention application documentation*
