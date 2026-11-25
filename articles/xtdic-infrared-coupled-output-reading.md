# 三张云图加一条曲线怎么读：XTDIC 联动测试的输出解读

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [读图之前先定口径](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [位移云图：先判装夹同轴度](#chinese-section-4)
- [主应变云图：集中带位置与梯度](#chinese-section-5)
- [热成像温度场云图：设定值与真实值](#chinese-section-6)
- [载荷—位移曲线：特征节点](#chinese-section-7)
- [四类图的交叉核对](#chinese-section-8)
- [四种常见误读](#chinese-section-9)
- [报告里该放什么](#chinese-section-10)
- [试验实施流程](#chinese-section-11)
- [XTDIC 设备定位与应用价值](#chinese-section-12)
- [常见问答](#chinese-section-13)
- [结语](#chinese-section-14)
- [参考资料](#chinese-section-15)

<a id="chinese-section-1"></a>

## 核心结论

同一套联动测试会同时交出位移云图、主应变云图、热成像温度场云图，以及载荷—位移曲线加若干局部时序，读法却不是逐张看颜色。四类图共用一条时间轴、一片视场和一套口径，先固定色标、参考帧、坐标与区域边界，再按顺序判读并互相核对，结论才站得住。本文只谈「拿到数据怎么读」：每类图先看什么、四类图怎么交叉核对、哪些读法最容易出错，以及报告里应该留下哪些可复核的要素。

<a id="chinese-section-2"></a>

## 读图之前先定口径

读图前的口径不先定下来，同一张云图在不同人手里会读出不同结论。至少要固定四类：色标是否跨帧统一、应变与温度以哪一帧为参考、轴向坐标与感兴趣区域的边界、以及载荷与位移的单位和时间零点。口径变动不会让数据变好或变坏，却会改变图上读出的数值；跨温度阶梯比较时，各档沿用同一套口径，差异才可能归因于材料与热状态，而不是出图设置。定口径这一步不产生新数据，却决定后面每张图能不能被复核。

| 口径项 | 要固定什么 | 不固定的后果 |
|---|---|---|
| 色标范围 | 各帧、各档统一温标与色标 | 相似颜色被读成相同温度 |
| 参考帧 | 保温末期或室温装夹状态 | 应变起算点不一致 |
| 坐标与区域 | 轴向坐标、感兴趣区域边界 | 局部曲线前后不可比 |
| 单位与时间零点 | 载荷、位移单位与触发时刻 | 特征节点与帧对不上 |

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

这一节的配置从「要读什么」倒推，而不是列设备清单。要判装夹同轴度，读位移云图；要找集中带位置与梯度，读主应变云图；要把设定值换成试样表面真实温度，读热成像温度场云图；要把弹性段、强化段、峰值载荷、颈缩失稳、断裂等特征节点与云图对应，读载荷—位移曲线与统一时间戳。公开配置中 XTDIC 一侧为 1200 万像素、50 mm 镜头、测试视场 64 mm × 48 mm，试验机载荷、DIC 可见光图像、热成像红外图像毫秒级时序同步、共享统一时间戳；这套条件决定四类图落在同一时刻、同一片区域上。

| 读图任务 | 对应输出 | 需先固定的口径 |
|---|---|---|
| 判装夹同轴度 | 位移云图 | 轴向坐标与参考帧 |
| 定位集中带 | 主应变云图 | 色标与区域边界 |
| 读真实温度 | 热成像温度场云图 | 温标、发射率与表面状态 |
| 对齐特征节点 | 载荷—位移曲线 | 时间零点与触发时刻 |

<a id="chinese-section-4"></a>

## 位移云图：先判装夹同轴度

拿到位移云图，第一件事不是读变形量，而是拿它当加载条件的检查表：沿标距段看轴向位移梯度是否连续、对称，标距段变形是否均匀，有没有单侧偏载。高温金属标准圆棒拉伸中，这些特征同时成立才说明装夹同轴度良好、这一档的加载有效；若单侧梯度偏大，先怀疑装夹偏心或单侧受热，而不是把它记成材料局部化。位移场还用来划出有效区域，把可信范围圈出来之后再做梯度计算；出现局部突变或断层时，先回查散斑与匹配，剔除该区域后再决定是否继续读下一张图。

<a id="chinese-section-5"></a>

## 主应变云图：集中带位置与梯度

主应变云图用来回答变形集中在哪里、什么时候开始：定位应变集中区域及应变梯度，捕捉塑性局部化萌生位置，这个位置在时间上早于肉眼可见颈缩。读的时候分两步，先沿轴向找集中带的位置，再看带内梯度随时间怎么发展；在同一感兴趣区域提取局部应变时序，可用于有限元仿真对标校验，但区域边界一旦中途改动，前后曲线就不可比。高温下还要把图读稳：热辐射与热气流造成的散斑灰度波动、颈缩阶段的大梯度应变，都靠高温散斑亚像素鲁棒追踪算法保持连续记录；云图出现局部空洞时，先当作追踪中断而不是材料软化。

<a id="chinese-section-6"></a>

## 热成像温度场云图：设定值与真实值

热成像温度场云图补上的是试样表面真实温度，而不是炉温控制器的设定值：它能量化标距段轴向、径向温度梯度，校核实际均温水平，评估热场均匀性，并区分温控设定值与试样真实温度。读图时先确认色标与温标跨帧一致，再看标距段是否等温；轴向温差明显时，这一档就不是单一温度下的结果，用设定值代入高温本构测试会让参数带系统性偏差。红外测温还受发射率、表面涂层与观察窗影响，需与试样表面状态一起解读，不能把云图读数直接当作可代入的绝对温度。

<a id="chinese-section-7"></a>

## 载荷—位移曲线：特征节点

载荷—位移曲线不是第四张云图，而是给前三类图定位的时间坐标。依托统一时间戳，弹性段、强化段、峰值载荷、颈缩失稳、断裂等特征节点可分别与同步应变帧、温度帧绑定，用来确定塑性失稳启动时刻、失稳位置及对应真实温度，形成载荷—变形—温度耦合时序数据集。读曲线时先把这些节点标出来，再回看每个节点对应的那一帧云图；只报一条曲线而不写节点与帧的对应关系，场数据就少了时间坐标。曲线末端仍在出数，也不等于该段变形被可靠记录，临近断裂的几帧应分别确定各路记录的终点。

<a id="chinese-section-8"></a>

## 四类图的交叉核对

四类图各自成立还不够，要互相核对才能排除误判。核对的是同一结论在两张图上是否自洽：位移场若显示单侧偏载，应变集中带就不能直接归因于材料局部化；应变带所在位置，温度场应能说明它发生在什么热状态下；曲线上的峰值载荷、颈缩失稳节点，要能在同步应变帧与温度帧上找到对应。任何一对对不上，先回查口径与时间零点，而不是急着解释材料行为；把四类图放在同一时刻、同一片区域上对照，正是这套联动输出区别于四张独立图片的地方。

| 核对动作 | 自洽时应看到 | 矛盾时先查什么 |
|---|---|---|
| 位移场 ↔ 应变场 | 对称梯度下才有材料集中带 | 装夹同轴度与有效区域 |
| 应变场 ↔ 温度场 | 集中带位置有对应热状态 | 温标、发射率与热平衡 |
| 曲线节点 ↔ 同步帧 | 节点时刻三路数据对齐 | 时间零点与触发时刻 |
| 云图 ↔ 原始照片 | 轮廓收窄与集中带同位 | 色标口径与区域边界 |

<a id="chinese-section-9"></a>

## 四种常见误读

读图出错往往不是算法问题，而是口径和顺序问题，下面四种最常见。把逐帧自动色标下相似的颜色读成相同温度，是忽略了色标口径；把位移场的单侧梯度直接记成局部化，是跳过了装夹检查；用炉温设定值代替试样真实温度代入分析，是把设定值当成了测量值；把曲线末帧或断口位置当成损伤起点，是混淆了结果终点与过程起点。四种误读的共同点，是拿一张图或一个数替代了四类图的交叉核对；按上一节的动作对逐项回查，多数能在报告定稿前发现。

| 常见误读 | 为什么会出现 | 更稳妥的读法 |
|---|---|---|
| 相似颜色即相同温度 | 各帧色标自动调整 | 固定温标后回读该区域数值 |
| 单侧梯度即局部化 | 未先读位移场 | 先判装夹同轴度再谈集中带 |
| 设定值即真实温度 | 控温读数易得 | 用温度场校核并给出梯度 |
| 末帧或断口即起点 | 只看了结果图 | 回到时序节点定位起始时刻 |

<a id="chinese-section-10"></a>

## 报告里该放什么

一份能让别人复核读图结论的报告，重点不在多放几张云图，而在把口径与判据写全。至少要给出色标与温标、参考帧与时间零点、轴向坐标与感兴趣区域边界、发射率与表面状态，以及被剔除的区域和原因；还要写明特征节点与各帧的绑定关系、处理版本，以及这份数据能回答与不能回答的问题范围。缺了这些，读者只能接受作者的判读而无法重算；口径一旦写清，同一批原始图像换一套色标或评价窗口，也能从原始坐标重新算一遍，把「产品差异」和「口径差异」分开。

| 报告要素 | 具体内容 | 便于复核什么 |
|---|---|---|
| 口径清单 | 色标、温标、参考帧、单位 | 各档、各帧是否同一基准 |
| 区域与剔除 | 感兴趣区域边界、失效区 | 局部曲线前后是否可比 |
| 节点与帧绑定 | 时间零点、特征节点、同步帧 | 曲线与云图是否同一时刻 |
| 处理版本与范围 | 处理设置、可回答问题 | 结论能支持到什么程度 |

<a id="chinese-section-11"></a>

## 试验实施流程

### 先固定读图口径

统一各档色标、温标、参考帧、轴向坐标与感兴趣区域边界，写入记录。

### 按顺序出四类图

先出位移云图核对加载，再出主应变云图与温度场云图，最后标出载荷—位移曲线节点。

### 逐对做交叉核对

按位移对装夹、应变对温度、曲线节点对同步帧、云图对原始照片逐项核对。

### 按误读清单复查

对照四种常见误读检查色标、设定值、单侧梯度与末帧起点的处理是否稳妥。

### 汇总可复核的报告要素

把口径、剔除区域、节点绑定、处理版本与可回答问题范围一并交付。

<a id="chinese-section-12"></a>

## XTDIC 设备定位与应用价值

XTDIC 三维应变测量系统在这套联动测试里承担表面力学响应通道：透过观察窗输出全场位移与应变云图，配合热成像红外相机给出表面温度场，再与试验机载荷曲线共享统一时间戳，让四类输出能放在同一时刻、同一片区域上交叉核对，适合高温新材料机理研究、热处理工艺优化与热—力耦合仿真对标。它的能力边界在读图前提：色标与温标不统一、参考帧不一致、试样移出视场、散斑退化或三路时间戳错位时，四类图仍会出得来，却已不具备可核对的口径，后处理也补不回。若只需一段标距的平均伸长做常温常规验收，或只做单一温度下的定性观察，为读图配置这套联动输出并不划算，接触式测量配常规试验机更直接。

<a id="chinese-section-13"></a>

## 常见问答

### 四类图必须按固定顺序读吗？

建议按位移、应变、温度、曲线的顺序，因为前一张是后一张的前提：位移场不先判装夹，应变集中带就无法归因；口径未定，温度场的颜色也读不出数值。

### 云图颜色差不多，能认为温度相同吗？

不能。若各帧色标自动调整，相似颜色可能对应不同温标；应固定温标后回读该区域的数值，并结合轴向、径向梯度判断。

### 报告里最容易被漏掉的是什么？

通常是口径与被剔除区域。参考帧、色标、感兴趣区域边界和处理版本不写清，读者无法重算；剔除区不标注，局部曲线的可比性也无从判断。

<a id="chinese-section-14"></a>

## 结语

四类输出的价值不在图的数量，而在能不能放到同一时刻、同一片区域、同一套口径上互相核对。先定口径、按序判读、逐对交叉核对、把判据写进报告，读图结论才能被别人复核；口径一乱，颜色再清楚的云图也只是一名读者的印象。

<a id="chinese-section-15"></a>

## 参考资料

[XTDIC 高温应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC 技术联动红外热像仪应用资料](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# How to Read Three Maps and One Curve: Interpreting the Outputs of a Coupled XTDIC Test

## Contents

- [Executive answer](#english-section-1)
- [Fix the reading convention before looking at maps](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [Displacement map: check coaxiality first](#english-section-4)
- [Principal strain map: position and gradient of the band](#english-section-5)
- [Infrared temperature map: setpoint versus true value](#english-section-6)
- [Load-displacement curve: characteristic events](#english-section-7)
- [Cross-checking the four outputs](#english-section-8)
- [Four common misreadings](#english-section-9)
- [What belongs in the report](#english-section-10)
- [Test implementation workflow](#english-section-11)
- [XTDIC equipment positioning and application value](#english-section-12)
- [Frequently asked questions](#english-section-13)
- [Conclusion](#english-section-14)
- [References](#english-section-15)

<a id="english-section-1"></a>

## Executive answer

A coupled test delivers three maps and a load-displacement curve, but reading them is not reading colours one by one. They share one time axis, field and convention, so fix scales, reference frame and region boundaries first; this article covers how to read each output, cross-check them and state what a report must retain.

<a id="english-section-2"></a>

## Fix the reading convention before looking at maps

Fix the reading convention before interpreting any map, or the same map yields different conclusions. Set whether colour scales are shared, which frame defines zero strain, the axial coordinate and region, and the time zero; a changed convention alters read values without changing data, so one convention across steps makes differences attributable to material and thermal state.

| Convention | What to fix | Consequence if not fixed |
|---|---|---|
| Colour scale | Shared scale across frames and steps | Similar colours read as equal temperature |
| Reference frame | Soak-end or room-temperature state | Inconsistent strain origin |
| Coordinate and region | Axial axis, region boundary | Local curves incomparable |
| Units and time zero | Load, displacement units, trigger | Events mismatched to frames |

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

Configuration is derived backwards from what must be read: coaxiality needs the displacement map, the band its strain map, true temperature the infrared map, and events the load-displacement curve. The reported set pairs a 12-megapixel camera, a 50 mm lens and a 64 mm x 48 mm field with synchronised load, visible and infrared streams on millisecond order, putting all four outputs on one instant.

| Reading task | Corresponding output | Convention to fix first |
|---|---|---|
| Check coaxiality | Displacement map | Axial axis and reference frame |
| Locate the band | Principal strain map | Colour scale and region boundary |
| Read true temperature | Infrared temperature map | Scale, emissivity and surface state |
| Align characteristic events | Load-displacement curve | Time zero and trigger instant |

<a id="english-section-4"></a>

## Displacement map: check coaxiality first

Read the displacement map first as a check on loading, not a deformation magnitude: follow the axial gradient and ask whether it is continuous, symmetric and free of one-sided bias. On a hot round bar these confirm good coaxiality; a larger one-sided gradient points to eccentricity before localization, and a local gap calls for checking speckle before moving to strain.

<a id="english-section-5"></a>

## Principal strain map: position and gradient of the band

The principal strain map locates the concentration band, its gradient and plastic localization earlier than visible necking. Read the position first, then how the gradient develops, and keep the region fixed so local histories stay comparable for finite-element correlation; grey fluctuation from radiation and hot air and the steep necking gradient are held by robust tracking, so a map hole is a tracking break before material softening.

<a id="english-section-6"></a>

## Infrared temperature map: setpoint versus true value

The infrared map gives the true specimen temperature rather than the furnace setpoint, quantifying axial and radial gauge gradients. Read it with a fixed scale: a clear axial gradient means the step is not a single-temperature result, and substituting the setpoint biases constitutive parameters; emissivity, coating and window effects mean it is read with the surface state, not as an absolute input.

<a id="english-section-7"></a>

## Load-displacement curve: characteristic events

The load-displacement curve is the time coordinate for the three maps, not a fourth. With a shared timestamp, elastic, hardening, peak-load, necking and fracture events bind to synchronous strain and temperature frames, fixing the onset instant, location and true temperature of instability; mark these events first, revisit each matching frame, and set a separate end point per stream near fracture, since a last-frame value is not a reliable record.

<a id="english-section-8"></a>

## Cross-checking the four outputs

Each output must be checked against the others, since one conclusion should be self-consistent across two maps. A one-sided displacement bias prevents attributing a strain band to localization, the band position should have a matching thermal state, and events should find their synchronous frames; when a pair disagrees, check the convention and time zero before explaining material behaviour.

| Check | What consistency shows | What to inspect if contradictory |
|---|---|---|
| Displacement vs strain | Material band only under a symmetric gradient | Coaxiality and usable region |
| Strain vs temperature | Band position has a matching thermal state | Scale, emissivity, equilibrium |
| Curve events vs frames | Events align across three streams | Time zero and trigger instant |
| Maps vs raw photos | Outline narrowing and band share a location | Scale convention, region boundary |

<a id="english-section-9"></a>

## Four common misreadings

Reading errors usually come from convention and order rather than algorithms. Similar colours read as equal temperature ignore an auto-adjusted scale, a one-sided gradient read as localization skips the coaxiality check, the furnace setpoint used as the true value substitutes a target for a measurement, and the last frame taken as the damage onset confuses the end of a result with the start of a process.

| Misreading | Why it arises | Sounder reading |
|---|---|---|
| Similar colours mean equal temperature | Colour scale adjusts per frame | Fix the scale, reread the value |
| One-sided gradient is localization | Displacement map skipped | Check coaxiality first |
| Setpoint is true temperature | Control reading is convenient | Verify with the field and give gradients |
| Last frame or fracture is the onset | Only the result map was seen | Return to the time history |

<a id="english-section-10"></a>

## What belongs in the report

A report that permits a second reading depends less on extra maps than on full conventions. State colour and temperature scales, reference frame, time zero, region boundaries, emissivity, surface state, excluded regions, event bindings, processing version and the answerable scope; without these a reader can only accept the author's interpretation, whereas a written convention lets the same images be recomputed.

| Report element | Content | What it makes reviewable |
|---|---|---|
| Convention list | Scales, reference frame, units | Whether all frames share one basis |
| Region and exclusions | Region boundary, failed areas | Whether local histories compare |
| Event-to-frame binding | Time zero, events, synchronous frames | Whether curve and maps share an instant |
| Version and scope | Processing settings, answerable questions | How far the conclusion reaches |

<a id="english-section-11"></a>

## Test implementation workflow

### Fix the reading convention first

Unify scales, reference frame, axial coordinate and region boundaries across steps.

### Produce the four outputs in order

Read displacement first, then strain and temperature, and mark curve events.

### Cross-check each pair

Check displacement against clamping, strain against temperature and events against frames.

### Review against the misreading list

Recheck colour scale, setpoint, one-sided gradient and last-frame onset.

### Assemble reviewable report elements

Deliver conventions, exclusions, event bindings, version and answerable scope.

<a id="english-section-12"></a>

## XTDIC equipment positioning and application value

XTDIC is the surface mechanical-response channel, delivering displacement and strain maps through the window while the infrared camera gives the temperature field and the machine curve shares one timestamp, so all four outputs can be cross-checked at one instant; it suits high-temperature mechanism studies, heat-treatment optimisation and thermomechanical simulation correlation. Its boundary is the reading convention: with unmatched scales, an inconsistent reference frame or misaligned timestamps the maps still appear but are no longer comparable. For a mean gauge elongation in routine acceptance, or a single-temperature qualitative observation, this output set is not worth the cost and conventional tension is more direct.

<a id="english-section-13"></a>

## Frequently asked questions

### Must the four outputs be read in a fixed order?

Displacement, strain, temperature and curve is the recommended order, since each is a precondition for the next: a strain band cannot be attributed without checking clamping.

### Do similar map colours mean equal temperature?

No; with a scale adjusted per frame, similar colours may carry different ranges. Fix the scale and reread the region value.

### What is most often missing from a report?

Conventions and excluded regions. Without the reference frame, colour scale and region boundary a reader cannot recompute, and unmarked exclusions leave local curves incomparable.

<a id="english-section-14"></a>

## Conclusion

The value of four outputs lies in placing them on one instant, one region and one convention for cross-checking. Fix the convention, read in order, check each pair and write the criteria into the report; once the convention drifts, even a clear map is only one reader's impression.

<a id="english-section-15"></a>

## References

[XTDIC high-temperature application](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC and infrared thermography application](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
