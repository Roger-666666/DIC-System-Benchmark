# 高温拉伸中温升和应变集中谁先出现？XTDIC 与红外热像的时间同步

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

**关键词**　统一时间戳、曝光时间、事件先后

高温拉伸临近断裂时，温度曲线和应变曲线的峰值可能出现在相邻帧。要判断先后，需要知道两台设备各自在什么时候看到了试样。XTDIC 高温拉伸案例采用统一时间戳。复用这一方法时，还要确认时间戳对应触发、曝光还是数据到达。

## 用一次共同事件检查时间轴

正式加载前，可在两路视场中移动一个边界清晰、与背景有温差的标记。记录标记通过同一物理位置的时刻，再在采集结束前重复检查。两次偏差相近，可以估计固定延迟；偏差随记录时长改变，则要检查时钟漂移。保存原始采样时刻，便于发现漏帧。

## 把起点写成区间

选定随材料移动的标距区域，用稳定保温段估计温度和应变各自的波动。事先约定何种持续偏离算作事件。将最后一个仍处于背景范围的观测与第一个持续偏离的观测作为区间两端，并考虑曝光时长及同步偏差。若温升和局部化两个起始区间重叠，报告可写为“在当前采样条件下，两者先后未分辨”。

## 报告中怎样画曲线

在同一时间轴保留两路原始采样点，以阴影标出事件区间。热像采样较慢时，插值可用于显示，新增的曲线点仍不能缩短观测间隔。载荷通道如需参与判断，也要通过同样的时间校验。

[返回系列导读](xtdic-infrared-hot-tension-case.md#chinese-version)

案例来源：[原文入口](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验说明](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

</details>

---

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Which Came First in Hot Tension? Synchronizing XTDIC Strain and Infrared Temperature Histories

**Keywords**　Timestamps, exposure timing, event ordering

Near fracture, a temperature peak and a strain peak may fall in adjacent frames. Deciding which occurred first requires the observation time of each instrument. The XTDIC hot tensile case used a common timestamp. In a repeat test, document whether each timestamp refers to a trigger, exposure or arrival of a recorded frame.

## Check the clocks with a common event

Before loading, move a distinct target with thermal contrast through both fields of view. Record its passage across the same physical position. Repeat the check near the end of acquisition. Similar offsets support a fixed-delay estimate. A changing offset calls for a clock-drift check. Retain native acquisition times so dropped frames remain visible.

## Give onset a time interval

Track one material region. Use the stable hot dwell to characterize variation in temperature and strain separately, and define a sustained departure before inspecting the event. Bracket onset between the last background observation and the first of the sustained departures. Account for exposure duration and synchronization error. If the two intervals overlap, report that their order was unresolved at the available sampling rate.

## Plot the observations

Show native samples on one time axis and shade the onset intervals. Interpolation can make a slower thermal trace easier to read, but the interval between observations stays the same. A force channel used to judge timing also needs a verified time reference.

[Back to the case overview](xtdic-infrared-hot-tension-case.md#english-version)

Case documentation: [Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test description](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

</details>
