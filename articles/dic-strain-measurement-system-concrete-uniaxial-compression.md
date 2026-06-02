# DIC应变测量系统在混凝土单轴压缩破坏力学研究中的应用

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：混凝土压缩破坏研究的测量困境](#1-引言混凝土压缩破坏研究的测量困境)
- [2. 混凝土单轴压缩的力学行为与损伤演化](#2-混凝土单轴压缩的力学行为与损伤演化)
- [3. 传统测量手段的盲区与DIC技术的破局](#3-传统测量手段的盲区与dic技术的破局)
- [4. DIC应变测量系统的核心技术原理](#4-dic应变测量系统的核心技术原理)
- [5. 混凝土压缩试验的DIC测量方案设计](#5-混凝土压缩试验的dic测量方案设计)
- [6. 关键测量数据与分析方法](#6-关键测量数据与分析方法)
- [7. XTDIC系统在混凝土压缩试验中的配置方案](#7-xtdic系统在混凝土压缩试验中的配置方案)
- [8. 典型应用场景与工程价值](#8-典型应用场景与工程价值)
- [9. 实验设计要点与常见问题](#9-实验设计要点与常见问题)
- [10. 结语](#10-结语)

---

## 1. 引言：混凝土压缩破坏研究的测量困境

混凝土作为世界上用量最大的建筑材料，其压缩性能直接决定了工程结构的安全性与耐久性。从超高层建筑的基础与框架到跨海大桥的桥墩与梁体，从水利工程的坝体到地下结构的衬砌，混凝土在各类工程中的承载角色决定了其力学性能研究的重要地位。

混凝土单轴压缩试验是评价混凝土力学性能最基础、最核心的测试方法。通过这一试验，研究人员可以获取混凝土的抗压强度、弹性模量、泊松比、峰值应变等关键参数，建立应力-应变全曲线，从而为结构设计提供依据。然而，混凝土是一种典型的多相非均质复合材料，其破坏过程涉及微裂纹萌生、扩展、局部化以及宏观断裂的复杂演化，传统测量手段在此过程中往往力不从心。

应变片只能测量固定方向的点应变数据，无法反映混凝土破坏过程中应变场的非均匀分布特征。更重要的是，应变片在混凝土接近峰值应力后的高应变区域往往出现数据异常或失效——应变片基底与混凝土表面之间的粘结在微裂缝密集区容易发生剥离，导致测量数据失真甚至中断。激光位移传感器虽然可以实现非接触测量，但仍然是单点测量，无法获取全场膨胀形貌。而X射线CT虽然可以观测内部结构，但设备昂贵、耗时长，无法实时监测加载过程中的损伤演化。

数字图像相关（DIC）应变测量系统以其非接触、全场、高精度的测量特性，为混凝土单轴压缩破坏力学研究提供了全新的实验手段。通过追踪试件表面散斑图案在变形前后的灰度变化，DIC可以在整个加载过程中同步获取全场三维位移数据和应变分布，将混凝土破坏这一瞬息万变的多变力学过程以可视化数据的方式完整记录下来。

## 2. 混凝土单轴压缩的力学行为与损伤演化

### 2.1 应力-应变全曲线的阶段特征

混凝土在单轴压缩荷载作用下的应力-应变曲线呈现明显的阶段性特征，大致可分为以下四个阶段：

**弹性阶段（O-A）**：应力水平低于约0.3倍抗压强度（0.3f_c），混凝土表现出近乎线弹性的应力-应变关系，内部微裂缝尚未明显扩展，变形可恢复。这一阶段的斜率即混凝土的初始弹性模量。

**稳定裂缝发展阶段（A-B）**：应力水平在0.3f_c至0.8f_c之间，裂缝开始出现并缓慢稳定扩展，材料进入弹塑性阶段。应力-应变曲线开始偏离直线，表现出轻微的非线性特征。泊松比在此阶段基本保持常数（约0.167-0.2）。

**不稳定裂缝扩展阶段（B-C）**：应力水平超过0.8f_c后，裂缝进入不稳定扩展阶段，材料体积开始膨胀（侧向膨胀速率超过轴向压缩速率），应力-应变曲线斜率持续降低。泊松比快速增大，在接近峰值应力时可达0.5以上。

**峰值后阶段与软化阶段（C点以后）**：达到峰值应力f_c后，材料进入软化阶段，承载能力迅速下降，变形局部化现象显著，形成主剪切带或劈裂裂缝，应变迅速增大直至最终破坏。

### 2.2 准脆性材料的破坏特征

混凝土属于典型的准脆性材料，其力学行为与理想脆性材料（如玻璃）和理想塑性材料（如金属）均有显著区别。准脆性材料的突出特征是：抗拉强度远低于抗压强度，且破坏前有明显的应变软化阶段。在单轴压缩条件下，混凝土的峰值应变通常在（1.5-2.5）×10⁻³量级（约1500-2500微应变），这意味着试件在达到极限荷载前已经经历了相当程度的内部损伤积累。

非均质性是理解混凝土破坏机理的关键。混凝土内部包含粗骨料、细骨料、水泥浆体以及二者之间的粘结界面等多种组分，其中骨料与水泥浆的粘结界面是天然的薄弱环节。在压缩荷载作用下，裂缝往往首先在粘结界面萌生，随后可能穿过水泥浆体扩展（砂浆裂缝），形成复杂的裂缝网络。

### 2.3 损伤局部化与剪切带形成

当混凝土进入不稳定裂缝扩展阶段后，变形开始显著局部化，形成明显的应变集中区，即剪切带（Shear Band）。剪切带是混凝土在压缩荷载下最典型的破坏模式之一，其角度通常与加载方向呈30°-60°夹角。

剪切带的形成过程是混凝土损伤累积的宏观表现：从应变场的微小不均匀性，到应变集中线的出现，再到主剪切带的贯通。这一过程的时间序列数据为研究剪切带的形成机理提供了直接的实验依据。通过DIC测量剪切带内外的应变场差异，可以定量分析剪切带宽度、应变跳跃幅度以及带内应变梯度等关键参数。这些参数对于建立混凝土的应变局部化本构模型和有限元数值模拟具有重要参考价值。

## 3. 传统测量手段的盲区与DIC技术的破局

### 3.1 应变片的局限性

在传统的混凝土压缩试验中，应变片是最常用的变形测量手段。然而，应变片只能获取固定方向的点应变数据，无法反映混凝土破坏过程中应变场的非均匀分布特征。更重要的是，应变片在混凝土接近峰值应力后的高应变区域往往出现数据异常或失效——应变片基底与混凝土表面之间的粘结在微裂缝密集区容易发生剥离，导致测量数据失真甚至中断。

应变片的另一个固有局限是接触式测量本身带来的干扰。虽然对于混凝土这类大尺度材料，应变片附加刚度的影响可以忽略，但应变片的测量方向固定，只能反映沿粘贴方向的平均应变，无法捕捉垂直于应变片方向的横向变形和剪切变形。

### 3.2 激光位移传感器的局限

激光位移传感器可以实现非接触测量单点膨胀位移，精度可达微米级。但仍然是单点测量，无法获取全场膨胀形貌；混凝土表面粗糙，激光反射特性不稳定；多传感器并行测量成本高；无法测量面内应变。

### 3.3 DIC技术的破局

DIC技术通过追踪试件表面散斑图案在变形前后的灰度变化，利用相关算法计算散斑区域的位移场和应变场。这一方法的本质是将整个视场划分为若干子区，通过匹配变形前后各子区的灰度分布来获取全场变形信息。

相比传统方法，DIC在混凝土压缩试验中的优势体现在以下几个方面：

**全场数据**：一次测量即可获取视场内所有测点的位移和应变数据，数据密度可达数十万至百万量级，远超应变片的点测模式。

**非接触测量**：无需与试件接触，避免了传感器安装对试件应力状态的影响，也消除了传感器自身刚度对测量的干扰。

**大应变测量能力**：应变测量范围覆盖0.005%至2000%以上，可以完整记录混凝土从弹性阶段到峰值后软化阶段的全过程变形。

**破坏过程追踪**：高帧率采集模式下，可以逐帧记录混凝土从裂缝萌生到扩展、直至最终破坏的完整过程，为研究破坏机理提供时间序列数据。

**多方向应变测量**：全场数据支持任意方向应变和位移的提取，可以获得横向应变、纵向应变、主应变方向等多维度信息。

## 4. DIC应变测量系统的核心技术原理

### 4.1 数字图像相关算法基础

DIC算法的核心是在变形前后的两幅图像中寻找对应子区的最佳匹配。具体而言，将参考图像（变形前）划分为若干大小相同的子区（subset），每个子区包含独特的灰度分布特征。在变形后的图像中，通过搜索与参考子区灰度分布最相似的区域，确定该子区的位移。

匹配准则通常采用归一化互相关（Normalized Cross-Correlation, NCC）或零均值归一化互相关（Zero-mean Normalized Cross-Correlation, ZNCC）函数。ZNCC对光照变化具有更好的鲁棒性，是实际应用中的首选。

位移计算达到像素精度后，通过亚像素算法（如牛顿-拉夫森迭代法、反向组合高斯-牛顿法）进一步提高位移测量精度至0.01像素量级。对于500万像素相机（2448×2048），在200mm视场下像素尺寸约0.08mm，0.01像素的位移精度对应约0.8μm的位移分辨力。

### 4.2 应变计算与平滑处理

从位移场计算应变场需要对位移数据进行空间微分。由于数字微分会放大噪声，直接对原始位移场求导得到的应变场往往噪声较大。因此，DIC软件通常采用局部最小二乘拟合或全局平滑算法来降低应变噪声。

常用的应变平滑方法包括：局部多项式拟合（在位移场的局部窗口内用多项式拟合位移分布，再解析求导）、Savitzky-Golay滤波（保持高阶矩的平滑滤波器）、以及基于有限元形函数的全局平滑方法。平滑窗口的大小需要在噪声抑制和细节保留之间权衡——窗口过大可能抹平真实的应变梯度，窗口过小则噪声抑制效果不佳。

### 4.3 三维DIC与双目立体视觉

混凝土压缩试验中，试件表面不仅发生轴向压缩变形，还伴随显著的侧向膨胀。二维DIC只能测量面内位移和应变，无法获取面外（厚度方向）的膨胀信息。三维DIC通过双目立体视觉配置，利用两台相机从不同角度拍摄试件表面，通过三角测量原理重建表面三维坐标，从而获取完整的三维位移场。

三维DIC的关键在于系统标定：通过拍摄已知几何尺寸的标定板（如棋盘格或编码点阵），确定两台相机的内参（焦距、主点、畸变系数）和外参（相对位置和姿态）。标定精度直接影响三维重建质量，进而影响位移和应变的测量精度。

对于混凝土压缩试验，三维DIC可以分离轴向压缩位移和侧向膨胀位移，计算体积应变（轴向应变+2倍侧向应变），为研究混凝土的体积膨胀特性（dilatancy）提供直接数据。

## 5. 混凝土压缩试验的DIC测量方案设计

### 5.1 试件表面散斑制备

混凝土试件表面粗糙，天然具有一定的纹理特征，但纹理的随机性和对比度通常不足以满足DIC算法的要求。因此，需要在试件表面制备人工散斑。

**散斑制备方法**：
- 白色底漆：先在试件表面喷涂一层白色亚光底漆（如乳胶漆），提供均匀的白色背景。
- 黑色散斑：待底漆干燥后，使用黑色亚光喷漆或黑色马克笔在表面随机点涂黑色斑点，形成高对比度的随机散斑图案。
- 散斑尺寸：散斑直径控制在1-3mm（对应相机分辨力下约10-30像素），散斑密度约40%-60%。
- 注意事项：散斑应覆盖整个测量区域，包括试件侧面（用于测量侧向膨胀）；避免散斑过密导致相邻散斑粘连，或过疏导致子区灰度特征不足。

**替代方案**：对于需要保持试件原始表面的情况（如研究表面裂缝的萌生和扩展），可以使用天然纹理DIC（Natural Texture DIC）技术，直接利用混凝土表面的天然纹理进行相关计算。但天然纹理的对比度和随机性通常不如人工散斑，测量精度可能略有降低。

### 5.2 成像系统配置

**相机选择**：对于标准混凝土立方体试件（150×150×150mm）或圆柱体试件（φ150×300mm），使用500万像素工业相机（2448×2048像素）即可满足测量需求。在200mm视场下，空间分辨力约0.08mm，足以分辨混凝土中的裂缝和应变局部化特征。

**镜头选择**：25-35mm焦距镜头，工作距离约400-600mm，确保两台相机均能清晰成像。

**照明方案**：均匀漫射照明是关键。推荐使用LED面光源或环形光源，避免直射光造成的镜面反射和阴影。双侧45°照射是常用的照明配置。

**采集帧率**：混凝土压缩试验的加载速率通常较低（0.5-2MPa/s），即使1fps的采集帧率也足以捕捉变形演化过程。对于研究裂缝动态扩展或冲击压缩试验，可提高采集帧率至数十至数百fps。

### 5.3 试验机同步与数据融合

DIC测量需要与万能试验机的荷载-位移数据同步：

**时间同步**：记录每帧图像的精确时间戳，与试验机的荷载-时间曲线对齐。

**触发同步**：对于特定事件（如峰值应力到达、裂缝贯通），使用外部触发信号同步启动DIC高速采集。

**数据融合**：将DIC全场应变数据与试验机荷载数据融合，构建应力-应变全曲线。与应变片单点数据不同，DIC可以选择特征区域（如应变最大区域、试件中部均匀区域等）来构建具有代表性的应力-应变曲线，从而更全面地反映混凝土的力学行为特征。

### 5.4 多相机同步方案：圆柱试件360°全周测量

对于圆柱体混凝土试件，单面DIC测量只能获取一个视角的变形信息，无法全面反映试件的三维变形状态。采用多相机同步方案，可以实现圆柱试件360°全周测量：

**四相机配置**：在试件四周均匀布置四台相机，每台相机覆盖90°弧段，通过系统标定建立统一的坐标系。

**数据拼接**：将四台相机获取的位移场和应变场拼接成完整的圆柱表面全场数据，消除单视角测量的盲区。

**优势**：全周测量可以捕捉裂缝在圆柱表面的完整扩展路径，识别主裂缝与次裂缝的空间关系，为建立三维裂缝网络模型提供实验数据。

## 6. 关键测量数据与分析方法

### 6.1 全场位移场与应变场

混凝土在单轴压缩过程中，其表面位移场和应变场的分布并非均匀对称的。由于骨料分布的随机性和试件端部约束效应的影响，位移场和应变场在加载初期就存在局部的微小差异。进入非线性阶段后，这些差异进一步放大，形成明显的应变集中区域和局部化带。

DIC技术可以在整个加载过程中同步记录全场三维位移数据（X、Y、Z三个方向），从而精确计算纵向应变（轴向）、横向应变（径向）和剪切应变。纵向应变场可以反映轴向压缩变形的空间分布，横向应变场则可以揭示侧向膨胀的不均匀性。通过纵向与横向应变场的比值，可以获得泊松比的空间分布——在弹性阶段泊松比近似均匀，而在破坏前阶段，裂缝区域的泊松比显著升高。

### 6.2 应变集中区域的识别

应变集中系数是评估混凝土裂缝萌生风险的重要参数。在DIC获取的全场应变数据中，应变最大值与区域平均应变值的比值即为局部应变集中系数。研究表明，混凝土圆柱试件在单轴压缩时，应变集中区域通常出现在试件端部（端部约束效应导致）、侧面中部（泊松效应导致）以及粘结界面附近（骨料分布导致）。

DIC通过全场应变分析可以精确定位这些应变集中区域，并追踪其随荷载增加的发展演化过程。这种能力对于理解混凝土的损伤演化规律、验证有限元模型预测具有不可替代的价值。

### 6.3 应力-应变全曲线的获取

通过DIC全场位移数据与试验机荷载数据的同步记录，可以构建混凝土试件的应力-应变全曲线。与应变片仅能获取局部应变不同，DIC提供的全场应变数据允许选择特征区域（如应变最大区域、试件中部均匀区域、避开端部效应的区域等）来构建具有代表性的应力-应变曲线，从而更全面地反映混凝土的力学行为特征。

**特征区域选择策略**：
- 均匀区法：选择试件中部避开端部效应和裂缝的均匀区域，计算平均应变，构建"平均"应力-应变曲线。
- 最大应变区法：选择应变最大区域，构建"极限"应力-应变曲线，反映试件的最不利受力状态。
- 全场统计法：计算全场应变的统计分布（均值、标准差、最大值等），构建应力-应变统计曲线。

### 6.4 裂缝检测与量化

DIC不仅可以测量位移和应变，还可以用于裂缝检测和量化：

**裂缝识别**：在应变场中，裂缝表现为应变的不连续跳跃——裂缝两侧的应变值发生突变。通过检测应变场中的不连续线，可以识别裂缝的位置和走向。

**裂缝宽度测量**：利用DIC测量的裂缝两侧位移不连续量，可以计算裂缝的开度（宽度）。对于混凝土表面裂缝，DIC可以分辨微米级的裂缝宽度变化。

**裂缝扩展追踪**：通过对比不同时刻的裂缝分布，可以追踪裂缝的扩展路径和速率，为研究裂缝扩展机理提供时间序列数据。

## 7. XTDIC系统在混凝土压缩试验中的配置方案

### 7.1 推荐配置

| 组件 | 规格 | 说明 |
|------|------|------|
| 相机 | XTDIC-CONST-SD (5MP) | 2448×2048像素，空间分辨力0.08mm@200mm视场 |
| 镜头 | 25-35mm焦距 | 工作距离400-600mm |
| 照明 | LED面光源或环形光源 | 均匀漫射照明，避免镜面反射 |
| 标定板 | 标准棋盘格标定板 | 覆盖200×200mm视场 |
| 采集帧率 | 1-10fps | 准静态加载过程 |
| 同步 | 外部触发+时间戳 | 与万能试验机同步 |

### 7.2 测量流程

1. **试件准备**：制备标准混凝土试件（立方体或圆柱体），养护至规定龄期。
2. **散斑制备**：在试件表面喷涂白色亚光底漆+黑色亚光散斑。
3. **安装定位**：将试件安装在试验机夹具中，调整位置使测量面正对相机。
4. **DIC系统架设**：安装双目相机系统，调整视场覆盖整个试件表面。
5. **系统标定**：使用标定板进行系统标定。
6. **基准采集**：采集初始状态（零荷载）的基准图像。
7. **压缩试验**：按预定加载制度执行试验，DIC全程采集图像。
8. **数据处理**：对DIC图像进行分析，计算全场三维位移和应变。
9. **结果提取**：提取应力-应变曲线、裂缝分布、应变集中系数等关键指标。

### 7.3 关键参数

| 参数 | 典型值 | 说明 |
|------|--------|------|
| 测量视场 | 200×200mm | 覆盖标准混凝土试件表面 |
| 空间分辨力 | 0.05-0.1mm | 取决于相机分辨率和视场 |
| 位移精度 | ≤0.01像素 | 亚像素算法 |
| 应变精度 | 50με | SD系列 |
| 应变测量范围 | 0.005%-2000%+ | 覆盖弹性到软化阶段 |
| 采集帧率 | 1-10fps | 准静态测试 |
| 裂缝宽度分辨力 | 5-20μm | 取决于空间分辨力和子区大小 |

## 8. 典型应用场景与工程价值

### 8.1 混凝土本构关系研究

混凝土的本构关系是结构分析和数值模拟的基础。DIC全场测量可以获取混凝土在单轴压缩下的完整应力-应变全曲线，包括弹性阶段、裂缝稳定扩展阶段、不稳定扩展阶段和软化阶段。与应变片单点数据相比，DIC可以选择不同特征区域（均匀区、最大应变区）构建多条应力-应变曲线，更全面地反映混凝土的非均质性和变异性。

**工程价值**：基于DIC全场数据的本构关系，比基于单点测量的本构关系更准确地反映混凝土的真实力学行为，为有限元模拟提供更可靠的输入参数。

### 8.2 裂缝扩展机理研究

混凝土的裂缝扩展机理是材料科学和结构工程的核心研究课题。DIC可以实时观测裂缝的萌生、扩展和贯通过程，获取裂缝的时空演化数据。通过分析裂缝尖端的应变场，可以研究裂缝扩展的驱动力和阻力机制。

**工程价值**：裂缝扩展数据是验证断裂力学模型（如双K断裂模型、裂缝带模型）和开发新型混凝土材料（如纤维增强混凝土、自愈合混凝土）的关键实验依据。

### 8.3 纤维增强混凝土性能评估

纤维增强混凝土（钢纤维、聚丙烯纤维、玄武岩纤维等）通过纤维的桥接作用抑制裂缝扩展，提高材料的韧性和延性。DIC可以定量评估纤维对裂缝扩展的抑制效果：对比素混凝土和纤维混凝土的裂缝扩展速率、裂缝宽度演化、应变软化斜率等参数。

**工程价值**：DIC数据为纤维类型、掺量、长度的优化设计提供定量依据，加速新型纤维混凝土材料的研发进程。

### 8.4 高温后混凝土残余力学性能

火灾后混凝土的残余力学性能评估是结构安全鉴定的重要内容。DIC可以测量高温后混凝土试件在压缩过程中的变形特征，评估高温损伤对材料性能的影响。通过对比常温试件和高温后试件的应力-应变曲线、裂缝扩展模式、应变局部化特征，可以建立温度-损伤-性能退化关系。

**工程价值**：DIC数据为火灾后结构安全评估和修复决策提供科学依据。

### 8.5 混凝土结构健康监测

在实际混凝土结构中（如桥梁、大坝、隧道），DIC可以用于长期健康监测：通过定期采集结构表面的图像，对比不同时刻的位移场和应变场，识别结构的变形累积、裂缝发展和损伤演化。

**工程价值**：DIC非接触、全场、可远程操作的特点，使其特别适合于大型混凝土结构的长期健康监测，替代传统的单点传感器网络。

## 9. 实验设计要点与常见问题

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 亚光漆，散斑1-3mm，密度40%-60%，覆盖整个测量区域 |
| 相机配置 | 双目三维DIC，获取完整的三维位移场 |
| 照明 | 均匀漫射照明，避免镜面反射和阴影 |
| 同步 | DIC时间戳与试验机荷载数据对齐 |
| 基准图像 | 零荷载状态下采集，作为变形计算参考 |
| 特征区域选择 | 根据研究目的选择均匀区、最大应变区或全场统计 |
| 应变平滑 | 选择合适的平滑窗口，平衡噪声抑制和细节保留 |
| 多循环测试 | 注意散斑耐久性，多次加载后可能需重新制备 |

**常见问题**：

**Q：混凝土表面粗糙，是否需要特殊处理？**
A：混凝土表面的天然纹理可以作为散斑使用，但对比度和随机性通常不足。建议喷涂白色底漆+黑色散斑，以获得高对比度的随机图案。对于需要保持原始表面的研究，可以使用天然纹理DIC，但精度可能略有降低。

**Q：裂缝穿过散斑区域，是否影响DIC测量？**
A：裂缝会导致位移不连续，在裂缝两侧形成位移跳跃。DIC算法在裂缝区域可能出现相关失败或异常位移值。建议在数据处理时识别裂缝区域，对裂缝两侧的位移场分别处理，或采用裂缝容忍DIC算法（Crack-Tolerant DIC）。

**Q：DIC测量与应变片数据如何对比验证？**
A：在试件表面同时布置应变片和散斑，在弹性阶段对比两者的应变读数。正常情况下，DIC在应变片粘贴位置的应变值应与应变片读数一致（偏差<5%）。这一验证可以确认DIC系统的测量精度。

**Q：峰值应力后试件表面剥落，散斑脱落怎么办？**
A：峰值应力后混凝土表面可能出现剥落和散斑脱落，导致DIC测量中断。建议在试验前在试件表面喷涂足够厚度的底漆，或使用耐高温、高附着力的散斑涂料。对于研究软化阶段的需求，可以考虑在试件侧面（剥落较轻的区域）布置备用测量面。

## 10. 结语

混凝土的压缩破坏不是"会不会发生"的问题，而是"如何演化、在哪里局部化、裂缝如何扩展"的量化问题。传统测量手段在这个问题上留下了显著的盲区——单点、接触、低时间分辨力，无法满足混凝土破坏机理研究对数据的精度和全面性要求。

DIC应变测量系统以其全场三维测量、非接触零干扰、高时序分辨力的特性，为混凝土单轴压缩破坏力学研究提供了全新的技术范式。从弹性阶段的微小不均匀性到软化阶段的应变局部化，从裂缝萌生到剪切带贯通，从素混凝土到纤维增强混凝土，DIC正在成为混凝土材料研究领域的核心实验工具。

XTDIC-CONST系列凭借其5MP分辨率、50με应变精度和灵活的双目立体视觉配置，为混凝土压缩试验提供了完整的解决方案。随着高性能混凝土、纤维增强混凝土、自愈合混凝土等新型材料的不断发展，对材料力学行为的精确表征需求将持续增加——DIC全场测量数据，将在混凝土材料研发和工程结构安全评估中发挥不可替代的作用。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: The Measurement Dilemma in Concrete Compression Research](#1-introduction-the-measurement-dilemma-in-concrete-compression-research)
- [2. Mechanical Behavior and Damage Evolution of Concrete Under Uniaxial Compression](#2-mechanical-behavior-and-damage-evolution-of-concrete-under-uniaxial-compression)
- [3. Blind Spots of Traditional Methods and DIC Breakthrough](#3-blind-spots-of-traditional-methods-and-dic-breakthrough)
- [4. Core Technical Principles of DIC Strain Measurement Systems](#4-core-technical-principles-of-dic-strain-measurement-systems)
- [5. DIC Measurement Scheme Design for Concrete Compression Tests](#5-dic-measurement-scheme-design-for-concrete-compression-tests)
- [6. Key Measurement Data and Analysis Methods](#6-key-measurement-data-and-analysis-methods)
- [7. XTDIC System Configuration for Concrete Compression Tests](#7-xtdic-system-configuration-for-concrete-compression-tests)
- [8. Typical Application Scenarios and Engineering Value](#8-typical-application-scenarios-and-engineering-value)
- [9. Experimental Design Considerations and FAQ](#9-experimental-design-considerations-and-faq)
- [10. Conclusion](#10-conclusion-1)

---

## 1. Introduction: The Measurement Dilemma in Concrete Compression Research

Concrete is the most widely used construction material in the world, and its compressive performance directly determines the safety and durability of engineering structures. From the foundations and frames of super high-rise buildings to the piers and girders of sea-crossing bridges, from dam bodies of hydraulic engineering to linings of underground structures, concrete's load-bearing role in various projects determines the important position of its mechanical property research.

The uniaxial compression test is the most basic and core testing method for evaluating concrete mechanical properties. Through this test, researchers can obtain key parameters such as compressive strength, elastic modulus, Poisson's ratio, and peak strain, establish the complete stress-strain curve, and thus provide basis for structural design. However, concrete is a typical multi-phase heterogeneous composite material, and its failure process involves complex evolution of micro-crack initiation, propagation, localization, and macro-fracture, where traditional measurement methods often fall short.

Strain gauges can only measure point strain data in fixed directions and cannot reflect the non-uniform distribution characteristics of strain fields during concrete failure. More importantly, strain gauges often exhibit data anomalies or failure in high strain regions after concrete approaches peak stress—the bonding between the strain gauge base and concrete surface is prone to peeling in micro-crack dense zones, leading to measurement data distortion or even interruption. Laser displacement sensors, while enabling non-contact measurement, are still single-point measurements that cannot capture full-field expansion topography. X-ray CT, though capable of observing internal structures, is expensive, time-consuming, and cannot monitor damage evolution during loading in real-time.

Digital Image Correlation (DIC) strain measurement systems, with their non-contact, full-field, and high-precision measurement characteristics, provide a new experimental means for concrete uniaxial compression failure mechanics research. By tracking the grayscale changes of speckle patterns on specimen surfaces before and after deformation, DIC can simultaneously obtain full-field 3D displacement data and strain distribution throughout the entire loading process, completely recording the multi-variable mechanical process of concrete failure in a visualized data format.

## 2. Mechanical Behavior and Damage Evolution of Concrete Under Uniaxial Compression

### 2.1 Stage Characteristics of Stress-Strain Curve

The stress-strain curve of concrete under uniaxial compression shows obvious stage characteristics, roughly divided into four stages:

**Elastic stage (O-A)**: When stress level is below approximately 0.3 times compressive strength (0.3f_c), concrete exhibits nearly linear elastic stress-strain relationship, internal micro-cracks have not significantly expanded, and deformation is recoverable. The slope of this stage is the initial elastic modulus of concrete.

**Stable crack development stage (A-B)**: When stress level is between 0.3f_c and 0.8f_c, cracks begin to appear and slowly expand stably, and the material enters the elastic-plastic stage. The stress-strain curve begins to deviate from the straight line, showing slight nonlinear characteristics. Poisson's ratio remains basically constant in this stage (approximately 0.167-0.2).

**Unstable crack propagation stage (B-C)**: After stress level exceeds 0.8f_c, cracks enter the unstable propagation stage, material volume begins to expand (lateral expansion rate exceeds axial compression rate), and the slope of the stress-strain curve continues to decrease. Poisson's ratio increases rapidly, reaching above 0.5 when approaching peak stress.

**Post-peak and softening stage (after point C)**: After reaching peak stress f_c, the material enters the softening stage, bearing capacity rapidly decreases, deformation localization becomes significant, forming main shear bands or splitting cracks, and strain rapidly increases until final failure.

### 2.2 Failure Characteristics of Quasi-Brittle Materials

Concrete belongs to typical quasi-brittle materials, whose mechanical behavior has significant differences from both ideal brittle materials (such as glass) and ideal plastic materials (such as metals). The prominent feature of quasi-brittle materials is: tensile strength is much lower than compressive strength, and there is an obvious strain softening stage before failure. Under uniaxial compression conditions, the peak strain of concrete is usually in the order of (1.5-2.5)×10⁻³ (approximately 1500-2500 microstrain), meaning the specimen has experienced considerable internal damage accumulation before reaching ultimate load.

Heterogeneity is the key to understanding concrete failure mechanisms. Concrete internally contains multiple components such as coarse aggregate, fine aggregate, cement paste, and the bonding interface between them, among which the bonding interface between aggregate and cement paste is a natural weak link. Under compressive load, cracks often first initiate at the bonding interface, and then may propagate through the cement paste, forming a complex crack network.

### 2.3 Damage Localization and Shear Band Formation

When concrete enters the unstable crack propagation stage, deformation begins to significantly localize, forming obvious strain concentration zones, namely shear bands. Shear bands are one of the most typical failure modes of concrete under compressive load, with angles usually forming 30°-60° angles with the loading direction.

The formation process of shear bands is the macroscopic manifestation of concrete damage accumulation: from small inhomogeneities in the strain field, to the appearance of strain concentration lines, to the penetration of main shear bands. This time-series data provides direct experimental evidence for studying shear band formation mechanisms. Through DIC measurement of strain field differences inside and outside shear bands, key parameters such as shear band width, strain jump amplitude, and strain gradient within the band can be quantitatively analyzed. These parameters have important reference value for establishing concrete strain localization constitutive models and finite element numerical simulation.

## 3. Blind Spots of Traditional Methods and DIC Breakthrough

### 3.1 Limitations of Strain Gauges

In traditional concrete compression tests, strain gauges are the most commonly used deformation measurement means. However, strain gauges can only obtain point strain data in fixed directions and cannot reflect the non-uniform distribution characteristics of strain fields during concrete failure. More importantly, strain gauges often exhibit data anomalies or failure in high strain regions after concrete approaches peak stress—the bonding between the strain gauge base and concrete surface is prone to peeling in micro-crack dense zones, leading to measurement data distortion or even interruption.

Another inherent limitation of strain gauges is the interference caused by contact measurement itself. Although for large-scale materials like concrete, the effect of strain gauge additional stiffness can be ignored, the measurement direction of strain gauges is fixed, only reflecting average strain along the粘贴 direction, unable to capture transverse deformation perpendicular to the strain gauge direction and shear deformation.

### 3.2 Limitations of Laser Displacement Sensors

Laser displacement sensors can achieve non-contact measurement of single-point expansion displacement with micron-level precision. But they remain single-point measurements, unable to obtain full-field expansion topography; concrete surfaces are rough with unstable laser reflection characteristics; multi-sensor parallel measurement is costly; cannot measure in-plane strain.

### 3.3 DIC Breakthrough

DIC technology tracks grayscale changes of speckle patterns on specimen surfaces before and after deformation, using correlation algorithms to calculate displacement fields and strain fields of speckle regions. The essence of this method is dividing the entire field of view into several subsets, and obtaining full-field deformation information by matching grayscale distributions of each subset before and after deformation.

Compared with traditional methods, DIC advantages in concrete compression tests are reflected in the following aspects:

**Full-field data**: One measurement can obtain displacement and strain data of all measurement points in the field of view, with data density reaching hundreds of thousands to millions of points, far exceeding the point measurement mode of strain gauges.

**Non-contact measurement**: No need to contact the specimen, avoiding the influence of sensor installation on specimen stress state, and eliminating interference from sensor stiffness on measurement.

**Large strain measurement capability**: Strain measurement range covers 0.005% to over 2000%, capable of completely recording the entire process deformation from elastic stage to post-peak softening stage.

**Failure process tracking**: In high frame rate acquisition mode, can frame-by-frame record the complete process from crack initiation to propagation to final failure, providing time-series data for studying failure mechanisms.

**Multi-directional strain measurement**: Full-field data supports extraction of strain and displacement in any direction, obtaining multi-dimensional information such as transverse strain, longitudinal strain, and principal strain direction.

## 4. Core Technical Principles of DIC Strain Measurement Systems

### 4.1 Digital Image Correlation Algorithm Foundation

The core of DIC algorithm is finding the best match of corresponding subsets in two images before and after deformation. Specifically, the reference image (before deformation) is divided into several subsets of the same size, each containing unique grayscale distribution characteristics. In the deformed image, by searching for regions most similar to the reference subset's grayscale distribution, the displacement of that subset is determined.

Matching criteria typically use Normalized Cross-Correlation (NCC) or Zero-mean Normalized Cross-Correlation (ZNCC) functions. ZNCC has better robustness to illumination changes and is the preferred choice in practical applications.

After displacement calculation reaches pixel precision, sub-pixel algorithms (such as Newton-Raphson iteration, inverse compositional Gauss-Newton method) further improve displacement measurement precision to 0.01 pixel level. For a 5-megapixel camera (2448×2048), at 200mm field of view, pixel size is approximately 0.08mm, and 0.01 pixel displacement precision corresponds to approximately 0.8μm displacement resolution.

### 4.2 Strain Calculation and Smoothing

Calculating strain fields from displacement fields requires spatial differentiation of displacement data. Since digital differentiation amplifies noise, strain fields obtained by directly differentiating raw displacement fields often have large noise. Therefore, DIC software typically uses local least squares fitting or global smoothing algorithms to reduce strain noise.

Common strain smoothing methods include: local polynomial fitting (fitting displacement distribution with polynomials in local windows of displacement field, then analytically differentiating), Savitzky-Golay filtering (smoothing filter preserving high-order moments), and global smoothing methods based on finite element shape functions. Smoothing window size needs to balance between noise suppression and detail preservation—windows too large may smooth out real strain gradients, while windows too small provide insufficient noise suppression.

### 4.3 3D DIC and Binocular Stereo Vision

In concrete compression tests, specimen surfaces not only undergo axial compressive deformation but also significant lateral expansion. 2D DIC can only measure in-plane displacement and strain, unable to obtain out-of-plane (thickness direction) expansion information. 3D DIC through binocular stereo vision configuration uses two cameras shooting specimen surfaces from different angles, reconstructing surface 3D coordinates through triangulation principles, thereby obtaining complete 3D displacement fields.

The key to 3D DIC is system calibration: by photographing calibration boards with known geometric dimensions (such as checkerboards or coded point arrays), determining internal parameters (focal length, principal point, distortion coefficients) and external parameters (relative position and pose) of both cameras. Calibration accuracy directly affects 3D reconstruction quality, which in turn affects displacement and strain measurement accuracy.

For concrete compression tests, 3D DIC can separate axial compressive displacement and lateral expansion displacement, calculating volumetric strain (axial strain + 2× lateral strain), providing direct data for studying concrete's volume expansion characteristics (dilatancy).

## 5. DIC Measurement Scheme Design for Concrete Compression Tests

### 5.1 Specimen Surface Speckle Preparation

Concrete specimen surfaces are rough and naturally have certain texture features, but the randomness and contrast of textures are usually insufficient to meet DIC algorithm requirements. Therefore, artificial speckles need to be prepared on specimen surfaces.

**Speckle preparation method**:
- White base coat: First spray a layer of white matte primer (such as latex paint) on specimen surface to provide uniform white background.
- Black speckles: After primer dries, use black matte spray paint or black marker to randomly dot black spots on surface, forming high-contrast random speckle patterns.
- Speckle size: Speckle diameter controlled at 1-3mm (approximately 10-30 pixels at camera resolution), speckle density about 40%-60%.
- Notes: Speckles should cover the entire measurement area, including specimen sides (for measuring lateral expansion); avoid speckles too dense causing adjacent speckles to粘连, or too sparse causing insufficient subset grayscale features.

**Alternative**: For situations requiring maintaining specimen original surface (such as studying surface crack initiation and propagation), Natural Texture DIC technology can be used, directly utilizing concrete surface natural texture for correlation calculation. However, natural texture contrast and randomness are usually inferior to artificial speckles, and measurement accuracy may be slightly reduced.

### 5.2 Imaging System Configuration

**Camera selection**: For standard concrete cube specimens (150×150×150mm) or cylinder specimens (φ150×300mm), a 5-megapixel industrial camera (2448×2048 pixels) can meet measurement requirements. At 200mm field of view, spatial resolution is approximately 0.08mm, sufficient to resolve cracks and strain localization features in concrete.

**Lens selection**: 25-35mm focal length lens, working distance approximately 400-600mm, ensuring both cameras can image clearly.

**Lighting scheme**: Uniform diffuse lighting is key. LED panel lights or ring lights are recommended, avoiding specular reflection and shadows from direct light. Dual 45° illumination is a commonly used lighting configuration.

**Acquisition frame rate**: Concrete compression test loading rates are usually low (0.5-2MPa/s), so even 1fps acquisition rate is sufficient to capture deformation evolution. For studying dynamic crack propagation or impact compression tests, acquisition frame rate can be increased to tens to hundreds of fps.

### 5.3 Testing Machine Synchronization and Data Fusion

DIC measurement needs to synchronize with universal testing machine load-displacement data:

**Time synchronization**: Record precise timestamps for each frame, aligned with testing machine load-time curve.

**Trigger synchronization**: For specific events (such as peak stress arrival, crack penetration), use external trigger signals to synchronously start DIC high-speed acquisition.

**Data fusion**: Integrate DIC full-field strain data with testing machine load data to construct stress-strain full curve. Unlike strain gauge single-point data, DIC can select characteristic regions (such as maximum strain region, specimen middle uniform region, etc.) to construct representative stress-strain curves, thereby more comprehensively reflecting concrete's mechanical behavior characteristics.

### 5.4 Multi-Camera Synchronization: 360° Full Circumference Measurement for Cylinder Specimens

For cylindrical concrete specimens, single-face DIC measurement can only obtain deformation information from one viewing angle, unable to fully reflect the specimen's 3D deformation state. Using multi-camera synchronization schemes, 360° full circumference measurement of cylindrical specimens can be achieved:

**Four-camera configuration**: Four cameras uniformly arranged around specimen, each covering 90° arc segment, establishing unified coordinate system through system calibration.

**Data stitching**: Stitch displacement fields and strain fields obtained from four cameras into complete cylindrical surface full-field data, eliminating blind spots from single-view measurement.

**Advantages**: Full circumference measurement can capture complete crack propagation paths on cylindrical surfaces, identify spatial relationships between main cracks and secondary cracks, providing experimental data for establishing 3D crack network models.

## 6. Key Measurement Data and Analysis Methods

### 6.1 Full-Field Displacement and Strain Fields

During concrete uniaxial compression, the distribution of surface displacement and strain fields is not uniformly symmetric. Due to randomness of aggregate distribution and specimen end constraint effects, displacement and strain fields already have local small differences in early loading stages. After entering nonlinear stage, these differences further amplify, forming obvious strain concentration regions and localization bands.

DIC technology can synchronously record full-field 3D displacement data (X, Y, Z three directions) throughout the entire loading process, thereby precisely calculating longitudinal strain (axial), transverse strain (radial), and shear strain. Longitudinal strain fields can reflect spatial distribution of axial compressive deformation, while transverse strain fields can reveal non-uniformity of lateral expansion. Through the ratio of longitudinal to transverse strain fields, Poisson's ratio spatial distribution can be obtained—Poisson's ratio is approximately uniform in elastic stage, while in pre-failure stage, Poisson's ratio in crack regions significantly increases.

### 6.2 Strain Concentration Region Identification

Strain concentration coefficient is an important parameter for assessing concrete crack initiation risk. In DIC-obtained full-field strain data, the ratio of maximum strain value to regional average strain value is the local strain concentration coefficient. Research shows that for concrete cylinder specimens under uniaxial compression, strain concentration regions usually appear at specimen ends (caused by end constraint effects), middle of sides (caused by Poisson effect), and near bonding interfaces (caused by aggregate distribution).

DIC through full-field strain analysis can precisely locate these strain concentration regions and track their development evolution process with increasing load. This capability makes DIC an irreplaceable tool for understanding concrete damage evolution laws and verifying finite element model predictions.

### 6.3 Stress-Strain Full Curve Acquisition

Through synchronous recording of DIC full-field displacement data and testing machine load data, concrete specimen's stress-strain full curve can be constructed. Unlike strain gauge single-point data, DIC's full-field strain data allows selecting different characteristic regions (such as uniform region, maximum strain region) to construct multiple stress-strain curves, more comprehensively reflecting concrete's heterogeneity and variability.

**Characteristic region selection strategies**:
- Uniform zone method: Select specimen middle region avoiding end effects and cracks, calculate average strain, construct "average" stress-strain curve.
- Maximum strain zone method: Select maximum strain region, construct "limit" stress-strain curve, reflecting specimen's most unfavorable stress state.
- Full-field statistical method: Calculate statistical distribution of full-field strain (mean, standard deviation, maximum, etc.), construct stress-strain statistical curve.

### 6.4 Crack Detection and Quantification

DIC can not only measure displacement and strain but also be used for crack detection and quantification:

**Crack identification**: In strain fields, cracks appear as discontinuous jumps in strain—strain values on both sides of cracks undergo突变. By detecting discontinuous lines in strain fields, crack positions and orientations can be identified.

**Crack width measurement**: Using DIC-measured displacement discontinuity on both sides of cracks, crack opening (width) can be calculated. For concrete surface cracks, DIC can resolve micron-level crack width changes.

**Crack propagation tracking**: By comparing crack distributions at different times, crack propagation paths and rates can be tracked, providing time-series data for studying crack propagation mechanisms.

## 7. XTDIC System Configuration for Concrete Compression Tests

### 7.1 Recommended Configuration

| Component | Specification | Notes |
|-----------|--------------|-------|
| Camera | XTDIC-CONST-SD (5MP) | 2448×2048 pixels, 0.08mm spatial resolution @200mm FOV |
| Lens | 25-35mm focal length | Working distance 400-600mm |
| Lighting | LED panel or ring light | Uniform diffuse lighting, avoid specular reflection |
| Calibration board | Standard checkerboard calibration board | Cover 200×200mm FOV |
| Acquisition rate | 1-10fps | Quasi-static loading process |
| Synchronization | External trigger + timestamp | Sync with universal testing machine |

### 7.2 Measurement Workflow

1. Specimen preparation, speckle fabrication, installation and positioning, DIC system setup, system calibration, reference acquisition (zero load), compression test with DIC acquisition, data processing, key metric extraction.

### 7.3 Key Parameters

| Parameter | Typical Value | Notes |
|-----------|--------------|-------|
| Measurement FOV | 200×200mm | Cover standard concrete specimen surface |
| Spatial resolution | 0.05-0.1mm | Depends on camera resolution and FOV |
| Displacement precision | ≤0.01 pixel | Sub-pixel algorithm |
| Strain precision | 50με | SD series |
| Strain measurement range | 0.005%-2000%+ | Cover elastic to softening stage |
| Acquisition rate | 1-10fps | Quasi-static testing |
| Crack width resolution | 5-20μm | Depends on spatial resolution and subset size |

## 8. Typical Application Scenarios and Engineering Value

### 8.1 Concrete Constitutive Relationship Research

Concrete's constitutive relationship is the foundation of structural analysis and numerical simulation. DIC full-field measurement can obtain the complete stress-strain full curve of concrete under uniaxial compression, including elastic stage, stable crack propagation stage, unstable propagation stage, and softening stage. Compared with strain gauge single-point data, DIC can select different characteristic regions (uniform zone, maximum strain zone) to construct multiple stress-strain curves, more comprehensively reflecting concrete's heterogeneity and variability.

**Engineering value**: Constitutive relationships based on DIC full-field data more accurately reflect concrete's true mechanical behavior than those based on single-point measurement, providing more reliable input parameters for finite element simulation.

### 8.2 Crack Propagation Mechanism Research

Concrete's crack propagation mechanism is a core research topic in materials science and structural engineering. DIC can real-time observe crack initiation, propagation, and penetration processes, obtaining crack spatiotemporal evolution data. By analyzing strain fields at crack tips, crack propagation driving forces and resistance mechanisms can be studied.

**Engineering value**: Crack propagation data is key experimental evidence for verifying fracture mechanics models (such as double-K fracture model, crack band model) and developing new concrete materials (such as fiber-reinforced concrete, self-healing concrete).

### 8.3 Fiber-Reinforced Concrete Performance Evaluation

Fiber-reinforced concrete (steel fiber, polypropylene fiber, basalt fiber, etc.) inhibits crack propagation through fiber bridging effects, improving material toughness and ductility. DIC can quantitatively evaluate fiber's inhibitory effect on crack propagation: comparing crack propagation rates, crack width evolution, strain softening slopes, and other parameters between plain concrete and fiber concrete.

**Engineering value**: DIC data provides quantitative basis for optimization design of fiber type, dosage, and length, accelerating the R&D process of new fiber concrete materials.

### 8.4 Residual Mechanical Properties of Post-High-Temperature Concrete

Residual mechanical property assessment of concrete after fire is an important content of structural safety appraisal. DIC can measure deformation characteristics of post-high-temperature concrete specimens during compression, assessing the impact of high-temperature damage on material properties. By comparing stress-strain curves, crack propagation patterns, and strain localization characteristics between room-temperature specimens and post-high-temperature specimens, temperature-damage-performance degradation relationships can be established.

**Engineering value**: DIC data provides scientific basis for post-fire structural safety assessment and repair decision-making.

### 8.5 Concrete Structure Health Monitoring

In actual concrete structures (such as bridges, dams, tunnels), DIC can be used for long-term health monitoring: by regularly acquiring images of structure surfaces, comparing displacement fields and strain fields at different times, identifying structural deformation accumulation, crack development, and damage evolution.

**Engineering value**: DIC's non-contact, full-field, remotely operable characteristics make it particularly suitable for long-term health monitoring of large concrete structures, replacing traditional single-point sensor networks.

## 9. Experimental Design Considerations and FAQ

| Key Factor | Considerations |
|------------|---------------|
| Speckle preparation | Matte paint, speckle 1-3mm, density 40%-60%, cover entire measurement area |
| Camera configuration | Binocular 3D DIC, obtain complete 3D displacement field |
| Lighting | Uniform diffuse lighting, avoid specular reflection and shadows |
| Synchronization | DIC timestamps aligned with testing machine load data |
| Reference image | Acquire at zero load, serve as deformation calculation reference |
| Characteristic region selection | Select uniform zone, maximum strain zone, or full-field statistics according to research purpose |
| Strain smoothing | Select appropriate smoothing window, balance noise suppression and detail preservation |
| Multi-cycle testing | Monitor speckle durability, may need re-preparation after multiple loadings |

**FAQ**:

**Q: Concrete surface is rough, does it need special treatment?**
A: Concrete surface natural texture can be used as speckles, but contrast and randomness are usually insufficient. It is recommended to spray white primer + black speckles for high-contrast random patterns. For research requiring maintaining original surface, Natural Texture DIC can be used, but accuracy may be slightly reduced.

**Q: Cracks pass through speckle regions, does it affect DIC measurement?**
A: Cracks cause displacement discontinuity, forming displacement jumps on both sides. DIC algorithms may experience correlation failure or abnormal displacement values in crack regions. It is recommended to identify crack regions during data processing, process displacement fields on both sides of cracks separately, or use Crack-Tolerant DIC algorithms.

**Q: How to compare and verify DIC measurement with strain gauge data?**
A: Arrange both strain gauges and speckles on specimen surface simultaneously, compare strain readings of both in elastic stage. Normally, DIC strain values at strain gauge粘贴 positions should be consistent with strain gauge readings (deviation <5%). This verification can confirm DIC system's measurement accuracy.

**Q: After peak stress, specimen surface spalls and speckles fall off, what to do?**
A: After peak stress, concrete surface may experience spalling and speckle脱落, causing DIC measurement interruption. It is recommended to spray sufficient thickness primer on specimen surface before test, or use high-temperature resistant, high-adhesion speckle paint. For research needs in softening stage, consider arranging backup measurement faces on specimen sides (where spalling is lighter).

## 10. Conclusion

Concrete compression failure is not a question of "whether it happens" but a quantification problem of "how it evolves, where it localizes, and how cracks propagate." Traditional measurement methods leave significant blind spots—single-point, contact-based, low temporal resolution—unable to meet the precision and comprehensiveness requirements of concrete failure mechanism research for data.

DIC strain measurement systems, with their full-field 3D measurement, non-contact zero-interference, and high temporal resolution characteristics, provide a new technical paradigm for concrete uniaxial compression failure mechanics research. From small inhomogeneities in elastic stage to strain localization in softening stage, from crack initiation to shear band penetration, from plain concrete to fiber-reinforced concrete, DIC is becoming a core experimental tool in concrete materials research.

The XTDIC-CONST series, with 5MP resolution, 50με strain precision, and flexible binocular stereo vision configuration, provides a complete solution for concrete compression tests. As high-performance concrete, fiber-reinforced concrete, self-healing concrete, and other new materials continue to develop, the demand for precise characterization of material mechanical behavior will continue to increase—DIC full-field measurement data will play an irreplaceable role in concrete material R&D and engineering structure safety assessment.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D XTDIC system documentation and concrete compression testing application notes*
