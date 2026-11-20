# 高温拉伸热区定位：红外热像与 XTDIC 应变场的三种对照方法

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温拉伸热区定位：红外热像与 XTDIC 应变场的三种对照方法</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 方法比较*

分析高温金属圆棒时，“工作段中部偏热”“颈缩区附近偏热”和“温度最高点与最大应变点重合”是三种精细程度不同的结论。XTDIC 与红外相机分别从自己的视角观察圆棒。时间上同步以后，空间上选择哪一种对照方法，取决于需要把结论落实到整段、某一块材料，还是某一个局部峰值。

## 三种方法分别适合回答什么问题

| 方法 | 读取对象 | 适合的任务 | 主要限制 |
| --- | --- | --- | --- |
| 按工作段分区 | 将两幅图各自分成靠近两端和中部的区域 | 检查保温后哪一段存在温差 | 难以确定窄带或峰值的位置 |
| 固定位置对照 | 在相机坐标下持续观察同一位置 | 分析炉内指定位置的温度随加载怎样变化 | 拉伸中经过此处的材料会改变 |
| 跟随材料区域 | 用 DIC 跟踪一块材料，把各时刻的位置对应到热像 | 研究最终颈缩区的温度与应变历程 | 需要空间配准，并验证跟踪有效性 |

## 以圆棒中部的一条应变带为例

当研究任务是确认试样是否已经均温，把工作段分区通常就能提供可读的结果。此时更有意义的是比较中部与端部各自的温度范围，并检查差异能否在保温期持续观察到。若问题转为“后来形成颈缩的材料，在开始集中伸长前是否已经偏热”，就需要改变取样方式。工作段会随拉伸伸长，屏幕中间的光标即使没动，经过它的表面材料也可能已经换了。

较细致的做法是先在 DIC 图像中跟踪材料区域，再给热像找到相应的位置。这一步称为空间配准。它需要让两套成像系统对同一物理位置建立对应，并用独立的可识别位置检验偏差。圆棒边缘弯曲，两台相机能同时看见的表面有限；如果目标区域转出其中一个镜头的有效视野，后续帧就应标记为无法比较。

## 怎么判断“重合”这个词用得是否合适

热像上一个有效测量区域可能覆盖应变带和两侧材料。此时热像记录包含邻近表面的贡献，最亮位置也会受观察范围和分辨率影响。如果两个峰值之间的距离与配准偏差相当，较为稳妥的表述是“在同一局部区域观察到温度与应变变化”。要精确报告峰值间距，则应同时交代空间尺度、有效视野和定位偏差。

公开试验提供了同步位移、应变和温度记录。上面的三种方法是利用这类记录开展分析时可以选择的路径。做均温检查可以采用分区比较；追溯颈缩区的材料经历，应采用跟随材料的区域；评估细小热点时，则需要先确认现有热像能否分辨目标。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [225 · 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#chinese-version)

</details>

<details>
<summary><b>English · Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields</b></summary>

<a id="english-version"></a>

# Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields

*Measuring deformation and damage at elevated temperature · Method comparison*

“The middle of the gauge section was warmer,” “the neck region was warmer,” and “the temperature and strain peaks coincided” require different levels of spatial evidence. XTDIC and infrared cameras observe a round bar from their respective viewpoints. Once the records are synchronized, the choice of spatial comparison depends on whether the conclusion concerns a section, a particular material patch or a local maximum.

## Comparing the available methods

| Method | What is sampled | Suitable question | Main limitation |
| --- | --- | --- | --- |
| Gauge-section zones | End and central regions defined in both views | Where does a temperature difference persist after the hold? | Limited localization of a narrow band |
| Fixed spatial region | The same location in camera coordinates | How does temperature at a furnace location evolve? | Material can pass through the region |
| Material-following region | A surface patch tracked by DIC and located in each thermogram | What history did the future neck experience? | Requires registration and valid tracking |

## Applying the distinction to a strain band

For a temperature-uniformity check, splitting the gauge length into zones can be sufficient. Compare the temperature ranges near the centre and ends and examine whether the difference persists during the hold. Asking whether the material that eventually necked was already warm requires another sampling strategy. During tension, the gauge section extends. A stationary cursor in the middle of the screen can sample a succession of different pieces of metal.

A material-following comparison tracks a patch in DIC and finds its counterpart in the thermal image. This spatial correspondence is called registration. Features at known common locations establish the mapping, and independent features can test its error. Curvature limits how much of the round bar both cameras can see. When a patch moves out of either usable view, the comparison ends for those frames.

## Choosing the precision of the claim

A thermally resolved area may include a narrow strain band and the surface on either side. Neighbouring radiation contributes to the reading, and the position of the apparent maximum depends on spatial resolution. When the separation between two peaks is comparable to registration error, the evidence supports changes in the same local region. Reporting a peak-to-peak distance also calls for the spatial scale, valid common field of view and localization error.

The published experiment provides synchronized displacement, strain and temperature records. The three methods above describe possible analyses of such records. Zonal comparison serves thermal uniformity studies. Tracking serves material histories. Investigating a small hot spot first requires evidence that the thermal view resolves the target.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [225 · High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#english-version)

</details>
