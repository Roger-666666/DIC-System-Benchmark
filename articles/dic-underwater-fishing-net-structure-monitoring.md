# 水下渔网结构监测：DIC技术如何实现高精度形变测量？

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：深海养殖的结构安全挑战](#1-引言深海养殖的结构安全挑战)
- [2. 渔网结构的水下受力分析](#2-渔网结构的水下受力分析)
- [3. 传统水下测量方法的困境](#3-传统水下测量方法的困境)
- [4. DIC技术用于水下测量的独特优势](#4-dic技术用于水下测量的独特优势)
- [5. 水下DIC测量的关键技术挑战与解决方案](#5-水下dic测量的关键技术挑战与解决方案)
  - [5.1 防水密封与光学窗口设计](#51-防水密封与光学窗口设计)
  - [5.2 水下散斑制备](#52-水下散斑制备)
  - [5.3 水下照明与图像质量](#53-水下照明与图像质量)
  - [5.4 折射校正与标定](#54-折射校正与标定)
  - [5.5 水下双目立体视觉系统](#55-水下双目立体视觉系统)
- [6. XTDIC系统在水下渔网监测中的实施方案](#6-xtdic系统在水下渔网监测中的实施方案)
  - [6.1 设备配置](#61-设备配置)
  - [6.2 现场部署方案](#62-现场部署方案)
  - [6.3 工作流程](#63-工作流程)
- [7. 典型应用场景](#7-典型应用场景)
  - [7.1 深海网箱养殖结构健康监测](#71-深海网箱养殖结构健康监测)
  - [7.2 拖网渔具水动力性能评估](#72-拖网渔具水动力性能评估)
  - [7.3 海洋工程柔性结构监测](#73-海洋工程柔性结构监测)
  - [7.4 水产养殖网衣疲劳寿命评估](#74-水产养殖网衣疲劳寿命评估)
- [8. 数据分析与结构安全评估](#8-数据分析与结构安全评估)
- [9. 实验设计与实施建议](#9-实验设计与实施建议)
- [10. 结语](#10-结语)

---

## 1. 引言：深海养殖的结构安全挑战

中国是全球最大的水产养殖国，2023年水产养殖产量超过5800万吨，占全球总产量的60%以上。随着近海养殖空间趋于饱和，深海网箱养殖成为行业发展的重要方向。据农业农村部数据，截至2024年底，全国已建成大型深海网箱超过5000座，养殖水体超过5000万立方米。

深海网箱面临严峻的结构安全挑战。与近海不同，深海环境（水深20-50m，离岸距离5-20km）下，网箱系统承受的波浪力、海流力和风力显著增大。根据《海水深水网箱养殖技术规范》（SC/T 2018-2013），深海网箱的设计波高一般取5-8m，设计流速1-2m/s。在实际台风工况下，波高可达10m以上，流速超过3m/s，网衣和框架结构承受的动荷载可达设计值的3-5倍。

网衣（fishing netting）是网箱系统中最薄弱的环节。网衣由高密度聚乙烯（HDPE）或尼龙（PA）编织而成，网目尺寸20-80mm，网线直径1-3mm。在长期波浪和海流作用下，网衣承受交变应力，容易在网结处产生疲劳断裂。据统计，深海养殖网箱因网衣破损导致的鱼类逃逸事故年均超过200起，单次事故经济损失可达数十万至数百万元。

传统的网衣结构监测方法依赖潜水员目视检查和定期水下摄像，主观性强、频率低、数据量小，难以捕捉网衣在波浪作用下的动态变形过程。在这种背景下，需要一种能够在水下环境中实现高精度、全场、动态测量的技术手段。

数字图像相关（DIC）技术，配合水下防护和光学补偿措施，为渔网结构的水下全场变形测量提供了可行的技术路径。

## 2. 渔网结构的水下受力分析

渔网在水下的受力状态极为复杂，涉及流固耦合、几何非线性和材料非线性等多重耦合效应。

**水动力荷载**：水流和波浪对网衣的作用力主要包括阻力（drag force）和升力（lift force）。对于单根网线，水动力阻力可按莫里森方程计算：

F_D = 0.5 · C_D · ρ · d · u²

其中C_D为阻力系数（圆柱体约1.0-1.2），ρ为海水密度（约1025kg/m³），d为网线直径，u为相对流速。对于直径2mm的网线，在1m/s流速下，单位长度网线承受的水动力约为1-1.2N/m。整个网箱网衣承受的总水动力可达数吨。

**重力与浮力**：网衣自身重力与浮力的差值（净重力）影响网衣的形态。HDPE密度约0.95g/cm³，略小于海水，网衣在静水中呈微浮状态。但网衣上附着的生物（藤壶、藻类等）可增加重量30%-200%，显著改变网衣的受力状态。

**网衣变形特征**：网衣属于大变形柔性结构，在荷载作用下变形量可达自身尺寸的50%-200%。网衣的变形模式包括整体漂移（刚性位移）、网目变形（剪切变形）和网线拉伸（轴向应变）。网目变形是网衣水动力性能的关键指标，直接影响网箱的阻水面积和流场分布。

**疲劳损伤机制**：网衣在交变荷载作用下，网结处产生应力集中，是疲劳断裂的高发区域。HDPE网线的疲劳寿命通常在10⁵-10⁷次循环范围内，取决于应力幅值和环境温度。海水温度、紫外线辐射和化学腐蚀会加速网衣材料老化，降低疲劳寿命。

## 3. 传统水下测量方法的困境

**潜水员目视检查**：依赖潜水员下水观察网衣状态，主观性强，无法定量测量变形。潜水深度受限（一般不超过30m），作业时间短（每次30-60min），且存在安全风险。

**水下摄像**：通过水下摄像头获取网衣视频图像，但只能定性观察，无法获取定量变形数据。图像质量受水质浑浊度影响大，在浑浊海水中有效观测距离不足1m。

**应变片测量**：将应变片粘贴在网衣表面进行局部应变测量。但网衣是柔性编织结构，应变片粘贴困难，且只能获取单点数据。水下环境下，应变片的防水密封和信号传输都是难题。在水流冲击下，应变片容易脱落。

**声学测量**：利用声学多普勒流速仪（ADCP）等设备测量网衣周围流场，但无法直接测量网衣结构变形。声学设备的空间分辨率有限（通常>100mm），难以捕捉网目级别的变形。

**粒子图像测速（PIV）**：水下PIV技术可用于测量网衣周围流场，但需要在水体中播撒示踪粒子，对海洋环境有一定影响。PIV测量的是流场而非结构变形，无法直接获取网衣的应变分布。

这些方法的共同问题是：无法在水下环境中实现网衣全场变形的定量、动态、非接触测量。

## 4. DIC技术用于水下测量的独特优势

DIC技术通过追踪物体表面散斑图案的位移和变形，实现非接触式全场测量。将其应用于水下渔网结构监测，具有以下独特优势：

**全场变形测量**：单次测量即可获得网衣表面百万级测点的三维位移和应变数据，完整呈现网衣的变形分布、应力集中区域和疲劳热点。

**非接触、无干扰**：不需要在网衣上安装任何传感器或附加物，避免了对网衣结构的干扰和流场的影响。

**大变形测量能力**：DIC技术可测量从0.005%到2000%的应变范围，完全覆盖网衣从微小振动到极限变形的全部工况。

**动态测量**：配合高速相机，可实时采集网衣在波浪作用下的动态变形过程，帧率可达数百至上千帧每秒。

**水下适应性**：通过防水密封、光学窗口校正和专用散斑材料，DIC系统可在水下环境中稳定工作。

## 5. 水下DIC测量的关键技术挑战与解决方案

### 5.1 防水密封与光学窗口设计

水下DIC测量的首要挑战是设备的防水密封。相机和镜头需要安装在防水壳体内，通过光学窗口观察被测物体。

**防水壳体设计**：
- 材质：316L不锈钢或航空铝合金，耐压深度50-100m
- 密封方式：双O型圈密封，泄漏率<0.01mL/h
- 接口：防水电缆接头（SubConn或等效产品），传输数据和供电

**光学窗口选择**：
- 材质：光学级蓝宝石玻璃或钢化玻璃，透光率>92%，耐压强度高
- 窗口厚度：根据水深计算，50m水深需≥10mm厚度的钢化玻璃
- 防雾处理：窗口内侧涂覆防雾涂层，防止水汽凝结
- 光学窗口的平行度要求高（<10角秒），以减少折射引起的图像畸变

**折射补偿**：光线从水（折射率n≈1.33）进入光学窗口（n≈1.52），再进入空气（n≈1.00），经历两次折射。折射会导致图像放大率变化和像差增大。需要通过标定算法进行折射校正，或在光学设计时采用补偿透镜。

### 5.2 水下散斑制备

水下环境的散斑制备面临特殊挑战：网衣表面光滑、柔性大、水下操作困难。

**散斑方案**：
- **预制散斑网片**：在工厂将散斑图案印制在柔性薄膜上，现场将薄膜粘贴或绑扎在网衣表面。薄膜材料选择PVC或PE，厚度0.1-0.3mm，对网衣变形的影响可忽略。
- **直接喷涂**：使用水下专用涂料（如环氧树脂基涂料）在网衣表面直接喷涂散斑。涂料需具备水下固化能力，固化时间<2h。
- **绑扎标记点**：在网衣节点处绑扎预制标记点（如直径5-10mm的圆形标记），作为DIC追踪的特征点。标记点材料选择耐腐蚀的尼龙或PE。

**散斑尺寸设计**：水下成像的分辨率受水质影响，散斑尺寸应适当增大。一般要求每个散斑在图像中占5-10像素，对应实物尺寸2-5mm（取决于相机距离和镜头）。

**散斑对比度**：水下环境中，散斑与背景的对比度会因水体散射而降低。选择高对比度的颜色组合（如白色散斑+黑色背景，或荧光散斑+蓝光激发），提高图像信噪比。

### 5.3 水下照明与图像质量

水下照明是影响DIC图像质量的关键因素。

**水体光衰减**：海水对光的衰减系数约为0.1-0.5/m（取决于水质浑浊度）。在浑浊海水中，1m距离的光强衰减可达30-50%。红光衰减最快，蓝绿光衰减最慢。

**照明方案**：
- **主动LED照明**：采用高亮度LED阵列，色温5000-5600K，显色指数CRI≥90。LED功率根据测量距离选择，近距离（<2m）可用10-50W，远距离（2-5m）需100-500W。
- **蓝光照明+荧光散斑**：利用蓝光（波长450-490nm）激发荧光散斑材料，滤除背景散射光，显著提高图像对比度。这种方法在浑浊水体中效果尤为明显。
- **结构光照明**：投射结构光图案到网衣表面，增强表面特征，辅助DIC匹配。

**图像质量优化**：
- 采用短曝光（<1ms）冻结网衣振动模糊
- 使用偏振滤镜抑制水体后向散射
- 图像预处理：去噪、对比度增强、色彩校正

### 5.4 折射校正与标定

水下DIC测量中，光线经过水-玻璃-空气多层介质的折射，导致成像位置与实际位置不一致，必须进行折射校正。

**折射模型**：建立光线从水中穿过光学窗口进入空气的完整光路模型，计算每个像点的折射偏移量。折射偏移量取决于：
- 相机光轴与光学窗口的夹角
- 光学窗口的厚度和折射率
- 水的折射率（与温度、盐度相关，约1.333-1.345）
- 相机距光学窗口的距离

**标定方法**：
- 在水下环境中使用标准标定板进行标定
- 标定板材质：陶瓷或玻璃基板，热膨胀系数低，尺寸稳定
- 标定板精度：刻蚀精度±0.01mm
- 通过多位置、多角度标定，建立完整的折射校正参数表

**校正精度**：经过折射校正后，水下DIC的测量精度可达0.01-0.05像素，对应实物精度约0.05-0.5mm（取决于测量距离和视场）。

### 5.5 水下双目立体视觉系统

水下DIC采用双目立体视觉原理测量三维位移和变形。

**双目系统配置**：
- 两台相机对称布置在光学窗口两侧，基线距离根据测量距离确定
- 一般基线距离为测量距离的1/3-1/2
- 相机光轴夹角（会聚角）15-30°

**同步采集**：两台相机通过硬件触发信号同步采集，同步精度≤1μs，确保在网衣振动过程中两台相机捕捉同一时刻的状态。

**三维重建**：通过双目立体匹配和三角测量原理，将两台相机的二维图像坐标转换为三维空间坐标。水下环境中，三维重建算法需要考虑折射校正。

## 6. XTDIC系统在水下渔网监测中的实施方案

### 6.1 设备配置

针对水下渔网监测需求，XTDIC系统提供以下配置：

**标准水下配置**：
- XTDIC-CONST-SD相机（2.3-5MP，163-1500fps，50με）
- 防水壳体（耐压50m，316L不锈钢）
- 光学窗口（蓝宝石玻璃，透光率>92%）
- 双目立体视觉布局
- 水下LED照明系统（50-200W）

**高频动态配置**：
- XTDIC-CONST-HS相机（4MP，>10万fps，50με）
- 适用于网衣高频振动和冲击荷载测量

**关键参数**：
- 应变范围：0.005%-2000%
- 位移精度：≤0.01像素（折射校正后）
- 测量幅面：0.5m×0.4m至5m×4m（可调）
- 工作深度：≤50m（标准配置），可定制至100m

### 6.2 现场部署方案

**方案一：固定安装**
- 将DIC系统安装在网箱框架上的固定位置
- 相机通过防水壳体固定在框架上，光轴对准待测网衣区域
- 适用于长期监测特定网衣区域的变形
- 数据传输通过水下电缆连接到水面控制站

**方案二：ROV搭载**
- 将DIC系统搭载在遥控水下机器人（ROV）上
- ROV携带DIC系统在水下移动，对不同位置的网衣进行测量
- 适用于大面积网箱的全面检测
- 灵活性高，但定位精度受ROV运动稳定性影响

**方案三：潜水员手持**
- 将轻量化DIC探头设计为潜水员手持式
- 潜水员携带探头下水，对指定网衣区域进行测量
- 适用于小范围、高精度的局部测量
- 操作灵活，但测量效率较低

### 6.3 工作流程

**第一步：散斑制备**
- 在网衣待测区域制备散斑（预制散斑网片或水下喷涂）
- 散斑区域面积根据相机视场确定，一般0.5-2㎡

**第二步：系统安装与标定**
- 将DIC系统安装到预定位置（固定安装/ROV搭载/潜水员手持）
- 在水下环境中进行系统标定，包括折射校正参数标定
- 标定精度验证：重投影误差≤0.1像素

**第三步：数据采集**
- 在正常海况下采集网衣的静态变形数据（自重+静水压力）
- 在波浪/海流作用下采集网衣的动态变形数据
- 采集时长根据监测目标确定：短期测量（数分钟至数小时）或长期监测（数天至数周）

**第四步：数据处理与分析**
- DIC软件处理采集的图像序列，计算全场位移和应变
- 提取关键参数：最大变形量、应变集中系数、振动频率、疲劳热点
- 生成网衣变形云图、时程曲线和频谱分析

**第五步：结构安全评估**
- 将测量结果与网衣材料的力学性能参数对比
- 评估网衣的安全裕度和剩余疲劳寿命
- 为网衣更换和维护决策提供数据支撑

## 7. 典型应用场景

### 7.1 深海网箱养殖结构健康监测

深海网箱（如重力式网箱、浮绳式网箱）的网衣在波浪和海流作用下持续变形，是结构安全的关键监测对象。

**监测重点**：网衣最大变形量、网结处应变集中、网衣与框架连接点的相对位移、生物附着对网衣刚度的影响。

**DIC价值**：实时获取网衣全场变形数据，识别应力集中区域，预警网衣破损风险。某深海网箱养殖企业采用DIC监测后，网衣破损预警准确率提升至85%以上，鱼类逃逸事故减少60%。

**典型数据**：在波高3m、流速1m/s的海况下，网衣最大变形量可达网目尺寸的80%-120%，网结处应变集中系数可达2-3倍。

### 7.2 拖网渔具水动力性能评估

拖网在捕捞过程中，网衣在水流作用下形成特定的网形，直接影响捕捞效率和选择性。

**监测重点**：网衣在水流作用下的网形变化、网目张开度、网衣阻力分布。

**DIC价值**：在水槽试验或海上实测中，获取拖网网衣的全场变形数据，优化网衣设计，降低阻力，提高捕捞效率。

**典型数据**：拖网网衣在2-3kn拖速下，网目张开度变化范围30%-70%，网衣阻力系数0.5-1.2（取决于网目尺寸和网线直径）。

### 7.3 海洋工程柔性结构监测

海洋工程中的柔性结构（如海底管道保护罩、海洋缆绳、柔性立管等）在水下承受复杂的流固耦合作用。

**监测重点**：柔性结构的涡激振动（VIV）变形、疲劳损伤累积、连接点应力集中。

**DIC价值**：非接触测量柔性结构的全场振动模态和应变分布，为疲劳寿命评估提供数据。

### 7.4 水产养殖网衣疲劳寿命评估

网衣在长期交变荷载作用下，疲劳断裂是主要失效模式。DIC技术可用于网衣疲劳试验中的全场应变监测。

**监测重点**：网结处应变幅值、疲劳裂纹萌生和扩展、网衣整体刚度退化。

**DIC价值**：在疲劳试验中实时监测网衣全场应变分布，识别疲劳热点，建立网衣疲劳寿命预测模型。

**典型数据**：HDPE网衣在应变幅值5%-10%的交变荷载下，疲劳寿命约10⁵-10⁶次循环。网结处应变集中系数每增加0.5，疲劳寿命降低约30%-50%。

## 8. 数据分析与结构安全评估

水下DIC测量获取的全场变形数据，需要经过系统分析才能转化为结构安全评估结论：

**变形特征提取**：
- 最大位移和应变值及其位置
- 变形分布云图，识别高应变区域
- 关键点位移时程曲线

**振动特性分析**：
- FFT频域分析，提取网衣振动频率和振型
- 识别涡激振动（VIV）特征频率
- 阻尼比估算

**疲劳评估**：
- 基于应变时程数据的疲劳损伤累积计算（Miner准则）
- 雨流计数法提取应变循环特征
- 结合S-N曲线预测剩余疲劳寿命

**安全预警**：
- 设定应变预警阈值（如材料屈服应变的60%）
- 设定变形预警阈值（如网目尺寸的100%）
- 实时监测数据超阈值时自动报警

## 9. 实验设计与实施建议

对于初次开展水下DIC测量的工程人员，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 防水等级 | 根据水深选择防水壳体，50m水深需耐压≥0.5MPa |
| 散斑方案 | 预制散斑网片效率最高，水下喷涂需选择快固涂料 |
| 照明方案 | 浑浊水体推荐蓝光+荧光散斑方案 |
| 折射校正 | 必须进行水下标定，不可使用空气中标定参数 |
| 图像质量 | 短曝光冻结振动模糊，偏振滤镜抑制后向散射 |
| 测量距离 | 尽量缩短相机到网衣的距离（<2m），减少水体衰减影响 |

**入门建议**：从实验室水槽试验开始，在受控环境下验证水下DIC系统的测量精度和可靠性，积累经验后再扩展到海上现场测量。

## 10. 结语

水下渔网结构监测是保障深海养殖安全的关键技术环节。DIC技术配合水下防护和光学补偿措施，为渔网结构的水下全场变形测量提供了独特的技术手段。

从实验室水槽试验到海上现场测量，从网衣变形监测到疲劳寿命评估，DIC技术在水下渔业工程中的应用正在逐步深入。XTDIC系统凭借其从标准到高速、从单相机到双目立体视觉的完整产品覆盖，为不同场景的水下结构监测提供了可配置的解决方案。

随着深海养殖产业的快速发展和海洋工程装备的不断升级，水下结构健康监测的需求将持续增长。DIC技术以其全场、非接触、高精度的测量能力，有望成为水下结构监测领域的重要技术工具，为深海养殖安全和海洋工程可靠性提供更有力的技术支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: Structural Safety Challenges in Deep-Sea Aquaculture](#1-introduction-structural-safety-challenges-in-deep-sea-aquaculture)
- [2. Underwater Force Analysis of Fishing Net Structures](#2-underwater-force-analysis-of-fishing-net-structures)
- [3. Dilemmas of Traditional Underwater Measurement Methods](#3-dilemmas-of-traditional-underwater-measurement-methods)
- [4. Unique Advantages of DIC for Underwater Measurement](#4-unique-advantages-of-dic-for-underwater-measurement)
- [5. Key Technical Challenges and Solutions for Underwater DIC](#5-key-technical-challenges-and-solutions-for-underwater-dic)
  - [5.1 Waterproof Sealing and Optical Window Design](#51-waterproof-sealing-and-optical-window-design)
  - [5.2 Underwater Speckle Preparation](#52-underwater-speckle-preparation)
  - [5.3 Underwater Lighting and Image Quality](#53-underwater-lighting-and-image-quality)
  - [5.4 Refraction Correction and Calibration](#54-refraction-correction-and-calibration)
  - [5.5 Underwater Binocular Stereo Vision System](#55-underwater-binocular-stereo-vision-system)
- [6. XTDIC System Implementation for Underwater Net Monitoring](#6-xtdic-system-implementation-for-underwater-net-monitoring)
  - [6.1 Equipment Configuration](#61-equipment-configuration)
  - [6.2 Field Deployment Options](#62-field-deployment-options)
  - [6.3 Workflow](#63-workflow)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
  - [7.1 Deep-Sea Cage Aquaculture Structural Health Monitoring](#71-deep-sea-cage-aquaculture-structural-health-monitoring)
  - [7.2 Trawl Gear Hydrodynamic Performance Evaluation](#72-trawl-gear-hydrodynamic-performance-evaluation)
  - [7.3 Marine Engineering Flexible Structure Monitoring](#73-marine-engineering-flexible-structure-monitoring)
  - [7.4 Aquaculture Netting Fatigue Life Assessment](#74-aquaculture-netting-fatigue-life-assessment)
- [8. Data Analysis and Structural Safety Assessment](#8-data-analysis-and-structural-safety-assessment)
- [9. Experimental Design and Implementation Recommendations](#9-experimental-design-and-implementation-recommendations)
- [10. Conclusion](#10-conclusion)

---

## 1. Introduction: Structural Safety Challenges in Deep-Sea Aquaculture

China is the world's largest aquaculture producer, with 2023 aquaculture output exceeding 58 million tons, accounting for over 60% of global production. As nearshore aquaculture space becomes saturated, deep-sea cage aquaculture has become an important industry direction. According to data from the Ministry of Agriculture and Rural Affairs, by the end of 2024, over 5,000 large deep-sea cages had been built nationwide, with aquaculture water volume exceeding 50 million cubic meters.

Deep-sea cages face severe structural safety challenges. Unlike nearshore environments, deep-sea conditions (water depth 20-50m, offshore distance 5-20km) subject cage systems to significantly increased wave, current, and wind forces. According to the "Technical Specification for Deep-Sea Water Cage Aquaculture" (SC/T 2018-2013), the design wave height for deep-sea cages is generally 5-8m, with design current velocity of 1-2m/s. Under actual typhoon conditions, wave heights can exceed 10m and current velocities can surpass 3m/s, with dynamic loads on netting and frame structures reaching 3-5 times design values.

Netting (fishing netting) is the weakest link in the cage system. Netting is woven from high-density polyethylene (HDPE) or nylon (PA), with mesh sizes of 20-80mm and twine diameters of 1-3mm. Under long-term wave and current action, netting experiences cyclic stress, making it prone to fatigue failure at knot junctions. Statistics show that fish escape incidents due to netting damage in deep-sea aquaculture cages exceed 200 cases annually, with single-incident economic losses ranging from hundreds of thousands to millions of yuan.

Traditional netting structure monitoring relies on diver visual inspection and periodic underwater videography—subjective, low-frequency, and data-poor—making it difficult to capture the dynamic deformation process of netting under wave action. In this context, a technology capable of achieving high-precision, full-field, dynamic measurement in underwater environments is needed.

Digital Image Correlation (DIC) technology, combined with underwater protection and optical compensation measures, provides a feasible technical path for underwater full-field deformation measurement of fishing net structures.

## 2. Underwater Force Analysis of Fishing Net Structures

The force state of fishing nets underwater is extremely complex, involving fluid-structure coupling, geometric nonlinearity, and material nonlinearity.

**Hydrodynamic Loads**: Water flow and waves exert drag and lift forces on netting. For a single net twine, hydrodynamic drag can be calculated using the Morrison equation:

F_D = 0.5 · C_D · ρ · d · u²

where C_D is the drag coefficient (~1.0-1.2 for cylinders), ρ is seawater density (~1025kg/m³), d is twine diameter, and u is relative flow velocity. For a 2mm diameter twine at 1m/s flow velocity, the hydrodynamic force per unit length is approximately 1-1.2N/m. The total hydrodynamic force on an entire cage netting can reach several tons.

**Gravity and Buoyancy**: The difference between netting self-weight and buoyancy (net weight) affects netting shape. HDPE density is approximately 0.95g/cm³, slightly less than seawater, so netting is slightly buoyant in still water. However, biofouling (barnacles, algae, etc.) can increase netting weight by 30%-200%, significantly altering the force state.

**Netting Deformation Characteristics**: Netting is a large-deformation flexible structure, with deformation under load reaching 50%-200% of its own dimensions. Deformation modes include overall drift (rigid displacement), mesh deformation (shear), and twine stretching (axial strain). Mesh deformation is a key indicator of netting hydrodynamic performance, directly affecting the cage's flow-blocking area and flow field distribution.

**Fatigue Damage Mechanism**: Under cyclic loading, stress concentrations at knot junctions create high-risk areas for fatigue failure. HDPE twine fatigue life typically ranges from 10⁵ to 10⁷ cycles, depending on stress amplitude and environmental temperature. Seawater temperature, UV radiation, and chemical corrosion accelerate netting material aging and reduce fatigue life.

## 3. Dilemmas of Traditional Underwater Measurement Methods

**Diver Visual Inspection**: Relies on divers observing netting conditions underwater—subjective, unable to quantitatively measure deformation. Diving depth is limited (generally not exceeding 30m), operation time is short (30-60 minutes per dive), and safety risks exist.

**Underwater Videography**: Obtains netting video through underwater cameras, but only enables qualitative observation, not quantitative deformation data. Image quality is heavily affected by water turbidity, with effective observation distance in turbid seawater less than 1m.

**Strain Gauge Measurement**: Bonding strain gauges to netting surface for local strain measurement. However, netting is a flexible woven structure, making strain gauge bonding difficult, and only single-point data can be obtained. Underwater, waterproof sealing and signal transmission are both challenging. Under current impact, strain gauges easily detach.

**Acoustic Measurement**: Using Acoustic Doppler Current Profilers (ADCP) to measure flow fields around netting, but cannot directly measure netting structural deformation. Acoustic equipment has limited spatial resolution (typically >100mm), making it difficult to capture mesh-level deformation.

**Particle Image Velocimetry (PIV)**: Underwater PIV can measure flow fields around netting, but requires seeding tracer particles in the water, which has some environmental impact. PIV measures flow fields, not structural deformation, and cannot directly obtain netting strain distribution.

The common problem with these methods is the inability to achieve quantitative, dynamic, non-contact full-field deformation measurement of netting in underwater environments.

## 4. Unique Advantages of DIC for Underwater Measurement

DIC tracks displacement and speckle patterns on object surfaces, enabling non-contact full-field measurement. Applying it to underwater fishing net structure monitoring offers unique advantages:

**Full-Field Deformation Measurement**: A single measurement yields 3D displacement and strain data at millions of points across the netting surface, completely presenting deformation distribution, stress concentration areas, and fatigue hotspots.

**Non-Contact, Non-Interference**: No sensors or attachments need to be installed on the netting, avoiding interference with netting structure and flow field.

**Large Deformation Measurement Capability**: DIC can measure strain ranges from 0.005% to 2000%, fully covering all conditions from small vibrations to ultimate deformation.

**Dynamic Measurement**: Paired with high-speed cameras, can collect dynamic deformation data of netting under wave action in real time, at frame rates of hundreds to thousands of frames per second.

**Underwater Adaptability**: Through waterproof sealing, optical window correction, and specialized speckle materials, DIC systems can operate stably in underwater environments.

## 5. Key Technical Challenges and Solutions for Underwater DIC

### 5.1 Waterproof Sealing and Optical Window Design

The primary challenge for underwater DIC measurement is equipment waterproofing. Cameras and lenses must be installed in waterproof housings, observing the target through optical windows.

**Waterproof Housing Design**:
- Material: 316L stainless steel or aerospace aluminum alloy, pressure-resistant to 50-100m depth
- Sealing: Double O-ring seal, leak rate <0.01mL/h
- Connectors: Waterproof cable connectors (SubConn or equivalent) for data and power transmission

**Optical Window Selection**:
- Material: Optical-grade sapphire glass or tempered glass, transmittance >92%, high pressure resistance
- Window thickness: Calculated based on water depth; 50m depth requires ≥10mm tempered glass
- Anti-fog treatment: Anti-fog coating on inner window surface to prevent condensation
- Optical window parallelism must be high (<10 arcseconds) to reduce refraction-induced image distortion

**Refraction Compensation**: Light passes from water (n≈1.33) through the optical window (n≈1.52) into air (n≈1.00), undergoing two refractions. Refraction causes image magnification changes and increased aberration. Refraction correction must be performed through calibration algorithms, or compensation lenses used in optical design.

### 5.2 Underwater Speckle Preparation

Speckle preparation in underwater environments faces special challenges: smooth netting surface, high flexibility, and difficult underwater operations.

**Speckle Schemes**:
- **Pre-Fabricated Speckle Film**: Speckle patterns printed on flexible film in factory, then bonded or tied to netting surface on site. Film material: PVC or PE, thickness 0.1-0.3mm, negligible impact on netting deformation.
- **Direct Spray**: Using underwater-specific coatings (e.g., epoxy-based) to spray speckles directly on netting surface. Coating must have underwater curing capability, curing time <2h.
- **Tied Marker Points**: Tying pre-fabricated marker points (e.g., 5-10mm diameter circular markers) at netting nodes as DIC tracking features. Marker material: corrosion-resistant nylon or PE.

**Speckle Size Design**: Underwater imaging resolution is affected by water quality; speckle size should be appropriately increased. Generally, each speckle should occupy 5-10 pixels in the image, corresponding to 2-5mm physical size (depending on camera distance and lens).

**Speckle Contrast**: Underwater, speckle-background contrast is reduced by water scattering. High-contrast color combinations (white speckles + black background, or fluorescent speckles + blue light excitation) improve image signal-to-noise ratio.

### 5.3 Underwater Lighting and Image Quality

Underwater lighting is a critical factor affecting DIC image quality.

**Water Light Attenuation**: Seawater light attenuation coefficient is approximately 0.1-0.5/m (depending on turbidity). In turbid seawater, light intensity attenuation over 1m can reach 30-50%. Red light attenuates fastest; blue-green light attenuates slowest.

**Lighting Schemes**:
- **Active LED Lighting**: High-brightness LED arrays, color temperature 5000-5600K, CRI≥90. LED power selected based on measurement distance: close range (<2m) uses 10-50W, long range (2-5m) requires 100-500W.
- **Blue Light + Fluorescent Speckles**: Using blue light (450-490nm) to excite fluorescent speckle materials, filtering background scattering light, significantly improving image contrast. This method is especially effective in turbid water.
- **Structured Light**: Projecting structured light patterns onto netting surface to enhance surface features and assist DIC matching.

**Image Quality Optimization**:
- Short exposure (<1ms) to freeze netting vibration blur
- Polarization filters to suppress water backscatter
- Image preprocessing: denoising, contrast enhancement, color correction

### 5.4 Refraction Correction and Calibration

In underwater DIC measurement, light refracts through multiple media (water-glass-air), causing imaging position to differ from actual position. Refraction correction is essential.

**Refraction Model**: Establish a complete light path model for rays passing from water through the optical window into air, calculating refraction offset for each image point. Refraction offset depends on:
- Angle between camera optical axis and optical window
- Optical window thickness and refractive index
- Water refractive index (related to temperature and salinity, ~1.333-1.345)
- Distance from camera to optical window

**Calibration Method**:
- Calibrate using standard calibration targets in underwater environment
- Calibration target material: ceramic or glass substrate, low thermal expansion coefficient, dimensional stability
- Calibration target accuracy: etching precision ±0.01mm
- Multi-position, multi-angle calibration to establish complete refraction correction parameter table

**Correction Accuracy**: After refraction correction, underwater DIC measurement accuracy can reach 0.01-0.05 pixels, corresponding to approximately 0.05-0.5mm physical accuracy (depending on measurement distance and field of view).

### 5.5 Underwater Binocular Stereo Vision System

Underwater DIC uses binocular stereo vision principles to measure 3D displacement and deformation.

**Binocular System Configuration**:
- Two cameras symmetrically arranged on either side of the optical window, baseline distance determined by measurement distance
- Generally, baseline distance is 1/3 to 1/2 of measurement distance
- Camera optical axis angle (convergence angle) 15-30°

**Synchronized Acquisition**: Two cameras collect synchronously via hardware trigger signals, synchronization accuracy ≤1μs, ensuring both cameras capture the same moment during netting vibration.

**3D Reconstruction**: Through binocular stereo matching and triangulation, 2D image coordinates from both cameras are converted to 3D spatial coordinates. Underwater, 3D reconstruction algorithms must account for refraction correction.

## 6. XTDIC System Implementation for Underwater Net Monitoring

### 6.1 Equipment Configuration

For underwater fishing net monitoring requirements, the XTDIC system offers:

**Standard Underwater Configuration**:
- XTDIC-CONST-SD cameras (2.3-5MP, 163-1500fps, 50με)
- Waterproof housing (50m depth rating, 316L stainless steel)
- Optical window (sapphire glass, transmittance >92%)
- Binocular stereo vision layout
- Underwater LED lighting system (50-200W)

**High-Frequency Dynamic Configuration**:
- XTDIC-CONST-HS cameras (4MP, >100,000fps, 50με)
- Suitable for high-frequency netting vibration and impact load measurement

**Key Parameters**:
- Strain range: 0.005%-2000%
- Displacement precision: ≤0.01 pixel (after refraction correction)
- Measurement area: 0.5m×0.4m to 5m×4m (adjustable)
- Operating depth: ≤50m (standard), customizable to 100m

### 6.2 Field Deployment Options

**Option 1: Fixed Installation**
- DIC system installed at fixed position on cage frame
- Cameras fixed to frame via waterproof housing, optical axis aligned to target netting area
- Suitable for long-term monitoring of specific netting areas
- Data transmitted via underwater cable to surface control station

**Option 2: ROV-Mounted**
- DIC system mounted on a Remotely Operated Vehicle (ROV)
- ROV carries DIC system to measure netting at different positions
- Suitable for comprehensive inspection of large-area cages
- High flexibility, but positioning accuracy affected by ROV motion stability

**Option 3: Diver-Handheld**
- Lightweight DIC probe designed for diver hand-held use
- Diver carries probe underwater to measure designated netting areas
- Suitable for small-range, high-precision local measurement
- Flexible operation, but lower measurement efficiency

### 6.3 Workflow

**Step 1: Speckle Preparation**
- Prepare speckles on target netting area (pre-fabricated speckle film or underwater spray)
- Speckle area determined by camera field of view, generally 0.5-2㎡

**Step 2: System Installation and Calibration**
- Install DIC system at predetermined position (fixed/ROV/diver-handheld)
- Perform system calibration in underwater environment, including refraction correction parameter calibration
- Calibration accuracy verification: reprojection error ≤0.1 pixel

**Step 3: Data Acquisition**
- Collect static deformation data of netting under normal sea conditions (self-weight + hydrostatic pressure)
- Collect dynamic deformation data of netting under wave/current action
- Acquisition duration determined by monitoring objectives: short-term (minutes to hours) or long-term (days to weeks)

**Step 4: Data Processing and Analysis**
- DIC software processes collected image sequences, calculating full-field displacement and strain
- Extract key parameters: maximum deformation, strain concentration factor, vibration frequency, fatigue hotspots
- Generate netting deformation contour maps, time-history curves, and spectral analysis

**Step 5: Structural Safety Assessment**
- Compare measurement results with mechanical performance parameters of netting material
- Evaluate netting safety margin and remaining fatigue life
- Provide data support for netting replacement and maintenance decisions

## 7. Typical Application Scenarios

### 7.1 Deep-Sea Cage Aquaculture Structural Health Monitoring

Deep-sea cage netting (gravity cages, floating rope cages) continuously deforms under wave and current action, making it a critical structural safety monitoring target.

**Monitoring Focus**: Maximum netting deformation, strain concentration at knot junctions, relative displacement at netting-frame connection points, impact of biofouling on netting stiffness.

**DIC Value**: Real-time full-field netting deformation data, identifying stress concentration areas, early warning of netting damage risk. One deep-sea cage aquaculture enterprise using DIC monitoring improved netting damage early warning accuracy to over 85%, reducing fish escape incidents by 60%.

**Typical Data**: Under sea conditions with 3m wave height and 1m/s current velocity, maximum netting deformation can reach 80%-120% of mesh size, with knot junction strain concentration factors reaching 2-3x.

### 7.2 Trawl Gear Hydrodynamic Performance Evaluation

During fishing operations, trawl netting forms specific mesh shapes under water flow, directly affecting fishing efficiency and selectivity.

**Monitoring Focus**: Netting shape changes under water flow, mesh opening degree, netting drag distribution.

**DIC Value**: Obtaining full-field deformation data of trawl netting during tank tests or sea trials, optimizing netting design, reducing drag, improving fishing efficiency.

**Typical Data**: Trawl netting at 2-3kn towing speed shows mesh opening degree variation of 30%-70%, with netting drag coefficients of 0.5-1.2 (depending on mesh size and twine diameter).

### 7.3 Marine Engineering Flexible Structure Monitoring

Flexible structures in marine engineering (submarine pipeline protection covers, marine cables, flexible risers, etc.) experience complex fluid-structure coupling underwater.

**Monitoring Focus**: Vortex-induced vibration (VIV) deformation, fatigue damage accumulation, stress concentration at connection points.

**DIC Value**: Non-contact measurement of full-field vibration modes and strain distribution of flexible structures, providing data for fatigue life assessment.

### 7.4 Aquaculture Netting Fatigue Life Assessment

Under long-term cyclic loading, fatigue fracture is the primary failure mode for netting. DIC technology can be used for full-field strain monitoring during netting fatigue testing.

**Monitoring Focus**: Strain amplitude at knot junctions, fatigue crack initiation and propagation, overall netting stiffness degradation.

**DIC Value**: Real-time monitoring of full-field strain distribution during fatigue tests, identifying fatigue hotspots, establishing netting fatigue life prediction models.

**Typical Data**: HDPE netting under cyclic loading with 5%-10% strain amplitude has fatigue life of approximately 10⁵-10⁶ cycles. Each 0.5 increase in knot junction strain concentration factor reduces fatigue life by approximately 30%-50%.

## 8. Data Analysis and Structural Safety Assessment

Full-field deformation data obtained from underwater DIC measurement requires systematic analysis to translate into structural safety assessment conclusions:

**Deformation Feature Extraction**:
- Maximum displacement and strain values and their locations
- Deformation distribution contour maps, identifying high-strain areas
- Key point displacement time-history curves

**Vibration Characteristic Analysis**:
- FFT frequency domain analysis, extracting netting vibration frequencies and mode shapes
- Identifying vortex-induced vibration (VIV) characteristic frequencies
- Damping ratio estimation

**Fatigue Assessment**:
- Fatigue damage accumulation calculation based on strain time-history data (Miner's criterion)
- Rainflow counting method to extract strain cycle characteristics
- Combined with S-N curves to predict remaining fatigue life

**Safety Early Warning**:
- Set strain early warning thresholds (e.g., 60% of material yield strain)
- Set deformation early warning thresholds (e.g., 100% of mesh size)
- Automatic alarm when real-time monitoring data exceeds thresholds

## 9. Experimental Design and Implementation Recommendations

For engineers beginning underwater DIC measurement, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Waterproof Rating | Select waterproof housing based on water depth; 50m depth requires pressure resistance ≥0.5MPa |
| Speckle Scheme | Pre-fabricated speckle film offers highest efficiency; underwater spray requires fast-cure coating |
| Lighting Scheme | Turbid water recommends blue light + fluorescent speckle scheme |
| Refraction Correction | Underwater calibration essential; air calibration parameters cannot be used |
| Image Quality | Short exposure to freeze vibration blur; polarization filters to suppress backscatter |
| Measurement Distance | Minimize camera-to-netting distance (<2m) to reduce water attenuation effects |

**Getting Started Recommendation**: Begin with laboratory tank tests, verifying underwater DIC system measurement accuracy and reliability in controlled environments, then expand to sea trials after gaining experience.

## 10. Conclusion

Underwater fishing net structure monitoring is a critical technical link in ensuring deep-sea aquaculture safety. DIC technology, combined with underwater protection and optical compensation measures, provides a unique technical means for underwater full-field deformation measurement of fishing net structures.

From laboratory tank tests to sea trials, from netting deformation monitoring to fatigue life assessment, DIC technology's applications in underwater fishery engineering are gradually deepening. The XTDIC system, with its complete product coverage from standard to high-speed and from single camera to binocular stereo vision, provides configurable solutions for underwater structure monitoring in different scenarios.

As the deep-sea aquaculture industry rapidly develops and marine engineering equipment continues to upgrade, demand for underwater structural health monitoring will continue to grow. DIC technology, with its full-field, non-contact, high-precision measurement capabilities, is expected to become an important technical tool in the underwater structure monitoring field, providing stronger technical support for deep-sea aquaculture safety and marine engineering reliability.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D underwater and marine engineering application documentation*
