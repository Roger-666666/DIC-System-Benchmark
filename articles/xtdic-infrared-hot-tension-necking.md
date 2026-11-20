# 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 原理与应用*

颈缩是拉伸试样在某一局部逐渐变细的现象。对于高温金属圆棒，颈缩位置关系到后续断裂发生在哪一段，也是研究材料局部变形能力的重要依据。XTDIC 高温拉伸案例显示，在圆棒外形明显收窄之前，主应变图上已经可以分辨出变形集中的区域。应变集中、外形颈缩与最终断裂各有对应的观测证据，标记这几个阶段时需要说清各自采用的判据。

## 为什么平均伸长容易遗漏局部变化

若在标距段的两端做标记，拉伸前后测量两点的距离变化，就能得到这段材料的平均伸长信息。局部化初期，只有很短的一段比周围伸得快，其变化在沿整段求平均时会被摊薄。两件试样即使达到相近的总伸长，也可能在不同位置形成不同宽度的集中区。要了解损伤在何处发展，需要把测量范围从两端之间的一个平均值，扩展到可见表面的许多小区域。

数字图像相关法跟踪表面花纹的运动，从局部位移变化计算应变。主应变描述局部沿主方向的拉伸或压缩程度，其中最大主应变有助于寻找伸长最为集中的区域。读图时应查看图例与方向定义，并让不同时刻的图使用相同色标。若每张图都把本帧最大值显示为红色，仅凭红色面积很难比较集中程度是否加重。

## 从试验信号识别变形阶段

| 试验阶段 | 优先观察的证据 | 可以作出的判断 |
| --- | --- | --- |
| 较均匀的拉伸 | 轴向位移沿标距连续变化，应变分布较平缓 | 观察范围内伸长较为分散 |
| 局部应变集中 | 同一区域连续多帧比两旁伸得更快 | 可将该区域列为后续颈缩的观察对象 |
| 可见颈缩 | 原始照片上局部宽度持续减小，且与邻近区域拉开差异 | 可以定位可见表面的收窄区域 |
| 接近断裂 | 轮廓继续演变，部分散斑可能无法匹配 | 标明最后可靠的应变帧，另存断裂照片 |

## 常见问题

**载荷开始下降，能直接定位颈缩吗？** 载荷峰值能确定值得回看的时段。要找位置，还需要这一时段的应变场和试样轮廓。比较轮廓时可跟随同一小段材料，避免把材料沿轴向移动误当成局部宽度变化。

**热像上的亮点能作为颈缩起点吗？** 亮点可以协助选择复查区域。识别颈缩仍要看材料是否局部收窄，并核对温度差在加载前是否已经存在。热像的意义在于为已定位的变形区域补充热状态。

**局部应变大就代表出现了内部裂纹吗？** 表面应变图提供的是表面运动信息。要确认内部裂纹或损伤机制，还要结合截面、断口或其他独立检查。对于材料筛选，可以先比较各试样的集中位置与发展过程；对于失效分析，则应把这些记录与断后证据相对应。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [227 · 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#chinese-version)

</details>

<details>
<summary><b>English · Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain</b></summary>

<a id="english-version"></a>

# Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain

*Measuring deformation and damage at elevated temperature · Measurement principles*

Necking is the progressive local narrowing of a specimen under tension. Its location in a hot round bar matters both to the eventual fracture site and to the assessment of local deformability. In the published XTDIC test, strain concentration could be identified before narrowing became obvious in the outline. Localized strain, a visible neck and final fracture each have their own observable evidence.

## Why average extension can miss an early change

Two marks at the ends of a gauge length give an average measure of extension between them. Early in localization, a short section stretches faster than its surroundings. Averaging across the gauge length dilutes its contribution. Two specimens with similar overall extension can develop concentrated bands in different locations and over different widths. Studying that process requires observations across many small regions on the visible surface.

Digital image correlation tracks surface texture and estimates strain from spatial changes in displacement. Principal strains describe extension or contraction along local principal directions. The maximum principal strain helps locate regions of concentrated stretch. Interpretation requires the plotted quantity and a consistent colour scale. If every map displays its own highest value in red, red area alone gives a poor comparison across time.

## Evidence for successive stages

| Stage | Evidence to examine | Supported interpretation |
| --- | --- | --- |
| Relatively uniform tension | Continuous axial displacement and broadly distributed strain | Extension is shared across the observed length |
| Strain localization | The same patch stretches faster than adjacent patches in successive frames | A region to follow for later necking |
| Visible necking | Local width persistently decreases relative to neighbouring sections | The visible narrowing can be located |
| Approaching fracture | The outline evolves and some speckles may cease to match | Identify the last reliable strain map and retain the fracture image separately |

## Frequently asked questions

**Does a fall in load locate the neck?** Peak force identifies a time interval worth reviewing. Strain fields and specimen outlines locate the region. Following the same material section avoids confusing axial motion with a change in local width.

**Does a bright thermal spot mark necking onset?** It can direct attention to a region. Identification still requires evidence of local narrowing and consideration of any temperature difference present before loading. Thermograms describe the thermal state of the identified region.

**Does high local strain establish an internal crack?** A surface strain map describes surface motion. Sectioning, fracture-surface observations or another independent inspection are needed for an internal crack or damage mechanism. Material screening can compare localization histories, while a failure investigation can connect those histories to post-fracture evidence.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [227 · Validating a Hot Tensile Simulation with XTDIC Strain Fields, Thermograms and Load Curves](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-validation.md#english-version)

</details>
