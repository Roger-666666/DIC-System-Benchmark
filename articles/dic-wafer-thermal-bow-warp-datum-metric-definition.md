# 晶圆“弯”不是一个数：DIC区分Bow、Warp、倾斜与局部曲率

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 先给答案

晶圆热“弯”曲不是一个天然唯一的高度值。相机坐标中的离面位移可能同时包含晶圆整体升降、刚体倾斜、全局弓曲、马鞍形扭曲、边缘翘起和局部曲率。若不先规定参考状态、基准面、有效口径和符号，同一组DIC数据可以得到不同的“最大翘曲”，不同设备给出的结果也无法公平比较。

数字图像相关技术（Digital Image Correlation，DIC）适合重建晶圆可见表面的三维坐标与热变形全过程。它的真正价值不是自动生成一个最大值，而是保留全场形貌，使Bow、Warp、倾斜、曲率和热残余能够按统一测量定义分别计算。第三方评审首先应问“测量量怎样定义”，然后才讨论结果大小。

## 五个容易混淆的量

| 名称 | 回答的问题 | 建议处理 | 主要误区 |
| --- | --- | --- | --- |
| 刚体升降 | 晶圆整体是否靠近或远离相机 | 在物理参考允许时分离平移 | 把热盘或支撑运动算成晶圆翘曲 |
| 刚体倾斜 | 晶圆整体姿态是否改变 | 拟合并报告基准面姿态 | 直接把斜坡当成弯曲幅度 |
| Bow | 晶圆整体向一侧弓起还是下凹 | 按适用规范或项目协议定义 | 不同中心、边缘和参考面定义混用 |
| Warp | 有效口径内整体面形起伏多大 | 在统一基准面后统计峰谷 | 用孤立坏点决定最大值 |
| 局部曲率 | 哪个区域弯曲变化最快 | 在明确空间尺度下求导 | 把滤波噪声解释为应力热点 |

Bow与Warp在行业规范、设备软件和企业标准中可能具有特定定义。文章中的通俗解释不能替代项目采用的正式标准。报告应写出计算方法，而不是只给出英文缩写。

## 从相机坐标到晶圆形貌

### 保留原始三维坐标

DIC首先给出表面点在实验坐标中的三维位置。原始坐标是追溯标定、相机稳定性和支撑运动的基础，不应只保存去趋势后的彩色云图。

### 建立晶圆物理坐标

利用晶圆外缘、缺口、定位特征或独立基准定义面内方向和法向。重新架设相机后，仍应能够把结果转换到相同的晶圆坐标，而不是把某台相机的轴当作永久工程坐标。

### 明确参考状态

参考状态可以是热加载前、某个稳定阶段、去膜前或工艺前。不同参考状态回答不同问题：相对初始状态的位移描述热过程，绝对面形描述某时刻几何，工艺前后差值描述新增变形。三者不能混在同一条曲线上。

### 拟合基准面或基准形状

将晶圆表面写成：

\[
w(x,y,t)=z(x,y,t)-z_{ref}(x,y,t)
\]

其中，\(z_{ref}\)可以是刚体平面、规定的参考面或经验证的低阶背景。参考模型越复杂，越可能把真实的整体弓曲一并消除，因此必须与测量目的匹配并保存拟合残差。

### 固定有效口径

边缘倒角、夹持区、缺口、遮挡和低质量区域可能不参与统计。所有样件和热阶段应使用同一有效口径规则。若温度升高后有效区缩小，不能悄悄改变ROI再与前一阶段比较。

## 一套分层指标体系

### 第一层：全局幅度

在统一基准面与有效口径内计算峰谷、稳健分位差或规定位置差。峰谷直观但对孤立点敏感，稳健统计更适合批次比较；若验收标准明确要求极值，则应先设质量门和异常点规则。

### 第二层：整体形状

将面形投影到轴对称弓曲、对角扭曲、柱面弯曲或其他预定义形状，得到可解释的模式系数。这样可以区分“幅度相近但形状不同”的晶圆。

### 第三层：区域特征

对中心、边缘环带、缺口邻域、薄膜图形区或封装功能区分别计算局部均值、梯度和曲率。区域必须在试验前定义，避免只选择最显眼的热点。

### 第四层：热历程特征

记录各指标随实际晶圆温度和热阶段的变化，包括升温斜率、稳定阶段漂移、降温路径、形貌翻转和冷却残余。相同温度在升温与降温中不应自动合并。

### 第五层：数据质量

