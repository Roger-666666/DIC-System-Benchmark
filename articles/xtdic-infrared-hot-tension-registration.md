# 红外热点与应变带是否落在同一处？高温拉伸的双场空间配准

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

**关键词**　空间配准、材料坐标、热像分辨率

试样拉长后，热像中固定像素看到的材料会改变。若要回答“出现热点的这块材料随后是否颈缩”，需要用 XTDIC 跟踪材料点，并把该点的当前位置投影到红外热像上。时间对齐只是这项分析的起点。

## 怎样建立对应位置

在预期标距段和运动深度范围内，用可被两类相机识别的标记建立几何对应，再用未参与拟合的标记复查偏差。若只能做平面映射，应在侧向弯曲、转动或厚度变化时检查其适用范围。设备从相反方向观察时，前后表面属于不同的观测面，应按各自表面标记结果。

## 用一条剖面检验重合程度

沿标距段布置材料测线，保存每帧的三维位置。在共同有效区内提取轴向应变和表面温度剖面。把较细的场按较粗通道的空间尺度汇总，再比较高值带的位置和宽度。将映射按实测配准偏差轻微移动后重算。如果“重合”随这点移动就消失，热像只支持区域级对应。

## 遇到遮挡怎样交付

在轮廓、夹具和断口附近输出共同可见范围。保留最终有效测线、映射复查误差以及原始图像。读者便能区分“同一材料区域同时升温和拉伸”与“两个相邻区域分别出现高值”，进而决定后续取样位置。

[返回系列导读](xtdic-infrared-hot-tension-case.md#chinese-version)

案例来源：[原文入口](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验说明](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

</details>

---

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Do the Hot Spot and Strain Band Coincide? Spatial Registration in Hot Tensile Testing

**Keywords**　Spatial registration, material coordinates, thermal resolution

As a coupon elongates, a fixed thermal pixel sees different material. To ask whether a hot material region later develops a neck, track that region with XTDIC and project its current position into the infrared view. The two frames must also correspond in time.

## Establish spatial correspondence

Use features visible to both optical systems throughout the gauge area and expected depth range. Check the mapping on features withheld from the fit. If only a planar transformation is available, test its validity when the coupon bends, rotates or changes thickness. Opposite-side observations refer to different physical faces and should be labeled by face.

## Test overlap on a profile

Place a material line along the gauge and retain its three-dimensional position in each frame. Extract axial strain and surface temperature along the common visible segment. Average the finer field to a support comparable to the coarser channel before comparing band position and width. Perturb the mapping within its measured registration error and repeat. Overlap that disappears under this change supports only a regional association.

## Deliver the common visible area

Mask boundaries, grips and the opening fracture where either view loses the specimen. Supply the last valid profile, the registration check and original images. A reader can then distinguish a material region that heats and stretches from neighboring regions with separate peaks, which matters when choosing a location for follow-up inspection.

[Back to the case overview](xtdic-infrared-hot-tension-case.md#english-version)

Case documentation: [Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test description](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

</details>
