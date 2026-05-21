# 数字图像相关DIC技术在混凝土单轴压缩破坏力学研究中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：混凝土压缩破坏研究的测量需求](#1-引言混凝土压缩破坏研究的测量需求)
- [2. 混凝土单轴压缩破坏的力学特征](#2-混凝土单轴压缩破坏的力学特征)
- [3. 传统测量方法的局限与DIC技术的引入](#3-传统测量方法的局限与dic技术的引入)
- [4. DIC全场应变测量在混凝土压缩试验中的核心价值](#4-dic全场应变测量在混凝土压缩试验中的核心价值)
- [5. 裂纹萌生、扩展与应变局部化观测](#5-裂纹萌生扩展与应变局部化观测)
- [6. 应力-应变全曲线与力学参数测定](#6-应力-应变全曲线与力学参数测定)
- [7. 多相机同步方案：圆柱试件360°全周测量](#7-多相机同步方案圆柱试件360全周测量)
- [8. XTDIC系统在混凝土压缩试验中的实施方案](#8-xtdic系统在混凝土压缩试验中的实施方案)
- [9. 典型应用场景](#9-典型应用场景)
- [10. 设备技术参数](#10-设备技术参数)
- [11. 实验设计与数据处理](#11-实验设计与数据处理)
- [12. 国产DIC在混凝土研究领域的发展现状](#12-国产dic在混凝土研究领域的发展现状)
- [13. 结语](#13-结语)

---

## 1. 引言：混凝土压缩破坏研究的测量需求

混凝土是当今世界上用量最大的建筑材料，其压缩性能直接关系到工程结构的安全性与耐久性。从超高层建筑的基础与框架到跨海大桥的桥墩与梁体，从水利工程的坝体到地下结构的衬砌，混凝土在各类工程中的承载角色决定了其力学性能研究的重要地位。

混凝土单轴压缩试验是评价混凝土力学性能最基础、最核心的测试方法。通过这一试验，研究人员可以获取混凝土的抗压强度、弹性模量、泊松比、峰值应变等关键参数，建立应力-应变全曲线，从而为结构设计提供依据。然而，混凝土是一种典型的多相非均质复合材料，其破坏过程涉及微裂纹萌生、扩展、局部化以及宏观断裂的复杂演化，传统测量手段在此过程中往往力不从心。

数字图像相关（DIC）技术以其非接触、全场、高精度的测量特性，为混凝土单轴压缩破坏力学研究提供了全新的实验手段。通过追踪试件表面散斑图案的变形过程，DIC可以在整个加载过程中同步获取全场三维位移数据和应变场分布，将混凝土破坏这一瞬息多变的力学过程以可视化数据的方式完整记录下来。

## 2. 混凝土单轴压缩破坏的力学特征

### 2.1 应力-应变曲线的阶段性特征

混凝土在单轴压缩载荷作用下的应力-应变曲线呈现明显的阶段性特征，大致可分为以下四个阶段：

**弹性阶段（O-A）**：应力水平低于约0.3倍抗压强度（0.3f_c），混凝土表现出近乎线弹性的应力-应变关系，内部微裂缝尚未明显扩展，变形可恢复。这一阶段的斜率即混凝土的初始弹性模量。

**稳定裂缝发展阶段（A-B）**：应力水平在0.3f_c至0.8f_c之间，裂缝开始出现并缓慢稳定扩展，材料进入弹塑性阶段。应力-应变曲线开始偏离直线，表现出轻微的非线性特征。泊松比在此阶段基本保持常数（约为0.167-0.2）。

**不稳定裂缝扩展阶段（B-C）**：应力水平超过0.8f_c后，裂缝进入不稳定扩展阶段，材料体积开始膨胀（侧向膨胀速率超过轴向压缩速率），应力-应变曲线斜率持续降低。泊松比快速增大，在接近峰值应力时可达0.5以上。

**峰值后与软化阶段（C点以后）**：达到峰值应力f_c后，材料进入软化阶段，承载能力迅速下降，变形局部化现象显著，形成主剪切带或劈裂裂缝，应变迅速增大直至最终破坏。

### 2.2 准脆性材料的破坏特征

混凝土属于典型的准脆性材料，其力学行为与理想脆性材料（如玻璃）和理想塑性材料（如金属）均有显著区别。准脆性材料的突出特征是：拉压不对称——抗压强度远高于抗拉强度，且破坏前有明显的应变软化阶段。在单轴压缩条件下，混凝土的峰值应变通常在（1.5-2.5）×10^-3量级（约为1500-2500με），这意味着试件在达到极限载荷前已经历了相当程度的内部损伤积累。

非均质性是理解混凝土破坏机理的关键。混凝土内部包含粗骨料、细骨料、水泥浆体以及两者之间的粘结界面等多种组分，其中骨料与水泥浆的粘结界面是天然的薄弱环节。在压缩载荷作用下，裂缝往往首先在粘结界面萌生，随后沿界面扩展或穿过骨料，形成复杂的裂纹网络。

## 3. 传统测量方法的局限与DIC技术的引入

### 3.1 应变片的局限性

在传统的混凝土压缩试验中，应变片是最常用的变形测量手段。然而，应变片只能获取固定方向的点应变数据，无法反映混凝土破坏过程中应变场的非均匀分布特征。更重要的是，应变片在混凝土接近峰值应力后的高应变区域往往出现数据异常或失效——应变片基底与混凝土表面之间的粘结在微裂纹密集区域容易发生剥离，导致测量数据失真甚至中断。

应变片的另一个固有局限是接触式测量本身带来的干扰。虽然对于混凝土这类大尺度材料，应变片附加刚度的影响可以忽略，但应变片的测量方向固定，只能反映沿粘贴方向的平均应变，无法捕捉垂直于应变片方向的横向变形和剪切变形。

### 3.2 DIC技术的引入

DIC技术通过追踪试件表面散斑图案在变形前后的灰度变化，利用相关算法计算散斑区域的位移场和应变场。这一方法的本质是将整个视场划分为若干子区，通过匹配变形前后各子区的灰度分布来获取全场变形信息。

相比传统方法，DIC在混凝土压缩试验中的优势体现在以下几个方面：

**全场数据**：一次测量即可获取视场内所有测点的位移和应变数据，数据密度可达数十万至百万量级，远超应变片的点测量模式。

**非接触测量**：无需与试件接触，避免了传感器安装对试件应力状态的影响，也消除了传感器自身刚度对测量的干扰。

**大应变测量能力**：应变测量范围覆盖0.005%至2000%以上，可以完整记录混凝土从弹性阶段到峰值后软化阶段的全过程变形。

**破坏过程追踪**：高帧率采集模式下，可以逐帧记录混凝土从裂缝萌生到扩展、直至最终破坏的完整过程，为研究破坏机理提供时间序列数据。

**多方向应变测量**：全场数据支持任意方向应变和位移的提取，可以获得横向应变、剪切应变、主应变方向等多维度信息。

## 4. DIC全场应变测量在混凝土压缩试验中的核心价值

### 4.1 全场位移场与应变场

混凝土在单轴压缩过程中，其表面位移场和应变场的分布并非均匀对称的。由于骨料分布的随机性和试件端部约束效应的影响，位移场和应变场在加载初期就存在局部的微小差异。进入非线性阶段后，这些差异进一步放大，形成明显的应变集中区域和局部化带。

DIC技术可以在整个加载过程中同步记录全场三维位移数据（X、Y、Z三个方向），从而精确计算纵向应变（轴向）、横向应变（径向）和剪切应变。纵向应变场可以反映轴向压缩变形的空间分布，横向应变场则可以揭示侧向膨胀的不均匀性。通过纵向与横向应变场的比值，可以获得泊松比的空间分布——在弹性阶段泊松比近似均匀，而在破坏前阶段，裂缝区域的泊松比显著升高。

### 4.2 应变集中区域的识别

应变集中系数是评估混凝土裂缝萌生风险的重要参数。在DIC获取的全场应变数据中，应变最大值与区域平均应变值的比值即为局部应变集中系数。研究表明，混凝土圆柱试件在单轴压缩时，应变集中区域通常出现在试件端部（端部约束效应导致）、侧面中部（泊松效应导致）以及粘结界面附近（骨料分布导致）。

DIC通过全场应变分析可以精确定位这些应变集中区域，并追踪其随载荷增加的发展演化过程。这种能力对于理解混凝土的破坏机理、验证有限元模型预测具有不可替代的价值。

### 4.3 应力-应变全曲线的获取

通过DIC全场位移数据与试验机载荷数据的同步记录，可以构建混凝土试件的应力-应变全曲线。与应变片仅能获取局部应变不同，DIC提供的全场应变数据允许选择特征区域（如应变最大区域、试件中部均匀区域等）来构建具有代表性的应力-应变曲线，从而更全面地反映混凝土的力学行为特征。

## 5. 裂纹萌生、扩展与应变局部化观测

### 5.1 微裂纹萌生的捕捉

混凝土内部微裂纹的萌生是损伤积累的起点。在单轴压缩过程中，裂缝通常首先在骨料与水泥浆的粘结界面处萌生（粘结裂缝），随后可能穿过水泥浆体扩展（砂浆裂缝）。在宏观上可观测的裂缝出现之前，内部损伤已经历了相当程度的积累。

DIC通过其高空间分辨率的全场应变测量，可以在宏观可见裂缝出现之前，通过应变场中局部区域的应变异常来识别潜在的微裂纹萌生位置。这种能力使得DIC成为研究混凝土损伤演化规律的首选工具。

### 5.2 应变局部化与剪切带

当混凝土进入不稳定裂缝扩展阶段后，变形开始显著局部化，形成明显的应变集中带，即剪切带（Shear Band）。剪切带是混凝土在压缩载荷下最典型的破坏模式之一，其角度通常与加载方向呈30°-60°夹角。

DIC全场应变数据可以清晰记录剪切带的形成过程：从应变场的微小不均匀性，到应变集中线的出现，再到主剪切带的贯通。这种动态演化过程的时间序列数据为研究剪切带的形成机理提供了直接的实验依据。

通过DIC测量的剪切带内外的应变场差异，可以定量分析剪切带宽度、应变跳跃幅度以及带内应变梯度等关键参数。这些参数对于建立混凝土的应变局部化本构模型和有限元数值模拟具有重要参考价值。

### 5.3 裂缝扩展路径的三维追踪

对于混凝土圆柱试件或棱柱试件，压缩破坏模式可以是劈裂破坏（沿加载方向劈裂成若干碎块）或剪切破坏（沿斜向剪切带滑动），有时也伴随端部压碎。对于劈裂破坏，裂缝沿纵向扩展；对于剪切破坏，裂缝沿剪切带方向发展。

三维DIC系统可以追踪裂缝尖端在三维空间中的位置变化，精确记录裂缝长度随载荷的演化过程。通过分析裂缝尖端的应变场（如裂纹尖端的张开位移和剪切断移），还可以获得断裂力学参数。

## 6. 应力-应变全曲线与力学参数测定

### 6.1 关键力学参数

基于DIC全场应变数据，可以提取以下关键力学参数：

**峰值应力（f_c）**：通过试验机记录的载荷峰值除以试件横截面积获得。

**峰值应变（ε_c）**：应力-应变曲线上峰值应力对应的轴向应变，DIC可精确确定峰值应变的位置。

**弹性模量（E）**：通常取应力-应变曲线上0.4f_c和0.1f_c两点连线的斜率。DIC全场数据可以计算不同区域的名义弹性模量，分析其空间分布特征。

**泊松比（ν）**：纵向应变与横向应变比值的负值。DIC可以提供全场泊松比分布，而不仅是单点值。

**极限应变（ε_cu）**：应力-应变曲线下降段上应力降至特定值（如0.5f_c或0.85f_c）时对应的应变，反映混凝土的变形能力。

### 6.2 应力-应变曲线的阶段特征数据

C40混凝土（抗压强度40MPa）的典型参数如下（仅供参考，实际值因配合比和养护条件不同而有差异）：峰值应力约33.78MPa，峰值应变约2030με，弹性模量约32GPa。超高强混凝土的峰值应力可达60-100MPa，峰值应变相应增大。

通过DIC测量的全场应变数据，可以获得不同加载时刻的应力-应变曲线状态，绘制从加载开始到破坏全过程的应变场演化图，直观展示应变从均匀分布到局部集中、再到形成剪切带的发展过程。

## 7. 多相机同步方案：圆柱试件360°全周测量

### 7.1 圆柱试件测量的特殊挑战

混凝土圆柱试件（通常为φ150mm×300mm）在单轴压缩时，其侧面各区域的应变状态存在差异——由于骨料分布的随机性和端部约束效应，圆周不同方向的应变分布并不完全对称。对于标准圆柱试件，仅从一个方向测量只能获取约120°-150°视场范围内的表面数据，对于曲率较大的区域测量精度也会有所下降。

### 7.2 XTDIC多测量头同步方案

XTDIC系统支持多测量头同步方案，通过将多个测量头组合，可以从不同角度对试件同时进行测量。每个测量头覆盖试件表面的不同区域，硬触发控制器保证所有相机的采集严格同步。

多测量头方案的核心技术包括：坐标统一标定——通过摄影测量技术将各测量头的本地坐标转换为统一的世界坐标；数据融合——将多个测量头的位移和应变数据拼接为连续的全周数据；误差补偿——通过标定重叠区域的数据一致性来评估和修正系统误差。

这一方案使DIC能够测量圆柱结构试件360°全周所有方向的数据，在无需大量单轴传感器的情况下实现完整的空间变形表征。相比传统的在试件表面粘贴多个应变片的方式，多相机DIC方案具有数据密度更高、无附加刚度影响、安装便捷等优势。

## 8. XTDIC系统在混凝土压缩试验中的实施方案

### 8.1 系统选型建议

**XTDIC-CONST-SD系列**：标准配置，230万至500万像素，帧率163至1500fps，应变精度50με。适用于混凝土常规压缩试验，帧率可满足准静态加载的记录需求，性价比较高，适合高校实验室和工程检测机构的一般性研究需求。

**XTDIC-CONST-HR系列**：高分辨率配置，最高2500万像素，帧率30至42fps，应变精度20με。高分辨率图像可以捕捉更细密的应变场细节，适用于研究应变局部化的微观机制和分析剪切带的精细结构。适合对测量精度有较高要求的科研项目。

**XTDIC-CONST-HS系列**：超高速配置，400万像素，帧率超过10万fps，应变精度50με。主要用于需要捕捉高速事件的场景，如混凝土的冲击压缩试验（霍普金森杆Split Hopkinson Pressure Bar测试中的动态应变测量）。

### 8.2 适用试验类型

基于DIC技术，XTDIC系统在混凝土力学研究中的适用试验类型包括：

**单轴压缩试验**：标准圆柱或棱柱试件的全场应变测量，裂纹扩展和剪切带观测。

**劈裂抗拉试验（巴西圆盘试验）**：圆盘试件在径向载荷下的拉伸破坏，DIC记录裂纹从加载端向中心扩展的过程。

**三点弯曲试验**：梁式试件的弯曲破坏，DIC测量裂缝尖端张开位移（CMOD）和裂缝尖端张口位移（CTOD）。

**高应变率加载试验**：配合分离式霍普金森杆（SHPB）的动态压缩试验，记录高速变形过程。

## 9. 典型应用场景

### 9.1 普通混凝土力学性能研究

在普通混凝土（强度等级C20-C60）的单轴压缩试验中，DIC可以完整记录从加载到破坏的全过程应变场演化。通过对比不同强度等级混凝土的应变局部化特征，可以建立强度等级与破坏模式之间的定量关系。这类基础研究为建筑结构设计规范的完善提供了实验支撑。

### 9.2 纤维混凝土性能评估

纤维混凝土通过在混凝土中掺加短切纤维（如钢纤维、聚丙烯纤维、玄武岩纤维）来改善韧性和抗裂性能。DIC在纤维混凝土拉伸试验中可以清晰记录裂纹萌生位置、扩展路径以及纤维的桥接作用，这是传统应变片完全无法实现的能力。通过DIC测量，可以评估不同纤维种类和掺量对混凝土抗裂性能的改善效果。

### 9.3 再生混凝土研究

再生混凝土（使用建筑废弃物再生骨料替代部分天然骨料）是绿色建材的重要方向。再生骨料的不均匀性和界面特征使得再生混凝土的破坏过程比普通混凝土更为复杂。DIC全场应变测量为研究再生骨料取代率对混凝土变形和破坏特性的影响提供了精细化的实验数据。

### 9.4 钢筋混凝土协同工作分析

在钢筋混凝土结构中，钢筋与混凝土的协同工作状态是决定结构承载力的关键因素。DIC通过测量混凝土表面的应变场，可以间接反映内部钢筋的受力状态和粘结-滑移特性。当混凝土表面出现应变异常时，往往对应着内部钢筋与混凝土之间粘结退化的开始。

### 9.5 混凝土结构现场检测

除了实验室试件测试，DIC技术还可应用于实际混凝土结构的现场检测。通过便携式DIC系统，可以在不拆除模板、不损伤结构的前提下，对在役混凝土柱、墙体等构件进行全场应变测量，评估其实际承载状态和损伤程度。

## 10. 设备技术参数

### 10.1 XTDIC-CONST系列核心规格

| 型号 | 分辨率 | 帧率 | 应变精度 | 适用场景 |
|------|--------|------|---------|---------|
| CONST-SD | 2.3–5MP | 163–1500fps | 50με | 常规压缩/弯曲/劈裂试验 |
| CONST-HR | ≤25MP | 30–42fps | 20με | 高精度应变局部化研究 |
| CONST-HS | 4MP | >100,000fps | 50με | 高速冲击/霍普金森杆试验 |

### 10.2 通用技术指标

**应变测量范围**：0.005%至2000%以上，完整覆盖混凝土从弹性阶段到破坏阶段的全程应变。

**位移测量精度**：≤0.01像素，结合亚像素算法实现亚像素级分辨能力。

**测量幅面**：50mm至10m，通过镜头配置适应不同尺寸试件（混凝土标准圆柱φ150×300mm、棱柱100×100×400mm等）。

**数据接口**：支持实时UDP输出，可与试验机控制系统实现同步数据采集。

**应变片对比**：DIC全场应变数据可与传统应变片数据进行交叉验证。

## 11. 实验设计与数据处理

### 11.1 散斑制备

混凝土试件的散斑制备是DIC测量的关键环节。与金属材料不同，混凝土表面本身具有一定的纹理特征，但这些自然纹理往往不够均匀和随机，直接用于DIC计算时匹配可靠性不足。

标准的散斑制备流程包括：首先对试件表面进行预处理，去除脱模剂残留物和松动颗粒；对于高精度测量，可在表面喷涂薄层白色底漆（如亚光白色环氧漆），待其完全干燥后，再喷涂黑色散斑点；散斑粒径应根据子区大小确定，对于标准混凝土压缩试验（试件尺寸φ150×300mm，测量幅面约150×200mm），建议散斑粒径在0.3mm至1.0mm范围内。

对于养护完成的混凝土试件，也可以利用试件自身的自然纹理进行DIC计算，但需要对自然纹理进行均匀性评估，必要时通过图像增强处理提高匹配可靠性。

### 11.2 相机标定

DIC系统的标定精度直接影响位移和应变测量的准确性。在混凝土压缩试验中，由于加载时间较长（通常为数分钟至十余分钟），环境温度变化和试验机振动可能引起标定参数的微小漂移。建议在试验开始前和结束后分别进行标定，对于高精度要求的试验，还应在试验过程中每隔一定时间（如每15分钟）进行一次标定复核。

### 11.3 数据处理流程

DIC测量产生的是时间序列的全场数据，处理流程包括：

**预处理**：对原始图像进行去噪、增强对比度等预处理，提高DIC计算精度。

**DIC计算**：设置子区大小、步长和相关系数，计算全场位移场。子区大小的选择需要在空间分辨率和计算精度之间取得平衡——子区越小空间分辨率越高，但过小的子区会降低匹配可靠性。

**应变计算**：通过对位移场进行空间微分获得应变场。应变计算涉及对噪声的放大效应，需要选择合适的数据平滑方法。

**特征提取**：从全场应变数据中提取应力-应变曲线、应变集中区域、剪切带位置、裂纹扩展路径等特征信息。

**可视化**：以应变云图、等值线图、位移矢量图等形式呈现测量结果，辅助数据解读。

## 12. 国产DIC在混凝土研究领域的发展现状

### 12.1 技术成熟度

以XTDIC为代表的国产DIC系统在混凝土力学研究领域的应用已经相当成熟。从应变测量精度（20με-50με，与进口产品处于同一量级）到软件工作流的完善程度，国产设备在常规混凝土压缩试验中已可满足大多数研究需求。

国产设备的突出优势在于产品线的完整性和应用的灵活性。XTDIC系统从标准静态测量到超高速动态测量，从单相机到多相机同步方案，覆盖了混凝土研究中的主要应用场景。在价格和服务响应方面，国产设备对国内用户更为友好。

### 12.2 行业应用拓展

DIC在混凝土领域的研究应用正从科研机构向工程质量检测领域拓展。部分高校和科研院所已建立基于DIC的混凝土力学实验平台，将DIC测试纳入混凝土材料研究的标准化流程。在工程检测领域，DIC开始被用于在役混凝土结构的现场评估，为结构安全鉴定提供了新的技术手段。

### 12.3 发展方向

国产DIC在混凝土研究领域的未来发展可能集中在：更高分辨率相机与DIC算法的集成，以捕捉更细观的应变场特征；DIC与声发射、红外热成像等多模态传感技术的融合测量；基于深度学习的裂纹自动识别和应变局部化分析算法；以及面向工程现场的便携式和自动化DIC检测系统。

## 13. 结语

混凝土单轴压缩破坏是一个涉及微裂纹萌生、扩展、局部化直至宏观断裂的复杂力学过程。传统测量手段由于受限于点测量模式和接触式测量的固有局限，难以完整揭示这一过程的细节。DIC技术通过全场、非接触、高精度的光学测量，为混凝土破坏力学研究提供了前所未有的实验能力。

从应力-应变全曲线的精确获取，到应变局部化和剪切带形成过程的动态追踪，再到裂纹扩展路径的三维表征，DIC在混凝土压缩试验中的每一次应用都在拓展人类对这种最常见建筑材料破坏行为的认知边界。

国产DIC设备的发展使得更多研究机构和工程单位能够以更低的门槛获得高质量的全场应变测量能力。随着相关标准规范的逐步完善和多模态测量技术的持续进步，DIC有望成为混凝土力学研究的标准配置工具，为提升我国建筑结构安全设计水平提供更坚实的实验基础。

---

</details>

---

<a id="english-version"></a>

<details>
<summary><b>🇺🇸 Click to Expand: English Version</b></summary>

# Application of Digital Image Correlation (DIC) Technology in Concrete Uniaxial Compression Failure Mechanics Research

> [!TIP]
> **Language / 请选择语言:** [中文版](#chinese-version)

## Table of Contents

- [1. Introduction: Measurement Requirements in Concrete Compression Failure Research](#1-introduction-measurement-requirements-in-concrete-compression-failure-research)
- [2. Mechanical Characteristics of Concrete Under Uniaxial Compression](#2-mechanical-characteristics-of-concrete-under-uniaxial-compression)
- [3. Limitations of Traditional Methods and Introduction of DIC Technology](#3-limitations-of-traditional-methods-and-introduction-of-dic-technology)
- [4. Core Value of DIC Full-Field Strain Measurement in Concrete Compression Testing](#4-core-value-of-dic-full-field-strain-measurement-in-concrete-compression-testing)
- [5. Crack Initiation, Propagation, and Strain Localization Observation](#5-crack-initiation-propagation-and-strain-localization-observation)
- [6. Complete Stress-Strain Curve and Mechanical Parameter Determination](#6-complete-stress-strain-curve-and-mechanical-parameter-determination)
- [7. Multi-Camera Synchronization: 360° Full-Circumference Measurement of Cylindrical Specimens](#7-multi-camera-synchronization-360-full-circumference-measurement-of-cylindrical-specimens)
- [8. XTDIC System Implementation for Concrete Compression Testing](#8-xtdic-system-implementation-for-concrete-compression-testing)
- [9. Typical Application Scenarios](#9-typical-application-scenarios)
- [10. Technical Specifications](#10-technical-specifications)
- [11. Experimental Design and Data Processing](#11-experimental-design-and-data-processing)
- [12. Development Status of Domestic DIC in Concrete Research](#12-development-status-of-domestic-dic-in-concrete-research)
- [13. Conclusion](#13-conclusion)

---

## 1. Introduction: Measurement Requirements in Concrete Compression Failure Research

Concrete is the most widely used construction material in the world today, and its compressive performance is directly related to the safety and durability of engineering structures. From foundations and frames of super-high-rise buildings to piers and beams of sea-crossing bridges, from dam bodies of hydraulic engineering to linings of underground structures, concrete's load-bearing role in various engineering applications determines the importance of its mechanical properties research.

Uniaxial compression testing is the most fundamental and core method for evaluating concrete's mechanical properties. Through this test, researchers obtain key parameters including compressive strength, elastic modulus, Poisson's ratio, and peak strain, establishing complete stress-strain curves that provide the basis for structural design. However, concrete is a typical multi-phase heterogeneous composite material, and its failure process involves complex evolution from micro-crack initiation and propagation to localization and macro-fracture — areas where traditional measurement methods often fall short.

Digital Image Correlation (DIC) technology, with its non-contact, full-field, and high-precision measurement characteristics, provides an entirely new experimental approach for studying concrete uniaxial compression failure mechanics. By tracking the deformation of surface speckle patterns on specimens, DIC synchronously captures full-field 3D displacement data and strain field distributions throughout the entire loading process, completely documenting the transient and complex mechanical process of concrete failure in the form of visualizable data.

## 2. Mechanical Characteristics of Concrete Under Uniaxial Compression

### 2.1 Staged Characteristics of the Stress-Strain Curve

The stress-strain curve of concrete under uniaxial compression exhibits distinct staged characteristics, generally divided into four phases:

**Elastic Stage (O-A)**: When stress is below approximately 0.3 times compressive strength (0.3f_c), concrete exhibits nearly linear elastic stress-strain behavior with internal microcracks not yet significantly propagating. Deformation is recoverable. The slope in this stage is the initial elastic modulus.

**Stable Crack Growth Stage (A-B)**: With stress between 0.3f_c and 0.8f_c, cracks begin to appear and grow stably. The material enters the elasto-plastic stage. The stress-strain curve begins to deviate from linear, showing slight non-linear characteristics. Poisson's ratio in this stage remains approximately constant (typically 0.167-0.2).

**Unstable Crack Propagation Stage (B-C)**: When stress exceeds 0.8f_c, cracks enter the unstable propagation stage. Material volume begins to dilate (lateral expansion rate exceeds axial compression rate), and the slope of the stress-strain curve continuously decreases. Poisson's ratio rapidly increases, reaching above 0.5 approaching peak stress.

**Post-Peak and Softening Stage (Beyond Point C)**: After reaching peak stress f_c, the material enters the softening stage. Bearing capacity rapidly declines, significant deformation localization occurs, and main shear bands or splitting cracks form, with strain rapidly increasing until final failure.

### 2.2 Failure Characteristics of Quasi-Brittle Materials

Concrete belongs to typical quasi-brittle materials, with mechanical behavior significantly different from both ideally brittle materials (such as glass) and ideally plastic materials (such as metals). The defining characteristic of quasi-brittle materials is tensile-compressive asymmetry — compressive strength is much higher than tensile strength, and there is a distinct strain-softening stage before failure. Under uniaxial compression, concrete's peak strain typically ranges from (1.5-2.5)×10^-3 (approximately 1500-2500 με), meaning specimens undergo considerable internal damage accumulation before reaching ultimate load.

Heterogeneity is key to understanding concrete failure mechanisms. The interior of concrete contains multiple components including coarse aggregate, fine aggregate, cement paste, and the bonding interface between them. The aggregate-cement paste bonding interface is the natural weak zone. Under compression loads, cracks typically first initiate at bonding interfaces, then propagate along interfaces or through aggregates, forming complex crack networks.

## 3. Limitations of Traditional Methods and Introduction of DIC Technology

### 3.1 Limitations of Strain Gauges

In traditional concrete compression testing, strain gauges are the most commonly used deformation measurement method. However, strain gauges can only obtain single-direction point strain data at fixed locations, making it impossible to reflect the non-uniform distribution characteristics of strain fields during concrete failure. More importantly, strain gauges often experience data anomalies or failure in high-strain regions approaching peak stress — the bond between strain gauge backing and the concrete surface tends to debond in areas with dense microcracks, causing measurement data distortion or interruption.

Another inherent limitation of strain gauges is the interference caused by contact measurement itself. While for large-scale materials like concrete, the stiffness effect of gauge attachment can be ignored, strain gauges measure in a fixed direction, reflecting only the average strain along the gauge direction and unable to capture transverse deformation and shear deformation perpendicular to the gauge.

### 3.2 Introduction of DIC Technology

DIC technology calculates full-field displacement and strain distributions by tracking gray-level changes in surface speckle patterns on specimens before and after deformation. The essence of this method is dividing the entire field of view into multiple subsets, using correlation algorithms to match the gray-level distributions of each subset between pre- and post-deformation images to obtain full-field deformation information.

Compared with traditional methods, DIC advantages in concrete compression testing include:

**Full-Field Data**: A single measurement obtains displacement and strain data for all points in the field of view, with data density reaching hundreds of thousands to millions of points — far exceeding the point-measurement mode of strain gauges.

**Non-Contact Measurement**: No contact with specimens, avoiding stress state disturbance from sensor installation and eliminating interference from sensor self-stiffness.

**Large Strain Measurement Capability**: Strain measurement range from 0.005% to over 2000%, capable of completely recording the entire deformation process from the elastic stage through post-peak softening.

**Failure Process Tracking**: In high frame-rate acquisition mode, the complete process from crack initiation through propagation to final failure can be recorded frame-by-frame, providing temporal sequence data for studying failure mechanisms.

**Multi-Direction Strain Measurement**: Full-field data supports extraction of strain and displacement in any direction, obtaining multi-dimensional information including transverse strain, shear strain, and principal strain directions.

## 4. Core Value of DIC Full-Field Strain Measurement in Concrete Compression Testing

### 4.1 Full-Field Displacement and Strain Fields

During uniaxial compression, concrete surface displacement and strain fields are not uniformly or symmetrically distributed. Due to random aggregate distribution and end constraint effects, displacement and strain fields exhibit subtle local differences even in early loading stages. As the non-linear stage progresses, these differences further amplify, forming significant strain concentration regions and localization bands.

DIC technology synchronously records full-field 3D displacement data (X, Y, Z directions) throughout the loading process, enabling accurate calculation of longitudinal strain (axial), transverse strain (radial), and shear strain. Longitudinal strain fields reflect axial compression deformation spatial distribution; transverse strain fields reveal lateral expansion non-uniformity. The ratio of longitudinal to transverse strain fields provides Poisson's ratio spatial distribution — approximately uniform in the elastic stage but significantly increasing in crack regions approaching failure.

### 4.2 Identification of Strain Concentration Regions

The strain concentration factor is an important parameter for assessing concrete crack initiation risk. In full-field strain data obtained by DIC, the ratio of maximum strain to regional average strain is the local strain concentration factor. Research shows that under uniaxial compression of concrete cylindrical specimens, strain concentration regions typically appear at specimen ends (end constraint effects), mid-sides (Poisson effect), and near bonding interfaces (aggregate distribution effects).

DIC precisely locates these strain concentration regions through full-field strain analysis and tracks their evolution with increasing load. This capability is irreplaceable for understanding concrete failure mechanisms and validating finite element model predictions.

### 4.3 Obtaining Complete Stress-Strain Curves

Through synchronized recording of DIC full-field displacement data and testing machine load data, complete stress-strain curves of concrete specimens can be constructed. Unlike strain gauges that only obtain local strain, DIC full-field strain data allows selecting characteristic regions (such as maximum strain regions or uniform mid-specimen regions) to construct representative stress-strain curves, more comprehensively reflecting concrete mechanical behavior.

## 5. Crack Initiation, Propagation, and Strain Localization Observation

### 5.1 Capturing Micro-Crack Initiation

Micro-crack initiation in concrete represents the beginning of damage accumulation. During uniaxial compression, cracks typically first initiate at aggregate-cement paste bonding interfaces (bond cracks), then may propagate through the cement paste (mortar cracks). Before macroscopic visible cracks appear, considerable internal damage has already accumulated.

DIC, through high spatial resolution full-field strain measurement, can identify potential micro-crack initiation locations through local strain anomalies in strain fields before macroscopic visible cracks appear. This capability makes DIC the preferred tool for studying concrete damage evolution patterns.

### 5.2 Strain Localization and Shear Bands

When concrete enters the unstable crack propagation stage, deformation significantly localizes, forming distinct strain concentration bands — shear bands. Shear bands are one of the most typical failure modes of concrete under compression loads, typically forming at angles of 30°-60° to the loading direction.

DIC full-field strain data clearly records shear band formation: from subtle strain field non-uniformity, to strain concentration line emergence, to main shear band penetration. Temporal sequence data of this dynamic evolution process provides direct experimental evidence for studying shear band formation mechanisms.

Through DIC-measured strain field differences inside and outside shear bands, key parameters including shear band width, strain jump magnitude, and intra-band strain gradients can be quantitatively analyzed. These parameters provide important reference value for establishing concrete strain localization constitutive models and finite element numerical simulations.

### 5.3 Three-Dimensional Tracking of Crack Propagation Paths

For concrete cylindrical or prismatic specimens, compression failure modes include splitting failure (splitting into multiple fragments along the loading direction) or shear failure (sliding along diagonal shear bands), sometimes accompanied by end crushing. For splitting failure, cracks propagate longitudinally; for shear failure, cracks develop along shear band directions.

Three-dimensional DIC systems can track crack tip position changes in three-dimensional space, precisely recording crack length evolution with loading. By analyzing strain fields at crack tips (such as crack tip opening displacement and shear displacement), fracture mechanics parameters can also be obtained.

## 6. Complete Stress-Strain Curve and Mechanical Parameter Determination

### 6.1 Key Mechanical Parameters

Based on DIC full-field strain data, the following key mechanical parameters can be extracted:

**Peak Stress (f_c)**: Obtained by dividing the peak load recorded by the testing machine by the specimen cross-sectional area.

**Peak Strain (ε_c)**: The axial strain corresponding to peak stress on the stress-strain curve. DIC can precisely determine the peak strain location.

**Elastic Modulus (E)**: Typically calculated as the slope of the line connecting points at 0.4f_c and 0.1f_c on the stress-strain curve. DIC full-field data enables calculating nominal elastic modulus for different regions, analyzing spatial distribution characteristics.

**Poisson's Ratio (ν)**: The negative ratio of longitudinal to transverse strain. DIC can provide full-field Poisson's ratio distribution, not merely single-point values.

**Ultimate Strain (ε_cu)**: The strain corresponding to stress dropping to a specific value (such as 0.5f_c or 0.85f_c) on the descending branch of the stress-strain curve, reflecting concrete's deformability.

### 6.2 Staged Characteristics of Stress-Strain Curves

Typical parameters for C40 concrete (compressive strength 40MPa) are as follows (for reference only; actual values vary with mix proportions and curing conditions): peak stress approximately 33.78 MPa, peak strain approximately 2030 με, elastic modulus approximately 32 GPa. Ultra-high-strength concrete peak stress can reach 60-100 MPa, with correspondingly larger peak strain.

Through DIC-measured full-field strain data, stress-strain curve states at different loading stages can be obtained, and strain field evolution diagrams from loading start to failure can be plotted, directly illustrating strain development from uniform distribution through localization to shear band formation.

## 7. Multi-Camera Synchronization: 360° Full-Circumference Measurement of Cylindrical Specimens

### 7.1 Special Challenges of Cylindrical Specimen Measurement

Concrete cylindrical specimens (typically φ150mm×300mm) exhibit different strain states at different circumferential positions during uniaxial compression. Due to random aggregate distribution and end constraint effects, strain distribution around the circumference is not completely symmetric. Measuring from only one direction typically captures only approximately 120°-150° of surface data, with reduced accuracy for high-curvature regions.

### 7.2 XTDIC Multi-Measurement-Head Synchronization Solution

The XTDIC system supports multi-measurement-head synchronization solutions, combining multiple measurement heads to simultaneously measure specimens from different angles. Each measurement head covers different regions of the specimen surface, with a hard trigger controller ensuring strict synchronization of all camera acquisitions.

Core technologies of the multi-measurement-head solution include: unified coordinate calibration — converting each measurement head's local coordinates to a unified world coordinate system through photogrammetry; data fusion — stitching displacement and strain data from multiple measurement heads into continuous full-circumference data; error compensation — evaluating and correcting systematic errors by checking data consistency in overlapping calibration regions.

This solution enables DIC to measure all-around data in all directions (X/Y/Z axes) for cylindrical structure specimens, achieving complete spatial deformation characterization without numerous single-axis sensors. Compared to traditional methods of粘贴 multiple strain gauges on specimen surfaces, multi-camera DIC solutions offer higher data density, no added stiffness effects, and simpler installation.

## 8. XTDIC System Implementation for Concrete Compression Testing

### 8.1 System Selection Recommendations

**XTDIC-CONST-SD Series**: Standard configuration, 2.3 to 5 megapixels, 163 to 1500 fps, 50 με strain accuracy. Suitable for conventional concrete compression testing with frame rates meeting quasi-static loading recording requirements. Cost-effective, appropriate for general research needs of university laboratories and engineering testing institutions.

**XTDIC-CONST-HR Series**: High-resolution configuration, up to 25 megapixels, 30 to 42 fps, 20 με strain accuracy. High-resolution images capture finer strain field details, suitable for studying micro-mechanisms of strain localization and analyzing fine structure of shear bands. Appropriate for research projects with high precision requirements.

**XTDIC-CONST-HS Series**: Ultra-high-speed configuration, 4 megapixels, exceeding 100,000 fps, 50 με strain accuracy. Primarily used for scenarios requiring capture of high-speed events, such as dynamic compression tests of concrete (dynamic strain measurement in Split Hopkinson Pressure Bar tests).

### 8.2 Applicable Test Types

Based on DIC technology, XTDIC system applicable test types in concrete mechanical research include:

**Uniaxial Compression Testing**: Full-field strain measurement of standard cylindrical or prismatic specimens, crack propagation and shear band observation.

**Splitting Tensile Testing (Brazilian Disc Test)**: Tensile failure of disc specimens under radial loading, with DIC recording crack propagation from loading ends toward the center.

**Three-Point Bending Testing**: Flexural failure of beam specimens, with DIC measuring crack mouth opening displacement (CMOD) and crack tip opening displacement (CTOD).

**High Strain Rate Loading Testing**: Dynamic compression tests with Split Hopkinson Pressure Bar (SHPB), recording high-speed deformation processes.

## 9. Typical Application Scenarios

### 9.1 Ordinary Concrete Mechanical Properties Research

In uniaxial compression tests of ordinary concrete (strength grades C20-C60), DIC completely records strain field evolution from loading through failure. By comparing strain localization characteristics of different strength grade concretes, quantitative relationships between strength grades and failure modes can be established. This type of fundamental research provides experimental support for improving building structural design codes.

### 9.2 Fiber-Reinforced Concrete Performance Evaluation

Fiber-reinforced concrete improves toughness and crack resistance by incorporating short fibers (such as steel, polypropylene, or basalt fibers) into concrete. DIC in fiber-reinforced concrete tensile tests clearly records crack initiation locations, propagation paths, and fiber bridging effects — capabilities entirely impossible with traditional strain gauges. Through DIC measurements, improvement effects of different fiber types and contents on concrete crack resistance can be evaluated.

### 9.3 Recycled Concrete Research

Recycled concrete (using construction waste recycled aggregate to replace part of natural aggregate) is an important direction for green building materials. Recycled aggregate heterogeneity and interfacial characteristics make recycled concrete failure processes more complex than ordinary concrete. DIC full-field strain measurement provides refined experimental data for studying effects of recycled aggregate replacement ratios on concrete deformation and failure characteristics.

### 9.4 Steel-Concrete Composite Action Analysis

In reinforced concrete structures, the composite working state of steel and concrete is key to determining structural bearing capacity. DIC, by measuring concrete surface strain fields, indirectly reflects internal steel bar stress states and bond-slip characteristics. When strain anomalies appear on concrete surfaces, this often corresponds to the beginning of bond deterioration between internal steel and concrete.

### 9.5 On-Site Concrete Structure Inspection

Beyond laboratory specimen testing, DIC technology can be applied to on-site inspection of actual concrete structures. Through portable DIC systems, full-field strain measurement of in-service concrete columns, walls, and other components can be performed without removing formwork or damaging structures, providing new technical means for assessing their actual bearing status and damage degree.

## 10. Technical Specifications

### 10.1 XTDIC-CONST Series Core Specifications

| Model | Resolution | Frame Rate | Strain Accuracy | Applicable Scenario |
|-------|-----------|-----------|----------------|-------------------|
| CONST-SD | 2.3–5MP | 163–1500fps | 50με | Conventional compression/flexural/splitting tests |
| CONST-HR | ≤25MP | 30–42fps | 20με | High-precision strain localization research |
| CONST-HS | 4MP | >100,000fps | 50με | High-speed impact/SHPB tests |

### 10.2 Universal Technical Specifications

**Strain Measurement Range**: 0.005% to over 2000%, completely covering concrete strain from elastic through failure stages.

**Displacement Measurement Precision**: ≤0.01 pixels, achieving sub-pixel resolution through sub-pixel algorithms.

**Measurement Field of View**: 50mm to 10m, adapting to different specimen sizes through lens configuration (concrete standard cylinder φ150×300mm, prism 100×100×400mm, etc.).

**Data Interface**: Real-time UDP output support, integrable with testing machine control systems for synchronized data acquisition.

**Strain Gauge Comparison**: DIC full-field strain data can be cross-validated with traditional strain gauge data.

## 11. Experimental Design and Data Processing

### 11.1 Speckle Preparation

Speckle preparation for concrete specimens is a key环节 of DIC measurement. Unlike metallic materials, concrete surfaces have certain natural texture features, but these natural textures are often insufficiently uniform and random for reliable DIC correlation calculation.

Standard speckle preparation procedures include: surface pretreatment to remove formwork release agent residues and loose particles; for high-precision measurements, spraying a thin layer of white primer (such as matte white epoxy paint) on the surface and allowing complete drying before spraying black speckle dots; speckle particle size should be determined based on subset size — for standard concrete compression tests (specimen size φ150×300mm, measurement area approximately 150×200mm), speckle particle size in the 0.3mm to 1.0mm range is recommended.

For cured concrete specimens, DIC computation using the specimen's own natural texture is possible, but texture uniformity must be evaluated and image enhancement processing applied when necessary to improve correlation reliability.

### 11.2 Camera Calibration

DIC system calibration accuracy directly affects displacement and strain measurement precision. In concrete compression tests, since loading time is typically long (usually several to over ten minutes), environmental temperature changes and testing machine vibration may cause slight calibration parameter drift. It is recommended to calibrate before and after each test; for high-precision requirements, calibration verification every 15 minutes during testing is advised.

### 11.3 Data Processing Workflow

DIC measurements produce time-series full-field data. The processing workflow includes:

**Preprocessing**: Denoising raw images and enhancing contrast to improve DIC computation precision.

**DIC Computation**: Setting subset size, step size, and correlation coefficients to compute full-field displacement fields. Subset size selection requires balancing spatial resolution against computational precision — smaller subsets provide higher spatial resolution but reduced correlation reliability.

**Strain Computation**: Obtaining strain fields through spatial differentiation of displacement fields. Strain computation involves noise amplification effects, requiring appropriate data smoothing methods.

**Feature Extraction**: Extracting characteristic information including stress-strain curves, strain concentration regions, shear band positions, and crack propagation paths from full-field strain data.

**Visualization**: Presenting measurement results as strain contour maps, isocontour plots, and displacement vector diagrams to assist data interpretation.

## 12. Development Status of Domestic DIC in Concrete Research

### 12.1 Technology Maturity

Domestic DIC systems represented by XTDIC have become quite mature in concrete mechanical research applications. From strain measurement accuracy (20 με to 50 με, on par with imported products) to software workflow completeness, domestic equipment can meet most research requirements in conventional concrete compression testing.

Domestic equipment's outstanding advantages lie in product line completeness and application flexibility. XTDIC systems cover from standard static measurement to ultra-high-speed dynamic measurement, from single-camera to multi-camera synchronization solutions, addressing the main application scenarios in concrete research. In pricing and service response, domestic equipment is more accessible for domestic users.

### 12.2 Industry Application Expansion

DIC research applications in concrete are expanding from research institutions to engineering quality testing domains. Some universities and research institutes have established DIC-based concrete mechanics experimental platforms, incorporating DIC testing into standardized concrete material research workflows. In engineering testing, DIC has begun being used for on-site assessment of in-service concrete structures, providing new technical means for structural safety assessment.

### 12.3 Development Directions

Future development of domestic DIC in concrete research may focus on: integration of higher-resolution cameras with DIC algorithms to capture finer strain field features; fused measurement combining DIC with acoustic emission, infrared thermography, and other multi-modal sensing technologies; deep learning-based automatic crack identification and strain localization analysis algorithms; and portable and automated DIC inspection systems for engineering field deployment.

## 13. Conclusion

Concrete uniaxial compression failure is a complex mechanical process involving micro-crack initiation, propagation, localization, and macro-fracture. Traditional measurement methods, limited by point-measurement modes and inherent contact measurement constraints, struggle to fully reveal the details of this process. DIC technology, through full-field, non-contact, high-precision optical measurement, provides unprecedented experimental capability for studying concrete failure mechanics.

From precise acquisition of complete stress-strain curves, through dynamic tracking of strain localization and shear band formation processes, to three-dimensional characterization of crack propagation paths — each application of DIC in concrete compression testing expands human understanding of the failure behavior of this most common building material.

The development of domestic DIC equipment enables more research institutions and engineering units to access high-quality full-field strain measurement capabilities at lower thresholds. As relevant standards and specifications progressively improve and multi-modal measurement technologies continue to advance, DIC is expected to become a standard configuration tool in concrete mechanics research, providing a more solid experimental foundation for improving China's building structural safety design standards.

---

</details>

---

*Published in DIC-System-Benchmark*  
*Reference: XTOP3D concrete DIC application documentation*
