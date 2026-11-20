# 高温拉伸同步采集方法：如何对齐 XTDIC 应变、红外温度与载荷记录

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温拉伸同步采集方法：如何对齐 XTDIC 应变、红外温度与载荷记录</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 同步采集*

在高温拉伸中，判断“局部升温与应变集中谁先出现”，需要把同一块材料的温度和应变放在同一条时间轴上。XTDIC 公开试验采用硬件触发，将拉伸试验机、双目相机和红外热像仪的记录按时间戳对应起来。同步解决了记录从何时开始比的问题；事件本身何时出现，还要结合曝光间隔、保温阶段的波动和连续图像判断。

**本文目录**

- [从一次峰值载荷回查照片](#chinese-section-1)
- [温升起点与局部变形起点怎样定义](#chinese-section-2)
- [建立时间轴时，先认清三种时间](#chinese-section-3)
- [从保温到断裂，怎样组织一次采集](#chinese-section-4)
- [没拍到精确起点时，怎样写出可复核的结论](#chinese-section-5)
- [怎样判断问题出在采集还是材料](#chinese-section-6)
- [对试验结果有什么帮助](#chinese-section-7)

<a id="chinese-section-1"></a>

## 从一次峰值载荷回查照片

实验人员通常先拿到一条载荷曲线。曲线的最高点表示试验机记录到了最大拉力。若想知道达到最大拉力时试样中部是否已经变细，可以读取峰值对应的时间，找到前后最接近的应变图与原始照片，再调出同一时段的热像。以载荷为入口，能够把“峰值前后”落实到一小段可回看的试验过程。

这里容易出错的是用相同帧号代替相同时间。即使设备同时启动，两台相机的采集间隔也可能不同。逐帧往后数，排在同一序号的照片就可能属于不同加载阶段。记录中保留触发时刻、各自的采样间隔和实际曝光时间，才便于追查一幅图究竟对应哪段载荷。遇到缺帧时也可以保留空缺，不必把后面的图片依次前移。

<a id="chinese-section-2"></a>

## 温升起点与局部变形起点怎样定义

可先选取保温后、加载前的一段热像，观察目标区域温度正常波动的范围。加载后继续跟随这块材料，找出温度持续偏离原来范围的时间段。若目标区域本来就比两旁热，报告中应分别写明初始温差与加载后的新增变化。对应的应变记录则关注这段材料何时开始持续比两旁伸得快。两个起点代表不同的物理现象，应分别判读。

| 记录情形 | 合适的时间判断 |
| --- | --- |
| 相邻两次热像曝光之间出现持续温升 | 把起点限定在两次曝光之间 |
| 应变集中和温升的起点范围重叠 | 两种变化出现在同一可分辨时段 |
| 一种变化的起点范围完全早于另一种 | 在当前采样条件和判据下可以报告先后 |

<a id="chinese-section-3"></a>

## 建立时间轴时，先认清三种时间

一次采集通常会留下触发时间、曝光时间以及数据写入计算机的时间。它们可能相距很近，含义却不同。触发时间说明设备何时收到拍摄指令；曝光对应的是相机实际采样的一小段时间；文件生成时间还包含传输、缓存和写盘过程。若以文件创建时间排序，在计算机忙于保存一批图像时，可能把本来连续的试验记录排出一段并不存在的延迟。

对于力信号，还要了解导出的曲线经过了怎样的处理。平滑能压低噪声，也可能改变快速转折看起来出现的时刻。设备带有滤波时，可同时保留原始通道与用于展示的曲线，给两者注明处理方式。特别是把“载荷突然下降”用作断裂标记时，应该先从原始记录找到下降区间，再核对照片中两段材料何时分开。若只用美化过的曲线选帧，读者无法判断看到的是试样变化还是平滑产生的移动。

<a id="chinese-section-4"></a>

## 从保温到断裂，怎样组织一次采集

**保温期间记录背景。** 这段记录能回答红外温度波动有多大、未增加载荷时应变图会不会自行闪动。可分别选中预期工作段与邻近区域，观察它们的温度和表观应变是否同时漂移。两处长期朝同一方向变化时，先检查试样是否还在升温或测量环境是否仍在变化。背景能够解释加载开始前两条曲线为什么没有停在一个固定值上。

**加载开始时保存共同事件。** 若系统提供共同触发信号，保存各设备实际收到的触发记录及曝光状态。需要独立核对时，可在正式试验前安排各通道都能直接或间接记录的校时事件，并说明这个事件传到各传感器的路径。不能只因为温度曲线和应变曲线后来都有一个峰，就平移其中一条使峰顶相合。局部变形和表面热量传递原本就可能存在时间差，强行对峰会把正准备研究的信息消掉。

**接近断裂时保留原始节奏。** 屏幕为了播放流畅，可能跳过若干画面或重复显示上一帧。复核时宜读取文件中每幅图的原始时间戳，并列出同一时段的有效热像和应变帧。若一个温度点正好位于很短的载荷跌落之后，不宜根据插值画出的平滑斜线，认定中间经历了某种升温速率。插值可帮助对齐读图，真实的观测间隔仍应同时标出。

<a id="chinese-section-5"></a>

## 没拍到精确起点时，怎样写出可复核的结论

以局部化区的温升为例。先记下最后一张仍在保温波动范围内的热像，再记下第一张持续偏离该范围的热像。接着回到应变图，找出最后一帧尚未出现持续集中的画面，以及第一帧能确认集中趋势的画面。这样会得到两个时间区间。把它们放到同一载荷曲线上，就能清楚看到“温升最早可能发生在这里”“局部化最迟已经在这里出现”。若区间只在端点接触，还应把时钟偏差与曝光持续时间考虑进去。

另一个有用的检查是换一块材料重做比较。选取集中区邻近、表面状态相近且没有发生明显局部化的位置，用同样的基线和判据计算它的温度变化。若整个工作段都在相似时段升温，应先审视炉内热环境；若只有集中区明显变化，则更适合把该局部事件与塑性变形联系起来继续研究。这个对照需要同步记录提供时间依据，同时也依赖两处的可比表面状态。

<a id="chinese-section-6"></a>

## 怎样判断问题出在采集还是材料

若每个工况的热像都比载荷曲线晚一个近似固定的时段，先查触发配置、时间戳含义及导出程序有没有统一偏移。若偏差随试验持续时间逐渐增大，应查设备是否共用时基，以及独立时钟之间是否存在漂移。若只有个别时段出现异常，优先核对该段是否缺帧、缓冲区是否中断或是否存在较长曝光。先识别误差的时间特征，可以减少盲目调整材料模型或反复拉断试样的次数。

对于需要复算的报告，将每个事件记为一行，保留事件定义、两端时间、对应图像编号以及所处载荷区间。即使后续团队采用了不同的温升判据，也能从同一批原始帧重新推定起点，并说明哪种判定发生了改变。

### 读图示例：怎样写一次有时间边界的材料观察

考虑这样一组待解读的记录：拉力仍在上升，局部与邻近区域的伸长已经出现持续差异；紧接着得到的热像才显示两处温差扩大。报告若仅写“变形导致升温”，读者无法判断热像仪在这之前多久拍过上一张图。可以先说清上一张热像时两个区域的温差是否还在保温波动范围内，再说明两张热像之间有哪几张有效的应变帧，最后写出温差扩大时拉力是仍在上升、接近峰值，还是已开始回落。这段表述直接使用了三个通道各自能够观测的量。

如果将这次判读用于比较两种工况，就要在两次试验中保留相同的事件定义。一个工况用中心像素的第一次升高作为温升起点，另一个工况用一片区域的平均温度连续升高作为起点，即使材料完全相同，也可能读出不同顺序。可以把同一套取样条件先用于保温阶段作为空白检查：若“温升事件”在未加载时就反复被检出，说明判据对背景波动过于敏感。等空白检查能解释后，再把同一判据用于正式加载。由此获得的工况差异更便于复验。

还有一项交付细节与后续复核密切相关。如果导出到表格，温度列在未曝光的时刻宜保留为空，并另存用于绘图的插值列。否则，后续分析人员可能把一串补算出来的温度值当成相机真正采到的密集记录。

<a id="chinese-section-7"></a>

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

**Contents**

- [Recovering images around peak force](#english-section-1)
- [Defining each onset independently](#english-section-2)
- [Three times associated with an image](#english-section-3)
- [Organising acquisition from hold to fracture](#english-section-4)
- [Reporting an onset that fell between frames](#english-section-5)
- [Distinguishing acquisition problems from material response](#english-section-6)
- [Implications for interpretation](#english-section-7)

<a id="english-section-1"></a>

## Recovering images around peak force

The high point on a load curve marks maximum recorded force. To determine whether the gauge section was already narrowing, locate the time of that peak, retrieve the nearest strain maps and photographs on either side, then examine thermograms from that interval. This gives the phrase “around peak force” a specific experimental meaning.

Matching frame numbers can produce a different answer. Two cameras can start together and still acquire at different rates. Images with the same sequence number may belong to different loading stages. Trigger records, individual sampling intervals and exposure times allow an analyst to place each image on the load curve. A missing frame can then remain a documented gap without shifting every later image forward.

<a id="english-section-2"></a>

## Defining each onset independently

Temperature variation during the unloaded hot hold establishes a baseline for the selected region. Following that material during loading reveals when its temperature departs persistently from the earlier range. If the region was already warmer than its neighbours, record the initial offset separately from any additional change. For localization, examine when extension in the region begins consistently to outpace the neighbouring material. These criteria describe two distinct physical events.

| Observation | Supported timing statement |
| --- | --- |
| A persistent temperature rise appears between successive exposures | Bound onset by those exposures |
| The onset intervals for strain localization and warming overlap | Both changes occurred within the same resolvable interval |
| One onset interval ends before the other begins | Their order can be reported for these criteria and acquisition conditions |

<a id="english-section-3"></a>

## Three times associated with an image

Trigger time, exposure time and file-write time can all appear in one acquisition. The trigger records when a command reached a device. Exposure covers the interval during which the camera sampled the scene. File creation also includes transfer, buffering and storage. Sorting by file creation can introduce an apparent lag while the computer is saving a batch of otherwise consecutive images.

Check how the force trace was processed as well. Smoothing suppresses noise and can shift the apparent time of a sharp transition. Keep the raw signal alongside the presentation curve and describe the filter. If a load drop serves as a fracture marker, bound it on the original record and compare it with the photographs showing separation. A smoothed display alone leaves the origin of any apparent shift uncertain.

<a id="english-section-4"></a>

## Organising acquisition from hold to fracture

**Record the background during the hold.** Examine temperature fluctuations and apparent strain before additional load is applied. Use the working region and a neighbouring area to check whether both drift together. A common trend warrants a check on continuing specimen heating or changing optical conditions. This baseline explains why traces need not be perfectly flat at the start of the pull.

**Keep a common event at loading onset.** Where available, retain the actual trigger and exposure status from each instrument. An independent pre-test timing check can use an event detectable directly or indirectly in all relevant channels, provided its path to each sensor is described. Sliding the strain and temperature curves until their peaks coincide would erase a possible physical lag between deformation and surface heating.

**Retain the acquisition cadence near fracture.** Video playback may skip images or repeat a frame. For review, read the original timestamps and list the valid strain and thermal observations in the interval of interest. A temperature sample immediately after a short force drop does not reveal the heating rate during the unsampled gap. Interpolation can aid display if the original exposures remain visible.

<a id="english-section-5"></a>

## Reporting an onset that fell between frames

For warming, identify the last thermogram within the unloaded range and the first in a persistent departure. For strain, identify the last frame before sustained localization and the first that establishes it. Place both intervals on the load curve. The result bounds the earliest possible warming and the latest time by which localization was present. If the intervals only touch, uncertainty in clocks and the exposure durations still matter.

Repeat the comparison for a neighbouring patch with a similar surface condition and little localization. Apply the same baseline and criteria. Warming throughout the gauge section warrants examination of the furnace environment. A change confined to the concentrating patch warrants further examination of the contribution of plastic deformation. This control requires both timing correspondence and comparable surfaces.

<a id="english-section-6"></a>

## Distinguishing acquisition problems from material response

A similar offset in all runs points first to trigger settings, timestamp definitions or a constant shift at export. An offset that grows through a run calls for checking the time bases and clock drift. An isolated anomaly calls for checking dropped frames, buffering gaps or unusually long exposures. The shape of the timing error helps direct investigation before another specimen is tested.

A reproducible event record gives the criterion, bounding times, image identifiers and corresponding load interval in one row. Another analyst can then apply a different temperature-onset criterion to the same frames and identify precisely which judgment changed.

### Worked interpretation of a bounded event

Suppose force is still rising when a patch begins to stretch persistently faster than its neighbour. The next thermogram shows a larger temperature difference. Before attributing warming to deformation, state whether the previous thermogram was still within the baseline range. Identify the valid strain frames between the thermal exposures and indicate whether force was rising, near its peak or falling when the difference became visible. Each part of this statement refers to an observable on its own channel.

Use identical event definitions for comparisons across conditions. The first increase of a central pixel and a sustained increase in a regional mean are different criteria that can give different event orders on the same specimen. Apply the proposed criterion to the unloaded hold as a blank check. Repeated detections before loading indicate sensitivity to baseline fluctuations. Once that behaviour is understood, the same rule can be applied during loading.

In an exported table, leave temperature empty at times with no thermal exposure. Keep any interpolated display values in a separately labelled column so a subsequent analyst cannot mistake those values for additional observations.

<a id="english-section-7"></a>

## Implications for interpretation

If a region was warmer before force was applied, the temperature distribution during the hold deserves attention. If localization clearly developed first and additional warming followed, plastic work, heat conduction and heat loss warrant investigation. These scenarios lead to different follow-up questions. The case demonstrates how to acquire synchronized records. The order in a given specimen must come from that run. Preserving the selected region, baseline interval, onset bounds and original frames allows another analyst to reproduce the interpretation.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)
- [224 · Locating Hot Regions in Tension: Three Ways to Compare Thermograms with XTDIC Strain Fields](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-registration.md#english-version)

</details>
