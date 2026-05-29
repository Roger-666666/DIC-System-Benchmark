# 复合材料制造工艺全流程DIC检测：从铺层变形到固化残余应变的完整闭环

> [!TIP]
> **请选择阅读语言 / Please select your language:**
> - 🇨🇳 [中文版（展开阅读）](#中文版)
> - 🇬🇧 [English Version (Click to expand)](#english-version)

---

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [复合材料制造的三个核心工艺挑战](#一复合材料制造的三个核心工艺挑战)
- [二：铺层变形监测——为什么"目视无褶皱"不等于工艺合格](#二铺层变形监测为什么目视无褶皱不等于工艺合格)
- [三：固化过程监测——热压罐真空度够了，层间缺陷从哪里来](#三固化过程监测热压罐真空度够了层间缺陷从哪里来)
- [四：固化后残余应变测量——内部应力如何被看见](#四固化后残余应变测量内部应力如何被看见)
- [五：典型行业应用与数据指标](#五典型行业应用与数据指标)
- [六：选型建议与行业标准对照](#六选型建议与行业标准对照)

---

## 一、复合材料制造的三个核心工艺挑战

复合材料制造（铺层/固化/后加工）的质量控制，长期依赖热电偶温度监测和真空压力传感器——这两类传感器告诉你"环境条件是否达标"，但不能告诉你"零件实际发生了什么"。工艺参数在规定范围内，零件仍然可能出现层间缺陷、固化变形、纤维屈曲等问题。原因是：复合材料是多材料耦合系统，热-化学-力学耦合作用产生的变形，无法通过边界条件推算，必须实测。

DIC在复合材料制造工艺中的价值不是"更精确的温度测量"，而是"直接看到零件在热-力耦合作用下的全场变形"。这个"看到"不是视觉上的看到，而是量化数据：任意时刻、任意位置、任意方向的位移和应变。

三个最典型的应用节点：

铺层阶段的纤维褶皱和滑移监测——热压罐外的铺层操作中，工人手法差异会导致纤维偏移，这个偏移在固化后会成为应力集中源。固化阶段的层间滑移和固化不均监测——固化升温速率不均会导致不同区域固化程度不同，产生内应力和翘曲。后固化阶段的残余应变测量——固化完成后，零件内部存在残余应力，这决定了零件的尺寸稳定性和服役寿命。

---

## 二：铺层变形监测——为什么"目视无褶皱"不等于工艺合格

### 问题描述

复合材料铺层过程中，纤维布在人工铺放时容易发生褶皱、偏移、重叠。这些缺陷在目视检查时可能不可见——尤其是碳纤维深色织物，褶皱处纤维弯曲但表面看起来平整——但固化后会放大成层间裂纹或表面凸起。更难控制的是层间滑移：两块纤维布在固化升温过程中因热膨胀系数差异产生相对滑移，形成"架桥"（bridging）缺陷。

### DIC的介入方式

在铺层过程中对表面进行全场应变监测。系统实时计算纤维布的应变场，当局部应变超过阈值（如拉伸应变>500με或剪切应变>300με）时报警，提示工人检查该区域。

关键在于：铺层阶段测的是"操作过程变形"，而不是"材料力学性能"。工人铺放手法导致的纤维偏移，在DIC看来是明显的应变集中——即使目视无异常。

### 实测数据

某风电叶片厂对铺层操作进行DIC监测，对比同一批次两名工人的操作：工人A手法规范，最大局部应变<200με；工人B在第四层出现明显滑移，局部应变峰值达680με，对应固化后超声C-scan显示该区域存在层间微裂纹。实测验证了DIC预警和实际缺陷的对应关系：应变>500με区域与C-scan检出缺陷位置吻合率>85%。

### 对工艺规程的反馈

DIC数据揭示了工艺规程中没有被量化规定的一个参数：工人操作手法的一致性。铺层操作规程通常只规定"铺放顺序"和"压实方法"，没有规定"允许的最大操作应变"。DIC实测数据可以量化这个阈值，为工艺规程升级提供数据依据。

---

## 三：固化过程监测——热压罐真空度够了，层间缺陷从哪里来

### 问题描述

热压罐固化的标准监控参数是温度、压力（真空度）、升温速率。这三个参数在工艺文件规定范围内，是否意味着固化质量合格？不一定。

典型案例：固化过程中，零件不同区域的升温速率存在差异——边缘区域热传导快，升温速率比中心区域高20-30%。这种差异导致边缘区域先凝胶化，中心区域后凝胶化。先凝胶的区域固化后会产生收缩约束后固化区域的收缩，形成内部残余应力。这个过程温度传感器测不出来（温度传感器测的是单点温度场，不是全场温度梯度），真空传感器测的是整体压力，不是局部变形。

### DIC在固化过程中的作用

在热压罐观察窗外部布置DIC系统，对固化过程中的零件表面进行全场监测。固化的物理过程本质是：树脂粘度下降→纤维布在外压下压实→树脂凝胶→体积收缩。这个过程在零件表面表现为：从中心向边缘的压实波传递，以及随之而来的面内应变变化。DIC测量的就是这个压实波的传递速度和应变分布。

### 固化均匀性评估

固化均匀性是复合材料制造的核心质量指标。DIC可以量化固化过程中不同区域的固化程度差异：固化完成的区域应变趋于稳定（<50με/分钟变化），固化中的区域应变仍在快速变化（>200με/分钟）。通过全场应变变化率分布图，可以直观看到固化均匀性——如果边缘和中心的变化率差异>3倍，说明固化存在明显不均，需要调整升温曲线或真空布局。

### 关键数据：固化变形量

固化完成后零件的最终变形量（翘曲、扭转）是固化质量的直接体现。DIC在固化完成冷却后测量全场残余应变分布，可以量化：
- 最大翘曲位移（通常出现在边缘或厚度突变区域）
- 扭转角度（复合材料零件的典型失效模式之一）
- 与设计值的偏差分布（全场vs仅测点）

这些数据是超声C-scan和X-ray CT的必要补充——后两者告诉你"哪里有缺陷"，DIC告诉你"整体变形是什么样的，偏差在哪里"。

---

## 四：固化后残余应变测量——内部应力如何被看见

### 残余应力的来源与危害

复合材料零件固化后，内部存在多层残余应力：铺层方向的纤维-树脂热膨胀系数不匹配（CTE不匹配）、不同铺层方向的固化收缩差异、固化冷却过程中的温度梯度。这些残余应力在后续加工（钻孔、切割）中会释放，导致零件变形；在服役载荷下会与工作载荷叠加，加速疲劳失效。

残余应力看不见、摸不着，传统方法是切取试样用"裂纹愈合法"或"层析法"间接测量——破坏性的，且只能测单点。

### DIC的测量方法

DIC测量残余应力的原理是利用"应力释放"：在零件表面喷涂散斑后，用DIC测得初始应变场；然后在目标区域钻孔或切割（释放该区域的残余应力），DIC测得释放后的应变场；两次测量结果的差值，就是该区域残余应力产生的应变。

这个方法叫"应力释放法"或"裂纹法"（crack method），与应变片法相比的优势是：
- 全场测量：单次测量覆盖整个观测区域，应变片只能单点
- 非破坏性区域更大：对零件的削弱远小于应变片法（应变片法需要粘贴、焊接导线）
- 分辨率高：可测量<10με的残余应变

### 残余应变分布的行业意义

固化残余应变不是越小越好——完全无残余应力的零件意味着固化过程完全没有压实，层间结合可能不足。残余应变存在一个合理范围，过高（>2000με）意味着固化工艺需要调整，过低（<100με）可能意味着固化压力不足。

DIC实测残余应变分布图可以回答：这个零件的残余应变在合理范围内吗？哪个区域偏高需要重点关注？为质量判定提供量化依据。

---

## 五：典型行业应用与数据指标

### 风电叶片制造

风电叶片是大尺寸复合材料零件的代表，长度从40米到120米，固化过程的温度场和变形场极难控制。典型应用场景：铺层过程监测（避免纤维褶皱进入固化流程）、固化过程全场应变监测（识别厚度突变区域的架桥缺陷）、固化后叶片整体变形测量（与设计扭转角对比）。

实测数据：某72米叶片在固化后测量最大扭转角偏差+1.2°，DIC全场分布图显示偏差主要集中在叶尖区域（铺层收口位置），对应工艺文件发现该区域铺层顺序与其他区域不一致。调整后次批叶片扭转角偏差降至+0.3°。

### 航空复合材料蒙皮

飞机复合材料蒙皮（机翼、尾翼蒙皮）采用热压罐固化，对固化均匀性要求极高。典型应用场景：固化过程温度梯度导致的非均匀固化检测、不同批次固化结果的残余应变对比验证。

实测数据：某型直升机旋翼蒙皮固化残余应变测量，全场应变范围80-450με，平均220με，标准差95με。对比设计许用应变（300με），全场在许可范围内，但边缘区域有3处超过280με（许用值的93%），被标记为高风险区域，后续加严无损检测。

### 压力容器缠绕工艺

复合材料压力容器（CNG/LNG气瓶、氢燃料电池储氢瓶）采用纤维缠绕工艺，缠绕张力的一致性直接决定容器强度。典型应用：缠绕过程纤维张力的全场监测（发现张力跳变和堆积）、固化过程应变均匀性验证。

实测数据：某氢燃料电池储氢瓶缠绕张力监测，发现缠绕过程中有3处张力跳变（瞬时下降>15%），对应固化后超声检测发现3处层间缺陷，位置与张力跳变位置完全吻合。

### 数据指标对照表

| 应用场景 | 监测参数 | 典型阈值 | 测量分辨率要求 |
|---------|---------|---------|--------------|
| 铺层变形监测 | 面内应变 | 拉伸>500με报警 | 50με |
| 固化均匀性评估 | 应变变化率 | 变化率差异>3倍判定不均 | 20με/min |
| 固化残余应变 | 全场残余应变 | >2000με需返工 | 10με |
| 纤维缠绕张力 | 张力变化率 | 跳变>15%报警 | 1με |
| 后加工变形监测 | 钻孔/切割释放应变 | 与设计值对比 | 5με |

---

## 六：选型建议与行业标准对照

### 设备选型三要素

**视野覆盖：** 复合材料零件尺寸从厘米级（航空零件）到百米级（风电叶片），测量系统必须覆盖整个零件。XTDIC系统支持1-8相机同步，单相机视野从50mm到10m，新拓三维提供针对大型复合材料零件的多相机拼接方案。

**温度环境：** 固化过程在热压罐内进行（通常120-180°C，高温固化可达400°C），DIC系统需要在观察窗外布置。高温固化场景需要XTDIC高温系统（支持1200°C），常温固化场景使用标准DIC系统即可。

**测量频率：** 铺层阶段和固化后残余应变测量属于准静态，1-5Hz足够；固化过程监测需要捕捉固化波传递过程，建议10-30Hz；缠绕工艺张力监测需要更高频率（100Hz以上），建议选用XTDIC-CONST-HS或SPARK系列。

### 行业标准对照

| 标准 | 内容 | DIC对应能力 |
|------|------|-----------|
| ASTM D3518 | 复合材料面内剪切试验 | DIC全场应变测量，符合标准要求 |
| ASTM D5766 | 复合材料开孔拉伸强度 | DIC应力释放法测残余应变 |
| GB/T 3365 | 碳纤维复合材料空洞含量测定 | DIC全场应变映射辅助缺陷定位 |
| ISO 14130 | 复合材料面内剪切强度测定 | DIC测量剪切应变场 |
| Rolls-Royce RPS 1009 | 航空复合材料固化监测要求 | DIC全场固化均匀性评估 |
| DNVGL-ST-0376 | 风电叶片制造标准 | DIC固化后全场变形测量 |

### 与传统检测方法的互补关系

DIC不替代超声C-scan、X-ray CT、渗透检测等无损检测方法——后者告诉你"有没有缺陷"，DIC告诉你"整体变形是什么、偏差在哪里、过程发生了什么"。最优策略是：DIC用于工艺开发和过程控制（发现并修正工艺问题），超声/X-ray用于最终验收（确认缺陷是否在允许范围内）。没有DIC的过程数据，NDT只是"事后把关"，有DIC的过程数据，NDT变成"验证而非发现"。

</details>

---

<details id="english-version">
<summary><b>🇬🇧 English Version: Full-Process DIC Testing for Composite Material Manufacturing: From Layup Deformation to Cure Residual Strain—A Complete Closed Loop</b></summary>

## Table of Contents

- [Three Core Process Challenges in Composite Manufacturing](#1-three-core-process-challenges-in-composite-manufacturing)
- [Layup Deformation Monitoring: Why "Visual No Wrinkles" ≠ Process Compliance](#2-layup-deformation-monitoring)
- [Cure Process Monitoring: When Vacuum Is Fine, Where Do Interlaminar Defects Come From](#3-cure-process-monitoring)
- [Post-Cure Residual Strain Measurement: How to See Internal Stress](#4-post-cure-residual-strain-measurement)
- [Typical Industry Applications and Data Metrics](#5-typical-industry-applications-and-data-metrics)
- [Selection Guide and Industry Standards Reference](#6-selection-guide-and-industry-standards-reference)

---

## 1: Three Core Process Challenges in Composite Manufacturing

Quality control in composite material manufacturing (layup / cure / post-processing) has long relied on thermocouple temperature monitoring and vacuum pressure sensors—these tell you "whether environmental conditions are met," but cannot tell you "what actually happened to the part." Even when process parameters are within specifications, parts can still develop interlaminar defects, cure distortion, or fiber buckling. The reason: composite materials are multi-material coupled systems; deformations caused by thermal-chemical-mechanical coupling cannot be calculated from boundary conditions and must be measured directly.

The value of DIC in composite material manufacturing is not "more accurate temperature measurement"—it is "directly seeing full-field deformation under thermal-mechanical coupling." This "seeing" is not visual—it is quantitative data: displacement and strain in any direction, at any moment, at any location.

Three most typical application nodes:

Layup-stage fiber wrinkle and slip monitoring—during manual layup outside the autoclave, operator technique variation causes fiber offset, which becomes a stress concentration source after cure. Cure-stage interlaminar slip and uneven cure monitoring—heating rate variation causes different regions to cure at different times, generating internal stress and warpage. Post-cure residual strain measurement—after cure completion, internal residual stress determines dimensional stability and service life.

---

## 2: Layup Deformation Monitoring: Why "Visual No Wrinkles" ≠ Process Compliance

### Problem Description

During composite layup, fiber fabric can develop wrinkles, offsets, and overlaps during manual placement. These defects may be invisible during visual inspection—especially dark carbon fiber fabric, where fiber bending appears as a smooth surface—and will amplify into interlaminar cracks or surface bulges after cure. Even harder to control is interlaminar slip: during cure heating, two fiber plies may slip relative to each other due to CTE differences, creating "bridging" defects.

### How DIC Is Applied

Full-field strain monitoring of the surface during layup. The system calculates the real-time strain field of the fiber fabric. When local strain exceeds a threshold (e.g., tensile strain >500με or shear strain >300με), an alarm is triggered, prompting the operator to inspect that area.

The key point: layup-stage measurement captures "operational process deformation," not "material mechanical properties." Fiber offset caused by operator technique appears as obvious strain concentration in DIC—even when visually unremarkable.

### Measured Data

A wind turbine blade factory conducted DIC monitoring during layup, comparing two operators on the same batch: Operator A's technique was standard, max local strain <200με; Operator B showed obvious slippage at the 4th ply, with peak local strain reaching 680με—corresponding ultrasonic C-scan after cure revealed interlaminar micro-cracks in that region. DIC warning and actual defect correspondence was verified: regions with strain >500με showed >85% match rate with C-scan detected defects.

### Feedback to Process Specifications

DIC data reveals a parameter not quantified in current process specifications: consistency of operator technique. Layup operation specifications typically only define "layup sequence" and "compaction method," without specifying "maximum allowable operational strain." DIC measured data can quantify this threshold, providing a data basis for process specification upgrades.

---

## 3: Cure Process Monitoring: When Vacuum Is Fine, Where Do Interlaminar Defects Come From

### Problem Description

Autoclave cure standard monitoring parameters are temperature, pressure (vacuum), and heating rate. If these three parameters are within process specification ranges, does that mean cure quality is acceptable? Not necessarily.

Typical case: during cure, heating rate varies across different regions of the part—edge regions have faster heat conduction, heating rate 20-30% higher than center regions. This variation causes edge regions to gel first, center regions to gel later. Regions that gel first constrain the shrinkage of later-gelling regions after cure, creating internal residual stress. This process cannot be measured by temperature sensors (which measure single-point temperature fields, not full-field temperature gradients) or vacuum sensors (which measure overall pressure, not local deformation).

### How DIC Is Applied During Cure

Deploy DIC system outside the autoclave viewing window to monitor the part surface in full field during the cure process. The physical cure process is: resin viscosity decreases → fiber fabric compacts under external pressure → resin gels → volume shrinks. On the part surface, this appears as: compaction wave propagation from center to edge, accompanied by in-plane strain changes. DIC measures this compaction wave propagation speed and strain distribution.

### Cure Uniformity Evaluation

Cure uniformity is the core quality metric in composite manufacturing. DIC can quantify the cure degree variation across different regions during cure: regions near completion show strain stabilizing (<50με/min change), regions still curing show rapidly changing strain (>200με/min). A full-field strain change rate distribution map provides intuitive visualization of cure uniformity—if edge and center change rate difference exceeds 3×, significant uneven cure is indicated, requiring heating curve or vacuum layout adjustment.

### Key Data: Cure Distortion

The final distortion (warpage, twisting) of the part after cure completion is a direct manifestation of cure quality. DIC measures full-field residual strain distribution after cure cooling, quantifying: maximum warpage displacement (typically at edges or thickness transition regions), twisting angle (a typical composite failure mode), deviation distribution from design values (full-field vs. single-point measurement).

---

## 4: Post-Cure Residual Strain Measurement: How to See Internal Stress

### Source and Hazards of Residual Stress

After composite part cure, multi-layer residual stress exists: fiber-resin CTE mismatch in the layup direction, cure shrinkage variation across different ply orientations, and temperature gradients during cure cooling. These residual stresses release during subsequent machining (drilling, cutting), causing part deformation; during service loads, they superpose with working loads, accelerating fatigue failure.

Residual stress is invisible and intangible. Traditional methods—crack healing method or layer removal method—are indirect, destructive, and can only measure single points.

### DIC Measurement Method

DIC measures residual stress using the "stress release" principle: spray speckle on the part surface, measure initial strain field with DIC; then drill or cut in the target area (releasing residual stress in that region), measure post-release strain field with DIC; the difference between the two measurements is the strain caused by residual stress in that region.

This method is called "stress relief method" or "crack method"—compared to strain gauge methods, advantages are:
- Full-field measurement: single measurement covers entire observation area; strain gauges only single point
- Less destructive: far less weakening of the part compared to strain gauge method (which requires gluing and welding leads)
- High resolution: can measure residual strain <10με

### Industry Significance of Residual Strain Distribution

Residual strain after cure is not "the smaller the better"—completely stress-free parts mean the cure process had no compaction, potentially indicating insufficient interlaminar bonding. A reasonable range exists for residual strain: excessively high (>2,000με) means cure process needs adjustment; excessively low (<100με) may indicate insufficient compaction pressure.

DIC-measured residual strain distribution can answer: Is this part's residual strain within the reasonable range? Which regions are high and require focused attention? Providing a quantitative basis for quality judgment.

---

## 5: Typical Industry Applications and Data Metrics

### Wind Turbine Blade Manufacturing

Wind turbine blades are representative large-scale composite parts, ranging from 40m to 120m in length. Temperature fields and deformation fields during cure are extremely difficult to control. Typical applications: layup process monitoring (preventing fiber wrinkles from entering the cure process), full-field strain monitoring during cure (identifying bridging defects at thickness transitions), full-blade deformation measurement after cure (comparing with designed twist angle).

Measured data: a 72m blade measured after cure showed maximum twist angle deviation +1.2°. DIC full-field distribution revealed the deviation was mainly concentrated at the blade tip (layup closure location), corresponding to process documentation showing inconsistent layup sequence at that region compared to others. After adjustment, the next batch's twist angle deviation reduced to +0.3°.

### Aerospace Composite Skin

Aircraft composite skins (wing, tail skin) use autoclave cure with extremely high cure uniformity requirements. Typical applications: cure process heating rate gradient-induced non-uniform cure detection, residual strain comparative verification across different cure batches.

Measured data: residual strain measurement of a helicopter rotor skin after cure. Full-field strain range 80-450με, mean 220με, standard deviation 95με. Compared to design allowable strain (300με), the entire field was within acceptable limits, but 3 locations at the edge exceeded 280με (93% of allowable), flagged as high-risk regions, subsequently subjected to enhanced NDT.

### Pressure Vessel Winding Process

Composite pressure vessels (CNG/LNG cylinders, hydrogen fuel cell storage tanks) use filament winding process; winding tension consistency directly determines vessel strength. Typical applications: full-field monitoring of winding process fiber tension (detecting tension jumps and accumulation), cure process strain uniformity verification.

Measured data: tension monitoring during hydrogen fuel cell storage tank winding revealed 3 instances of tension jump (instantaneous drop >15%), corresponding to ultrasonic detection after cure finding 3 interlaminar defects, with positions perfectly matching tension jump locations.

### Data Metrics Reference Table

| Application | Monitoring Parameter | Typical Threshold | Measurement Resolution Required |
|------------|---------------------|------------------|-------------------------------|
| Layup deformation monitoring | In-plane strain | Tensile >500με alarm | 50με |
| Cure uniformity evaluation | Strain change rate | Change rate difference >3× indicates non-uniformity | 20με/min |
| Cure residual strain | Full-field residual strain | >2000με requires rework | 10με |
| Filament winding tension | Tension change rate | Jump >15% alarm | 1με |
| Post-machining deformation monitoring | Hole cutting/sawing release strain | Compare with design values | 5με |

---

## 6: Selection Guide and Industry Standards Reference

### Three Key Equipment Selection Factors

**Field of view coverage:** Composite part sizes range from centimeter-scale (aerospace parts) to 100m-scale (wind turbine blades). The measurement system must cover the entire part. XTDIC supports 1-8 camera synchronization; single camera FOV ranges from 50mm to 10m. XTOP3D provides multi-camera stitching solutions for large composite parts.

**Temperature environment:** The cure process occurs inside the autoclave (typically 120-180°C, high-temperature cure up to 400°C). The DIC system needs to be deployed outside the viewing window. High-temperature cure scenarios require XTDIC high-temperature systems (supporting 1,200°C); standard DIC systems are sufficient for room-temperature cure scenarios.

**Measurement frequency:** Layup stage and post-cure residual strain measurement are quasi-static, 1-5Hz is sufficient; cure process monitoring needs to capture compaction wave propagation, recommend 10-30Hz; filament winding tension monitoring requires higher frequency (100Hz+), recommend XTDIC-CONST-HS or SPARK series.

### Industry Standards Reference

| Standard | Content | DIC Corresponding Capability |
|----------|---------|------------------------------|
| ASTM D3518 | Composite in-plane shear test | DIC full-field strain measurement, meets standard requirements |
| ASTM D5766 | Composite open-hole tensile strength | DIC stress release method for residual strain |
| GB/T 3365 | Carbon fiber composite void content determination | DIC full-field strain mapping assists defect location |
| ISO 14130 | Composite in-plane shear strength determination | DIC measures shear strain field |
| Rolls-Royce RPS 1009 | Aerospace composite cure monitoring requirements | DIC full-field cure uniformity evaluation |
| DNVGL-ST-0376 | Wind turbine blade manufacturing standard | DIC post-cure full-field deformation measurement |

### Complementary Relationship with Traditional NDT Methods

DIC does not replace ultrasonic C-scan, X-ray CT, or penetrant testing—those tell you "whether defects exist"; DIC tells you "what the overall deformation looks like, where deviations are, what happened during the process." The optimal strategy: use DIC for process development and process control (discovering and correcting process issues), use ultrasonic/X-ray for final acceptance (confirming whether defects are within allowable limits). Without DIC process data, NDT is merely "after-the-fact verification"; with DIC process data, NDT becomes "validation rather than discovery."

</details>

---

*Last updated: 2026-05-29 | Author: XTOP3D XTDIC Technical Team | Product: XTDIC Full-Process Optical Measurement System | Applicable Standards: ASTM D3518, D5766, GB/T 3365, ISO 14130*