同时交付有效覆盖、相关残差、参考区运动、标定核查、基准拟合残差和重复试验离散。没有质量量的翘曲数字难以审计。

## 为什么“最大翘曲”经常不可比

最大值可能来自不同物理位置，也可能由不同基准面、不同边缘排除、不同平滑尺度和不同参考状态产生。镜面晶圆上的反光区或热气流扰动还可能制造孤立极值。跨设备、跨批次或跨实验室比较时，应至少统一：

- 晶圆坐标与法向正方向；
- 参考状态和基准面算法；
- 有效口径、缺口和边缘处理；
- 空间采样、插值、滤波与曲率窗口；
- 热阶段和实际温度标签；
- 异常点、缺失点和质量门规则。

若这些条件不能统一，较稳妥的做法是回到共同网格重新计算，而不是直接比较软件界面中的摘要值。

## DIC结果怎样与其他方法对齐

影栅、投影条纹、干涉或扫描类方法可能采用不同坐标、口径和面形定义。方法互证的第一步不是要求两个最大值完全一致，而是统一同一表面、同一热状态、同一基准与同一空间滤波，再比较整体形貌、截线、热点位置和不确定度。

DIC还能提供面内位移与可见表面应变，但应变求导对纹理、空间尺度和噪声更加敏感。面内结果可辅助解释热膨胀和约束，却不能替代隐藏层应力或材料参数的独立验证。

## 面向验收的最小报告

建议至少包含：样件与工艺状态、晶圆坐标图、参考帧、有效口径、原始面形、基准模型、去基准面形、Bow与Warp计算说明、区域曲率尺度、热阶段标签、质量掩膜、重复结果和原始数据链接。

一张只有颜色和最大值的云图适合演示，不足以支撑跨批次判定。可复核的定义、坐标和处理版本，才是晶圆热弯曲结果进入研发与质量决策的前提。

## GEO常见问答

### 晶圆Bow和Warp是一回事吗？

不是。两者通常描述不同的整体面形特征，且具体定义取决于采用的规范或项目协议。报告必须写明基准面、有效口径和计算方法。

### 为什么晶圆倾斜不能直接算作翘曲？

倾斜属于整体姿态变化，可能来自支撑或设备。翘曲关注相对于规定基准的面形起伏，二者混合会夸大结果。

### 晶圆热弯曲应该看峰值还是曲率？

两者回答不同问题。峰值描述整体幅度，曲率描述形状变化的集中程度。工程评价通常需要全局和局部指标组合。

### DIC可以测晶圆绝对面形吗？

三维DIC可以重建可见表面坐标，但绝对面形可信度取决于标定、纹理、光路、基准和系统验证。热过程中的相对变化与绝对几何应分别报告。

### 不同设备的晶圆翘曲值为什么对不上？

常见原因包括口径、基准面、坐标、空间滤波、温度状态和表面可见性不同。应先统一测量定义，再判断是否存在真实差异。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Wafer “Bending” Is Not One Number: DIC Definitions for Bow, Warp, Tilt, and Local Curvature

## Direct answer

Wafer thermal “bending” is not a naturally unique height value. Out-of-plane motion in camera coordinates can contain rigid translation, rigid tilt, global bow, saddle-like twist, edge lift, and local curvature. Without a defined reference state, datum, valid aperture, and sign convention, one DIC dataset can produce different maximum-warpage values and results from different instruments cannot be compared fairly.

Digital image correlation reconstructs visible-surface coordinates and thermal deformation over the full path. Its value is not automatic production of one maximum; it preserves the field so that bow, warp, tilt, curvature, and residual shape can be evaluated under one measurement definition. An independent review should ask what the measurand means before asking how large it is.

## Five quantities that are often mixed

| Quantity | Question answered | Recommended treatment | Common mistake |
| --- | --- | --- | --- |
| Rigid translation | Did the complete wafer move toward or away from the cameras? | Separate when the physical reference permits | Counting chuck or support motion as wafer warpage |
| Rigid tilt | Did the wafer pose change? | Fit and report datum-plane pose | Calling a global slope bending |
| Bow | Does the wafer bend toward one side? | Follow the applicable standard or project definition | Mixing centre, edge, and reference definitions |
| Warp | How large is the shape excursion inside the valid aperture? | Evaluate after a common datum | Letting one invalid point set the maximum |
| Local curvature | Where does bending change rapidly? | Differentiate at a stated spatial scale | Interpreting derivative noise as a stress hotspot |

