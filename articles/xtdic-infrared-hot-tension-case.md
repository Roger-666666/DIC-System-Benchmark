# 高温金属拉伸时怎样同时看见温度与变形？XTDIC 与红外热像联动试验

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

**关键词**　高温拉伸、数字图像相关、红外热成像、应变局部化

同一根金属试样受拉时，拉力可以从试验机读出，最先集中变形的位置却需要在标距段里寻找。XTDIC 公开案例在不同温度条件下开展金属拉伸，用双目数字图像相关（DIC）记录表面运动，再按时间戳与红外热像记录对照。这样可以回到颈缩前的一帧，查看当时哪段材料已经拉长，以及对应区域的表面温度怎样变化。

## 两幅图各自测到了什么

XTDIC 从可见光图像中跟踪随试样移动的散斑，根据标定后的双目图像重建表面位移，再由邻域位移变化求应变。红外热像仪接收辐射，结合表面发射率和光路条件换算温度。前者的空间尺度取决于相关计算与应变拟合范围，后者受热像采样与光学分辨能力约束。一个很窄的颈缩区可能在两幅图上呈现不同宽度。

## 怎样读一次拉伸记录

先在加载前的稳定温度段取参考帧，再沿拉伸轴观察应变是否从较宽区域向窄带集中。回到相同时段的原始照片，查找标距段轮廓收窄的位置。随后提取该材料区域和邻近区域的温度历程，并标记载荷变化。若热点跟着收窄处移动，可以报告两种表面现象的时空对应；要解释热量来源，还要考虑炉内加热、传热与表面状态。

## 试验报告值得保留哪一页

把加载前、局部化发展期和断裂前最后一个相关有效时刻排成一页。每列保留原始轮廓、轴向应变图、同步热像与载荷位置，旁注参考帧及缺测范围。这一页既能交代试样经历了什么，也让读者判断“温度与应变同时集中”的说法能得到多细的证据支持。

## 专题阅读

- [223 · 高温拉伸中温升和应变集中谁先出现？XTDIC 与红外热像的时间同步](xtdic-infrared-hot-tension-timing.md#chinese-version)
- [224 · 红外热点与应变带是否落在同一处？高温拉伸的双场空间配准](xtdic-infrared-hot-tension-registration.md#chinese-version)
- [225 · 高温散斑会改变红外读数吗？XTDIC 联动测试的表面核查](xtdic-infrared-hot-tension-surface.md#chinese-version)
- [226 · 高温拉伸怎样识别颈缩起点？结合 XTDIC 局部应变、轮廓与热像](xtdic-infrared-hot-tension-necking.md#chinese-version)
- [227 · 热力耦合仿真如何用 XTDIC 和红外热像验证？从温度边界到应变残差](xtdic-infrared-hot-tension-validation.md#chinese-version)

案例来源：[原文入口](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验说明](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

</details>

---

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Measuring Temperature and Deformation Together in a Hot Tensile Test with XTDIC and Infrared Thermography

**Keywords**　Hot tensile testing, digital image correlation, infrared thermography, strain localization

A load cell records the force on a hot metal coupon. Locating the first concentration of deformation requires observations along its gauge section. In the published XTDIC case, stereo digital image correlation (DIC) followed the surface of metal specimens in tensile tests at different temperatures. Timestamps linked deformation records with infrared images. An analyst can revisit a frame before necking and ask which material region was already stretching and how its surface temperature evolved.

## What each field measures

XTDIC tracks visible speckles attached to the specimen, reconstructs surface displacement from calibrated stereo views and estimates strain over a neighborhood. A thermal camera measures radiation and uses surface emissivity and optical-path information to estimate temperature. Strain fitting and thermal imaging have different spatial resolutions. The same narrow neck can therefore have different apparent widths in the two maps.

## Reading the tensile history

Choose a reference image during the stable hot interval before loading. Follow the axial strain field as deformation concentrates into a band, then inspect the specimen outline for narrowing. Extract temperature histories from that material region and an adjacent region, and mark the corresponding load history. A hot region traveling with the neck supports a spatial and temporal association. Interpreting the heat source also requires information about external heating, heat transfer and the surface condition.

## A useful case-report page

Arrange the unloaded hot state, developing localization and last valid pre-fracture frame in columns. For each, show the original outline, axial strain map, thermogram and position on the load curve. Record the reference frame and missing areas. This layout lets a reader assess the timing and spatial detail behind a claim that temperature and strain concentrated together.

## Further reading

- [223 · Which Came First in Hot Tension? Synchronizing XTDIC Strain and Infrared Temperature Histories](xtdic-infrared-hot-tension-timing.md#english-version)
- [224 · Do the Hot Spot and Strain Band Coincide? Spatial Registration in Hot Tensile Testing](xtdic-infrared-hot-tension-registration.md#english-version)
- [225 · Can a High-Temperature Speckle Pattern Change Infrared Readings? Surface Checks for XTDIC Tests](xtdic-infrared-hot-tension-surface.md#english-version)
- [226 · Identifying Necking Onset in Hot Tension with XTDIC Strain, Specimen Outlines and Thermograms](xtdic-infrared-hot-tension-necking.md#english-version)
- [227 · Validating a Thermomechanical Tensile Model with XTDIC and Infrared Data](xtdic-infrared-hot-tension-validation.md#english-version)

Case documentation: [Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test description](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

</details>
