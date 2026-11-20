# DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 应用案例*

高温金属拉伸试验中，试验机能记录试样承受的拉力和两端的位移。要判断局部变形从哪里开始，还需要观察两端之间的材料。本文所述案例在多个温度条件下对金属圆棒开展拉伸试验，通过 XTDIC 三维数字图像相关系统测量表面位移与应变，并用红外热像仪同步记录表面温度。公开结果中，局部应变集中在外形出现明显颈缩前已经可以辨认。热像则提供了同一阶段标距段的温度分布。

**本文目录**

- [试验背景与测量目标](#chinese-section-1)
- [试样、设备与实施过程](#chinese-section-2)
- [实测结果怎样解读](#chinese-section-3)
- [把四个加载阶段连起来读](#chinese-section-4)
- [同一套图如何用于不同温度工况的比较](#chinese-section-5)
- [一张能复核结论的结果页应放什么](#chinese-section-6)
- [案例的工程价值](#chinese-section-7)

<a id="chinese-section-1"></a>

## 试验背景与测量目标

一根圆棒的总伸长量相同，中间各段的变形分布可以很不一样。变形较均匀时，各段共同承担伸长；进入局部化阶段后，新增的伸长会更多地集中到较短的一段。高温又给判断增加了一个变量。炉温控制器显示的是控温位置的读数，圆棒工作段的两端与中部仍可能存在温差。要研究变形集中区域与温度的关系，需要知道同一时刻这段材料的位置、伸长程度和表面温度。

<a id="chinese-section-2"></a>

## 试样、设备与实施过程

案例采用金属标准圆棒拉伸试样，在中部工作段喷涂耐高温无机散斑。所谓散斑，是一层随材料表面移动的不规则纹理。双目相机从不同方向拍摄这些纹理。软件通过前后图像识别同一小片材料，重建表面位移，再根据相邻区域位移的差异计算应变。这样既能看试样整体向哪里移动，也能看哪些位置发生了相对伸长。

圆棒安装在配有电阻炉的高温拉伸试验机上。每个温度工况先升温并保温，随后施加拉伸载荷。可见光相机隔着炉窗观察试样，XTDIC 对观察窗引入的折射进行校准。试验机、可见光相机和热像仪通过硬件触发采集，用统一时间戳把载荷曲线、试样照片和热像联系起来。因而在曲线上选择一个加载阶段时，可以查到该阶段实际拍摄的图像。

<a id="chinese-section-3"></a>

## 实测结果怎样解读

| 公开试验记录 | 从图上看什么 | 能回答的工程问题 |
| --- | --- | --- |
| 轴向位移场 | 工作段的位移沿轴向连续变化，所示分布较为对称 | 这一阶段有无明显的单侧偏载迹象？ |
| 主应变场 | 局部区域的拉伸应变逐渐高于邻近区域 | 变形最先集中在哪一段，外形何时才明显收窄？ |
| 红外温度场 | 同一时刻工作段表面的温度分布及其沿轴向的变化 | 哪些区域具备可比的温度条件？ |
| 载荷与位移记录 | 拉力上升、达到峰值及随后变化的时刻 | 各幅云图分别对应哪一段受力过程？ |

以应变图为例，断后查看断口，只能确认最终分离的位置。在拉伸过程中比较相邻时刻的主应变场，则能找到局部伸长开始集中的区域，再用原始照片上的轮廓检查收窄是否在同一处发展。此时调出热像，便能继续追问该处原先已经偏热，还是加载后才出现新的温差。热点与应变带即便接近，也仍需考虑加热条件、表面辐射和空间分辨率，才能解释两者之间的关系。

<a id="chinese-section-4"></a>

## 把四个加载阶段连起来读

**保温末期，先建立一张起始图。** 试验中有两个容易混用的长度。一个是室温装夹时两标记之间的距离，另一个是保温结束、即将施加载荷时的距离。前者适合研究从室温开始的总变化，后者适合研究材料已经处于目标热状态时又被拉长了多少。为后一个问题计算应变时，可以把保温末期的一帧设为参考，同时保存那一帧的温度场。这样跨工况比较时，读者知道各条曲线从哪个状态起算。若要研究升温本身，则应另行保留从室温开始的记录。

**拉伸初期，先读位移，再读应变。** 靠近移动夹头的一侧，位移往往比另一侧大。这并不意味着靠近夹头的材料就伸得最多。相距相等的相邻小段，如果轴向位移增量也近似相等，说明伸长仍分布在较宽的区域。反过来，若沿轴线只有一小段的位移变化突然变陡，才有理由到应变图查找相应的集中带。公开位移图展示了较连续、对称的变化，可作为判断这一步的实物图例。

**局部化阶段，回看同一小段材料。** 可以在未来颈缩处与两侧各取一个小区域，保留这几个区域的轴向应变随加载的变化。若中间区域持续偏离两旁，原始照片又显示两侧轮廓逐渐向内收拢，二者共同支持局部伸长正在发展。此时读热像尤其需要看图例。有些软件逐帧调整色标，上下两幅图即使呈现相似的颜色，温度范围也可能不同。比较某处是否升温，应回到该区域在相同温标下的读数。

**临近断裂，分别确定各种记录的终点。** 照片可能拍到了分离，最后几帧的散斑却已经难以逐片对应。原来跨越裂口的两簇纹理一旦分属两段材料，它们间距的变化就不宜继续按完整材料的局部应变解释。应变曲线可以停在最后可靠的帧，原始照片和载荷曲线则继续显示后续事件。这样保留的记录既能定位断口，也不会给断口两侧强行补出一个应变峰值。

<a id="chinese-section-5"></a>

## 同一套图如何用于不同温度工况的比较

比较两次试验时，若把各自的最后一幅云图并排放置，容易把材料行为与采集终点混在一起。一件试样最后一帧可能仍保留完整轮廓，另一件却已经分离。更有意义的做法是按问题选择比较时刻。想知道在相似整体伸长下哪件试样更早集中，可按工作段平均伸长配对；想了解承载能力达到极限前的变形状态，可各取峰值载荷附近的有效帧。两种选法回答的问题不同，报告中宜注明采用了哪一种。

再看位置。试样装夹后在照片里出现的高度可能不同，直接比较屏幕上的纵坐标，会把装夹位置差异带进结果。可给每个工作段建立从一端到另一端的轴向坐标，标出肩部、可用工作段以及集中区中心。将各组结果按初始工作段长度换算到可比的位置，同时保留实际长度用于解释带宽。若某次集中区落在工作段与肩部过渡位置，还需检查几何与约束影响，不能凭这一件试样推断材料总会从此处失效。

<a id="chinese-section-6"></a>

## 一张能复核结论的结果页应放什么

结果页可围绕“应变集中何时演变为可见颈缩”这个判断来组织。左侧保留载荷曲线和选帧标记，右侧依次排出保温末期、集中初期和清楚收窄时的原始照片、应变场与热像。统一试样朝向，在每张图上标出同一段材料，另用阴影表示失去跟踪或超出热像视野的位置。读者沿列比较能看到变化经过，沿行比较则能检查不同相机看到的是否是同一区域。

若出现“拉力峰值之后才看清轮廓收窄，但峰值之前应变带已经形成”，这几项记录仍可同时成立。峰值属于整根试样的受力过程，轮廓受像素分辨能力限制，应变图又取决于局部花纹对应的范围。将三者的观测时刻写开，比给出一个没有判据的“损伤起点”更有价值。这里是对同类试验结果页的解读方法，具体时刻应从对应试样的原始记录读取。

### 一组材料怎样从单件案例走向性能比较

如果实验室要比较两种热处理状态，可以先把“哪一种更能承受拉力”和“哪一种更能分散局部伸长”拆成两个问题。前一个问题用载荷及试样初始截面说明，后一个问题用相同工作段、相同热参考状态下的应变场说明。若两组圆棒直径不同，直接比较最大拉力会把尺寸差异带进材料判断。若两组有效光学标距不同，直接比较断前平均应变又会改变参与平均的材料长度。让样件制备记录与云图一起进入分析，就能在开始比较前发现这两类差异。

另一项值得记录的是断口相对于有效视野的位置。假设一件试样恰好在视野中央形成颈缩，另一件却在观察区之外收窄，后一件的应变图可能显得格外均匀。这个结果只说明相机看见的范围内没有同等明显的集中带。若研究目的包括失效位置，需先用整体轮廓或断后试样确认断口是否落在共同覆盖区。根据已有视场作出不同等级的结论，比将失去观察的试样当成“抗局部化能力更强”更准确。

对于想复用案例做材料比较的读者，优先查阅原文中的三组图。位移图用来检查加载是否出现明显不对称，主应变图用来寻找何时开始局部伸长，温度图用来判断被比较区域的热状态是否相近。三项条件逐项满足之后，再讨论不同材料或工艺的差别，才有机会把试验条件的影响和材料表现区分开。

<a id="chinese-section-7"></a>

## 案例的工程价值

对于高温材料筛选，这套记录可以帮助区分“整体伸长相近、局部变形分布不同”的试样。对于材料模型验证，实验室可以保留完整的应变分布和温度历程，让模型同时接受整体拉力与局部变形的检验。若研究目标是裂纹萌生或试样内部损伤，则还需要与断口、截面或其他独立观察对应。就本案例而言，证据最明确的结果是记录到了可见表面的应变集中、后续颈缩及其对应时刻的温度场。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [223 · 高温材料热力耦合测试方案：XTDIC 联动红外热像实现载荷、温度与应变同步测量](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-timing.md#chinese-version)
- [224 · 高温材料局部损伤监测：XTDIC 全场应变与红外温度场联合定位方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#chinese-version)
- [225 · 高温炉内非接触应变测量：XTDIC 光学测试系统的配置与应用](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#chinese-version)
- [226 · 高温金属颈缩与失效研究：XTDIC 全场应变测量揭示局部变形演化](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#chinese-version)
- [227 · 高温材料本构与有限元验证：XTDIC 联动红外热像的多场试验方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#chinese-version)

</details>

<details>
<summary><b>English · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars</b></summary>

<a id="english-version"></a>

# XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars

*Measuring deformation and damage at elevated temperature · Application case*

A tensile machine measures force and travel between the ends of a hot specimen. Locating the onset of concentrated deformation requires observations between those ends. In the published experiment, metal round bars were tested in tension at several temperatures. XTDIC stereo digital image correlation measured surface displacement and strain, while an infrared camera recorded surface temperature. Concentrated strain could be identified before necking was obvious in the outline. Thermograms supplied the temperature distribution over the gauge section at the corresponding stages.

**Contents**

- [Measurement objective](#english-section-1)
- [Specimen and experimental arrangement](#english-section-2)
- [Reading the reported results](#english-section-3)
- [Reading the loading history in four stages](#english-section-4)
- [Comparing tests at different temperatures](#english-section-5)
- [A results page that permits a second reading](#english-section-6)
- [Engineering use](#english-section-7)

<a id="english-section-1"></a>

## Measurement objective

Two bars with the same total extension can distribute that extension differently. During relatively uniform stretching, neighbouring lengths share the deformation. As localization develops, a shorter length accommodates a larger share of each additional increment. Heating introduces another variable. A furnace controller reports conditions at its sensing location, while the specimen centre and ends can differ in temperature. Relating temperature to localization therefore requires the position, stretch and surface temperature of the same region at the same time.

<a id="english-section-2"></a>

## Specimen and experimental arrangement

The working length of a standard round tensile specimen carried a heat-resistant inorganic speckle pattern. Stereo cameras viewed this irregular texture from different angles. Matching patches in successive images reconstructed surface displacement. Differences in displacement between neighbouring patches supplied strain, allowing both motion and relative extension to be examined.

An electric resistance furnace surrounded the specimen in a tensile machine. Each run included heating and a hold at the target condition before loading. XTDIC accounted for refraction through the observation window in the visible-light measurement. A hardware trigger and shared timestamps linked machine records, visible images and thermograms. A stage selected on the load curve could therefore be traced to actual exposures from that part of the test.

<a id="english-section-3"></a>

## Reading the reported results

| Record | Feature to examine | Engineering question |
| --- | --- | --- |
| Axial displacement | A continuous, broadly symmetric distribution in the reported field | Is there visible evidence of one-sided loading at this stage? |
| Principal strain | A region develops higher tensile strain than its neighbours | Where does stretch concentrate, and when does narrowing become visible? |
| Surface temperature | Temperature across and along the observed gauge section | Which regions experienced comparable thermal conditions? |
| Force and travel | Rising load, peak force and subsequent changes | Which stage of loading does each image represent? |

The broken specimen identifies the final separation site. Successive strain maps make it possible to locate concentrated extension earlier and to compare it with the evolving outline in the photographs. The corresponding thermograms can then show whether a region was already warmer before loading or developed an additional temperature difference during the pull. Interpreting a nearby hot spot requires attention to heating conditions, surface radiation and the spatial resolution of the thermal view.

<a id="english-section-4"></a>

## Reading the loading history in four stages

**End of the hot hold.** Two gauge lengths may appear in the records. One is measured when the bar is gripped at room temperature. The other is measured just before force is applied at the test temperature. The first is useful for total change from the cold condition. The second serves extension caused by loading from an already hot state. For the latter question, use an end-of-hold image as the strain reference and retain its thermogram. For expansion during heating, retain the separate sequence beginning at room temperature.

**Early loading.** Read displacement before strain. The end nearest the moving grip may travel farthest. That observation alone says little about which part stretched most. Similar displacement increments over successive equal lengths indicate distributed extension. A steep change concentrated in one short length gives a reason to inspect that region in the strain map. The continuous and broadly symmetric displacement field in the published case illustrates what to look for at this step.

**Localization.** Select a small region at the eventual neck and neighbouring regions on either side. Follow their axial strains during loading. A persistent departure of the middle trace, together with inward movement of both specimen edges, supports developing local extension. Check the legend before interpreting the corresponding thermograms. Automatic rescaling can give similar colours to different temperatures in successive frames. Use readings on a common temperature scale to assess warming.

**Approaching fracture.** A photograph can capture separation after some speckles have become unrecognisable. Once a crack separates two patches, their increasing distance can include crack opening. Treating it all as strain in an intact piece of metal would create a misleading peak. End the local strain history at its last valid frame and retain later photographs and force records on their own timelines.

<a id="english-section-5"></a>

## Comparing tests at different temperatures

The final strain map from each test may represent quite different states. One image can contain an intact bar while another already shows separation. Select stages according to the comparison. Match average gauge extension to ask which specimen localized earlier at comparable overall stretch. Select valid frames around each specimen’s peak force to assess deformation near maximum load. Record the criterion so the comparison can be repeated.

Mounting position can also change between runs. An image row is consequently a poor coordinate for comparing localization sites. Define a coordinate along each initial gauge section and mark its ends, shoulders and localization centre. Position expressed as a fraction of the initial gauge length supports comparisons between specimens, while the physical length retains the meaning of band width. A band near a shoulder warrants investigation of the transition geometry and constraints before generalising about the material.

<a id="english-section-6"></a>

## A results page that permits a second reading

Organise a page around the question of when concentrated strain became visible narrowing. Put the force curve and selected times beside the raw photographs, strain fields and thermograms from the end of the hold, early localization and visible narrowing. Keep orientation consistent, identify the same material region and shade areas of tracking loss or missing thermal coverage. Reading across time shows the sequence. Reading across instruments checks the correspondence.

A neck might first be visible after peak force while a strain band is already detectable before the peak. Those observations can coexist. The peak refers to the load on the specimen as a whole, edge visibility depends on optical resolution, and strain comes from the motion of finite patches. Reporting the three observations with their criteria is more informative than assigning a single unspecified damage-onset time. Exact times would have to come from the specimen’s original records.

### Moving from one specimen to a material comparison

For two heat treatments, separate load capacity from the ability to distribute extension. Address the first with force and initial cross-section, and the second with strain fields over comparable gauge lengths and hot reference states. Different diameters confound a comparison of peak forces. Different optical gauge lengths change how much material contributes to average pre-fracture strain. Keep specimen preparation records beside the maps to detect these differences early.

Also locate the fracture relative to the shared field of view. A neck at the centre may be easy to see in one specimen while a second neck develops outside the observed area. A uniform-looking map of the second gauge section establishes only what happened inside the view. An overall outline or post-test inspection can establish whether both failure sites were actually covered before resistance to localization is compared.

The three sets of published maps offer a useful reading order for this purpose. Displacement reveals gross asymmetry, principal strain identifies localized extension, and temperature helps establish comparable thermal states. Only then is it productive to discuss differences between materials or processes.

<a id="english-section-7"></a>

## Engineering use

For material screening, the records can distinguish similar overall elongation from similar distributions of local strain. For model assessment, measured force, strain fields and surface temperature histories offer separate comparisons. A claim about crack initiation or subsurface damage requires further evidence, such as fracture-surface or section observations. The clearest result in this case is the record of visible-surface strain concentration, subsequent necking and the temperature field at corresponding times.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [223 · Coupled Thermal and Mechanical Testing with Synchronized XTDIC and Infrared Thermography](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-timing.md#english-version)
- [224 · Localizing High-Temperature Material Damage with XTDIC Strain Fields and Thermography](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#english-version)
- [225 · Configuring XTDIC for Non-Contact Strain Measurement Inside High-Temperature Furnaces](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#english-version)
- [226 · Investigating Necking and Failure of Hot Metals with XTDIC Full-Field Strain Measurement](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#english-version)
- [227 · Material Calibration and Finite Element Validation with XTDIC and Infrared Thermal Measurements](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#english-version)

</details>
