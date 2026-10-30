# 高温密闭腔里测晶圆翘曲，为什么总是不准：四类症状与对症处理

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 晶圆热翘曲测量的大部分麻烦，不是设备坏了，而是四类系统偏差在悄悄叠加：腔内热气流让图像“呼吸”、观察窗折射让边缘“缩水”、支架热漂移让整条曲线“平移”、温度与图像错时让 CTE 老是偏大。本文按“症状—成因—判断—处理”的顺序拆这四类问题，给出一条能照着走的排查链，并说明哪些偏差可以补、哪些只能改方案。

> **关键词：** 高温测量；晶圆翘曲；热气流；窗口折射；刚体漂移；温度同步；散斑失效

## 目录

- [一、先认症状，再找原因](#一先认症状再找原因)
- [二、症状一：图像在“呼吸”](#二症状一图像在呼吸)
- [三、症状二：边缘“缩水”](#三症状二边缘缩水)
- [四、症状三：曲线整体“平移”](#四症状三曲线整体平移)
- [五、症状四：CTE 总是偏大](#五症状四cte-总是偏大)
- [六、还有一类：散斑“翻脸”](#六还有一类散斑翻脸)
- [七、排查顺序：从便宜的动作开始](#七排查顺序从便宜的动作开始)
- [八、哪些能补，哪些只能改](#八哪些能补哪些只能改)
- [九、常见问题](#九常见问题)

## 一、先认症状，再找原因

热翘曲测试出问题，最忌讳一上来就怀疑相机精度。精度往往是最后才需要怀疑的，前头还有一堆更常见的原因。

现场的四类症状很好认，各有各的“长相”：

| 症状 | 表面现象 | 实际成因 |
| --- | --- | --- |
| 图像呼吸 | 同一工况多帧之间数据抖动 | 腔内热气流、折射率波动 |
| 边缘缩水 | 中心正常、外围形貌偏小 | 观察窗斜视折射 |
| 曲线平移 | 整条曲线整体抬高或压低 | 支架热漂移、样品滑移 |
| CTE 偏大 | 反演系数系统性偏高 | 温度与图像错时 |

四类症状的共同点是：它们都不产生明显噪声，只产生偏差。云图看起来干干净净，数值就是不对。这也是为什么它们能长期潜伏在数据里。

## 二、症状一：图像在“呼吸”

表现很典型：同一个温度节点连拍十帧，算出来的离面位移在场均值上能差出几微米到十几微米，而且没有规律。

原因在空气。腔内温度升高，空气密度不均，形成对流；对流层在样品与窗口之间缓慢移动，折射率随之波动，成像光路被“晃”了一下。这种现象在高温段尤为明显，因为温差大、对流强。

判断方法很简单：把相机对着一个静止的参考物（标定板、固定标志点）连拍一组，看它算出来的位移是否也在抖。如果参考物在抖，抖动就来自空气，不是样品。

处理手段有三层。最省事的是等温——延长保温时间，让腔内温度趋于均匀再采集；其次是挡风——在样品与窗口之间加导流板，把直吹样品的气流引开；最后是平均——同一工况采集多帧取平均，随机抖动能被压掉一部分。

要注意，平均只对随机成分有效。如果气流形成了稳定的密度梯度，那是系统偏差，平均压不掉。

## 三、症状二：边缘“缩水”

表现是：中心区域的形貌与预期一致，越往边缘形貌越被“压平”，翘曲量偏小，整体呈一种被向内收的错觉。

原因是折射。双目相机从视场边缘看进去时，视线是斜的，穿过玻璃的光程比正入射时长，像点位置内移。玻璃越厚、视场越大、相机越斜，偏移越明显。它不影响中心，只影响边缘，所以特别容易被误认为“样品边缘本来就这样”。

判断方法：同一片样品，在安全温区内分别做关窗与开箱两次测量，把两张形貌图相减。差值如果呈现中心小、边缘大的马鞍形分布，就是折射的贡献。

处理有两条路。一条是建模——把窗口厚度、折射率、入射角纳入光线追迹模型，做反向校正；另一条是缩小依赖——用更薄的窗、更小的视场角、更远的拍摄距离，从源头减少斜视。

这里要提醒一句：折射校正不是可选项。在大视场、厚窗的配置下，边缘偏差可以与待测量同量级，不校正等于放弃边缘数据。

## 四、症状三：曲线整体“平移”

表现是：形貌形状看着没问题，但整条曲线的绝对值偏高或偏低，而且这种偏移随温度变化，越热偏得越多。

来源是刚体运动。晶圆放在支架上，支架随温度膨胀，把样品整体抬起一点；样品与支架之间也可能发生微滑移；如果相机支架与试验箱有机械连接，箱体热膨胀还会改变双目基线。这些运动全片一致，与热变形无关，但会一比一叠加。

判断方法：看形貌的整体平移分量。把每个温度节点的位移场做平面拟合，如果拟合平面的常数项随温度单调增长，且量级与支架热膨胀估算相符，基本可以确认。

处理是刚体位移消除：选一组假定不动的参照（样品边缘的固定标志点、或支架上的参考点），解算六自由度并扣除。难度不在算法，在“参照点选得对不对”——参照点如果本身在动，扣掉的就是真实变形。

## 五、症状四：CTE 总是偏大

表现是：反演出来的热膨胀系数，比材料手册上的值系统性地高一截，而且不同批次偏高程度还不一样。

原因通常是温度与图像没对齐。升温过程中，样品温度、腔内空气温度、热电偶读数三者不同步；如果图像采集与温度记录各走各的时钟，某一帧对应的真实温度就说不准。CTE 是位移差除以温差，温差如果被低估，系数就被高估。

判断方法：查同一温度节点在升温段与保温段的位移是否一致。如果保温十分钟后数据还在缓慢变化，说明样品还没热透，此刻的温度读数偏高或位移读数偏低。

处理分两级。硬件级是让温度记录与相机共用一个触发源；软件级是以保温平台的末段作为对齐锚点，把帧号与温度节点绑定。两级都做，才算把这条时间轴钉住。

| 症状 | 本质 | 是否系统偏差 | 处理成本 |
| --- | --- | --- | --- |
| 图像呼吸 | 折射率随机波动 | 部分是 | 低（等温、平均） |
| 边缘缩水 | 斜视折射 | 是 | 中（建模或改配置） |
| 曲线平移 | 刚体运动 | 是 | 低（算法扣除） |
| CTE 偏大 | 时间轴错位 | 是 | 低到中（同步） |

## 六、还有一类：散斑“翻脸”

这一类不属于光学干扰，但破坏力最大：散斑在某个温度点开始起皮、流淌或与基底相对滑移。

表现是曲线突然跳一下，之后整体偏一个常数；或者匹配残差在某区域骤增，云图出现“撕裂”。最麻烦的是它往往不可逆——一旦滑移，之后的位移都是错的。

判断方法：测完后回放每一帧的匹配质量图，看是否有区域在某个温度节点突然变差。另一招是空跑：不放样品，只放一块带固定散斑的耐温板，走一遍完整温度曲线，看散斑是否稳定。

处理只能从制样入手：薄而致密、与基底结合牢、耐温区间覆盖全工况。散斑一旦出问题，算法救不回来。

## 七、排查顺序：从便宜的动作开始

四类问题加一类制样问题，排查应该按成本从低到高走，别一上来就换设备。

| 顺序 | 动作 | 能排除什么 | 耗时 |
| --- | --- | --- | --- |
| 1 | 对着参考物连拍 | 抖动来自空气还是样品 | 十分钟 |
| 2 | 空跑整条温度曲线 | 散斑与光路稳定性 | 半天 |
| 3 | 开窗与关窗对照 | 折射贡献量级 | 半天 |
| 4 | 平面拟合看常数项 | 刚体漂移 | 十分钟 |
| 5 | 保温段末帧与首帧对比 | 温度是否稳定 | 十分钟 |
| 6 | 换标定件复核 | 标定本身是否漂 | 一小时 |

这六步做完，九成问题能定位到具体环节，剩下的一成才需要讨论设备精度。

## 八、哪些能补，哪些只能改

**能补的**：刚体漂移（算法扣除）、温度错时（同步或锚定）、气流抖动（等温加平均）、折射（建模校正）。这四类都属于“知道原因就有办法”。

**只能改的**：散斑高温失效（重做制样）、视场不足（换镜头或分段）、温区超限（换窗口与镜头）、腔内强对流无法抑制（改结构或改采集策略）。

这个区分很重要。前者是调试功夫，后者是方案缺陷。把方案缺陷当调试问题处理，会陷入反复试验却总也不到位的循环。

## 九、常见问题

**1. 数据抖动大，是不是相机分辨率不够？**

多数不是。先看参考物是否也在抖，如果参考物稳定而样品抖，问题在样品或装夹；如果两者都抖，问题在空气或光路。分辨率不够只会让数据“台阶粗”，不会让数据“忽上忽下”。

**2. 只测室温与峰值两个温度，能不能省掉同步的麻烦？**

省了工序，但丢了信息。热翘曲的关键往往在中间温度段的转折与局部演化，两个端点看不出这些。而且同步问题在端点测量里同样存在，只是不容易被发现。

**3. 折射校正能不能用软件后期做？**

可以，但需要窗口参数与视角信息。没有这些参数，后期只能做经验性拉伸，属于“看着顺眼”，不是校正。

**4. 支架热膨胀能不能靠选低膨胀材料解决？**

能缓解不能根除。低膨胀材料（如殷钢、陶瓷）热变形小，但仍有残余，且成本上升。比较务实的组合是低膨胀材料加算法扣除。

**5. 怎么判断一次测试的数据可信？**

三条自检：同一工况重复采集的一致性、开窗与关窗的差值是否可解释、升温与保温段的读数是否收敛。三条都过，数据基本可信。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>点击展开：English Version (Click to Expand)</b></summary>

> **Abstract:** Most trouble in wafer thermal warp measurement is not broken equipment but four systematic biases stacking quietly: internal airflow makes the image "breathe", window refraction shrinks the edges, fixture thermal drift shifts the whole curve, and temperature-image misalignment inflates CTE. This article works through the four in symptom-cause-diagnosis-treatment order, provides a diagnostic chain that can be followed step by step, and separates the biases that can be corrected from those that require a design change.

> **Keywords:** high-temperature measurement; wafer warp; airflow; window refraction; rigid-body drift; temperature synchronisation; speckle failure

## Contents

- [1. Recognise the Symptom First](#1-recognise-the-symptom-first)
- [2. Symptom One: The Image Breathes](#2-symptom-one-the-image-breathes)
- [3. Symptom Two: The Edges Shrink](#3-symptom-two-the-edges-shrink)
- [4. Symptom Three: The Curve Shifts](#4-symptom-three-the-curve-shifts)
- [5. Symptom Four: CTE Runs High](#5-symptom-four-cte-runs-high)
- [6. One More: Speckle Turns on You](#6-one-more-speckle-turns-on-you)
- [7. Diagnostic Order: Cheapest First](#7-diagnostic-order-cheapest-first)
- [8. What Can Be Fixed and What Cannot](#8-what-can-be-fixed-and-what-cannot)
- [9. FAQ](#9-faq)

## 1. Recognise the Symptom First

When a thermal warp test goes wrong, suspecting camera accuracy first is a mistake. Accuracy is the last thing to doubt; there are far more common causes upstream.

Four symptoms are easy to recognise, each with its own signature.

| Symptom | What you see | Actual cause |
| --- | --- | --- |
| Breathing image | Data jitters between frames of one condition | Internal airflow, refractive index fluctuation |
| Shrinking edges | Centre normal, periphery form too small | Oblique refraction at the window |
| Shifted curve | Whole curve raised or lowered | Fixture thermal drift, sample slip |
| High CTE | Inverted coefficient systematically large | Temperature-image misalignment |

What they share: they produce no obvious noise, only bias. The contours look clean and the numbers are wrong. That is how they survive in datasets for months.

## 2. Symptom One: The Image Breathes

The signature is clear: ten consecutive frames at one temperature node differ by several to a dozen micrometres in field-mean out-of-plane displacement, with no pattern.

The cause is air. Heating the chamber creates density gradients and convection; the convective layer drifts between sample and window, its refractive index changes, and the imaging path wobbles. It is worst in the hot segment, where the temperature difference is largest.

Diagnosis is easy: point the camera at a stationary reference — a calibration target or fixed marker — and capture a burst. If the reference appears to move, the motion comes from air, not the specimen.

Three levels of treatment. Cheapest is waiting: extend the hold so the chamber equalises before acquisition. Next is baffling: a deflector between sample and window diverts direct airflow. Last is averaging: capture several frames per condition and average, which suppresses random jitter.

Averaging only removes the random component. A stable density gradient is systematic bias, and averaging does nothing for it.

## 3. Symptom Two: The Edges Shrink

The signature: centre region matches expectation, the periphery flattens progressively, warp reads low, and the whole shape seems pulled inward.

The cause is refraction. Stereo cameras viewing the edge of the field look obliquely; the path through glass is longer than at normal incidence, and the image point shifts inward. Thicker glass, wider field and more oblique angles amplify it. The centre is unaffected, so it is easily mistaken for the specimen's natural edge shape.

Diagnosis: measure the same sample within a safe range with the window closed and with the chamber open, then subtract. A difference that is small at the centre and large at the edges — a saddle-shaped residual — indicates refraction.

Two remedies. One is modelling: include window thickness, refractive index and incidence angle in a ray-tracing model and correct backwards. The other is reducing dependence: thinner window, narrower field angle, longer working distance.

Refraction correction is not optional. With a large field and thick window, edge bias can reach the same order as the measurand, and skipping correction means abandoning edge data.

## 4. Symptom Three: The Curve Shifts

The signature: shape looks right, absolute values sit high or low, and the offset grows with temperature.

The source is rigid-body motion. The fixture expands and lifts the specimen; the specimen may slip slightly; if the camera mount is mechanically tied to the chamber, shell expansion changes the stereo baseline. These motions are global, unrelated to thermal deformation, and add one-to-one to the field.

Diagnosis: fit a plane to the displacement field at each node. If the constant term grows monotonically with temperature at a magnitude consistent with fixture expansion, the cause is confirmed.

Treatment is rigid-body removal: choose references assumed fixed — edge markers, or points on the fixture — solve six degrees of freedom and subtract. The algorithm is not the difficulty; choosing the right references is. If a reference point is itself moving, you subtract real deformation.

## 5. Symptom Four: CTE Runs High

The signature: the inverted expansion coefficient sits systematically above handbook values, and the excess differs between batches.

The cause is usually temperature-image misalignment. During a ramp, specimen temperature, chamber air temperature and thermocouple reading are out of phase. If acquisition and temperature logging run on separate clocks, the true temperature of a frame is uncertain. CTE is displacement difference divided by temperature difference; underestimate the denominator and the coefficient rises.

Diagnosis: compare displacement at one node between the ramp and the hold. If data still drifts after ten minutes of holding, the specimen has not equilibrated and either the temperature or the displacement reading is off.

Two levels of treatment. Hardware: drive the logger and cameras from one trigger. Software: anchor frames to the end of each hold and bind frame index to node. Both are needed to pin the time axis.

| Symptom | Nature | Systematic? | Cost to fix |
| --- | --- | --- | --- |
| Breathing image | Random index fluctuation | Partly | Low (equalise, average) |
| Shrinking edges | Oblique refraction | Yes | Medium (model or reconfigure) |
| Shifted curve | Rigid-body motion | Yes | Low (algorithmic subtraction) |
| High CTE | Time-axis offset | Yes | Low to medium (synchronise) |

## 6. One More: Speckle Turns on You

This one is not optical interference, but it does the most damage: the speckle begins to peel, flow or slide relative to the substrate at some temperature.

The signature is a sudden step in the curve followed by a constant offset, or matching residuals spiking in one region and the contour tearing. The worst part is irreversibility — once it slips, every subsequent displacement is wrong.

Diagnosis: replay the matching-quality map for every frame and look for a region degrading abruptly at one node. A dry run with a temperature-tolerant patterned plate through the full profile also works.

Treatment starts at preparation: thin, dense, well bonded, rated for the whole range. Once speckle fails, no algorithm recovers it.

## 7. Diagnostic Order: Cheapest First

Five problem classes, and diagnosis should run from low cost to high. Do not start by replacing equipment.

| Order | Action | Rules out | Time |
| --- | --- | --- | --- |
| 1 | Burst capture on a reference | Air versus specimen jitter | Ten minutes |
| 2 | Dry run through the full profile | Speckle and optical stability | Half a day |
| 3 | Open-chamber versus closed-window | Refraction magnitude | Half a day |
| 4 | Plane fit on the constant term | Rigid-body drift | Ten minutes |
| 5 | End-of-hold versus first frame | Temperature stability | Ten minutes |
| 6 | Re-verify with a calibration artefact | Calibration drift | One hour |

Six steps locate nine out of ten problems to a specific link. Only the remaining tenth requires a discussion about equipment accuracy.

## 8. What Can Be Fixed and What Cannot

**Fixable:** rigid-body drift (algorithmic subtraction), temperature misalignment (synchronisation or anchoring), airflow jitter (equalise and average), refraction (model correction). All four are cases of "know the cause, find a remedy".

**Not fixable by tuning:** speckle failure at temperature (re-prepare), insufficient field of view (change lens or segment), range beyond limits (change window and optics), strong convection that cannot be suppressed (change structure or acquisition strategy).

The distinction matters. The first group is commissioning work; the second is a design defect. Treating a design defect as a commissioning problem leads to endless iteration that never quite lands.

## 9. FAQ

**1. Is large data jitter a resolution problem?**

Usually not. Check whether the reference is also jittering: a stable reference with a jittering specimen points to the specimen or mounting; both jittering points to air or optics. Insufficient resolution makes data coarse, not unstable.

**2. Can I skip synchronisation by measuring only room temperature and peak?**

You save steps and lose information. The interesting behaviour — inflection and local evolution — lives in the middle of the range. Synchronisation problems also exist at endpoints, only less visibly.

**3. Can refraction be corrected in post-processing?**

Yes, given window parameters and viewing geometry. Without them, post-processing amounts to empirical stretching that looks acceptable rather than corrects anything.

**4. Does a low-expansion fixture material solve thermal drift?**

It mitigates without eliminating. Low-expansion materials such as Invar or ceramics deform less but not zero, and cost more. A practical combination is low-expansion material plus algorithmic subtraction.

**5. How do I judge whether a dataset is trustworthy?**

Three self-checks: repeatability of the same condition, explainable difference between open and closed window, and convergence between ramp and hold readings. Pass all three and the data is broadly credible.

</details>
