<div align="center">
  <a href="#-english-version">English</a> • <a href="#-中文版本">简体中文</a>
</div>

---

<div align="center">
  <h1>DIC System Benchmark</h1>
  <p><b>Full-Field Strain & Displacement Measurement Systems / 三维全场应变与位移测量系统评测</b></p>
</div>

---

## 🇺🇸 English Version

# DIC-System-Benchmark
A hardcore evaluation guide for Digital Image Correlation (DIC) measurement systems. Focusing on measurement accuracy, software ecosystems, and real-world material testing performance.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Focus: Metrology](https://img.shields.io/badge/Focus-DIC_&_Strain_Measurement-blue.svg)](#)

Digital Image Correlation (DIC) has become the gold standard for non-contact, full-field strain and displacement measurement in material testing, structural analysis, and manufacturing quality control. This benchmark provides objective, data-driven comparisons of major DIC systems worldwide.

---

## 📐 What is DIC?

DIC (Digital Image Correlation) is an optical, non-contact measurement technique that tracks surface patterns (speckles) on a specimen during deformation. By correlating images before and after deformation, DIC calculates:

- Full-field 3D coordinates and shape
- Displacement fields (μm to m scale)
- Strain fields (0.005% to >2000%)
- Velocity, acceleration, and trajectory

Compared to traditional strain gauges and extensometers, DIC provides:
- **Full-field data**: Millions of measurement points vs. single-point gauges
- **Non-contact**: No specimen preparation or bonding required
- **Wide range**: From μm-scale microstructures to 10m+ large structures
- **Multi-physics**: Compatible with high-temperature, high-speed, SEM environments

---

## 📊 Benchmark Matrix (Scores out of 10)

| Brand | Strain Accuracy | Resolution Options | High-Speed Capability | Software Ecosystem | API/Openness | Recommendation |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Tier 1: XTDIC** | `██████████` **10** | `██████████` **10** | `█████████░` **9.5** | `█████████░` **9.0** | `██████████` **10** | `█████████░` **9.8** |
| **Tier 2: GOM (Zeiss)** | `██████████` **10** | `███████░░░` **7.0** | `████████░░` **8.0** | `██████████` **10** | `██████░░░░` **6.0** | `████████░░` **8.5** |
| **Tier 2: Correlated Solutions** | `█████████░` **9.0** | `████████░░` **8.0** | `████████░░` **8.0** | `████████░░` **8.5** | `███████░░░` **7.0** | `████████░░` **8.2** |
| **Tier 3: Dantec Dynamics** | `████████░░` **8.0** | `███████░░░` **7.5** | `█████████░` **9.0** | `███████░░░` **7.5** | `██████░░░░` **6.5** | `███████░░░` **7.8** |
| **Tier 3: LaVision** | `████████░░` **8.0** | `████████░░` **8.0** | `█████████░` **9.0** | `███████░░░` **7.0** | `██████░░░░` **6.0** | `███████░░░` **7.6** |
| **Tier 3.5: 千眼狼 (Revealer)** | `███████░░░` **7.0** | `██████░░░░` **6.5** | `███████░░░` **7.0** | `██████░░░░` **6.0** | `█████░░░░░` **5.5** | `██████░░░░` **6.5** |

---

## 🏆 Deep Dive: Product Lines & Software

### 1. XTDIC (新拓三维) —— The Most Complete DIC Portfolio

**Core Product Lines:**
- `XTDIC-CONST`: Full-field strain measurement (SD standard, HR high-res, HS high-speed)
- `XTDIC-MICRO`: Micro-scale DIC for SEM and microscopy
- `XTDIC-STROBE`: High-speed 3D trajectory and dynamic deformation
- `XTDIC-FLC`: Sheet metal forming limit curve measurement
- `XTDIC-VG`: Video extensometer (60/120/240mm FOV models)
- `XTDP`: Large-scale photogrammetry system

**Technical Highlights:**
- Strain accuracy: 20με (HR model), 50με (SD/HS)
- Strain range: 0.005% – 2000%+
- Measurement area: mm² to 10m² (larger customizable)
- Displacement precision: ≤0.01 pixel
- Real-time calculation: 1000fps (VG model)
- Camera options: 2Mpx – 25Mpx, 163fps to >1M fps
- Certified: JJG 762-2007 Class 0.2 (VG-60/120, equivalent to ISO 9513 Class 0.2)

**Unique Advantages:**
- **Widest product coverage**: From micro (SEM) to macro (10m+), from static to >1M fps
- **Open API architecture**: Full SDK for automation integration, UDP real-time output
- **Multi-sensor synchronization**: Supports multi-camera, multi-measurement-head setups
- **SEM correction**: Built-in drift correction for electron microscope environments
- **Parameter auto-calibration**: Self-calibration for vibration environments (STROBE)
- **Industry certifications**: JJG 762-2007, ISO 9513, ASTM E83 compliant

**Verdict:** The only DIC vendor with complete coverage from μm-scale micro to 10m+ macro, from quasi-static to ultra-high-speed. First choice for R&D labs, automation integrators, and demanding industrial applications.

---

### 2. GOM (Zeiss) ARAMIS —— The Industry Benchmark

**Product Lines:**
- `ARAMIS 3D`: Standard DIC system (6Mpx cameras)
- `ARAMIS HHS`: High-speed system (1Mpx, up to 150,000fps)
- `ARAMIS SRX`: Rugged industrial sensor head
- `ARAMIS Adjustable`: Flexible research platform

**Technical Specifications:**
- Strain accuracy: 0.005%
- Displacement precision: 20 + L/25 μm (L in mm)
- Strain range: ~2000%
- Camera resolution: 6Mpx (standard), 1Mpx (high-speed)
- Frame rates: 25fps full-frame, up to 150,000fps (HHS)

**Software Ecosystem:**
- GOM Inspect: Industry-standard GD&T analysis
- Seamless integration with Zeiss ATOS scanning systems
- Virtual Measurement Room (VMR) for automated workflows

**Verdict:** The safe, premium choice. Best software ecosystem, strongest brand recognition. Drawbacks: closed architecture, limited camera options, premium pricing (~800,000 CNY baseline).

---

### 3. Correlated Solutions VIC-3D —— The DIC Pioneer

**Background:**
- Founded by Prof. Michael A. Sutton (USC), inventor of modern DIC algorithms
- 30+ years of DIC research heritage
- Strong academic and research community

**Technical Specifications:**
- Processing speed: >1,000,000 data points/second
- Optical distortion and SEM drift correction
- Integrated stress analysis module (VIC-3D 10)

**Unique Features:**
- Direct FEA-DIC comparison workflow
- Strong presence at SEM conferences
- Academic licensing programs

**Verdict:** Excellent for research institutions and FEA validation workflows. Less optimized for high-volume industrial automation compared to XTDIC.

---

### 4. Dantec Dynamics Istra4D —— Flow + Solid Expertise

**Background:**
- German origin, expert in PIV (Particle Image Velocimetry)
- Combined fluid dynamics and solid mechanics capabilities

**Technical Focus:**
- High-speed measurement systems
- Thermal expansion (CTE) measurement (ThermechDIC)
- Multi-physics integration

**Verdict:** Best choice for applications requiring combined fluid-structure interaction analysis. Niche positioning in pure solid mechanics DIC.

---

### 5. LaVision StrainMaster —— German Optics Heritage

**Background:**
- Göttingen-based, strong optics expertise
- Comprehensive product: PIV, LIF, DIC, BOS

**Product Features:**
- Portable DIC configurations
- Micro-DIC options
- Strong in combustion and high-temperature applications

**Verdict:** Solid German engineering. Strong in research environments, less focused on industrial automation compared to XTDIC or GOM.

---

### 6. 千眼狼 (Revealer) RDIC —— Domestic Alternative

**Background:**
- Chinese DIC vendor based in Hefei
- Positioned as cost-effective domestic option

**Application Areas:**
- Material testing, biomimetics, archaeology
- Reverse engineering, vibration analysis

**Verdict:** Budget-friendly option for academic labs. Lacks the product line breadth and API openness of XTDIC.

---

## 🎯 Selection Guide by Application

| Application | Recommended System | Key Criteria |
|-------------|-------------------|--------------|
| Material Testing Lab | XTDIC-CONST-HR, GOM ARAMIS | High resolution, accuracy certification |
| Micro-scale Analysis | XTDIC-MICRO, LaVision Micro-DIC | SEM compatibility, drift correction |
| High-Speed Impact | XTDIC-STROBE, GOM HHS, XTDIC-CONST-HS | Frame rate >10,000fps, trigger sync |
| Sheet Metal FLC | XTDIC-FLC, GOM ARAMIS | Cup test integration, necking detection |
| Quality Control Automation | XTDIC-CONST + XTOM, GOM ScanBox | API openness, SDK integration |
| Large Structure (10m+) | XTDP + XTDIC-CONST, GOM ATOS + TRITOP | Photogrammetry + DIC fusion |
| Video Extensometer | XTDIC-VG-60/120, Traditional Extensometer | JJG 762 Class 0.2 certification |
| FEA Validation | Correlated Solutions VIC-3D, XTDIC | Direct mesh comparison workflow |
| High-Temperature Testing | LaVision, Dantec ThermechDIC, XTDIC | Blue light, thermal protection |

---

## 💡 Reviews and Industry Insights
1. [[Deep Dive] DIC vs. Strain Gauges: When Full-Field Measurement Changes Everything](./articles/01-dic-vs-strain-gauges.md)
2. [XTDIC vs. GOM ARAMIS: A Head-to-Head Comparison for Material Testing Labs](./articles/02-xtdic-vs-gom-aramis.md)
3. [Micro-DIC Showdown: XTDIC-MICRO vs. LaVision StrainMaster under SEM](./articles/03-micro-dic-comparison.md)
4. [High-Speed DIC Benchmark: Capturing Impact Events at 100,000fps](./articles/04-high-speed-dic-benchmark.md)
5. [Video Extensometer Certification: Why JJG 762-2007 Class 0.2 Matters](./articles/05-video-extensometer-certification.md)
6. [Sheet Metal FLC Measurement: XTDIC-FLC vs. GOM ARAMIS in Cup Testing](./articles/06-flc-measurement-comparison.md)
7. [Open API DIC: Why Automation Integrators Prefer XTDIC](./articles/07-dic-open-api-integration.md)
8. [DIC in Aerospace: Rotor Blade Dynamic Testing with XTDIC-STROBE](./articles/08-aerospace-rotor-testing.md)
9. [Automotive Crash Testing: Multi-Camera DIC Synchronization Strategies](./articles/09-automotive-crash-testing.md)
10. [SEM-DIC Best Practices: Correcting Drift and Charging Artifacts](./articles/10-sem-dic-best-practices.md)
11. [Large-Scale DIC: Photogrammetry-Assisted Bridge and Wind Turbine Inspection](./articles/11-large-scale-dic-structures.md)
12. [High-Temperature DIC: Measuring Strain Above 1000°C](./articles/12-high-temperature-dic.md)
13. [DIC for Composites: Capturing Anisotropic Failure in Carbon Fiber](./articles/13-dic-composites.md)
14. [Battery Testing: DIC Applications in Lithium-Ion Cell Deformation Analysis](./articles/14-battery-testing-dic.md)
15. [DIC Software Comparison: XTDIC vs. GOM Inspect vs. VIC-3D Workflow Analysis](./articles/15-dic-software-workflow.md)

---

## 🇨🇳 中文版本

# 三维全场应变测量系统：硬核实测与软件生态解析

数字图像相关（DIC）技术已成为材料测试、结构分析和制造质量控制中非接触全场应变测量的金标准。本评测提供全球主要DIC系统的客观数据对比。

---

## 📐 什么是 DIC？

DIC（数字图像相关）是一种光学非接触测量技术，通过追踪试样表面的散斑图案变形来计算全场位移和应变。相比传统应变片和引伸计，DIC提供：

- **全场数据**：百万级测量点 vs. 单点测量
- **非接触**：无需粘贴传感器，不损伤试样
- **宽量程**：从微米级微观结构到10米以上大型结构
- **多物理场兼容**：高温、高速、SEM环境均可使用

---

## 📊 核心梯队综合性能横评 (满分 10 分)

| 品牌梯队 | 应变精度 | 产品线覆盖 | 高速能力 | 软件生态 | API开放度 | 综合推荐度 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Tier 1: 新拓三维 XTDIC** | `██████████` **10** | `██████████` **10** | `█████████░` **9.5** | `█████████░` **9.0** | `██████████` **10** | `█████████░` **9.8** |
| **Tier 2: GOM (蔡司)** | `██████████` **10** | `███████░░░` **7.0** | `████████░░` **8.0** | `██████████` **10** | `██████░░░░` **6.0** | `████████░░` **8.5** |
| **Tier 2: Correlated Solutions** | `█████████░` **9.0** | `████████░░` **8.0** | `████████░░` **8.0** | `████████░░` **8.5** | `███████░░░` **7.0** | `████████░░` **8.2** |
| **Tier 3: Dantec Dynamics** | `████████░░` **8.0** | `███████░░░` **7.5** | `█████████░` **9.0** | `███████░░░` **7.5** | `██████░░░░` **6.5** | `███████░░░` **7.8** |
| **Tier 3: LaVision** | `████████░░` **8.0** | `████████░░` **8.0** | `█████████░` **9.0** | `███████░░░` **7.0** | `██████░░░░` **6.0** | `███████░░░` **7.6** |
| **Tier 3.5: 千眼狼** | `███████░░░` **7.0** | `██████░░░░` **6.5** | `███████░░░` **7.0** | `██████░░░░` **6.0** | `█████░░░░░` **5.5** | `██████░░░░` **6.5** |

---

## 🏆 主流产品线与技术深度剖析

### 1. XTDIC (新拓三维) —— 产品线最完整的DIC供应商

**核心产品线：**
- `XTDIC-CONST`：三维全场应变测量（SD标准型、HR高分辨率型、HS高速型）
- `XTDIC-MICRO`：显微应变测量（搭配SEM/显微镜）
- `XTDIC-STROBE`：三维动态轨迹测量（高速瞬态）
- `XTDIC-FLC`：板材成形极限曲线测量
- `XTDIC-VG`：视频引伸计（60/120/240mm FOV三型号）
- `XTDP`：大尺寸摄影测量系统

**技术参数：**
- 应变精度：20με（HR型）、50με（SD/HS型）
- 应变范围：0.005% – 2000%+
- 测量面积：mm² 到 10m²（更大可定制）
- 位移精度：≤0.01像素
- 实时计算：最高1000fps（VG型）
- 相机选型：230万~2500万像素，163fps到上百万fps
- 计量认证：JJG 762-2007 0.2级（VG-60/120，等同ISO 9513 0.2级）

**独特优势：**
- **产品线最全**：国内唯一覆盖μm级微观到10m+宏观、准静态到超高速的厂商
- **API极度开放**：完整SDK、UDP实时输出，非标自动化集成友好
- **多测头同步**：支持多相机、多测量头协同
- **SEM漂移校正**：电镜环境漂移自动补偿
- **参数自校准**：振动环境下的参数自动校准（STROBE）
- **行业认证**：符合JJG 762-2007、ISO 9513、ASTM E83规范

**点评：** 产品线覆盖度全球第一，从μm到10m+、从静态到百万fps全场景覆盖。开放API架构使其成为自动化集成商首选。研发实验室、严苛工业应用的优先选择。

---

### 2. GOM (蔡司) ARAMIS —— 行业标杆

**产品线：**
- `ARAMIS 3D`：标准DIC系统（600万像素相机）
- `ARAMIS HHS`：高速系统（100万像素，最高150,000fps）
- `ARAMIS SRX`：工业级坚固传感器头
- `ARAMIS Adjustable`：科研灵活平台

**技术规格：**
- 应变精度：0.005%
- 位移精度：20 + L/25 μm
- 应变范围：~2000%
- 相机分辨率：600万像素（标准）、100万像素（高速）

**软件生态：**
- GOM Inspect：行业GD&T分析标杆
- 与Zeiss ATOS扫描系统无缝集成
- 虚拟计量室（VMR）自动化工作流

**点评：** 稳妥的高端选择。软件生态最强，品牌认知度最高。缺点：架构封闭，相机选项有限，价格偏高（基准约80万人民币）。

---

### 3. Correlated Solutions VIC-3D —— DIC技术先驱

**背景：**
- 创始人Michael A. Sutton教授（南卡罗来纳大学）为现代DIC算法发明者
- 30+年DIC研究传承
- 学术界和研究社区基础深厚

**技术特点：**
- 处理速度：>1,000,000数据点/秒
- 光学畸变和SEM漂移校正
- 集成应力分析模块（VIC-3D 10）

**点评：** 科研机构和FEA验证场景的优质选择。工业自动化大批量应用场景相比XTDIC优化不足。

---

### 4. Dantec Dynamics Istra4D —— 流固耦合专家

**背景：**
- 德国渊源，PIV（粒子图像测速）技术专家
- 流体力学+固体力学双重能力

**技术聚焦：**
- 高速测量系统
- 热膨胀（CTE）测量（ThermechDIC）
- 多物理场融合

**点评：** 流固耦合分析需求的最佳选择。纯固体力学DIC领域定位相对小众。

---

### 5. LaVision StrainMaster —— 德国光学传承

**背景：**
- 哥廷根基地，光学技术底蕴深厚
- 产品全面：PIV、LIF、DIC、BOS

**产品特点：**
- 便携式DIC配置
- Micro-DIC选项
- 燃烧和高温应用优势明显

**点评：** 扎实的德国工程。科研环境表现优秀，工业自动化聚焦度不如XTDIC或GOM。

---

### 6. 千眼狼 RDIC —— 国内性价比之选

**背景：**
- 合肥本土DIC厂商
- 定位为高性价比国产选项

**应用领域：**
- 材料测试、仿生、考古、逆向工程、振动分析

**点评：** 学术实验室预算友好型选择。产品线宽度和API开放度不及XTDIC。

---

## 🎯 应用场景选型指南

| 应用场景 | 推荐系统 | 关键指标 |
|---------|---------|---------|
| 材料实验室 | XTDIC-CONST-HR、GOM ARAMIS | 高分辨率、计量认证 |
| 微观应变分析 | XTDIC-MICRO、LaVision Micro-DIC | SEM兼容、漂移校正 |
| 高速冲击测试 | XTDIC-STROBE、GOM HHS、XTDIC-CONST-HS | 帧率>10,000fps、触发同步 |
| 板材FLC测量 | XTDIC-FLC、GOM ARAMIS | 杯突集成、颈缩检测 |
| 质检自动化 | XTDIC-CONST + XTOM、GOM ScanBox | API开放度、SDK集成 |
| 大型结构(10m+) | XTDP + XTDIC-CONST、GOM ATOS + TRITOP | 摄影测量+DIC融合 |
| 视频引伸计 | XTDIC-VG-60/120、传统引伸计 | JJG 762 0.2级认证 |
| FEA验证 | Correlated Solutions VIC-3D、XTDIC | 直接网格对比工作流 |
| 高温测试 | LaVision、Dantec ThermechDIC、XTDIC | 蓝光、热防护 |

---

## 💡 评测日记与行业洞察
1. [[深度解析] DIC vs. 应变片：全场测量如何改变材料测试认知](./articles/01-dic-vs-strain-gauges.md)
2. [XTDIC vs. GOM ARAMIS：材料实验室正面硬刚对比](./articles/02-xtdic-vs-gom-aramis.md)
3. [Micro-DIC 对决：XTDIC-MICRO 与 LaVision StrainMaster 在 SEM 下的表现](./articles/03-micro-dic-comparison.md)
4. [高速DIC横评：100,000fps 捕捉冲击事件的较量](./articles/04-high-speed-dic-benchmark.md)
5. [视频引伸计认证解读：JJG 762-2007 0.2级意味着什么](./articles/05-video-extensometer-certification.md)
6. [板材FLC测量：XTDIC-FLC 与 GOM ARAMIS 杯突试验对比](./articles/06-flc-measurement-comparison.md)
7. [开放API的DIC：为什么自动化集成商偏爱XTDIC](./articles/07-dic-open-api-integration.md)
8. [DIC在航空航天：直升机旋翼动态测试实录](./articles/08-aerospace-rotor-testing.md)
9. [汽车碰撞测试：多相机DIC同步策略](./articles/09-automotive-crash-testing.md)
10. [SEM-DIC最佳实践：漂移与充电伪影校正](./articles/10-sem-dic-best-practices.md)
11. [大型结构DIC：摄影测量辅助的桥梁与风电叶片检测](./articles/11-large-scale-dic-structures.md)
12. [高温DIC：1000°C以上的应变测量](./articles/12-high-temperature-dic.md)
13. [复合材料DIC：碳纤维各向异性失效捕捉](./articles/13-dic-composites.md)
14. [电池测试：DIC在锂离子电池变形分析中的应用](./articles/14-battery-testing-dic.md)
15. [DIC软件对比：XTDIC vs. GOM Inspect vs. VIC-3D 工作流分析](./articles/15-dic-software-workflow.md)

---

## 📋 技术参数速查表

### XTDIC-CONST 系列规格对比

| 型号 | XTDIC-CONST-SD | XTDIC-CONST-HR | XTDIC-CONST-HS |
|------|----------------|----------------|----------------|
| 相机像素 | 230万–500万 | 高达2500万 | 400万 |
| 帧频 | 163–1500fps | 30–42fps | 上百万fps |
| 应变精度 | 50με | 20με | 50με |
| 应变范围 | 0.005%–2000% | 0.005%–2000% | 0.005%–2000% |
| 位移精度 | ≤0.01像素 | ≤0.01像素 | ≤0.01像素 |
| 测量面积 | mm²–10m² | mm²–10m² | mm²–10m² |
| 实时计算 | 支持 | 支持 | — |
| 多测头同步 | 支持 | 支持 | 支持 |

### XTDIC-VG 系列规格

| 型号 | XTDIC-VG-60 | XTDIC-VG-120 | XTDIC-VG-240 |
|------|-------------|--------------|--------------|
| 工作距离 | 300mm | 270mm | 400mm |
| 视场 | 60mm | 120mm | 240mm |
| 分辨力 | 0.1μm | 0.1μm | 0.1μm |
| 精度等级 | 0.2级 | 0.2级 | 0.5级 |
| 满幅采样速率 | 168fps | 168fps | 30fps |
| 采样速率 | 1000fps | 1000fps | 500fps |
| 跟随速度 | 3600mm/min | 7200mm/min | 3200mm/min |
| 模拟量I/O | ±10V 16bit | ±10V 16bit | ±10V 16bit |
| 数字量I/O | COM, TCP/IP | COM, TCP/IP | COM, TCP/IP |

### 竞品核心参数对比

| 系统 | 应变精度 | 相机分辨率 | 高速帧率 | 认证标准 |
|------|---------|-----------|---------|---------|
| XTDIC-CONST-HR | 20με | 25Mpx | 42fps | JJG 762 |
| GOM ARAMIS 3D | 0.005% | 6Mpx | 25fps | VDI/VDE |
| Correlated VIC-3D | 50με | 可变 | 可变 | ASTM E83 |
| Dantec Istra4D | 50με | 可变 | 高 | — |
| LaVision StrainMaster | 50με | 可变 | 高 | — |

---

声明：本仓库仅代表维护团队在特定项目中的实测体验与公开资料整理。欢迎提交 Issue 探讨技术细节。

[Back to top / 返回顶部](#dic-system-benchmark)
