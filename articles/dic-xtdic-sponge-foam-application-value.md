# 一台XTDIC能放在研发流程的哪个位置：海绵与泡沫材料的应用落点

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 海绵与泡沫的研发长期依赖手感与经验，数据常停在“压下去多少”这一层。本文把三维全场应变测量放进研发链条，讨论它在配方迭代、来料一致性、仿真对标与终端验证各环节能提供什么，给出应用落点表与数据交付表，并说明评估这类设备的四个维度。

> **关键词：** XTDIC；数字图像相关技术；柔性多孔材料；研发流程；配方迭代；本构参数标定；数据可比性

## 目录

- [一、设备在研发链条中的位置](#一设备在研发链条中的位置)
- [二、配方迭代：在同样的条件下比](#二配方迭代在同样的条件下比)
- [三、来料与批次一致性](#三来料与批次一致性)
- [四、仿真对标：单轴数据能做什么](#四仿真对标单轴数据能做什么)
- [五、三类终端场景](#五三类终端场景)
- [六、数据可比与数据资产](#六数据可比与数据资产)
- [七、设备能力评估的四个维度](#七设备能力评估的四个维度)
- [八、常见问题](#八常见问题)

## 一、设备在研发链条中的位置

海绵配方调整的日常多半是：换一种原料，把发泡剂的量往上提一点，打一块样，用手按一按，再上试验机压一条曲线。曲线出来了，硬度、回弹、压陷量都有数，可要说清“手感为什么变了”，还得靠那几个做久了的师傅。

三维全场测量的价值不在好看的云图，而在把“手感”变成可比的数据，让配方、工艺、结构设计有共同的判断依据。压到哪个阶段屈服、平台能撑多长、边缘与中心差多少，这些过去只能靠描述的东西，变成可以并排看的曲线与场图。它不替代试验机，也不替代经验，而是把总量拆成空间分布，把“按着差不多”换成“差在哪个阶段、差多少”。

## 二、配方迭代：在同样的条件下比

配方对比最怕条件飘。同一批试样，这周用这套压盘和这个加载速率，下周换一套，曲线高低可能来自工艺而不是配方。前提是条件固定：试样规格、制斑方式、加载步序、ROI范围都按同一套做，只让配方这一个变量动。

固定之后，比较的对象就具体了。平台段多长，反映泡孔在多大应变区间持续坍塌；屈服拐点在哪一步，反映初始刚度与结构稳定性；极限压缩量到哪，反映致密化的早晚。三者放在一张图上，差别一眼可见，而且可以复述：不是“这个软一点”，而是“这个到三成附近才拐，平台拖到接近七成”。

还有个常被低估的用处：把没做成的配方也留下数据。改坏的那一版，恰恰解释了哪个参数不能动；口径统一后，失败样本同样是资产。

## 三、来料与批次一致性

量产的麻烦常出在来料。同一牌号的泡沫，批次间密度与泡孔均匀性有波动，落到成品上就是坐感忽软忽硬、某一批提前塌陷。全检不现实，抽检容易漏，比较稳的做法是固定一套小样快测口径：同样的试样规格、制斑方式、加载步序与ROI，做批次间横向对比。

可比性靠四件事撑住：站位、参考、色标、记录。站位是相机位置、试样方向与压盘对中，换一次要重新对齐；参考是参考帧与初始状态的定义，跨批次不能各用各的；色标是云图上下限与配色，一变图就不同；记录是温度、湿度、放置时间这些容易忽略却影响软材料的因素。四项都在，批次差异才有解释力。

这类对比看趋势和相对位置，不是把两批数据叠起来算小数点后的差值。软材料的批次波动本来就在，测量把它变成看得见、可以分级的东西。

## 四、仿真对标：单轴数据能做什么

超弹性本构的参数不好定。单轴压缩只给一条应力—应变曲线，待定参数却有好几组，反算的组合往往不止一个。全场数据的用处在这里：它不只给平均值，还给同一加载步下整个表面的应变分布，标定时能同时对照量级与形态，模型在“哪里变形大”上跑偏也看得出来。

常见做法是：用单轴压缩的全场数据标定一组初始参数，再把模型放到剪切、双轴或压陷工况下验证，看预测形态与实测是否一致。单轴数据不足以定全部参数，涉及体积压缩与泡孔壁屈曲的部分得靠其他工况补。对标的目标不是让曲线重合，而是让模型在没测过的工况下也说得过去。

这一步做扎实，配方开发的试错会少一些：过去要反复打样才能判断的改动，可以先在模型里过一遍。

## 五、三类终端场景

柔性多孔材料的应用大体分三片，关心的东西不同。

| 场景 | 关心的问题 | 数据用途 | 配置要点 |
| --- | --- | --- | --- |
| 汽车座椅与内饰 | 软硬分布、久坐后的塌陷、反复压缩下的支撑 | 分区结构设计、面套匹配、耐久评估 | 双相机、大行程视场、与试验机同步 |
| 床垫与家居 | 人形坑的深度与恢复、边缘支撑 | 分层结构、材料搭配、技术说明 | 大视场、长时加载序列 |
| 包装与减振垫 | 压缩与冲击下的吸能、反复压缩后的保持 | 缓冲结构、厚度与密度选择、寿命预估 | 速率覆盖工况、ROI在受力区 |

汽车座椅是个典型例子：驾驶位长期受压，最先塌的往往不是正中间，而是坐骨附近那一小片。全场图能把它找出来，结构设计才好加厚或换料。床垫关心“人形坑”恢复得快不快，对应压缩永久变形；包装与减振垫关心平台段，平台越长越平稳，吸能与隔振的窗口越宽。

三类场景都不看单点峰值，而看分布与过程，这正是全场手段的用武之处。

## 六、数据可比与数据资产

一台设备用上两年，数据会攒很多，能不能用是另一回事。常见的是想找半年前那个配方的数据，翻出来发现没记加载速率，或色标范围跟这次不同，两张图没法看。

让数据留得住，靠几条朴素的规则。命名把日期、材料体系、试样编号、加载工况写进文件名，别用“最终版”“再改”这类词。元数据记录试样规格、制斑方式、加载步序、环境与镜头配置。质量标记注明哪一段因反光或出画不可用，后来的人不至于把噪声当现象。版本管理让同一批数据只有一份“当前有效”。

| 交付项 | 内容 | 谁会用 | 留存要点 |
| --- | --- | --- | --- |
| 云图序列 | 各加载步的应变场 | 设计、工艺、仿真 | 色标固定，图注写明加载步 |
| ROI平均曲线 | 平均应变随加载步的变化 | 配方开发、材料选型 | ROI位置与范围随图保存 |
| 原始图像与标定 | 未处理序列、标定结果 | 复算、争议复核 | 与结果同目录，标注版本 |
| 测试记录 | 试样信息、环境、加载制度 | 质量、项目管理 | 与数据同批归档 |

四类交付各有归宿，缺一项，半年后的人就要重新问一遍当时怎么做的。门槛不在设备，在习惯。

## 七、设备能力评估的四个维度

四个维度比参数表更实用。

第一，能不能覆盖全过程不断线。从初始接触压到接近七成，不退相关、不丢帧是底线；做不到，平台段就得靠拼接，连续性要打折。

第二，输出是否同时给场与曲线。云图看分布，ROI曲线看阶段，缺一样就要妥协。

第三，软试样上是否免干扰。非接触是前提，还要看照明会不会把试样烤热、支架会不会随压头动、线缆会不会牵住压盘。

第四，配置能不能随试样尺寸调整。薄片、方块、整块坐垫，视场从几十毫米到半米，同一套系统能否靠换镜头、调距离、改标定覆盖，决定使用频率。

四条都过关，设备才算进入日常流程，而不是只在验收那天开一次机。具体怎么配取决于试样尺寸、加载方式与数据形态：常规静态看XTDIC-CONST，显微尺度看XTDIC-MICRO，视频引伸计是XTDIC-VG，动态与高速对应XTDIC-STROBE与XTDIC-SPARK。

前面几篇想说的其实就四句：测得全、跟得住、读得懂、用得上。前两句靠设备，后两句靠流程与习惯。

## 八、常见问题

**1. 这类设备和试验机是什么关系？**

互补。试验机给载荷与位移，全局且可溯源；全场测量给同一时刻表面各处的变形分布，解释曲线为什么这样走。两者时间同步，数据才绑得住。

**2. 原始图像都要留吗，存储压力怎么处理？**

关键批次留原始图，复核与复算都靠它；常规批次可只留结果与缩略序列，但参数和标定文件要留。留什么、留多久，按数据给谁用来定。

**3. 配方只改了一点点，全场测量分得出差别吗？**

取决于差别是否落在可分辨范围，也取决于条件是否固定。条件固定时，平台长度与拐点的变化比单点硬度更敏感；条件漂了，差别再大也会被噪声盖住。

**4. 仿真参数能不能直接来自一次压缩试验？**

可以做起点，不足以定全部。单轴压缩对初始剪切约束强，对体积压缩与泡孔壁屈曲约束弱；可用的参数组要配合其他工况验证。

**5. 一条产线要不要配这种设备？**

看它要回答什么问题。产线关心批次一致与合格判定，压盘位移加抽检通常够用；要定位塌陷区域、比较结构方案、给仿真提供数据，才轮到全场测量。设备放在研发端，比放在产线端合适。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Where a 3D Full-Field System Sits in Development: Applications for Sponge and Foam

> **Abstract:** Sponge and foam development still leans on touch and experience, and the data usually stops at how much load a specimen took. This article places 3D full-field strain measurement inside the development chain, covering formulation iteration, incoming consistency, simulation calibration and end-product validation, with an application table, a data delivery table and four criteria for judging whether a system fits the work.

> **Keywords:** XTDIC; digital image correlation; flexible porous material; development workflow; formulation iteration; constitutive calibration; data comparability

## Contents

- [1. Where the equipment sits in the chain](#1-where-the-equipment-sits-in-the-chain)
- [2. Formulation iteration: compare under fixed conditions](#2-formulation-iteration-compare-under-fixed-conditions)
- [3. Incoming material and batch consistency](#3-incoming-material-and-batch-consistency)
- [4. Simulation calibration: what uniaxial data can do](#4-simulation-calibration-what-uniaxial-data-can-do)
- [5. Three end applications](#5-three-end-applications)
- [6. Comparability and data as an asset](#6-comparability-and-data-as-an-asset)
- [7. Four criteria for judging a system](#7-four-criteria-for-judging-a-system)
- [8. FAQ](#8-faq)

## 1. Where the equipment sits in the chain

Formulation work usually goes like this: change a raw material, raise the blowing agent a little, mould a block, press it by hand, then run a curve on the machine. The curve gives hardness, resilience and indentation figures, yet explaining why the feel changed still comes down to the people who have done it for years.

The value of full-field measurement is not a handsome contour. It turns feel into comparable data, so formulation, process and structural design share one basis: at which stage a specimen yields, how long the plateau holds, how far edge differs from centre. It replaces neither the machine nor experience; it splits the machine's single number into a distribution.

## 2. Formulation iteration: compare under fixed conditions

Formulation comparison suffers most from drifting conditions. If one week uses one platen and loading rate and the next week another, the difference between curves may come from the process rather than the recipe. A comparison needs fixed conditions: specimen size, speckle preparation, load sequence and ROI identical, with formulation the only variable.

Once fixed, the comparisons become specific. Plateau length shows over what strain range cells keep collapsing; the yield knee shows initial stiffness and structural stability; the compression limit shows how early densification begins. On one chart the difference becomes repeatable in words: not "this one is softer" but "this one only turns at about thirty percent and the plateau runs to nearly seventy".

There is an underrated use as well: keep data from the formulations that failed. The version that went wrong explains which parameter must not be touched.

## 3. Incoming material and batch consistency

Production trouble often starts at incoming material. Foam of the same grade varies in density and cell uniformity between batches, and the product feels soft one week and firm the next. Full inspection is unrealistic and sampling misses things, so the steadier approach is a fixed small-specimen quick test compared across batches.

Comparability rests on four things: station, reference, colour scale, record. Station covers camera position, specimen orientation and platen alignment, and must be realigned after any change. Reference cannot differ between batches. Colour scale is the range and palette of the contour. Record covers temperature, humidity and standing time, easily ignored yet affecting soft materials.

Such comparison reads trend and relative position, not a decimal difference between two stacked datasets. Batch variation exists in soft materials; measurement makes it visible and classifiable.

## 4. Simulation calibration: what uniaxial data can do

Hyperelastic parameters are hard to pin down. Uniaxial compression yields one stress-strain curve, but several unknowns leave more than one combination. Full-field data helps because it gives the strain distribution at each step as well as an average, so magnitude and shape can be checked together and a model that distorts in the wrong place shows up.

The usual route: calibrate initial parameters from uniaxial full-field data, then run the model under shear, biaxial or indentation conditions and compare shape with measurement. One caution: uniaxial data cannot fix every parameter, particularly those governing volumetric compression and cell-wall buckling. The aim is not coincident curves but a model that holds up where it was not measured.

Done properly, this shortens formulation trials: changes that once needed repeated moulding can be checked in the model first.

## 5. Three end applications

| Application | Question | Use of data | Configuration |
| --- | --- | --- | --- |
| Automotive seats and trim | Stiffness distribution, sag after long use, support under repeated compression | Zoned structure design, trim matching, durability assessment | Two cameras, large-travel field, synchronisation |
| Mattresses and furniture | Depth and recovery of body hollows, edge support | Layered structure, material matching, documentation | Wide field, long load sequences |
| Packaging and damping pads | Energy absorption, retention after repeated compression | Cushion design, thickness and density choice, life estimate | Rate covering service, ROI on the loaded zone |

Seats are the clearest case. A driver's seat is loaded for years, and the first area to collapse is rarely the centre but a small patch near the ischial contact; a full field locates it, so the structure can be thickened where it matters. Mattresses care how fast a body hollow recovers, which is compression set; packaging and damping pads care about the plateau: the longer and flatter, the wider the window for absorption and isolation.

What the three share: none looks at a single peak value; all look at distribution and process.

## 6. Comparability and data as an asset

After two years a system holds plenty of data, and usability is a separate question. Someone wants last season's formulation, finds no loading rate recorded or a colour range that no longer matches, and the two figures cannot be read together.

Keeping data usable takes plain rules. Naming carries date, material system, specimen number and load case; "final" and "revised again" do not. Metadata records specimen size, speckle method, load sequence, environment and lens. Quality flags mark segments spoiled by glare or by the specimen leaving the frame. Version control keeps one current dataset.

| Deliverable | Content | Used by | Retention |
| --- | --- | --- | --- |
| Contour sequence | Strain field at each load step | Design, process, simulation | Fixed colour scale, step annotated |
| ROI curve | Mean strain against load step | Formulation, material selection | ROI position and extent stored |
| Raw images and calibration | Unprocessed sequence, calibration result | Recalculation, dispute review | Same folder, versioned |
| Test record | Specimen, environment, loading schedule | Quality, project management | Archived with the batch |

Each has its place, and a missing one sends the next person back to ask how it was done.

## 7. Four criteria for judging a system

Four criteria say more than a specification sheet.

First, does it cover the whole process without a break? From first contact to nearly seventy percent, without decorrelation or dropped frames. If not, the plateau has to be stitched and continuity suffers.

Second, does it deliver field and curve together? The contour shows distribution, the ROI curve shows stages; missing either forces a compromise.

Third, is it free of disturbance on soft specimens? Non-contact is the premise, but check whether illumination heats the specimen, whether the mount moves with the platen, whether a cable pulls on it.

Fourth, can the configuration follow specimen size? Thin coupons, blocks, whole cushions, fields from tens of millimetres to half a metre: whether one system covers them by changing lens, distance and calibration decides its use.

When all four hold, the system enters daily work rather than being switched on for acceptance once. Which family fits depends on specimen size, loading mode and the data to be delivered: XTDIC-CONST for routine static work, XTDIC-MICRO at microscopic scale, XTDIC-VG as a video extensometer, XTDIC-STROBE and XTDIC-SPARK for dynamic and high-speed work.

Four sentences sum up the series: measure the whole field, follow the whole process, read it without guesswork, put it to use. The first two come from equipment; the last two from process and habit.

## 8. FAQ

**1. How does this equipment relate to the testing machine?**

They complement each other. The machine gives load and displacement, global and traceable; full-field measurement gives the distribution over the surface at the same instant. Time synchronisation binds the two.

**2. Should all raw images be kept, and what about storage?**

Keep raw images for key batches; review and recalculation depend on them. Routine batches can keep results and a reduced sequence, provided parameters and calibration files are retained.

**3. A formulation changes only slightly. Can full-field measurement resolve it?**

It depends on whether the change falls inside the resolvable range, and on whether conditions are fixed. With fixed conditions, plateau length and knee position respond more sharply than single-point hardness; with drift, even a large difference disappears into noise.

**4. Can simulation parameters come straight from one compression test?**

They can start there but will not be complete. Uniaxial compression constrains initial shear well and volumetric compression or cell-wall buckling poorly; a usable set needs other load cases.

**5. Does a production line need this equipment?**

It depends on the question. A line cares about batch consistency and pass or fail, where platen displacement with sampling usually suffices. Locating collapse zones, comparing structural options and feeding simulation call for full-field measurement, which sits in development rather than on the line.

</details>
