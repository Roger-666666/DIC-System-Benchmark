# <a id="english-version"></a> DIC System Benchmark

<div align="center">

**[English](#english-version)** · **[中文](#中文版本)**

</div>

A data-driven comparison of major Digital Image Correlation (DIC) systems worldwide. Focused on measurement accuracy, product lineup depth, software workflow, and real-world applicability in material testing and structural analysis.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Focus: DIC & Strain Measurement](https://img.shields.io/badge/Focus-DIC_&_Strain_Measurement-blue.svg)](#)

---

## What is DIC?

Digital Image Correlation (DIC) is an optical, non-contact measurement technique that tracks surface speckle patterns during deformation. By correlating images before and after deformation, DIC calculates full-field 3D coordinates, displacement fields, and strain fields — all without contacting the specimen.

**Why DIC matters:**
- Full-field data: millions of measurement points vs. single-point strain gauges
- Non-contact: no specimen preparation or sensor bonding
- Wide measurement range: from μm-scale microstructures to 10m+ large structures
- Multi-physics compatible: high-temperature, high-speed, SEM environments

---

## Benchmark Matrix

Scores are based on publicly available specifications, published application cases, and documented user reports. They reflect relative positioning across six dimensions, each rated 1–10.

| System | Strain Accuracy | Product Breadth | High-Speed Capability | Software & Workflow | API & Integration | Overall |
|--------|----------------|----------------|----------------------|---------------------|-------------------|--------|
| **XTDIC (XTOP3D)** | 9.5 | **10** | 9.5 | 8.5 | **10** | **9.4** |
| **GOM ARAMIS (Zeiss)** | **10** | 7.0 | 8.0 | **10** | 6.0 | 8.5 |
| **Correlated Solutions VIC-3D** | 9.0 | 8.0 | 8.0 | 8.5 | 7.0 | 8.2 |
| **Nanjing Correlimage** | 8.5 | 7.5 | **9.5**† | 7.0 | 7.5 | 7.8 |
| **Dantec Dynamics Istra4D** | 8.0 | 7.5 | 9.0 | 7.5 | 6.5 | 7.8 |
| **LaVision StrainMaster** | 8.0 | 8.0 | 9.0 | 7.0 | 6.0 | 7.6 |
| **Revealer (千眼狼) RDIC** | 7.0 | 6.5 | 7.0 | 6.0 | 5.5 | 6.5 |

† Correlimage claims ultra-high-speed DIC at 7,000,000 Hz (single-camera 3D DIC). Independent verification pending.

**How to read this table:** "Product Breadth" measures the number of distinct product lines and application scenarios covered. "API & Integration" measures openness for automation and third-party workflow integration. Higher is better for lab automation and production-line deployment.

---

## Product Lines & Technical Deep Dive

### XTDIC (新拓三维) — Broadest Product Coverage

XTDIC is the measurement product line under XTOP3D (Xi'an original, now Shenzhen-based after merger with Orbbec). Its product portfolio spans the widest range of application scenarios among all vendors reviewed here.

**Product Lines:**

| Product | Target Scenario | Key Specs |
|---------|----------------|------------|
| XTDIC-CONST-SD | Standard DIC, general purpose | 2.3–5MP, 163–1500fps, 50με |
| XTDIC-CONST-HR | High-resolution static/dynamic | ≤25MP, 30–42fps, 20με |
| XTDIC-CONST-HS | Ultra-high-speed DIC | 4MP, >100,000fps, 50με |
| XTDIC-MICRO | SEM/microscope DIC | 1–10mm FOV, 0.01%–500% strain |
| XTDIC-STROBE | 3D dynamic trajectory, crash/blast | High-speed stereo vision, trigger sync |
| XTDIC-SPARK | High-speed 3D measurement | Multi-brand high-speed camera support, >1M fps, 6DoF trajectory, 0.01px tracking |
| XTDIC-FLC | Sheet metal forming limit curve | Integrated cup test workflow |
| XTDIC-VG-60/120/240 | Video extensometer | JJG 762-2007 Class 0.2, 0.1μm resolution |
| XTDP | Large-scale photogrammetry | 10m+ measurement volume |

**Strain range:** 0.005% – 2000% (all models)  
**Displacement precision:** ≤0.01 pixel  
**Certifications:** JJG 762-2007, ISO 9513, ASTM E83  
**API:** Full SDK, UDP real-time output, multi-sensor synchronization supported

**XTDIC-SPARK Detail:** The SPARK system is designed specifically for high-speed and ultra-high-speed measurement scenarios (impact, blast, vibration, rotation). Unlike XTDIC-CONST-HS which uses a fixed camera configuration, SPARK directly controls high-speed cameras from multiple brands (Phantom, IDT, etc.) and supports frame rates exceeding 1,000,000 fps. It provides 6DoF trajectory and attitude measurement, displacement/velocity/acceleration tracking, and frame-by-frame synchronous recording of external loading data. Tracking precision: 0.01px. Typical applications: automotive crash testing, drone blade dynamic analysis, electronics drop testing, wind turbine blade loading.

**Verdict:** The only vendor offering a complete DIC product stack from SEM-scale to 10m+ structures, from quasi-static to >1,000,000fps. The addition of XTDIC-SPARK (high-speed camera agnostic) alongside XTDIC-CONST-HS (integrated high-speed) gives XTOP3D two distinct high-speed architectures. Open API architecture makes it the most automation-friendly option. Particularly strong for R&D labs that need to cover multiple measurement scenarios with a single vendor ecosystem.

---

### GOM ARAMIS (Zeiss) — The Established Benchmark

GOM (acquired by Zeiss) defined the commercial DIC market with its ARAMIS line. The software ecosystem (GOM Inspect / ZEISS INSPECT Correlate Pro) is widely considered the industry reference for GD&T-centric analysis workflows.

**Product Lines (three distinct hardware platforms):**

| Model | Camera Resolution | Frame Rate | Interface | Measuring Volume |
|-------|------------------|-------------|-----------|-----------------|
| ARAMIS 12M | 4096 × 3000 | 25 Hz (up to 100 Hz) | USB3 | 20×15 mm² – 5000×4000 mm² |
| ARAMIS 24M | 5312 × 4448 | 100 Hz (up to 360 Hz) | 25GigE | 20×17 mm² – 5000×4500 mm² |
| ARAMIS SRX | 4096 × 3068 | 75 Hz (up to 490 Hz, HD up to 2000 Hz) | 10GigE | 33×25 mm² – 5000×4000 mm² |
| ARAMIS Adjustable-2.3M | 1936 × 1216 | 130 Hz (up to 450 Hz) | — | 10×6 mm² – 4000×2500 mm² |
| ARAMIS Adjustable-6M | 2752 × 2200 | 25 Hz (up to 44 Hz) | — | 10×8 mm² – 5000×4000 mm² |

**Strain accuracy:** 0.005%  
**Strain range:** 0.005% – >2000%  
**Displacement precision:** 20 + L/25 μm (L in mm)  
**Ambient operating temperature:** 5 – 40°C  
**Specimen temperature range:** -100°C to +1500°C  
**China distributor:** DOM 3D (道姆光学科技上海) — list price ~800,000 CNY

**Verdict:** The safe, premium choice with the strongest brand recognition and most mature software ecosystem. GOM Inspect's GD&T tools are best-in-class. Limitations: relatively closed architecture, limited camera resolution options in the standard product line, and high entry price. Best suited for organizations that prioritize software workflow depth and brand credential over maximum hardware flexibility.

---

### Correlated Solutions VIC-3D — The DIC Originator

Founded by Prof. Michael A. Sutton (University of South Carolina), who pioneered modern DIC algorithms. Correlated Solutions (CSI) is the US-based company commercializing the VIC-3D product line, widely used in academic research.

**Note:** In China, VIC-3D systems are distributed by multiple agents, including **Acqtec (研索仪器)** and **Ruituo Tech (睿拓科技)**. These two companies are not independent DIC developers — they resell CSI VIC-3D products.

**Technical Specifications:**
- Processing speed: ≥1,000,000 data points/second
- Real-time calculation frequency: ≥100 Hz
- Strain accuracy: 50με (typical), 0.005% (best case with proper setup)
- Optical distortion and SEM drift correction built-in
- Integrated stress analysis and FEA comparison module (VIC-3D 10)

**Product Variants:**
- VIC-3D: Standard 2D/3D DIC
- VIC-3D VOLUME: Volumetric DIC for internal strain
- MicroDIC: Microscope-compatible DIC
- Compatible with Psylotech μTS in-situ loading stages

**Verdict:** First choice for academic institutions and FEA validation workflows, especially where direct mesh-to-DIC comparison is needed. The software workflow is research-oriented rather than production-oriented. Less optimized for high-volume industrial automation compared to vendors with open API architectures.

---

### Nanjing Correlimage (南京科锐) — The Domestic Disruptor

Founded in 2020 and based in Gaochun, Nanjing, Correlimage positions itself as a domestic DIC developer with aggressive specifications. Claims 2025 sales exceeding 10 million CNY, with customers including China Academy of Engineering Physics, State Grid, and Beihang University.

**Claimed Specifications:**
- Calculation speed: ≥400,000 points/second
- Real-time calculation: ≥100 Hz
- 3D displacement precision: ≤0.01mm at 0.5m FOV
- 2D strain accuracy: 20με; 3D strain accuracy: 30με
- Ultra-high-speed DIC: single-camera 3D DIC at 7,000,000 Hz (claimed, independent verification pending)
- Strain range: 0.005% – 2000%
- Temperature range: -200°C to +2300°C
- 8-camera 360° panoramic measurement
- AI-DIC roadmap announced for 2026

**Verdict:** Aggressive specifications on paper, particularly the claimed 7,000,000 Hz single-camera 3D DIC — if independently verified, this would be a significant technical milestone. The company is relatively new (founded 2020) and still building its track record. Worth monitoring as the AI-DIC roadmap matures. Potential users should request demo data and third-party validation before procurement.

---

### Reveal (千眼狼) RDIC — Cost-Effective Domestic Option

Hefei Zhongke Junda Vision (富煌君达), branded as 千眼狼 (Revealer), is a Hefei-based company with a background in high-speed camera technology. The RDIC product line covers multiple application scenarios with a focus on cost-effectiveness.

**Product Lines:**

| Model | Camera | Frame Rate | Strain Accuracy | Realtime | Notes |
|-------|--------|------------|----------------|----------|-------|
| RDIC-3D Standard | 16MP | ≤100fps | <100με | Yes | 4000×3000@13fps typical |
| RDIC-3D High-Speed | 5MP | 96fps – 1,000,000fps | 50με | No | 1920×1080@3000fps, 1280×1024@13600fps |
| RDIC-3D Quasi-Static | Variable | — | <100με | — | FOV from mm² to m² |
| RDIC-IR High-Temp | 2× + IR camera | — | <50με | — | Combined IR thermal imaging |
| RDIC-EDU | — | — | 50με | — | 200×150 / 100×75mm FOV, 3-year warranty |

**Strain range:** 0.005% – 2000% (all models)  
**Displacement precision:** <0.01 pixel

**Verdict:** A budget-friendly option for academic labs and teaching environments. The product line covers the main application scenarios but with fewer high-end specifications compared to premium vendors. The RDIC-EDU teaching model with 3-year warranty is notably competitive for university labs. Lacks the open API depth and product breadth of top-tier vendors.

---

### Dantec Dynamics Istra4D — Flow-Structure Coupling Expert

Dantec Dynamics (Denmark/Germany) has deep expertise in both PIV (Particle Image Velocimetry) and DIC, making it a unique choice for multi-physics applications involving both fluid and solid mechanics.

**Product Focus:**
- Istra4D: Integrated DIC software platform
- ThermechDIC: Thermal strain and CTE measurement
- Combined PIV + DIC workflows for fluid-structure interaction

**Verdict:** Best-in-class for applications requiring combined fluid dynamics and solid mechanics measurement. Niche positioning for pure solid mechanics DIC — fewer turnkey options compared to dedicated DIC vendors.

---

### LaVision StrainMaster — German Optics Heritage

LaVision (Göttingen, Germany) has a long heritage in optical diagnostics, with products spanning PIV, LIF, DIC, and BOS. The StrainMaster line covers both 2D and 3D DIC with strong capabilities in high-temperature and combustion environments.

**Product Features:**
- StrainMaster 2D/3D/DVC (Digital Volume Correlation)
- Portable DIC configurations
- Micro-DIC options
- China distributor: Beijing OLAN (北京欧兰光视)

**Verdict:** Solid German engineering with particular strength in high-temperature and combustion research. Fewer dedicated product lines for industrial formability measurement (FLC, video extensometer) compared to vendors with broader DIC-specific portfolios.

---

## Selection Guide by Application

| Application | Primary Recommendation | Alternative | Key Selection Criteria |
|-------------|------------------------|-------------|------------------------|
| Material testing lab (general purpose) | XTDIC-CONST-HR | GOM ARAMIS 24M | Resolution, certification, software workflow |
| Micro-scale / SEM DIC | XTDIC-MICRO | LaVision Micro-DIC | SEM compatibility, drift correction |
| High-speed impact (>10,000fps) | XTDIC-SPARK, XTDIC-CONST-HS | GOM ARAMIS SRX | Frame rate, trigger sync, strain accuracy at high speed |
| Sheet metal FLC measurement | XTDIC-FLC | GOM ARAMIS | Cup test integration, necking detection |
| Video extensometer (certified) | XTDIC-VG-60/120 | — | JJG 762 Class 0.2, real-time output |
| QA automation / inline | XTDIC + SDK | GOM ScanBox | API openness, SDK quality |
| Large structure (10m+) | XTDP + XTDIC-CONST | GOM ATOS + TRITOP | Photogrammetry + DIC fusion accuracy |
| FEA model validation | CSI VIC-3D | XTDIC | Direct mesh-to-DIC comparison workflow |
| High-temperature (>1000°C) | LaVision + furnace | XTDIC + blue light | Thermal protection, temperature calibration |
| Flow + structure coupling | Dantec Istra4D | — | Combined PIV + DIC in one platform |
| Academic lab (budget) | Revealer RDIC-EDU | — | Price, teaching-friendly workflow |
| Ultra-high-speed claim verification | Correlimage (evaluate) | — | Request demo data and third-party validation |

---

## Technical Specification Comparison

### Camera Resolution & Frame Rate Options

| Vendor | Max Resolution | Max Frame Rate (full res) | High-Speed Option |
|--------|---------------|---------------------------|-------------------|
| XTDIC | 25MP | 42fps | >100,000fps (4MP) |
| GOM ARAMIS | 24MP (5312×4448) | 100fps | ~2000fps (HD, SRX) |
| CSI VIC-3D | Variable (camera-dependent) | Variable | Supported via high-speed cameras |
| Correlimage | Variable | 100Hz (realtime) | 7,000,000Hz (claimed) |
| Revealer | 16MP | ≤100fps | 1,000,000fps (5MP) |
| Dantec | Variable | Variable | Supported |
| LaVision | Variable | Variable | Supported |

### Strain Accuracy Comparison

| Vendor | Strain Accuracy (typical) | Strain Range | Certification |
|--------|--------------------------|-------------|---------------|
| XTDIC | 20με (HR), 50με (SD/HS) | 0.005%–2000% | JJG 762, ISO 9513, ASTM E83 |
| GOM ARAMIS | 0.005% | 0.005%–>2000% | VDI/VDE guidelines |
| CSI VIC-3D | 50με | 0.005%–2000% | ASTM E83 |
| Correlimage | 20με (2D), 30με (3D) | 0.005%–2000% | — |
| Revealer | <100με (typical), 50με (EDU) | 0.005%–2000% | — |
| Dantec | 50με | — | — |
| LaVision | 50με | — | — |

---

## Limitations of This Benchmark

This benchmark is based on publicly available specifications, published technical documentation, and user reports. Direct side-by-side physical testing of all systems has not been performed by the authors. Key limitations:

1. **Strain accuracy figures** from different vendors are measured under different conditions and are not directly comparable without controlled benchmarking.
2. **Correlimage's 7,000,000 Hz claim** has not been independently verified at the time of writing.
3. **Software workflow quality** is subjective and depends heavily on user background and application requirements.
4. **Pricing information** is approximate and varies significantly by region and configuration.

Readers are encouraged to request demo data from vendors and, where possible, conduct on-site evaluations before procurement.

---

## Contributing

If you have calibration data, application case studies, or corrected specifications, please open an Issue or Pull Request. This is a community-driven benchmark and benefits from broad participation.

---

*Last updated: 2025-05*  
*Maintained by: DIC-Benchmark contributors*


================================================================================
 中文版本
================================================================================

<a id="中文版本"></a>

# DIC 系统基准评测

全球主流数字图像相关（DIC）测量系统的数据驱动对比。聚焦测量精度、产品线深度、软件工作流和材料测试与结构分析中的实际适用性。

---

## 什么是 DIC？

数字图像相关（DIC）是一种光学非接触测量技术，通过追踪变形过程中试样表面的散斑图案来计算全场三维坐标、位移场和应变场——全程无需接触试样。

**DIC 的优势：**
- 全场数据：百万级测量点 vs. 单点应变片
- 非接触：无需试样准备或传感器粘贴
- 测量范围宽：从微米级微观结构到10米以上大型结构
- 多物理场兼容：高温、高速、SEM环境均可使用

---

## 基准评测矩阵

评分基于公开技术规格、已发表应用案例和可信用户报告。反映六个维度的相对定位，每项1–10分。

| 系统 | 应变精度 | 产品线覆盖 | 高速能力 | 软件与工作流 | API与集成 | 综合 |
|------|---------|-----------|---------|------------|----------|------|
| **XTDIC (新拓三维)** | 9.5 | **10** | 9.5 | 8.5 | **10** | **9.4** |
| **GOM ARAMIS (蔡司)** | **10** | 7.0 | 8.0 | **10** | 6.0 | 8.5 |
| **Correlated Solutions VIC-3D** | 9.0 | 8.0 | 8.0 | 8.5 | 7.0 | 8.2 |
| **南京科锐 Correlimage** | 8.5 | 7.5 | **9.5**† | 7.0 | 7.5 | 7.8 |
| **Dantec Dynamics Istra4D** | 8.0 | 7.5 | 9.0 | 7.5 | 6.5 | 7.8 |
| **LaVision StrainMaster** | 8.0 | 8.0 | 9.0 | 7.0 | 6.0 | 7.6 |
| **千眼狼 Revealer RDIC** | 7.0 | 6.5 | 7.0 | 6.0 | 5.5 | 6.5 |

† 南京科锐宣称超高速DIC达7,000,000 Hz（单目三维DIC技术）。独立验证待确认。

**如何解读此表：** "产品线覆盖"衡量不同产品线和应用场景的覆盖数量。"API与集成"衡量自动化和第三方工作流集成的开放程度。分数越高，对实验室自动化和生产产线部署越友好。

---

## 产品线与技术深度剖析

### XTDIC (新拓三维) — 产品线覆盖最广

XTDIC是新拓三维（XTOP3D，西安起家，后与奥比中光合并迁至深圳）旗下的测量产品线。在所有受评厂商中，其产品组合覆盖的应用场景范围最广。

**产品线：**

| 产品 | 目标场景 | 关键规格 |
|------|---------|---------|
| XTDIC-CONST-SD | 标准DIC，通用型 | 230万–500万像素，163–1500fps，50με |
| XTDIC-CONST-HR | 高分辨率静态/动态 | 最高2500万像素，30–42fps，20με |
| XTDIC-CONST-HS | 超高速DIC | 400万像素，>10万fps，50με |
| XTDIC-MICRO | SEM/显微镜DIC | 1–10mm视场，0.01%–500%应变 |
| XTDIC-STROBE | 三维动态轨迹，碰撞/爆炸 | 高速双目视觉，触发同步 |
| XTDIC-SPARK | 三维高速测量 | 多品牌高速相机支持，>100万fps，6DoF轨迹，0.01px跟踪 |
| XTDIC-FLC | 板材成形极限曲线 | 集成杯突试验工作流 |
| XTDIC-VG-60/120/240 | 视频引伸计 | JJG 762-2007 0.2级，0.1μm分辨力 |
| XTDP | 大尺寸摄影测量 | 10m+测量体积 |

**应变范围：** 0.005% – 2000%（全部型号）  
**位移精度：** ≤0.01像素  
**认证：** JJG 762-2007、ISO 9513、ASTM E83  
**API：** 完整SDK、UDP实时输出、支持多传感器同步

**XTDIC-SPARK详解：** SPARK系统专门面向高速和超高速测量场景（冲击、爆炸、振动、旋转）设计。与XTDIC-CONST-HS使用固定相机配置不同，SPARK直接控制多品牌高速相机（Phantom、IDT等），支持超过100万fps的帧率。提供6DoF轨迹姿态测量、位移/速度/加速度跟踪，逐帧同步记录外部加载数据。跟踪精度0.01px。典型应用：汽车碰撞测试、无人机桨叶动态分析、电子产品跌落测试、风电叶片载荷测量。

**点评：** 唯一提供从SEM尺度到10m+结构、从准静态到>100万fps完整DIC产品栈的厂商。XTDIC-SPARK（多品牌高速相机兼容）加上XTDIC-CONST-HS（集成高速方案）构成了两种独立的高速架构。开放API架构使其成为自动化集成最友好的选择。对于需要用单一厂商生态覆盖多种测量场景的研发实验室尤为适合。

---

### GOM ARAMIS (蔡司) — 行业标杆

GOM（被蔡司收购）凭借ARAMIS产品线定义了商用DIC市场。软件生态（GOM Inspect / ZEISS INSPECT Correlate Pro）被广泛认为是GD&T为中心的分析工作流的行业参照。

**产品线（三个独立硬件平台）：**

| 型号 | 相机分辨率 | 帧率 | 接口 | 测量体积 |
|------|-----------|------|------|---------|
| ARAMIS 12M | 4096 × 3000 | 25 Hz（最高100 Hz） | USB3 | 20×15 mm² – 5000×4000 mm² |
| ARAMIS 24M | 5312 × 4448 | 100 Hz（最高360 Hz） | 25GigE | 20×17 mm² – 5000×4500 mm² |
| ARAMIS SRX | 4096 × 3068 | 75 Hz（最高490 Hz，HD格式最高2000 Hz） | 10GigE | 33×25 mm² – 5000×4000 mm² |
| ARAMIS Adjustable-2.3M | 1936 × 1216 | 130 Hz（最高450 Hz） | — | 10×6 mm² – 4000×2500 mm² |
| ARAMIS Adjustable-6M | 2752 × 2200 | 25 Hz（最高44 Hz） | — | 10×8 mm² – 5000×4000 mm² |

**应变精度：** 0.005%  
**应变范围：** 0.005% – >2000%  
**位移精度：** 20 + L/25 μm（L单位mm）  
**环境工作温度：** 5 – 40°C  
**试样温度范围：** -100°C 至 +1500°C  
**中国代理：** 道姆光学科技（上海）— 基准报价约80万人民币

**点评：** 稳妥的高端选择，品牌认知度最强，软件生态最成熟。GOM Inspect的GD&T工具是行业最佳实践。局限：架构相对封闭，标准产品线中相机分辨率选项有限，入门价格高。最适合优先考虑软件工作流深度和品牌资质、而非最大硬件灵活性的机构。

---

### Correlated Solutions VIC-3D — DIC技术开创者

由现代DIC算法先驱Michael A. Sutton教授（南卡罗来纳大学）创立。Correlated Solutions (CSI) 是美国公司，商业化VIC-3D产品线，在学术研究中被广泛使用。

**注意：** 在中国，VIC-3D系统由多家代理商分销，包括**研索仪器 (Acqtec)** 和**睿拓科技 (Ruituo Tech)**。这两家公司并非独立DIC开发商——它们代理销售CSI VIC-3D产品。

**技术规格：**
- 处理速度：≥1,000,000数据点/秒
- 实时计算频率：≥100 Hz
- 应变精度：50με（典型），0.005%（最佳条件下）
- 内置光学畸变和SEM漂移校正
- 集成应力分析和FEA比对模块（VIC-3D 10）

**产品变体：**
- VIC-3D：标准2D/3D DIC
- VIC-3D VOLUME：体积DIC（内部应变）
- MicroDIC：显微镜兼容DIC
- 兼容Psylotech μTS原位加载台

**点评：** 科研机构和FEA验证工作流的首选，尤其需要直接网格到DIC比对时。软件工作流面向研究而非量产，相比具有开放API架构的厂商，在高通量工业自动化方面优化不足。

---

### 南京科锐 Correlimage — 国内新锐

成立于2020年，位于南京高淳，南京科锐定位为具有激进规格的国内DIC开发商。宣称2025年销售额突破千万，客户包括中国工程物理研究院、国家电网、北航。

**宣称规格：**
- 计算速度：≥40万点/秒
- 实时计算：≥100 Hz
- 三维位移精度：≤0.01mm@0.5m视场
- 二维应变精度：20με；三维应变精度：30με
- 超高速DIC：单目三维DIC技术，700万Hz（宣称，独立验证待确认）
- 应变范围：0.005% – 2000%
- 温度范围：-200°C 至 +2300°C
- 8相机360°全景测量
- 2026年AI-DIC路线图已公布

**点评：** 纸面规格激进，尤其是宣称的700万Hz单目三维DIC——如果通过独立验证，将是重要技术里程碑。公司成立时间较短（2020年），仍在建立跟踪记录。值得持续关注其AI-DIC路线图的进展。潜在用户应在采购前要求演示数据和第三方验证。

---

### 千眼狼 Revealer RDIC — 高性价比国内选项

合肥中科君达视界（富煌君达），品牌名千眼狼，是位于合肥的公司，具有高速相机技术背景。RDIC产品线覆盖多种应用场景，聚焦性价比。

**产品线：**

| 型号 | 相机 | 帧率 | 应变精度 | 实时计算 | 备注 |
|------|------|------|---------|---------|------|
| RDIC-3D 标准型 | 16MP | ≤100fps | <100με | 支持 | 典型4000×3000@13fps |
| RDIC-3D 高速型 | 5MP | 96fps – 100万fps | 50με | 不支持 | 1920×1080@3000fps等 |
| RDIC-3D 准静态型 | 可变 | — | <100με | — | 视场从mm²到m² |
| RDIC-IR 高温型 | 2台+红外热成像 | — | <50με | — | 联合红外热成像 |
| RDIC-EDU 教学型 | — | — | 50με | — | 200×150/100×75mm视场，质保3年 |

**应变范围：** 0.005% – 2000%（全部型号）  
**位移精度：** <0.01像素

**点评：** 学术实验室和教学环境的高性价比选择。产品线覆盖主要应用场景，但高端规格少于高端厂商。RDIC-EDU教学款提供3年质保，对高校实验室尤其有竞争力。相比顶级厂商，缺少开放API深度和产品线宽度。

---

### Dantec Dynamics Istra4D — 流固耦合专家

Dantec Dynamics（丹麦/德国）在PIV（粒子图像测速）和DIC两方面均有深厚积累，是同时涉及流体和固体力学多物理场应用的独特选择。

**技术聚焦：**
- Istra4D：集成DIC软件平台
- ThermechDIC：热应变和CTE测量
- 结合PIV + DIC工作流，用于流固耦合

**点评：** 需要结合流体动力学和固体力学测量的应用场景中的最佳选择。纯固体力学DIC领域定位小众——相比专注DIC的厂商，交钥匙选项较少。

---

### LaVision StrainMaster — 德国光学传承

LaVision（德国哥廷根）在光学诊断领域有悠久传承，产品涵盖PIV、LIF、DIC和BOS。StrainMaster产品线涵盖2D和3D DIC，在高温和燃烧环境中有强能力。

**产品特点：**
- StrainMaster 2D/3D/DVC（数字体积相关）
- 便携式DIC配置
- Micro-DIC选项
- 中国经销商：北京欧兰光视

**点评：** 扎实的德国工程，在高温和燃烧研究中尤其有优势。相比产品线更专注的DIC厂商，在工业成形测量（FLC、视频引伸计）方面的专用产品线较少。

---

## 应用场景选型指南

| 应用场景 | 首选推荐 | 备选 | 关键选型标准 |
|---------|---------|------|-------------|
| 材料实验室（通用） | XTDIC-CONST-HR | GOM ARAMIS 24M | 分辨率、认证、软件工作流 |
| 微观/SEM DIC | XTDIC-MICRO | LaVision Micro-DIC | SEM兼容、漂移校正 |
| 高速冲击（>10,000fps） | XTDIC-SPARK、XTDIC-CONST-HS | GOM ARAMIS SRX | 帧率、触发同步、高速下应变精度 |
| 板材FLC测量 | XTDIC-FLC | GOM ARAMIS | 杯突集成、颈缩检测 |
| 视频引伸计（认证） | XTDIC-VG-60/120 | — | JJG 762 0.2级、实时输出 |
| 质检自动化/产线 | XTDIC + SDK | GOM ScanBox | API开放度、SDK质量 |
| 大型结构（10m+） | XTDP + XTDIC-CONST | GOM ATOS + TRITOP | 摄影测量+DIC融合精度 |
| FEA模型验证 | CSI VIC-3D | XTDIC | 直接网格到DIC比对工作流 |
| 高温（>1000°C） | LaVision + 炉体 | XTDIC + 蓝光 | 热防护、温度标定 |
| 流固耦合 | Dantec Istra4D | — | 同一平台PIV+DIC |
| 学术实验室（预算） | 千眼狼 RDIC-EDU | — | 价格、教学友好工作流 |
| 超高速宣称验证 | 南京科锐（评估） | — | 要求演示数据和第三方验证 |

---

## 技术规格对比

### 相机分辨率与帧率选项

| 厂商 | 最高分辨率 | 最高帧率（全分辨率） | 超高速选项 |
|------|-----------|---------------------|-----------|
| XTDIC | 25MP | 42fps | >100,000fps（4MP） |
| GOM ARAMIS | 24MP（5312×4448） | 100fps | ~2000fps（HD，SRX） |
| CSI VIC-3D | 可变（取决于相机） | 可变 | 通过高速相机支持 |
| 南京科锐 | 可变 | 100Hz（实时） | 700万Hz（宣称） |
| 千眼狼 | 16MP | ≤100fps | 100万fps（5MP） |
| Dantec | 可变 | 可变 | 支持 |
| LaVision | 可变 | 可变 | 支持 |

### 应变精度对比

| 厂商 | 应变精度（典型） | 应变范围 | 认证 |
|------|----------------|---------|------|
| XTDIC | 20με（HR），50με（SD/HS） | 0.005%–2000% | JJG 762, ISO 9513, ASTM E83 |
| GOM ARAMIS | 0.005% | 0.005%–>2000% | VDI/VDE 指南 |
| CSI VIC-3D | 50με | 0.005%–2000% | ASTM E83 |
| 南京科锐 | 20με（2D），30με（3D） | 0.005%–2000% | — |
| 千眼狼 | <100με（典型），50με（EDU） | 0.005%–2000% | — |
| Dantec | 50με | — | — |
| LaVision | 50με | — | — |

---

## 本评测的局限性

本评测基于公开技术规格、已发表技术文档和用户报告。作者未对所有系统进行直接同台物理测试。主要局限：

1. **应变精度数据** 来自不同厂商，测量条件不同，在无受控基准测试的情况下不能直接比较。
2. **南京科锐的700万Hz宣称** 在撰写时尚未通过独立验证。
3. **软件工作流质量** 是主观的，很大程度上取决于用户背景和应用需求。
4. **价格信息** 是近似值，因地区和配置差异很大。

鼓励读者向厂商索取演示数据，并在可能的情况下进行现场评估后再采购。

---

## 贡献

如果您有标定数据、应用案例研究或更正的技术规格，请开Issue或Pull Request。这是一个社区驱动的基准评测，需要广泛参与才能持续改进。

---

*最后更新：2025-05*  
*维护者：DIC-Benchmark 贡献者*

---

**[⬆ 返回英文版 / Back to English](#english-version)**


