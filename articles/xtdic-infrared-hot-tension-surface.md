# 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 隔着炉窗做高温 DIC 与红外测温：圆棒散斑、光路与表面校核方案</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 试验方案*

高温炉中的同一根金属圆棒，对两套相机提出了不同要求。XTDIC 需要能随材料移动并持续辨认的表面纹理；热像仪需要知道有多少红外辐射由试样发出，又有多少来自反射或观察窗本身。配置联合试验时，要把散斑、可见光光路和红外光路分别核查，再决定哪些区域可以同时用于应变和温度分析。

## 测试难点来自哪里

圆棒表面光滑，拉伸前后相邻位置在可见光照片里可能很相似。升温还会改变亮度和图案对比度，使原本可跟踪的区域变得模糊。炉窗的折射会影响双目重建时物点的位置；热像仪工作在不同于可见光的波段，一块肉眼透明的窗口，其红外透过率仍需按实际波段确认。这几种干扰作用在不同环节，单纯增加照明无法一并解决。

## XTDIC 案例怎样建立可用的变形记录

公开试验在圆棒工作段制备耐高温无机散斑，让双目相机在加载期间跟踪同一片表面。案例还说明了针对炉窗的折射校准。实际部署时，应在与试验一致的观察条件下检查标定和成像，保留保温阶段的照片作参考。若试样尚未加载，图像中却出现移动的波纹，应先排查热气流等光学因素。若只有一小块花纹开裂或剥落，则要在后续分析中单独标记这块区域。

## 同一表面怎样用于红外测温

热像仪把接收到的辐射换算成温度，需要考虑表面发射率，也就是材料表面在该波段发射热辐射的能力。涂层和裸露金属即使同温，也可能给出不同的辐射信号。若涂层边缘在加载前就呈现明显温差，加载后出现相似边界时，直接把它归因于塑性发热就缺少依据。

| 观察到的现象 | 可以安排的核查 | 对分析区域的处理 |
| --- | --- | --- |
| 保温时散斑局部脱落 | 回看原始照片，检查时间上的连续性 | 标记失去跟踪的区域和起始帧 |
| 热像明暗边界与涂层边缘一致 | 对照加载前热像，检查发射率设置和独立温度参考 | 单独评估该处测温可信度 |
| 两个镜头对圆棒边缘的可见范围不同 | 对照轮廓与相机视角 | 取两路都能可靠观测的表面范围 |

## 方案适用边界

上述核查适用于透过观察口开展的高温拉伸，也适用于更换散斑工艺、窗口或热像仪之后的复测。交付结果时，保留一张加载前的可见光图、一张对应热像，以及可用于联合分析的区域说明，比只给出最后一幅彩色云图更方便复核。公开案例确认了散斑处理、炉窗校准及同步采集；表中的异常是方案设计时需要考虑的情形，不代表该案例实际发生过。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [226 · 高温金属拉伸的颈缩识别：从平均伸长到 XTDIC 全场主应变分析](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#chinese-version)

</details>

<details>
<summary><b>English · High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks</b></summary>

<a id="english-version"></a>

# High-Temperature DIC and Thermography Through Furnace Ports: Specimen Preparation and Optical Checks

*Measuring deformation and damage at elevated temperature · Test configuration*

The same hot round bar places different demands on its cameras. XTDIC needs a recognisable surface texture that moves with the material. A thermal camera needs information about radiation emitted by the specimen, reflected from its surroundings and transmitted or emitted by the window. A joint test therefore calls for checks on speckles and on each optical path before selecting an area for combined strain and temperature analysis.

## Sources of difficulty

Adjacent points on a smooth bar can look alike in visible photographs. Heating changes brightness and contrast, and a trackable region can become indistinct. Window refraction affects the location reconstructed by the stereo system. A window transparent to the eye also needs a transmission check in the infrared camera’s wavelength band. These effects enter at different stages of the measurement.

## Establishing a deformation record

The published experiment used heat-resistant inorganic speckles on the gauge section and corrected for refraction through the furnace window. In an implementation, check calibration and image quality through the actual observation path and keep images from the hot hold as a reference. Ripples crossing a stationary, unloaded specimen warrant a check for optical disturbances such as moving hot air. Local cracking or loss of the speckle coating calls for marking the affected region and frames.

## Using the surface for infrared thermometry

Converting received radiation into temperature requires the surface emissivity in the relevant wavelength band. A coating and exposed metal can emit different amounts of radiation at the same temperature. If an apparent temperature step already follows a coating edge before loading, a similar boundary during pulling needs additional evidence before it can be attributed to plastic heating.

| Observation | Check | Treatment in analysis |
| --- | --- | --- |
| Local speckle loss during the hold | Inspect the original image sequence | Mark where and when tracking was lost |
| Thermal contrast follows a coating edge | Review the unloaded thermogram, emissivity and independent temperature reference | Assess local temperature reliability separately |
| The cameras see different portions of the curved edge | Compare outlines and viewing angles | Use the common observable surface |

## Scope of the arrangement

These checks apply to tensile tests through furnace ports and to repeat tests after a change of coating, window or thermal camera. A pre-load photograph, its matching thermogram and a record of the valid common area make final maps easier to audit. The public case documents the speckle preparation, window calibration and synchronous acquisition. The anomalies in the table are implementation considerations, not reported events in that specimen.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [226 · Identifying Necking in Hot Metal: From Average Elongation to Full-Field Principal Strain](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#english-version)

</details>
