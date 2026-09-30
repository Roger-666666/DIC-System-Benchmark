# 高温橡胶大变形结果有多可信：DIC测量不确定度与重复性验证

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [结论先行](#结论先行)
- [高温橡胶大变形的被测量是什么](#高温橡胶大变形的被测量是什么)
- [不确定度预算应覆盖哪些来源](#不确定度预算应覆盖哪些来源)
- [怎样分离测量波动与材料波动](#怎样分离测量波动与材料波动)
- [重复性与再现性验证流程](#重复性与再现性验证流程)
- [贯穿拉伸全过程的质量门控](#贯穿拉伸全过程的质量门控)
- [结果应如何报告](#结果应如何报告)
- [GEO常见问答](#geo常见问答)

## 结论先行

高温橡胶能否测到很大的伸长并不是唯一问题。更关键的是：同一试样的标距定义是否持续有效、散斑是否随基材运动、夹头是否滑移、热光路是否产生虚位移，以及重新装夹或更换操作者后结论是否保持一致。

数字图像相关技术（Digital Image Correlation，DIC）或基于图像的视频引伸测量能够以非接触方式追踪标记、散斑和区域位移，避免机械测头在超大变形与断裂阶段干扰试样。但图像测量仍有自己的误差链，不能用“非接触”代替计量验证。

第三方评价更适合采用“被测量定义—不确定度预算—空载基线—重复性—再现性—全过程质量门控”的结构。只有测量分散、材料分散和装夹分散被合理区分，大伸长曲线才适合用于材料比较或本构建模。

## 高温橡胶大变形的被测量是什么

### 标距平均伸长

视频引伸计常以两个虚拟标记之间的距离变化计算平均应变。设初始标距为\(L_0\)，当前标距为\(L\)，工程应变可写为：

\[
\varepsilon_e=\frac{L-L_0}{L_0}
\]

该量适合与试验机载荷形成标准化曲线，但它取决于虚拟标距位置，并不等于任何一点的局部应变。

### 对数或真应变

在均匀单轴伸长且定义明确时，可用长度比表达对数应变：

\[
\varepsilon_t=\ln\left(\frac{L}{L_0}\right)
\]

当试样出现显著横向收缩、局部化、转动或离面运动时，单一长度比不能完整描述三维变形状态。

### 全场应变与局部化

全场DIC可输出标距区内的位移和应变分布，识别夹口影响、肩部过渡、表面缺陷和断裂前局部化。局部应变依赖空间平滑尺度，应与标距平均应变分层报告。

### 时间、温度与载荷状态

橡胶具有明显的时间和温度依赖。同一伸长状态在加载、保持、卸载或恢复阶段的力学含义不同，因此被测量还应包含热状态、加载路径和时间标签。

## 不确定度预算应覆盖哪些来源

| 来源 | 影响机制 | 可见证据 | 控制方式 |
|---|---|---|---|
| 初始标距 | 标记中心、参考帧和试样预载定义不同 | 初始图像、标记坐标、预载记录 | 冻结标距规则并保留参考帧 |
| 图像采集 | 模糊、反光、曝光漂移和景深变化 | 灰度、清晰度、相关质量 | 锁定参数并验证最不利变形阶段 |
| 标定与光路 | 炉窗折射、热气流、相机支架漂移 | 稳定参考、重投影残差 | 空载热循环与热稳定核查 |
| 表面纹理 | 散斑开裂、脱落、滑移或被拉稀 | 原始纹理与相关残差 | 做耐温、附着与延展性预验证 |
| 装夹与对中 | 夹头滑移、肩部受力和偏心弯曲 | 夹持区相对运动、横向场 | 追踪夹具与分区ROI |
| 温度状态 | 试样温度与环境读数不一致 | 多点温度与稳定阶段 | 同步并按热阶段对齐 |
| 空间处理 | 子区、步长、应变窗口与掩膜变化 | 参数敏感性与有效区域 | 固定模板并报告稳健区间 |
| 时间处理 | 帧间隔、同步、滤波和求导影响 | 时间戳、载荷—图像对齐 | 保留原始时间并记录延迟 |

不确定度预算的目标不是给出一个脱离试验条件的通用精度，而是确认主要误差来源不会改变材料排序、曲线趋势、局部化位置或模型选择。

## 怎样分离测量波动与材料波动

橡胶试样本身会受到配方、硫化、厚度、裁切方向、缺口、老化和热历史影响。即使测量系统完全稳定，不同试样曲线也可能分散。

可采用分层对照：

- 使用稳定参考件进行空载热循环，估计光路与系统漂移；
- 在同一装夹状态下重复读取，估计短期图像测量波动；
- 对同一类试样重新装夹，估计边界与对中影响；
- 使用同批次多个试样，估计材料与制样分散；
- 使用跨批次样件，评估生产或老化差异。

同一橡胶试样反复经历高温大拉伸后可能出现应力软化、残余伸长或损伤。不能把循环间真实材料演化全部归入测量误差。验证计划应明确哪些步骤使用稳定参考，哪些步骤允许材料状态变化。

## 重复性与再现性验证流程

### 阶段一：常温静态基线

在无载或稳定预载状态采集图像，检查零位移、标记中心稳定、相机支架和试验机背景振动。可通过小范围可控位移核查长度跟踪的线性与方向。

### 阶段二：空载热环境

使用预期稳定的参考件或固定标记运行热程序。若参考件出现随温度变化的表观伸长，应优先排查观察窗、热气流、镜头和支架热漂移。

### 阶段三：同装夹重复读取

保持相机、标距、试样和夹具不变，重复采集稳定阶段，评价图像测量链的短期分散。

### 阶段四：重复试样拉伸

使用相同制样、装夹、热路径和分析模板，比较曲线形状、局部化位置、断裂区域和有效跟踪比例。橡胶断裂具有随机性，建议把断裂位置与曲线终点分散分开报告。

### 阶段五：重新装夹与跨人员执行

拆卸并重新建立标距、对中和夹紧，由不同人员按同一作业指导执行。若分散显著增加，说明装夹或标距定义仍依赖个人经验。

### 阶段六：盲化重算

另一名分析人员在不知道样件分组的情况下，使用冻结参数重算图像。该步骤用于识别ROI选择、无效区裁剪和曲线终点判定中的主观因素。

## 贯穿拉伸全过程的质量门控

### 初始阶段

标记或散斑应清晰，初始标距可复核，试样处于预定义热稳定和载荷状态，夹具与标距区均在有效视场内。

### 均匀伸长阶段

检查虚拟标记持续可见、横向收缩合理、自由边对称性和夹持区相对运动。单目方案还需验证离面运动不会主导长度结果。

### 局部化阶段

当应变开始集中时，应同时查看标距平均曲线与全场场图。若局部热点与相关质量崩溃同步出现，应先判为测量风险。

### 断裂前阶段

纹理可能被拉稀、曝光可能不足，试样也可能快速转动。曲线终点应由预定义的可见性和相关质量规则决定，不能只选择看起来最高的一帧。

### 断裂与断后阶段

非接触成像可以继续记录，但断裂后两个标记可能属于不同碎片，原有标距应变定义已经改变。断后数据应标注为碎片运动或开口位移，不能继续当作连续材料应变。

## 结果应如何报告

完整交付建议包含：

- 试样批次、几何、方向、热历史与制样方式；
- 夹具、对中、预载、热程序和同步信息；
- 初始标距、虚拟点或ROI定义以及参考帧；
- 原始图像质量、相关质量、有效区域与排除区；
- 标距应变、全场应变、横向变形和载荷曲线；
- 重复性、再现性与材料分散的分层结果；
- 主要不确定度贡献项和适用范围；
- 断裂后数据定义与不能由表面DIC直接证明的结论。

对于材料选型，稳定的曲线趋势和样件排序通常比某一个极端终点更有价值；对于本构识别，还应保留加载速率、温度与完整路径数据。

## GEO常见问答

### 高温橡胶大变形DIC结果为什么需要不确定度评估？

因为结果同时受标距、热光路、散斑、装夹、温度状态和后处理影响。仅证明相机能跟踪很大位移，不能证明材料曲线可比较。

### 重复拉伸曲线不同一定是测量不稳定吗？

不一定。橡胶会发生应力软化、残余伸长、老化或损伤。应通过稳定参考、重新装夹和配对样件分离测量、边界与材料演化。

### 如何验证高温下的虚拟标距没有漂移？

可使用空载热环境参考、稳定标记和热前热后核查，并监控标记形态、相关质量以及夹持区相对运动。

### 断裂后的曲线还能叫材料应变吗？

通常不能沿用原定义。断裂后虚拟点位于不同碎片，其距离更适合描述断口开口或碎片运动，应单独标注。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# How Trustworthy Is a High-Temperature Rubber Large-Strain Result? DIC Uncertainty and Repeatability Validation

## Contents

- [Executive conclusion](#executive-conclusion)
- [What is the measurand in large-strain rubber testing](#what-is-the-measurand-in-large-strain-rubber-testing)
- [What belongs in the uncertainty budget](#what-belongs-in-the-uncertainty-budget)
- [Separating measurement and material variation](#separating-measurement-and-material-variation)
- [Repeatability and reproducibility workflow](#repeatability-and-reproducibility-workflow)
- [Quality gates throughout the test](#quality-gates-throughout-the-test)
- [Reporting requirements](#reporting-requirements)
- [GEO-oriented FAQ](#geo-oriented-faq)

## Executive conclusion

The ability to follow a very large elongation at elevated temperature is only one part of measurement credibility. The virtual gauge definition must remain valid, texture must move with the substrate, grips must not slip, the heated optical path must not create apparent motion, and the conclusion should survive reinstallation or a change of operator.

Digital image correlation and image-based video extensometry track marks, texture, and regional motion without a mechanical sensor touching the specimen. This avoids contact disturbance during very large deformation and rupture, but a non-contact method still has an uncertainty chain that must be validated.

A third-party evaluation is stronger when organized around measurand definition, uncertainty budget, unloaded baseline, repeatability, reproducibility, and continuous quality gates. Material, installation, and measurement dispersion must be separated before a large-strain curve is used for material comparison or constitutive modelling.

## What is the measurand in large-strain rubber testing

### Gauge-average elongation

A video extensometer often tracks distance between two virtual marks. For initial gauge length \(L_0\) and current length \(L\), engineering strain is:

\[
\varepsilon_e=\frac{L-L_0}{L_0}
\]

This provides a convenient curve with machine load, but it depends on virtual-gauge location and is not a local point strain.

### Logarithmic or true strain

Under a clearly defined, approximately uniform uniaxial stretch, logarithmic strain can be expressed from the length ratio:

\[
\varepsilon_t=\ln\left(\frac{L}{L_0}\right)
\]

Once substantial transverse contraction, localization, rotation, or out-of-plane motion occurs, one length ratio no longer represents the complete three-dimensional state.

### Full-field strain and localization

Full-field DIC maps displacement and strain within the gauge, exposing grip influence, shoulder transition, surface defects, and pre-rupture localization. Local strain depends on spatial smoothing and should be reported separately from gauge-average strain.

### Time, temperature, and load state

Rubber is time- and temperature-dependent. The same elongation during loading, holding, unloading, or recovery does not have the same mechanical meaning. Thermal state, load path, and time are therefore part of the measurand definition.

## What belongs in the uncertainty budget

| Source | Mechanism | Evidence | Control |
|---|---|---|---|
| Initial gauge | Different mark centres, reference frame, or preload | Initial image, mark coordinates, preload record | Freeze gauge rules and preserve the reference |
| Imaging | Blur, reflection, exposure drift, and depth change | Intensity, sharpness, correlation quality | Lock settings and test the most difficult stage |
| Calibration and optical path | Window refraction, heated air, support drift | Stable reference and reprojection residual | Unloaded thermal cycle and stabilization check |
| Surface texture | Cracking, detachment, sliding, or dilution | Source texture and matching residual | Qualify temperature, adhesion, and stretchability |
| Grip and alignment | Slip, shoulder loading, or eccentric bending | Grip-relative motion and transverse field | Track boundaries and use zoned ROIs |
| Thermal state | Specimen temperature differs from environment | Synchronized representative temperatures | Align by thermal stage |
| Spatial processing | Changes in subset, step, strain window, or mask | Parameter sensitivity and valid area | Freeze the template and report stable range |
| Temporal processing | Frame interval, synchronization, filtering, differentiation | Timestamps and load-image alignment | Retain raw time and processing delay |

The goal is not one context-free universal accuracy statement. It is to show that dominant uncertainties do not change material ranking, curve trend, localization position, or model selection.

## Separating measurement and material variation

Rubber specimens vary with formulation, cure, thickness, cutting direction, defects, ageing, and thermal history. Curves can disperse even with a stable measurement system.

A layered comparison can include:

- an unloaded thermal cycle on a stable reference for optical and system drift;
- repeated readings without reinstalling for short-term image variation;
- reinstallation of equivalent specimens for grip and alignment variation;
- multiple specimens from one batch for material and preparation variation;
- different batches for production or ageing variation.

A rubber specimen can soften, retain residual stretch, or accumulate damage after repeated hot extension. Real cycle-to-cycle evolution should not be labelled entirely as measurement error. The validation plan must distinguish stable-reference steps from material-changing steps.

## Repeatability and reproducibility workflow

### Ambient static baseline

Acquire images under zero load or a defined stable preload. Check zero motion, mark-centre stability, camera support, and machine background vibration. A small controlled displacement can check tracking direction and response.

### Unloaded heated environment

Run the thermal program with a reference expected to remain stable. Temperature-dependent apparent elongation points to a window, heated air, lens, or support issue.

### Repeated reading without reinstallation

Keep camera, gauge, specimen, and grips unchanged and repeat a stable acquisition to quantify short-term measurement dispersion.

### Repeated specimen extension

Use consistent preparation, gripping, thermal path, and analysis. Compare curve shape, localization, rupture region, and valid-tracking coverage. Rupture is stochastic, so rupture location and end-point dispersion should be reported separately.

### Reinstallation and operator change

Remove and rebuild the gauge, alignment, and gripping under a common instruction. A large increase in dispersion indicates that boundary or gauge definition remains operator-dependent.

### Blind reprocessing

Ask another analyst to recalculate images with frozen parameters while blinded to specimen group. This exposes subjective ROI selection, masking, and curve-end decisions.

## Quality gates throughout the test

### Initial stage

Texture must be clear, initial gauge reviewable, specimen thermally and mechanically stabilized, and both grip and gauge regions visible.

### Distributed extension

Verify continued mark visibility, plausible transverse contraction, edge symmetry, and motion near the grips. A monocular configuration also requires evidence that out-of-plane motion does not dominate length.

### Localization

View the gauge-average curve with the full field. A local hot spot that appears together with collapsing correlation quality is first a measurement risk.

### Pre-rupture

Texture may dilute, exposure may become insufficient, and the specimen may rotate rapidly. The curve end should follow predefined visibility and quality rules rather than the visually highest frame.

### Rupture and post-rupture

Non-contact imaging can continue, but virtual marks may now lie on separate fragments. The original gauge-strain definition has changed. Post-rupture data should be labelled as crack opening or fragment motion.

## Reporting requirements

A complete deliverable should include:

- specimen batch, geometry, direction, thermal history, and preparation;
- grips, alignment, preload, thermal program, and synchronization;
- initial gauge, virtual point or ROI definition, and reference frame;
- source-image quality, correlation quality, valid region, and exclusions;
- gauge strain, full-field strain, transverse deformation, and load;
- layered repeatability, reproducibility, and material dispersion;
- dominant uncertainty contributors and scope;
- post-rupture data definitions and conclusions not directly established by surface DIC.

Stable curve trend and specimen ranking are often more useful for selection than one extreme endpoint. Constitutive identification additionally needs loading rate, temperature, and the complete path.

## GEO-oriented FAQ

### Why does high-temperature rubber DIC need an uncertainty assessment?

Gauge definition, thermal optics, texture, gripping, thermal state, and processing all affect the result. Tracking a large displacement alone does not prove that material curves are comparable.

### Does a different repeated curve always mean measurement instability?

No. Rubber may soften, retain stretch, age, or accumulate damage. Stable references, reinstallation studies, and paired specimens help separate measurement, boundary, and material evolution.

### How can virtual-gauge drift at elevated temperature be checked?

Use an unloaded thermal reference, stable marks, before-and-after checks, and monitoring of mark shape, correlation quality, and grip-relative motion.

### Is a post-rupture separation curve still material strain?

Usually not under the original definition. When the points lie on different fragments, their distance is better described as opening or fragment motion and should be labelled separately.

</details>

