# DIC技术在新型建筑混凝土浇筑过程墙壁振动变形监测中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：混凝土浇筑过程监测的工程背景](#1-引言混凝土浇筑过程监测的工程背景)
- [2. 混凝土浇筑过程中的墙体振动与变形机制](#2-混凝土浇筑过程中的墙体振动与变形机制)
- [3. 传统监测方法的局限性](#3-传统监测方法的局限性)
- [4. DIC技术用于混凝土浇筑监测的核心优势](#4-dic技术用于混凝土浇筑监测的核心优势)
- [5. 混凝土浇筑DIC测量的关键技术环节](#5-混凝土浇筑dic测量的关键技术环节)
  - [5.1 大面积散斑制备](#51-大面积散斑制备)
  - [5.2 多相机协同与视场覆盖](#52-多相机协同与视场覆盖)
  - [5.3 动态采集与振动频率匹配](#53-动态采集与振动频率匹配)
  - [5.4 环境适应性设计](#54-环境适应性设计)
- [6. XTDIC系统在混凝土浇筑监测中的实施方案](#6-xtdic系统在混凝土浇筑监测中的实施方案)
  - [6.1 设备配置方案](#61-设备配置方案)
  - [6.2 现场部署与工作流程](#62-现场部署与工作流程)
- [7. 典型应用场景](#7-典型应用场景)
  - [7.1 高层住宅剪力墙浇筑监测](#71-高层住宅剪力墙浇筑监测)
  - [7.2 大体积混凝土基础底板浇筑](#72-大体积混凝土基础底板浇筑)
  - [7.3 桥梁墩柱浇筑过程监测](#73-桥梁墩柱浇筑过程监测)
  - [7.4 地下连续墙浇筑质量监控](#74-地下连续墙浇筑质量监控)
- [8. 数据驱动的施工质量闭环控制](#8-数据驱动的施工质量闭环控制)
- [9. 实验设计与现场实施建议](#9-实验设计与现场实施建议)
- [10. 结语](#10-结语)

---

## 1. 引言：混凝土浇筑过程监测的工程背景

混凝土浇筑是建筑施工中最关键的工序之一。浇筑过程中，混凝土浆体对模板系统产生巨大的侧压力，同时振捣作业引起模板和已浇筑结构的持续振动。当浇筑速度过快、模板刚度不足或振捣参数不当时，墙体结构可能产生过大的变形甚至发生胀模、爆模等质量事故。

根据住建部发布的《混凝土结构工程施工规范》（GB 50666-2011），混凝土浇筑时模板的侧向位移应控制在设计允许范围内，一般不超过模板高度的1/1000且不大于3mm。然而，传统的监测手段——如位移传感器、倾角仪等——只能获取有限测点的数据，难以全面反映墙体表面的变形分布和振动模态。

随着装配式建筑和超高层建筑的快速发展，混凝土浇筑速度不断提高（高层核心筒浇筑速度可达每小时3-5米），模板系统承受的动荷载更加复杂。在此背景下，需要一种能够实时获取全场变形数据、适应恶劣施工环境的非接触式测量技术。

数字图像相关（DIC）技术为这一需求提供了可行的技术路径。

## 2. 混凝土浇筑过程中的墙体振动与变形机制

混凝土浇筑过程中的墙体变形来源于多种荷载的叠加作用：

**混凝土侧压力**：新浇混凝土呈流态，对模板产生类似静水压力的侧向作用力。侧压力最大值出现在浇筑面以下约1/3高度处，与浇筑速度、混凝土坍落度、外加剂类型和振捣方式密切相关。根据GB 50666-2011，普通混凝土的侧压力可按以下公式计算：

F = min(0.22γ_c t_0 β_1 β_2 V^{1/2}, γ_c H)

其中γ_c为混凝土重度（约24kN/m³），t_0为初凝时间，β_1为外加剂影响系数，β_2为坍落度影响系数，V为浇筑速度，H为有效压头高度。对于C40普通混凝土（坍落度180mm，浇筑速度2m/h），最大侧压力约为50-60kPa。

**振捣器激振力**：插入式振捣器工作时产生的激振频率通常在80-200Hz范围内，振幅0.5-2mm。当振捣器频率接近模板系统的固有频率时，可能引起共振，导致模板振幅急剧增大。钢模板的固有频率通常在30-80Hz之间（取决于模板厚度和加劲肋间距），与振捣器频率存在重叠区域。

**泵送冲击荷载**：混凝土泵送过程中，泵管出口处的混凝土流速可达1-2m/s，对模板产生周期性冲击荷载。泵送频率与泵车排量和泵管直径相关，一般在0.5-3Hz范围内。

**温度效应**：大体积混凝土浇筑过程中，水泥水化热导致混凝土内部温度升高（可达60-80°C），热膨胀使模板产生附加变形。对于3m厚的底板，水化热引起的模板侧向膨胀可达1-2mm。

这些荷载的叠加作用使得墙体模板系统在浇筑过程中处于复杂的动态变形状态，传统的单点测量方法难以全面捕捉。

## 3. 传统监测方法的局限性

**位移传感器（LVDT/拉线式）**：需要在模板上安装固定支架和传感器，施工干扰大。传感器数量有限（通常每面墙2-3个测点），无法获取全场变形分布。在振动工况下，传感器连接件容易松动，数据可靠性下降。

**倾角仪**：只能测量模板整体的倾斜角度，无法反映局部变形和振动模态。对于高度超过4m的墙体，倾角仪的测量精度不足以满足规范要求。

**全站仪/水准仪**：需要人工逐点测量，无法实现实时动态监测。在浇筑作业面上，测量人员的安全风险高，且测量频率无法满足振动监测的需求。

**应变片**：需要粘贴在模板表面，施工环境下容易损坏。只能测量单点应变，无法获取全场分布。混凝土浆液飞溅和振动工况下，应变片存活率低。

这些局限性使得传统方法难以满足现代混凝土施工对变形监测的全面性、实时性和安全性要求。

## 4. DIC技术用于混凝土浇筑监测的核心优势

DIC技术通过追踪模板表面散斑图案的位移和变形，实现非接触式全场测量。相比传统方法，其核心优势体现在：

**全场数据获取**：单次测量即可获得模板表面百万级测点的三维位移和应变数据，完整呈现模板的变形分布、振动模态和应变集中区域。

**非接触测量**：不干扰浇筑施工，不需要在模板上安装任何传感器或支架，避免了传统方法对施工工序的影响。

**实时动态监测**：配合高速相机，可实时采集模板振动数据，帧率可达数百至上千帧每秒，满足振捣器激振频率（80-200Hz）的采样要求。

**全场振动模态分析**：通过FFT频域分析，可从全场位移数据中提取模板系统的固有频率、振型和阻尼比，为振捣参数优化提供依据。

**恶劣环境适应**：DIC系统可远距离部署（距模板2-10m），避免混凝土浆液飞溅和振动对设备的直接影响。

## 5. 混凝土浇筑DIC测量的关键技术环节

### 5.1 大面积散斑制备

混凝土浇筑现场的散斑制备面临特殊挑战：模板面积大（单面墙模板可达50-200㎡）、模板反复使用、施工环境潮湿。

**散斑方案选择**：
- **模板表面直接制备**：在模板面板上喷涂耐高温亚光漆作为底色，再用模板或喷枪制作随机散斑图案。散斑尺寸根据相机距离和分辨率确定，一般要求每个散斑在图像中占3-5像素。
- **预制散斑贴纸**：在工厂预制带有随机散斑图案的不干胶贴纸，现场直接粘贴在模板表面。这种方式散斑质量稳定，施工效率高，适合标准化模板体系。
- **自然纹理利用**：对于钢模板，其表面轧制纹理和焊缝痕迹可作为天然散斑，但对比度较低，需要增强照明。

**散斑耐久性**：考虑到模板的多次周转使用，散斑材料应具有足够的耐磨性和耐水性。陶瓷基散斑涂层可耐受50次以上的拆模-清理-重装循环。

### 5.2 多相机协同与视场覆盖

单台相机的视场有限，对于大面积墙体模板，需要多台相机协同工作：

**相机布局原则**：
- 相机沿墙体长度方向等间距布置，相邻相机视场重叠率≥20%
- 相机光轴垂直于模板表面，偏角≤15°
- 相机距模板表面的距离根据镜头焦距和测量幅面确定，一般为2-8m

**多相机同步**：多台相机通过硬件触发信号同步采集，同步精度≤1μs。XTDIC系统支持1-8相机组同步工作，通过统一的坐标系标定实现多视场数据的自动拼接。

**视场拼接**：相邻相机视场重叠区域的同名点数据进行加权平均，消除拼接缝，形成完整的全场变形数据。

### 5.3 动态采集与振动频率匹配

混凝土浇筑过程中的振动频率范围较宽，需要根据监测目标选择合适的采集帧率：

| 振动源 | 频率范围 | 推荐帧率 | 监测目标 |
|--------|---------|---------|---------|
| 泵送冲击 | 0.5–3Hz | 30–60fps | 模板整体位移 |
| 振捣器激振 | 80–200Hz | 500–2000fps | 模板局部振动 |
| 模板共振 | 30–80Hz | 200–500fps | 模态参数识别 |
| 风荷载 | 0.1–5Hz | 10–30fps | 整体稳定性 |

**采样定理应用**：根据奈奎斯特采样定理，采集帧率应至少为最高关注频率的2.5倍以上。对于200Hz的振捣器激振，推荐帧率不低于500fps。

**长时间连续监测**：混凝土浇筑持续时间可达数小时甚至数十小时，DIC系统需要具备长时间连续采集和存储能力。XTDIC系统支持SSD直写存储，单台相机可连续采集数小时的高帧率数据。

### 5.4 环境适应性设计

施工现场环境恶劣，DIC系统需要具备相应的防护措施：

**防水防尘**：相机和镜头采用IP65以上防护等级的防护罩，防止混凝土浆液飞溅和水雾侵蚀。

**照明补偿**：施工现场光照条件变化大（白天阳光直射到夜间施工照明），采用主动LED照明系统，确保散斑图像亮度稳定。推荐使用高显色指数（CRI≥90）的LED面板灯，色温5000-5600K。

**设备固定**：相机安装在三脚架或专用固定支架上，支架底部配重或锚固，防止设备因振动而移位。

**线缆保护**：数据线和电源线采用耐磨护套，沿脚手架或地面敷设，避免被施工机械碾压。

## 6. XTDIC系统在混凝土浇筑监测中的实施方案

### 6.1 设备配置方案

针对混凝土浇筑监测的需求，XTDIC系统提供以下配置：

**标准配置（全场变形+低频振动）**：
- XTDIC-CONST-SD（2.3–5MP，163–1500fps，50με）
- 适用于模板整体变形监测和泵送冲击荷载分析
- 双目立体视觉，三维全场测量
- 测量幅面：2m×1.5m至10m×8m（可调）

**高频振动配置（振捣器激振+模态分析）**：
- XTDIC-CONST-HS（4MP，>10万fps，50με）
- 适用于振捣器激振频率范围内的模板振动测量
- 高帧率采集，支持FFT频域分析

**关键参数**：
- 应变范围：0.005%–2000%
- 位移精度：≤0.01像素（对应实物约0.01–0.1mm，取决于测量距离和镜头）
- 测量幅面：50mm–10m
- 同步能力：1–8相机组同步采集

### 6.2 现场部署与工作流程

**第一步：散斑制备与系统标定**
- 在模板表面制备散斑（按5.1节方案）
- 相机就位后进行三维标定，使用标准标定板
- 标定精度验证：重投影误差≤0.05像素

**第二步：浇筑前基线采集**
- 在混凝土浇筑开始前，采集模板初始状态图像
- 记录模板在自重和施工荷载下的初始变形
- 建立变形监测的基准坐标系

**第三步：浇筑过程实时监测**
- 混凝土浇筑开始后，DIC系统连续采集模板变形数据
- 实时显示模板全场位移云图和关键点位移时程曲线
- 当位移超过预警阈值（如2mm）时，系统自动报警

**第四步：振捣参数优化**
- 在振捣器作业期间，采集模板振动数据
- 通过FFT分析识别模板固有频率和振型
- 调整振捣器频率和插入位置，避免共振

**第五步：数据分析与报告**
- 生成浇筑过程模板变形报告
- 包括最大变形量、变形分布图、振动频谱分析
- 为后续类似工程提供参考数据

## 7. 典型应用场景

### 7.1 高层住宅剪力墙浇筑监测

高层住宅剪力墙厚度通常为200-300mm，层高3-4m，浇筑速度快（每小时2-4m），模板侧压力大。

**监测重点**：模板中下部最大侧压力区域的变形、振捣引起的模板振动、相邻模板接缝处的相对位移。

**DIC价值**：替代传统位移传感器，实现模板全场变形实时监测。某32层住宅项目采用DIC监测后，剪力墙浇筑合格率从92%提升至98%，胀模事故率降低80%。

### 7.2 大体积混凝土基础底板浇筑

大体积混凝土基础底板厚度可达2-5m，一次浇筑量可达数千立方米。浇筑时间长（12-48小时），模板系统承受持续的混凝土侧压力和水化热膨胀力。

**监测重点**：模板侧向位移的时变特性、水化热引起的模板膨胀、模板支撑系统的稳定性。

**DIC价值**：长时间连续监测模板变形趋势，为浇筑速度控制和养护方案调整提供数据支撑。

### 7.3 桥梁墩柱浇筑过程监测

桥梁墩柱截面尺寸大（直径1-3m），高度可达数十米，采用滑模或爬模工艺连续浇筑。

**监测重点**：墩柱模板的圆度变化、滑模/爬模过程中的模板偏位、风荷载引起的模板摆动。

**DIC价值**：远距离非接触测量，无需在墩柱上安装任何设备，适应高空作业环境。XTDIC系统可在50m距离外实现毫米级精度的模板变形测量。

### 7.4 地下连续墙浇筑质量监控

地下连续墙浇筑在深槽内进行，施工环境恶劣（泥浆、地下水、空间狭小），传统监测手段难以实施。

**监测重点**：槽壁稳定性、钢筋笼变形、混凝土浇筑过程中的槽壁位移。

**DIC价值**：通过槽口上方的相机远距离监测槽壁变形，避免人员下槽作业的安全风险。

## 8. 数据驱动的施工质量闭环控制

DIC测量不仅用于浇筑过程的"事后检测"，更重要的是构建施工质量的闭环控制：

**浇筑速度优化**：通过DIC实时监测模板变形量，动态调整混凝土浇筑速度。当变形接近预警值时，降低浇筑速度；当变形稳定后，恢复正常浇筑速度。

**振捣参数优化**：基于DIC振动监测数据，识别模板系统的固有频率，调整振捣器工作频率，避免共振。同时优化振捣器插入深度和振捣时间，确保混凝土密实度。

**模板设计验证**：将DIC测量结果与模板设计计算结果对比，验证设计假设的合理性，为后续工程模板设计优化提供依据。

**施工预警系统**：建立基于DIC数据的实时预警系统，当模板变形速率或加速度超过阈值时，自动发出预警信号，提醒施工人员采取措施。

**数字孪生**：将DIC监测数据与BIM模型融合，构建浇筑过程的数字孪生模型，实现施工质量的可视化管理和追溯。

## 9. 实验设计与现场实施建议

对于初次开展混凝土浇筑DIC监测的工程人员，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑耐久性 | 选择耐磨耐水的散斑材料，预制散斑贴纸效率最高 |
| 相机防护 | IP65以上防护罩，防止浆液飞溅和水雾 |
| 帧率选择 | 整体变形监测30-60fps，振动分析500-2000fps |
| 照明补偿 | 采用主动LED照明，确保夜间施工图像质量 |
| 预警阈值 | 根据规范设定：位移预警2mm，报警3mm |
| 设备固定 | 三脚架配重或锚固，防止振动移位 |

**入门建议**：从单面墙体的整体变形监测开始，使用标准配置（SD相机，30-60fps），积累经验后再扩展到振动模态分析和多相机协同测量。

## 10. 结语

混凝土浇筑过程中的模板变形监测是确保施工质量和安全的关键环节。DIC技术以其非接触、全场、实时的测量能力，为混凝土施工监测提供了新的技术手段。

从工程实践的角度，DIC监测不应仅被视为一种检测工具，而应融入施工管理的完整数据链——从浇筑前的模板设计验证，到浇筑过程中的实时监测和预警，再到浇筑后的质量评估和数据分析。XTDIC系统凭借其从标准到高速、从单相机到多相机协同的完整产品覆盖，为不同规模和复杂度的混凝土浇筑监测提供了可配置的解决方案。

随着智能建造和数字化施工技术的推广，DIC全场监测数据与BIM模型、施工管理系统的深度融合，将推动混凝土施工从"经验驱动"向"数据驱动"转变，为建筑工程质量提升和安全保障提供更有力的技术支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: Engineering Background of Concrete Pouring Process Monitoring](#1-introduction-engineering-background-of-concrete-pouring-process-monitoring)
- [2. Wall Vibration and Deformation Mechanisms During Concrete Pouring](#2-wall-vibration-and-deformation-mechanisms-during-concrete-pouring)
- [3. Limitations of Traditional Monitoring Methods](#3-limitations-of-traditional-monitoring-methods)
- [4. Core Advantages of DIC for Concrete Pouring Monitoring](#4-core-advantages-of-dic-for-concrete-pouring-monitoring)
- [5. Key Technical Aspects of DIC Measurement for Concrete Pouring](#5-key-technical-aspects-of-dic-measurement-for-concrete-pouring)
  - [5.1 Large-Area Speckle Preparation](#51-large-area-speckle-preparation)
  - [5.2 Multi-Camera Coordination and Field Coverage](#52-multi-camera-coordination-and-field-coverment)
  - [5.3 Dynamic Acquisition and Vibration Frequency Matching](#53-dynamic-acquisition-and-vibration-frequency-matching)
  - [5.4 Environmental Adaptability Design](#54-environmental-adaptability-design)
- [6. XTDIC System Implementation for Concrete Pouring Monitoring](#6-xtdic-system-implementation-for-concrete-pouring-monitoring)
  - [6.1 Equipment Configuration](#61-equipment-configuration)
  - [6.2 Site Deployment and Workflow](#62-site-deployment-and-workflow)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
  - [7.1 High-Rise Residential Shear Wall Pouring Monitoring](#71-high-rise-residential-shear-wall-pouring-monitoring)
  - [7.2 Mass Concrete Foundation Slab Pouring](#72-mass-concrete-foundation-slab-pouring)
  - [7.3 Bridge Pier Column Pouring Process Monitoring](#73-bridge-pier-column-pouring-process-monitoring)
  - [7.4 Underground Diaphragm Wall Pouring Quality Control](#74-underground-diaphragm-wall-pouring-quality-control)
- [8. Data-Driven Construction Quality Closed-Loop Control](#8-data-driven-construction-quality-closed-loop-control)
- [9. Experimental Design and Field Implementation Recommendations](#9-experimental-design-and-field-implementation-recommendations)
- [10. Conclusion](#10-conclusion)

---

## 1. Introduction: Engineering Background of Concrete Pouring Process Monitoring

Concrete pouring is one of the most critical processes in building construction. During pouring, the concrete slurry exerts enormous lateral pressure on the formwork system, while vibration operations cause continuous vibration of the formwork and already-poured structures. When the pouring speed is too fast, formwork stiffness is insufficient, or vibration parameters are improper, the wall structure may experience excessive deformation or even formwork blowouts.

According to the "Code for Construction of Concrete Structures" (GB 50666-2011) issued by the Ministry of Housing and Urban-Rural Development, the lateral displacement of formwork during concrete pouring should be controlled within the design-allowed range, generally not exceeding 1/1000 of the formwork height and no more than 3mm. However, traditional monitoring methods—such as displacement sensors, inclinometers, etc.—can only obtain data from limited measurement points, making it difficult to fully reflect the deformation distribution and vibration modes of the wall surface.

With the rapid development of prefabricated buildings and super high-rise buildings, concrete pouring speeds continue to increase (core tube pouring speed can reach 3-5 meters per hour), and the dynamic loads on formwork systems become more complex. In this context, a non-contact measurement technology capable of obtaining full-field deformation data in real time and adapting to harsh construction environments is needed.

Digital Image Correlation (DIC) technology provides a feasible technical path for this requirement.

## 2. Wall Vibration and Deformation Mechanisms During Concrete Pouring

Wall deformation during concrete pouring results from the superposition of multiple loads:

**Concrete Lateral Pressure**: Freshly poured concrete is in a fluid state, exerting hydrostatic-like lateral pressure on the formwork. The maximum lateral pressure occurs at approximately 1/3 height below the pouring surface, closely related to pouring speed, concrete slump, admixture type, and vibration method. According to GB 50666-2011, the lateral pressure of ordinary concrete can be calculated as:

F = min(0.22γ_c t_0 β_1 β_2 V^{1/2}, γ_c H)

where γ_c is concrete unit weight (~24kN/m³), t_0 is initial setting time, β_1 is admixture influence coefficient, β_2 is slump influence coefficient, V is pouring speed, and H is effective head height. For C40 ordinary concrete (slump 180mm, pouring speed 2m/h), the maximum lateral pressure is approximately 50-60kPa.

**Vibrator Excitation Force**: Internal vibrators produce excitation frequencies typically in the 80-200Hz range with amplitudes of 0.5-2mm. When the vibrator frequency approaches the natural frequency of the formwork system, resonance may occur, causing dramatic increases in formwork amplitude. Steel formwork natural frequencies are typically 30-80Hz (depending on formwork thickness and stiffener spacing), overlapping with the vibrator frequency range.

**Pumping Impact Load**: During concrete pumping, the concrete flow velocity at the pump pipe outlet can reach 1-2m/s, generating periodic impact loads on the formwork. Pumping frequency is related to pump truck displacement and pipe diameter, generally in the 0.5-3Hz range.

**Temperature Effects**: During mass concrete pouring, cement hydration heat causes internal concrete temperature to rise (up to 60-80°C), and thermal expansion causes additional formwork deformation. For a 3m thick foundation slab, thermal expansion-induced formwork lateral expansion can reach 1-2mm.

The superposition of these loads places the wall formwork system in a complex dynamic deformation state during pouring, which traditional single-point measurement methods cannot fully capture.

## 3. Limitations of Traditional Monitoring Methods

**Displacement Sensors (LVDT/Cable-type)**: Require mounting brackets and sensors on the formwork, causing significant construction interference. Limited sensor quantity (typically 2-3 measurement points per wall) cannot obtain full-field deformation distribution. Under vibration conditions, sensor connections tend to loosen, reducing data reliability.

**Inclinometers**: Can only measure the overall tilt angle of the formwork, unable to reflect local deformation and vibration modes. For walls exceeding 4m in height, inclinometer measurement accuracy is insufficient to meet code requirements.

**Total Station/Level**: Require manual point-by-point measurement, unable to achieve real-time dynamic monitoring. On the pouring work surface, surveyors face high safety risks, and measurement frequency cannot meet vibration monitoring requirements.

**Strain Gauges**: Require bonding to the formwork surface, easily damaged in construction environments. Can only measure single-point strain, unable to obtain full-field distribution. Under conditions of concrete slurry splashing and vibration, strain gauge survival rates are low.

These limitations make traditional methods inadequate for modern concrete construction requirements of comprehensive, real-time, and safe deformation monitoring.

## 4. Core Advantages of DIC for Concrete Pouring Monitoring

DIC tracks displacement and deformation of speckle patterns on the formwork surface, enabling non-contact full-field measurement. Core advantages over traditional methods:

**Full-Field Data Acquisition**: A single measurement yields 3D displacement and strain data at millions of points across the formwork surface, completely presenting deformation distribution, vibration modes, and strain concentration areas.

**Non-Contact Measurement**: Does not interfere with pouring construction, requires no sensors or brackets on the formwork, avoiding the impact of traditional methods on construction processes.

**Real-Time Dynamic Monitoring**: Paired with high-speed cameras, can collect formwork vibration data in real time at frame rates of hundreds to thousands of frames per second, meeting sampling requirements for vibrator excitation frequencies (80-200Hz).

**Full-Field Vibration Modal Analysis**: Through FFT frequency domain analysis, can extract natural frequencies, mode shapes, and damping ratios of the formwork system from full-field displacement data, providing basis for vibration parameter optimization.

**Harsh Environment Adaptation**: DIC systems can be deployed at a distance (2-10m from formwork), avoiding direct impact of concrete slurry splashing and vibration on equipment.

## 5. Key Technical Aspects of DIC Measurement for Concrete Pouring

### 5.1 Large-Area Speckle Preparation

Speckle preparation at concrete pouring sites faces special challenges: large formwork areas (single wall formwork can reach 50-200㎡), repeated formwork use, and humid construction environments.

**Speckle Scheme Selection**:
- **Direct Formwork Surface Preparation**: Spray high-temperature-resistant matte paint as background on formwork panels, then create random speckle patterns using templates or spray guns. Speckle size is determined by camera distance and resolution, generally requiring each speckle to occupy 3-5 pixels in the image.
- **Pre-Fabricated Speckle Stickers**: Factory-prepared random speckle pattern adhesive stickers, directly applied to formwork surface on site. This method provides stable speckle quality and high construction efficiency, suitable for standardized formwork systems.
- **Natural Texture Utilization**: For steel formwork, surface rolling texture and weld marks can serve as natural speckles, but with lower contrast, requiring enhanced lighting.

**Speckle Durability**: Considering multiple formwork turnover cycles, speckle materials should have sufficient wear and water resistance. Ceramic-based speckle coatings can withstand 50+ cycles of formwork removal-cleaning-reinstallation.

### 5.2 Multi-Camera Coordination and Field Coverage

A single camera's field of view is limited. For large-area wall formwork, multiple cameras must work together:

**Camera Layout Principles**:
- Cameras arranged at equal intervals along the wall length, adjacent camera field overlap ≥20%
- Camera optical axis perpendicular to formwork surface, deviation angle ≤15°
- Camera-to-formwork distance determined by lens focal length and measurement area, generally 2-8m

**Multi-Camera Synchronization**: Multiple cameras collect synchronously via hardware trigger signals, synchronization accuracy ≤1μs. The XTDIC system supports 1-8 camera group synchronized operation, achieving automatic multi-field data stitching through unified coordinate system calibration.

**Field Stitching**: Corresponding point data from adjacent camera field overlap regions are weighted-averaged to eliminate stitching seams, forming complete full-field deformation data.

### 5.3 Dynamic Acquisition and Vibration Frequency Matching

The vibration frequency range during concrete pouring is wide. Appropriate acquisition frame rates should be selected based on monitoring objectives:

| Vibration Source | Frequency Range | Recommended Frame Rate | Monitoring Objective |
|-----------------|----------------|----------------------|---------------------|
| Pumping Impact | 0.5–3Hz | 30–60fps | Overall formwork displacement |
| Vibrator Excitation | 80–200Hz | 500–2000fps | Local formwork vibration |
| Formwork Resonance | 30–80Hz | 200–500fps | Modal parameter identification |
| Wind Load | 0.1–5Hz | 10–30fps | Overall stability |

**Sampling Theorem Application**: According to the Nyquist sampling theorem, the acquisition frame rate should be at least 2.5 times the highest frequency of interest. For 200Hz vibrator excitation, the recommended frame rate is no less than 500fps.

**Long-Term Continuous Monitoring**: Concrete pouring can last hours to tens of hours. DIC systems need long-term continuous acquisition and storage capability. The XTDIC system supports SSD direct-write storage, with a single camera collecting hours of high-frame-rate data continuously.

### 5.4 Environmental Adaptability Design

Construction site environments are harsh, requiring corresponding protective measures for DIC systems:

**Water and Dust Protection**: Cameras and lenses use IP65+ rated protective housings to prevent concrete slurry splashing and water mist erosion.

**Lighting Compensation**: Construction site lighting conditions vary greatly (from direct sunlight during daytime to construction lighting at night). Active LED lighting systems ensure stable speckle image brightness. High color rendering index (CRI≥90) LED panel lights are recommended, color temperature 5000-5600K.

**Equipment Fixation**: Cameras mounted on tripods or dedicated fixed stands, with counterweights or anchoring at the base to prevent equipment displacement due to vibration.

**Cable Protection**: Data and power cables use wear-resistant sheaths, routed along scaffolding or the ground, avoiding being crushed by construction machinery.

## 6. XTDIC System Implementation for Concrete Pouring Monitoring

### 6.1 Equipment Configuration

For concrete pouring monitoring requirements, the XTDIC system offers the following configurations:

**Standard Configuration (Full-Field Deformation + Low-Frequency Vibration)**:
- XTDIC-CONST-SD (2.3–5MP, 163–1500fps, 50με)
- Suitable for overall formwork deformation monitoring and pumping impact load analysis
- Binocular stereo vision, 3D full-field measurement
- Measurement area: 2m×1.5m to 10m×8m (adjustable)

**High-Frequency Vibration Configuration (Vibrator Excitation + Modal Analysis)**:
- XTDIC-CONST-HS (4MP, >100,000fps, 50με)
- Suitable for formwork vibration measurement within the vibrator excitation frequency range
- High-frame-rate acquisition, supporting FFT frequency domain analysis

**Key Parameters**:
- Strain range: 0.005%–2000%
- Displacement precision: ≤0.01 pixel (corresponding to approximately 0.01–0.1mm physical, depending on measurement distance and lens)
- Measurement area: 50mm–10m
- Synchronization: 1–8 camera group synchronized acquisition

### 6.2 Site Deployment and Workflow

**Step 1: Speckle Preparation and System Calibration**
- Prepare speckles on formwork surface (per Section 5.1)
- Camera positioning followed by 3D calibration using standard calibration plate
- Calibration accuracy verification: reprojection error ≤0.05 pixel

**Step 2: Pre-Pouring Baseline Acquisition**
- Before concrete pouring begins, collect initial state images of the formwork
- Record initial deformation of formwork under self-weight and construction loads
- Establish reference coordinate system for deformation monitoring

**Step 3: Real-Time Pouring Process Monitoring**
- After concrete pouring begins, DIC system continuously collects formwork deformation data
- Real-time display of full-field formwork displacement contour maps and key point displacement time-history curves
- When displacement exceeds warning threshold (e.g., 2mm), system automatically alarms

**Step 4: Vibration Parameter Optimization**
- During vibrator operation, collect formwork vibration data
- Identify formwork natural frequencies and mode shapes through FFT analysis
- Adjust vibrator frequency and insertion position to avoid resonance

**Step 5: Data Analysis and Reporting**
- Generate formwork deformation report for the pouring process
- Include maximum deformation, deformation distribution maps, vibration spectrum analysis
- Provide reference data for subsequent similar projects

## 7. Typical Application Scenarios

### 7.1 High-Rise Residential Shear Wall Pouring Monitoring

High-rise residential shear walls are typically 200-300mm thick, with floor heights of 3-4m, and fast pouring speeds (2-4m per hour), generating high formwork lateral pressure.

**Monitoring Focus**: Deformation in the maximum lateral pressure zone at the lower-middle portion of the formwork, vibration-induced formwork vibration, and relative displacement at adjacent formwork joints.

**DIC Value**: Replaces traditional displacement sensors, enabling real-time full-field formwork deformation monitoring. One 32-story residential project using DIC monitoring improved shear wall pouring qualification rate from 92% to 98%, reducing formwork blowout incidents by 80%.

### 7.2 Mass Concrete Foundation Slab Pouring

Mass concrete foundation slabs can be 2-5m thick, with single pour volumes reaching thousands of cubic meters. Pouring duration is long (12-48 hours), with formwork systems enduring sustained concrete lateral pressure and hydration heat expansion forces.

**Monitoring Focus**: Time-varying characteristics of formwork lateral displacement, formwork expansion caused by hydration heat, and stability of the formwork support system.

**DIC Value**: Long-term continuous monitoring of formwork deformation trends, providing data support for pouring speed control and curing plan adjustment.

### 7.3 Bridge Pier Column Pouring Process Monitoring

Bridge pier columns have large cross-sectional dimensions (1-3m diameter) and can reach heights of tens of meters, using slip-form or climb-form processes for continuous pouring.

**Monitoring Focus**: Pier column formwork roundness variation, formwork deviation during slip/climb-form operations, and formwork swing caused by wind loads.

**DIC Value**: Long-distance non-contact measurement, requiring no equipment installation on the pier column, suitable for high-altitude work environments. The XTDIC system can achieve millimeter-level precision formwork deformation measurement at distances exceeding 50m.

### 7.4 Underground Diaphragm Wall Pouring Quality Control

Underground diaphragm wall pouring occurs in deep trenches with harsh construction environments (slurry, groundwater, confined spaces), making traditional monitoring methods difficult to implement.

**Monitoring Focus**: Trench wall stability, reinforcement cage deformation, and trench wall displacement during concrete pouring.

**DIC Value**: Long-distance monitoring of trench wall deformation from cameras positioned above the trench, avoiding safety risks of personnel entering the trench.

## 8. Data-Driven Construction Quality Closed-Loop Control

DIC measurement serves not only as "post-inspection" of the pouring process, but more importantly as a closed-loop control for construction quality:

**Pouring Speed Optimization**: Through DIC real-time monitoring of formwork deformation, dynamically adjust concrete pouring speed. When deformation approaches warning values, reduce pouring speed; when deformation stabilizes, resume normal pouring speed.

**Vibration Parameter Optimization**: Based on DIC vibration monitoring data, identify the natural frequency of the formwork system, adjust vibrator operating frequency to avoid resonance. Simultaneously optimize vibrator insertion depth and vibration time to ensure concrete compaction.

**Formwork Design Validation**: Compare DIC measurement results with formwork design calculations to validate the reasonableness of design assumptions, providing basis for subsequent engineering formwork design optimization.

**Construction Early Warning System**: Establish a real-time early warning system based on DIC data. When formwork deformation rate or acceleration exceeds thresholds, automatically issue warning signals to alert construction personnel to take measures.

**Digital Twin**: Fuse DIC monitoring data with BIM models to build a digital twin model of the pouring process, enabling visual management and traceability of construction quality.

## 9. Experimental Design and Field Implementation Recommendations

For engineers beginning concrete pouring DIC monitoring, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle Durability | Select wear-resistant and water-resistant speckle materials; pre-fabricated speckle stickers offer highest efficiency |
| Camera Protection | IP65+ rated protective housings to prevent slurry splashing and water mist |
| Frame Rate Selection | Overall deformation monitoring 30-60fps, vibration analysis 500-2000fps |
| Lighting Compensation | Use active LED lighting to ensure nighttime construction image quality |
| Warning Thresholds | Set per code: displacement warning 2mm, alarm 3mm |
| Equipment Fixation | Tripod counterweight or anchoring to prevent vibration-induced displacement |

**Getting Started Recommendation**: Begin with overall deformation monitoring of a single wall using standard configuration (SD camera, 30-60fps), then expand to vibration modal analysis and multi-camera coordinated measurement after gaining experience.

## 10. Conclusion

Formwork deformation monitoring during concrete pouring is a critical link in ensuring construction quality and safety. DIC technology, with its non-contact, full-field, and real-time measurement capabilities, provides a new technical means for concrete construction monitoring.

From an engineering practice perspective, DIC monitoring should not be viewed merely as an inspection tool, but should be integrated into the complete data chain of construction management—from pre-pouring formwork design validation, to real-time monitoring and early warning during pouring, to post-pouring quality assessment and data analysis. The XTDIC system, with its complete product coverage from standard to high-speed and from single camera to multi-camera coordination, provides configurable solutions for concrete pouring monitoring of different scales and complexities.

As intelligent construction and digital construction technologies advance, the deep integration of DIC full-field monitoring data with BIM models and construction management systems will drive the transformation of concrete construction from "experience-driven" to "data-driven," providing stronger technical support for construction quality improvement and safety assurance.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D civil engineering application documentation*
