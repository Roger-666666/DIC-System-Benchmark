# 高温拉伸同步采集方法：如何对齐 XTDIC 应变、红外温度与载荷记录

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温拉伸同步采集方法：如何对齐 XTDIC 应变、红外温度与载荷记录</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 同步采集*

在高温拉伸中，判断“局部升温与应变集中谁先出现”，需要把同一块材料的温度和应变放在同一条时间轴上。XTDIC 公开试验采用硬件触发，将拉伸试验机、双目相机和红外热像仪的记录按时间戳对应起来。同步解决了记录从何时开始比的问题；事件本身何时出现，还要结合曝光间隔、保温阶段的波动和连续图像判断。

## 从一次峰值载荷回查照片

实验人员通常先拿到一条载荷曲线。曲线的最高点表示试验机记录到了最大拉力。若想知道达到最大拉力时试样中部是否已经变细，可以读取峰值对应的时间，找到前后最接近的应变图与原始照片，再调出同一时段的热像。以载荷为入口，能够把“峰值前后”落实到一小段可回看的试验过程。

这里容易出错的是用相同帧号代替相同时间。即使设备同时启动，两台相机的采集间隔也可能不同。逐帧往后数，排在同一序号的照片就可能属于不同加载阶段。记录中保留触发时刻、各自的采样间隔和实际曝光时间，才便于追查一幅图究竟对应哪段载荷。遇到缺帧时也可以保留空缺，不必把后面的图片依次前移。

## 温升起点与局部变形起点怎样定义

可先选取保温后、加载前的一段热像，观察目标区域温度正常波动的范围。加载后继续跟随这块材料，找出温度持续偏离原来范围的时间段。若目标区域本来就比两旁热，报告中应分别写明初始温差与加载后的新增变化。对应的应变记录则关注这段材料何时开始持续比两旁伸得快。两个起点代表不同的物理现象，应分别判读。

| 记录情形 | 合适的时间判断 |
| --- | --- |
| 相邻两次热像曝光之间出现持续温升 | 把起点限定在两次曝光之间 |
| 应变集中和温升的起点范围重叠 | 两种变化出现在同一可分辨时段 |
| 一种变化的起点范围完全早于另一种 | 在当前采样条件和判据下可以报告先后 |

## 对试验结果有什么帮助

例如，若一段材料在加载前已持续偏热，首先应审视试样的均温状态。若局部伸长先集中，随后才出现额外温升，则可进一步检验塑性变形发热、热传导和散热条件。这两种情形对应不同的后续分析方向。公开案例给出了同步测量的实现方式，但没有据此规定所有金属的固定先后次序。用于复核的报告应留下选区、基线、时间范围和原始帧，使另一位读者能按同一条件重看这一判断。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)
- [224 · 高温拉伸热区定位：红外热像与 XTDIC 应变场的三种对照方法](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#chinese-version)

</details>

<details>
<summary><b>English · Synchronizing XTDIC Strain, Infrared Temperature and Load in Hot Tensile Tests</b></summary>

<a id="english-version"></a>

# Synchronizing XTDIC Strain, Infrared Temperature and Load in Hot Tensile Tests

*Measuring deformation and damage at elevated temperature · Data acquisition*

Determining whether warming precedes strain localization requires temperature and strain histories for the same material on the same clock. The published XTDIC experiment used hardware triggering and timestamps to link the tensile machine, stereo cameras and thermal camera. Synchronization establishes which records belong together. Locating the onset of a physical event also requires exposure intervals, baseline fluctuations and a sequence of observations.

## Recovering images around peak force

The high point on a load curve marks maximum recorded force. To determine whether the gauge section was already narrowing, locate the time of that peak, retrieve the nearest strain maps and photographs on either side, then examine thermograms from that interval. This gives the phrase “around peak force” a specific experimental meaning.

Matching frame numbers can produce a different answer. Two cameras can start together and still acquire at different rates. Images with the same sequence number may belong to different loading stages. Trigger records, individual sampling intervals and exposure times allow an analyst to place each image on the load curve. A missing frame can then remain a documented gap without shifting every later image forward.

## Defining each onset independently

Temperature variation during the unloaded hot hold establishes a baseline for the selected region. Following that material during loading reveals when its temperature departs persistently from the earlier range. If the region was already warmer than its neighbours, record the initial offset separately from any additional change. For localization, examine when extension in the region begins consistently to outpace the neighbouring material. These criteria describe two distinct physical events.

| Observation | Supported timing statement |
| --- | --- |
| A persistent temperature rise appears between successive exposures | Bound onset by those exposures |
| The onset intervals for strain localization and warming overlap | Both changes occurred within the same resolvable interval |
| One onset interval ends before the other begins | Their order can be reported for these criteria and acquisition conditions |

## Implications for interpretation

If a region was warmer before force was applied, the temperature distribution during the hold deserves attention. If localization clearly developed first and additional warming followed, plastic work, heat conduction and heat loss warrant investigation. These scenarios lead to different follow-up questions. The case demonstrates how to acquire synchronized records. The order in a given specimen must come from that run. Preserving the selected region, baseline interval, onset bounds and original frames allows another analyst to reproduce the interpretation.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [224 · Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#english-version)

</details>
