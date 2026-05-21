# DIC技术用于材料与结构应力-应变测试：原理、应用场景与测试案例

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：材料应力-应变测试的核心地位](#1-引言材料应力-应变测试的核心地位)
- [2. DIC技术原理：从散斑图像到全场应变](#2-dic技术原理从散斑图像到全场应变)
- [3. 传统测量方法的局限](#3-传统测量方法的局限)
- [4. DIC在材料应力-应变测试中的核心能力](#4-dic在材料应力-应变测试中的核心能力)
- [5. 精度验证：DIC与应变片的对比数据](#5-精度验证dic与应变片的对比数据)
- [6. 典型应用场景与测试案例](#6-典型应用场景与测试案例)
- [7. XTDIC系统技术方案](#7-xtdic系统技术方案)
- [8. 实验设计与数据处理](#8-实验设计与数据处理)
- [9. 行业标准与规范](#9-行业标准与规范)
- [10. 国产DIC在材料测试领域的发展](#10-国产dic在材料测试领域的发展)
- [11. 结语](#11-结语)

---

## 1. 引言：材料应力-应变测试的核心地位

材料的应力-应变关系是工程设计与安全评估最基础的数据输入。从航空航天用钛合金的屈服强度到建筑用钢筋的断后伸长率，从复合材料的层间断裂韧性到橡胶密封件的超弹性本构参数，几乎所有工程材料的力学性能评价都离不开应力-应变测试。

以金属材料为例，一次标准的拉伸试验需要测定屈服强度、抗拉强度、断后伸长率、断面收缩率等关键指标。这些参数直接决定了材料在结构中的许用应力水平，进而影响整个工程的安全裕度。对于复合材料、橡胶、混凝土等非均质或非线性材料，应力-应变测试的复杂度更高——各向异性、非线性本构、大变形、应变局部化等现象使得传统单点测量方法难以全面表征材料的力学行为。

数字图像相关（DIC）技术的出现，为材料应力-应变测试带来了方法论层面的变革。通过非接触式光学测量，DIC可以在整个试验过程中同步获取试件表面的全场位移和应变数据，将传统的"点测量"升级为"场测量"，为材料力学性能研究提供了前所未有的数据维度和空间分辨率。

## 2. DIC技术原理：从散斑图像到全场应变

### 2.1 基本原理

数字图像相关法（Digital Image Correlation，DIC），又称数字散斑相关法，其核心思想是通过匹配变形前后两幅数字图像中对应区域的灰度信息，计算物体表面的位移场和应变场。

测量过程的第一步是在试件表面制备散斑图案——一种随机分布的黑白斑点图案，作为变形信息的载体。散斑图案需要满足两个基本要求：一是随机性，确保每个子区域的灰度分布具有唯一可识别性；二是适当的密度和粒径，与相机分辨率和测量视场匹配。

试验过程中，工业相机在试件变形前后分别采集散斑图像。以变形前图像为参考图像，DIC算法在参考图像中选取以待测点为中心的矩形子区（通常为(2M+1)×(2M+1)像素），然后在变形后图像中通过搜索算法和相关函数计算，寻找与该子区互相关系数最大的区域，从而确定该点在变形后的位置。

### 2.2 相关函数与亚像素算法

子区匹配的核心是相关函数。常用的归一化互相关函数（NCC）或最小平方距离函数（SSD）用于衡量参考子区与目标子区之间的相似程度。当相关函数取得最大值时，即认为找到了最佳匹配位置。

由于数字图像的离散性，直接匹配只能获得整像素级的位移精度。DIC系统通过亚像素插值算法（如双三次样条插值、二次曲面拟合等）将位移精度提升至0.01像素甚至更高。结合相机标定参数，亚像素级位移精度可以转换为微米级的实际位移测量精度。

### 2.3 三维DIC与双目立体视觉

三维DIC系统基于双目立体视觉原理，使用两个相机从不同角度同时拍摄试件表面。通过预先标定的相机内外参数和立体匹配算法，系统可以重建散斑图案上每个匹配点的三维空间坐标。比较变形前后三维坐标的变化，即可同时获得面内位移（X、Y方向）和离面位移（Z方向），进而计算完整的三维应变张量。

### 2.4 从位移场到位应变场

获得全场位移数据后，DIC软件通过对位移场进行空间微分计算应变场。由于位移数据包含噪声，直接微分会放大噪声，因此需要先对位移场进行平滑处理（如最小二乘拟合、样条插值等），然后再计算应变。常用的应变计算方法包括拉格朗日应变、格林-应变等，适用于不同量级变形的分析需求。

## 3. 传统测量方法的局限

### 3.1 应变片

应变片是材料拉伸试验中最常用的变形测量工具，其标称精度可达1με。但这一精度是在理想实验室条件下针对特定材料和粘接工艺给出的。在实际复杂工况下，应变片的有效精度可能大打折扣：

**单点局限**：应变片只能测量粘贴点附近局部区域的平均应变，无法反映应变场的空间分布。对于非均质材料（如复合材料、混凝土）或存在应力集中的情况，单点数据难以代表试件整体的变形状态。

**方向限制**：单个应变片只能测量沿其敏感栅方向的应变。要获得主应变方向和大小，需要粘贴应变花（三个不同方向的应变片组合），增加了制备工作量。

**量程有限**：常规应变片的测量范围通常在5%以内，对于橡胶等大变形材料（断裂伸长率可达300%-800%），应变片在远未达到材料断裂时就已失效。

**接触影响**：应变片需要粘贴在试件表面，对于软质材料（如橡胶、生物组织），应变片的附加刚度可能改变局部应力状态，引入测量误差。

### 3.2 引伸计

引伸计可以测量标距范围内的平均应变，精度较高（可达0.5με），但同样存在接触式测量的固有问题：需要与试件物理接触（夹持或刀口接触），可能损伤软质材料表面；标距固定，无法灵活调整测量区域；对于大变形试验，引伸计需要在试件断裂前卸除，无法记录断裂瞬态过程。

### 3.3 激光多普勒测振仪

激光多普勒测振仪可以实现非接触测量，但本质上是单点扫描式测量——要获取全场数据需要在试件表面逐点扫描，测量速度慢，不适合动态试验。此外，设备成本较高，对试件表面反射特性有要求。

## 4. DIC在材料应力-应变测试中的核心能力

### 4.1 全场数据：从点到面的维度提升

DIC最本质的优势在于将测量维度从"点"提升到"面"。一次标准拉伸试验，DIC可以同步获取视场内数十万至数百万个测点的位移和应变数据。这种数据密度的提升不是简单的数量增加，而是带来了质的飞跃——研究者可以观察应变场的空间分布、识别应变集中区域、追踪裂纹扩展路径，这些都是传统方法无法实现的。

### 4.2 多物理量同步获取

现代DIC系统可以同时解算多个力学量：面内位移（U、V）、离面位移（W）、面内应变（ε_xx、ε_yy、ε_xy）、主应变（ε_1、ε_2）、主应变方向角、厚度减薄率等。这些多维数据支持复杂失效模式的解耦分析，例如可以同时评估材料的塑性变形、颈缩行为和损伤演化。

### 4.3 全过程可视化

DIC以位移云图、应变云图、矢量场等形式实时呈现变形过程，实现"所见即所得"的实验分析。研究者可以在试验过程中直观判断最大变形点位置、应变集中区域的发展、裂纹萌生与扩展方向，及时调整试验方案或关注重点区域。

### 4.4 大应变与极端工况适应

DIC的应变测量范围覆盖0.005%至2000%以上，从金属材料的弹性阶段（应变<0.2%）到橡胶材料的超大变形（应变>500%），从室温到3000℃超高温环境，从准静态到微秒级瞬态动态过程，DIC均能提供有效的全场应变数据。

### 4.5 有限元验证

DIC全场数据为有限元分析（FEA）提供了前所未有的验证手段。传统方法只能对比有限个点的应变值，而DIC可以提供整个视场内的应变场分布云图，与有限元计算结果进行逐点对比，更全面地评估模型的准确性和适用性。

## 5. 精度验证：DIC与应变片的对比数据

DIC测量精度是工程应用中最为关注的问题之一。多项对比实验数据表明：

在金属材料标准拉伸试验中，DIC与应变片的纵向应变测量结果高度一致。实测数据显示，两者应变差值在20με以内——具体对比数据为0.085με、19.5με、11.3με，均在20微应变范围之内。这一精度水平对于工程应用完全足够，因为大多数工程材料的屈服应变在数百至数千微应变量级。

在复合材料领域，ASTM E08委员会组织多家航空实验室对CFRP螺栓连接件进行了疲劳试验交叉验证。数据显示，DIC全场应变测量结果与传统应变片数据误差小于1.8%，并且能够提前约2000次循环预警螺栓孔边微裂纹的萌生，证明了其工程适用性。

在高温环境下，DIC系统与传统引伸计的对比数据同样令人信服：弹性阶段偏差≤1.2%，塑性阶段偏差≤2.8%，断裂前临界阶段（受高温白雾影响）最大偏差3.5%。全场位移测量标准差≤0.03mm，验证了非接触测量在极端工况下的可靠性。

## 6. 典型应用场景与测试案例

### 6.1 金属材料拉伸试验

金属材料的拉伸试验是应力-应变测试最经典的应用场景。DIC在金属拉伸试验中的价值不仅在于替代应变片获取应力-应变曲线，更在于揭示传统方法无法观测的现象：

**颈缩行为研究**：金属材料在达到抗拉强度后进入局部颈缩阶段，变形集中在颈缩区域内。DIC可以精确记录颈缩区域的应变分布、颈缩起始位置和发展过程，为研究材料的塑性失稳行为提供关键数据。

**预制孔应力集中**：对于带有预制孔的金属试件（模拟螺栓连接孔），DIC可以测量孔边的应变集中系数和应变梯度，评估应力集中对材料承载能力的影响。

**断裂瞬态记录**：DIC配合高速相机可以记录金属试件断裂瞬间的应变场演化，揭示断裂起始位置和裂纹扩展速度。

### 6.2 复合材料力学表征

复合材料（如碳纤维增强聚合物CFRP、玻璃纤维增强聚合物GFRP）因其各向异性和多相结构，应力-应变测试面临独特挑战：

**各向异性表征**：复合材料的力学性能随方向变化，DIC全场数据可以同时获取不同方向的应变分布，为各向异性本构模型的建立提供丰富的实验数据。

**损伤演化分析**：复合材料在加载过程中经历基体开裂、界面脱粘、纤维断裂等多种损伤模式。DIC通过应变场异常（如局部应变突变、应变梯度异常）来识别损伤起始位置和扩展路径。

**高温双向拉伸**：在航空航天与新能源领域，复合材料需要在高温环境下工作。DIC配合高温试验箱和耐高温光学窗口，可以在不同温度下开展双向拉伸试验，获得弹性模量、泊松比、屈服强度随温度的连续变化曲线，区分常温纤维主导失效与高温基体主导失效的模式差异。

**高速瞬态脆断**：XTDIC-SPARK系统配合高速相机，可以捕捉复合材料在高速拉伸过程中的瞬态脆性断裂机制——从应变集中区域出现到裂纹萌生、扩展直至最终脆断的全过程，为研究复合材料的动态失效行为提供时间分辨的实验数据。

### 6.3 橡胶与高分子材料

橡胶材料属于超弹性体，应力-应变曲线呈高度非线性，断裂伸长率可达300%-800%。传统应变片和引伸计的量程远不能满足橡胶大变形测量的需求。

DIC的非接触、大量程特性使其成为橡胶材料力学测试的理想工具。通过DIC全场应变测量，可以精确获取橡胶拉伸过程中的应力-应变曲线（基于载荷和DIC位移数据计算），识别应变集中区域（通常出现在夹具附近或材料缺陷处），并追踪裂纹在橡胶材料中的扩展路径。

对于橡胶-金属复合密封件、橡胶减震器等工程产品，DIC可以测量产品在实际工况下的全场变形，验证产品设计的合理性。

### 6.4 混凝土与土木工程材料

混凝土是一种典型的准脆性非均质材料，其压缩破坏过程涉及微裂纹萌生、扩展、局部化和宏观断裂的复杂演化。DIC在混凝土单轴压缩试验中可以完整记录全场应变场演化，识别应变集中区域（对应微裂纹萌生位置），追踪剪切带的形成和发展过程。

多相机同步方案（多个XTDIC测量头组合）可以实现圆柱体试件360°全周测量，解决曲率表面单视角测量盲区的问题。

### 6.5 高温材料测试

高温环境下的材料力学性能测试是航空航天、冶金、新能源等领域的关键需求。DIC通过蓝/紫外光照明、光学滤波、气刀降温等技术手段，克服热辐射和热雾干扰，在300℃至2300℃的温度范围内稳定获取全场应变数据。

典型应用包括：航空发动机涡轮叶片用高温合金的蠕变试验、陶瓷基复合材料的高温拉伸试验、碳/碳复合材料的超高温（2300℃）双向加载试验。

## 7. XTDIC系统技术方案

### 7.1 产品线配置

**XTDIC-CONST-SD系列**：标准配置，230万至500万像素，帧率163至1500fps，应变精度50με。适用于大多数材料常规力学测试，包括金属拉伸、复合材料压缩、混凝土压缩等准静态或低速动态试验。

**XTDIC-CONST-HR系列**：高分辨率配置，最高2500万像素，帧率30至42fps，应变精度20με。高分辨率图像可以捕捉更细密的应变场细节，适用于研究应变局部化、剪切带精细结构、微观损伤演化等对空间分辨率要求较高的场景。

**XTDIC-CONST-HS系列**：超高速配置，400万像素，帧率超过10万fps，应变精度50με。适用于霍普金森杆冲击试验、高速拉伸瞬态断裂、爆炸冲击等微秒级瞬态过程的测量。

**XTDIC-SPARK系列**：三维高速测量系统，支持多品牌高速相机直接控制，超100万fps，6DoF轨迹姿态测量。适用于高速跟踪测量和极端试验条件下的非接触全场动态应变测量。

**XTDIC-VG系列**：视频引伸计，单相机2.5D/双目3D测量，分辨力0.1μm，精度等级0.2级至0.5级，满足JJG 762/ISO-9513/ASTM-E83标准。适用于需要引伸计级别精度但希望避免接触式安装的场景。

### 7.2 通用技术指标

| 参数 | 指标 |
|------|------|
| 应变测量范围 | 0.005%–2000%以上 |
| 位移测量精度 | ≤0.01像素 |
| 应变精度 | 20–50με（视型号而定） |
| 测量幅面 | 50mm–10m（可调） |
| 相机同步 | 1–8相机同步采集 |
| 数据接口 | 实时UDP输出，支持试验机同步 |
| 工作温度 | 常温型/高温型（配冷却装置） |

## 8. 实验设计与数据处理

### 8.1 散斑制备

散斑质量是决定DIC测量精度的首要因素。不同材料和应用场景需要不同的散斑制备方案：

**金属材料**：常用喷涂法——先喷涂白色底漆，再喷涂黑色散斑。散斑粒径与视场大小的比例建议在1/30至1/50之间。对于高温试验，需使用耐高温散斑材料（如陶瓷基涂料）。

**复合材料**：碳纤维复合材料表面本身具有编织纹理，有时可直接利用自然纹理进行DIC计算。但为提高匹配可靠性，通常仍建议制备人工散斑。

**橡胶材料**：橡胶表面通常为黑色，可直接喷涂白色散斑。由于橡胶变形量大，散斑材料需要具有良好的延展性，避免在拉伸过程中脱落或开裂。

**混凝土材料**：混凝土表面粗糙且非均匀，建议先涂覆薄层白色底漆，再喷涂黑色散斑。散斑粒径建议在0.3mm至1.0mm范围内。

### 8.2 相机配置与标定

相机配置需要根据试验需求确定：

**单相机2D-DIC**：适用于平面试件的面内应变测量，系统简单、成本低，是最基本的DIC配置。

**双目立体视觉3D-DIC**：适用于三维曲面试件或需要离面位移信息的场景，是材料力学测试中最常用的配置。

**多相机同步系统**：适用于360°全周测量、大视场拼接测量或复杂三维形貌的重建。

相机标定是确保测量精度的关键步骤。标定过程需要使用已知尺寸的标定板（如棋盘格或圆点阵列），通过多姿态拍摄获取相机的内外参数和畸变系数。对于高精度测量，标定误差应控制在0.01像素以内。

### 83 数据处理流程

DIC数据处理的标准流程包括：

**图像预处理**：灰度化、去噪、对比度增强，提高散斑图案的识别质量。

**DIC计算**：设置子区大小、步长和相关函数，计算全场位移场。子区大小的选择需要在空间分辨率和计算精度之间取得平衡。

**应变计算**：对位移场进行平滑处理后，通过空间微分计算应变场。常用的平滑方法包括局部最小二乘拟合和高斯滤波。

**结果提取**：从全场数据中提取应力-应变曲线、应变集中系数、主应变方向、裂纹扩展路径等特征信息。

**可视化**：以应变云图、等值线图、位移矢量图等形式呈现测量结果。

## 9. 行业标准与规范

DIC技术在材料测试领域的应用需要遵循相关行业标准：

**ASTM E8/E8M**：金属材料拉伸试验的标准试验方法，规定了金属材料在10-38℃环境温度下的拉伸性能测试要求。DIC测量结果需要与标准方法进行对比验证。

**ASTM D3039**：聚合物基复合材料拉伸性能的标准试验方法，适用于纤维增强复合材料的拉伸性能测试。

**ASTM D638**：塑料拉伸性能的标准试验方法，适用于各类塑料和高分子材料的拉伸测试。

**ASTM D3518**：聚合物基复合材料面内剪切响应的标准试验方法，常采用±45°层合板拉伸试验，DIC可以测量全场剪切应变分布。

**ISO 527**：塑料拉伸性能的测定，与ASTM D638类似，是国际标准版本。

**JJG 762**：引伸计检定规程，XTDIC-VG视频引伸计满足该规程0.5级标准（60/120型可达0.2级）。

**GB/T 228**：金属材料拉伸试验的国家标准，与ASTM E8对应。

DIC测量结果与上述标准方法的对比验证数据（如应变片误差<20με、引伸计偏差<3.5%）表明，DIC技术已具备在标准化测试中替代或补充传统方法的能力。

## 10. 国产DIC在材料测试领域的发展

### 10.1 技术成熟度

以XTDIC为代表的国产DIC系统在材料测试领域已达到较高的技术成熟度。从应变测量精度（20-50με）到三维重建算法的稳定性，从软件工作流的完善程度到多相机同步系统的可靠性，国产设备在常规材料力学测试中已可完全替代进口产品。

国产设备的突出优势在于产品线的完整性——从标准静态测量到超高速动态测量，从常温到超高温，从宏观到微观，覆盖了材料测试的主要应用场景。在价格和服务响应方面，国产设备对国内用户更为友好。

### 10.2 应用拓展

DIC在材料测试领域的应用正从科研机构向企业质检和生产线在线检测拓展。部分材料检测实验室已将DIC纳入标准测试流程，作为传统应变片和引伸计的补充或替代手段。在航空航天、汽车、新能源等行业，DIC开始被用于材料入库检验和产品质量控制。

### 10.3 发展方向

国产DIC在材料测试领域的未来发展可能集中在：更高分辨率相机与更高效的DIC算法集成，提升应变场的空间分辨率；DIC与红外热成像、声发射等多模态传感技术的融合测量，实现力学-热学-损伤的多维度表征；基于深度学习的材料损伤自动识别和应变场智能分析；以及面向工业现场的便携式和自动化DIC检测系统。

## 11. 结语

材料应力-应变测试是工程材料研究和结构安全评估的基石。DIC技术通过将测量维度从"点"提升到"面"，从"接触"升级到"非接触"，从"单量"拓展到"多量"，为材料力学测试带来了方法论层面的深刻变革。

从金属材料的颈缩行为研究到复合材料的损伤演化分析，从橡胶材料的大变形测量到混凝土的应变局部化观测，从室温标准测试到3000℃超高温极端工况，DIC技术正在越来越多的材料测试场景中展现其独特的价值。

随着国产DIC设备在精度、可靠性和产品线完整性方面的持续提升，以及相关行业标准对DIC测量方法的逐步认可，这项技术有望成为材料力学性能测试的标准配置工具，为我国材料科学研究和工程安全评估提供更坚实的数据基础。

---

</details>

---

<a id="english-version"></a>

<details>
<summary><b>🇺🇸 Click to Expand: English Version</b></summary>

# DIC Technology for Material and Structure Stress-Strain Testing: Principles, Applications, and Test Cases

> [!TIP]
> **Language / 请选择语言:** [中文版](#chinese-version)

## Table of Contents

- [1. Introduction: The Central Role of Stress-Strain Testing](#1-introduction-the-central-role-of-stress-strain-testing)
- [2. DIC Principles: From Speckle Images to Full-Field Strain](#2-dic-principles-from-speckle-images-to-full-field-strain)
- [3. Limitations of Traditional Measurement Methods](#3-limitations-of-traditional-measurement-methods)
- [4. Core Capabilities of DIC in Stress-Strain Testing](#4-core-capabilities-of-dic-in-stress-strain-testing)
- [5. Accuracy Validation: DIC vs. Strain Gauge Comparison Data](#5-accuracy-validation-dic-vs-strain-gauge-comparison-data)
- [6. Typical Application Scenarios and Test Cases](#6-typical-application-scenarios-and-test-cases)
- [7. XTDIC System Technical Solutions](#7-xtdic-system-technical-solutions)
- [8. Experimental Design and Data Processing](#8-experimental-design-and-data-processing)
- [9. Industry Standards and Specifications](#9-industry-standards-and-specifications)
- [10. Development of Domestic DIC in Materials Testing](#10-development-of-domestic-dic-in-materials-testing)
- [11. Conclusion](#11-conclusion)

---

## 1. Introduction: The Central Role of Stress-Strain Testing

The stress-strain relationship of materials is the most fundamental data input for engineering design and safety assessment. From the yield strength of aerospace titanium alloys to the elongation at fracture of construction rebar, from the interlaminar fracture toughness of composites to the hyperelastic constitutive parameters of rubber seals, the mechanical property evaluation of nearly all engineering materials relies on stress-strain testing.

Taking metallic materials as an example, a standard tensile test requires determining key parameters including yield strength, tensile strength, elongation at fracture, and reduction of area. These parameters directly determine the allowable stress levels of materials in structures, thereby influencing the safety margin of entire engineering projects. For non-homogeneous or nonlinear materials such as composites, rubber, and concrete, the complexity of stress-strain testing is significantly higher — phenomena such as anisotropy, nonlinear constitutive behavior, large deformation, and strain localization make it difficult for traditional single-point measurement methods to comprehensively characterize material mechanical behavior.

The emergence of Digital Image Correlation (DIC) technology has brought a methodological transformation to material stress-strain testing. Through non-contact optical measurement, DIC can synchronously capture full-field displacement and strain data on specimen surfaces throughout the entire testing process, upgrading traditional "point measurement" to "field measurement" and providing unprecedented data dimensionality and spatial resolution for material mechanical property research.

## 2. DIC Principles: From Speckle Images to Full-Field Strain

### 2.1 Fundamental Principles

Digital Image Correlation (DIC), also known as Digital Speckle Correlation Method, works by matching gray-level information in corresponding regions of two digital images captured before and after deformation to calculate the displacement and strain fields on the object's surface.

The first step in the measurement process is preparing a speckle pattern on the specimen surface — a randomly distributed pattern of black and white spots that serves as the deformation information carrier. The speckle pattern must meet two basic requirements: randomness, ensuring that the gray-level distribution of each sub-region is uniquely identifiable; and appropriate density and particle size, matched to camera resolution and measurement field of view.

During testing, industrial cameras capture speckle images before and after specimen deformation. Using the pre-deformation image as the reference, the DIC algorithm selects a rectangular subset (typically (2M+1)×(2M+1) pixels) centered on each point of interest in the reference image. It then uses search algorithms and correlation functions to find the region in the deformed image with the maximum cross-correlation coefficient, thereby determining the post-deformation position of each point.

### 2.2 Correlation Functions and Sub-Pixel Algorithms

The core of subset matching is the correlation function. Commonly used Normalized Cross-Correlation (NCC) or Sum of Squared Differences (SSD) functions measure the similarity between reference and target subsets. When the correlation function reaches its maximum value, the best match position is identified.

Due to the discreteness of digital images, direct matching can only achieve integer-pixel displacement accuracy. DIC systems employ sub-pixel interpolation algorithms (such as bicubic spline interpolation or quadratic surface fitting) to improve displacement accuracy to 0.01 pixels or better. Combined with camera calibration parameters, sub-pixel displacement accuracy can be converted to micrometer-level actual displacement measurement precision.

### 2.3 3D-DIC and Binocular Stereo Vision

3D-DIC systems are based on binocular stereo vision principles, using two cameras to simultaneously capture specimen surfaces from different angles. Through pre-calibrated camera intrinsic and extrinsic parameters and stereo matching algorithms, the system can reconstruct the 3D spatial coordinates of each matched point on the speckle pattern. By comparing 3D coordinate changes before and after deformation, the system simultaneously obtains in-plane displacement (X, Y directions) and out-of-plane displacement (Z direction), enabling calculation of the complete 3D strain tensor.

### 2.4 From Displacement Field to Strain Field

After obtaining full-field displacement data, DIC software calculates the strain field through spatial differentiation of the displacement field. Since displacement data contains noise, direct differentiation amplifies noise, so the displacement field must first be smoothed (e.g., through least-squares fitting or spline interpolation) before strain calculation. Common strain calculation methods include Lagrangian strain and Green strain, suitable for different deformation magnitude analysis requirements.

## 3. Limitations of Traditional Measurement Methods

### 3.1 Strain Gauges

Strain gauges are the most commonly used deformation measurement tools in material tensile testing, with nominal accuracy reaching 1 με. However, this accuracy is given under ideal laboratory conditions for specific materials and bonding processes. In actual complex working conditions, the effective accuracy of strain gauges may be significantly compromised:

**Single-Point Limitation**: Strain gauges can only measure the average strain in the local area near the bonding point, unable to reflect the spatial distribution of the strain field. For non-homogeneous materials (such as composites, concrete) or situations with stress concentration, single-point data cannot represent the overall deformation state of the specimen.

**Directional Limitation**: A single strain gauge can only measure strain along its sensitive grid direction. To obtain principal strain magnitude and direction, strain rosettes (three strain gauges in different directions) must be bonded, increasing preparation workload.

**Limited Range**: Conventional strain gauges typically measure up to approximately 5% strain. For large-deformation materials like rubber (elongation at break can reach 300%-800%), strain gauges fail long before the material fractures.

**Contact Effects**: Strain gauges require bonding to the specimen surface. For soft materials (such as rubber, biological tissue), the added stiffness of the strain gauge may alter the local stress state, introducing measurement errors.

### 3.2 Extensometers

Extensometers can measure average strain within a gauge length with high accuracy (up to 0.5 με), but they also have inherent problems with contact-based measurement: physical contact with the specimen (clamping or knife-edge contact) may damage soft material surfaces; fixed gauge length prevents flexible adjustment of the measurement area; for large-deformation tests, extensometers must be removed before specimen fracture, preventing recording of the fracture transient process.

### 3.3 Laser Doppler Vibrometers

Laser Doppler vibrometers can achieve non-contact measurement, but are essentially single-point scanning instruments — obtaining full-field data requires point-by-point scanning across the specimen surface, resulting in slow measurement speeds unsuitable for dynamic testing. Additionally, equipment costs are high, and requirements exist for specimen surface reflectivity characteristics.

## 4. Core Capabilities of DIC in Stress-Strain Testing

### 4.1 Full-Field Data: Dimensionality Enhancement from Point to Surface

DIC's most essential advantage lies in elevating measurement dimensionality from "point" to "surface." In a single standard tensile test, DIC can synchronously obtain displacement and strain data for hundreds of thousands to millions of measurement points within the field of view. This increase in data density is not merely a quantitative improvement but represents a qualitative leap — researchers can observe the spatial distribution of strain fields, identify strain concentration regions, and track crack propagation paths, all impossible with traditional methods.

### 4.2 Simultaneous Multi-Physics Measurement

Modern DIC systems can simultaneously resolve multiple mechanical quantities: in-plane displacement (U, V), out-of-plane displacement (W), in-plane strain (ε_xx, ε_yy, ε_xy), principal strains (ε_1, ε_2), principal strain direction angle, thickness reduction rate, and more. These multi-dimensional data support decoupled analysis of complex failure modes, enabling simultaneous evaluation of plastic deformation, necking behavior, and damage evolution.

### 4.3 Full-Process Visualization

DIC presents the deformation process in real-time through displacement contour maps, strain contour maps, and vector fields, achieving "what you see is what you get" experimental analysis. Researchers can visually identify maximum deformation point locations, development of strain concentration regions, and crack initiation and propagation directions during testing, enabling timely adjustment of test plans or focus areas.

### 4.4 Large Strain and Extreme Condition Adaptability

DIC's strain measurement range covers 0.05% to over 2000%, spanning from the elastic stage of metallic materials (strain <0.2%) to the ultra-large deformation of rubber materials (strain >500%), from room temperature to ultra-high temperature environments up to 3000°C, from quasi-static to microsecond-level transient dynamic processes — DIC provides effective full-field strain data across all these conditions.

### 4.5 Finite Element Validation

DIC full-field data provides unprecedented validation capabilities for Finite Element Analysis (FEA). Traditional methods can only compare strain values at limited points, while DIC provides full-field strain distribution contour maps across the entire field of view, enabling point-by-point comparison with FEA calculation results and more comprehensive evaluation of model accuracy and applicability.

## 5. Accuracy Validation: DIC vs. Strain Gauge Comparison Data

DIC measurement accuracy is one of the most critical concerns in engineering applications. Multiple comparison experimental data demonstrate:

In standard metallic material tensile tests, DIC and strain gauge longitudinal strain measurement results show high consistency. Measured data indicates strain differences within 20 με — specific comparison values of 0.085 με, 19.5 με, and 11.3 με, all within the 20 microstrain range. This accuracy level is fully sufficient for engineering applications, since most engineering materials have yield strains in the hundreds to thousands of microstrain range.

In the composites field, ASTM Committee E08 organized multiple aerospace laboratories to conduct fatigue test cross-validation on CFRP bolted joints. Data showed that DIC full-field strain measurement results had errors less than 1.8% compared to traditional strain gauge data, and could provide early warning of micro-crack initiation at bolt hole edges approximately 2000 cycles in advance, demonstrating its engineering applicability.

In high-temperature environments, comparison data between DIC systems and traditional extensometers is equally compelling: elastic stage deviation ≤1.2%, plastic stage deviation ≤2.8%, and critical pre-fracture stage (affected by high-temperature white fog) maximum deviation 3.5%. Full-field displacement measurement standard deviation ≤0.03mm, verifying the reliability of non-contact measurement under extreme conditions.

## 6. Typical Application Scenarios and Test Cases

### 6.1 Metallic Material Tensile Testing

Metallic material tensile testing is the most classic application scenario for stress-strain testing. DIC's value in metal tensile tests extends beyond replacing strain gauges to obtain stress-strain curves — it reveals phenomena unobservable by traditional methods:

**Necking Behavior Research**: After metallic materials reach tensile strength, they enter a localized necking stage where deformation concentrates in the necking region. DIC can precisely record strain distribution in the necking region, necking initiation location, and development process, providing key data for studying material plastic instability behavior.

**Stress Concentration at Pre-drilled Holes**: For metallic specimens with pre-drilled holes (simulating bolt connection holes), DIC can measure strain concentration factors and strain gradients near hole edges, evaluating the influence of stress concentration on material bearing capacity.

**Fracture Transient Recording**: DIC combined with high-speed cameras can record strain field evolution during the instant of metallic specimen fracture, revealing fracture initiation location and crack propagation velocity.

### 6.2 Composite Material Mechanical Characterization

Composite materials (such as Carbon Fiber Reinforced Polymer CFRP, Glass Fiber Reinforced Polymer GFRP) present unique challenges for stress-strain testing due to their anisotropy and multi-phase structure:

**Anisotropic Characterization**: Composite material mechanical properties vary with direction. DIC full-field data can simultaneously obtain strain distributions in different directions, providing abundant experimental data for establishing anisotropic constitutive models.

**Damage Evolution Analysis**: Composite materials undergo multiple damage modes during loading, including matrix cracking, interface debonding, and fiber fracture. DIC identifies damage initiation locations and propagation paths through strain field anomalies (such as local strain mutations and abnormal strain gradients).

**High-Temperature Biaxial Tension**: In aerospace and new energy fields, composite materials must operate in high-temperature environments. DIC, combined with high-temperature test chambers and high-temperature-resistant optical windows, can perform biaxial tensile tests at different temperatures, obtaining continuous variation curves of elastic modulus, Poisson's ratio, and yield strength with temperature, distinguishing between room-temperature fiber-dominated failure and high-temperature matrix-dominated failure mode differences.

**High-Speed Transient Brittle Fracture**: The XTDIC-SPARK system, combined with high-speed cameras, can capture the transient brittle fracture mechanism of composite materials during high-speed tensile processes — the complete process from strain concentration region appearance through crack initiation and propagation to final brittle fracture, providing time-resolved experimental data for studying composite material dynamic failure behavior.

### 6.3 Rubber and Polymer Materials

Rubber materials belong to hyperelastic bodies with highly nonlinear stress-strain curves and elongation at break reaching 300%-800%. Traditional strain gauges and extensometers cannot meet the range requirements for rubber large-deformation measurement.

DIC's non-contact, large-range characteristics make it an ideal tool for rubber material mechanical testing. Through DIC full-field strain measurement, the stress-strain curve of rubber during tension can be precisely obtained (calculated from load and DIC displacement data), strain concentration regions identified (usually appearing near fixtures or material defects), and crack propagation paths in rubber materials tracked.

For engineering products such as rubber-metal composite seals and rubber dampers, DIC can measure full-field deformation of products under actual working conditions, verifying product design rationality.

### 6.4 Concrete and Civil Engineering Materials

Concrete is a typical quasi-brittle non-homogeneous material whose compressive failure process involves complex evolution from micro-crack initiation, propagation, localization, to macro-fracture. DIC in concrete uniaxial compression tests can completely record full-field strain field evolution, identify strain concentration regions (corresponding to micro-crack initiation locations), and track shear band formation and development processes.

Multi-camera synchronization solutions (combining multiple XTDIC measurement heads) can achieve 360° full-circumference measurement of cylindrical specimens, solving the problem of single-view measurement blind spots on curved surfaces.

### 6.5 High-Temperature Material Testing

Mechanical property testing of materials in high-temperature environments is a critical requirement in aerospace, metallurgy, and new energy fields. DIC, through blue/UV illumination, optical filtering, air-knife cooling, and other technical means, overcomes thermal radiation and thermal fog interference, stably obtaining full-field strain data in temperature ranges from 300°C to 2300°C.

Typical applications include: creep testing of high-temperature alloys for aerospace turbine blades, high-temperature tensile testing of ceramic matrix composites, and ultra-high-temperature (2300°C) biaxial loading tests of carbon/carbon composites.

## 7. XTDIC System Technical Solutions

### 7.1 Product Line Configuration

**XTDIC-CONST-SD Series**: Standard configuration, 2.3 to 5 megapixels, 163 to 1500 fps, 50 με strain accuracy. Suitable for most conventional material mechanical tests, including metal tension, composite compression, concrete compression, and other quasi-static or low-speed dynamic tests.

**XTDIC-CONST-HR Series**: High-resolution configuration, up to 25 megapixels, 30 to 42 fps, 20 με strain accuracy. High-resolution images capture finer strain field details, suitable for studying strain localization, fine shear band structures, microscopic damage evolution, and other scenarios requiring high spatial resolution.

**XTDIC-CONST-HS Series**: Ultra-high-speed configuration, 4 megapixels, exceeding 100,000 fps, 50 με strain accuracy. Suitable for Hopkinson bar impact tests, high-speed tensile transient fracture, blast impact, and other microsecond-level transient process measurements.

**XTDIC-SPARK Series**: Three-dimensional high-speed measurement system, supporting direct control of multi-brand high-speed cameras, exceeding 1,000,000 fps, 6DoF trajectory and attitude measurement. Suitable for high-speed tracking measurement and non-contact full-field dynamic strain measurement under extreme test conditions.

**XTDIC-VG Series**: Video extensometer, single-camera 2.5D / binocular 3D measurement, 0.1 μm resolution, 0.2 to 0.5 accuracy class, meeting JJG 762 / ISO-9513 / ASTM-E83 standards. Suitable for scenarios requiring extensometer-level accuracy but wishing to avoid contact-based installation.

### 7.2 Universal Technical Specifications

| Parameter | Specification |
|-----------|--------------|
| Strain Measurement Range | 0.005%–2000%+ |
| Displacement Measurement Precision | ≤0.01 pixels |
| Strain Accuracy | 20–50 με (model dependent) |
| Measurement Field of View | 50mm–10m (adjustable) |
| Camera Synchronization | 1–8 camera synchronous acquisition |
| Data Interface | Real-time UDP output, supports testing machine synchronization |
| Operating Temperature | Room temperature type / high-temperature type (with cooling system) |

## 8. Experimental Design and Data Processing

### 8.1 Speckle Preparation

Speckle quality is the primary factor determining DIC measurement accuracy. Different materials and application scenarios require different speckle preparation approaches:

**Metallic Materials**: Spray coating is commonly used — first spray white primer, then spray black speckles. The ratio of speckle particle size to field of view is recommended between 1/30 and 1/50. For high-temperature tests, high-temperature-resistant speckle materials (such as ceramic-based coatings) are required.

**Composite Materials**: Carbon fiber composite surfaces have inherent weave textures that can sometimes be used directly for DIC computation. However, to improve matching reliability, artificial speckle preparation is generally still recommended.

**Rubber Materials**: Rubber surfaces are typically black, allowing direct white speckle spraying. Due to large rubber deformation, speckle materials must have good ductility to prevent detachment or cracking during stretching.

**Concrete Materials**: Concrete surfaces are rough and non-uniform. It is recommended to first apply a thin layer of white primer, then spray black speckles. Speckle particle size in the 0.3mm to 1.0mm range is recommended.

### 8.2 Camera Configuration and Calibration

Camera configuration should be determined based on test requirements:

**Single-Camera 2D-DIC**: Suitable for in-plane strain measurement of flat specimens. The system is simple and cost-effective, representing the most basic DIC configuration.

**Binocular Stereo Vision 3D-DIC**: Suitable for 3D curved specimens or scenarios requiring out-of-plane displacement information. This is the most commonly used configuration for material mechanical testing.

**Multi-Camera Synchronization Systems**: Suitable for 360° full-circumference measurement, large field-of-view stitching measurement, or complex 3D topography reconstruction.

Camera calibration is a critical step ensuring measurement accuracy. The calibration process requires calibration targets of known dimensions (such as checkerboard or dot array patterns), capturing images from multiple orientations to obtain camera intrinsic parameters, extrinsic parameters, and distortion coefficients. For high-precision measurement, calibration errors should be controlled within 0.01 pixels.

### 8.3 Data Processing Workflow

The standard DIC data processing workflow includes:

**Image Preprocessing**: Grayscale conversion, denoising, and contrast enhancement to improve speckle pattern recognition quality.

**DIC Computation**: Setting subset size, step size, and correlation functions to compute full-field displacement fields. Subset size selection requires balancing spatial resolution against computational precision.

**Strain Computation**: After smoothing the displacement field, calculating the strain field through spatial differentiation. Common smoothing methods include local least-squares fitting and Gaussian filtering.

**Result Extraction**: Extracting characteristic information from full-field data, including stress-strain curves, strain concentration factors, principal strain directions, and crack propagation paths.

**Visualization**: Presenting measurement results as strain contour maps, isocontour plots, and displacement vector diagrams.

## 9. Industry Standards and Specifications

DIC technology applications in materials testing must follow relevant industry standards:

**ASTM E8/E8M**: Standard Test Methods for Tension Testing of Metallic Materials, specifying tensile property testing requirements for metallic materials at ambient temperatures of 10-38°C. DIC measurement results require comparison and validation against standard methods.

**ASTM D3039**: Standard Test Method for Tensile Properties of Polymer Matrix Composite Materials, applicable to tensile property testing of fiber-reinforced composites.

**ASTM D638**: Standard Test Method for Tensile Properties of Plastics, applicable to tensile testing of various plastics and polymer materials.

**ASTM D3518**: Standard Test Method for In-Plane Shear Response of Polymer Matrix Composite Materials by Tensile Test of a ±45° Laminate, commonly using ±45° laminate tensile tests where DIC can measure full-field shear strain distribution.

**ISO 527**: Plastics — Determination of Tensile Properties, similar to ASTM D638, serving as the international standard version.

**JJG 762**: Extensometer Verification Regulation. The XTDIC-VG video extensometer meets the 0.5 class standard of this regulation (60/120 models can achieve 0.2 class).

**GB/T 228**: Chinese National Standard for Metallic Material Tensile Testing, corresponding to ASTM E8.

Comparison validation data between DIC measurement results and the above standard methods (such as strain gauge error <20 με, extensometer deviation <3.5%) indicates that DIC technology has achieved the capability to replace or supplement traditional methods in standardized testing.

## 10. Development of Domestic DIC in Materials Testing

### 10.1 Technology Maturity

Domestic DIC systems represented by XTDIC have achieved high technology maturity in the materials testing field. From strain measurement accuracy (20-50 με) to 3D reconstruction algorithm stability, from software workflow completeness to multi-camera synchronization system reliability, domestic equipment can fully replace imported products in conventional material mechanical testing.

Domestic equipment's outstanding advantages lie in product line completeness — from standard static measurement to ultra-high-speed dynamic measurement, from room temperature to ultra-high temperature, from macro to micro scale, covering the main application scenarios in materials testing. In pricing and service response, domestic equipment is more accessible for domestic users.

### 10.2 Application Expansion

DIC applications in materials testing are expanding from research institutions to enterprise quality control and production-line online inspection. Some materials testing laboratories have incorporated DIC into standard testing workflows as a supplement or replacement for traditional strain gauges and extensometers. In aerospace, automotive, new energy, and other industries, DIC has begun being used for material incoming inspection and product quality control.

### 10.3 Development Directions

Future development of domestic DIC in materials testing may focus on: integration of higher-resolution cameras with more efficient DIC algorithms to improve strain field spatial resolution; fused measurement combining DIC with infrared thermography, acoustic emission, and other multi-modal sensing technologies to achieve mechanical-thermal-damage multi-dimensional characterization; deep learning-based automatic material damage identification and intelligent strain field analysis; and portable and automated DIC inspection systems for industrial field deployment.

## 11. Conclusion

Material stress-strain testing is the cornerstone of engineering material research and structural safety assessment. DIC technology, by elevating measurement dimensionality from "point" to "surface," upgrading from "contact" to "non-contact," and expanding from "single quantity" to "multi-quantity," has brought a profound methodological transformation to material mechanical testing.

From necking behavior research in metallic materials to damage evolution analysis in composites, from large-deformation measurement of rubber materials to strain localization observation in concrete, from room-temperature standard testing to extreme conditions at 3000°C — DIC technology is demonstrating its unique value in an increasing number of material testing scenarios.

As domestic DIC equipment continues to improve in accuracy, reliability, and product line completeness, and as relevant industry standards progressively recognize DIC measurement methods, this technology is expected to become a standard configuration tool for material mechanical property testing, providing a more solid data foundation for China's materials science research and engineering safety assessment.

---

</details>

---

*Published in DIC-System-Benchmark*  
*Reference: XTOP3D material testing application documentation*
