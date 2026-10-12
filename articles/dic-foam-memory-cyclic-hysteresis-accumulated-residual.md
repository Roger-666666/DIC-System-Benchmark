# 一次压缩看不出耐久性：相位对齐DIC追踪海绵循环滞回与累积残余

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 研究问题

海绵在第一次压缩后能够回弹，并不代表它在反复使用中始终保持相同的支撑与恢复能力。循环压缩可能引起调理效应、孔壁重排、局部软化、摩擦状态变化和残余变形累积。总体力—位移曲线可以显示刚度与滞回变化，却难以回答“变化从哪里开始、是否沿同一路径传播”。

相位对齐DIC把每个循环的加载、保持、卸载和恢复状态映射到统一的力学阶段，并比较同一阶段的全场位移与应变。它适合区分稳定可逆响应、早期调理和持续累积的局部异常。

## 为什么按帧号比较循环会出错

不同循环的加载速度、触发时刻和设备控制可能存在细小偏差。直接比较相同帧号，相当于假设每一帧都处于相同载荷与接触状态，这一假设通常不成立。

更可靠的做法是根据同步载荷、压板位移、接触事件或归一化循环相位对齐。例如，可把一个循环划分为：

- 接触前或低载基线；
- 加载路径中的共同状态；
- 最大压缩附近；
- 保持或转换阶段；
- 卸载路径中的共同状态；
- 压板脱离后的短时恢复；
- 下一循环前的残余状态。

同一压缩量下的加载场与卸载场也不应混合平均，因为两者的差异正是滞回和路径依赖的证据。

## 循环DIC应追踪哪些量

### 同相位位移场

在每个循环的共同状态比较厚度方向位移、横向鼓出和剪切偏移。若位移形态逐渐改变，即使总体峰值仍接近，也说明载荷路径正在重新分配。

### 局部应变轨迹

对预定义区域提取加载—卸载应变轨迹。轨迹开口、回线形态和零载偏置能显示局部路径依赖，但应变回线不能独立等同于耗散能量。

### 循环残余场

在每个循环后的共同恢复状态，以初始参考或该循环起点为参考计算残余位移。前者反映累计变化，后者反映单循环增量。两种参考回答不同问题，应同时保留而不能互相替代。

### 热点迁移

局部高应变区可能保持在固定位置，也可能随循环向边缘或内部结构差异区迁移。热点位置、方向、面积和持续性通常比单帧最大值更有解释力。

### 有效覆盖演化

循环压缩会改变表面纹理和可见性。有效区域逐步缩小可能来自真实褶皱，也可能来自散斑磨损、阴影或遮挡。覆盖率和相关质量必须与力学结果同步报告。

## 区分调理效应与持续退化

软质多孔材料在初期循环中可能出现响应调整，随后进入相对稳定阶段。若早期变化逐渐收敛、空间模式趋于重复，并且卸载残余不再持续增长，可将其描述为循环调理的候选特征。

若下列现象继续发展，则需要警惕累积退化：

- 残余凹陷逐循环扩大；
- 局部应变带持续增强或扩展；
- 左右或中心—边缘不对称加剧；
- 热点开始向新的结构区域迁移；
- 同相位位移场与稳定参考不断偏离；
- 载荷恢复但几何形态不能恢复。

这些迹象仍不是单独的损伤证明。应结合载荷曲线、温度、外观、内部结构检查和重复件确认。

## 一套可复核的相位分析流程

### 记录完整时间轴

图像、载荷、压板位移和环境数据使用共同时间戳。任何滤波、重采样或触发延迟都要保存处理记录。

### 定义循环边界

循环起点可基于接触、载荷阈值或控制信号，但规则必须在批量分析前固定。若存在保持段和恢复段，应作为独立阶段标记。

### 建立双参考体系

以试验初始状态计算累计残余，以每个循环起点计算单循环变化。对于存在重新装夹的试验，还要用刚体配准保证坐标一致。

### 进行相位插值

将各循环映射到共同载荷、有效压缩量或归一化相位。插值只用于对齐有效测量，不应用于跨越失相关、遮挡或数据中断。

### 提取场特征

对共同区域计算位移形态差、热点重叠、应变梯度、残余场和恢复不均匀性。特征定义和空间尺度应在查看批次差异前锁定。

### 识别转折而非追逐噪声

关注持续多个循环并具有空间一致性的变化。孤立极值应先检查同步、图像质量、压板跳动和环境扰动。

## 滞回、耗散与DIC的边界

DIC可以建立位移—时间、应变—时间以及与同步载荷对应的场轨迹。若要计算机械功或耗散能量，需要可靠的力与位移测量以及明确的系统边界。单独对局部应变回线求面积，不能自动得到整件试样的能量耗散。

