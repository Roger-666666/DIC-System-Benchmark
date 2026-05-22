# 利用DIC进行焊接试样循环加载疲劳试验：从裂纹萌生到断裂的全场感知

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<details open id="chinese-version">
<summary><b>🇨🇳 点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [1. 引言：焊接接头疲劳性能的工程意义](#1-引言焊接接头疲劳性能的工程意义)
- [2. 焊接试样疲劳试验的力学基础](#2-焊接试样疲劳试验的力学基础)
- [3. 传统测量方法在焊接疲劳试验中的局限](#3-传统测量方法在焊接疲劳试验中的局限)
- [4. DIC技术用于焊接疲劳试验的核心能力](#4-dic技术用于焊接疲劳试验的核心能力)
- [5. 焊接试样DIC疲劳试验的关键技术环节](#5-焊接试样dic疲劳试验的关键技术环节)
- [6. XTDIC系统在焊接疲劳试验中的实施方案](#6-xtdic系统在焊接疲劳试验中的实施方案)
- [7. 典型应用场景](#7-典型应用场景)
- [8. 实验设计与数据处理](#8-实验设计与数据处理)
- [9. 结语](#9-结语)

---

## 1. 引言：焊接接头疲劳性能的工程意义

焊接接头是工程结构中最常见的连接形式，也是结构安全评估中最受关注的薄弱环节。据统计，约60%-80%的结构失效起源于焊接接头区域——焊缝余高处的应力集中、热影响区的微观组织劣化、焊接残余应力的叠加效应，使得焊接接头在循环载荷下成为裂纹萌生和扩展的首选位置。

焊接试样的循环加载疲劳试验，是评估焊接接头疲劳性能最直接、最可靠的方法。通过在一定应力比和频率下对焊接试样施加循环载荷，记录试样从初始状态到裂纹萌生、扩展直至最终断裂的完整过程，可以获得焊接接头的S-N曲线（应力-寿命曲线）、裂纹扩展速率da/dN与应力强度因子幅值ΔK的关系曲线（Paris曲线）、以及断裂韧性等关键疲劳参数。

然而，焊接疲劳试验的测量需求极为特殊：需要同时关注焊缝区域的全场应变分布（识别应变集中位置，即裂纹可能萌生的位置）、裂纹尖端附近的局部应变场（用于计算应力强度因子和J积分）、以及试样整体刚度退化（反映损伤累积程度）。传统的单点测量方法——应变片、引伸计、裂纹规——只能提供有限几个位置的数据，无法呈现焊接试样在循环加载下从均匀变形到局部化、从裂纹萌生到断裂的全场演化过程。

数字图像相关（DIC）技术以其非接触、全场、高精度的测量特性，为焊接试样循环加载疲劳试验提供了全新的测量手段。通过追踪试样表面散斑图案在循环载荷下的变化，DIC可以实时获取整个试样表面的位移场和应变场数据，完整记录焊接疲劳全过程的变形演化信息。

## 2. 焊接试样疲劳试验的力学基础

### 2.1 疲劳破坏的三个阶段

焊接试样的疲劳破坏通常经历三个阶段：

**裂纹萌生阶段（Crack Initiation）**：在循环载荷作用下，焊缝表面或内部的缺陷（气孔、夹渣、未熔合）以及几何不连续处（焊趾、焊根）产生应力集中，局部区域的循环塑性应变逐渐累积，形成微裂纹。这一阶段通常占据疲劳寿命的10%-30%，对于高强钢焊接接头，裂纹萌生寿命占比更低。

**裂纹扩展阶段（Crack Propagation）**：微裂纹形成后，在循环载荷作用下沿垂直于主应力方向稳定扩展。裂纹扩展速率da/dN与应力强度因子幅值ΔK之间的关系通常用Paris公式描述：da/dN = C(ΔK)^m，其中C和m为材料常数。这一阶段占据疲劳寿命的主要部分（60%-80%）。

**最终断裂阶段（Final Fracture）**：当裂纹扩展到临界尺寸（使得应力强度因子达到材料的断裂韧性K_IC）时，试样发生快速失稳断裂。这一阶段通常只占疲劳寿命的很小比例。

### 2.2 焊接接头的疲劳特性

焊接接头的疲劳特性与母材存在显著差异，主要体现在：

**应力集中效应**：焊缝余高处的几何不连续导致局部应力集中，焊趾处的应力集中系数K_t通常在1.5-3.0之间，取决于焊缝几何形状和焊接工艺。

**残余应力影响**：焊接热循环在焊缝区域产生残余拉应力，其数值可达到材料屈服强度的50%-100%。残余拉应力叠加在循环载荷上，显著提高有效应力比，加速裂纹萌生和扩展。

**微观组织不均匀性**：焊缝金属、热影响区和母材的微观组织差异导致力学性能不均匀，裂纹扩展路径受到微观组织的影响。

**缺陷敏感性**：焊接缺陷（气孔、夹渣、未熔合、咬边）是裂纹萌生的优先位置，缺陷尺寸和分布对疲劳寿命有显著影响。

### 2.3 疲劳试验标准体系

焊接疲劳试验遵循一系列国际和国家标准：

- **ISO 14324**：焊接接头疲劳试验方法
- **ASTM E466**：金属材料轴向等幅疲劳试验标准
- **GB/T 3075**：金属材料疲劳试验轴向力控制方法
- **GB/T 26077**：金属材料疲劳试验轴向应变控制方法
- **IIW Recommendations**：国际焊接学会焊接接头疲劳设计指南

这些标准规定了试样几何、加载条件、数据采集和结果处理的基本要求，但对测量方法没有强制规定——这为DIC技术的应用留下了空间。

## 3. 传统测量方法在焊接疲劳试验中的局限

### 3.1 应变片

应变片是疲劳试验中最常用的测量工具，但在焊接疲劳试验中存在明显局限：

**单点测量**：一个应变片只能测量一个点在一个方向上的应变，无法提供全场数据。焊接接头区域应变分布极不均匀，单点数据难以反映真实的应变集中程度。

**粘贴位置依赖**：应变片的测量结果高度依赖于粘贴位置。如果应变片恰好粘贴在应变集中区域，测量值偏高；如果粘贴在应变较低区域，测量值偏低。对于焊接接头，应变梯度大，粘贴位置的微小偏差可能导致测量结果的显著差异。

**疲劳寿命限制**：应变片本身在循环载荷下也会发生疲劳破坏，其疲劳寿命通常只有10^4-10^6次循环，远低于焊接试样的疲劳寿命（10^5-10^7次循环）。这意味着在疲劳试验后期，应变片可能已经失效，无法提供完整的数据。

**无法追踪裂纹**：应变片无法直接测量裂纹长度和裂纹扩展速率，需要配合其他测量手段（如裂纹规或电位法）。

### 3.2 引伸计

引伸计可以测量标距范围内的平均位移，但在焊接疲劳试验中：

**标距平均效应**：引伸计测量的是标距范围内的平均应变，无法反映焊缝区域的局部应变集中。对于焊接试样，焊缝区域的应变可能是母材应变的2-5倍，引伸计的平均值会严重低估焊缝区域的真实应变。

**接触压力影响**：引伸计需要接触试样表面，接触压力可能影响薄板焊接试样的局部变形行为。

**无法测量裂纹**：引伸计无法直接测量裂纹参数。

### 3.3 裂纹规（Crack Gauge）

裂纹规专门用于测量裂纹长度，但只能测量裂纹尖端的局部信息，无法提供裂纹周围的应变场分布。此外，裂纹规需要粘贴在预定的裂纹扩展路径上，对于裂纹路径不确定的焊接试样，粘贴位置的选择具有挑战性。

### 3.4 电位法（Potential Drop Method）

电位法通过测量裂纹扩展引起的电位变化来推算裂纹长度，但需要预先在试样上焊接导线，且测量结果受温度、材料电导率等因素影响。电位法无法提供应变场信息。

## 4. DIC技术用于焊接疲劳试验的核心能力

### 4.1 全场应变分布：识别裂纹萌生位置

DIC可以在每次循环（或每隔一定循环次数）后获取试样表面的全场应变分布。通过分析应变云图，可以识别应变集中区域——这些区域就是裂纹可能萌生的位置。

对于焊接试样，焊缝余高、焊趾、焊根等几何不连续处是天然的应变集中区域。DIC的全场应变数据可以精确量化这些区域的应变集中程度，为裂纹萌生位置的预测提供直接依据。

更重要的是，DIC可以捕捉到肉眼不可见的早期损伤信号。在裂纹萌生之前，局部区域的应变幅值会逐渐增大（由于微观损伤累积导致局部刚度下降），这种应变幅值的渐进变化可以通过DIC精确记录，为裂纹萌生寿命的判定提供客观标准。

### 4.2 裂纹尖端应变场：量化裂纹扩展驱动力

裂纹扩展阶段，DIC可以获取裂纹尖端附近的局部应变场。通过分析裂纹尖端的应变分布，可以计算应力强度因子（SIF）和J积分，量化裂纹扩展的驱动力。

传统的裂纹扩展速率测量需要在裂纹两侧粘贴裂纹规或使用电位法，操作复杂且精度有限。DIC通过分析裂纹张开位移（COD）和裂纹尖端应变场，可以非接触地计算裂纹长度和应力强度因子，同时获得裂纹周围的完整应变分布信息。

### 4.3 循环变形演化：记录损伤累积全过程

DIC可以在疲劳试验的整个过程中（从初始循环到最终断裂）持续记录试样表面的变形演化。通过分析不同循环次数下的应变云图变化，可以追踪损伤累积的全过程：

- **初始阶段**：应变分布相对均匀，焊缝区域有轻微的应变集中
- **裂纹萌生阶段**：局部区域应变幅值逐渐增大，应变集中区域逐渐明确
- **裂纹扩展阶段**：裂纹尖端形成高应变集中区，裂纹两侧出现不连续的位移场
- **最终断裂阶段**：裂纹快速扩展，试样刚度急剧下降，应变分布发生突变

这种全过程的变形演化数据，是理解焊接疲劳损伤机制、验证疲劳寿命预测模型的宝贵资源。

### 4.4 刚度退化监测：评估损伤程度

随着循环次数的增加，焊接试样的整体刚度会逐渐降低（由于裂纹扩展导致有效承载面积减小）。DIC通过测量试样在最大载荷和最小载荷下的全场位移，可以计算试样整体刚度的变化曲线。刚度退化曲线是评估损伤程度的重要指标，也是疲劳寿命预测模型的关键输入。

### 4.5 非接触测量：不干扰疲劳过程

DIC通过光学成像实现测量，不接触试样表面，不引入任何附加质量或刚度。这对于焊接疲劳试验至关重要——任何接触式测量手段都可能改变试样的局部应力状态，影响裂纹萌生和扩展行为。

## 5. 焊接试样DIC疲劳试验的关键技术环节

### 5.1 散斑制备

焊接疲劳试验的散斑制备需要满足以下要求：

**耐高温性**：虽然疲劳试验通常在室温下进行，但焊接试样表面可能存在焊接氧化层，散斑材料需要与氧化层有良好的附着力。

**抗疲劳性**：散斑需要在数百万次循环载荷下不脱落、不剥落。通常采用环氧树脂基底的散斑涂料，其疲劳寿命可达10^7次以上。

**对比度**：散斑需要与试样表面形成良好的对比度。对于钢质焊接试样，通常先喷涂亚光白底漆，再喷涂亚光黑漆形成随机散斑。

**散斑尺寸**：散斑大小需要与相机分辨率和测量区域匹配，通常要求每个散斑占据3-5个像素。对于焊接疲劳试验，由于需要同时关注焊缝区域的局部应变和试样整体变形，建议采用中等大小的散斑（约0.1-0.3mm）。

### 5.2 循环同步采集

焊接疲劳试验的加载频率通常在1-30Hz范围内。DIC系统需要与疲劳试验机实现同步采集：

**降频采集策略**：由于DIC的图像采集和处理速度有限（通常在几十到几百fps），无法在每个循环都进行全分辨率采集。常用的策略是每隔一定循环次数（如每100次或每1000次循环）进行一次完整的DIC采集，采集时试验机保持当前载荷（通常在最大载荷处保持）。

**峰值保持采集**：在疲劳试验机的载荷峰值处触发DIC采集，此时试样变形最大，应变信号最强。通过控制疲劳试验机的保持时间，确保DIC采集期间试样处于稳定变形状态。

**多相位采集**：对于需要研究循环变形行为的试验，可以在一个循环内的多个相位点（如最大载荷、最小载荷、零载荷）进行DIC采集，获取循环变形的完整信息。

### 5.3 数据处理策略

焊接疲劳试验产生的数据量巨大——每次DIC采集产生数十万到数百万个测点的位移和应变数据，整个疲劳试验可能进行数百次采集。高效的数据处理策略至关重要：

**感兴趣区域（ROI）分析**：将试样表面划分为多个感兴趣区域（焊缝区域、热影响区、母材区域），分别计算各区域的平均应变和最大应变，减少数据量。

**应变幅值追踪**：对于每个测点，记录其在循环过程中的应变幅值变化。应变幅值的逐渐增大是损伤累积的早期信号。

**裂纹自动识别**：通过分析位移场的不连续性，自动识别裂纹位置和长度。裂纹两侧的位移场存在不连续跳跃，这种不连续性可以通过位移梯度分析自动检测。

### 5.4 温度补偿

疲劳试验过程中，由于循环塑性变形的功热转化，试样温度会升高（通常升高5-30°C，取决于加载频率和应力水平）。温度升高导致试样热膨胀，在DIC测量中表现为虚假的应变信号。

温度补偿方法包括：
- 在试样附近安装温度传感器，实时记录温度变化，从DIC测量结果中扣除热膨胀分量
- 在试验开始前进行空载温度标定，建立温度-热膨胀关系
- 控制试验环境温度，减小温度波动

## 6. XTDIC系统在焊接疲劳试验中的实施方案

### 6.1 设备配置

**相机配置**：
- 对于标准焊接试样（标距长度50-200mm），推荐使用XTDIC-CONST-SD系列（2.3-5MP），单相机即可覆盖试样标距区域
- 对于大型焊接结构件（标距长度>500mm），推荐使用XTDIC-CONST-HR系列（≤25MP）或多相机组网
- 对于需要高时间分辨率的试验（如研究循环变形行为），推荐使用XTDIC-CONST-HS系列（>10万fps）

**加载设备**：
- 液压伺服疲劳试验机（如Instron、MTS），载荷范围根据试样尺寸确定
- 试验频率：1-30Hz（取决于试样刚度和试验机能力）
- 应力比：R=0.1（典型拉-拉疲劳）或R=-1（完全反向疲劳）

**散斑制备**：
- 亚光白底漆 + 亚光黑漆随机散斑
- 散斑尺寸：0.1-0.3mm（根据相机分辨率调整）
- 散斑覆盖率：50%-70%

### 6.2 测量流程

1. **试样准备**：在焊接试样标距区域制备散斑，确保焊缝区域、热影响区和母材区域都有良好的散斑覆盖
2. **相机安装**：调整相机位置和焦距，确保散斑区域清晰成像，标定相机参数
3. **初始采集**：在加载前进行初始DIC采集，获取试样的初始状态
4. **疲劳试验**：启动疲劳试验机，按照预定的载荷幅值、频率和应力比进行循环加载
5. **定期DIC采集**：每隔一定循环次数（如每1000次循环），在载荷峰值处触发DIC采集
6. **数据保存**：保存每次采集的图像和DIC分析结果
7. **裂纹监测**：通过DIC应变云图监测裂纹萌生和扩展
8. **试验结束**：试样断裂后，停止试验，整理数据

### 6.3 关键参数

| 参数 | 典型值 | 说明 |
|------|--------|------|
| 相机分辨率 | 2.3-25MP | 根据试样尺寸选择 |
| 采集帧率 | 1-100fps | 静态采集（峰值保持） |
| 位移精度 | ≤0.01像素 | 取决于标定质量 |
| 应变精度 | 20με（静态） | XTDIC-CONST-HR |
| 应变范围 | 0.005%-2000% | 覆盖弹性到塑性 |
| 采集间隔 | 每100-10000次循环 | 根据疲劳寿命调整 |
| 加载频率 | 1-30Hz | 取决于试样和试验机 |
| 应力比 | R=0.1或R=-1 | 典型疲劳条件 |

## 7. 典型应用场景

### 7.1 焊接接头S-N曲线测定

通过在不同应力幅值下对焊接试样进行疲劳试验，结合DIC全场应变测量，可以获得更精确的S-N曲线。DIC提供的全场应变数据可以准确判定裂纹萌生寿命（通过应变幅值的突变识别），而传统方法通常以试样完全断裂作为疲劳寿命终点。

**工程价值**：更精确的S-N曲线为焊接结构的疲劳寿命预测提供更可靠的数据基础。

### 7.2 裂纹扩展速率da/dN测量

DIC可以实时测量裂纹长度随循环次数的变化，直接计算裂纹扩展速率da/dN。结合裂纹尖端应变场分析，可以计算应力强度因子幅值ΔK，获得Paris曲线（da/dN-ΔK关系）。

**工程价值**：Paris曲线参数C和m是疲劳寿命预测的关键输入，DIC提供了一种非接触、高精度的测量方法。

### 7.3 焊接残余应力对疲劳性能的影响研究

通过对比不同残余应力状态（焊态、去应力退火态、喷丸处理态）下焊接试样的DIC疲劳试验数据，可以定量评估残余应力对裂纹萌生寿命和裂纹扩展速率的影响。

**工程价值**：为焊接工艺优化（如焊后热处理、喷丸强化）提供实验数据支撑。

### 7.4 焊接缺陷对疲劳性能的影响研究

通过在焊接试样中预制不同尺寸和类型的缺陷（气孔、夹渣、未熔合），结合DIC疲劳试验，可以定量评估缺陷尺寸和类型对疲劳寿命的影响。

**工程价值**：为焊接质量验收标准的制定提供实验依据。

### 7.5 异种钢焊接接头疲劳性能评估

异种钢焊接接头（如碳钢-不锈钢、高强钢-低强钢）的疲劳性能评估需要考虑两种母材和焊缝金属的力学性能差异。DIC全场应变测量可以揭示异种钢焊接接头在循环载荷下的应变分布特征和裂纹扩展行为。

**工程价值**：为异种钢焊接结构的设计和安全性评估提供数据支撑。

## 8. 实验设计与实施建议

对于初次在焊接疲劳试验中引入DIC的工程团队，建议关注以下要点：

| 关键因素 | 注意事项 |
|---------|---------|
| 散斑制备 | 散斑需在数百万次循环下不脱落，建议使用环氧树脂基底涂料 |
| 采集策略 | 根据疲劳寿命确定采集间隔，寿命越长间隔越大 |
| 温度补偿 | 监测试样温度变化，扣除热膨胀分量 |
| 裂纹识别 | 通过位移场不连续性自动识别裂纹，设定合理的检测阈值 |
| 数据管理 | 疲劳试验数据量巨大，建议采用ROI分析和自动处理流程 |
| 相机防护 | 疲劳试验可能发生试样断裂，相机需配备防护罩 |

**入门建议**：从简单的母材疲劳试验开始（无焊缝），验证DIC测量结果与应变片的一致性，建立信心后再扩展到焊接试样。

## 9. 结语

焊接试样的循环加载疲劳试验是评估焊接结构安全性的基础手段，但传统的单点测量方法只能提供有限的信息，无法呈现焊接疲劳全过程的变形演化。DIC技术通过全场、非接触、高精度的测量能力，为焊接疲劳试验带来了质的飞跃——从"看几个点"到"看全场"，从"看最终结果"到"看演化过程"，从"看裂纹长度"到"看裂纹尖端应变场"。

裂纹萌生位置的精确识别、裂纹扩展速率的实时测量、损伤累积全过程的循环变形记录、试样整体刚度的退化监测——这些能力使DIC成为焊接疲劳研究中不可替代的技术手段。XTDIC系统凭借其从2.3MP到25MP的灵活配置、≤0.01像素的位移精度、0.005%-2000%的应变范围，正在成为焊接疲劳试验领域的重要工具。

随着焊接结构向更高强度、更轻量化、更复杂形式发展，对焊接疲劳性能的评估要求也在不断提高。DIC技术在焊接疲劳试验中的应用也将不断深化——从实验室研究到工程验证，从标准试样到实际焊接结构，为焊接结构的安全性评估和寿命预测提供更有力的技术支撑。

</details>

<details id="english-version">
<summary><b>🇺🇸 Click to Expand: English Version (点击展开：英文版)</b></summary>

## Table of Contents

- [1. Introduction: Engineering Significance of Welded Joint Fatigue Performance](#1-introduction-engineering-significance-of-welded-joint-fatigue-performance)
- [2. Mechanical Basics of Welded Specimen Fatigue Testing](#2-mechanical-basics-of-welded-specimen-fatigue-testing)
- [3. Limitations of Traditional Measurement Methods in Weld Fatigue Testing](#3-limitations-of-traditional-measurement-methods-in-weld-fatigue-testing)
- [4. Core Capabilities of DIC for Weld Fatigue Testing](#4-core-capabilities-of-dic-for-weld-fatigue-testing)
- [5. Key Technical Aspects of DIC Weld Fatigue Testing](#5-key-technical-aspects-of-dic-weld-fatigue-testing)
- [6. XTDIC System Implementation for Weld Fatigue Testing](#6-xtdic-system-implementation-for-weld-fatigue-testing)
- [7. Typical Application Scenarios](#7-typical-application-scenarios)
- [8. Experimental Design and Data Processing](#8-experimental-design-and-data-processing)
- [9. Conclusion](#9-conclusion)

---

## 1. Introduction: Engineering Significance of Welded Joint Fatigue Performance

Welded joints are the most common connection form in engineering structures and the most critical weak link in structural safety assessment. Statistics show that approximately 60%-80% of structural failures originate from welded joint areas—stress concentrations at weld reinforcement, microstructural degradation in the heat-affected zone (HAZ), and superposition of welding residual stresses make welded joints preferred sites for crack initiation and propagation under cyclic loading.

Cyclic loading fatigue testing of welded specimens is the most direct and reliable method for evaluating welded joint fatigue performance. By applying cyclic loads at a specific stress ratio and frequency, recording the complete process from initial state through crack initiation, propagation, and final fracture, key fatigue parameters can be obtained: S-N curves (stress-life curves), crack growth rate da/dN versus stress intensity factor range ΔK (Paris curves), and fracture toughness.

However, measurement requirements for weld fatigue testing are extremely special: simultaneous attention to full-field strain distribution in the weld zone (identifying strain concentration locations where cracks may initiate), local strain fields near crack tips (for calculating stress intensity factors and J-integrals), and overall specimen stiffness degradation (reflecting damage accumulation). Traditional single-point measurement methods—strain gauges, extensometers, crack gauges—can only provide data at limited locations and cannot present the complete evolution from uniform deformation to localization, from crack initiation to fracture.

Digital Image Correlation (DIC) technology, with its non-contact, full-field, high-precision measurement capabilities, provides a means to track speckle pattern changes on specimen surfaces under cyclic loading, obtaining displacement and strain field data across the entire specimen surface in real time, and completely recording deformation evolution throughout the entire weld fatigue process.

## 2. Mechanical Basics of Welded Specimen Fatigue Testing

### 2.1 Three Stages of Fatigue Failure

Welded specimen fatigue failure typically proceeds through three stages:

**Crack Initiation**: Under cyclic loading, stress concentrations at surface/internal defects (porosity, slag inclusions, lack of fusion) and geometric discontinuities (weld toe, weld root) cause gradual accumulation of cyclic plastic strain, forming micro-cracks. This stage typically occupies 10%-30% of fatigue life.

**Crack Propagation**: Once micro-cracks form, they stably extend perpendicular to the principal stress direction under cyclic loading. The relationship between crack growth rate da/dN and stress intensity factor range ΔK is described by the Paris law: da/dN = C(ΔK)^m, where C and m are material constants. This stage occupies the majority of fatigue life (60%-80%).

**Final Fracture**: When cracks extend to critical size (reaching material fracture toughness K_IC), rapid unstable fracture occurs. This stage typically occupies a small fraction of fatigue life.

### 2.2 Fatigue Characteristics of Welded Joints

Welded joint fatigue characteristics differ significantly from base metal:

**Stress concentration effect**: Geometric discontinuities at weld reinforcement cause local stress concentration, with stress concentration factors K_t typically 1.5-3.0 at the weld toe, depending on weld geometry and welding process.

**Residual stress influence**: Welding thermal cycles produce residual tensile stresses in the weld zone, reaching 50%-100% of material yield strength. These residual tensile stresses superimpose on cyclic loading, significantly increasing the effective stress ratio and accelerating crack initiation and propagation.

**Microstructural inhomogeneity**: Differences in microstructure between weld metal, HAZ, and base metal lead to non-uniform mechanical properties, affecting crack propagation paths.

**Defect sensitivity**: Welding defects (porosity, slag, lack of fusion, undercut) are preferred crack initiation sites, with defect size and distribution significantly affecting fatigue life.

### 2.3 Fatigue Testing Standards

Weld fatigue testing follows international and national standards: ISO 14324 (welded joint fatigue test methods), ASTM E466 (axial constant-amplitude fatigue), GB/T 3075 (axial force-controlled fatigue), GB/T 26077 (axial strain-controlled fatigue), and IIW Recommendations for fatigue design of welded joints.

## 3. Limitations of Traditional Measurement Methods in Weld Fatigue Testing

**Strain gauges**: Single-point measurement only, highly dependent on bonding position, limited fatigue life (10^4-10^6 cycles vs. specimen life of 10^5-10^7 cycles), cannot track cracks.

**Extensometers**: Gauge-length averaging effect underestimates strain concentration in weld zones (weld strain may be 2-5x base metal strain), contact pressure may affect thin-plate behavior, cannot measure cracks.

**Crack gauges**: Only measure local crack tip information, require bonding on predetermined crack paths—challenging for welded specimens with uncertain crack paths.

**Potential drop method**: Requires pre-welded lead wires, affected by temperature and conductivity, cannot provide strain field information.

## 4. Core Capabilities of DIC for Weld Fatigue Testing

### 4.1 Full-Field Strain Distribution: Identifying Crack Initiation Sites

DIC obtains full-field strain distribution on specimen surfaces at each cycle (or at regular intervals). Analyzing strain contour maps identifies strain concentration regions—potential crack initiation sites. For welded specimens, weld reinforcement, weld toe, and weld root are natural strain concentration areas. DIC full-field strain data can precisely quantify strain concentration levels, providing direct evidence for crack initiation site prediction.

More importantly, DIC can capture early damage signals invisible to the naked eye. Before crack initiation, local strain amplitudes gradually increase (due to micro-damage accumulation causing local stiffness reduction). This progressive change in strain amplitude can be precisely recorded by DIC, providing objective criteria for crack initiation life determination.

### 4.2 Crack Tip Strain Field: Quantifying Crack Propagation Driving Force

During crack propagation, DIC can obtain local strain fields near crack tips. Analyzing crack tip strain distributions enables calculation of stress intensity factors (SIF) and J-integrals, quantifying crack propagation driving forces. Through crack opening displacement (COD) and crack tip strain field analysis, DIC can non-contactly calculate crack length and stress intensity factors, simultaneously obtaining complete strain distribution information around cracks.

### 4.3 Cyclic Deformation Evolution: Recording Complete Damage Accumulation

DIC can continuously record surface deformation evolution throughout the entire fatigue test (from initial cycling to final fracture). Analyzing strain contour map changes at different cycle counts tracks the complete damage accumulation process: initial stage (relatively uniform strain distribution with slight weld zone concentration), crack initiation stage (gradually increasing local strain amplitude), crack propagation stage (high strain concentration at crack tips with discontinuous displacement fields on crack flanks), and final fracture stage (rapid crack extension with sudden stiffness drop and strain distribution change).

### 4.4 Stiffness Degradation Monitoring: Assessing Damage Level

As cycle counts increase, welded specimen overall stiffness gradually decreases (due to crack extension reducing effective load-bearing area). DIC measures full-field displacement at maximum and minimum loads, calculating specimen overall stiffness change curves. Stiffness degradation curves are important indicators for assessing damage levels and key inputs for fatigue life prediction models.

### 4.5 Non-Contact Measurement: No Interference with Fatigue Process

DIC achieves measurement through optical imaging without contacting specimen surfaces, introducing no additional mass or stiffness. This is critical for weld fatigue testing—any contact measurement method may alter local stress states, affecting crack initiation and propagation behavior.

## 5. Key Technical Aspects of DIC Weld Fatigue Testing

### 5.1 Speckle Preparation

Requirements for weld fatigue testing speckle preparation: high-temperature resistance (for welding oxide layer adhesion), fatigue resistance (must not detach over millions of cycles—epoxy-based speckle coatings with fatigue life exceeding 10^7 cycles are recommended), good contrast (matte white base + matte black paint for steel specimens), and appropriate speckle size (0.1-0.3mm, occupying 3-5 pixels).

### 5.2 Cyclic Synchronous Acquisition

Weld fatigue test loading frequencies are typically 1-30Hz. DIC systems require synchronization with fatigue testing machines:

**Down-sampling strategy**: Due to limited DIC image acquisition and processing speeds (typically tens to hundreds of fps), full-resolution acquisition at every cycle is not feasible. Common strategy: perform complete DIC acquisition at regular cycle intervals (e.g., every 100 or 1000 cycles), with the testing machine holding current load (typically at maximum load).

**Peak-hold acquisition**: Trigger DIC acquisition at load peaks of the fatigue testing machine, where specimen deformation is maximum and strain signals are strongest. Control holding time to ensure stable deformation during DIC acquisition.

**Multi-phase acquisition**: For studying cyclic deformation behavior, perform DIC acquisition at multiple phase points within one cycle (maximum load, minimum load, zero load) to obtain complete cyclic deformation information.

### 5.3 Data Processing Strategies

Weld fatigue tests generate enormous data volumes—each DIC acquisition produces displacement and strain data for hundreds of thousands to millions of measurement points, with hundreds of acquisitions over the entire test. Efficient data processing strategies are critical:

**Region of Interest (ROI) analysis**: Divide specimen surface into multiple ROIs (weld zone, HAZ, base metal), calculate average and maximum strain for each region to reduce data volume.

**Strain amplitude tracking**: For each measurement point, record strain amplitude changes during cycling. Gradually increasing strain amplitude is an early signal of damage accumulation.

**Automatic crack identification**: Automatically identify crack positions and lengths through displacement field discontinuity analysis. Displacement fields on crack flank sides exhibit discontinuous jumps, detectable through displacement gradient analysis.

### 5.4 Temperature Compensation

During fatigue testing, specimen temperature rises (typically 5-30°C, depending on loading frequency and stress level) due to cyclic plastic deformation work-to-heat conversion. Temperature rise causes thermal expansion, appearing as false strain signals in DIC measurements. Compensation methods include: installing temperature sensors near specimens to record temperature changes in real time and subtracting thermal expansion components from DIC measurements; performing unloaded temperature calibration before testing to establish temperature-thermal expansion relationships; and controlling test environment temperature to reduce fluctuations.

## 6. XTDIC System Implementation for Weld Fatigue Testing

### 6.1 Equipment Configuration

**Camera configuration**: For standard welded specimens (gauge length 50-200mm), XTDIC-CONST-SD series (2.3-5MP) is recommended, with a single camera covering the specimen gauge area. For large welded structural components (gauge length >500mm), XTDIC-CONST-HR series (≤25MP) or multi-camera networking is recommended. For high temporal resolution requirements (studying cyclic deformation behavior), XTDIC-CONST-HS series (>100,000fps) is recommended.

**Loading equipment**: Hydraulic servo fatigue testing machines (e.g., Instron, MTS), with loading frequency of 1-30Hz and stress ratio R=0.1 (typical tension-tension fatigue) or R=-1 (fully reversed fatigue).

**Speckle preparation**: Matte white base paint + matte black paint random speckles, speckle size 0.1-0.3mm, speckle coverage 50%-70%.

### 6.2 Measurement Workflow

1. **Specimen preparation**: Prepare speckles on welded specimen gauge areas, ensuring good speckle coverage in weld zone, HAZ, and base metal regions.
2. **Camera mounting**: Adjust camera position and focal length for clear speckle imaging; calibrate camera parameters.
3. **Initial acquisition**: Perform initial DIC acquisition before loading to obtain specimen initial state.
4. **Fatigue testing**: Start fatigue testing machine, apply cyclic loading at predetermined load amplitude, frequency, and stress ratio.
5. **Periodic DIC acquisition**: Trigger DIC acquisition at load peaks every certain number of cycles (e.g., every 1000 cycles).
6. **Data storage**: Save images and DIC analysis results from each acquisition.
7. **Crack monitoring**: Monitor crack initiation and propagation through DIC strain contour maps.
8. **Test completion**: After specimen fracture, stop test and organize data.

### 6.3 Key Parameters

| Parameter | Typical Value | Notes |
|-----------|--------------|-------|
| Camera resolution | 2.3-25MP | Selected based on specimen size |
| Acquisition frame rate | 1-100fps | Static acquisition (peak hold) |
| Displacement precision | ≤0.01 pixel | Depends on calibration quality |
| Strain precision | 20με (static) | XTDIC-CONST-HR |
| Strain range | 0.005%-2000% | Covers elastic to plastic |
| Acquisition interval | Every 100-10000 cycles | Adjusted based on fatigue life |
| Loading frequency | 1-30Hz | Depends on specimen and machine |
| Stress ratio | R=0.1 or R=-1 | Typical fatigue conditions |

## 7. Typical Application Scenarios

### 7.1 Welded Joint S-N Curve Determination

By performing fatigue tests on welded specimens at different stress amplitudes combined with DIC full-field strain measurement, more accurate S-N curves can be obtained. DIC full-field strain data can accurately determine crack initiation life (identified through strain amplitude mutations), whereas traditional methods typically use complete specimen fracture as the fatigue life endpoint.

**Engineering Value**: More accurate S-N curves provide more reliable data foundations for fatigue life prediction of welded structures.

### 7.2 Crack Growth Rate da/dN Measurement

DIC can measure crack length changes with cycle counts in real time, directly calculating crack growth rate da/dN. Combined with crack tip strain field analysis, stress intensity factor range ΔK can be calculated, obtaining Paris curves (da/dN-ΔK relationship).

**Engineering Value**: Paris curve parameters C and m are key inputs for fatigue life prediction; DIC provides a non-contact, high-precision measurement method.

### 7.3 Effect of Welding Residual Stress on Fatigue Performance

By comparing DIC fatigue test data from welded specimens with different residual stress states (as-welded, stress-relieved, shot-peened), the quantitative effect of residual stress on crack initiation life and crack growth rate can be evaluated.

**Engineering Value**: Provides experimental data support for welding process optimization (post-weld heat treatment, shot peening).

### 7.4 Effect of Welding Defects on Fatigue Performance

By pre-placing different sizes and types of defects (porosity, slag, lack of fusion) in welded specimens combined with DIC fatigue testing, the quantitative effect of defect size and type on fatigue life can be evaluated.

**Engineering Value**: Provides experimental basis for establishing welding quality acceptance standards.

### 7.5 Dissimilar Steel Welded Joint Fatigue Performance Evaluation

Dissimilar steel welded joints (carbon steel-stainless steel, high-strength steel-low-strength steel) require consideration of mechanical property differences between two base metals and weld metal. DIC full-field strain measurement can reveal strain distribution characteristics and crack propagation behavior of dissimilar steel welded joints under cyclic loading.

**Engineering Value**: Provides data support for design and safety assessment of dissimilar steel welded structures.

## 8. Experimental Design and Data Processing Recommendations

For engineering teams introducing DIC into weld fatigue testing for the first time, the following key points should be considered:

| Key Factor | Considerations |
|------------|---------------|
| Speckle Preparation | Speckles must not detach over millions of cycles; epoxy-based coatings recommended |
| Acquisition Strategy | Determine acquisition interval based on fatigue life; longer life requires larger intervals |
| Temperature Compensation | Monitor specimen temperature changes and subtract thermal expansion components |
| Crack Identification | Automatically identify cracks through displacement field discontinuity; set reasonable detection thresholds |
| Data Management | Fatigue test data volumes are enormous; ROI analysis and automated processing workflows recommended |
| Camera Protection | Specimen fracture may occur during fatigue testing; cameras require protective shields |

**Getting Started Recommendation**: Begin with simple base metal fatigue tests (no welds) to verify consistency between DIC measurements and strain gauge data, build confidence, then extend to welded specimens.

## 9. Conclusion

Cyclic loading fatigue testing of welded specimens is a fundamental method for evaluating welded structural safety, but traditional single-point measurement methods can only provide limited information and cannot present complete deformation evolution throughout the weld fatigue process. DIC technology, through its full-field, non-contact, high-precision measurement capabilities, brings a qualitative leap to weld fatigue testing—from "watching a few points" to "watching the full field," from "watching final results" to "watching evolution processes," from "watching crack length" to "watching crack tip strain fields."

Precise identification of crack initiation sites, real-time measurement of crack growth rates, cyclic deformation recording throughout complete damage accumulation, and overall specimen stiffness degradation monitoring—these capabilities make DIC an indispensable technical means for weld fatigue research. The XTDIC system, with its flexible configuration from 2.3MP to 25MP, displacement precision ≤0.01 pixel, and strain range of 0.005%-2000%, is becoming an important tool in the field of weld fatigue testing.

As welded structures develop toward higher strength, lighter weight, and more complex forms, requirements for weld fatigue performance evaluation continue to increase. DIC technology applications in weld fatigue testing will continue to deepen—from laboratory research to engineering verification, from standard specimens to actual welded structures—providing stronger technical support for welded structural safety assessment and life prediction.

</details>

---

*Published in DIC-System-Benchmark*
*Reference: XTOP3D XTDIC system documentation and welded joint fatigue testing application notes*
