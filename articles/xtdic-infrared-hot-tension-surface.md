# 为什么要给高温试样做散斑？从一块金属表面读懂两台相机

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 为什么要给高温试样做散斑？从一块金属表面读懂两台相机</b></summary>

<a id="chinese-version"></a>

*高温拉伸中的变形与损伤 · 专题三*

光滑的金属条被慢慢拉长，肉眼看两端就能发现它变长了。可如果只看金属条中间一小块光亮的表面，怎样认出上一张照片里那块材料去了哪里？旁边的材料看起来几乎一模一样。这正是高温数字图像相关测量要在试样表面制作散斑的原因。小斑点一旦组成不规则的花纹，相机就有了能沿途辨认的标记。

## 斑点必须跟着金属一起走

XTDIC 比较连续照片中局部花纹的位置，根据邻近花纹间距的变化计算应变。对于高温拉伸，花纹需要经历升温、保温和随后的拉伸。如果涂层在保温时已经剥落，两张照片里最相似的亮点可能属于不同位置。如果涂层在拉伸时开裂，花纹自身也会发生突变。软件在这些区域给出的突变，首先需要回到照片上辨认来源。看到一条突出的色带时，检查斑点有没有随金属完整移动，是很实际的一步。

## 同一层散斑，到了红外相机里是什么

热像仪根据接收到的红外辐射估计表面温度。这里有一个和金属表面状态密切相关的量，叫作发射率。可以这样理解：即使处在相同温度，裸露金属和表面涂层发出的红外辐射也可能不同。光亮的金属还可能把炉壁的辐射反射到镜头里。因此，一块在热像上显得特别亮的区域，可能真的更热，也可能与它的表面状态有关。可见光照片里斑点的黑白深浅，不能直接给出红外相机要用的发射率。

## 一个能在加力前问清的问题

设想样品还在保温，试验机尚未开始拉。若热像中一道明暗分界恰好沿着涂层边缘延伸，这个时候就值得把原始热像留下，核查表面处理、热像波段和观察窗的透过特性，并与独立测温位置作比较。等到拉伸后再看到同一条边界，有了加载前的记录，就不容易把它误读为刚刚发生的局部发热。这是对公开试验方法的读图举例，并非该试样出现过的异常。

同一块表面要同时回答两个问题。散斑附着得好，才有把握判断材料在哪里伸长；辐射条件核查清楚，才有把握判断那里是否变热。两种证据都在，局部温升和局部变形之间的联系才值得进一步追究。

[原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验与图像](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

## 系列阅读

[222 · 一根金属拉断之前发生了什么？用 XTDIC 和红外热像看懂高温拉伸](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version) · [226 · 断口形成之前，金属从哪里开始变细？沿着应变图找颈缩](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#chinese-version)

</details>

<details>
<summary><b>English · Why Speckle Hot Metal? One Surface Seen by Two Different Cameras</b></summary>

<a id="english-version"></a>

# Why Speckle Hot Metal? One Surface Seen by Two Different Cameras

*Deformation and damage in hot tension · Part 3*

A smooth strip of metal lengthens as its ends move apart. Looking at the grips makes that easy to see. Looking only at a tiny shiny patch in the middle poses a harder question. Where did the piece of material in the previous photograph go? Its neighbours look almost identical. This is why a digital image correlation test gives the surface an irregular speckle pattern. A small cluster of marks can be recognised again as it moves.

## The marks must travel with the metal

XTDIC compares patches in successive photographs and uses their relative motion to calculate strain. During a hot tensile test the pattern goes through heating, a hold and stretching. If a coating flakes during the hold, a bright spot in the next picture may belong to a different patch. If the coating itself cracks under tension, its pattern changes abruptly. A striking band on the strain map warrants a look at the original photographs. Did the pattern remain attached and move with the underlying surface?

## What the infrared camera sees

A thermal camera estimates surface temperature from the infrared radiation reaching it. Emissivity describes how effectively a surface emits thermal radiation compared with an ideal emitter at the same temperature. A coating and bare metal can emit different amounts even when equally hot. Shiny metal can also reflect radiation from a furnace wall into the lens. A bright patch on a thermogram can therefore reflect temperature, surface condition or both. The shade of a speckle in a visible photograph does not supply its infrared emissivity.

## A question worth asking before the pull

Imagine the specimen during its hot hold, before the force is applied. A boundary between bright and dark areas on the thermal image follows the edge of a coating. Saving this frame gives the analyst a chance to check the surface treatment, the infrared wavelength band and window transmission, and to compare a location with an independent temperature reading. If the same boundary reappears during loading, there is already evidence of what it looked like beforehand. This is an example of interpreting the test, rather than a reported defect in the published specimen.

The two cameras ask different things of one surface. A pattern that stays attached lets the reader follow the stretch. Understanding how radiation reaches the camera makes the temperature reading interpretable. Together these checks give a local rise in temperature a sound basis for comparison with local deformation.

[Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test and images](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

## In this series

[222 · Before Hot Metal Breaks: Reading a Tensile Test with XTDIC and Infrared Thermography](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version) · [226 · Where Does Hot Metal Begin to Narrow? Following a Neck Before Fracture](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-necking.md#english-version)

</details>
