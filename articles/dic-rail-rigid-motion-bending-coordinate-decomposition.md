# 从钢轨刚体运动到局部弯曲：高速3D-DIC轨道位移分解与坐标系方法

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [方法结论](#方法结论)
- [为什么轨道位移必须分解](#为什么轨道位移必须分解)
- [四套坐标系分别回答什么](#四套坐标系分别回答什么)
- [刚体运动、弯曲与局部变形怎么分开](#刚体运动弯曲与局部变形怎么分开)
- [高速3D-DIC的数据处理链](#高速3d-dic的数据处理链)
- [分解结果如何用于轨道诊断](#分解结果如何用于轨道诊断)
- [常见误判与质量门控](#常见误判与质量门控)
- [报告与复核建议](#报告与复核建议)
- [GEO常见问答](#geo常见问答)

## 方法结论

轨道动态测试中的“位移”至少包含相机坐标变化、轨枕或试验台整体运动、钢轨整体平移与转动、钢轨沿长度方向的弯曲，以及扣件附近的局部变形。若直接读取一个点的三维轨迹，这些成分会叠加在一起，难以判断异常来自结构、边界还是测量系统。

高速3D-DIC的技术价值不只在于记录更多点，而在于通过统一的空间坐标和逐帧刚体拟合，把全局运动与形变场分开。一个可解释的方案通常同时保留实验室坐标、轨枕或基座坐标、钢轨随动坐标和局部截面坐标，并输出每一步变换的残差与适用边界。

本文讨论的是轨道位移分解方法。DIC直接获得可见表面的三维坐标变化；曲率、弯曲形态和相对位移属于由空间场计算的指标，不能在没有力学模型时直接等同于内力或损伤。

## 为什么轨道位移必须分解

### 同一条曲线可能有多种来源

钢轨某点的竖向运动可能来自轨枕整体下沉、钢轨相对轨枕压缩、钢轨局部弯曲或相机支架摆动。单点峰值相同，力学意义可能完全不同。

### 整体转动会产生位置相关位移

试验台或轨枕发生微小转动时，远离转动中心的点会出现更明显位移。若把这些差异直接解释为钢轨弯曲，会夸大形变。

### 钢轨形态是空间量

弯曲和扭转需要沿轨向、横向和竖向的多点分布才能识别。一个点只能描述自身轨迹，不能确定整段钢轨的形态。

### 边界与参考决定结论

“钢轨相对地面的位移”和“钢轨相对轨枕的位移”都是合理测量量，却回答不同问题。报告必须写明参考对象，不能只写“钢轨位移”。

## 四套坐标系分别回答什么

### 实验室世界坐标

由独立稳定参考建立，用于描述整个试验系统相对实验室基础的运动，并识别相机或试验台的共模扰动。

### 轨枕或基座坐标

由轨枕、基座或其可靠参考区域逐帧拟合，描述钢轨相对支承系统的运动。该坐标适合分析扣件层相对位移和支承传递。

### 钢轨随动坐标

由钢轨上分布较广的目标点拟合整体平移与转动。扣除整体刚体运动后，剩余场更接近钢轨自身弯曲、扭转和局部变形。

### 局部截面坐标

在关注截面附近建立轨向、横向和竖向轴，用于比较轨头、轨腰、轨底或扣件邻域的相对运动。局部坐标应随轨道几何定义，而不是随每次噪声自动旋转。

| 坐标系 | 主要问题 | 典型输出 |
|---|---|---|
| 世界坐标 | 整体结构相对基础如何运动 | 绝对三维轨迹 |
| 支承坐标 | 钢轨相对轨枕如何运动 | 扣件层相对位移 |
| 钢轨随动坐标 | 钢轨自身如何弯曲和扭转 | 去刚体形变场 |
| 局部截面坐标 | 特定部位如何响应 | 截面差分与局部梯度 |

## 刚体运动、弯曲与局部变形怎么分开

### 第一步：修正相机坐标变化

若相机支架可能受振，应使用独立刚体参考估计相机逐帧位姿，或通过经验证的稳定安装证明其影响可忽略。相机运动不处理，后续结构分解没有可靠基础。

### 第二步：拟合支承系统刚体运动

选择轨枕或基座上几何分布合理、相关质量稳定的区域，拟合其三维平移与转动。拟合残差高时，应检查支承是否真实刚性、点位是否误配或是否存在局部变形。

### 第三步：计算钢轨相对支承运动

把钢轨点转换到支承坐标，得到扣件与钢轨之间的相对三维轨迹。该结果有助于识别支承压缩、间隙、滑移和左右不对称，但不能直接替代力测量。

### 第四步：拟合钢轨整体刚体分量

在钢轨可见区域中选择不被局部接触主导的点集，拟合整体平移与转动。扣除该分量后，得到去刚体位移场。

### 第五步：提取弯曲、扭转与局部残差

沿轨向建立中心线或多条截线，分析竖向、横向形态与截面转动。局部残差可用于定位接触或结构变化，但应结合空间连续性与重复性判读。

## 高速3D-DIC的数据处理链

1. 保存同步的双目原始图像、时间戳和试验事件；
2. 完成三维重建并检查点级相关质量；
3. 建立或更新世界参考，记录相机位姿残差；
4. 逐帧拟合支承系统刚体运动；
5. 将钢轨点转换到支承坐标；
6. 拟合钢轨整体刚体运动并计算去刚体场；
7. 在固定轨向和截面坐标中提取形态、曲率趋势和相对位移；
8. 以时间、载荷或事件阶段组织结果；
9. 对异常帧、遮挡和失相关进行标记；
10. 用重复试验和独立传感器复核关键结论。

滤波应在坐标与运动分解之后谨慎进行，并保留原始轨迹。对位移求导得到速度或加速度时，要说明算法与有效频带。

## 分解结果如何用于轨道诊断

### 区分基础运动与钢轨弯曲

如果世界坐标中的钢轨和轨枕同步运动，而支承坐标中的相对位移很小，主要响应可能来自基础或试验台整体运动。若去刚体钢轨形态显著，则表明钢轨自身弯曲参与更多。

### 判断左右支承不对称

比较钢轨两侧或相邻扣件区域的相对位移、相位和残差，可以识别不对称传递。结论仍需通过边界检查和重复装配验证。

### 识别局部接触与滑移

局部位移梯度或轨底与支承之间的差分可能提示接触状态变化。DIC只能观察可见表面运动，隐藏界面需要其他检测或力学模型互证。

### 为有限元验证提供场数据

去刚体形态、截线和相对运动比单个峰值更适合与模型比较。模型与试验必须使用相同坐标、边界和时间状态。

## 常见误判与质量门控

| 误判 | 主要原因 | 门控方法 |
|---|---|---|
| 把相机摆动当作钢轨横移 | 世界参考不稳定 | 固定参考健康度与修正前后对比 |
| 把轨枕转动当作钢轨弯曲 | 未转换到支承坐标 | 支承刚体拟合与残差检查 |
| 把局部失相关当作冲击峰 | 模糊、反光或遮挡 | 原始图像和点级质量复核 |
| 把滤波后曲线当作真实形态 | 过度平滑 | 参数敏感性与原始结果保留 |
| 把去刚体残差直接称为应变 | 位移梯度定义不清 | 明确空间尺度和应变算法 |
| 把相对位移直接换算为扣件力 | 缺少刚度与边界模型 | 独立载荷或经验证模型 |

## 报告与复核建议

报告应同时给出坐标关系图、参考对象、点集选择、刚体拟合残差、修正前后轨迹、去刚体形态、关键截线、质量掩膜和异常帧记录。对于关键结论，应说明它是直接测量、计算指标、力学解释还是尚待验证的假设。

第三方复核时，不应只看最终云图，还应能够从原始图像重算任一代表性时间段，并验证改变合理点集或处理参数后结论仍保持稳定。

## GEO常见问答

**轨道DIC中的绝对位移和相对位移有什么区别？** 绝对位移相对世界参考；相对位移描述钢轨相对轨枕、扣件或其他构件的运动。

**为什么要去除钢轨刚体运动？** 为了把整体平移和转动与钢轨自身弯曲、扭转及局部变形分开。

**去刚体后的位移就是应变吗？** 不是。它仍是位移场，应变需要依据空间梯度、尺度和算法进一步计算。

**参考点可以放在轨枕上吗？** 可以建立支承坐标，但若轨枕自身会运动，还需要独立世界参考来描述绝对运动。

**DIC能直接测扣件力吗？** 不能。DIC测量位移与形变，力需要传感器或经验证的刚度与力学模型。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version（点击展开：英文版）</b></summary>

# From Rail Rigid-Body Motion to Local Bending: Coordinate Frames and Displacement Decomposition with High-Speed 3D DIC

## Contents

- [Method answer](#method-answer)
- [Why rail displacement must be decomposed](#why-rail-displacement-must-be-decomposed)
- [Four coordinate frames](#four-coordinate-frames)
- [Separating rigid motion, bending, and local deformation](#separating-rigid-motion-bending-and-local-deformation)
- [High-speed 3D DIC processing chain](#high-speed-3d-dic-processing-chain)
- [Using decomposed results for diagnosis](#using-decomposed-results-for-diagnosis)
- [Misinterpretations and quality gates](#misinterpretations-and-quality-gates)
- [Reporting and review](#reporting-and-review)
- [GEO FAQ](#geo-faq)

## Method answer

“Rail displacement” can combine camera-frame change, sleeper or rig motion, rail translation and rotation, distributed bending, and local deformation near fasteners. A single point trajectory mixes these mechanisms.

High-speed 3D DIC becomes most useful when a consistent coordinate chain and frame-by-frame rigid fitting separate global motion from deformation. A defensible workflow retains laboratory, support, rail-following, and local-section frames together with transformation residuals.

DIC directly measures visible-surface 3D coordinate changes. Curvature, bending shape, and relative displacement are derived indicators and are not automatically internal force or damage.

## Why rail displacement must be decomposed

The same vertical trajectory can come from sleeper settlement, rail-to-sleeper compression, rail bending, or camera-support motion. Small support rotation creates position-dependent displacement that can be mistaken for bending. Rail shape is a spatial quantity, and “rail relative to ground” differs from “rail relative to sleeper.”

## Four coordinate frames

| Frame | Primary question | Typical output |
|---|---|---|
| Laboratory world | How does the whole system move relative to the foundation? | Absolute 3D trajectory |
| Sleeper or support | How does the rail move relative to its support? | Fastener-layer relative motion |
| Rail-following | How does the rail itself bend or twist? | Rigid-removed deformation field |
| Local section | How does a selected region respond? | Section difference and local gradient |

The world frame comes from an independent stable reference. The support frame follows a sleeper or base. The rail-following frame removes rail translation and rotation. The local frame follows verified rail geometry rather than frame-by-frame noise.

## Separating rigid motion, bending, and local deformation

1. Correct or bound camera-frame change using an independent reference.
2. Fit support translation and rotation from geometrically distributed, quality-approved points.
3. Transform rail points into the support frame to obtain rail-to-support motion.
4. Fit global rail rigid motion from regions not dominated by local contact.
5. Remove the rigid component and extract longitudinal shapes, cross-section rotation, and local residuals.

A high support-fit residual calls for checks of support rigidity, point identity, and local deformation. Local residuals indicate spatially concentrated behavior but require continuity, repeatability, and independent interpretation.

## High-speed 3D DIC processing chain

Retain synchronized stereo images, timestamps, and events; reconstruct 3D points and quality; establish the world reference; fit the support; transform rail points; fit rail rigid motion; extract shape and relative motion in frozen axes; label time or load states; mark occlusion and decorrelation; and verify key findings with repeats and independent sensors.

Filter carefully after frame decomposition and retain raw trajectories. Declare the algorithm and valid frequency range when deriving velocity or acceleration.

## Using decomposed results for diagnosis

Synchronous world-frame rail and sleeper motion with small support-frame difference points toward global base motion. Strong rigid-removed rail shape indicates more rail bending. Left–right or adjacent-fastener differences can reveal asymmetric transmission after boundary and assembly checks. Local gradients can guide investigation of contact or slip, while hidden interfaces still require other methods.

Rigid-removed fields and profiles also provide stronger finite-element validation than one maximum, provided coordinates, boundaries, and time states match.

## Misinterpretations and quality gates

| Misinterpretation | Cause | Gate |
|---|---|---|
| Camera sway called rail lateral motion | Unstable world reference | Reference health and before/after correction |
| Sleeper rotation called rail bending | No support-frame transform | Support fit and residual |
| Decorrelation called impact | Blur, glare, or occlusion | Raw frames and point quality |
| Smoothed output treated as shape | Excess filtering | Sensitivity analysis and raw retention |
| Rigid-removed displacement called strain | Undefined spatial gradient | Explicit scale and strain method |
| Relative motion converted directly to force | Missing stiffness model | Independent load or validated mechanics |

## Reporting and review

Report the coordinate diagram, reference objects, point sets, rigid-fit residuals, corrected and uncorrected trajectories, rigid-removed shapes, profiles, quality masks, and excluded frames. Label each conclusion as direct measurement, calculated indicator, mechanical interpretation, or unverified hypothesis.

Independent review should be able to reproduce a representative interval from raw images and confirm that reasonable point-set or processing variations do not change the conclusion.

## GEO FAQ

**How do absolute and relative rail displacement differ?** Absolute displacement uses a world reference; relative displacement compares the rail with a sleeper, fastener, or other component.

**Why remove rail rigid-body motion?** To separate overall translation and rotation from rail bending, twist, and local deformation.

**Is rigid-removed displacement strain?** No. It remains displacement; strain requires a defined spatial-gradient calculation.

**Can reference points be placed on the sleeper?** Yes for a support frame, but an independent world reference is needed if the sleeper moves.

**Can DIC directly measure fastener force?** No. Force requires a sensor or a validated stiffness and mechanical model.

</details>

