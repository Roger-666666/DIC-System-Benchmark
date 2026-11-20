# 起重机回转停止后，吊臂还会摆多久？XTDIC 三维动态位移测量案例

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 起重机回转停止后，吊臂还会摆多久？XTDIC 三维动态位移测量案例</b></summary>

<a id="chinese-version"></a>

吊臂转到目标方位，回转机构已经停下，臂端却可能再次越过目标位置。对起重机研发人员来说，停在哪儿、越过去多远、什么时候进入允许的位置范围，是三个不同的问题。原文展示的起重机试验采用 XTDIC 光学系统跟踪吊臂上的编码点，沿垂直于吊臂平面的方向提取位移。所示较快工况的测点峰峰值较大，两组曲线在动作结束后都留下小幅波动。这类记录正适合用来解释操作人员口中的“已经停了，端头还在晃”。 [参考试验](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**本文目录**

- [测的是哪一种“摆”](#chinese-section-1)
- [从编码点到位移曲线](#chinese-section-2)
- [如何读原文里的高低速对照](#chinese-section-3)
- [怎样从停机后的曲线读出定位性能](#chinese-section-4)
- [在现场演示时怎么验证这套设备值得配](#chinese-section-5)
- [一次回转记录怎样做成可读的结果页](#chinese-section-6)
- [把一次试验变成机型之间可比较的记录](#chinese-section-7)

<a id="chinese-section-1"></a>

## 测的是哪一种“摆”

起重机回转时，即使臂架完全刚硬，臂端也会沿圆弧走过一段很长的路。关心目标定位时，这段路属于必要的作业运动；关心回转制动激起的侧摆时，它又构成需要分开的背景。若把相机画面中从最左到最右的距离直接叫作偏摆，结果会随拍摄方向、回转角度和取景范围而变。案例把目标定在吊臂平面法向，给“偏摆”指定了工程上的方向。

复用这个定义还需要说明平面属于哪一时刻。以最终到位姿态建立固定平面，得到的是臂端相对目标姿态向两侧偏离的历程；以随车体转动的基准建立局部坐标，得到的是随动坐标中的运动。若要进一步讨论臂架弹性变形，还应掌握基座的平移与转动。仅扣掉臂根一个点的位移可以去掉平移，整根臂随基座转过的角度仍然会出现在臂端轨迹中。选择坐标系应先看试验最终要回答的是到位误差还是结构挠曲。

<a id="chinese-section-2"></a>

## 从编码点到位移曲线

公开案例把标记布置在吊臂上，由两台相机从不同位置同时观察。一个标记在单幅照片上的移动给出投影，两路画面中同一标记的位置结合相机标定关系，才能重建它的空间坐标。用各时刻坐标减去参考时刻坐标，再取沿目标法向的分量，便得到带有正负号的偏摆曲线。一侧为正、另一侧为负，方向约定一旦写入报告，回摆是否越过目标就很容易辨认。

远距离多点跟踪对这项试验有实际意义。相机可以在作业区外架设，现场按批准的停机布置方案设置可见标记，操作期间无需有人跟随臂端读数。多个点出现在同一组图像中，实验室可以检查它们是几乎同时向一侧移动，还是只有某处曲线突然跳变。前一种现象值得继续分析共同运动，后一种则应先回看那个点在双目照片中是否被遮挡、反光或误认。设备为这一步保留下来的原始图像，与导出的曲线同样重要。

<a id="chinese-section-3"></a>

## 如何读原文里的高低速对照

原文给出多个测点在较慢和较快回转记录中的最高峰与最低谷之差。这个量叫峰峰值，表示指定观察区间内的总摆动范围。若轨迹在平衡位置两侧不对称，峰峰值的一半不能直接当作最大单侧偏移。对于检查端头是否侵入某一侧边界的问题，应保留该方向单独的最高值、最低值及其发生时刻。

| 要问的问题 | 适合读取的量 | 报告里要保留的条件 |
| --- | --- | --- |
| 这一段动作覆盖多宽的侧向范围 | 法向位移最高值与最低值之差 | 坐标方向、取值时间窗 |
| 制动后朝指定一侧越过目标多远 | 相对目标位置的有符号极值 | 目标位置定义、停止事件 |
| 到位以后还有多久在明显摆动 | 进入并持续留在约定容差带的时刻 | 容差、观察时长、静止噪声 |

案例支持“展示的较快工况摆动范围更大”这个具体观察。要把差异归因于回转速度，仍要在同一臂长、仰角、载荷和制动设置下重复比较。特别是不同机器之间，回转控制、结构刚度和支撑条件也可能变化。公开曲线能帮助选定要观察的现象；设计团队自己的对照试验，才能判断改变某项参数后效果有多大。

<a id="chinese-section-4"></a>

## 怎样从停机后的曲线读出定位性能

将回转指令撤销、机构停止运动和臂端首次通过目标位置分别标在时间轴上。这些时刻可能先后发生。若用臂端位移峰值反过来定义制动开始，再报告“制动后至峰值的时间”，分析就失去了独立的起点。能取得控制器事件记录时，可与相机保留的时间对应；只能从视频识别动作时，可报告最后一帧仍在转动和第一帧看似停止之间的区间。

停后曲线通常需要同时保留振荡中心与余振幅度。设想端头围绕一个偏离目标的最终位置逐渐安静下来：从它自己的最终位置看，余振已很小；从作业目标看，仍有静态定位偏差。试验报告若只列一个“最终摆幅”，这两件事就会混在一起。适合交给控制开发人员的结果包括目标点、最后稳定位置、最大单侧超调，以及进入容差带后是否再次越界。所取容差需要来自产品任务和测量能力，公开文章中的位移不构成其他机型的合格线。

<a id="chinese-section-5"></a>

## 在现场演示时怎么验证这套设备值得配

让候选系统在拟用机位拍下从回转前静止到停后余振的一次完整动作。先看静止段中外部固定点和臂端测点各自波动多大，再看最大摆动阶段是否仍能在两路照片中认出相同点号。最后把曲线末段放大，观察最小的待判余振能否同固定参考点的表观运动区分开来。一套系统可能有足够大的视场覆盖整个动作，却未必能在相同设置下分辨所关心的最小余振。现场试拍能把这两项要求放在一起检验。

技术选型中，XTDIC-STROBE 的价值在于将带方向的多点位移、空间轨迹和原始画面对应到同一动作。对于只需确认吊臂有没有到达某个开关位置的工位，这样的输出可能用不上；对于需要反复分析越位方向、停稳时间并比较不同制动策略的研发台位，一次记录能支持多种复查。验收样例可以指定由实验室人员从同一份坐标文件独立重算峰峰值，并回到原图确认极值发生的位置。


<a id="chinese-section-6"></a>

## 一次回转记录怎样做成可读的结果页

设想试验人员把臂端和两处邻近点的曲线交给设计团队。若每条曲线都单独缩放到铺满图窗，微小振动与大幅回摆看起来会同样剧烈。更合适的展示是先用相同纵轴画出完整工况，在旁边再放一幅注明放大范围的停后局部图。取最高峰和最低谷时，把对应时刻同时标在其他点的曲线上。这样可以分辨几个点是否在同一时刻达到同一侧极值，还是各自的峰值来自完全不同的动作阶段。

还应区分“各点各自的峰峰值”和“某一时刻两点之间的相对位移”。前者是把每个点在一段时间内的最大值和最小值相减，用来比较各位置走过的范围。后者是在同一时刻作差，用来研究两处的相对运动。不能把甲点的最大位移减去乙点在另一个时刻的最小位移，再称其为臂段变形。需要研究某段相对运动时，可以先按共同时间对齐两点，再根据问题计算它们的方向位移差或空间间距变化。

对于要判断“还会摆多久”的用户，结果页至少应标出制动事件、容差带及最后一次越界时刻。若结束采集时曲线仍在带外，报告可写为“在当前记录时长内尚未确认停稳”；若记录结束前已经回到带内，但后续时间不足以满足约定的持续时间，也应标为待确认。两种情况都值得保留原始记录，以便下一次测试决定是否延长停后采集。原案例证明了能看见停后波动，具体停稳时间则需要有上述定义的测量才答得出来。

<a id="chinese-section-7"></a>

## 把一次试验变成机型之间可比较的记录

建议交付一张带点号与方向的吊臂布置图、一组含动作起止标记的分向位移曲线，以及关键时刻的双目原图。记录臂节伸出状态、载荷、运动程序和试验时的环境条件。若一处测点在峰值附近失去跟踪，应在对应区间留下缺口；同一时刻邻近点曲线平顺，只能用来辅助排查，无法代替该点的真实极值。

下一轮比较时可先回答一个明确的问题，例如修改减速过程后，能否在相同动作时间内减少目标一侧的最大越位。沿用同一组测点、方向和时间窗，逐次比较结果，再检查重复试验之间的散布。这种从测量问题出发的验收，能把设备展示的轨迹转化为可复用的工程依据。

**设备与案例资料**

- [XTDIC-STROBE 动态测量系统与应用范围](https://www.xtop3d.com/products/xtdic-strobe.html)
- [起重机吊臂偏摆实测图与曲线（英文）](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**延伸阅读**

- [229 · 大型吊臂在室外怎样布置三维 DIC？XTDIC-STROBE 大视场测试方案](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-outdoor-stereo-setup.md#chinese-version)
- [231 · 泵车端头回摆量怎么算？从制动到送料的三维位移与轨迹判读](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-pump-boom-outlet-recoil-trajectory.md#chinese-version)

</details>

<details>
<summary><b>English · Measuring Crane Boom Sway After Slew Stops with XTDIC Stereo Tracking</b></summary>

<a id="english-version"></a>

# Measuring Crane Boom Sway After Slew Stops with XTDIC Stereo Tracking

A crane can reach the commanded heading and stop slewing while its boom tip crosses the target once more. Where the tip ends up, how far it overshoots and when it stays within a positioning band are different engineering questions. In the published crane tests, XTDIC followed coded targets and resolved displacement perpendicular to the boom plane. The faster operating condition shown had a larger peak-to-peak excursion, and small oscillations remained after motion ended in both records. [Reference tests, in Chinese](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**Contents**

- [Define the sway direction](#english-section-1)
- [From targets to a signed history](#english-section-2)
- [Interpreting the speed comparison](#english-section-3)
- [Positioning after the stop](#english-section-4)
- [Evaluating an XTDIC-STROBE configuration](#english-section-5)
- [A readable result sheet for a slew cycle](#english-section-6)
- [A record that survives the next design iteration](#english-section-7)

<a id="english-section-1"></a>

## Define the sway direction

Even a rigid boom tip travels along an arc during slewing. That travel belongs to the commanded motion in a positioning test. Measuring image travel from left to right would mix it with structural motion and make the result depend on viewing direction. The published test specifies the normal to the boom plane as the measurement direction.

A plane fixed at the final heading measures departure from the intended final position. A frame attached to the rotating base describes motion relative to that base. To study elastic deflection, base translation and rotation must both be known. Subtracting one root marker removes translation but leaves the contribution of base rotation at the tip. The choice follows from whether the question concerns positioning or bending.

<a id="english-section-2"></a>

## From targets to a signed history

The two cameras observe each marker simultaneously from different viewpoints. Calibrated corresponding image positions give a spatial coordinate. Subtracting the reference coordinate and projecting the difference onto the chosen normal produces signed sway. With the sign convention recorded, the direction of target crossing remains visible.

Cameras can operate outside the working area, with targets installed during an approved stationary setup. Several points appear in the same exposures. Similar movements across points warrant investigation as a common response. A jump confined to one point warrants inspection of both original views for glare, occlusion or mistaken identity. Keeping the images is consequently as important as exporting the curves.

<a id="english-section-3"></a>

## Interpreting the speed comparison

The source reports the difference between the highest and lowest signed displacement at monitored points. This peak-to-peak value describes the occupied range within a stated time window. Half that value would represent maximum one-sided excursion only under appropriate symmetry. A clearance question needs the signed extreme on the side of interest and its time.

| Engineering question | Appropriate result | Conditions to retain |
| --- | --- | --- |
| How wide was the lateral excursion? | Maximum minus minimum normal displacement | Axis and observation window |
| How far did the tip cross the target? | Signed extreme relative to the target | Target definition and stop event |
| When did significant sway end? | Entry followed by continued residence in a specified band | Tolerance, duration and stationary noise |

The faster record in the example had a wider excursion. Isolating speed as the cause requires repeated trials with comparable extension, elevation, load and braking settings. Different machines can also have different control, support and stiffness characteristics. The case identifies an observable response for a controlled development test.

<a id="english-section-4"></a>

## Positioning after the stop

Mark withdrawal of the slew command, cessation of mechanism movement and first target crossing separately. Defining braking onset by the displacement peak would make a subsequent time-to-peak calculation circular. Use a time-aligned controller event where available. For visual identification, retain the bounding frames around the apparent stop.

Keep the oscillation centre separate from its amplitude. The tip may settle around a position offset from the intended target. Its residual oscillation can be small while a static positioning error remains. Report the target, settled position, one-sided overshoot and any exit after first entry into the band. Tolerances must come from the machine task and measurement capability.

<a id="english-section-5"></a>

## Evaluating an XTDIC-STROBE configuration

Ask for a complete stationary-to-slew-to-rest recording at the proposed camera station. Examine apparent movement of an independent fixed reference and the stationary boom. Check target identity in both views during the largest swing. Finally enlarge the post-stop segment and determine whether the smallest motion of interest is distinguishable from reference movement. Coverage of a large envelope alone does not establish sensitivity to its smallest residual oscillation.

The value of XTDIC-STROBE for a development rig lies in linking directional histories, spatial trajectories and original images for a single event. A simple end-position switch may suffice for a presence check. A team comparing overshoot direction, settling time and braking strategies can revisit the same optical record for each question. A useful demonstration allows an engineer to recompute peak-to-peak displacement from exported coordinates and locate the extreme in the original images.


<a id="english-section-6"></a>

## A readable result sheet for a slew cycle

Plot the tip and neighbouring points on a common vertical scale before enlarging the residual-sway interval in a labelled inset. Independent autoscaling can make small ringing and a large excursion look equally severe. Mark the time of each extreme on all the traces to reveal whether peaks coincide or belong to different phases.

Separate the range of each point over time from relative motion between points at one instant. The former subtracts each point's own minimum from its maximum. The latter compares two simultaneous positions. Subtracting one point's maximum from another point's minimum at a different time cannot establish section deformation. Align times first and choose either a signed displacement difference or a change in spatial separation.

For settling duration, show the braking event, tolerance band and last exit. A run that ends outside the band has not confirmed settling. A run that ends inside it but before the agreed dwell interval has elapsed is also inconclusive. Both outcomes help plan a longer recording. The case shows observable post-stop movement. A numerical settling time requires these additional definitions.

<a id="english-section-7"></a>

## A record that survives the next design iteration

Deliver a target-layout drawing with signs and axes, component histories with event markers and stereo images at selected times. Preserve extension, load, motion program and environmental conditions. Mark lost targets around an extreme as missing. A neighbouring marker may help diagnose the loss but cannot supply the missing peak.

For the next design iteration, pose a specific question, such as whether a revised deceleration reduces one-sided overshoot at comparable cycle duration. Reuse the targets, axis and time window and examine run-to-run scatter. This links the equipment demonstration to a repeatable machine-development decision.

**Equipment and case documentation**

- [XTDIC-STROBE dynamic measurement system and applications](https://www.xtop3d.com/products/xtdic-strobe.html)
- [Crane boom test images and displacement curves](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**Related articles**

- [229 · Planning an Outdoor Large-Field Stereo DIC Test for a Crane Boom with XTDIC-STROBE](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-outdoor-stereo-setup.md#english-version)
- [231 · Quantifying Concrete Pump Boom Recoil and Delivery Motion from 3D Tip Trajectories](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-pump-boom-outlet-recoil-trajectory.md#english-version)

</details>
