# 热像里最热的地方，真是金属被拉得最厉害的地方吗？

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 热像里最热的地方，真是金属被拉得最厉害的地方吗？</b></summary>

<a id="chinese-version"></a>

*高温拉伸中的变形与损伤 · 专题二*

在一张应变图上圈出伸长最集中的地方，再把这张图盖到红外热像上。如果两个圈重合，能说明那一小块金属又热、又被拉得厉害吗？对于透过炉窗观察的高温拉伸试验，先得弄清楚一个朴素的问题：两个镜头里的圈，究竟有没有圈到同一块材料？

## 让不同角度拍到的试样对得上

XTDIC 的双目相机用可见光观察试样，热像仪从自己的位置接收红外辐射。试样在一幅图上可能显得较宽，在另一幅上可能稍微倾斜。即使把两幅图裁成一样大，让中心重叠，靠近边缘的细节也可能错开。这个误差对于一整段标距或许不显眼，对于一条窄窄的应变带，却足以把要比较的区域移到旁边。

把两个视角对应起来，称为空间配准。可以借助两种相机都能辨认的定位特征，在试样所在的位置建立对应关系，再用没有参与计算的特征检验映射是否可靠。炉窗、相机位置和观察距离都属于这次测量的条件。如果改变了光路，曾经对齐的图像也值得重新检查。

## 画面中的位置不动，材料却会走

用笔在屏幕上指住试样中部。随着夹具拉开，原来在指尖下的那块材料可能已经移到上方。此后一直读取指尖处的温度，得到的就是陆续经过这里的材料温度。要追问“后来变细的这一块经历了怎样的温度变化”，就应利用 DIC 跟踪那一簇斑点，再到各时刻的热像中寻找对应区域。前一种读法适合研究炉内固定位置，后一种适合研究随试样移动的材料。

## 两片颜色相遇，可以得出多细的结论

还要考虑热像能看清多小的细节。假如应变集中在一条很窄的带内，而一个热像测量区域已经同时覆盖窄带和两旁材料，温度读数就混入了周围的贡献。此时可以比较窄带附近与远处的温度趋势。要进一步断言温度最高点正好落在应变最高点上，就需要比两点间距更精细的空间证据。这样读图，结论会落在实际可辨的那块金属上。

[原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验与图像](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

## 系列阅读

[222 · 一根金属拉断之前发生了什么？用 XTDIC 和红外热像看懂高温拉伸](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version) · [225 · 为什么要给高温试样做散斑？从一块金属表面读懂两台相机](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#chinese-version)

</details>

<details>
<summary><b>English · Is the Hottest Spot Also the Most Stretched Part of the Metal?</b></summary>

<a id="english-version"></a>

# Is the Hottest Spot Also the Most Stretched Part of the Metal?

*Deformation and damage in hot tension · Part 2*

Circle the area of greatest stretch on a strain map and lay it over a thermal image. If the circles overlap, have the cameras found a piece of metal that is both hot and highly strained? In a furnace test the answer begins with a simpler question. Did the two cameras actually see the same piece of material inside those circles?

## Matching the views

XTDIC’s stereo cameras observe the specimen in visible light. The infrared camera receives radiation from its own position. The strip may look wider in one view and slightly tilted in the other. Cropping the images to the same size and lining up their centres can still leave their edges displaced. An offset that looks small across the full gauge section can move a narrow strain band entirely outside the area being compared.

Establishing this correspondence is called spatial registration. Features visible to both systems can establish a mapping at the specimen position. Other features, left out of that calculation, can independently show how well the mapping works. The window, viewing distance and camera positions belong to this particular setup. Changing the optical path gives a reason to check the alignment again.

## A stationary cursor can sample moving material

Hold a finger against the middle of the specimen on a screen. As the grips separate, the surface patch beneath the fingertip may move upwards. Reading temperature at the fingertip then gives a history of successive pieces of material passing through one location. To recover the history of the piece that eventually necks, the analyst can follow its speckles with DIC and locate the corresponding area in each thermal image. A fixed point answers a question about a place in the furnace. A moving patch answers a question about the metal.

## How close is close enough?

A thermal measurement area may cover a narrow strain band and material on both sides. Its reading then includes contributions from the neighbours. Comparing temperatures near the band with temperatures farther away can still reveal a regional difference. To claim that the hottest point coincides with the most highly strained point, the images and their alignment must resolve the separation in question. The size of the region the cameras can distinguish determines how precisely the conclusion can be stated.

[Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test and images](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

## In this series

[222 · Before Hot Metal Breaks: Reading a Tensile Test with XTDIC and Infrared Thermography](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version) · [225 · Why Speckle Hot Metal? One Surface Seen by Two Different Cameras](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-surface.md#english-version)

</details>
