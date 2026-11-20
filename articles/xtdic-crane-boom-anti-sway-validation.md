# 吊臂抑摆控制改进如何验证？用 XTDIC 多点轨迹对标制动策略与动力学仿真

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 吊臂抑摆控制改进如何验证？用 XTDIC 多点轨迹对标制动策略与动力学仿真</b></summary>

<a id="chinese-version"></a>

吊臂在修改减速程序后看起来更稳，原因可能是控制策略更有效，也可能只是这一次动作更慢、伸臂更短或观察方向变了。要验证改进，关键是保留可比较的指令、姿态与负载，并用独立测量得到臂端相对目标的运动。XTDIC-STROBE 的多点三维轨迹适合充当这项外部观测。原文展示了起重机停后余振和泵车端头回摆；下文以这些现象为出发点，设计一种可用于研发对照的试验，并不声称原案例已验证某种控制器。 [参考试验](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**本文目录**

- [把“更稳”改写成可以失败的预测](#chinese-section-1)
- [分别安排运动基准、结构测点和独立对照](#chinese-section-2)
- [让基线和改进方案经受同一组动作](#chinese-section-3)
- [同一条曲线怎样检验控制性能](#chinese-section-4)
- [动力学仿真应当预测哪条实测曲线](#chinese-section-5)
- [从试验结论反推下一轮该改哪里](#chinese-section-6)
- [研发台位为什么值得配置外部光学测量](#chinese-section-7)

<a id="chinese-section-1"></a>

## 把“更稳”改写成可以失败的预测

假设一项修改希望在相同工作节拍下减少制动后的侧向越位。试验前应先约定几项结果：比较哪一个点、相对哪一个目标、朝哪一侧为正，从什么事件起算，以及如何定义工作节拍。若主要目标是减少某一侧的最大偏离，就不要在测试完后因另一条曲线更好看而临时改用空间合位移。可同时保留其他方向的结果作为观察量，它们有助于检查侧向改善有没有伴随额外竖向摆动。

另一个常见需求是缩短“可开始下一步作业”的等待时间。这一时间包括机构完成主动作和端头进入允许范围的过程。修改后的程序可能牺牲主动作时间以减少后续振荡。单独列停后余振会显得很好，但从发出动作指令到端头可用的总时间未必变短。报告应让两段时间都能被看到，并使用研发团队在试验前批准的目标范围与观察时长。

<a id="chinese-section-2"></a>

## 分别安排运动基准、结构测点和独立对照

地面稳定参考有助于识别相机支架运动，车体上的参考则描述底座相对地面的运动。沿臂架选择末端及中间臂节的目标，用途是区分各部位的响应。若任务要求扣除回转机构带来的刚体运动，应有足够的参考几何来估计底座姿态；只减去一个基点的轨迹不能消除转动。若任务是评估实际作业区内的端头定位，则地面坐标中的完整轨迹也应保留，不能只交付扣除车体运动后的轨迹。

| 记录 | 在验证中的角色 | 最需要避免的混淆 |
| --- | --- | --- |
| 回转指令或阀控事件 | 描述输入与制动起始 | 将命令停止视为臂端已经停住 |
| 地面参考与车体参考 | 检查相机稳定性，描述底座运动 | 把随车参考当作地面静止点 |
| 中段和臂端坐标 | 检验沿臂响应与目标侧越位 | 只留下一个无方向的最大值 |
| 载荷、伸出状态和姿态 | 对齐比较条件 | 将不同结构状态的差别归于控制策略 |

试验中可保留控制器自身估计的端头位置，但应另存光学观测。控制器估计值参与闭环控制时，它与指令吻合并不必然说明实体端头按预期移动。独立相机观察的价值正在于揭示这种差别。若控制器与光学通道并非共用时钟，需用两边都能识别且物理含义清楚的事件建立时间对应。用事后平移曲线强行让峰值重合，会抹掉正在验证的响应滞后。

<a id="chinese-section-3"></a>

## 让基线和改进方案经受同一组动作

建立一组能重复执行的动作，尽量保持臂长、仰角、载荷状态和回转范围一致。记录动作开始前端头是否已经稳定，因为尚未衰减的前一次摆动可能与本次制动相叠加。同一组比较中尽量使用同一机位、点号和坐标方向。存在环境变化时，可以交替实施基线和改进方案，并保存各次运行条件，避免把随时间变化的风或设备状态只分配给其中一组。

结果应逐次展示。若某个点在端头越过目标时刚好被遮挡，这次运行仍可保留其他可用通道，但它不能提供该点可靠的最大越位。若只删掉不利于某一方案的缺测记录，就会给比较带来偏差。可提前定义何种可见区间和初始状态属于有效试验，并同时报告无法判读的原因。比较之前也应从静止记录估计光学坐标在相应方向的波动范围，确认期待辨别的改善足以高于背景波动。

<a id="chinese-section-4"></a>

## 同一条曲线怎样检验控制性能

对于每一次有效动作，先在任务轴上读取有符号的偏差，标出第一次越过目标的极值。再检查后续是否从另一侧越界，并读取进入容差带后持续留在其中的时刻。若采集在仍明显摆动时结束，只能说明在已观测时间内尚未确认停稳。把最后一帧当成停稳时刻会低估等待时间。控制程序的速度设置、极值方向与有效观察窗需要随结果一起保存。

设想改进程序的第一下越位变小，后续却有更多次小摆动。若任务是避免跨越某侧边界，第一项改善具有实际价值；若任务要求端头持续保持在一小块作业区域，最终可用时间可能更重要。另一种情况是臂端曲线变好，中间臂节响应反而增大。多点记录能把这种代价显现出来，但单凭位移增大还不足以判定某处应力增加，进一步解释需要结构模型或独立应变测量。

<a id="chinese-section-5"></a>

## 动力学仿真应当预测哪条实测曲线

把模型中的输出节点放到与光学标记相同的物理位置，确认模型和试验使用同一参考系、同一时间零点和同一坐标单位。若网格节点与实际标记错开，可按构件上的安装位置建立虚拟测点。长臂转动时，小位置差也会改变点的运动幅度，不能只因为两个点都叫“臂端”就直接对比。可同时看方向峰值、到达峰值的时间以及余振波形，分别检验幅度、相位和衰减特征。

如果实测的底座运动已经作为仿真输入，模型重现底座轨迹只是正确施加边界条件。真正独立的比较量可以选在中段或臂端。若各点整体都滞后，优先检查输入事件、时钟和执行机构响应；若根部相近而端部差异逐渐放大，则值得进一步检查臂节刚度、关节间隙或阻尼，但不能仅凭这种图形就锁定唯一原因。用一个工况调整参数之后，还应留出其他动作进行独立预测，才有依据讨论模型的迁移能力。


<a id="chinese-section-6"></a>

## 从试验结论反推下一轮该改哪里

设想基线方案和改进方案都完成了同一回转动作。改进方案的端头峰值更小，但控制日志也显示主动作持续时间变长。在这组证据下，可以先记录“当前运行条件下越位较小”，同时单列周期代价。下一轮若要判断是否源于减速曲线形状，可让对照程序保持相近总动作时间，再检查差异是否重现。这样的对照比直接宣布控制器提高了结构阻尼更贴近现有证据，因为臂架材料和连接形式在程序修改前后可能根本没有改变。

另一种结果是端头侧向波动下降、臂段之间的相对位移几乎没变。此时值得检查车体是否整体晃动减小，或者改变的是主要回转运动。将地面参考下的臂端轨迹与随车坐标下的相对轨迹并排展示，通常能缩小解释范围。若两者都下降，结构响应和整体运动可能同时受益；若只有地面坐标中的量下降，则直接归因于臂段弯曲减小仍缺证据。

最终报告可以只突出一个与研发任务有关的主要结论，再附各方向记录和有效工况。例如对停稳指标，说明参考目标、观察截止时间、重复动作的分布，以及有几次未能在记录结束前确认停稳。对模型验证，则说明输入用了哪些实测量、留出了哪些独立观测。让“还不能区分哪些原因”也有具体对应的下一项测量，实验室才知道是需要增加一个基准点、补采控制事件，还是值得重新布置整套试验。

<a id="chinese-section-7"></a>

## 研发台位为什么值得配置外部光学测量

同一份 XTDIC 记录可以被不同岗位独立复用。控制工程师用目标坐标和停稳判据评价程序，结构工程师用各点相对运动定位值得复查的臂段，仿真人员按虚拟测点提取预测轨迹。适合交接的结果包括编号点位图、参考坐标、原始时序、缺测标记、事件表以及每次对照试验的条件。另附一幅关键帧，让下一位使用者确认峰值来自哪一个真实构件。

设备采购可以安排一项与研发任务相同的演示：由实验室指定一段制动动作，设备方交付多点坐标，由控制和仿真团队分别重算一个约定指标。两方都能从同一份记录得到可解释的结果，说明这项配置能服务日常迭代。至于某一版控制程序是否达到整机验收条件，仍应依据项目规定的工况、重复试验与判据作出结论。

**设备与案例资料**

- [XTDIC-STROBE 动态测量系统与应用范围](https://www.xtop3d.com/products/xtdic-strobe.html)
- [起重机吊臂偏摆实测图与曲线（英文）](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**延伸阅读**

- [228 · 起重机回转停止后，吊臂还会摆多久？XTDIC 三维动态位移测量案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-slew-sway-case.md#chinese-version)
- [231 · 泵车端头回摆量怎么算？从制动到送料的三维位移与轨迹判读](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-pump-boom-outlet-recoil-trajectory.md#chinese-version)

</details>

<details>
<summary><b>English · Validating Crane Boom Sway Control with XTDIC Multipoint Trajectories and Dynamic Models</b></summary>

<a id="english-version"></a>

# Validating Crane Boom Sway Control with XTDIC Multipoint Trajectories and Dynamic Models

A boom can look steadier after a deceleration change because the controller improved, the run slowed down, the extension changed or the camera saw a different direction. A development comparison requires comparable input, pose and load plus an independent observation of the tip relative to its target. XTDIC-STROBE multipoint histories can supply that external observation. The published crane and pump records motivate the following test design. They do not establish a controller improvement. [Reference tests, in Chinese](https://mp.weixin.qq.com/s/d0u425YBDpKgXK-3bYqRMQ)

**Contents**

- [Turn “steadier” into a prediction that can fail](#english-section-1)
- [Assign roles to references and response points](#english-section-2)
- [Compare the same operating tasks](#english-section-3)
- [Read performance from component histories](#english-section-4)
- [Give the dynamic model a measurable prediction](#english-section-5)
- [Using the result to design the next comparison](#english-section-6)
- [Justifying external optical measurement on a development rig](#english-section-7)

<a id="english-section-1"></a>

## Turn “steadier” into a prediction that can fail

Suppose the change is intended to reduce post-braking lateral overshoot at the same cycle duration. Predefine the target point, origin, positive side, event zero and cycle definition. Use the specified signed component for the primary result. Keep other directions to check whether improved lateral behaviour is accompanied by additional vertical movement.

A different objective is the time until the next operation can begin. This includes main motion and residence within an acceptable region. A slower command may suppress residual vibration while extending the complete cycle. Report both portions using a task tolerance and observation duration agreed before testing.

<a id="english-section-2"></a>

## Assign roles to references and response points

Stable ground references check camera movement. Chassis targets describe base motion. Intermediate and end targets distinguish responses along the boom. Removing rigid base movement requires adequate reference geometry to estimate orientation. Subtracting one base point removes translation only. For actual work-area positioning, retain the ground-frame trajectory as well as any chassis-relative result.

| Record | Role | Common ambiguity |
| --- | --- | --- |
| Slew or valve event | Input and braking onset | Command withdrawal does not mean the tip has stopped |
| Ground and chassis references | Camera stability and base motion | A chassis point can move relative to ground |
| Intermediate and tip coordinates | Distributed response and signed overshoot | One unsigned maximum discards direction |
| Load, extension and pose | Comparability of runs | Structural conditions can confound a control change |

Keep controller estimates separate from optical measurements. A state estimate used in feedback can agree with its command while the physical outlet departs from it. Align time bases using an identifiable event with known physical meaning. Sliding peaks into agreement would remove precisely the response lag under investigation.

<a id="english-section-3"></a>

## Compare the same operating tasks

Repeat a motion with comparable length, elevation, load and angular range. Record the initial state because residual swing from a previous run can add to the current transient. Reuse stations, identifiers and axes. Alternating baseline and modified runs can reduce confounding from environmental or machine changes over time.

Show individual runs. An occluded tip at target crossing leaves its maximum unresolved even if other channels remain valid. Define usability conditions in advance and report reasons for missing results. Use stationary histories to check whether the claimed improvement exceeds apparent movement in the relevant direction.

<a id="english-section-4"></a>

## Read performance from component histories

Find the first signed overshoot, later excursions on the opposite side and the time after which the tip stays within the agreed band. A recording that ends during ongoing sway has no confirmed settling time within the observed interval. Keep speed settings, sign conventions and windows with every result.

A smaller first overshoot can coexist with longer low-amplitude ringing. One-sided clearance and stable positioning in a small region give these outcomes different weights. A better tip curve can also accompany greater movement farther down the arm. Multipoint observations expose that trade-off. Stress implications require a structural model or independent strain measurement.

<a id="english-section-5"></a>

## Give the dynamic model a measurable prediction

Place virtual outputs at the actual optical target locations. Match coordinates, units and time zero. Small position differences matter on a rotating arm, so a node labelled “tip” is insufficient without its physical offset. Compare component peaks, time to peak and the residual waveform to examine magnitude, phase and decay separately.

Measured base motion imposed on the model is an input. Reproducing it does not validate a predicted tip response. Reserve intermediate or tip histories for independent comparison. Common lag across points warrants checks on timing, input and actuator response. Growing disagreement toward the tip warrants examination of stiffness, joint behaviour and damping without assigning a unique cause from the pattern alone. Hold back other operating conditions when fitting parameters to one run.


<a id="english-section-6"></a>

## Using the result to design the next comparison

Suppose the modified run has lower peak overshoot but a longer main movement. Record the smaller overshoot under those conditions and show the cycle cost. To test deceleration-profile shape, repeat with comparable total movement duration. Calling the change increased structural damping would go beyond the evidence, especially when material and joints were untouched.

If ground-frame tip sway falls while relative movement between sections barely changes, investigate chassis or gross rotation. Plot ground-frame and chassis-frame histories side by side. Improvement only in ground coordinates offers limited evidence of reduced section bending.

For a settling result, give the target, end of observation, distribution over repeats and runs that failed to confirm settling before recording ended. For model validation, distinguish measured inputs from held-out responses. An unresolved cause can then point to a specific next measurement: a base reference, a missing control event or a revised test layout.

<a id="english-section-7"></a>

## Justifying external optical measurement on a development rig

Controls engineers can apply a task-frame settling criterion, structural engineers can inspect relative movement and simulation teams can extract equivalent virtual targets from the same acquisition. Deliver a target drawing, axes, original histories, gap flags, event table, run conditions and an identifiable image at a selected extreme.

An equipment demonstration can reproduce this workflow. Specify one braking event, ask for multipoint coordinates and have the controls and simulation teams independently recompute their agreed metrics. If both can use the same record, the configuration has demonstrated value for routine design iterations. Formal machine acceptance remains tied to the project conditions, repeat tests and agreed limits.

**Equipment and case documentation**

- [XTDIC-STROBE dynamic measurement system and applications](https://www.xtop3d.com/products/xtdic-strobe.html)
- [Crane boom test images and displacement curves](https://www.xtop3d.com/en/casesdetail/3d-dic-crane-boom-deflection-measurement.html)

**Related articles**

- [228 · Measuring Crane Boom Sway After Slew Stops with XTDIC Stereo Tracking](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-crane-boom-slew-sway-case.md#english-version)
- [231 · Quantifying Concrete Pump Boom Recoil and Delivery Motion from 3D Tip Trajectories](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-pump-boom-outlet-recoil-trajectory.md#english-version)

</details>