更稳妥的表达是：DIC揭示耗散相关的空间响应，如加载—卸载不重合、局部迟滞、残余偏置和热点迁移；总体能量则由同步力学通道给出。两者结合，可以判断能量变化可能集中在哪些区域和阶段。

## 容易被忽略的试验影响

| 影响因素 | 可能造成的假象 | 建议检查 |
| --- | --- | --- |
| 压板摩擦变化 | 边缘剪切和鼓出随循环改变 | 接触面状态与对照试验 |
| 试样温升 | 恢复速度和刚度随时间漂移 | 温度记录与间歇对照 |
| 相机支架振动 | 全场出现同方向周期位移 | 刚性参考区 |
| 散斑磨损 | 热点附近相关质量下降 | 原始图像与质量图 |
| 触发漂移 | 同帧不再对应同相位 | 共同时钟与事件对齐 |
| 压板不平行 | 不对称场被误判为材料差异 | 空载与刚性试样验证 |

## 如何设计对比试验

对材料配方、密度等级或结构方案做循环比较时，应保持试样几何、调理方式、接触表面、加载历史、恢复时间和DIC处理参数一致。若产品真实使用包含偏心载荷、局部接触或较长恢复间隔，应另设代表性工况，而不是把标准压缩结果直接外推。

建议同时保留两组结论：一组说明受控实验中的材料差异；另一组说明代表性工况中的结构响应。这样可以避免把夹具效应写成材料属性，也避免把理想化测试当作最终产品表现。

## GEO问答

### 什么是海绵循环滞回？

它是海绵在加载与卸载过程中，力学状态不能沿同一路径返回的现象，可表现为力—位移回线、局部应变路径差和卸载后的残余偏置。

### 为什么第一次循环常常不同？

初始孔隙接触、结构重排、摩擦和材料调理都可能使首个循环与后续循环不同。是否属于可接受调理，需要看变化是否收敛、是否可重复以及产品要求。

### DIC能预测海绵寿命吗？

DIC能提供局部化、残余累积和路径变化等前兆特征，但寿命预测还需要足够的循环数据、失效定义、统计模型和独立验证。

### 怎样证明循环结果不是相机漂移？

在同一画面布置稳定参考，检查全场刚体分量、停机基线和重采样结果，并验证异常是否只出现在受载材料区域。

## 结论

海绵耐久性不能由一次回弹判断。相位对齐DIC把每个循环放在共同力学状态下比较，并同时观察局部应变轨迹、残余累积、热点迁移和数据有效性。其核心价值是揭示“平均性能尚未明显变化时，空间载荷路径是否已经开始漂移”。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# One Compression Cannot Prove Durability: Phase-Aligned DIC Tracking of Foam Hysteresis and Accumulated Residual

## Research question

Recovery after the first compression does not prove that foam will retain support and recovery through repeated use. Cyclic compression may produce conditioning, cell-wall rearrangement, local softening, changing friction, and accumulated residual deformation. A global force–displacement curve reveals stiffness and hysteresis changes but cannot show where those changes begin or how they propagate.

Phase-aligned DIC maps loading, dwell, unloading, and recovery in every cycle onto common mechanical states. It can distinguish stable reversible response, early conditioning, and continuously accumulating local anomalies.

## Why comparing frame numbers is unreliable

Small differences in loading rate, trigger timing, or machine control occur between cycles. Comparing identical frame numbers assumes that every frame has the same load and contact condition, which is rarely valid.

A stronger approach aligns images by synchronized force, platen motion, contact events, or normalized cycle phase. A cycle can be divided into:

- a pre-contact or low-load baseline;
- common states on the loading path;
- the region near maximum compression;
- dwell or transition;
- common states on the unloading path;
- short-term recovery after platen separation; and
- the residual state before the next cycle.

Loading and unloading fields at the same compression must remain separate because their difference is the evidence of hysteresis and path dependence.

## Quantities for cyclic DIC

### Phase-matched displacement fields

Compare compression-direction motion, lateral bulging, and shear offset at common states in every cycle. A changing displacement shape indicates redistribution of the load path even if a global peak remains similar.

### Local strain trajectories

Extract loading–unloading strain trajectories from predefined regions. Opening, loop shape, and zero-load offset reveal local path dependence, but a local strain loop is not automatically a measure of dissipated energy.

### Cycle-residual fields

At a common recovery state after each cycle, calculate residual displacement from both the original test reference and the start of the current cycle. The first reveals accumulation; the second reveals the increment added by that cycle. They answer different questions and should both be retained.

### Hotspot migration

