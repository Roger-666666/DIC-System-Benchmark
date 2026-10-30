# 测晶圆翘曲的三条路线：Shadow Moiré、DFP与三维DIC怎么选

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 同样一片翘了 300 μm 的晶圆，三种主流手段测出来的数字可能对不上，因为它们根本不在测同一个量。Shadow Moiré 给 Z 向面形，DFP 给大视场的相位面形，三维 DIC 给全场位移与应变。本文不排名次，只做一件事：把三条路线的成像原理、输出口径、适用边界摊在桌面上，再列出五种最常见的误配——选错方法的代价，往往比买贵设备更大。

> **关键词：** 晶圆翘曲测量；Shadow Moiré；DFP；三维DIC；方法选型；面形与应变

## 目录

- [一、数字对不上，是因为口径不同](#一数字对不上是因为口径不同)
- [二、Shadow Moiré：用光栅把高度变成条纹](#二shadow-moiré用光栅把高度变成条纹)
- [三、DFP：投影条纹的相位路线](#三dfp投影条纹的相位路线)
- [四、三维DIC：双目加散斑的全场路线](#四三维dic双目加散斑的全场路线)
- [五、四条能力维度摊开比](#五四条能力维度摊开比)
- [六、各自的失效边界](#六各自的失效边界)
- [七、五种典型误配](#七五种典型误配)
- [八、选型只需回答三个问题](#八选型只需回答三个问题)
- [九、常见问题](#九常见问题)

## 一、数字对不上，是因为口径不同

先摆一个常见场面。同一片晶圆，甲用莫尔条纹法测出翘曲 280 μm，乙用三维DIC测出 310 μm，丙用投影条纹法测出 295 μm。三个人开会，先吵半小时谁错了。

很可能谁都没错。三种方法测的不是同一个量：莫尔给的是相对参考平面的高度分布，投影条纹给的是相位解算出的面形，DIC给的是每点的三维位移。参考面不同、平均口径不同、包含的刚体分量不同，数字自然不同。

| 方法 | 本质测的量 | 时间维度 |
| --- | --- | --- |
| Shadow Moiré | Z 向高度分布（相对光栅平面） | 单状态快照 |
| DFP | 相位解算的全场面形 | 单状态或短序列 |
| 三维DIC | 每点三维位移场 | 全温域序列 |

所以方法比较的第一步不是比精度，而是比“测的是不是同一个东西”。口径不统一，精度讨论毫无意义。

## 二、Shadow Moiré：用光栅把高度变成条纹

原理不复杂：在样品上方放一块光栅，光透过光栅照到样品表面再返回，与光栅本身形成干涉。样品表面高度不同，光程不同，形成的莫尔条纹就发生位移。条纹的疏密与位移直接编码了高度信息。

它的优点是直接、快、成本可控，适合产线上的快速抽检与平整度判断。缺点是它需要光栅贴近样品，工作距离短，样品必须处在光栅覆盖范围内；对温度环境不友好——高温腔里放光栅，热膨胀会让光栅栅距变化，条纹基准跟着漂。

另一个限制是它只能测高度（Z 向），拿不到面内信息。想知道应变分布、想反演 CTE，这条路走不通。

## 三、DFP：投影条纹的相位路线

DFP（投影条纹相位测量）把光栅换成投影仪：把正弦条纹投影到样品表面，相机拍摄变形后的条纹，通过相位解算还原面形。

相比莫尔，它的优势是视场大、非接触距离远，能覆盖整片晶圆甚至整块大板；投影条纹的相位解算精度也高。它在整机厂的大板检测、晶圆级封装的面形检查中用得不少。

它的边界在于：投影与成像都要经过光学窗口，条纹在窗口上的折射会引入相位误差；条纹投影对表面反射特性敏感，镜面样品的强反光会让相位解算出现空洞；同样，它输出的是面形，不是位移场与应变场。

## 四、三维DIC：双目加散斑的全场路线

三维DIC走的是另一条逻辑：不做干涉，不做投影，只做“跟踪”。双目相机拍下表面散斑，通过相关匹配找到同一点在变形前后的位置，三角测量给出三维坐标，坐标之差就是位移。

它的强项是“全”：全场位移、全场应变、离面翘曲、面内伸缩，一套数据全在里面；而且可以在整个温度历程里连续采集，形成序列，而不是单点快照。

代价是：需要表面有可匹配的纹理（镜面硅片要做散斑）；计算量比条纹法大；对成像稳定性（标定、刚体漂移、窗口折射）要求高，前期调校的功夫多。

| 维度 | Shadow Moiré | DFP | 三维DIC |
| --- | --- | --- | --- |
| 输出量 | Z 向面形 | 全场面形 | 位移场 + 应变场 |
| 视场 | 受光栅尺寸限制 | 大，可拼接 | 中到大，取决于镜头 |
| 工作距离 | 短，需贴近 | 中远距离 | 中距离 |
| 高温环境适应性 | 弱（光栅热变形） | 中（窗口折射） | 中到强（可校准） |
| 表面要求 | 需一定漫反射 | 需适中反射 | 需散斑纹理 |
| CTE 反演 | 不可 | 不可 | 可 |
| 典型定位 | 产线抽检 | 大板/晶圆面形 | 研发、失效分析、仿真对标 |

## 五、四条能力维度摊开比

把上表浓缩成四条判断线，选型时更实用。

**第一条：你要的是面形还是场。** 只要一个“平不平”的结论，前两种够用；要应变、要 CTE、要看局部集中，只有第三种给得出。

**第二条：你要的是快照还是过程。** 产线抽检关心单片节拍，快照更合适；研发关心温度历程，需要序列。

**第三条：环境有多不友好。** 高温、有窗、有气流，这三种干扰对干涉与投影类方法的影响更直接；DIC 可以靠校准与算法补偿，但也需要投入。

**第四条：你有没有制样条件。** 散斑需要工艺与时间，产线上给每片做散斑不现实；而干涉类方法对表面准备要求低。

| 判断线 | 偏向前两种 | 偏向三维DIC |
| --- | --- | --- |
| 输出需求 | 只要面形/平整度 | 要应变、CTE、局部集中 |
| 时间需求 | 单状态快照、高节拍 | 全温域序列 |
| 环境 | 常温、无遮挡 | 高温、隔窗、有气流（需校准） |
| 制样 | 不愿改变表面 | 可做散斑、可等待 |

## 六、各自的失效边界

**Shadow Moiré 失效于**：光栅与样品间距超出范围；样品高度变化超过条纹级次可解范围（大幅翘曲会出现级次混淆）；高温导致光栅热变形。

**DFP 失效于**：镜面强反光导致相位空洞；窗口折射未校正；投影与成像夹角过大造成遮挡阴影。

**三维DIC 失效于**：无纹理且无法制斑；散斑在高温下失效；变形超出视场或景深；腔内强对流导致噪声抬升。

三种方法的失效条件不一样，这一点比精度指标更值得记住——因为失效往往不是“差一点”，而是“完全不能用”。

## 七、五种典型误配

| 误配 | 表面诉求 | 实际问题 |
| --- | --- | --- |
| 用莫尔做全温域演化 | 想看升温过程 | 只能给快照，且光栅受热变形 |
| 用莫尔反演 CTE | 想要热膨胀系数 | 无面内信息，原理上不可行 |
| 用 DFP 隔着厚窗测高温 | 想省掉开窗 | 折射相位误差，数据整体偏移 |
| 用 DIC 做产线全检 | 想提效率 | 散斑制备与计算时间拖垮节拍 |
| 用单点位移计代表全场 | 想省成本 | 局部塌陷完全漏检 |

第三、第五种最隐蔽。折射引起的偏差不会让图像变糊，只会让数值整体偏一点；单点位移计读数稳定、曲线漂亮，但恰恰漏掉了最危险的那个局部。

## 八、选型只需回答三个问题

**问题一：结论要用来干什么？** 来料验收、工艺放行、机理分析、仿真对标，四个用途对应四种数据要求。用途定了，方法范围就窄了一半。

**问题二：样品在什么环境里？** 常温台面、高温腔体、隔窗观察，环境决定了能上什么方法。环境不合适，再高的精度指标也用不上。

**问题三：这个数据要重复多少次？** 一次性研究、每批抽检、每片全检，三种频次对应三套投入。研究可以慢慢调，全检必须算节拍。

三个问题答完，选择通常已经很清楚。真正难的不是技术比较，而是承认“我们其实只需要一个面形结论”，然后不必买全场系统。

## 九、常见问题

**1. 三种方法能不能互相替代？**

部分场景可以。只是判断“平不平”，莫尔或投影都够；一旦涉及应变、CTE、局部变形集中，就只有全场位移类方法能给出。替代性取决于输出口径，不取决于精度。

**2. 三维DIC 的精度一定比莫尔高吗？**

不一定，而且这样比没有意义。莫尔在 Z 向面形上有很好的分辨能力，DIC 的强项是全场位移与应变。选型应该比“能不能给出我要的量”，而不是笼统比精度。

**3. 高温环境下哪种方法更稳？**

取决于处理方式。干涉与投影类方法受窗口折射与光栅热变形影响较大，DIC 受散斑稳定性与气流影响较大。没有天然更稳的方法，只有校准做得更扎实的方案。

**4. 散斑能不能省掉？**

如果样品表面本身有可利用的微结构（电路图形、镀层颗粒），可以尝试天然纹理。但镜面硅片通常需要制斑，且要全程保持稳定。省掉制斑的代价往往是数据不可用。

**5. 一套系统能不能兼顾研发与产线？**

可以兼顾但很难兼顾好。研发要的是信息量与可追溯，产线要的是节拍与一致性，两者对配置、操作复杂度、数据处理的要求相反。多数情况是两套配置各司其职。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>点击展开：English Version (Click to Expand)</b></summary>

> **Abstract:** The same wafer with 300 μm of warp can produce three different numbers from three mainstream methods, because they are not measuring the same quantity. Shadow Moiré gives Z-direction surface form, DFP gives phase-derived form over a large field, and 3D DIC gives full-field displacement and strain. This article ranks nothing; it lays out the imaging principle, output definition and applicable boundary of each route, then lists five common mismatches — choosing the wrong method usually costs more than buying expensive equipment.

> **Keywords:** wafer warp measurement; Shadow Moiré; DFP; 3D DIC; method selection; surface form and strain

## Contents

- [1. Numbers Disagree Because Definitions Differ](#1-numbers-disagree-because-definitions-differ)
- [2. Shadow Moiré: Turning Height into Fringes](#2-shadow-moiré-turning-height-into-fringes)
- [3. DFP: The Phase Route](#3-dfp-the-phase-route)
- [4. 3D DIC: Stereo Plus Speckle](#4-3d-dic-stereo-plus-speckle)
- [5. Four Capability Dimensions](#5-four-capability-dimensions)
- [6. Where Each Method Fails](#6-where-each-method-fails)
- [7. Five Typical Mismatches](#7-five-typical-mismatches)
- [8. Three Questions Settle the Choice](#8-three-questions-settle-the-choice)
- [9. FAQ](#9-faq)

## 1. Numbers Disagree Because Definitions Differ

A familiar scene: the same wafer measures 280 μm by moiré, 310 μm by 3D DIC and 295 μm by fringe projection. The meeting spends half an hour establishing who is wrong.

Probably nobody. The three methods do not measure the same quantity: moiré gives a height distribution relative to a reference plane, fringe projection gives a phase-derived surface form, and DIC gives 3D displacement at every point. Different references, different averaging conventions, different rigid-body content — different numbers follow.

| Method | Quantity measured | Time dimension |
| --- | --- | --- |
| Shadow Moiré | Z-height distribution relative to the grating plane | Single-state snapshot |
| DFP | Phase-derived full-field surface form | Single state or short sequence |
| 3D DIC | 3D displacement field per point | Full-range sequence |

The first step in comparing methods is therefore not accuracy but whether they measure the same thing. Without a common definition, accuracy discussion is meaningless.

## 2. Shadow Moiré: Turning Height into Fringes

The principle is straightforward. A grating sits above the sample; light passes through it, reflects off the surface and interferes with the grating itself. Different surface heights mean different optical paths, so the moiré fringes shift. Fringe spacing and displacement encode height directly.

Its strengths are directness, speed and moderate cost, which suits rapid sampling and flatness checks on a line. Its limits are equally clear: the grating must sit close to the sample, working distance is short, and the sample must fall within the grating's coverage. High-temperature environments are unfriendly — a grating inside a hot chamber expands, the pitch changes, and the fringe datum drifts.

It also measures height only. In-plane information is unavailable, so strain distribution and CTE inversion are out of reach.

## 3. DFP: The Phase Route

DFP replaces the grating with a projector: sinusoidal fringes are projected onto the surface, a camera captures the deformed pattern, and phase decoding reconstructs the shape.

Compared with moiré, the advantages are a large field and a longer non-contact working distance, enough to cover a whole wafer or a large panel. Phase decoding also delivers good resolution. It is widely used for panel inspection and wafer-level package form checks.

Its boundaries: both projection and imaging pass through an optical window, and refraction introduces phase error; fringe projection is sensitive to surface reflectance, and strong specular reflection on mirror samples creates phase holes. It also outputs form, not a displacement or strain field.

## 4. 3D DIC: Stereo Plus Speckle

3D DIC follows a different logic: no interference, no projection, only tracking. Stereo cameras image a speckle pattern, correlation matching locates the same point before and after deformation, triangulation yields 3D coordinates, and the coordinate difference is displacement.

Its strength is completeness: full-field displacement, full-field strain, out-of-plane warp and in-plane expansion all come from one dataset, and acquisition can run continuously through a temperature history to form a sequence rather than a snapshot.

The costs: the surface needs matchable texture (mirror silicon requires speckle); computation is heavier than fringe methods; and imaging stability — calibration, rigid-body drift, window refraction — demands careful setup work.

| Dimension | Shadow Moiré | DFP | 3D DIC |
| --- | --- | --- | --- |
| Output | Z-direction form | Full-field form | Displacement and strain fields |
| Field of view | Limited by grating size | Large, tileable | Medium to large, lens dependent |
| Working distance | Short, close to sample | Medium to long | Medium |
| High-temperature tolerance | Weak (grating distortion) | Moderate (window refraction) | Moderate to strong (calibratable) |
| Surface requirement | Some diffuse reflection | Moderate reflection | Speckle texture |
| CTE inversion | Not possible | Not possible | Possible |
| Typical role | Line sampling | Panel and wafer form | R&D, failure analysis, simulation correlation |

## 5. Four Capability Dimensions

Condensed into four decision lines, the comparison becomes practical.

**Form or field.** If the conclusion is "is it flat", the first two suffice. Strain, CTE and local concentration require the third.

**Snapshot or process.** Line sampling cares about per-unit takt, where a snapshot fits. Development cares about thermal history, which needs a sequence.

**How hostile the environment is.** High temperature, a window, airflow — these disturb interference and projection methods more directly. DIC can compensate through calibration and algorithms, but the investment is real.

**Whether you can prepare the surface.** Speckle takes process and time; applying it to every wafer on a line is unrealistic, while interference methods need little surface preparation.

| Decision line | Favours the first two | Favours 3D DIC |
| --- | --- | --- |
| Output need | Form or flatness only | Strain, CTE, local concentration |
| Time need | Single snapshot, high takt | Full-range sequence |
| Environment | Room temperature, unobstructed | Hot, behind glass, airflow (needs calibration) |
| Surface preparation | Surface must stay untouched | Speckle acceptable, time available |

## 6. Where Each Method Fails

**Shadow Moiré fails when** the grating-to-sample gap exceeds its range; height change exceeds the resolvable fringe order (large warp causes order ambiguity); or heat distorts the grating.

**DFP fails when** specular reflection creates phase holes; window refraction is uncorrected; or the projection-imaging angle causes shadowing.

**3D DIC fails when** the surface has no texture and cannot be patterned; speckle degrades at temperature; deformation exceeds the field of view or depth of field; or strong convection raises the noise floor.

The failure conditions differ, and that matters more than accuracy figures — failure is usually not "slightly off" but "unusable".

## 7. Five Typical Mismatches

| Mismatch | Intended goal | Actual problem |
| --- | --- | --- |
| Moiré for full-range evolution | Watch the heating process | Snapshots only, grating distorts with heat |
| Moiré for CTE inversion | Obtain expansion coefficient | No in-plane data, impossible in principle |
| DFP through a thick window at temperature | Avoid opening the chamber | Refraction phase error biases the whole field |
| DIC for 100% line inspection | Raise throughput | Speckle preparation and computation break takt |
| One displacement sensor for the field | Save cost | Local collapse goes undetected |

The third and fifth are the most deceptive. Refraction bias does not blur the image, it merely shifts values; a single sensor gives stable, well-behaved curves while missing exactly the dangerous local region.

## 8. Three Questions Settle the Choice

**What will the conclusion be used for?** Incoming acceptance, process release, mechanism analysis, simulation correlation — four uses, four data requirements. Fix the use and half the method space disappears.

**What environment is the sample in?** Benchtop, hot chamber, behind glass — the environment decides which methods are even possible. If it does not fit, the highest accuracy specification is irrelevant.

**How many times must this be repeated?** One-off study, batch sampling, full inspection — three frequencies, three investment levels. Research can be tuned slowly; full inspection must meet takt.

After those three answers the choice is usually obvious. The hard part is not technical comparison but admitting "we only need a form verdict" and not buying a full-field system.

## 9. FAQ

**1. Can the three methods substitute for each other?**

Partly. For "is it flat", moiré or projection suffices; once strain, CTE or local concentration matters, only a full-field displacement method delivers. Substitutability depends on output definition, not accuracy.

**2. Is 3D DIC always more accurate than moiré?**

No, and the comparison is meaningless. Moiré resolves Z-direction form well; DIC's strength is full-field displacement and strain. Selection should ask whether a method produces the required quantity.

**3. Which method is more stable at high temperature?**

It depends on the implementation. Interference and projection suffer from window refraction and grating distortion; DIC suffers from speckle stability and airflow. No method is inherently steadier — only better-calibrated setups.

**4. Can speckle be skipped?**

If the surface carries usable micro-structure (circuit features, coating grains), natural texture may work. Mirror silicon usually needs a pattern, and it must survive the whole run. Skipping preparation typically costs the dataset.

**5. Can one system serve both development and production?**

It can, but rarely well. Development needs information density and traceability; production needs takt and consistency — opposite demands on configuration, operating complexity and data processing. Most sites end up with two configurations, each doing its own job.

</details>
