# 6英寸硅晶圆0~150℃热翘曲实测复盘：297μm峰值与那一段回落

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 一次完整的晶圆热翘曲测试：6 英寸单晶硅片，直径 150 mm、厚 1 mm，0~150℃ 每 10℃ 一个温度节点，S0~S15 共 16 个工况。结果里最值得琢磨的不是峰值数字，而是峰值之后的那段回落——120℃ 平均离面位移到 297 μm，温度继续升高，翘曲不升反降。这篇复盘按“目标—工况—读图—曲线—解释—误读—去向”的顺序把这次测试拆开，重点讲清回落为什么不是测量出错，以及这类数据到底能拿去做什么。

> **关键词：** 晶圆翘曲；热翘曲实测；离面位移；温度节点；应力释放；非均匀变形；三维DIC

## 目录

- [一、这次测试要回答什么](#一这次测试要回答什么)
- [二、试样与工况](#二试样与工况)
- [三、开测前的三个动作](#三开测前的三个动作)
- [四、按温度段读云图](#四按温度段读云图)
- [五、主曲线：从 S0 到 S15](#五主曲线从-s0-到-s15)
- [六、回落这一段怎么解释](#六回落这一段怎么解释)
- [七、三个容易被误读的地方](#七三个容易被误读的地方)
- [八、这批数据往哪用](#八这批数据往哪用)
- [九、复盘：重做一次会改什么](#九复盘重做一次会改什么)
- [十、常见问题](#十常见问题)

## 一、这次测试要回答什么

做热翘曲测试，最怕目标含糊：只想“看看翘多少”，测一个室温加一个峰值温度就够了。这次定了四条：复现升温全过程的翘曲演化，取序列而不取点；量化各温度节点的离面位移幅值；定位局部变形集中区，而不只给全场平均；为封装热匹配分析提供实测输入。

| 目标 | 对应要求 | 对工况的影响 |
| --- | --- | --- |
| 复现演化过程 | 全温域连续采集 | 节点加密，不能只取首末 |
| 量化离面位移 | 全场位移场 | 需要全场三维手段 |
| 定位集中区域 | 空间分辨率足够 | 视场覆盖全片，不能裁边 |
| 提供对标输入 | 数据可追溯 | 帧-温绑定、元数据完整 |

## 二、试样与工况

试样是一批 6 英寸单晶硅晶圆，直径 150 mm，厚度 1 mm。选裸片而非封装成品，是先看清基底本身在热载荷下的响应，把变量压到最少。

工况是阶梯升温：0℃ 起步，150℃ 结束，每 10℃ 一个节点，共 16 个工况（S0 到 S15），每个节点保温至样品温度稳定后采集一组图像。

| 项目 | 设定 |
| --- | --- |
| 试样 | 6 英寸单晶硅晶圆 |
| 直径 | 150 mm |
| 厚度 | 1 mm |
| 温度区间 | 0℃ ~ 150℃ |
| 节点间隔 | 10℃ |
| 节点数 | 16（S0~S15） |
| 升温方式 | 阶梯升温、逐点保温 |
| 测量手段 | 三维DIC + 高低温试验箱 |

## 三、开测前的三个动作

实测数据好不好，八成在开测前就定了。

**第一件，散斑。** 硅片是镜面，直接成像是均匀亮区，匹配无从下手。表面做薄而致密的散斑，使其在 0℃ 不脆裂、150℃ 不流淌，先试片再上正式样品。

**第二件，支撑方式。** 晶圆怎么放决定边界条件。这次用轻支撑，尽量减少夹具对自由变形的约束——研究目标是基底本身的热响应。

**第三件，光路与零点。** 双目相机隔着观察窗成像，折射先做校准；每片样品单独建参考面，初始形貌作零位。

| 动作 | 做错的后果 | 现场判据 |
| --- | --- | --- |
| 散斑制备 | 中途失配、曲线断裂 | 空跑首末帧匹配良好 |
| 支撑方式 | 测出“夹具+样品”的合成变形 | 空载重复性稳定 |
| 折射校准 | 边缘形貌系统性压缩 | 开窗对照差值可解释 |
| 零点建立 | 初始差异算进热变形 | 同片重装复现性好 |

## 四、按温度段读云图

16 个节点分四组看，脉络比较清楚。

**S0~S3（0~30℃）**：材料尚硬、膨胀量小，形貌接近初始状态，只有边缘轻微起伏。这一段是基准。

**S4~S7（40~70℃）**：起伏明显，中心与边缘高差拉大，形貌从“接近平”转向“明显拱起”，是判断转折起点的区间。

**S8~S11（80~110℃）**：幅值增长最快，翘曲近似线性上升，等高线变密，局部出现“鼓包”，变形不再是协调的球面。

**S12~S15（120~150℃）**：120℃ 前后达到本轮最大值，之后峰谷差不再扩大，反而略有收缩。

| 温度段 | 节点 | 形貌特征 | 读图要点 |
| --- | --- | --- | --- |
| 0~30℃ | S0~S3 | 接近初始形貌，边缘轻微起伏 | 作为基准段 |
| 40~70℃ | S4~S7 | 中心-边缘高差拉大 | 转折起点判断 |
| 80~110℃ | S8~S11 | 幅值快速增长，出现局部鼓包 | 变形协调性下降 |
| 120~150℃ | S12~S15 | 达峰后小幅收缩 | 非单调，需解释 |

云图上各温度段都不是规整球面：中心平缓、中环起伏最大、边缘收敛。平均值说得出“翘了多少”，说不出“哪里翘得最狠”。

## 五、主曲线：从 S0 到 S15

把 16 个节点的平均离面位移连成曲线，形状并不单调：S0 到 S11 持续上升，S8 之后斜率变大；S12（120℃）附近达峰，约 297 μm；S13 之后掉头，S15（150℃）低于峰值。

| 节点 | 温度 | 平均离面位移（相对 S0） | 阶段特征 |
| --- | --- | --- | --- |
| S0 | 0℃ | 基准 | 起始 |
| S4 | 40℃ | 缓慢增长 | 过渡 |
| S8 | 80℃ | 加速增长 | 斜率变大 |
| S12 | 120℃ | 约 297 μm | 本轮峰值 |
| S15 | 150℃ | 低于峰值 | 回落 |

口径要说清：297 μm 是全场平均离面位移，不是单点最大值，也不是峰谷差，三个量不能混用。

## 六、回落这一段怎么解释

曲线掉头，第一反应是“是不是测错了”。可以排除：测量问题通常是抖动、跳变、中断，不会是平滑缓慢的下降，且 16 个节点全部参与。

解释在材料行为里。

**一是应力松弛。** 温度升到一定区间，位错活动增强，部分弹性应变被塑性吸收，靠弹性“撑着”的翘曲失去支撑，形貌回收一些。

**二是材料软化。** 温度升高，各层模量下降，同样应力产生的变形响应改变；层间约束减弱，刚度下降，形貌趋于松弛。

**三是 CTE 曲线本身不是直线。** 膨胀系数随温度变化，某些区间膨胀速率放缓，翘曲增量随之减小。当松弛效应超过膨胀效应，宏观表现就是回落。

| 解释 | 机理 | 可验证的特征 |
| --- | --- | --- |
| 应力松弛 | 位错活动、塑性吸收弹性应变 | 降温段出现迟滞 |
| 材料软化 | 模量下降、约束减弱 | 回落幅度随温度单调增加 |
| CTE 非线性 | 膨胀速率随温度变化 | 与材料曲线对照可核 |

三种机制不互斥，很可能同时作用；要区分需加一段降温，看是否出现迟滞环。这次只做升温，解释只能停留在“机制上说得通”。

## 七、三个容易被误读的地方

**误读一：把平均值当成全场。** 297 μm 是平均量，局部可能 400 μm、另一处 200 μm；只盯平均值，容易在局部失效点上看走眼。

**误读二：把回落当成测量失效。** 热翘曲不是单调函数，回落是有物理含义的信号，剔除等于扔掉信息量最大的一段。

**误读三：把单点比较当成工艺比较。** 297 μm 与 280 μm 不能直接判后者更好——前者形貌均匀、后者局部塌陷时，风险排序可能相反。

| 误读 | 后果 | 纠正方式 |
| --- | --- | --- |
| 平均值代替全场 | 漏掉局部高风险区 | 同时报峰谷差与最大梯度位置 |
| 回落当失效 | 丢失机理信息 | 结合松弛与软化解释，加降温验证 |
| 单点比工艺 | 结论反向 | 固定口径，附形貌类型 |

## 八、这批数据往哪用

**封装热匹配。** 基底在 0~150℃ 的形貌演化，是叠层热匹配设计的边界条件；知道哪个温度段变化最剧烈，就能判断工艺窗口往哪边调。

**仿真对标。** 有限元曲线需要实测参照；16 个节点正好看出模型在哪个温度段偏离最大，是模量取值偏了还是 CTE 曲线不对。

**材料与工艺选型。** 同一套工况换不同批次、不同减薄厚度的样品，形貌演化差异可直接比较。

**失效分析。** 出现裂纹或焊点开路时，把失效件与正常件的翘曲历史对比，往往能找到异常温区。

| 用途 | 输入 | 输出 |
| --- | --- | --- |
| 封装热匹配 | 全温域形貌序列 | 工艺窗口建议 |
| 仿真对标 | 曲线 + 云图 | 模型参数修正方向 |
| 材料选型 | 多批次对比 | 批次一致性判断 |
| 失效分析 | 失效件历史曲线 | 异常温区定位 |

## 九、复盘：重做一次会改什么

**加降温段。** 最该补的一项：只有升温看不出迟滞，也分不清回落到弹性非线性还是塑性；加一段对称降温，成本有限，信息量翻倍。

**局部高分辨率采集。** 全场解决了覆盖，局部鼓包的细节受像素限制；下一轮加一组特写，盯住起伏最大的中环带。

**记录夹具温度。** 这次只记了腔内与样品附近温度。夹具热膨胀是刚体位移的主要来源，补上它，刚体扣除更有依据。

**延长高温段保温。** S13~S15 的回落若与松弛相关，保温时长直接影响幅度；拉长保温看回落是否持续，是廉价判据。

## 十、常见问题

**1. 为什么用单晶硅裸片而不是封装成品？**

裸片把变量减到最少。叠层翘曲是多种材料共同作用的结果，先测基底，才能分清哪些变化来自硅本身、哪些来自叠层失配。

**2. 297 μm 这个数能不能直接拿去做标准？**

不能。它是这一批样品、这一套工况下的实测结果，与支撑方式、升温速率、批次都相关，只能作为对比基准与仿真输入。

**3. 16 个节点够不够密？**

对 0~150℃ 这个区间，10℃ 一档足以看出拐点与斜率变化；要精确定位转折温度，可在候选区间加密到 5℃。

**4. 回落幅度不大，是不是可以忽略？**

不建议。回落幅度小不代表信息量小，它标记了应力松弛开始起作用的温度区间，忽略它可能把“已经开始松弛”误判成“仍在弹性增长”。

**5. 同样的测试换一台设备，结果会一样吗？**

量级应该一致，数值不会完全相同，差异来自支撑方式、散斑质量、折射校准、温度控制精度等一整套条件；跨设备比较前要先确认这些条件可比。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>点击展开：English Version (Click to Expand)</b></summary>

> **Abstract:** A complete wafer thermal warp test: a 6-inch monocrystalline silicon wafer, 150 mm in diameter and 1 mm thick, ramped from 0 to 150℃ in 10℃ steps — 16 conditions labelled S0 to S15. The most instructive feature is not the peak value but the decline after it: mean out-of-plane displacement reaches 297 μm at 120℃, then falls as temperature continues to rise. This review walks through objective, conditions, contour reading, curve, explanation, misreadings and downstream use, with emphasis on why the decline is not a measurement error and what such data can actually support.

> **Keywords:** wafer warp; thermal warp measurement; out-of-plane displacement; temperature node; stress relaxation; non-uniform deformation; 3D DIC

## Contents

- [1. What the Test Had to Answer](#1-what-the-test-had-to-answer)
- [2. Specimen and Conditions](#2-specimen-and-conditions)
- [3. Three Actions Before the First Frame](#3-three-actions-before-the-first-frame)
- [4. Reading the Contours by Temperature Band](#4-reading-the-contours-by-temperature-band)
- [5. The Main Curve from S0 to S15](#5-the-main-curve-from-s0-to-s15)
- [6. Explaining the Decline](#6-explaining-the-decline)
- [7. Three Common Misreadings](#7-three-common-misreadings)
- [8. Where This Data Goes](#8-where-this-data-goes)
- [9. What to Change Next Time](#9-what-to-change-next-time)
- [10. FAQ](#10-faq)

## 1. What the Test Had to Answer

A thermal warp test with a vague objective produces a vague dataset; if the only question is how much it warps, one room-temperature reading and one peak reading suffice. This run had four objectives.

Reproduce the evolution of warp through the ramp, a sequence rather than points; quantify out-of-plane displacement at each node; locate regions of concentrated deformation rather than a field average; and provide measured input for package thermal-matching analysis.

| Objective | Requirement | Effect on conditions |
| --- | --- | --- |
| Reproduce evolution | Continuous acquisition across the range | Dense nodes, not just endpoints |
| Quantify displacement | Full-field displacement data | Full-field 3D method |
| Locate concentration | Adequate spatial resolution | Whole wafer in frame, no cropping |
| Provide correlation input | Traceable data | Frame-temperature binding, complete metadata |

## 2. Specimen and Conditions

The specimens were 6-inch monocrystalline silicon wafers, 150 mm in diameter, 1 mm thick. Bare wafers rather than packaged parts came first so the substrate response under thermal load is seen with variables minimised.

The profile was stepped heating: start at 0℃, end at 150℃, one node every 10℃, 16 conditions labelled S0 to S15, each held until the specimen stabilised before a frame set was captured.

| Item | Setting |
| --- | --- |
| Specimen | 6-inch monocrystalline silicon wafer |
| Diameter | 150 mm |
| Thickness | 1 mm |
| Temperature range | 0℃ to 150℃ |
| Node spacing | 10℃ |
| Node count | 16 (S0–S15) |
| Heating | Stepped, hold at each node |
| Measurement | 3D DIC with thermal chamber |

## 3. Three Actions Before the First Frame

Most of the data quality is settled before the first frame.

**Speckle.** Silicon is a mirror; direct imaging gives a uniform bright field with nothing to match. A thin, dense pattern that neither cracks at 0℃ nor flows at 150℃ is needed, trialled on a spare wafer first.

**Support.** How the wafer sits defines its boundary condition. Light support minimised fixture constraint, because the target was the substrate's own response.

**Optical path and zero.** The stereo cameras image through a window, so refraction was calibrated first, and a reference plane was set per wafer with the initial shape as datum.

| Action | Consequence if wrong | Field criterion |
| --- | --- | --- |
| Speckle preparation | Mid-run decorrelation, broken curve | Good first-to-last frame match on a dry run |
| Support choice | Measuring combined fixture and specimen deformation | Stable repeatability unloaded |
| Refraction calibration | Systematic compression of edge topography | Explainable open-chamber difference |
| Zero establishment | Initial difference folded into thermal deformation | Good remount reproducibility |

## 4. Reading the Contours by Temperature Band

Split the sixteen nodes into four groups and the evolution becomes legible.

**S0–S3 (0–30℃).** Material still stiff, expansion small: the shape stays near the initial form with slight edge undulation. This is the baseline.

**S4–S7 (40–70℃).** Undulation grows and the centre-to-edge difference widens — the transition from near-flat to arched, and the interval where the onset is judged.

**S8–S11 (80–110℃).** Fastest growth: warp rises nearly linearly, contours densify, local bulges appear, and the shape is no longer coordinated.

**S12–S15 (120–150℃).** The maximum occurs around 120℃; afterwards the peak-to-valley spread stops growing and contracts slightly.

| Band | Nodes | Shape feature | Reading focus |
| --- | --- | --- | --- |
| 0–30℃ | S0–S3 | Near initial shape, slight edge undulation | Baseline band |
| 40–70℃ | S4–S7 | Centre-edge height difference grows | Onset of inflection |
| 80–110℃ | S8–S11 | Rapid growth, local bulges | Loss of deformation compatibility |
| 120–150℃ | S12–S15 | Peak then slight contraction | Non-monotonic, needs explanation |

Across all bands the shape is never a clean sphere: flat centre, strongest undulation in the middle annulus, converging rim. A mean says how much it warped, not where it warped worst.

## 5. The Main Curve from S0 to S15

Connecting the mean displacement across the sixteen nodes gives a non-monotonic curve.

It rises from S0 to S11 with a steeper slope after S8, peaks near S12 (120℃) at about 297 μm, then turns down below the peak by S15 (150℃).

| Node | Temperature | Mean out-of-plane displacement (vs S0) | Phase |
| --- | --- | --- | --- |
| S0 | 0℃ | Baseline | Start |
| S4 | 40℃ | Slow growth | Transition |
| S8 | 80℃ | Accelerating | Slope increases |
| S12 | 120℃ | About 297 μm | Peak of this run |
| S15 | 150℃ | Below peak | Decline |

Definition matters: 297 μm is the field mean, not the single-point maximum and not the peak-to-valley spread; the three cannot be interchanged.

## 6. Explaining the Decline

A turning curve invites suspicion of measurement error, which can be ruled out: measurement problems give jitter, jumps or dropouts, not a smooth decrease, and all sixteen nodes take part.

**Stress relaxation.** Above a certain temperature, dislocation activity rises and part of the elastic strain is absorbed plastically; warp held up elastically loses support and partially recovers.

**Material softening.** Moduli fall with temperature, the response to the same stress changes, interlayer constraint weakens and the structure relaxes.

**Non-linear CTE.** Expansion coefficients vary with temperature; where the expansion rate slows, the warp increment shrinks. When relaxation exceeds expansion, the result is a decline.

| Explanation | Mechanism | Verifiable signature |
| --- | --- | --- |
| Stress relaxation | Dislocation activity, plastic absorption of elastic strain | Hysteresis in the cooling leg |
| Material softening | Modulus drop, weaker constraint | Decline amplitude grows monotonically with temperature |
| Non-linear CTE | Expansion rate varies with temperature | Consistent with material property curves |

The three act together and are not mutually exclusive; separating them needs a cooling leg and a hysteresis loop. This run only heated, so the explanation stays qualitative.

## 7. Three Common Misreadings

**Average taken for the field.** 297 μm is a mean; a region at 400 μm and another at 200 μm still average 297, so judging on the mean alone misses the local failure point.

**Decline taken for failure.** Thermal warp is not monotonic and the decline carries physical meaning; discarding it throws away the most informative segment.

**Single-value process comparison.** 297 μm against 280 μm cannot be ranked directly — a uniform wafer may be safer than one with a local collapse.

| Misreading | Consequence | Correction |
| --- | --- | --- |
| Average for full field | Local high-risk zones missed | Report spread and location of maximum gradient |
| Decline as failure | Mechanism information lost | Explain via relaxation and softening, verify with cooling |
| Single value for process | Conclusion may reverse | Fix definition, attach shape type |

## 8. Where This Data Goes

**Package thermal matching.** The substrate's shape evolution from 0 to 150℃ is a boundary condition for stack design; knowing which band changes fastest indicates which way to adjust the process window.

**Simulation correlation.** A finite element curve needs a measured reference; sixteen nodes show where the model diverges most, whether in modulus or CTE.

**Material and process selection.** The same profile on other batches or thinning thicknesses makes evolution differences directly comparable.

**Failure analysis.** Comparing the warp history of a failed part with a good one often locates the anomalous band.

| Use | Input | Output |
| --- | --- | --- |
| Package thermal matching | Full-range shape sequence | Process window recommendation |
| Simulation correlation | Curve and contours | Direction for model parameter correction |
| Material selection | Multi-batch comparison | Batch consistency judgement |
| Failure analysis | Failed-part history | Anomalous temperature band |

## 9. What to Change Next Time

**Add a cooling leg.** The most important addition: heating alone reveals no hysteresis, and a symmetric cooling leg costs little while multiplying the information.

**Higher-resolution acquisition of the region of interest.** The full field covers the whole wafer but limits detail in bulges; a second configuration on the middle annulus would capture it.

**Log the fixture temperature.** Only chamber and near-specimen temperatures were recorded; fixture expansion is a major source of rigid-body motion, so logging it grounds the subtraction.

**Longer holds in the high-temperature band.** If the S13–S15 decline relates to relaxation, hold duration affects its amplitude; extending holds and watching the decline is a cheap test.

## 10. FAQ

**1. Why bare silicon rather than a packaged part?**

A bare wafer minimises variables. Warp in a stack results from several materials acting together, so measuring the substrate first separates what comes from silicon from what comes from stack mismatch.

**2. Can 297 μm be used as a standard?**

No. It is a measured result for this batch under this profile, tied to support method, ramp rate and batch, so it serves as a comparison baseline and simulation input.

**3. Are sixteen nodes dense enough?**

For 0–150℃, 10℃ spacing reveals inflections and slope changes adequately; refining to 5℃ near a candidate interval pins down the transition temperature.

**4. The decline is small. Can it be ignored?**

Better not. A small decline is not small information: it marks where stress relaxation begins, and reading it as continued elastic growth would misjudge the process window.

**5. Would the same test on another system give the same result?**

The order of magnitude should agree; the values will not. Differences come from support method, speckle quality, refraction calibration and temperature control, so comparability must be confirmed first.

</details>
