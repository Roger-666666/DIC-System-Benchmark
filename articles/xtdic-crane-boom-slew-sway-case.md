# 大型起重机吊臂偏摆测试：XTDIC-STROBE 三维动态位移测量应用方案

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [吊臂动态测试的行业需求](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [远距离多点三维测量的工作方式](#chinese-section-4)
- [面向回转与制动的试验设计](#chinese-section-5)
- [停后余振与定位性能评价](#chinese-section-6)
- [多测点响应与停稳指标](#chinese-section-7)
- [机型迭代中的重复测试](#chinese-section-8)
- [在产品平台研发中的扩展应用](#chinese-section-9)
- [从位移记录到产品改进](#chinese-section-10)
- [试验实施流程](#chinese-section-11)
- [XTDIC 设备定位与应用价值](#chinese-section-12)
- [常见问答](#chinese-section-13)
- [结语](#chinese-section-14)
- [参考资料](#chinese-section-15)

<a id="chinese-section-1"></a>

## 核心结论

大型起重机在回转、变幅与制动时，长臂结构会出现随动作发展的空间位移和振动。臂端偏摆影响到位性能，停后余振又关系到下一步操作的等待时间。XTDIC-STROBE 三维动态测量系统通过远距离双目成像跟踪臂上特征点，输出多位置的分向位移和空间轨迹，为臂架研发、制动性能评价与动态响应研究提供非接触测量方案。

三维动态位移测量通过同步双目图像重建目标点的空间坐标，再计算其随时间的变化。吊臂上的离散特征点主要用于运动与位移分析；需要连续表面应变时，应另行设计数字图像相关（Digital Image Correlation，DIC）的散斑观察区域和计算尺度。

<a id="chinese-section-2"></a>

## 吊臂动态测试的行业需求

长臂结构的运动同时包含回转机构带来的整体位移、支撑处运动以及臂架的弹性响应。地面观察人员能够发现明显摆动，但要量化动作过程中的方向、极值和余振，需要具有尺度和时间信息的记录。研发团队还希望比较不同臂节之间的运动，了解端部变化是否伴随中段或底座响应。

传统布线方式在高处、大运动范围或频繁换机型的测试中可能增加准备工作。光学系统可在作业区域外建立观察位置，通过预先布置的稳定标记获取运动。它特别适合需要把同一动作交给控制、结构和试验人员共同分析的开发场景。

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

起重机回转偏摆测试的配置，应从测量对象、输出指标和研发用途之间的关系展开。下面的对应表可用于确定观察范围、数据通道与后续分析任务。

| 测量要素 | 配置或输出 | 工程用途 |
|---|---|---|
| 测量对象 | 臂端、代表性臂节与参考点 | 保留沿臂架分布的运动信息 |
| 设备输出 | XTDIC-STROBE 三维坐标与分向位移 | 区分侧向越位、竖向运动与空间路径 |
| 性能评价 | 峰峰值、单侧极值与停后历程 | 服务定位性能和制动响应研究 |

<a id="chinese-section-4"></a>

## 远距离多点三维测量的工作方式

两台相机同步识别同一特征点，通过标定关系计算其空间位置。XTDIC-STROBE 持续跟踪目标后，可以按照工程坐标分解侧向、竖向和其他方向的位移，并保留点的空间路径。多个目标共享采集时序，便于比较不同位置的同阶段响应。

布点可覆盖臂端、代表性臂节和适当的参考区域。远距离成像减少操作期间接近运动结构的需要，点位图则使曲线可以对应到真实构件。对于需要局部材料应变的任务，可另外设计相应散斑区和空间分辨率；臂上稀疏点跟踪主要服务位移与运动分析。

<a id="chinese-section-5"></a>

## 面向回转与制动的试验设计

试验可设置相近臂长、仰角与载荷下的回转动作，在开始前记录静止基线，并持续采集至停后观察结束。以机械动作或控制事件建立时间零点，以目标方位建立方向。各组比较使用共同的点号和坐标定义，便于区分动作改变与测量布置改变。

针对端头定位，可分别提取最大单侧越位、最终位置偏差和进入容差范围的时间。针对结构响应，可观察不同臂节的相对运动与回摆趋势。有效数据中出现的重复特征用于比较，而被遮挡或失配的区间保留缺测标记，以便研发人员明确哪些指标仍有完整记录。

<a id="chinese-section-6"></a>

## 停后余振与定位性能评价

将回转指令撤销、机构停止运动和臂端首次通过目标位置分别标在时间轴上。这些时刻可能先后发生。若用臂端位移峰值反过来定义制动开始，再报告“制动后至峰值的时间”，分析就失去了独立的起点。能取得控制器事件记录时，可与相机保留的时间对应；只能从视频识别动作时，可报告最后一帧仍在转动和第一帧看似停止之间的区间。

停后曲线通常需要同时保留振荡中心与余振幅度。设想端头围绕一个偏离目标的最终位置逐渐安静下来：从它自己的最终位置看，余振已很小；从作业目标看，仍有静态定位偏差。试验报告若只列一个“最终摆幅”，这两件事就会混在一起。适合交给控制开发人员的结果包括目标点、最后稳定位置、最大单侧超调，以及进入容差带后是否再次越界。所取容差根据产品任务和现场测量能力确定。

<a id="chinese-section-7"></a>

## 多测点响应与停稳指标

设想试验人员把臂端和两处邻近点的曲线交给设计团队。若每条曲线都单独缩放到铺满图窗，微小振动与大幅回摆看起来会同样剧烈。更合适的展示是先用相同纵轴画出完整工况，在旁边再放一幅注明放大范围的停后局部图。取最高峰和最低谷时，把对应时刻同时标在其他点的曲线上。这样可以分辨几个点是否在同一时刻达到同一侧极值，还是各自的峰值来自完全不同的动作阶段。

还应区分“各点各自的峰峰值”和“某一时刻两点之间的相对位移”。前者是把每个点在一段时间内的最大值和最小值相减，用来比较各位置走过的范围。后者是在同一时刻作差，用来研究两处的相对运动。不能把甲点的最大位移减去乙点在另一个时刻的最小位移，再称其为臂段变形。需要研究某段相对运动时，可以先按共同时间对齐两点，再根据问题计算它们的方向位移差或空间间距变化。

对于要判断“还会摆多久”的用户，结果页至少应标出制动事件、容差带及最后一次越界时刻。若结束采集时曲线仍在带外，报告可写为“在当前记录时长内尚未确认停稳”；若记录结束前已经回到带内，但后续时间不足以满足约定的持续时间，也应标为待确认。两种情况都值得保留原始记录，以便下一次测试决定是否延长停后采集。停稳指标按统一的容差与持续时间定义计算，可用于同类动作的重复比较。

<a id="chinese-section-8"></a>

## 机型迭代中的重复测试

建议交付一张带点号与方向的吊臂布置图、一组含动作起止标记的分向位移曲线，以及关键时刻的双目原图。记录臂节伸出状态、载荷、运动程序和试验时的环境条件。若一处测点在峰值附近失去跟踪，应在对应区间留下缺口；同一时刻邻近点曲线平顺，只能用来辅助排查，无法代替该点的真实极值。

下一轮比较时可先回答一个明确的问题，例如修改减速过程后，能否在相同动作时间内减少目标一侧的最大越位。沿用同一组测点、方向和时间窗，逐次比较结果，再检查重复试验之间的散布。这种从测量问题出发的验收，能把设备展示的轨迹转化为可复用的工程依据。

<a id="chinese-section-9"></a>

## 在产品平台研发中的扩展应用

对于采用不同臂节组合的机型，可将同一套三维观测用于比较代表性姿态。较短姿态便于建立初始测试方法，伸展姿态则更需要检验视场、深度变化和停后运动。每一种构型保存自己的几何与负载条件，再按明确的问题比较，可避免把结构变化与操作变化混在一起。

设计阶段可以关注末端运动方向是否满足作业需求，调试阶段可以关注减速过程与回摆，重复验证阶段则可以检查同一动作的响应是否稳定。多个阶段共享数据格式和点位说明后，研发人员能够沿同一位置追溯设计变化。必要时结合独立的局部应变或其他振动通道，把空间位移研究进一步连接到结构力学分析。

这种配置适合以多工况迭代为常态的开发团队。采购决策可以围绕典型产品的实际观察任务展开，让测试方法与设备一起交付，使后续人员具备重建坐标、计算方向指标并复查原图的能力。

<a id="chinese-section-10"></a>

## 从位移记录到产品改进

设计人员可用不同工况的轨迹检查大幅侧摆发生在哪一段动作，并据此调整减速安排、结构参数或试验条件。若改进后侧向越位减小，还可检查竖向响应与总动作时间，评价改变是否符合整机任务。

XTDIC-STROBE 的配置价值体现在可复用数据。一次采集可以保留原始画面、三维坐标和各测点历程，后续按不同目标位置重新计算指标。交付中明确机位、臂架姿态、载荷与参考系后，实验室能够在机型迭代中保持可比较的动态测试方法。

<a id="chinese-section-11"></a>

## 试验实施流程

### 确定代表动作

记录回转范围、臂长、仰角和载荷，明确偏摆方向与停稳定义。

### 配置共同视野

覆盖关键点及预计回摆，设置独立参考并校核坐标。

### 采集完整动作

保留初始静止、动作执行及停后观察阶段，与控制事件对应。

### 计算方向指标

提取有符号越位、最终位置与停后历程，标记极值图像。

### 比较迭代结果

沿用同一指标与条件重复测试，观察控制或构型改变的影响。

<a id="chinese-section-12"></a>

## XTDIC 设备定位与应用价值

XTDIC-STROBE 在吊臂测试中的优势，是让多个关键位置在共同时间下形成三维运动记录。臂端侧摆、不同臂节的运动差异和停后余振，可以从同一份数据中提取。测量头位于允许的外部机位，编码点或稳定特征承担目标识别，使大运动范围下的位移研究具备直接的空间依据。

对整机研发团队，设备交付可延伸到机型迭代。保留点位、参考系和动作条件后，可以比较调整减速程序、改变臂节组合或改变代表工况后的响应。原始图像与数值轨迹共同保存，也便于其他岗位核对极值属于哪个构件、发生在哪一阶段。

<a id="chinese-section-13"></a>

## 常见问答

### 三维测点与吊臂应变场有什么关系？

三维测点适合描述关键位置的运动。需要连续表面应变时，应另行规划散斑覆盖和局部观察尺度，使设备配置服务相应物理量。

### 重复测试最需要固定哪些条件？

应记录臂节伸出、仰角、载荷与动作程序，并沿用点号、方向和事件定义。初始静止状态也会影响停后比较。

### 起重机为何需要三维动态位移测量？

臂端运动可能同时包含侧向、竖向和深度变化。三维坐标便于按任务方向提取偏摆，并在同一动作中比较多个位置的响应。

<a id="chinese-section-14"></a>

## 结语

大型吊臂的偏摆评价需要兼顾运动方向、极值时刻和停止后的响应。XTDIC-STROBE 通过多点三维记录，把臂端与沿臂架分布的运动连接到同一动作过程。由此建立的分向位移、空间轨迹和停稳指标，可以持续服务整机定位性能研究与产品迭代。

<a id="chinese-section-15"></a>

## 参考资料

[XTDIC-STROBE 设备资料](https://www.xtop3d.com/products/xtdic-strobe.html) · [三维吊臂动态位移应用资料](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# XTDIC-STROBE for Three-Dimensional Dynamic Sway Measurement of Large Crane Booms

## Contents

- [Executive answer](#english-section-1)
- [Requirements in boom testing](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [Remote multipoint measurement](#english-section-4)
- [Designing slew and braking tests](#english-section-5)
- [Positioning after the stop](#english-section-6)
- [A readable result sheet for a slew cycle](#english-section-7)
- [A record that survives the next design iteration](#english-section-8)
- [Use across product configurations](#english-section-9)
- [From measured movement to product improvement](#english-section-10)
- [Implementation workflow](#english-section-11)
- [XTDIC equipment positioning and application value](#english-section-12)
- [Frequently asked questions](#english-section-13)
- [Conclusion](#english-section-14)
- [References](#english-section-15)

<a id="english-section-1"></a>

## Executive answer

Large crane booms move and vibrate during slewing, luffing and braking. Tip sway affects positioning, while residual vibration affects readiness for the next operation. XTDIC-STROBE follows multiple visible targets through remote stereo imaging, providing component displacement and spatial paths for boom development and braking-response assessment.

Three-dimensional dynamic displacement measurement reconstructs target coordinates from synchronized stereo images and follows their change over time. Discrete boom targets principally describe motion and displacement. Continuous surface strain requires a separately designed speckle region and processing scale for Digital Image Correlation (DIC).

<a id="english-section-2"></a>

## Requirements in boom testing

Boom motion combines commanded rotation, support movement and elastic response. Quantitative development needs scaled, timed observations across the tip, intermediate sections and references. Remote optical placement is useful for large envelopes and configurations shared by structural, control and test teams.

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

For crane slewing and sway tests, the configuration should connect the observed object, the output and the development decision. The following table defines these relationships before equipment placement and data processing.

| Measurement element | Configuration or output | Engineering purpose |
|---|---|---|
| Targets | Tip, representative sections and references | Observe motion along the boom |
| Outputs | Spatial coordinates and displacement components | Resolve lateral, vertical and spatial movement |
| Assessment | Peak-to-peak range, signed extremes and residual motion | Support positioning and braking studies |

<a id="english-section-4"></a>

## Remote multipoint measurement

Synchronized camera observations reconstruct spatial coordinates. XTDIC-STROBE provides task-axis components and paths for multiple targets on one timeline. Identify each physical part in a layout. Sparse targets serve motion analysis; local material strain requires a separately designed patterned region.

<a id="english-section-5"></a>

## Designing slew and braking tests

Run comparable motions with recorded extension, elevation and load, including an initial stationary interval and post-stop observation. Use common events and axes. Extract signed overshoot, final offset and settling measures for positioning, or relative station movements for structural studies. Preserve gaps.

<a id="english-section-6"></a>

## Positioning after the stop

Mark withdrawal of the slew command, cessation of mechanism movement and first target crossing separately. Defining braking onset by the displacement peak would make a subsequent time-to-peak calculation circular. Use a time-aligned controller event where available. For visual identification, retain the bounding frames around the apparent stop.

Keep the oscillation centre separate from its amplitude. The tip may settle around a position offset from the intended target. Its residual oscillation can be small while a static positioning error remains. Report the target, settled position, one-sided overshoot and any exit after first entry into the band. Tolerances must come from the machine task and measurement capability.

<a id="english-section-7"></a>

## A readable result sheet for a slew cycle

Plot the tip and neighbouring points on a common vertical scale before enlarging the residual-sway interval in a labelled inset. Independent autoscaling can make small ringing and a large excursion look equally severe. Mark the time of each extreme on all the traces to reveal whether peaks coincide or belong to different phases.

Separate the range of each point over time from relative motion between points at one instant. The former subtracts each point's own minimum from its maximum. The latter compares two simultaneous positions. Subtracting one point's maximum from another point's minimum at a different time cannot establish section deformation. Align times first and choose either a signed displacement difference or a change in spatial separation.

For settling duration, show the braking event, tolerance band and last exit. A run that ends outside the band has not confirmed settling. A run that ends inside it but before the agreed dwell interval has elapsed is also inconclusive. Both outcomes help plan a longer recording. Settling time can be compared across runs using consistent tolerance and dwell definitions.

<a id="english-section-8"></a>

## A record that survives the next design iteration

Deliver a target-layout drawing with signs and axes, component histories with event markers and stereo images at selected times. Preserve extension, load, motion program and environmental conditions. Mark lost targets around an extreme as missing. A neighbouring marker may help diagnose the loss but cannot supply the missing peak.

For the next design iteration, pose a specific question, such as whether a revised deceleration reduces one-sided overshoot at comparable cycle duration. Reuse the targets, axis and time window and examine run-to-run scatter. This links the equipment demonstration to a repeatable machine-development decision.

<a id="english-section-9"></a>

## Use across product configurations

A product family can use a common coordinate format across different section combinations while retaining each configuration's geometry and load. Development may examine motion direction, commissioning may focus on braking, and repeated verification may assess consistency. Shared target documentation lets teams follow the same physical locations through iterations. Independent strain or vibration channels can extend the study where structural mechanics requires them. Delivering a repeatable method with the equipment supports teams that routinely test multiple operating conditions.

<a id="english-section-10"></a>

## From measured movement to product improvement

Trajectories identify which stage produces lateral excursions and allow assessment of deceleration or structural changes alongside vertical motion and cycle time. Images and exported coordinates can be reanalysed for different targets. Consistent setup and condition records support machine iterations.

<a id="english-section-11"></a>

## Implementation workflow

### Define the event

Record range, extension, elevation, load and sway criteria.

### Configure common coverage

Include targets, return swing and independent references.

### Acquire the full event

Retain rest, motion and post-stop observation with control timing.

### Calculate signed metrics

Extract overshoot, final position and residual histories with images at extremes.

### Compare iterations

Repeat consistent conditions after control or configuration changes.

<a id="english-section-12"></a>

## XTDIC equipment positioning and application value

XTDIC-STROBE records several key positions on a shared timeline. Tip sway, differences along the boom and residual movement can be extracted from one acquisition. Permitted external camera stations and stable target identification provide direct spatial observations over the intended motion envelope.

Documented targets, frames and conditions support comparisons after changes in deceleration, section combinations or operating conditions. Images alongside numerical paths let other teams locate an extreme on the actual component and event.

<a id="english-section-13"></a>

## Frequently asked questions

### Do target coordinates provide a continuous strain field?

They describe motion at selected locations. Continuous strain requires suitable surface pattern coverage and spatial resolution.

### What needs consistency across runs?

Extension, elevation, load, program, identifiers, axes, events and initial rest conditions.

### Why measure crane motion in three dimensions?

The tip can move laterally, vertically and in depth. Spatial coordinates provide task-axis sway and simultaneous comparisons between stations.

<a id="english-section-14"></a>

## Conclusion

Large-boom sway assessment requires direction, event timing and post-stop response. XTDIC-STROBE links tip and distributed target motion to one operating cycle. Component histories, spatial trajectories and defined settling measures can then support positioning studies and machine development.

<a id="english-section-15"></a>

## References

[XTDIC-STROBE equipment information](https://www.xtop3d.com/products/xtdic-strobe.html) · [Three-dimensional boom displacement application](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

</details>
