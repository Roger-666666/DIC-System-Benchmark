# DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 应用案例*

高温金属拉伸试验中，试验机能记录试样承受的拉力和两端的位移。要判断局部变形从哪里开始，还需要观察两端之间的材料。本文所述案例在多个温度条件下对金属圆棒开展拉伸试验，通过 XTDIC 三维数字图像相关系统测量表面位移与应变，并用红外热像仪同步记录表面温度。公开结果中，局部应变集中在外形出现明显颈缩前已经可以辨认。热像则提供了同一阶段标距段的温度分布。

## 试验背景与测量目标

一根圆棒的总伸长量相同，中间各段的变形分布可以很不一样。变形较均匀时，各段共同承担伸长；进入局部化阶段后，新增的伸长会更多地集中到较短的一段。高温又给判断增加了一个变量。炉温控制器显示的是控温位置的读数，圆棒工作段的两端与中部仍可能存在温差。要研究变形集中区域与温度的关系，需要知道同一时刻这段材料的位置、伸长程度和表面温度。

## 试样、设备与实施过程

案例采用金属标准圆棒拉伸试样，在中部工作段喷涂耐高温无机散斑。所谓散斑，是一层随材料表面移动的不规则纹理。双目相机从不同方向拍摄这些纹理。软件通过前后图像识别同一小片材料，重建表面位移，再根据相邻区域位移的差异计算应变。这样既能看试样整体向哪里移动，也能看哪些位置发生了相对伸长。

圆棒安装在配有电阻炉的高温拉伸试验机上。每个温度工况先升温并保温，随后施加拉伸载荷。可见光相机隔着炉窗观察试样，XTDIC 对观察窗引入的折射进行校准。试验机、可见光相机和热像仪通过硬件触发采集，用统一时间戳把载荷曲线、试样照片和热像联系起来。因而在曲线上选择一个加载阶段时，可以查到该阶段实际拍摄的图像。

## 实测结果怎样解读

| 公开试验记录 | 从图上看什么 | 能回答的工程问题 |
| --- | --- | --- |
| 轴向位移场 | 工作段的位移沿轴向连续变化，所示分布较为对称 | 这一阶段有无明显的单侧偏载迹象？ |
| 主应变场 | 局部区域的拉伸应变逐渐高于邻近区域 | 变形最先集中在哪一段，外形何时才明显收窄？ |
| 红外温度场 | 同一时刻工作段表面的温度分布及其沿轴向的变化 | 哪些区域具备可比的温度条件？ |
| 载荷与位移记录 | 拉力上升、达到峰值及随后变化的时刻 | 各幅云图分别对应哪一段受力过程？ |

以应变图为例，断后查看断口，只能确认最终分离的位置。在拉伸过程中比较相邻时刻的主应变场，则能找到局部伸长开始集中的区域，再用原始照片上的轮廓检查收窄是否在同一处发展。此时调出热像，便能继续追问该处原先已经偏热，还是加载后才出现新的温差。热点与应变带即便接近，也仍需考虑加热条件、表面辐射和空间分辨率，才能解释两者之间的关系。

## 案例的工程价值

对于高温材料筛选，这套记录可以帮助区分“整体伸长相近、局部变形分布不同”的试样。对于材料模型验证，实验室可以保留完整的应变分布和温度历程，让模型同时接受整体拉力与局部变形的检验。若研究目标是裂纹萌生或试样内部损伤，则还需要与断口、截面或其他独立观察对应。就本案例而言，证据最明确的结果是记录到了可见表面的应变集中、后续颈缩及其对应时刻的温度场。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [223 · 高温拉伸同步采集方法：如何对齐 XTDIC 应变、红外温度与载荷记录](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-timing.md#chinese-version)
- [224 · 高温拉伸热区定位：红外热像与 XTDIC 应变场的三种对照方法](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#chinese-version)
- [225 · 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#chinese-version)
- [226 · 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#chinese-version)
- [227 · 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#chinese-version)

</details>

<details>
<summary><b>English · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars</b></summary>

<a id="english-version"></a>

# XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars

*Measuring deformation and damage at elevated temperature · Application case*

A tensile machine measures force and travel between the ends of a hot specimen. Locating the onset of concentrated deformation requires observations between those ends. In the published experiment, metal round bars were tested in tension at several temperatures. XTDIC stereo digital image correlation measured surface displacement and strain, while an infrared camera recorded surface temperature. Concentrated strain could be identified before necking was obvious in the outline. Thermograms supplied the temperature distribution over the gauge section at the corresponding stages.

## Measurement objective

Two bars with the same total extension can distribute that extension differently. During relatively uniform stretching, neighbouring lengths share the deformation. As localization develops, a shorter length accommodates a larger share of each additional increment. Heating introduces another variable. A furnace controller reports conditions at its sensing location, while the specimen centre and ends can differ in temperature. Relating temperature to localization therefore requires the position, stretch and surface temperature of the same region at the same time.

## Specimen and experimental arrangement

The working length of a standard round tensile specimen carried a heat-resistant inorganic speckle pattern. Stereo cameras viewed this irregular texture from different angles. Matching patches in successive images reconstructed surface displacement. Differences in displacement between neighbouring patches supplied strain, allowing both motion and relative extension to be examined.

An electric resistance furnace surrounded the specimen in a tensile machine. Each run included heating and a hold at the target condition before loading. XTDIC accounted for refraction through the observation window in the visible-light measurement. A hardware trigger and shared timestamps linked machine records, visible images and thermograms. A stage selected on the load curve could therefore be traced to actual exposures from that part of the test.

## Reading the reported results

| Record | Feature to examine | Engineering question |
| --- | --- | --- |
| Axial displacement | A continuous, broadly symmetric distribution in the reported field | Is there visible evidence of one-sided loading at this stage? |
| Principal strain | A region develops higher tensile strain than its neighbours | Where does stretch concentrate, and when does narrowing become visible? |
| Surface temperature | Temperature across and along the observed gauge section | Which regions experienced comparable thermal conditions? |
| Force and travel | Rising load, peak force and subsequent changes | Which stage of loading does each image represent? |

The broken specimen identifies the final separation site. Successive strain maps make it possible to locate concentrated extension earlier and to compare it with the evolving outline in the photographs. The corresponding thermograms can then show whether a region was already warmer before loading or developed an additional temperature difference during the pull. Interpreting a nearby hot spot requires attention to heating conditions, surface radiation and the spatial resolution of the thermal view.

## Engineering use

For material screening, the records can distinguish similar overall elongation from similar distributions of local strain. For model assessment, measured force, strain fields and surface temperature histories offer separate comparisons. A claim about crack initiation or subsurface damage requires further evidence, such as fracture-surface or section observations. The clearest result in this case is the record of visible-surface strain concentration, subsequent necking and the temperature field at corresponding times.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [223 · Synchronizing XTDIC Strain, Infrared Temperature and Load in Hot Tensile Tests](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-timing.md#english-version)
- [224 · Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#english-version)
- [225 · High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#english-version)
- [226 · Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#english-version)
- [227 · Validating a Hot Tensile Simulation with XTDIC Strain Fields, Thermograms and Load Curves](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#english-version)

</details>
