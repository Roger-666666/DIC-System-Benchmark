# 数字图像相关（DIC）技术在汽车板料成形极限测量中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：汽车板料成形极限——冲压工艺的"安全边界"](#1-引言汽车板料成形极限冲压工艺的安全边界)
- [2. 成形极限图（FLD/FLC）：板料失效的"地图"](#2-成形极限图fldflc板料失效的地图)
- [3. 传统成形极限测量方法的困境](#3-传统成形极限测量方法的困境)
- [4. DIC技术如何革新成形极限测量](#4-dic技术如何革新成形极限测量)
- [5. XTDIC-FLC系统：专为成形极限测量设计](#5-xtdic-flc系统专为成形极限测量设计)
- [6. 汽车板材成形极限测量标准体系](#6-汽车板材成形极限测量标准体系)
- [7. 典型汽车板材的成形极限特征](#7-典型汽车板材的成形极限特征)
- [8. 实验设计与实施建议](#8-实验设计与实施建议)
- [9. 结语](#9-结语)

---

## 1. 引言：汽车板料成形极限——冲压工艺的"安全边界"

汽车车身覆盖件——车门、引擎盖、翼子板、车顶——几乎全部由金属板料冲压成形。一辆普通乘用车约有300-500个冲压件，板料厚度从0.5mm到2.0mm不等，材料涵盖低碳钢、高强度钢（HSS）、先进高强度钢（AHSS）、铝合金等。

冲压成形过程中，板料经历复杂的应力应变状态——拉伸、压缩、胀形、拉深、弯曲。每一种应力状态都对应一个"极限"：超过这个极限，板料就会发生颈缩（Necking）或破裂（Fracture）。这个极限就是"成形极限"（Forming Limit），它是冲压工艺设计的安全边界。

如果冲压工艺中板料的应变超过了成形极限，零件就会开裂——这是冲压生产中最常见的缺陷之一。据统计，汽车冲压件废品率中约40%与开裂和起皱有关。如果工艺设计过于保守，远离成形极限，则材料利用率低，成本上升。精确测量每种板材的成形极限，是优化冲压工艺、提高材料利用率、降低废品率的基础。

成形极限的测量方法经历了从机械测量到光学测量的演变。传统的网格分析法（Circle Grid Analysis）需要在板料表面印制网格，冲压变形后用应变尺测量网格变形——这种方法效率低、精度有限、无法提供全场应变信息。数字图像相关（DIC）技术的出现，为成形极限测量带来了革命性的变化。

## 2. 成形极限图（FLD/FLC）：板料失效的"地图"

成形极限图（Forming Limit Diagram，FLD），也称成形极限曲线（Forming Limit Curve，FLC），是描述金属板料在不同应变路径下失效极限的图形化工具。

**坐标轴含义**：FLD的横轴为次主应变（ε₂，Minor Strain），纵轴为主应变（ε₁，Major Strain）。平面上每一个点代表一种应变状态（ε₁, ε₂），即板料在该点的变形方式。

**应变路径类型**：
- **单向拉伸**（Uniaxial Tension）：ε₂ = -ε₁/2（泊松比效应），位于FLD左侧
- **平面应变**（Plane Strain）：ε₂ = 0，位于FLD底部最低点，是最危险的应变状态
- **等双轴拉伸**（Equi-biaxial Stretching）：ε₂ = ε₁，位于FLD右侧
- **胀形**（Deep Drawing）：ε₂ < 0（压缩），位于FLD左下方

**FLC的意义**：FLD上的曲线（FLC）将应变空间分为两个区域——曲线以下为"安全区"（Safe Zone），板料在该应变状态下不会发生颈缩或破裂；曲线以上为"失效区"（Failure Zone），板料将发生颈缩或破裂。冲压工艺设计的目标就是确保板料上所有点的应变状态都位于安全区内，并且尽可能靠近FLC以充分利用材料。

**影响FLC的因素**：
- **材料类型**：不同材料的FLC位置不同。一般来说，材料的强度越高，FLC位置越低（成形性能越差）
- **板料厚度**：FLC₀（平面应变点的主应变值）与板料厚度近似成正比，经验公式FLC₀ ≈ n/(1+n) × (1 + 0.5t)，其中n为硬化指数，t为厚度
- **应变路径**：FLD假设线性应变路径，实际冲压中非线性应变路径会影响FLC的形状
- **温度**：高温下材料的塑性提高，FLC位置上移

## 3. 传统成形极限测量方法的困境

**网格分析法（Circle Grid Analysis，CGA）**是传统的成形极限测量标准方法。其流程是：在板料表面通过化学蚀刻或电化学方法印制圆形网格（通常直径2.5-5.0mm）→冲压变形→用应变尺或光学测量工具测量变形后的椭圆网格→计算主应变和次主应变→绘制FLD。

CGA的主要问题：
- **效率极低**：每个试件只能提供几十个有效数据点，要绘制完整的FLD需要大量重复试验
- **精度有限**：应变尺的读数精度约为0.5-1.0%，远低于DIC的0.005%
- **无法提供全场信息**：只能测量网格点位置的应变，无法呈现板料表面的完整应变分布
- **无法识别颈缩起始**：CGA测量的是变形后的应变，无法判断颈缩是从哪个时刻开始的
- **人为误差大**：网格变形的测量依赖操作者的经验和判断

**应变片法**：在板料表面粘贴应变片测量局部应变。应变片的标距（最小约0.5mm）远大于DIC的测量分辨率，且只能提供单点数据。在冲压成形中，应变片容易被剥离或损坏。

**引伸计法**：用于测量标距内的平均应变，无法提供局部应变信息。在板料成形中，应变分布极不均匀，引伸计的平均值无法反映真实的应变状态。

这些传统方法的共同问题是：它们都是离散点测量，无法提供连续的应变场信息，无法精确识别颈缩起始点，无法呈现应变局部化的发展过程。

## 4. DIC技术如何革新成形极限测量

DIC技术在成形极限测量中的核心价值在于：**全场、实时、精确**地追踪板料从均匀变形到颈缩、破裂的全过程应变场演化。

**全场应变分布**：DIC一次测量可以获取板料表面数十万至数百万个测点的应变数据。在冲压成形过程中，这意味着可以完整呈现从压边圈到凸模圆角的应变分布，清晰识别应变集中区域——这往往就是颈缩和破裂的起始位置。

**颈缩起始识别**：颈缩是板料从均匀变形向局部化变形转变的临界点。DIC通过实时监测全场应变分布，可以精确识别颈缩的起始时刻和位置。当某个区域的应变增长率突然加快、明显高于周围区域时，就标志着颈缩的开始。

**FLC数据点提取**：在DIC测量的全场应变数据中，提取颈缩前一时刻（或破裂前一时刻）的应变值，作为该应变路径下的成形极限数据点。通过不同模具几何形状（改变应变路径），可以获得覆盖整个FLD的数据点。

**应变路径追踪**：DIC可以追踪每个测点在变形过程中的完整应变路径（ε₁-ε₂曲线），而不仅仅是最终应变值。这对于研究非线性应变路径对成形极限的影响至关重要。

**破裂预测**：通过实时监测应变集中区域的发展，DIC可以在破裂发生前预测破裂位置和破裂时间，为工艺优化提供预警。

**与有限元模拟对比**：DIC获取的全场应变数据可以直接与冲压成形有限元模拟（如AutoForm、PAM-STAMP、LS-DYNA）结果进行对比，验证模拟准确性并优化材料模型参数。

## 5. XTDIC-FLC系统：专为成形极限测量设计

XTDIC-FLC系统是专为金属板料成形极限测量设计的DIC测量系统，配合杯突试验机（Erichsen Tester）或板材成形试验机使用。

**系统组成**：
- 高分辨率工业相机（可选配2.3MP-25MP）
- 定焦镜头或变焦镜头（根据测量幅面选择）
- LED光源（均匀稳定，色温5000-6500K）
- 杯突试验机或板材成形试验机
- XTDIC-FLC分析软件

**测量流程**：
1. **散斑制备**：在板料表面喷涂亚光白底漆，再喷涂亚光黑漆形成随机散斑。散斑尺寸根据相机分辨率和测量幅面确定，通常要求每个散斑在图像中占据3-5像素。
2. **相机标定**：使用与测量幅面匹配的标定板，在试验前完成相机内外参数标定。
3. **冲压试验**：将板料装夹在杯突试验机上，凸模以恒定速度（通常10-30mm/min）压入板料。相机同步采集板料变形图像。
4. **图像采集**：采集帧率根据冲压速度确定，通常10-100fps，确保相邻图像之间的变形量不超过子区大小的10%。
5. **DIC分析**：XTDIC软件对采集的图像序列进行DIC分析，计算全场位移和应变。
6. **FLC数据提取**：在破裂前一状态的应变云图上，垂直于裂纹方向划分三条以上间隔大于2mm的截线，对每条截线上的应变数据进行二次曲线拟合，得到该应变路径下的FLC数据点。
7. **FLD绘制**：将不同应变路径下的FLC数据点拟合成完整的FLD。

**关键参数**：
- 测量幅面：1mm×0.8mm至10m×8m（根据镜头配置）
- 应变范围：0.01%-500%以上
- 应变精度：静态20με，动态50με
- 位移精度：≤0.01像素
- 采集帧率：最高1500fps（根据相机配置）
- 支持标准：GB/T 15825.8-1995、GB/T 24171.1-2009、ISO 12004-2

**软件功能**：
- 全场位移和应变实时计算
- 破裂帧自动定位
- 截线划分和二次曲线拟合
- FLC曲线自动生成
- FLD绘制和材料对比
- 数据导出（CSV/ASCII格式）

## 6. 汽车板材成形极限测量标准体系

**GB/T 15825.8-1995**《金属薄板成形性能与试验方法 成形极限图（FLD）试验》是中国的成形极限测量国家标准，规定了FLD试验的试件尺寸、模具几何、试验步骤和数据处理方法。

**GB/T 24171.1-2009**《金属薄板成形极限曲线的测定 第1部分：冲压车间用的成形极限图》是更新的国家标准，与国际标准ISO 12004-2接轨，规定了更详细的试验程序和数据处理方法。

**ISO 12004-2:2008**《Metallic materials — Sheet and strip — Determination of forming-limit curves — Part 2: Determination of forming-limit curves in the laboratory》是国际标准化组织的成形极限测量标准，被全球汽车制造商广泛采用。

**JIS Z 2253:2011**是日本工业标准的成形极限测量方法，与ISO 12004-2基本一致。

这些标准的核心要求包括：
- 试件尺寸：通常宽度为25mm、50mm、75mm、100mm、125mm、150mm、175mm、200mm的矩形试件，以覆盖不同的应变路径
- 模具几何：凸模直径通常为100mm（GB/T 15825.8）或50mm（ISO 12004-2），凹模圆角半径5-10mm
- 润滑条件：规定润滑方式和润滑剂类型，以控制摩擦条件
- 冲压速度：通常10-30mm/min
- 数据处理：规定截线划分方法和拟合算法

## 7. 典型汽车板材的成形极限特征

**DC04（超深冲钢）**：碳含量≤0.08%，屈服强度120-180MPa，抗拉强度270-350MPa，延伸率≥38%。FLC₀（平面应变点主应变值）约为35-45%，是汽车覆盖件最常用的材料之一。DC04的FLC位置较高，成形性能优异，适合深冲和复杂形状零件。

**DP590（双相钢）**：屈服强度350-450MPa，抗拉强度≥590MPa，延伸率≥16%。FLC₀约为20-28%，明显低于DC04。DP590的强度高但成形性能较差，主要用于车身结构件和加强件，不适合深冲成形。

**AA6016-T4（铝合金）**：屈服强度110-160MPa，抗拉强度210-280MPa，延伸率≥24%。FLC₀约为25-35%，介于DC04和DP590之间。铝合金的密度仅为钢的1/3，是汽车轻量化的重要材料，但其成形性能不如低碳钢，需要更精确的工艺控制。

**AA5182-O（铝合金）**：屈服强度110-150MPa，抗拉强度250-310MPa，延伸率≥22%。FLC₀约为22-30%，主要用于汽车内板件。

**TRIP钢**：屈服强度400-550MPa，抗拉强度≥600MPa，延伸率≥20%。FLC₀约为22-30%。TRIP钢具有优异的强度和延伸率组合，但成形极限相对较低。

**热成形钢（22MnB5）**：热成形后抗拉强度≥1500MPa，但室温下塑性极差，FLC₀极低。热成形工艺通过加热至900-950°C进行成形，然后在模具中淬火，获得超高强度。DIC可以用于热成形过程中的高温应变测量。

**不同板材FLC对比的意义**：通过DIC测量不同板材的FLD，可以直观比较各种材料的成形性能，为汽车设计中的材料选择提供数据支撑。例如，在需要深冲成形的零件中，应选择FLC位置较高的材料（如DC04）；在需要高强度的结构件中，可以选择FLC位置较低但强度更高的材料（如DP590），但需要更精确的工艺控制。

## 8. 实验设计与实施建议

对于初次在成形极限测量中引入DIC的工程团队，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 亚光白底+亚光黑漆随机散斑，散斑尺寸3-5像素，确保在冲压过程中不脱落 |
| 试件尺寸 | 至少准备5种不同宽度的试件（如25/50/100/150/200mm），以覆盖不同应变路径 |
| 润滑条件 | 严格按照标准规定的润滑方式和润滑剂类型执行，摩擦条件对FLC影响显著 |
| 冲压速度 | 保持恒定速度（通常10-30mm/min），速度波动会影响应变路径 |
| 图像采集 | 帧率根据冲压速度确定，确保相邻图像变形量不超过子区大小的10% |
| 截线划分 | 在破裂前一状态的应变云图上，垂直于裂纹方向划分至少3条间隔大于2mm的截线 |
| 数据处理 | 使用二次曲线拟合截线上的应变数据，得到FLC数据点 |

**入门建议**：从DC04等成熟材料开始，验证DIC测量结果与传统CGA方法的一致性，建立信心后再扩展到高强度钢和铝合金等更具挑战性的材料。

## 9. 结语

汽车板料成形极限是冲压工艺设计的"安全边界"——精确测量这个边界，是提高材料利用率、降低废品率、优化零件设计的基础。

DIC技术为成形极限测量带来了从离散点到全场、从静态到动态、从低精度到高精度的全面升级。全场应变分布、颈缩起始识别、FLC数据点精确提取、应变路径追踪——这些能力使DIC成为现代成形极限测量中不可替代的技术手段。

XTDIC-FLC系统凭借其专为成形极限测量设计的硬件配置和软件功能，正在成为汽车板材成形极限表征的重要工具。随着汽车轻量化趋势的持续推进（铝合金、高强度钢、热成形钢的广泛应用），成形极限测量的精度要求将持续提高，DIC技术在汽车冲压领域的应用也将不断深化，从实验室研究走向在线工艺监控，为汽车制造的效率提升和质量保障提供更有力的技术支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: Automotive Sheet Metal Forming Limits—The "Safety Boundary" of Stamping](#1-introduction-automotive-sheet-metal-forming-limits-the-safety-boundary-of-stamping)
- [2. Forming Limit Diagram (FLD/FLC): The "Map" of Sheet Metal Failure](#2-forming-limit-diagram-fldflc-the-map-of-sheet-metal-failure)
- [3. Dilemmas of Traditional Forming Limit Measurement Methods](#3-dilemmas-of-forming-limit-measurement-methods)
- [4. How DIC Technology Revolutionizes Forming Limit Measurement](#4-how-dic-technology-revolutionizes-forming-limit-measurement)
- [5. XTDIC-FLC System: Purpose-Built for Forming Limit Measurement](#5-xtdic-flc-system-purpose-built-for-forming-limit-measurement)
- [6. Automotive Sheet Metal Forming Limit Measurement Standards](#6-automotive-sheet-metal-forming-limit-measurement-standards)
- [7. Forming Limit Characteristics of Typical Automotive Sheet Metals](#7-forming-limit-characteristics-of-typical-automotive-sheet-metals)
- [8. Experimental Design and Implementation Recommendations](#8-experimental-design-and-implementation-recommendations)
- [9. Conclusion](#9-conclusion)

---

## 1. Introduction: Automotive Sheet Metal Forming Limits—The "Safety Boundary" of Stamping

Automotive body panels—doors, hoods, fenders, roof panels—are almost entirely formed by metal sheet stamping. A typical passenger vehicle has approximately 300-500 stamped parts, with sheet thicknesses ranging from 0.5mm to 2.0mm, covering materials from mild steel, High-Strength Steel (HSS), Advanced High-Strength Steel (AHSS), to aluminum alloys.

During stamping, sheet metal experiences complex stress-strain states—tension, compression, stretching, deep drawing, bending. Each stress state corresponds to a "limit": beyond this limit, the sheet metal will undergo necking or fracture. This limit is the "Forming Limit," and it represents the safety boundary of stamping process design.

If sheet metal strain during stamping exceeds the forming limit, the part will crack—one of the most common defects in stamping production. Statistics show that approximately 40% of automotive stamping scrap rates are related to cracking and wrinkling. If process design is overly conservative, far from the forming limit, material utilization is low and costs increase. Precisely measuring the forming limit for each sheet material is the foundation for optimizing stamping processes, improving material utilization, and reducing scrap rates.

Forming limit measurement methods have evolved from mechanical to optical measurement. Traditional Circle Grid Analysis (CGA) requires printing grids on sheet surfaces, then measuring grid deformation with strain gauges after stamping—a method with low efficiency, limited accuracy, and inability to provide full-field strain information. The emergence of Digital Image Correlation (DIC) technology has brought revolutionary changes to forming limit measurement.

## 2. Forming Limit Diagram (FLD/FLC): The "Map" of Sheet Metal Failure

The Forming Limit Diagram (FLD), also known as the Forming Limit Curve (FLC), is a graphical tool describing the failure limits of metal sheets under different strain paths.

**Axis meanings**: The FLD horizontal axis represents minor strain (ε₂), and the vertical axis represents major strain (ε₁). Each point on the plane represents a strain state (ε₁, ε₂), i.e., the deformation mode at that point on the sheet.

**Strain path types**:
- **Uniaxial tension**: ε₂ = -ε₁/2 (Poisson effect), located on the left side of FLD
- **Plane strain**: ε₂ = 0, located at the lowest point at the bottom of FLD—the most dangerous strain state
- **Equi-biaxial stretching**: ε₂ = ε₁, located on the right side of FLD
- **Deep drawing**: ε₂ < 0 (compression), located in the lower-left area of FLD

**FLC significance**: The curve on the FLD (FLC) divides the strain space into two regions—below the curve is the "Safe Zone," where sheet metal will not undergo necking or fracture under that strain state; above the curve is the "Failure Zone," where sheet metal will undergo necking or fracture. The goal of stamping process design is to ensure all points on the sheet remain within the safety zone, while staying as close as possible to the FLC to fully utilize material.

**Factors affecting FLC**:
- **Material type**: Different materials have different FLC positions. Generally, higher-strength materials have lower FLC positions (worse formability)
- **Sheet thickness**: FLC₀ (major strain value at plane strain point) is approximately proportional to sheet thickness. Empirical formula: FLC₀ ≈ n/(1+n) × (1 + 0.5t), where n is the hardening index and t is thickness
- **Strain path**: FLD assumes linear strain paths; actual stamping nonlinear strain paths affect FLC shape
- **Temperature**: At elevated temperatures, material plasticity increases and FLC position shifts upward

## 3. Dilemmas of Traditional Forming Limit Measurement Methods

**Circle Grid Analysis (CGA)** is the traditional standard method for forming limit measurement. The process involves: printing circular grids (typically 2.5-5.0mm diameter) on sheet surfaces through chemical etching or electrochemical methods → stamping deformation → measuring deformed elliptical grids with strain gauges or optical tools → calculating major and minor strains → plotting FLD.

CGA's main problems:
- **Extremely low efficiency**: Each specimen provides only dozens of valid data points; plotting a complete FLD requires extensive repeated testing
- **Limited accuracy**: Strain gauge reading precision is approximately 0.5-1.0%, far below DIC's 0.005%
- **No full-field information**: Only measures strain at grid point locations, unable to present complete strain distribution on the sheet surface
- **Cannot identify necking onset**: CGA measures post-deformation strain, unable to determine when necking began
- **Large human error**: Grid deformation measurement relies on operator experience and judgment

**Strain gauge method**: Strain gauges are attached to sheet surfaces to measure local strain. The minimum gauge length (approximately 0.5mm) far exceeds DIC measurement resolution, and only provides single-point data. During stamping, strain gauges are easily peeled off or damaged.

**Extensometer method**: Used to measure average strain within a gauge length, unable to provide local strain information. In sheet metal forming, strain distribution is highly non-uniform, and extensometer averages cannot reflect true strain states.

The common problem with these traditional methods is that they are all discrete point measurements, unable to provide continuous strain field information, unable to precisely identify necking onset points, and unable to present the development of strain localization.

## 4. How DIC Technology Revolutionizes Forming Limit Measurement

DIC's core value in forming limit measurement lies in its ability to track the complete strain field evolution from uniform deformation to necking and fracture in a **full-field, real-time, precise** manner.

**Full-field strain distribution**: A single DIC measurement can obtain strain data for hundreds of thousands to millions of measurement points on the sheet surface. During stamping, this means completely presenting strain distribution from the blankholder to the punch radius, clearly identifying strain concentration areas—often the locations where necking and fracture initiate.

**Necking onset identification**: Necking is the critical transition from uniform to localized deformation. DIC monitors full-field strain distribution in real time to precisely identify the onset moment and location of necking. When strain growth rate in a particular area suddenly accelerates, significantly exceeding surrounding regions, this marks the beginning of necking.

**FLC data point extraction**: From DIC-measured full-field strain data, extract strain values at the moment before necking (or before fracture) as forming limit data points for that strain path. Through different die geometries (varying strain paths), data points covering the entire FLD can be obtained.

**Strain path tracking**: DIC can track the complete strain path (ε₁-ε₂ curve) of each measurement point throughout the deformation process, not just the final strain values. This is critical for studying the effects of nonlinear strain paths on forming limits.

**Fracture prediction**: By real-time monitoring of strain concentration zone development, DIC can predict fracture location and timing before fracture occurs, providing early warning for process optimization.

**Comparison with finite element simulation**: DIC-obtained full-field strain data can be directly compared with stamping finite element simulation results (such as AutoForm, PAM-STAMP, LS-DYNA) to verify simulation accuracy and optimize material model parameters.

## 5. XTDIC-FLC System: Purpose-Built for Forming Limit Measurement

The XTDIC-FLC system is a DIC measurement system purpose-built for metal sheet forming limit measurement, used in conjunction with Erichsen testers or sheet metal forming testing machines.

**System Components**:
- High-resolution industrial cameras (configurable 2.3MP-25MP)
- Fixed-focus or zoom lenses (selected based on measurement area)
- LED light source (uniform and stable, color temperature 5000-6500K)
- Erichsen tester or sheet metal forming testing machine
- XTDIC-FLC analysis software

**Measurement Workflow**:
1. **Speckle preparation**: Spray matte white base paint on sheet surface, then spray matte black paint to form random speckle. Speckle size is determined by camera resolution and measurement area, typically requiring each speckle to occupy 3-5 pixels.
2. **Camera calibration**: Use a calibration target matching the measurement area to complete camera intrinsic and extrinsic parameter calibration before testing.
3. **Stamping test**: Clamp the sheet specimen on the Erichsen tester; the punch presses into the sheet at a constant speed (typically 10-30mm/min). Cameras synchronously capture sheet deformation images.
4. **Image acquisition**: Capture frame rate is determined by stamping speed, typically 10-100fps, ensuring deformation between adjacent images does not exceed 10% of subset size.
5. **DIC analysis**: XTDIC software performs DIC analysis on captured image sequences, calculating full-field displacement and strain.
6. **FLC data extraction**: On the strain contour map of the state before fracture, draw three or more section lines perpendicular to the crack direction with intervals greater than 2mm. Perform quadratic curve fitting on strain data along each section line to obtain FLC data points for that strain path.
7. **FLD plotting**: Fit FLC data points from different strain paths into a complete FLD.

**Key Parameters**:
- Measurement area: 1mm×0.8mm to 10m×8m (depending on lens configuration)
- Strain range: 0.01%-500%+
- Strain precision: static 20με, dynamic 50με
- Displacement precision: ≤0.01 pixel
- Capture frame rate: up to 1500fps (depending on camera configuration)
- Supported standards: GB/T 15825.8-1995, GB/T 24171.1-2009, ISO 12004-2

**Software Features**:
- Full-field displacement and strain real-time calculation
- Automatic fracture frame localization
- Section line division and quadratic curve fitting
- Automatic FLC curve generation
- FLD plotting and material comparison
- Data export (CSV/ASCII format)

## 6. Automotive Sheet Metal Forming Limit Measurement Standards

**GB/T 15825.8-1995** "Metal Sheet Forming Performance and Test Methods—Forming Limit Diagram (FLD) Test" is China's national standard for forming limit measurement, specifying specimen dimensions, die geometry, test procedures, and data processing methods for FLD testing.

**GB/T 24171.1-2009** "Determination of Forming Limit Curves for Metallic Sheets—Part 1: Forming Limit Diagrams for Use in Stamping Shops" is a newer national standard aligned with ISO 12004-2, specifying more detailed test procedures and data processing methods.

**ISO 12004-2:2008** "Metallic materials — Sheet and strip — Determination of forming-limit curves — Part 2: Determination of forming-limit curves in the laboratory" is the ISO forming limit measurement standard, widely adopted by global automotive manufacturers.

**JIS Z 2253:2011** is the Japanese Industrial Standard for forming limit measurement, essentially consistent with ISO 12004-2.

Core requirements of these standards include:
- Specimen dimensions: Typically rectangular specimens with widths of 25mm, 50mm, 75mm, 100mm, 125mm, 150mm, 175mm, 200mm to cover different strain paths
- Die geometry: Punch diameter is typically 100mm (GB/T 15825.8) or 50mm (ISO 12004-2), die corner radius 5-10mm
- Lubrication conditions: Specified lubrication methods and lubricant types to control friction conditions
- Stamping speed: Typically 10-30mm/min
- Data processing: Specified section line division methods and fitting algorithms

## 7. Forming Limit Characteristics of Typical Automotive Sheet Metals

**DC04 (Extra Deep Drawing Steel)**: Carbon content ≤0.08%, yield strength 120-180MPa, tensile strength 270-350MPa, elongation ≥38%. FLC₀ (plane strain point major strain value) is approximately 35-45%. DC04 is one of the most commonly used materials for automotive body panels, with high FLC position and excellent formability, suitable for deep drawing and complex-shaped parts.

**DP590 (Dual Phase Steel)**: Yield strength 350-450MPa, tensile strength ≥590MPa, elongation ≥16%. FLC₀ is approximately 20-28%, significantly lower than DC04. DP590 has high strength but poor formability, mainly used for body structural parts and reinforcements, not suitable for deep drawing.

**AA6016-T4 (Aluminum Alloy)**: Yield strength 110-160MPa, tensile strength 210-280MPa, elongation ≥24%. FLC₀ is approximately 25-35%, between DC04 and DP590. Aluminum alloy density is only 1/3 that of steel, making it an important material for automotive lightweighting, but its formability is inferior to mild steel, requiring more precise process control.

**AA5182-O (Aluminum Alloy)**: Yield strength 110-150MPa, tensile strength 250-310MPa, elongation ≥22%. FLC₀ is approximately 22-30%, mainly used for automotive inner panels.

**TRIP Steel**: Yield strength 400-550MPa, tensile strength ≥600MPa, elongation ≥20%. FLC₀ is approximately 22-30%. TRIP steel has an excellent combination of strength and elongation, but relatively low forming limits.

**Press-Hardened Steel (22MnB5)**: Tensile strength ≥1500MPa after press hardening, but room temperature plasticity is extremely poor with very low FLC₀. The press hardening process involves heating to 900-950°C for forming, then quenching in the die to achieve ultra-high strength. DIC can be used for high-temperature strain measurement during press hardening.

**Significance of FLC comparison across materials**: By measuring FLDs of different materials using DIC, formability of various materials can be intuitively compared, providing data support for material selection in automotive design. For example, parts requiring deep drawing should use materials with higher FLC positions (such as DC04); structural parts requiring high strength can use materials with lower FLC positions but higher strength (such as DP590), but require more precise process control.

## 8. Experimental Design and Implementation Recommendations

For engineering teams introducing DIC into forming limit measurement for the first time, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle Preparation | Matte white base + matte black paint random speckles, speckle size 3-5 pixels, ensure no detachment during stamping |
| Specimen Dimensions | Prepare at least 5 different width specimens (e.g., 25/50/100/150/200mm) to cover different strain paths |
| Lubrication Conditions | Strictly follow standard-specified lubrication methods and lubricant types; friction conditions significantly affect FLC |
| Stamping Speed | Maintain constant speed (typically 10-30mm/min); speed fluctuations affect strain paths |
| Image Acquisition | Frame rate determined by stamping speed; ensure adjacent image deformation does not exceed 10% of subset size |
| Section Line Division | On the strain contour map of the state before fracture, draw at least 3 section lines perpendicular to the crack with intervals greater than 2mm |
| Data Processing | Use quadratic curve fitting on strain data along section lines to obtain FLC data points |

**Getting Started Recommendation**: Begin with well-established materials such as DC04 to verify consistency between DIC measurements and traditional CGA methods, build confidence, then extend to more challenging materials such as high-strength steels and aluminum alloys.

## 9. Conclusion

Automotive sheet metal forming limits are the "safety boundary" of stamping process design—precisely measuring this boundary is the foundation for improving material utilization, reducing scrap rates, and optimizing part design.

DIC technology has brought a comprehensive upgrade to forming limit measurement: from discrete points to full-field, from static to dynamic, from low precision to high precision. Full-field strain distribution, necking onset identification, precise FLC data point extraction, strain path tracking—these capabilities make DIC an indispensable technical means in modern forming limit measurement.

The XTDIC-FLC system, with its hardware configuration and software features purpose-built for forming limit measurement, is becoming an important tool for automotive sheet metal forming limit characterization. As automotive lightweighting trends continue (widespread adoption of aluminum alloys, high-strength steels, and press-hardened steels), forming limit measurement precision requirements will continue to increase. DIC technology applications in automotive stamping will continue to deepen—moving from laboratory research to inline process monitoring, providing stronger technical support for efficiency improvement and quality assurance in automotive manufacturing.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D XTDIC-FLC system documentation and automotive stamping application notes*