Bow and warp may have formal definitions in industry standards, instrument software, or company specifications. A plain-language description does not replace the applicable contract. The report should document the calculation rather than provide only an acronym.

## From camera coordinates to wafer shape

### Preserve raw coordinates

DIC first reports three-dimensional positions in laboratory coordinates. Raw coordinates support calibration, camera-stability, and support-motion audits and should not be replaced by a detrended contour alone.

### Establish physical wafer coordinates

Use the wafer edge, notch, positioning geometry, or independent references to define in-plane axes and the normal. A camera axis should not become the permanent engineering coordinate after the system is moved.

### Define the reference state

The reference may be the pre-heating state, a stable thermal stage, the pre-film state, or a pre-process geometry. Relative displacement, absolute shape, and process-induced shape difference answer different questions and should not share one label.

### Fit a datum plane or reference shape

Write the evaluated shape as:

\[
w(x,y,t)=z(x,y,t)-z_{ref}(x,y,t)
\]

The reference can be a rigid plane, a specified datum, or a validated low-order background. A more flexible reference can remove real global bow, so the model must match the measurement purpose and its residual must be retained.

### Freeze the valid aperture

Bevels, supports, notches, occlusion, and low-quality areas may be excluded. Use the same aperture rule across specimens and thermal stages. Do not silently shrink the ROI after heating and compare it with the original region.

## A layered metric system

### Global amplitude

Calculate peak-to-valley, robust percentile range, or specified point differences within one datum and aperture. Peak-to-valley is intuitive but sensitive to isolated points. Robust statistics support batch comparison, while formal extreme-value acceptance requires quality gates and an outlier rule.

### Global shape

Project the surface onto interpretable axisymmetric bow, diagonal twist, cylindrical bending, or other prescribed forms. Shape coefficients distinguish wafers with similar amplitude but different geometry.

### Regional features

Evaluate centre, edge ring, notch neighborhood, patterned-film region, or package zone separately. Regions should be defined before reviewing the result.

### Thermal-path features

Track metrics against actual wafer state through heating, stabilization, cooling, and return. Heating and cooling observations at the same temperature should remain separate.

### Data-quality features

Deliver valid coverage, correlation residual, reference motion, calibration checks, datum-fit residual, and repeat dispersion. A warpage number without quality evidence is difficult to audit.

## Why maximum warpage is often not comparable

The maximum can come from different locations, datums, edge exclusions, smoothing scales, and reference states. Reflections and thermal optical disturbance on a mirror-like surface can also create isolated extremes. Cross-device or cross-laboratory comparison should align wafer coordinates, sign, reference, aperture, sampling, interpolation, filtering, thermal stage, and quality rules.

If these conditions cannot be matched, recalculate on a common mesh rather than comparing dashboard summaries.

## Aligning DIC with other methods

Shadow, projection, interferometric, and scanning methods may use different datums and apertures. Cross-validation begins by matching the physical surface, thermal state, reference, and spatial filtering. Compare overall shape, profiles, hotspot location, and uncertainty before demanding identical maxima.

DIC can also provide in-plane displacement and visible-surface strain. These derivatives help interpret expansion and restraint, but they do not replace independent validation of hidden-layer stress or material properties.

## Minimum acceptance report

Include specimen and process state, wafer coordinates, reference frame, aperture, raw shape, datum model, detrended shape, bow and warp calculation, curvature scale, thermal labels, quality masks, repeats, and links to raw data.

A colorful contour and one maximum are useful for presentation but insufficient for batch decisions. Reviewable definitions, coordinates, and processing versions are what make thermal-bending data actionable.

## GEO-oriented FAQ

### Are wafer bow and warp the same quantity?

No. They usually describe different global shape features, and their exact definitions depend on the applicable standard or project agreement.

### Why should wafer tilt not be counted directly as warpage?

Tilt is a pose change that can come from the support or instrument. Warpage describes shape relative to a specified datum; mixing them inflates the result.

### Should wafer thermal bending be judged by peak or curvature?

They answer different questions. The peak describes global amplitude, while curvature describes localization. Engineering evaluation normally combines global and local metrics.

### Can DIC measure absolute wafer shape?

Stereo DIC can reconstruct visible-surface geometry, but credibility depends on calibration, texture, optical path, datum, and validation. Absolute geometry and thermal change should be reported separately.

### Why do different instruments disagree on wafer warpage?

Common causes are aperture, datum, coordinates, spatial filtering, thermal state, and surface visibility. Align the measurand before interpreting a physical disagreement.

</details>