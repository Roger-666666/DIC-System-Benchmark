# 泵车端头回摆量怎么算？从制动到送料的三维位移与轨迹判读

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 泵车端头回摆量怎么算？从制动到送料的三维位移与轨迹判读</b></summary>

<a id="chinese-version"></a>

混凝土泵车把送料端头移到指定位置后，现场关心两件事：停下时端头会朝哪边回摆，连续送料时出口又会在多大范围内活动。前一个问题围绕一次制动事件，后一个问题描述一段作业中的空间轨迹。两者都可以用三维坐标回答，但坐标相同，算法和结论却可以完全不同。原文分别展示了泵车端头到位回摆和送料摆动试验，正好说明“最大位移”为什么需要带上方向、基准和取值区间。 [参考试验](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**本文目录**

- [先认清运动的是哪一个点](#chinese-section-1)
- [一份坐标记录能算出哪些距离](#chinese-section-2)
- [制动测试怎样选起点和终点](#chinese-section-3)
- [连续送料为什么要读一段轨迹](#chinese-section-4)
- [端臂上多布几个点，有什么额外价值](#chinese-section-5)
- [一次回摆能否用一个最大值概括](#chinese-section-6)
- [设备应交付怎样的泵车测试结果](#chinese-section-7)

<a id="chinese-section-1"></a>

## 先认清运动的是哪一个点

泵车末端可以有多个候选目标：末节臂架上的标记、管路连接处、刚性出口以及柔性软管端部。它们彼此相连，但末节臂的运动不一定等于软管出口的运动。若研究的是臂架制动，布置在末节刚性构件上的稳定标记具有明确含义；若研究的是混凝土实际落料位置，则还要确认所测点与出口、落料目标之间的关系。把标记位置拍清楚，可防止后续报告把“臂上测点摆幅”写成“落料精度”。

原文的制动案例单独列出了 XTDIC-12M，以首帧作为分析基准，给出了空间轨迹和合位移曲线。送料案例则选取端臂多个测点，调整坐标系后分别读取分向位移和空间轨迹。对于希望配置 XTDIC-STROBE 的实验室，这两个案例最值得借鉴的是试验问题和交付量。复用时应按实际视场、速度和可见表面验证所选配置，保留每组数据对应的设备和工况。

<a id="chinese-section-2"></a>

## 一份坐标记录能算出哪些距离

设端头某一时刻的位置为 **P(t)**。以首帧 **P₀** 为参考，合位移是从 P₀ 到 P(t) 的直线距离，始终非负。它适合回答“离起点有多远”，却不能给出端头在目标的左边还是右边。若把相邻采样点之间的距离逐段相加，得到的是所拍轨迹在该采样条件下的路径长度。端头先过去、再回来，路径会继续增加，合位移却可能回到很小。报告中只写“运动距离”，容易把两种量混为一谈。

| 结果名 | 定义与用途 |
| --- | --- |
| 方向偏差 | 当前位置与目标位置之差在选定方向上的投影，用来判断越过目标的方向和幅度 |
| 合位移 | 当前点至参考点的直线距离，描述相对初始位置的空间偏离 |
| 合位移变化范围 | 一段时间内合位移的最大值减最小值，描述与参考点距离的变化范围 |
| 两时刻点间距 | 起点、终点两个实际空间位置的直线距离，回答从一次极值位置到另一次移了多远 |

一个简单的几何关系很有用：若端头沿围绕参考点的圆弧运动，到参考点的距离可以几乎不变，而端头已经从一侧移到另一侧。因此，合位移的最大值减最小值不能普遍解释为两个极值位置之间的三维距离。原文采用首帧基准并列出合位移变化，工程报告复用这项指标时，应沿用其定义。若要回答“制动以后向目标反方向退了多远”，则另外计算目标轴上的有符号回摆。

<a id="chinese-section-3"></a>

## 制动测试怎样选起点和终点

可以分别保留首帧、控制指令停止时刻和动作最终稳定位置。以首帧作参考能保留整个动作的总移动；以制动事件作参考能突出动作结束后的附加行程；以作业目标作参考则便于列出最终定位偏差。建议在同一组数据上分别作图，不必为了突出制动后的细节而删除较早时段。若指令日志与相机时间尚未对齐，宜用照片中可复查的动作标记注明时刻范围，并说明停止信号来源。

解读时可先看主运动方向的曲线，标出首次越过目标、第一次反向和可辨余振结束的区间。再查看相同时刻的竖向与深度分量。有的轨迹从正面看像沿原路返回，换到侧面才看出端头同时下沉或向操作者视线深处移动。把空间轨迹按时间标色或加上方向箭头，能帮助区分“经过同一投影位置”和“回到同一空间位置”。原文展示的回摆伴随上下运动，就是采用三维观察的直接理由。

<a id="chinese-section-4"></a>

## 连续送料为什么要读一段轨迹

送料过程中，关心的往往是端头围绕作业位置反复活动的范围。可先建立与作业面对应的水平轴和竖直轴，再将一定作业阶段内的轨迹投影到这些平面。俯视投影回答平面内覆盖范围，侧视投影说明高度变化，带时间的三维轨迹则表示两种运动是否同步。若只保留一幅没有时间顺序的轨迹图，两次方向相反的动作也可能留下相近的图形。

原文的送料记录显示多个方向都有运动。要进一步解释其中一个反复成分是否与送料节奏关联，需另有可靠的泵送事件或压力、控制记录，并和光学时序对齐。仅凭一条定期起伏的位移曲线，无法单独分辨送料激励、外部操纵或支撑处运动。若目标是比较两种配置，可固定臂姿和动作阶段，记录可用的工况信息；只有在对照条件相近时，轨迹覆盖范围的差别才具有清楚的工程含义。

<a id="chinese-section-5"></a>

## 端臂上多布几个点，有什么额外价值

多点轨迹首先能互相校核。同一刚性段上附着良好的点在整体转动时，空间轨迹可以差很多，点点距离却应大致稳定。若在某个姿态只有一对点的距离出现异常台阶，应先检查点号是否切换、深度重建是否失效或标记是否移动。若这些点分属不同构件，点间距变化又可能是本来存在的关节运动，因此要在点位图上注明构件归属。

需要描述末节姿态时，可以选择分布良好、非共线且稳定附着于同一刚性段的多个点。基于刚体假设拟合姿态后，还可检查各点对拟合结果的偏差。若偏差持续超出试验静止时的波动，应重新检查假设和布点，不能仅凭一个刚体拟合结果就把柔性端部的运动完整外推到出口。需要精确出口轨迹且条件允许时，直接观察出口附近的合适特征更有说服力。


<a id="chinese-section-6"></a>

## 一次回摆能否用一个最大值概括

做端头缓冲方案对比时，可以先在作业方向上标出目标带，再把制动后至首次折返的轨迹放大。若端头先沿水平方向越过目标，随后向下回落，空间距离最大的那一帧未必就是水平越位最大的那一帧。宜分别取各项指标的极值时刻，点回原始画面，检查标记是否仍在同一个部位，再标注当时的运动方向。这样，即使两个方案得到相近的合位移峰值，读者仍能看清其差别来自抑制了水平越位，还是改变了竖向活动。

读送料范围时，同样要留意统计区间。若把操作者将端头移向下一处作业位置的过渡也计入送料摆动，轨迹范围会同时包含主动换位与稳定送料时的波动。可以先用操作记录或视频将作业分成移位、到位调整及连续送料，在各段内分别列出观察时长和空间范围。对端头定位而言，应该保留换位过程；对稳定送料而言，可能只关心到位之后的区间。不同结论使用不同区间时，应让图例明确显示每一段的起止。

最后检查坐标方向是否能被现场人员读懂。相机坐标里的“深度”只是远离或接近镜头，更换相机站位后物理含义就会改变。若改用沿施工目标、横向于目标以及竖直方向的作业坐标，并在点位图上画明正向，则不同机位下的测试可以用相同语言描述。设备导出的三维坐标保留这种转换的可能，试验人员则负责提供可靠的现场基准。

<a id="chinese-section-7"></a>

## 设备应交付怎样的泵车测试结果

面向制动评价，可交付停止事件对齐的分向曲线、回摆极值处的原始画面，以及端头围绕最终位置的轨迹。面向送料评价，则要注明采样工况和时长，保留多测点轨迹、各作业方向的活动范围与缺测区间。两种报告都应保留原始点号和参考坐标，便于读者回到同一批数据改算目标侧的偏差。试验记录能支持对机构和控制的研究，具体是否合格须结合设备任务与既定验收指标判断。

选用三维光学设备的理由也由此变得具体：实验室需要用同一份动态记录分清端头“走了多远”“往哪边回摆”“最终落在哪里”。现场演示时若只能提供一张空间轨迹截图，可以进一步要求导出时间、坐标和点号，让使用者自己选基准重算一次。能完成这一步，这条轨迹才真正成为可以交给设计与测试团队的数据。

**设备与案例资料**

- [XTDIC-STROBE 动态测量系统与应用范围](https://www.xtop3d.com/products/xtdic-strobe.html)

**延伸阅读**

- [228 · 起重机回转停止后，吊臂还会摆多久？XTDIC 三维动态位移测量案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-slew-sway-case.md#chinese-version)
- [232 · 吊臂抑摆控制改进如何验证？用 XTDIC 多点轨迹对标制动策略与动力学仿真](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-anti-sway-validation.md#chinese-version)

</details>

<details>
<summary><b>English · Quantifying Concrete Pump Boom Recoil and Delivery Motion from 3D Tip Trajectories</b></summary>

<a id="english-version"></a>

# Quantifying Concrete Pump Boom Recoil and Delivery Motion from 3D Tip Trajectories

After a concrete pump boom positions its outlet, two questions arise. In which direction does it recoil after stopping, and what region does it occupy during delivery? The first concerns an event, the second an operating interval. Both use spatial coordinates, but their metrics differ. The reference reports separate stopping and delivery tests, illustrating why any maximum displacement needs a direction, origin and observation window. [Reference tests, in Chinese](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**Contents**

- [Identify the physical target](#english-section-1)
- [Four distances from one coordinate file](#english-section-2)
- [Choose references for the stop](#english-section-3)
- [Read delivery over an operating interval](#english-section-4)
- [What additional targets contribute](#english-section-5)
- [Can one maximum describe a recoil event?](#english-section-6)
- [Specify the equipment deliverable](#english-section-7)

<a id="english-section-1"></a>

## Identify the physical target

A marker on the last rigid section, a pipe joint, a rigid outlet and a flexible hose end can all move differently. A rigid-section marker is meaningful for braking response. Actual placement accuracy also depends on the relation between that marker, the outlet and the deposition target. Photograph the target so a later analyst cannot mistake a boom-marker excursion for placement accuracy.

The stopping case names XTDIC-12M and uses the first image as its reference. The delivery test follows several points on the end section and reports component histories and spatial paths in an adjusted coordinate frame. For a laboratory evaluating XTDIC-STROBE, the transferable elements are the questions and outputs. Verify the selected configuration at its intended field of view, speed and surface conditions and keep each record attached to its actual equipment.

<a id="english-section-2"></a>

## Four distances from one coordinate file

Let **P(t)** be the tip position and **P₀** its initial position. Resultant displacement is their straight-line separation. It is non-negative and cannot identify the side of a target. Summing successive distances along the sampled trajectory gives travelled path length at that sampling cadence. A returning tip adds path length even while its resultant displacement becomes small.

| Metric | Interpretation |
| --- | --- |
| Directional error | Projection of position relative to the target onto a chosen signed axis |
| Resultant displacement | Distance to the reference position |
| Range of resultant displacement | Maximum minus minimum distance to that origin within a window |
| Distance between two positions | Straight-line separation of the two actual spatial points |

A tip moving around an arc centred on the reference can maintain the same radius while crossing from side to side. The range of resultant displacement need not equal the distance between the two extreme positions. Preserve the reference case’s first-frame convention when reusing its metric. Calculate signed recoil on the task axis separately for reverse movement past a target.

<a id="english-section-3"></a>

## Choose references for the stop

Keep the first frame, stop-command event and final settled position. The first retains total travel, the stop highlights additional movement after braking, and the target reveals final positioning error. Plot these views from the same recorded coordinates. If the controller log lacks time alignment, identify a visual event and its bounding frames and state where the stop time came from.

On the principal travel axis mark the first target crossing, reversal and last discernible residual oscillation. Inspect vertical and depth components at those times. A frontal projection can suggest a return along the original route while a side view reveals vertical or depth movement. Colouring a path by time or adding arrows distinguishes revisiting an image position from returning to a spatial point. The reported vertical movement accompanying recoil illustrates that benefit.

<a id="english-section-4"></a>

## Read delivery over an operating interval

Reference axes to the working surface. A plan projection shows horizontal coverage, a side projection shows height variation, and a time-indexed spatial trajectory shows whether the changes coincide. A path without time order can look similar for opposing directions of travel.

The delivery record contains motion in several directions. Attributing a repeated component to pumping requires an independently observed pump event, pressure channel or control record aligned to the optical data. Periodic displacement alone does not isolate pumping, operator input or support motion. For a configuration comparison, match boom pose and operating stage and record available process conditions.

<a id="english-section-5"></a>

## What additional targets contribute

Markers on one rigid section can follow very different paths during rotation while their mutual distances stay approximately constant. A step in one distance at a particular attitude warrants checking identities, depth reconstruction and attachment. A pair on different parts can legitimately change separation at a joint. Identify the owning component for each marker.

For end-section orientation, use well-spaced non-collinear targets on the same rigid part and inspect residuals from the fitted rigid motion. Departures above stationary variability warrant reviewing target geometry and the rigidity assumption. Extrapolating that motion to a flexible outlet introduces an additional assumption. Direct tracking near the outlet provides stronger evidence when the task permits it.


<a id="english-section-6"></a>

## Can one maximum describe a recoil event?

For a buffer comparison, plot the work-axis target band and expand the trajectory from braking to first reversal. A horizontal overshoot followed by downward movement can produce its largest spatial distance at a different time from its largest horizontal error. Mark each extreme, check its original image and note the direction of motion. Similar resultant peaks can then be distinguished by horizontal overshoot and vertical travel.

For delivery, separate repositioning, final adjustment and continuous pumping using operator records or video. Including a deliberate move to the next placement location can dominate the apparent delivery envelope. Keep it for positioning studies and identify the settled operating interval for delivery studies. State the duration and range of each segment used.

Camera depth means toward or away from the camera and can change meaning after relocation. Work axes aligned along the task, across it and vertically allow field staff to interpret repeat tests in consistent terms. Exported spatial coordinates make that transformation possible when the site supplies reliable references.

<a id="english-section-7"></a>

## Specify the equipment deliverable

A braking report needs signed component histories aligned to stop, images at extremes and motion about the settled position. A delivery report needs operating duration and condition, multipoint paths, task-axis ranges and gaps. Both benefit from original identifiers and reference coordinates so another reader can recompute a target-side deviation. Acceptance limits come from the machine task.

Stereo measurement earns its place when one acquisition must establish distance travelled, recoil direction and final position. During a demonstration, request time, identifiers and coordinates behind the trajectory image. Recomputing one result with a different reference is a practical test of whether the data will serve both design and test teams.

**Equipment and case documentation**

- [XTDIC-STROBE dynamic measurement system and applications](https://www.xtop3d.com/products/xtdic-strobe.html)

**Related articles**

- [228 · Measuring Crane Boom Sway After Slew Stops with XTDIC Stereo Tracking](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-slew-sway-case.md#english-version)
- [232 · Validating Crane Boom Sway Control with XTDIC Multipoint Trajectories and Dynamic Models](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-anti-sway-validation.md#english-version)

</details>
