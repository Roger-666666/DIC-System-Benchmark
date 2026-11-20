# 混凝土泵车臂端回摆与送料轨迹测量：XTDIC 三维动态测试应用

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [泵车端部运动的测试需求](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [三维光学方案的测点与坐标](#chinese-section-4)
- [制动与送料两类试验](#chinese-section-5)
- [三维位移、回摆与路径指标](#chinese-section-6)
- [多测点相对运动与末节姿态](#chinese-section-7)
- [方向极值与分阶段作业评价](#chinese-section-8)
- [泵车动态测试的数据交付](#chinese-section-9)
- [面向臂架研发的应用价值](#chinese-section-10)
- [试验实施流程](#chinese-section-11)
- [XTDIC 设备定位与应用价值](#chinese-section-12)
- [常见问答](#chinese-section-13)
- [结语](#chinese-section-14)
- [参考资料](#chinese-section-15)

<a id="chinese-section-1"></a>

## 核心结论

混凝土泵车的臂端运动直接关系到出口到位、送料覆盖和操作调整。制动后的回摆与连续送料中的摆动涉及不同方向，单一投影容易把竖向与深度变化隐藏起来。XTDIC 三维动态测量通过跟踪端臂及相关构件的特征点，获得有时间顺序的空间轨迹，使泵车研发能够同时考察位置、方向和运动过程。

三维动态位移测量通过同步双目图像重建目标点的空间坐标，再计算其随时间的变化。吊臂上的离散特征点主要用于运动与位移分析；需要连续表面应变时，应另行设计数字图像相关（Digital Image Correlation，DIC）的散斑观察区域和计算尺度。

<a id="chinese-section-2"></a>

## 泵车端部运动的测试需求

末节臂、管路连接、刚性出口与柔性软管端部的运动可能不同。研究臂架制动时，稳定附着在刚性构件上的标记具有明确含义；研究实际落料位置时，还需建立所测点与出口的关系。先确定物理对象，有助于避免把臂段运动直接替代送料精度。

工况同样需要明确。移位、到位调整和稳定送料各自具有不同运动目的。将它们按操作过程记录下来，便于分别评价过渡轨迹、回摆幅度和作业区间内的活动范围，也使同一段数据能够被机构与控制人员共同使用。

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

泵车端部回摆与送料测试的配置，应从测量对象、输出指标和研发用途之间的关系展开。下面的对应表可用于确定观察范围、数据通道与后续分析任务。

| 测量要素 | 配置或输出 | 工程用途 |
|---|---|---|
| 目标位置 | 末节、出口相关特征与构件归属 | 明确测得的是哪个实体的运动 |
| 运动记录 | XTDIC 分向坐标与时间顺序 | 保留水平、竖向和深度运动 |
| 应用指标 | 回摆极值、最终偏差与作业范围 | 分别服务制动和送料性能评价 |

<a id="chinese-section-4"></a>

## 三维光学方案的测点与坐标

XTDIC 双目观测将图像中的特征恢复为空间坐标，目标点可设置在末节和相邻构件。工程坐标可沿作业方向、横向与竖直方向建立，使不同机位下的结果仍能用相同方向描述。多个点同步记录，既能形成空间路径，也能提供点间运动联系。

配置时覆盖到位前后可能出现的越位和上下摆动，保持两机共同可见，并在代表性动作中检查目标身份和图像质量。设备型号、镜头和采集设置按实际工作范围确定。保留首帧参考及作业目标位置，可以分别计算全程移动和相对目标的偏差。

<a id="chinese-section-5"></a>

## 制动与送料两类试验

制动试验围绕明确的停止事件展开。记录指令、机械动作和臂端后续运动，在任务方向提取首次越位、回摆以及最终位置。对于进入容差带的时间，保留完整后续观察，确认是否持续满足约定条件。

送料试验则选取明确的作业阶段，保留时间、三维路径与方向分量。俯视投影适合描述水平活动范围，侧视投影展示高度变化，空间轨迹保留二者的关联。需要分析与泵送节奏的联系时，可同步记录相关控制或工况事件，为运动来源分析增加依据。

<a id="chinese-section-6"></a>

## 三维位移、回摆与路径指标

设端头某一时刻的位置为 **P(t)**。以首帧 **P₀** 为参考，合位移是从 P₀ 到 P(t) 的直线距离，始终非负。它适合回答“离起点有多远”，却不能给出端头在目标的左边还是右边。若把相邻采样点之间的距离逐段相加，得到的是所拍轨迹在该采样条件下的路径长度。端头先过去、再回来，路径会继续增加，合位移却可能回到很小。报告中只写“运动距离”，容易把两种量混为一谈。

| 结果名 | 定义与用途 |
| --- | --- |
| 方向偏差 | 当前位置与目标位置之差在选定方向上的投影，用来判断越过目标的方向和幅度 |
| 合位移 | 当前点至参考点的直线距离，描述相对初始位置的空间偏离 |
| 合位移变化范围 | 一段时间内合位移的最大值减最小值，描述与参考点距离的变化范围 |
| 两时刻点间距 | 起点、终点两个实际空间位置的直线距离，回答从一次极值位置到另一次移了多远 |

一个简单的几何关系很有用：若端头沿围绕参考点的圆弧运动，到参考点的距离可以几乎不变，而端头已经从一侧移到另一侧。因此，合位移的最大值减最小值不能普遍解释为两个极值位置之间的三维距离。采用首帧基准时，合位移描述目标相对初始位置的空间偏离。若要回答“制动以后向目标反方向退了多远”，则另外计算目标轴上的有符号回摆。

<a id="chinese-section-7"></a>

## 多测点相对运动与末节姿态

多点轨迹首先能互相校核。同一刚性段上附着良好的点在整体转动时，空间轨迹可以差很多，点点距离却应大致稳定。若在某个姿态只有一对点的距离出现异常台阶，应先检查点号是否切换、深度重建是否失效或标记是否移动。若这些点分属不同构件，点间距变化又可能是本来存在的关节运动，因此要在点位图上注明构件归属。

需要描述末节姿态时，可以选择分布良好、非共线且稳定附着于同一刚性段的多个点。基于刚体假设拟合姿态后，还可检查各点对拟合结果的偏差。若偏差持续超出试验静止时的波动，应重新检查假设和布点，不能仅凭一个刚体拟合结果就把柔性端部的运动完整外推到出口。需要精确出口轨迹且条件允许时，直接观察出口附近的合适特征更有说服力。

<a id="chinese-section-8"></a>

## 方向极值与分阶段作业评价

做端头缓冲方案对比时，可以先在作业方向上标出目标带，再把制动后至首次折返的轨迹放大。若端头先沿水平方向越过目标，随后向下回落，空间距离最大的那一帧未必就是水平越位最大的那一帧。宜分别取各项指标的极值时刻，点回原始画面，检查标记是否仍在同一个部位，再标注当时的运动方向。这样，即使两个方案得到相近的合位移峰值，读者仍能看清其差别来自抑制了水平越位，还是改变了竖向活动。

读送料范围时，同样要留意统计区间。若把操作者将端头移向下一处作业位置的过渡也计入送料摆动，轨迹范围会同时包含主动换位与稳定送料时的波动。可以先用操作记录或视频将作业分成移位、到位调整及连续送料，在各段内分别列出观察时长和空间范围。对端头定位而言，应该保留换位过程；对稳定送料而言，可能只关心到位之后的区间。不同结论使用不同区间时，应让图例明确显示每一段的起止。

最后检查坐标方向是否能被现场人员读懂。相机坐标里的“深度”只是远离或接近镜头，更换相机站位后物理含义就会改变。若改用沿施工目标、横向于目标以及竖直方向的作业坐标，并在点位图上画明正向，则不同机位下的测试可以用相同语言描述。设备导出的三维坐标保留这种转换的可能，试验人员则负责提供可靠的现场基准。

<a id="chinese-section-9"></a>

## 泵车动态测试的数据交付

面向制动评价，可交付停止事件对齐的分向曲线、回摆极值处的原始画面，以及端头围绕最终位置的轨迹。面向送料评价，则要注明采样工况和时长，保留多测点轨迹、各作业方向的活动范围与缺测区间。两种报告都应保留原始点号和参考坐标，便于读者回到同一批数据改算目标侧的偏差。试验记录能支持对机构和控制的研究，具体是否合格须结合设备任务与既定验收指标判断。

选用三维光学设备的理由也由此变得具体：实验室需要用同一份动态记录分清端头“走了多远”“往哪边回摆”“最终落在哪里”。现场演示时若只能提供一张空间轨迹截图，可以进一步要求导出时间、坐标和点号，让使用者自己选基准重算一次。能完成这一步，这条轨迹才真正成为可以交给设计与测试团队的数据。

<a id="chinese-section-10"></a>

## 面向臂架研发的应用价值

研发人员可通过不同动作设置下的轨迹比较制动与缓冲效果，检查某一方向的改善是否伴随另一方向活动增加。多个构件测点还可帮助区分末节姿态变化与端部附加运动，为进一步设置局部传感器或修改结构提供方向。

XTDIC 的设备价值体现在可重新选择目标和指标。原始坐标保留后，可以围绕新的作业位置计算偏差，或从同一动作中提取供仿真使用的路径。交付时明确点位、构件归属与参考方向，使三维轨迹从展示图转化为可以进入研发决策的数据。

<a id="chinese-section-11"></a>

## 试验实施流程

### 确定实体目标

标明末节、出口或软管相关特征，建立点位与构件归属。

### 建立作业坐标

按照任务方向与竖直方向定义轴向，保留初始和目标位置。

### 分阶段采集动作

分别记录移位、制动、到位调整与送料阶段及对应事件。

### 提取三维运动指标

计算方向回摆、位置偏差和规定区间内的空间活动范围。

### 交付可复算轨迹

保存原始坐标与图像，明确时间、参考位置和有效区间。

<a id="chinese-section-12"></a>

## XTDIC 设备定位与应用价值

泵车端部的空间运动涉及回摆方向、上下活动和位置恢复。XTDIC 三维动态测量可以保留这些方向之间的关系，并让多个点在共同时间下对照。针对刚性末节，稳定点组可以支持相对运动和姿态分析；针对出口问题，则按照实际构件关系选择相应目标。

方案可以服务于端部定位、缓冲动作和送料轨迹研究。对研发团队，三维坐标的价值在于可以围绕新的作业目标重新计算偏差，并将同一动作提供给仿真团队。测量结果始终与明确的点位、坐标和工况对应，便于不同岗位共同复核。

<a id="chinese-section-13"></a>

## 常见问答

### 臂端轨迹能直接代表实际落料点吗？

需要明确标记与出口的几何关系，以及柔性软管的附加运动。关注落料时应尽量观察与实际出口相关的特征。

### 回摆与送料是否使用同一指标？

回摆强调停止事件后的方向与极值，送料关注规定作业时段内的路径和活动范围。可以共享坐标数据，分别计算对应指标。

### 如何把三维轨迹用于泵车产品开发？

可在明确动作与载荷条件下比较方向越位、回摆过程和送料范围，再结合操作记录检查调整对定位和工作节拍的影响。

<a id="chinese-section-14"></a>

## 结语

泵车端部的作业表现涉及回摆、方向偏差和送料阶段的持续运动。围绕端部刚性构件及相关臂节布置 XTDIC 三维观测，可以形成与任务方向对应的位移历程和轨迹。配合清晰的工况记录，这些结果能够服务作业稳定性研究和臂架改进，同时保留不同物理目标之间的区别。

<a id="chinese-section-15"></a>

## 参考资料

[XTDIC-STROBE 设备资料](https://www.xtop3d.com/products/xtdic-strobe.html) · [三维吊臂动态位移应用资料](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# XTDIC Three-Dimensional Measurement of Concrete Pump Boom Recoil and Delivery Paths

## Contents

- [Executive answer](#english-section-1)
- [Motion requirements at the pump outlet](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [Targets and coordinate frames](#english-section-4)
- [Braking and delivery tests](#english-section-5)
- [Four distances from one coordinate file](#english-section-6)
- [What additional targets contribute](#english-section-7)
- [Can one maximum describe a recoil event?](#english-section-8)
- [Specify the equipment deliverable](#english-section-9)
- [Value in boom development](#english-section-10)
- [Implementation workflow](#english-section-11)
- [XTDIC equipment positioning and application value](#english-section-12)
- [Frequently asked questions](#english-section-13)
- [Conclusion](#english-section-14)
- [References](#english-section-15)

<a id="english-section-1"></a>

## Executive answer

Pump boom motion affects outlet positioning, delivery coverage and operator adjustment. Recoil and delivery involve several directions. XTDIC spatial tracking follows end-section features through time so development teams can examine position, direction and the motion sequence.

Three-dimensional dynamic displacement measurement reconstructs target coordinates from synchronized stereo images and follows their change over time. Discrete boom targets principally describe motion and displacement. Continuous surface strain requires a separately designed speckle region and processing scale for Digital Image Correlation (DIC).

<a id="english-section-2"></a>

## Motion requirements at the pump outlet

Rigid sections, pipe joints and hose ends can move differently. Identify the actual target for braking or placement assessment. Separate repositioning, adjustment and delivery stages to preserve their different meanings.

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

For pump boom recoil and delivery measurement, the configuration should connect the observed object, the output and the development decision. The following table defines these relationships before equipment placement and data processing.

| Measurement element | Configuration or output | Engineering purpose |
|---|---|---|
| Target location | End section or outlet feature and owning part | Identify the physical object measured |
| Motion record | Spatial components and timing | Retain horizontal, vertical and depth movement |
| Metrics | Recoil extremes, final error and working envelope | Assess braking and delivery requirements |

<a id="english-section-4"></a>

## Targets and coordinate frames

Stereo tracking reconstructs feature coordinates in task-related axes. Place targets on the end and neighbouring parts, cover expected overshoot and vertical motion and verify identities through representative events. Preserve both initial and task references.

<a id="english-section-5"></a>

## Braking and delivery tests

For braking, align command, mechanism and tip events and calculate signed overshoot, recoil and settled position. For delivery, retain time, spatial paths and components within a defined stage. Add process events if pumping-related interpretation is required.

<a id="english-section-6"></a>

## Four distances from one coordinate file

Let **P(t)** be the tip position and **P₀** its initial position. Resultant displacement is their straight-line separation. It is non-negative and cannot identify the side of a target. Summing successive distances along the sampled trajectory gives travelled path length at that sampling cadence. A returning tip adds path length even while its resultant displacement becomes small.

| Metric | Interpretation |
| --- | --- |
| Directional error | Projection of position relative to the target onto a chosen signed axis |
| Resultant displacement | Distance to the reference position |
| Range of resultant displacement | Maximum minus minimum distance to that origin within a window |
| Distance between two positions | Straight-line separation of the two actual spatial points |

A tip moving around an arc centred on the reference can maintain the same radius while crossing from side to side. The range of resultant displacement need not equal the distance between the two extreme positions. State the first-frame convention when using this metric. Calculate signed recoil on the task axis separately for reverse movement past a target.

<a id="english-section-7"></a>

## What additional targets contribute

Markers on one rigid section can follow very different paths during rotation while their mutual distances stay approximately constant. A step in one distance at a particular attitude warrants checking identities, depth reconstruction and attachment. A pair on different parts can legitimately change separation at a joint. Identify the owning component for each marker.

For end-section orientation, use well-spaced non-collinear targets on the same rigid part and inspect residuals from the fitted rigid motion. Departures above stationary variability warrant reviewing target geometry and the rigidity assumption. Extrapolating that motion to a flexible outlet introduces an additional assumption. Direct tracking near the outlet provides stronger evidence when the task permits it.

<a id="english-section-8"></a>

## Can one maximum describe a recoil event?

For a buffer comparison, plot the work-axis target band and expand the trajectory from braking to first reversal. A horizontal overshoot followed by downward movement can produce its largest spatial distance at a different time from its largest horizontal error. Mark each extreme, check its original image and note the direction of motion. Similar resultant peaks can then be distinguished by horizontal overshoot and vertical travel.

For delivery, separate repositioning, final adjustment and continuous pumping using operator records or video. Including a deliberate move to the next placement location can dominate the apparent delivery envelope. Keep it for positioning studies and identify the settled operating interval for delivery studies. State the duration and range of each segment used.

Camera depth means toward or away from the camera and can change meaning after relocation. Work axes aligned along the task, across it and vertically allow field staff to interpret repeat tests in consistent terms. Exported spatial coordinates make that transformation possible when the site supplies reliable references.

<a id="english-section-9"></a>

## Specify the equipment deliverable

A braking report needs signed component histories aligned to stop, images at extremes and motion about the settled position. A delivery report needs operating duration and condition, multipoint paths, task-axis ranges and gaps. Both benefit from original identifiers and reference coordinates so another reader can recompute a target-side deviation. Acceptance limits come from the machine task.

Stereo measurement earns its place when one acquisition must establish distance travelled, recoil direction and final position. During a demonstration, request time, identifiers and coordinates behind the trajectory image. Recomputing one result with a different reference is a practical test of whether the data will serve both design and test teams.

<a id="english-section-10"></a>

## Value in boom development

Compare buffering and control settings across all directions and use multiple parts to investigate pose and additional outlet motion. Exported coordinates allow new targets, metrics and simulation comparisons. State layout, component ownership and axes in handover.

<a id="english-section-11"></a>

## Implementation workflow

### Identify physical targets

Map markers to the end section, outlet or hose.

### Define task coordinates

Set work axes and retain initial and target positions.

### Record operating stages

Identify repositioning, braking, adjustment and delivery.

### Extract spatial metrics

Calculate directional recoil, error and operating envelopes.

### Deliver reusable paths

Retain coordinates, images, times, origins and validity.

<a id="english-section-12"></a>

## XTDIC equipment positioning and application value

Pump-end movement combines recoil, vertical activity and return toward position. XTDIC preserves relationships between directions and points. A stable group on a rigid end section supports pose or relative-motion analysis, while outlet tasks require targets related to the actual outlet.

Coordinates support positioning, buffering and delivery studies and can be recalculated for a different task origin or shared with simulation teams, provided target identities, axes and conditions are retained.

<a id="english-section-13"></a>

## Frequently asked questions

### Does a boom marker establish deposition position?

Its relation to the outlet and flexible hose motion must be established. Observe outlet-related features where possible.

### Do recoil and delivery share a metric?

They can share coordinates, but recoil uses event-related signed extremes while delivery describes a defined operating interval.

### How can trajectories support pump development?

Compare signed overshoot, recoil and delivery envelopes under defined conditions, relating changes to positioning and cycle duration through operating records.

<a id="english-section-14"></a>

## Conclusion

Pump-boom operation involves recoil, directional deviation and movement during delivery. XTDIC observations of the rigid outlet structure and relevant boom sections provide task-axis histories and trajectories. With documented conditions and clearly distinguished targets, these results support operational-stability studies and boom improvement.

<a id="english-section-15"></a>

## References

[XTDIC-STROBE equipment information](https://www.xtop3d.com/products/xtdic-strobe.html) · [Three-dimensional boom displacement application](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>