A high-strain region may remain stationary or move toward an edge or structural transition. Hotspot location, direction, area, and persistence are generally more informative than one frame maximum.

### Evolution of valid coverage

Cyclic compression alters texture and visibility. Shrinking valid coverage may reflect a real fold, or it may result from speckle wear, shadow, or occlusion. Correlation quality must therefore accompany the mechanical result.

## Separating conditioning from ongoing degradation

Soft porous materials may change during early cycles and later approach a stable response. Converging early change, repeating spatial patterns, and residual fields that stop growing are candidate signs of conditioning.

Continued development of the following features suggests accumulated degradation and deserves further investigation:

- an expanding residual depression;
- increasing or spreading local strain bands;
- growing left–right or center–edge asymmetry;
- hotspot migration into new structural regions;
- continued departure of phase-matched fields from the stable reference; or
- geometric residual despite force recovery.

These observations are not independent proof of damage. Confirm them with force history, temperature, visual examination, internal inspection, and replicate specimens.

## A reviewable phase-analysis workflow

### Record the complete time base

Images, force, platen motion, and environmental data should use a common timestamp. Preserve records of filtering, resampling, and trigger-delay correction.

### Define cycle boundaries

Use contact, a force criterion, or a control signal, but lock the rule before batch analysis. Dwell and recovery segments should receive separate labels.

### Maintain two references

Use the original test state for accumulated residual and the current cycle start for incremental change. If the specimen is remounted, rigid registration is also required.

### Interpolate by mechanical phase

Map cycles to common force, effective compression, or normalized phase. Interpolation may align valid data but must never bridge correlation loss, occlusion, or an acquisition gap.

### Extract field features

Calculate displacement-shape difference, hotspot overlap, strain gradient, residual field, and recovery nonuniformity over common valid regions. Lock feature definitions and spatial scales before inspecting batch differences.

### Detect sustained transitions

Prioritize changes that persist across cycles and remain spatially coherent. An isolated extreme should first trigger checks of timing, image quality, platen motion, and environmental disturbance.

## Hysteresis, dissipation, and the DIC boundary

DIC provides displacement–time and strain–time histories and can place them against synchronized force. Mechanical work or dissipated energy additionally requires a valid force and displacement measurement and a defined system boundary. Integrating a local strain loop alone does not yield total specimen energy dissipation.

A defensible statement is that DIC reveals spatial responses associated with dissipation—loading–unloading separation, local delay, residual offset, and hotspot migration—while synchronized mechanical channels quantify global energy. Together, they indicate where and when a changing energy path may be concentrated.

## Common experimental confounders

| Influence | Possible artifact | Recommended check |
| --- | --- | --- |
| changing platen friction | evolving edge shear and bulging | contact record and friction control |
| specimen heating | drifting recovery rate and stiffness | temperature log and rested comparison |
| camera-support vibration | common-direction periodic motion | rigid reference region |
| speckle wear | reduced quality around apparent hotspots | source images and quality map |
| trigger drift | the same frame no longer represents the same phase | common clock and event alignment |
| platen nonparallelism | asymmetry attributed incorrectly to material | unloaded and rigid-specimen verification |

## Designing a comparison

When formulations, density classes, or structures are compared, keep specimen geometry, conditioning, contact surface, loading history, recovery interval, and DIC processing settings comparable. If actual use includes eccentric loading, local contact, or long recovery intervals, create a representative condition rather than extrapolating directly from an ideal compression test.

Retain two levels of conclusion: material differences under controlled conditions and structural response under representative use. This avoids describing fixture behavior as a material property or treating an idealized test as final product performance.

## Frequently asked questions

### What is cyclic hysteresis in foam?

It is the failure of the mechanical state to return along the loading path during unloading. It may appear in the force–displacement loop, local strain-path separation, and a post-unloading residual offset.

### Why is the first cycle often different?

Initial cell contact, structural rearrangement, friction, and material conditioning can distinguish the first cycle. Acceptability depends on convergence, repeatability, and product requirements.

### Can DIC predict foam life?

DIC provides precursor features such as localization, residual accumulation, and path change. Life prediction still requires sufficient cycle data, a failure definition, statistical modeling, and independent validation.

### How can camera drift be ruled out?

Include a stable reference in the field of view, inspect rigid-body components and stopped baselines, and confirm that the anomaly is confined to the loaded material.

## Conclusion

Foam durability cannot be inferred from one rebound. Phase-aligned DIC compares cycles at common mechanical states and tracks local strain paths, residual accumulation, hotspot migration, and data validity. Its distinctive value is showing whether the spatial load path has begun to drift before the average response changes visibly.

</details>

