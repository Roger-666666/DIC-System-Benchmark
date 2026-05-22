# DIC三维应变测量系统：芯片晶圆热变形测量的"纳米级温度尺"

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：芯片制造中的"热胀冷缩"有多致命](#1-引言芯片制造中的热胀冷缩有多致命)
- [2. 芯片晶圆热变形：从微观到宏观的全链条影响](#2-芯片晶圆热变形从微观到宏观的全链条影响)
- [3. 传统晶圆热变形测量方法的困境](#3-传统晶圆热变形测量方法的困境)
- [4. DIC三维应变测量系统的技术原理](#4-dic三维应变测量系统的技术原理)
- [5. DIC在晶圆热变形测量中的独特优势](#5-dic在晶圆热变形测量中的独特优势)
- [6. XTDIC系统在晶圆热变形测量中的配置方案](#6-xtdic系统在晶圆热变形测量中的配置方案)
- [7. 典型应用场景](#7-典型应用场景)
- [8. 实验设计与实施建议](#8-实验设计与实施建议)
- [9. 结语](#9-结语)

---

## 1. 引言：芯片制造中的"热胀冷缩"有多致命

芯片制造是人类工业史上最精密的制造工艺之一。在指甲盖大小的硅片上集成数百亿个晶体管，线宽缩小至3nm甚至更小，这种极致的精密性对任何微小的物理变形都极度敏感。

热变形是芯片制造中最普遍也最棘手的物理问题。从晶圆制造到封装测试，几乎每一个工艺环节都涉及温度变化——氧化扩散（800-1200°C）、薄膜沉积（200-900°C）、快速热处理（RTP，升温速率100-200°C/s）、光刻胶烘烤（90-150°C）、化学机械抛光（CMP，局部温升50-100°C）、回流焊（峰值温度约260°C）。每一次温度变化，都会在晶圆内部产生热应力和热变形。

硅片的热膨胀系数（CTE）约为2.6ppm/°C，看似微小，但对于直径300mm、厚度仅775μm的硅晶圆，100°C的温差就能产生约78μm的面内热膨胀。更关键的是，晶圆表面的多层薄膜结构（SiO₂、Si₃N₄、金属布线层等）具有不同的热膨胀系数，温度变化时层间CTE失配会产生弯曲应力，导致晶圆翘曲。一个典型的300mm晶圆在经历薄膜沉积工艺后，翘曲量可达50-200μm。

这种量级的变形对于先进工艺节点来说是致命的。在极紫外光刻（EUV）中，掩模与晶圆的对准精度要求达到亚纳米级，任何热变形都会导致套刻误差（Overlay Error），直接影响芯片良率。据统计，热变形相关的套刻误差占先进制程总套刻预算的30%-40%。

问题在于，如何精确测量晶圆在温度变化过程中的三维热变形？传统的测量方法各有局限，而DIC三维应变测量系统为这一难题提供了全新的解决方案。

## 2. 芯片晶圆热变形：从微观到宏观的全链条影响

芯片晶圆的热变形问题贯穿整个制造流程，从单晶硅锭切割到最终封装，每个环节都面临不同的热变形挑战。

**晶圆制造阶段的热变形**：

在单晶硅锭切割成晶圆的过程中，线锯切割产生的局部温升会导致晶圆表面产生热应力，影响切割面的平面度。切割后的晶圆需要经过研磨、抛光等工序，每一步都涉及温度变化引起的变形。

在氧化扩散工艺中，晶圆被加热至800-1200°C，在表面生长SiO₂薄膜。由于SiO₂的CTE（0.5ppm/°C）与硅（2.6ppm/°C）不同，冷却过程中SiO₂层受到压缩应力，硅基底受到拉伸应力，导致晶圆向SiO₂一侧弯曲。

在薄膜沉积工艺中（CVD、PVD、ALD），不同材料薄膜的CTE差异更大——铝（23ppm/°C）、铜（17ppm/°C）、钨（4.5ppm/°C），与硅基底的CTE失配更加显著。多层薄膜结构的累积应力会导致晶圆产生复杂的翘曲形态。

**光刻工艺中的热变形**：

光刻是芯片制造中最关键的工艺步骤，对热变形最为敏感。在光刻过程中，晶圆经历涂胶→曝光→显影→烘烤等多个步骤，每一步都涉及温度变化。

曝光过程中，光刻胶吸收光能并转化为热能，导致晶圆局部温升。虽然单次曝光的温升很小（通常<1°C），但对于EUV光刻，晶圆上数以亿计的光点累积效应不可忽视。曝光后的烘烤步骤（PEB，Post Exposure Bake）温度通常在100-130°C，会引起光刻胶的热膨胀和收缩，影响线宽精度。

**封装测试中的热变形**：

在封装过程中，晶圆被切割成单个芯片，然后进行引线键合、倒装芯片焊接、回流焊等工序。回流焊过程中，整个封装经历从室温到260°C（SAC305无铅焊料）的温度循环，CTE失配导致的热变形是封装可靠性的主要威胁。

在热测试中，芯片需要在-55°C到+150°C的温度范围内正常工作，热变形会导致焊点疲劳、界面分层、芯片开裂等失效模式。

## 3. 传统晶圆热变形测量方法的变形

**晶圆翘曲测量仪（Warpage Metrology）**是最常用的晶圆热变形测量工具。它利用激光干涉或电容传感器测量晶圆的翘曲量，精度可达亚微米级。但这种方法只能测量晶圆的整体翘曲（即面外位移），无法测量面内应变分布。对于多层薄膜结构的晶圆，面内应变分布是评估薄膜应力的关键参数。

**热成像仪（IR Camera）**可以测量晶圆表面的温度分布，但无法直接测量变形。温度场和变形场之间的关系需要通过复杂的热-力耦合分析才能建立，且分析结果的准确性取决于材料参数的精确度。

**X射线衍射（XRD）**可以测量薄膜应力，但它只能提供微米深度范围内的应力信息，且测量速度慢，不适合在线监测。

**电阻应变片**是传统的应变测量工具，但在晶圆测量中面临根本性困难：应变片的尺寸（最小标距约0.5mm）远大于芯片特征尺寸（纳米级），无法分辨微观应变梯度。更严重的是，应变片的粘贴会污染晶圆表面，这在半导体洁净室环境中是不可接受的。

**扫描电子显微镜（SEM）结合数字图像相关（SEM-DIC）**可以实现纳米级应变测量，但SEM的视场极小（通常<1mm），无法覆盖整个晶圆。此外，SEM需要在真空环境中操作，无法模拟实际工艺中的温度变化环境。

这些传统方法的共同问题是：它们要么只能测量整体变形而无法提供全场应变分布，要么只能测量微小区域而无法覆盖整个晶圆。DIC三维应变测量系统通过光学非接触测量，可以同时实现全场覆盖和微应变量级的测量精度。

## 4. DIC三维应变测量系统的技术原理

DIC三维应变测量系统的核心是通过双目立体视觉原理，对比变形前后晶圆表面的散斑图像，计算全场三维位移和应变。

**双目立体视觉**：两个工业相机从不同角度同时观察晶圆表面，形成具有视差的双目图像。通过匹配两幅图像中的对应点，利用三角测量原理计算该点的三维坐标。双目视觉的基线距离（两相机光心之间的距离）和焦距决定了系统的深度测量精度。

**散斑制备**：在晶圆表面制备微米级随机散斑图案，通常通过喷涂纳米颗粒（如SiO₂或TiO₂）实现。散斑尺寸根据相机分辨率和测量幅面确定，通常要求每个散斑在图像中占据3-5像素。对于晶圆测量，散斑材料需要满足半导体洁净室的要求，不能引入金属污染。

**亚像素匹配算法**：DIC算法通过子区匹配（Subset Matching）技术，在变形前后的图像中找到对应点的亚像素级坐标。亚像素匹配精度通常可达0.01-0.05像素，对应物理尺寸取决于系统的放大倍率。

**热环境集成**：系统配备精密温控平台（Thermal Chuck），可以在-60°C到+300°C的温度范围内精确控制晶圆温度。温控平台的温度均匀性通常≤±0.5°C，温度稳定性≤±0.1°C。相机通过温控平台的光学窗口观察晶圆表面，窗口材料采用石英玻璃，具有良好的光学透过率和热稳定性。

**面内与面外位移分离**：双目立体视觉可以同时测量面内位移（x、y方向）和面外位移（z方向）。对于晶圆热变形测量，面外位移（翘曲）和面内位移（热膨胀）都是关键参数。面内位移的测量精度取决于相机的像素分辨率和散斑质量，面外位移的测量精度取决于双目系统的基线距离和标定精度。

## 5. DIC在晶圆热变形测量中的独特优势

**全场测量**：DIC一次测量可以获取晶圆表面数十万至数百万个测点的三维位移数据。对于300mm晶圆，DIC可以完整呈现从中心到边缘的位移分布，清晰识别位移梯度最大的区域——这往往对应着薄膜应力集中或界面缺陷的位置。

**非接触测量**：DIC通过光学成像实现测量，不与晶圆表面接触，不会引入污染或损伤。这对于半导体洁净室环境至关重要——任何接触式测量工具都可能引入颗粒污染或划伤晶圆表面。

**同步测量面内和面外变形**：DIC可以同时测量面内位移（热膨胀）和面外位移（翘曲），提供完整的热变形信息。传统的翘曲测量仪只能测量面外位移，无法提供面内应变数据。

**宽温度范围**：配合温控平台，DIC可以在-60°C到+300°C的温度范围内进行测量，覆盖芯片制造中的大部分工艺温度。对于更高温度的测量（如氧化扩散），可以配合高温窗口和冷却系统扩展温度范围。

**高测量精度**：DIC的位移测量精度可达0.01像素，在合适的放大倍率下，对应的物理分辨率可达亚微米级。应变测量精度可达20με（0.002%），足以分辨薄膜应力引起的微小应变。

**动态测量能力**：配合高速相机，DIC可以实时记录温度变化过程中的动态热变形。在快速热处理（RTP）模拟中，温度变化速率可达100-200°C/s，DIC可以捕捉到毫秒级的瞬态热变形过程。

## 6. XTDIC系统在晶圆热变形测量中的配置方案

**系统组成**：
- 高分辨双目立体视觉相机（可选配2.3MP-25MP）
- 精密温控平台（温度范围-60°C至+300°C，均匀性≤±0.5°C）
- 光学窗口（石英材质，透过率>90%）
- 散斑制备系统（纳米颗粒喷涂）
- XTDIC分析软件

**测量配置**：
- 晶圆尺寸：兼容150mm（6英寸）、200mm（8英寸）、300mm（12英寸）
- 测量幅面：单次测量可覆盖局部区域（10mm×10mm至100mm×100mm），通过拼接可覆盖整个晶圆
- 位移分辨率：≤0.01像素（对应物理尺寸取决于放大倍率）
- 应变精度：静态20με，动态50με
- 温度范围：-60°C至+300°C
- 采集帧率：1-100fps（根据相机配置）

**软件功能**：
- 三维全场位移和应变计算
- 热膨胀系数（CTE）自动计算
- 翘曲量（Warpage）自动计算
- 温度-位移/应变曲线生成
- 晶圆面形（Bow/Warp/TTV）分析
- 数据导出（CSV/ASCII格式）

## 7. 典型应用场景

### 7.1 薄膜沉积工艺中的热应力评估

在CVD、PVD或ALD薄膜沉积过程中，不同材料薄膜与硅基底的CTE失配会产生热应力，导致晶圆翘曲。DIC可以测量薄膜沉积前后晶圆的三维变形，计算薄膜应力，优化沉积工艺参数（温度、压力、气体流量）。

**工程价值**：通过DIC实测数据优化薄膜沉积工艺，降低薄膜应力，减少晶圆翘刻，提高后续光刻工艺的套刻精度。

### 7.2 快速热处理（RTP）中的瞬态热变形测量

RTP工艺中，晶圆在数秒内被加热至1000°C以上，然后快速冷却。这种剧烈的温度变化会在晶圆内部产生巨大的热应力，可能导致晶圆破裂或产生位错。DIC可以实时测量RTP过程中的瞬态热变形，评估温度均匀性和热应力分布。

**工程价值**：通过DIC瞬态测量数据优化RTP温度曲线，降低热应力，减少晶圆破裂和位错缺陷。

### 7.3 光刻工艺中的套刻误差热变形分量分析

套刻误差是影响芯片良率的关键因素之一，而热变形是套刻误差的重要来源。DIC可以测量晶圆在光刻过程中的热变形，分离出套刻误差中的热变形分量，为套刻补偿提供数据。

**工程价值**：通过DIC热变形数据指导套刻补偿算法，降低套刻误差，提高芯片良率。

### 7.4 封装回流焊过程中的热变形监测

在回流焊过程中，封装件经历从室温到260°C的温度循环。DIC可以测量封装件在回流焊过程中的三维热变形，评估不同封装结构、焊球布局和基板材料对热变形的影响。

**工程价值**：通过DIC热变形数据优化封装设计，降低回流焊过程中的热应力，提高封装可靠性。

### 7.5 晶圆级封装（WLP）翘曲控制

晶圆级封装中，整个晶圆被同时封装，然后切割成单个芯片。封装过程中多层材料（硅、RDL层、钝化层、焊球）的CTE失配会导致晶圆产生显著翘曲。翘曲过大会影响后续的切割、贴片和回流焊工艺。DIC可以测量WLP过程中晶圆的翘曲变化，优化封装结构和工艺参数。

**工程价值**：通过DIC翘曲数据优化WLP工艺，降低晶圆翘曲，提高封装良率。

## 8. 实验设计与实施建议

对于初次在晶圆热变形测量中引入DIC的工程团队，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 采用半导体级纳米颗粒（SiO₂或TiO₂），避免金属污染，散斑尺寸1-3像素 |
| 温控平台 | 温度均匀性≤±0.5°C，温度稳定性≤±0.1°C，避免温度梯度引入额外热应力 |
| 光学窗口 | 选用光学级石英窗口，确保窗口平整度，减少光学畸变 |
| 洁净度 | 所有组件需满足洁净室要求，避免颗粒污染晶圆表面 |
| 标定 | 在测量温度范围内进行温度补偿标定，消除窗口热变形的影响 |
| 图像采集 | 每个温度点保持足够时间（通常2-5分钟），确保晶圆温度均匀 |

**入门建议**：从简单的硅片热膨胀测量开始（如测量硅片在室温至200°C范围内的热膨胀系数），验证系统精度和重复性，再扩展到多层薄膜结构的热变形测量。

## 9. 结语

芯片制造进入纳米尺度后，"热胀冷缩"不再是初中物理课本上的简单概念，而是直接影响芯片良率和可靠性的关键工程问题。从薄膜沉积到光刻曝光，从快速热处理到回流焊，每一次温度变化都在晶圆上留下"热变形的指纹"。

DIC三维应变测量系统为读取这些"指纹"提供了精确的工具。全场、非接触、同步测量面内和面外变形、宽温度范围、微应变量级精度——这些特性使DIC成为晶圆热变形测量中不可替代的技术手段。

XTDIC系统凭借其从宏观到微观、从静态到动态、从室温到高温的完整测量能力，正在成为半导体制造中热变形表征的重要工具。随着芯片制程的不断缩小和3D封装技术的持续发展，晶圆热变形测量的精度要求将持续提高，DIC技术在半导体领域的应用也将不断深化，从实验室研究走向在线工艺监控，为芯片制造的良率提升和可靠性保障提供更有力的技术支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: How Deadly Is "Thermal Expansion" in Chip Manufacturing](#1-introduction-how-deadly-is-thermal-expansion-in-chip-manufacturing)
- [2. Chip Wafer Thermal Deformation: A Full-Chain Impact from Micro to Macro](#2-chip-wafer-thermal-deformation-a-full-chain-impact-from-micro-to-macroe)
- [3. Dilemmas of Traditional Wafer Thermal Deformation Measurement Methods](#3-dilemmas-of-traditional-wafer-thermal-deformation-measurement-methods)
- [4. Technical Principles of DIC 3D Strain Measurement Systems](#4-technical-principles-of-dic-3d-strain-measurement-systems)
- [5. Unique Advantages of DIC in Wafer Thermal Deformation Measurement](#5-unique-advantages-of-dic-in-wafer-thermal-deformation-measurement)
- [6. XTDIC System Configuration for Wafer Thermal Deformation Measurement](#6-xtdic-system-configuration-for-wafer-thermal-deformation-measurement)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
- [8. Experimental Design and Implementation Recommendations](#8-experimental-design-and-implementation-recommendations)
- [9. Conclusion](#9-conclusion)

---

## 1. Introduction: How Deadly Is "Thermal Expansion" in Chip Manufacturing

Chip manufacturing is one of the most precise manufacturing processes in human industrial history. Integrating billions of transistors on a silicon wafer the size of a fingernail, with line widths shrinking to 3nm or smaller, this extreme precision makes the process highly sensitive to any minute physical deformation.

Thermal deformation is one of the most pervasive and challenging physical problems in chip manufacturing. From wafer fabrication to packaging and testing, nearly every process step involves temperature changes—oxidation/diffusion (800-1200°C), thin film deposition (200-900°C), Rapid Thermal Processing (RTP, heating rate 100-200°C/s), photoresist baking (90-150°C), Chemical Mechanical Polishing (CMP, local temperature rise 50-100°C), and reflow soldering (peak temperature approximately 260°C). Each temperature change generates thermal stress and thermal deformation within the wafer.

Silicon's Coefficient of Thermal Expansion (CTE) is approximately 2.6ppm/°C—seemingly small, but for a 300mm diameter, 775μm thick silicon wafer, a 100°C temperature differential can produce approximately 78μm of in-plane thermal expansion. More critically, the multilayer thin film structures on the wafer surface (SiO₂, Si₃N₄, metal wiring layers, etc.) have different CTEs. During temperature changes, interlayer CTE mismatch generates bending stress, causing wafer warpage. A typical 300mm wafer can exhibit warpage of 50-200μm after thin film deposition processes.

This magnitude of deformation is fatal for advanced process nodes. In Extreme Ultraviolet Lithography (EUV), mask-to-wafer alignment accuracy requirements reach the sub-nanometer level. Any thermal deformation causes overlay error, directly impacting chip yield. Statistics show that thermal deformation-related overlay errors account for 30%-40% of the total overlay budget in advanced process nodes.

The challenge is: how to precisely measure the three-dimensional thermal deformation of wafers during temperature changes? Traditional measurement methods each have limitations, while DIC 3D strain measurement systems provide a novel solution to this problem.

## 2. Chip Wafer Thermal Deformation: A Full-Chain Impact from Micro to Macro

Thermal deformation issues in chip wafers span the entire manufacturing flow, from single crystal silicon ingot cutting to final packaging, with each stage facing different thermal deformation challenges.

**Thermal Deformation During Wafer Manufacturing**:

During wire saw cutting of single crystal silicon ingots into wafers, localized temperature rise from cutting generates thermal stress on the wafer surface, affecting cut surface flatness. Cut wafers undergo grinding, polishing, and other processes, each involving deformation from temperature changes.

In oxidation/diffusion processes, wafers are heated to 800-1200°C to grow SiO₂ films on the surface. Since SiO₂'s CTE (0.5ppm/°C) differs from silicon's (2.6ppm/°C), during cooling the SiO₂ layer experiences compressive stress while the silicon substrate experiences tensile stress, causing the wafer to bend toward the SiO₂ side.

In thin film deposition processes (CVD, PVD, ALD), CTE differences between different material films are even more significant—aluminum (23ppm/°C), copper (17ppm/°C), tungsten (4.5ppm/°C)—creating more pronounced CTE mismatch with the silicon substrate. Cumulative stress from multilayer thin film structures causes complex warpage morphologies in wafers.

**Thermal Deformation in Lithography**:

Lithography is the most critical process step in chip manufacturing and is most sensitive to thermal deformation. During lithography, wafers undergo coating → exposure → development → baking, with each step involving temperature changes.

During exposure, photoresist absorbs light energy and converts it to heat, causing localized wafer temperature rise. Although single-exposure temperature rise is small (typically <1°C), for EUV lithography, the cumulative effect of billions of light spots on the wafer cannot be ignored. Post-exposure bake (PEB) steps typically operate at 100-130°C, causing photoresist thermal expansion and contraction that affects line width accuracy.

**Thermal Deformation in Packaging and Testing**:

During packaging, wafers are diced into individual chips, followed by wire bonding, flip-chip bonding, reflow soldering, and other processes. During reflow soldering, the entire package undergoes temperature cycling from room temperature to 260°C (SAC305 lead-free solder). Thermal deformation from CTE mismatch is a primary threat to packaging reliability.

In thermal testing, chips must operate normally across temperature ranges from -55°C to +150°C. Thermal deformation can cause solder joint fatigue, interface delamination, chip cracking, and other failure modes.

## 3. Dilemmas of Traditional Wafer Thermal Deformation Measurement Methods

**Wafer warpage metrology** is the most commonly used wafer thermal deformation measurement tool. It uses laser interferometry or capacitance sensors to measure wafer warpage with sub-micrometer accuracy. However, this method can only measure overall wafer warpage (out-of-plane displacement) and cannot measure in-plane strain distribution. For multilayer thin film wafers, in-plane strain distribution is a critical parameter for evaluating film stress.

**Infrared cameras (IR Camera)** can measure wafer surface temperature distribution but cannot directly measure deformation. The relationship between temperature fields and deformation fields requires complex thermomechanical coupling analysis, and analysis accuracy depends on the precision of material parameters.

**X-ray Diffraction (XRD)** can measure thin film stress, but only provides stress information within micrometer-depth ranges, with slow measurement speeds unsuitable for inline monitoring.

**Resistance strain gauges** are traditional strain measurement tools, but face fundamental difficulties in wafer measurement: strain gauge minimum gauge lengths (approximately 0.5mm) far exceed chip feature sizes (nanometer-scale), making it impossible to resolve microscopic strain gradients. More seriously, strain gauge attachment contaminates wafer surfaces, which is unacceptable in semiconductor cleanroom environments.

**Scanning Electron Microscopy (SEM) combined with DIC (SEM-DIC)** can achieve nanometer-level strain measurement, but SEM fields of view are extremely small (typically <1mm), unable to cover entire wafers. Additionally, SEM requires vacuum operation and cannot simulate temperature changes in actual processes.

The common problem with these traditional methods is that they can only measure overall deformation without providing full-field strain distribution, or can only measure tiny areas without covering the entire wafer. DIC 3D strain measurement systems, through optical non-contact measurement, can simultaneously achieve full-field coverage and microstrain-level measurement precision.

## 4. Technical Principles of DIC 3D Strain Measurement Systems

The core of DIC 3D strain measurement systems uses binocular stereo vision principles to compare speckle images of the wafer surface before and after deformation, calculating full-field 3D displacement and strain.

**Binocular stereo vision**: Two industrial cameras simultaneously observe the wafer surface from different angles, creating parallax-rich binocular images. By matching corresponding points in both images, the 3D coordinates of each point are calculated using triangulation. The baseline distance (distance between camera optical centers) and focal length determine the system's depth measurement precision.

**Speckle preparation**: Micron-scale random speckle patterns are prepared on the wafer surface, typically through nanoparticle spray coating (such as SiO₂ or TiO₂). Speckle size is determined by camera resolution and measurement area, typically requiring each speckle to occupy 3-5 pixels. For wafer measurement, speckle materials must meet semiconductor cleanroom requirements without introducing metallic contamination.

**Sub-pixel matching algorithms**: DIC algorithms use subset matching technology to find sub-pixel-level coordinates of corresponding points in pre- and post-deformation images. Sub-pixel matching precision typically reaches 0.01-0.05 pixel, with corresponding physical dimensions depending on system magnification.

**Thermal environment integration**: The system is equipped with a precision thermal chuck capable of precisely controlling wafer temperature across ranges from -60°C to +300°C. Thermal chuck temperature uniformity is typically ≤±0.5°C, with temperature stability ≤±0.1°C. Cameras observe the wafer surface through an optical window on the thermal chuck, with window material using quartz glass with good optical transmittance and thermal stability.

**In-plane and out-of-plane displacement separation**: Binocular stereo vision can simultaneously measure in-plane displacement (x, y directions) and out-of-plane displacement (z direction). For wafer thermal deformation measurement, both out-of-plane displacement (warpage) and in-plane displacement (thermal expansion) are critical parameters. In-plane displacement measurement precision depends on camera pixel resolution and speckle quality, while out-of-plane displacement measurement precision depends on the binocular system's baseline distance and calibration precision.

## 5. Unique Advantages of DIC in Wafer Thermal Deformation Measurement

**Full-field measurement**: A single DIC measurement can obtain 3D displacement data for hundreds of thousands to millions of measurement points on the wafer surface. For a 300mm wafer, DIC can completely present displacement distribution from center to edge, clearly identifying areas of maximum displacement gradient—often corresponding to locations of thin film stress concentration or interface defects.

**Non-contact measurement**: DIC achieves measurement through optical imaging without contacting the wafer surface, introducing no contamination or damage. This is critical for semiconductor cleanroom environments—any contact measurement tool may introduce particle contamination or scratch the wafer surface.

**Simultaneous in-plane and out-of-plane deformation measurement**: DIC can simultaneously measure in-plane displacement (thermal expansion) and out-of-plane displacement (warpage), providing complete thermal deformation information. Traditional warpage measurement tools can only measure out-of-plane displacement and cannot provide in-plane strain data.

**Wide temperature range**: Combined with a thermal chuck, DIC can perform measurements across temperature ranges from -60°C to +300°C, covering most process temperatures in chip manufacturing. For higher temperature measurements (such as oxidation/diffusion), high-temperature windows and cooling systems can extend the temperature range.

**High measurement precision**: DIC displacement measurement precision can reach 0.01 pixel, with corresponding physical resolution reaching the sub-micrometer level at appropriate magnification. Strain measurement precision can reach 20με (0.002%), sufficient to resolve minute strains caused by thin film stress.

**Dynamic measurement capability**: Paired with high-speed cameras, DIC can record dynamic thermal deformation during temperature changes in real time. In Rapid Thermal Processing (RTP) simulation, temperature change rates can reach 100-200°C/s, and DIC can capture millisecond-level transient thermal deformation processes.

## 6. XTDIC System Configuration for Wafer Thermal Deformation Measurement

**System Components**:
- High-resolution binocular stereo vision cameras (configurable 2.3MP-25MP)
- Precision thermal chuck (temperature range -60°C to +300°C, uniformity ≤±0.5°C)
- Optical window (quartz material, transmittance >90%)
- Speckle preparation system (nanoparticle spray coating)
- XTDIC analysis software

**Measurement Configuration**:
- Wafer size: compatible with 150mm (6-inch), 200mm (8-inch), 300mm (12-inch)
- Measurement area: single measurement covers local areas (10mm×10mm to 100mm×100mm), full wafer coverage through stitching
- Displacement resolution: ≤0.01 pixel (physical dimensions depend on magnification)
- Strain precision: static 20με, dynamic 50με
- Temperature range: -60°C to +300°C
- Capture frame rate: 1-100fps (depending on camera configuration)

**Software Features**:
- 3D full-field displacement and strain calculation
- Automatic CTE calculation
- Automatic warpage calculation
- Temperature-displacement/strain curve generation
- Wafer surface profile (Bow/Warp/TTV) analysis
- Data export (CSV/ASCII format)

## 7. Typical Application Scenarios

### 7.1 Thermal Stress Evaluation in Thin Film Deposition

During CVD, PVD, or ALD thin film deposition, CTE mismatch between different material films and the silicon substrate generates thermal stress, causing wafer warpage. DIC can measure 3D wafer deformation before and after thin film deposition, calculate thin film stress, and optimize deposition process parameters (temperature, pressure, gas flow).

**Engineering Value**: Using DIC measurement data to optimize thin film deposition processes, reducing film stress, decreasing wafer warpage, and improving overlay accuracy in subsequent lithography processes.

### 7.2 Transient Thermal Deformation Measurement in RTP

In RTP processes, wafers are heated to above 1000°C within seconds, then rapidly cooled. Such drastic temperature changes generate enormous thermal stress within the wafer, potentially causing wafer cracking or dislocation generation. DIC can measure transient thermal deformation in real time during RTP, evaluating temperature uniformity and thermal stress distribution.

**Engineering Value**: Using DIC transient measurement data to optimize RTP temperature profiles, reducing thermal stress, and minimizing wafer cracking and dislocation defects.

### 7.3 Overlay Error Thermal Deformation Component Analysis in Lithography

Overlay error is a critical factor affecting chip yield, and thermal deformation is a significant source of overlay error. DIC can measure wafer thermal deformation during lithography, separating the thermal deformation component from overlay error to provide data for overlay compensation.

**Engineering Value**: Using DIC thermal deformation data to guide overlay compensation algorithms, reducing overlay error and improving chip yield.

### 7.4 Thermal Deformation Monitoring During Package Reflow

During reflow soldering, packages undergo temperature cycling from room temperature to 260°C. DIC can measure 3D thermal deformation of packages during reflow, evaluating the impact of different package structures, solder ball layouts, and substrate materials on thermal deformation.

**Engineering Value**: Using DIC thermal deformation data to optimize package design, reducing thermal stress during reflow and improving package reliability.

### 7.5 Wafer-Level Packaging (WLP) Warpage Control

In wafer-level packaging, the entire wafer is packaged simultaneously, then diced into individual chips. CTE mismatch between multiple materials (silicon, RDL layers, passivation, solder balls) during packaging causes significant wafer warpage. Excessive warpage affects subsequent dicing, die attach, and reflow processes. DIC can measure wafer warpage changes during WLP, optimizing package structure and process parameters.

**Engineering Value**: Using DIC warpage data to optimize WLP processes, reducing wafer warpage and improving packaging yield.

## 8. Experimental Design and Implementation Recommendations

For engineering teams introducing DIC into wafer thermal deformation measurement for the first time, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle Preparation | Use semiconductor-grade nanoparticles (SiO₂ or TiO₂), avoid metallic contamination, speckle size 1-3 pixels |
| Thermal Chuck | Temperature uniformity ≤±0.5°C, temperature stability ≤±0.1°C, avoid temperature gradients introducing additional thermal stress |
| Optical Window | Use optical-grade quartz window, ensure window flatness, reduce optical distortion |
| Cleanliness | All components must meet cleanroom requirements, avoid particle contamination of wafer surface |
| Calibration | Perform temperature-compensated calibration across measurement temperature range to eliminate window thermal deformation effects |
| Image Acquisition | Hold at each temperature point for sufficient time (typically 2-5 minutes) to ensure uniform wafer temperature |

**Getting Started Recommendation**: Begin with simple silicon wafer thermal expansion measurement (such as measuring silicon wafer CTE from room temperature to 200°C) to verify system precision and repeatability, then extend to thermal deformation measurement of multilayer thin film structures.

## 9. Conclusion

As chip manufacturing enters the nanometer scale, "thermal expansion and contraction" is no longer a simple concept from middle school physics—it is a critical engineering problem directly impacting chip yield and reliability. From thin film deposition to lithography exposure, from rapid thermal processing to reflow soldering, every temperature change leaves "thermal deformation fingerprints" on the wafer.

DIC 3D strain measurement systems provide a precise tool for reading these "fingerprints." Full-field, non-contact, simultaneous in-plane and out-of-plane deformation measurement, wide temperature range, microstrain-level precision—these characteristics make DIC an indispensable technical means for wafer thermal deformation measurement.

The XTDIC system, with its complete measurement capability from macro to micro, static to dynamic, and room temperature to high temperature, is becoming an important tool for thermal deformation characterization in semiconductor manufacturing. As chip process nodes continue to shrink and 3D packaging technology continues to develop, wafer thermal deformation measurement precision requirements will continue to increase. DIC technology applications in the semiconductor field will continue to deepen—moving from laboratory research to inline process monitoring, providing stronger technical support for chip manufacturing yield improvement and reliability assurance.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D semiconductor and XTDIC system documentation*
