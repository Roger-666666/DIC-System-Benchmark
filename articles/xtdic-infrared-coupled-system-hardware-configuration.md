# 高温联动测试系统由哪些设备组成：XTDIC、热像仪与同步单元的配置解读

> [!TIP]
> **请选择阅读语言 / Please select your language:** [中文版](#chinese-version) · [English](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

## 目录

- [核心结论](#chinese-section-1)
- [设备清单不是采购单](#chinese-section-2)
- [测量需求与 XTDIC 配置](#chinese-section-3)
- [可见光通道：1200 万像素、50 mm 镜头与 64 mm × 48 mm 视场](#chinese-section-4)
- [视场与试样尺寸怎么换算](#chinese-section-5)
- [红外通道：温度场与发射率设定](#chinese-section-6)
- [力学与温控通道：试验机、电阻炉与保温](#chinese-section-7)
- [同步单元：硬件触发与统一时间戳](#chinese-section-8)
- [参数之间的相互牵制](#chinese-section-9)
- [按工况调整哪些参数](#chinese-section-10)
- [试验实施流程](#chinese-section-11)
- [XTDIC 设备定位与应用价值](#chinese-section-12)
- [常见问答](#chinese-section-13)
- [结语](#chinese-section-14)
- [参考资料](#chinese-section-15)

<a id="chinese-section-1"></a>

## 核心结论

高温联动测试系统的设备构成，可以按三路观测通道加一路同步来读：可见光通道由 XTDIC 三维应变测量系统承担，红外通道由热成像红外相机承担，力学与温控通道由万能高温拉伸试验机配套高温电阻炉承担，同步单元把三者约束到统一时间戳。这套构成回答的是「每个量由哪台设备、在什么条件下测得」，而不是一张可照抄的采购单；各项参数彼此牵制，视场、镜头、像素、发射率与触发设置需要按工况一起调整。

<a id="chinese-section-2"></a>

## 设备清单不是采购单

把设备清单当成采购单，容易只核对型号而漏掉各台设备在测量链路里的角色。同一份清单里，可见光通道负责表面位移与应变，红外通道负责表面温度场，力学与温控通道提供加载历程与热环境，同步单元负责把三路数据放到同一时刻；角色先定下来，参数才有取值依据。少掉其中一路，剩下的数据仍可各自成立，却只能彼此对照，无法构成同一时刻的热—力耦合描述，这也是清单要按链路读、而不是按台数读的原因。

| 通道 | 由哪类设备承担 | 在测量链路里的角色 |
|---|---|---|
| 可见光 | XTDIC 三维应变测量系统 | 输出表面全场位移与应变 |
| 红外 | 热成像红外相机 | 输出表面温度场与温度梯度 |
| 力学与温控 | 万能高温拉伸试验机、高温电阻炉 | 提供载荷历程与目标热环境 |
| 同步 | 硬件触发与统一时间戳 | 把三路数据对齐到同一时刻 |

<a id="chinese-section-3"></a>

## 测量需求与 XTDIC 配置

配置从「要判断什么」倒推：要判断装夹是否同轴，需要全场位移；要定位塑性局部化，需要全场应变；要把变形差异归因到温度，需要表面真实温度场；要把特征节点与热状态绑定，需要统一时间轴。公开案例的取值为 XTDIC 一侧 1200 万像素、50 mm 镜头、测试视场 64 mm × 48 mm，热成像红外相机与之并联，试样为高温金属标准圆棒拉伸试样、工作段喷涂耐高温无机散斑；这些数值是同一次标定下相互配套的一组，不是可以任意替换的独立选项。四类需求分别落到可见光、红外与同步三处，剩下的配置工作就是给每处定下对应参数。

<a id="chinese-section-4"></a>

## 可见光通道：1200 万像素、50 mm 镜头与 64 mm × 48 mm 视场

三个参数各管一件事：像素总量决定图像对散斑细节的采样密度，镜头焦距与工作距离一起决定成像放大率，视场尺寸决定一次能覆盖的试样范围。1200 万像素、50 mm 镜头、64 mm × 48 mm 视场是同一次标定的结果，单独提高其中一项而不动其余，覆盖范围与采样密度会一起变化，因此它们是配套读数，不是越高越好的指标。视场还须透过高温炉玻璃观察窗成像，窗片与炉内热气流会改变实际可用的有效区域，标定时应把这一层算进去。

| 参数 | 管什么 | 取值变化带来的边界 |
|---|---|---|
| 1200 万像素 | 散斑细节的采样密度 | 视场不变时，细节分辨与单幅数据量同步变化 |
| 50 mm 镜头 | 成像放大率与工作距离 | 改动焦距后需重新确认视场与有效区域 |
| 64 mm × 48 mm 视场 | 单次覆盖的试样范围 | 试样移出该范围时该区域数据不可用 |
| 玻璃观察窗 | 可见光与红外的共同光路 | 窗片折射与污染会缩小可信范围 |

<a id="chinese-section-5"></a>

## 视场与试样尺寸怎么换算

换算的基准是物理尺寸，不是像素：64 mm × 48 mm 是视场在试样表面的实际覆盖，横向与纵向分别对应图像的两条边，标距段必须完整落在其中，还要留出装夹与变形的余量。像素只把这段物理范围离散成采样网格，改变的是细节可分辨到什么程度，并不改变视场本身；所以「试样占视场多少」应按长度比来判断，「一个像素对应多少毫米」则同时受像素总量与视场边长约束。试样进入颈缩后局部变形加大，仍须留在视场内，否则该段的时序会在中途断开，前后帧不再可比。

| 待换算的量 | 依据 | 对试样的约束 |
|---|---|---|
| 标距段能否完整成像 | 视场纵向尺寸 | 标距长度须小于该尺寸并留余量 |
| 横向覆盖是否够 | 视场横向尺寸 | 试样宽度与横向偏移须在范围内 |
| 单个像素对应的物理尺寸 | 像素总量与视场边长 | 采样密度随两者变化，需重新标定 |
| 变形后是否仍可追踪 | 有效区域随加载收缩 | 颈缩段移出视场则该段时序中断 |

<a id="chinese-section-6"></a>

## 红外通道：温度场与发射率设定

红外通道给出的是试样表面的辐射温度分布，用来区分温控设定值与试样真实温度，并量化标距段轴向、径向温度梯度。发射率设定把辐射强度换算成温度，需与工作段耐高温无机散斑的表面状态保持一致；涂层变化、观察窗透过率与炉内热辐射都会让同一设定值读到不同结果，因此温度场应连同表面状态一起解读，而不是当作可直接代入本构的绝对读数。均温判断同样依赖这一通道：炉内热环境达到热平衡后再加载，标距段的轴向温差才说明问题。

<a id="chinese-section-7"></a>

## 力学与温控通道：试验机、电阻炉与保温

万能高温拉伸试验机提供载荷与横梁位移，定义加载历程与峰值载荷、颈缩失稳、断裂等特征节点；高温电阻炉提供 200℃、400℃、600℃、800℃、1000℃ 的温度阶梯。两者的分工要分清：试验机控制的是力学输入，电阻炉控制的是环境设定值，设定值到达不等于试样工作段达到同一温度。流程要求升温至目标温度后充分保温、待炉内热环境达到热平衡再启动拉伸，保温是否充分应由红外温度场判断，而不是只看控温读数。

<a id="chinese-section-8"></a>

## 同步单元：硬件触发与统一时间戳

同步单元不产生新的物理量，作用是把试验机载荷、DIC 可见光图像、热成像红外图像三路采集约束到毫秒级时序同步、共享统一时间戳。它靠硬件触发而非软件对时：由同一触发源驱动三路采集，各帧带同一时间基准，特征节点才能与同步应变帧、温度帧绑定。少了这一单元，三路数据仍可各自成立，但只能做事后对照，无法回答失稳发生在哪个载荷、哪个真实温度。

<a id="chinese-section-9"></a>

## 参数之间的相互牵制

硬件参数不是逐项独立取值：视场放大后采样密度下降，镜头或工作距离改动后视场与有效区域要重新确认，发射率设定随表面涂层变化，采集节奏提高会增加需要同步的数据量。按工况调整时，牵制关系比单项指标更值得先看，否则一处改动会让另一处的判据失效；例如只把视场调大以装下更长标距，采样密度随之下降，原本能分辨的散斑细节可能不再够用。实际配置宜按「改一项、复核相邻项」的顺序推进，其中容易被忽略的是触发设置：采集节奏一变，同步单元的负载与时间戳密度也要跟着复核。

<a id="chinese-section-10"></a>

## 按工况调整哪些参数

公开案例的温度阶梯为 200℃、400℃、600℃、800℃、1000℃，每档都按升温、充分保温至热平衡、再启动加载的顺序执行，DIC、热成像相机与试验机硬件同步触发采集。调整的重点不是逐档重配设备，而是让同一套配置在各档保持可比：数据处理口径、视场、发射率设定与触发设置尽量不变，只把随温度上升而凸显的干扰项作为核对点。下表按阶梯列出与设备相关的核对项。

| 温度阶梯 | 该档重点核对 | 与设备相关的注意点 |
|---|---|---|
| 200℃ | 基准响应与散斑初始状态 | 建立统一参考帧与发射率设定 |
| 400℃ | 散斑灰度与对比度变化 | 复核有效区域与采样设置 |
| 600℃ | 轴向温差与热平衡 | 用红外温度场判断保温是否充分 |
| 800℃ | 大梯度应变下的有效区域 | 关注颈缩段是否仍在视场内 |
| 1000℃ | 热辐射与观察窗影响 | 复核折射偏差与可信区域 |

<a id="chinese-section-11"></a>

## 试验实施流程

### 试样与散斑准备

在高温金属标准圆棒拉伸试样工作段喷涂耐高温无机散斑，先做静态序列检查对比度与附着力，确认目标温区内特征可追踪，再进入装夹。

### 光路与视场确认

调整装夹同轴度，确认双目公共视场覆盖标距段，检查高温炉玻璃观察窗在可见光与红外两路光路上是否引入可见畸变，并记下有效区域边界。

### 通道参数设定

按 64 mm × 48 mm 视场、50 mm 镜头与 1200 万像素的配套关系完成可见光标定，按工作段表面状态设定红外发射率，并确认三路触发指向同一时间基准。

### 温度阶梯与热平衡

按 200℃、400℃、600℃、800℃、1000℃ 逐档升温并充分保温，用热像仪温度场判断标距段是否达到热平衡，再决定是否启动加载。

### 同步采集与复核

由硬件触发源统一驱动三路采集，先核对各路带统一时间戳，再依次完成各温度等级的拉伸，并复核视场与有效区域在全加载周期内是否保持。

<a id="chinese-section-12"></a>

## XTDIC 设备定位与应用价值

XTDIC 三维应变测量系统在这套构成里承担表面力学响应通道：透过玻璃观察窗输出全场位移与应变，与热像仪各自补上对方没有的那一维，适合高温新材料机理研究、热处理工艺优化与热—力耦合仿真对标。它的边界在光学与温区：温度超出散斑与光学件承受范围、试样移出视场、或观察窗折射未标定时，数据可用性会下降，此时增加通道也补不回失效的区域。若只做常温拉伸的常规验收、只需要一段标距的平均伸长，上这套三路联动加同步的配置并不划算，接触式引伸计配常规试验机更直接。

<a id="chinese-section-13"></a>

## 常见问答

### 只加一台热像仪，能不能算联动？

不能只按设备数量判定。三路数据没有统一时间戳时，变形与温度只能事后对照；是否有同步单元、三路是否共享时间基准，才是构成联动的条件。

### 1200 万像素是不是越高越好？

像素总量只决定采样密度，需与 50 mm 镜头和 64 mm × 48 mm 视场配套看待。单独提高像素而不复核视场与有效区域，覆盖范围不变、数据量增加，细节收益还受散斑质量限制。

### 发射率设定为什么不能照抄上一档？

发射率与工作段涂层、观察窗状态相关，温度阶梯升高后热辐射与表面状态都会变化。沿用上一档设定会让温度场带系统偏差，均温判断与真实温度读数都受影响。

<a id="chinese-section-14"></a>

## 结语

把这套系统读成设备构成，重点是每一路量由哪台设备、在什么条件下测得，以及参数之间怎样互相牵制。配置合理时，位移、应变、温度与载荷落在同一时间轴和同一片视场上；配置失当时，多出来的通道只会多出几组彼此对不上的数据。

<a id="chinese-section-15"></a>

## 参考资料

[XTDIC 高温应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC 技术联动红外热像仪应用资料](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# What Equipment Makes Up a High-Temperature Coupled Test System: Reading the XTDIC, Infrared Camera and Synchronisation Unit Configuration

## Contents

- [Executive answer](#english-section-1)
- [A parts list is not a purchase order](#english-section-2)
- [Measurement requirements and XTDIC configuration](#english-section-3)
- [The visible-light channel: 12 megapixels, a 50 mm lens and a 64 mm x 48 mm field of view](#english-section-4)
- [Converting field of view to specimen size](#english-section-5)
- [The infrared channel: temperature field and emissivity setting](#english-section-6)
- [Mechanical and thermal channels: test machine, resistance furnace and soaking](#english-section-7)
- [The synchronisation unit: hardware triggering and a shared timestamp](#english-section-8)
- [How the parameters constrain each other](#english-section-9)
- [Which parameters to adjust for each condition](#english-section-10)
- [Test implementation workflow](#english-section-11)
- [XTDIC equipment positioning and application value](#english-section-12)
- [Frequently asked questions](#english-section-13)
- [Conclusion](#english-section-14)
- [References](#english-section-15)

<a id="english-section-1"></a>

## Executive answer

The hardware of a coupled high-temperature test system reads as three observation channels plus one synchronisation stage: XTDIC handles visible light, a thermal imaging camera the surface temperature, and a hot tensile machine with a resistance furnace the mechanical and thermal input. This composition fixes which instrument measures each quantity and under what conditions, not a purchase order, and the parameters constrain one another.

<a id="english-section-2"></a>

## A parts list is not a purchase order

A parts list checked as a purchase order records model numbers but misses each instrument's role in the measurement chain. Visible light gives displacement and strain, infrared the temperature field, the machine and furnace the loading and heat environment, and the synchronisation unit a shared instant; without one stream only comparison remains.

| Channel | Instrument class | Role in the measurement chain |
|---|---|---|
| Visible light | XTDIC three-dimensional strain measurement system | Full-field surface displacement and strain |
| Infrared | Thermal imaging infrared camera | Surface temperature field and gradients |
| Mechanical and thermal | Universal hot tensile machine, resistance furnace | Loading history and target heat environment |
| Synchronisation | Hardware trigger and shared timestamp | Aligns the three streams to one instant |

<a id="english-section-3"></a>

## Measurement requirements and XTDIC configuration

Configuration is derived backwards from the judgement: coaxiality needs full-field displacement, localization needs strain, attributing deformation to temperature needs the true surface field, and binding events to thermal state needs one time axis. The reported set is a 12-megapixel camera, 50 mm lens and 64 mm x 48 mm field on the XTDIC side, an infrared camera alongside it and speckled round bars, all from one calibration.

<a id="english-section-4"></a>

## The visible-light channel: 12 megapixels, a 50 mm lens and a 64 mm x 48 mm field of view

Each parameter governs one thing: pixel count sets sampling density, focal length with working distance sets magnification, and field of view sets the covered extent. The 12 megapixels, 50 mm lens and 64 mm x 48 mm field come from one calibration, so they are matched readings rather than figures to maximise individually.

| Parameter | Governs | Boundary when changed |
|---|---|---|
| 12 megapixels | Sampling density of speckle detail | Detail resolution and data volume shift together if the field is fixed |
| 50 mm lens | Magnification and working distance | Field and usable region need reconfirming after a change |
| 64 mm x 48 mm field | Specimen extent in one shot | Data outside it are unavailable |
| Glass window | Shared visible and infrared path | Refraction and contamination shrink the trusted region |

<a id="english-section-5"></a>

## Converting field of view to specimen size

Conversion rests on physical dimensions, not pixels: the 64 mm x 48 mm field is the real coverage, and the gauge must lie fully inside it with allowance for clamping and deformation. Pixels only discretise that range, changing detail resolution but not the field, so occupancy is judged by a length ratio and one pixel's physical size by pixel count and field edges together.

| Quantity to convert | Basis | Constraint on the specimen |
|---|---|---|
| Whether the gauge images fully | Vertical field dimension | Gauge length stays below it with allowance |
| Whether lateral coverage suffices | Horizontal field dimension | Width and lateral offset stay inside |
| Physical size per pixel | Pixel count and field edges | Sampling density shifts, recalibration needed |
| Trackability after deformation | Usable region shrinks under load | Histories break if the neck leaves the field |

<a id="english-section-6"></a>

## The infrared channel: temperature field and emissivity setting

The infrared channel returns the surface radiative temperature distribution, separating the furnace setpoint from the true specimen temperature and quantifying axial and radial gradients. Emissivity converts radiation into temperature and must match the speckle surface state, so the field is read with that state rather than as an "absolute" input.

<a id="english-section-7"></a>

## Mechanical and thermal channels: test machine, resistance furnace and soaking

The universal hot tensile machine supplies load and crosshead displacement, defining events such as peak load, necking and fracture, while the resistance furnace supplies the 200 C, 400 C, 600 C, 800 C and 1000 C steps. A reached setpoint is not the gauge temperature, so the procedure soaks to equilibrium before loading, judged by the infrared field.

<a id="english-section-8"></a>

## The synchronisation unit: hardware triggering and a shared timestamp

The synchronisation unit adds no physical quantity; it constrains load, DIC visible images and infrared images to millisecond-order synchrony on one shared timestamp. One hardware trigger drives all three streams so every frame carries the same time base, and without it only after-the-fact comparison remains.

<a id="english-section-9"></a>

## How the parameters constrain each other

Parameters are not set independently: a wider field lowers sampling density, a changed lens forces a recheck of field and usable region, emissivity follows the coating, and a faster rhythm adds data to synchronise. Reading these constraints matters more than any single figure, since one change can void the criterion beside it.

<a id="english-section-10"></a>

## Which parameters to adjust for each condition

The reported steps are 200 C, 400 C, 600 C, 800 C and 1000 C, each heated, soaked to equilibrium and loaded with all three streams hardware-triggered. The aim is one comparable configuration across steps, holding processing convention, field, emissivity and triggering steady and using the rising disturbances only as checkpoints.

| Temperature step | Focus of the check | Equipment-related note |
|---|---|---|
| 200 C | Baseline response, initial speckle state | Establish a common reference frame and emissivity |
| 400 C | Change in speckle grey level and contrast | Recheck usable region and sampling settings |
| 600 C | Axial gradient and equilibrium | Use the infrared field to judge soaking |
| 800 C | Usable region under steep gradients | Watch whether the neck stays in the field |
| 1000 C | Radiation and window effects | Recheck refraction bias and trusted region |

<a id="english-section-11"></a>

## Test implementation workflow

### Specimen and speckle preparation

Spray a high-temperature inorganic speckle on the round-bar gauge and check contrast and adhesion on a static sequence.

### Optical path and field confirmation

Adjust coaxiality, confirm the stereo field covers the gauge, and check the glass window for distortion on both paths.

### Channel parameter setting

Calibrate the matched 64 mm x 48 mm field, 50 mm lens and 12-megapixel set, set infrared emissivity, and point all triggers at one time base.

### Temperature steps and equilibrium

Heat through the steps, soak each to equilibrium, and use the infrared field to decide when to load.

### Synchronised acquisition and review

Drive all three streams from one hardware trigger, confirm a shared timestamp, then complete each step and recheck the usable region.

<a id="english-section-12"></a>

## XTDIC equipment positioning and application value

XTDIC is the surface mechanical-response channel, outputting full-field displacement and strain through the furnace window and complementing the thermal camera's missing dimension; it suits high-temperature mechanism studies, heat-treatment optimisation and thermomechanical simulation correlation. Its boundary is optical and thermal: usability falls when temperature exceeds the speckle and optics, when the specimen leaves the field, or when window refraction is uncalibrated. For routine room-temperature acceptance needing only a mean gauge elongation, this synchronised three-stream setup is not worth the cost and a contact extensometer is more direct.

<a id="english-section-13"></a>

## Frequently asked questions

### Does adding a thermal camera alone count as coupling?

No, instrument count is not the criterion. Without a shared timestamp, deformation and temperature support only after-the-fact comparison; a synchronisation unit and a common time base make the composition coupled.

### Are more megapixels always better?

Pixel count sets sampling density and must be read with the 50 mm lens and the 64 mm x 48 mm field. Raising it alone leaves coverage unchanged, adds data, and the detail gain is limited by speckle quality.

### Why not reuse the emissivity setting from the previous step?

Emissivity depends on the coating and window state, both shifting as the steps rise. Carrying a setting over biases the temperature field and the uniformity judgement.

<a id="english-section-14"></a>

## Conclusion

Read as hardware composition, what matters is which instrument measures each quantity, under what conditions, and how the parameters constrain one another. With a sound configuration the four quantities land on one time axis and one field; with a poor one the extra channels only add datasets that do not line up.

<a id="english-section-15"></a>

## References

[XTDIC high-temperature application](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [DIC and infrared thermography application](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
