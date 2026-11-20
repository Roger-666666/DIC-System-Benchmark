# 电脑算出的金属拉伸过程可信吗？用一次高温试验检验仿真

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 电脑算出的金属拉伸过程可信吗？用一次高温试验检验仿真</b></summary>

<a id="chinese-version"></a>

*高温拉伸中的变形与损伤 · 专题五*

假设计算机模拟了一根金属条在高温下被拉长的过程。计算的拉力曲线几乎贴着试验曲线，画面里的金属条却偏偏在另一个地方变细。模型算准了吗？如果工程师关心的是拉动试样需要多大的力，这条曲线提供了有用的证据。如果要据此判断零件上哪一处容易发生局部损伤，那个偏了位置的细颈，就成了必须解释的问题。

## 先让计算中的试样和炉里的试样经受相近的温度

材料在高温下对拉力的反应和温度有关。在模型里给整根试样填入同一个炉温，相当于预先假定每一处都一样热。试验中的热像可以检查这个假定。比如，若试样中段和靠近夹具的部分在加载前已有可辨别的温差，计算中忽略它，后面应变集中的位置就可能受影响。这是一种需要检验的解释。红外相机测到的是可见表面的温度，要推断试样内部的温度分布，还需要传热条件等信息。

## 选一段真实的材料，看它怎样伸长

XTDIC 的作用在这里很具体。以保温结束、拉伸尚未开始的照片为起点，在试样上选出中间一段和旁边一段。沿拉伸方向观察两段材料的应变怎样随加载发展，再在模型上找到相同的位置和方向。当两条总拉力曲线都很接近时，这个对照仍可能发现差别：模型也许把伸长分摊到较宽的范围，试样却逐渐把伸长集中到窄带里。

做这样的比较还有一个细节。相机通过一小片表面花纹估计应变，计算软件却能列出某个很小单元里的尖峰值。把模型结果在与光学测量相近的范围内取平均，并使用相同的应变定义和时刻，再来比较，才知道差别有多少来自材料、有多少来自两把“尺子”的长短。

## 一次对照可以把模型用到哪里

如果模型用了这次试验的数据来调整材料参数，它能够重现这条记录，说明调整后与已有试验相容。更有说服力的问题是，换到另一组没有参与调参的温度工况，它能否仍然算对拉力变化、变形集中位置和范围？XTDIC 公开案例提供了不同温度条件下开展拉伸并联动记录的试验基础。这里讨论的是怎样利用这类记录检验模型；要给某个模型下结论，仍应拿出它的预测与对应的实测结果。

[原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验与图像](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

## 系列阅读

[222 · 一根金属拉断之前发生了什么？用 XTDIC 和红外热像看懂高温拉伸](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)

</details>

<details>
<summary><b>English · Can a Simulation Predict Where Hot Metal Will Stretch? Testing It Against a Tensile Experiment</b></summary>

<a id="english-version"></a>

# Can a Simulation Predict Where Hot Metal Will Stretch? Testing It Against a Tensile Experiment

*Deformation and damage in hot tension · Part 5*

Imagine a simulation of a strip of hot metal under tension. The predicted force curve runs almost on top of the measured one, yet the strip narrows in a different place on the screen. Is the model accurate? The curve supports an answer about the force required to pull the specimen. If the purpose is to locate a component’s vulnerable region, the misplaced neck becomes a question the model still has to answer.

## Give the virtual specimen a comparable thermal history

The mechanical response of hot metal depends on temperature. Assigning the furnace setpoint everywhere in a model assumes a uniform specimen temperature. A thermal image provides a way to examine that assumption. If the middle and the regions near the grips differ in temperature before loading, omitting that difference might affect the predicted location of concentrated strain. This is an explanation to investigate. Infrared data describe the visible surface, and inferring temperatures through the thickness requires additional heat-transfer information.

## Follow an actual piece of material

XTDIC supplies a practical comparison. Use the image after the hold and before loading as the reference. Pick a central region and a neighbouring length, follow their strain along the tensile axis and find the equivalent regions and direction in the model. Two nearly identical total-force histories can conceal quite different behaviour. The calculation might spread extension across a broad area while the specimen increasingly concentrates it in a narrow band.

There is also a question of scale. A camera estimates strain across a patch of surface texture. A simulation can report a sharp peak from a very small element. Averaging the simulation over a comparable measurement area and using the same strain definition and time makes the comparison interpretable. Otherwise a difference in the two measuring lengths can masquerade as a difference in material behaviour.

## How far does agreement carry?

If data from a test were used to tune the material parameters, reproducing that test demonstrates agreement with a known record. A more demanding question is whether the model predicts the force history, location and width of concentrated deformation at a temperature held back from the tuning process. The published XTDIC case describes tensile tests at several temperatures with linked optical and thermal observations. They illustrate the kind of records such a comparison requires. A verdict on any particular model would also require its predictions alongside the corresponding measurements.

[Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test and images](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

## In this series

[222 · Before Hot Metal Breaks: Reading a Tensile Test with XTDIC and Infrared Thermography](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)

</details>
