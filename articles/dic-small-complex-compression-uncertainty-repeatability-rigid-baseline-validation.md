# 微小变形结果有多可信：小尺寸压缩DIC不确定度、重复性与刚体基线验证

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

小尺寸复杂结构压缩测试的可信度，不能用软件显示的一个“精度”数值概括。成像噪声、标定、纹理、工作距离、刚体运动、离面位移、温度、同步、空间平滑和试样离散都会进入最终结果。可靠验证应把测量重复性、试验重复性和试样重复性分开，并通过静态基线、刚体运动、已知相对位移和重复压缩逐层检查。

不确定度评价的目标不是给每张云图附一个统一误差，而是判断关键结论是否高于噪声、是否对合理处理参数稳定、是否能在重复试验中复现，以及异常是否可能由测量链解释。

## 三种“重复”不能混为一谈

### 测量重复性

同一试样、同一装夹和同一状态下重复采图与处理，评价相机、光照、相关算法和时间稳定性。

### 试验重复性

同一试样在可恢复或低载条件下重复加载，包含加载控制、接触就位、夹具和同步的影响。

### 试样重复性

不同试样按同一流程测试，包含制造尺寸、孔隙、表面、材料和装夹重建的离散。

如果直接把不同试样的差异全部称为测量误差，就无法判断系统是否稳定，也无法评价结构真实散布。

## 建立验证阶梯

### 静态图像基线

在试样和设备不动时连续采集，使用正式参数计算位移与应变散布。静态基线揭示图像噪声、照明波动和处理参数影响，但不包含运动与重新定位误差。

### 刚体平移与倾转

让具有稳定纹理的目标做可控面内平移、离面移动或小角度倾转。理想刚体表面不应产生真实应变，因此残余场可用于检查透视、标定和二维假设。

### 已知相对位移

使用稳定点距、位移台或可追溯结构产生相对运动，验证虚拟标距、方向投影和比例关系。应覆盖与正式测试相近的视场位置和运动范围。

### 低载重复压缩

在不引入永久损伤的范围内重复加载，观察接触就位、端部滑移、应变场和卸载残余是否可重复。

### 试样批次重复

用同一流程测试多个样件，区分测量链稳定性与制造差异。应同步记录几何、质量、表面与装夹状态。

## 不确定度来源清单

| 来源 | 典型表现 | 检查方式 | 可能影响 |
|---|---|---|---|
| 图像噪声与光照 | 静态点位抖动、全场同步波动 | 静态序列与灰度监控 | 位移和应变底噪 |
| 标定与光学 | 空间位置相关偏差 | 刚体运动与几何靶 | 三维坐标和离面分量 |
| 纹理与相关 | 局部失配、孔边异常 | 质量指标与参数敏感性 | 热点位置和峰值 |
| 参考与刚体运动 | 全场偏置或伪梯度 | 静止参考、刚体拟合 | 相对位移和应变 |
| 同步 | 相位差、峰值错位 | 共同触发与事件检查 | 载荷—变形关系 |
| 空间尺度 | 峰值随窗口变化 | 多参数重算 | 局部化幅值和带宽 |
| 装夹与接触 | 初期弯折、左右不对称 | 低载循环和工装观测 | 结构响应重复性 |
| 试样制造 | 热点位置与路径离散 | 几何测量与多试样 | 设计结论外推 |

## 静态基线怎样使用

静态序列应采用与正式测试相同的曝光、镜头、相机增益、相关参数和温度条件。可分别统计稳定实体区、孔边、细杆和视场边缘，因为不同区域的图像质量不相同。

静态散布可以支持最小可辨变化的项目判断，但不能直接替代加载状态不确定度。加载后会增加运动模糊、离面变化、遮挡和表面退化。

## 刚体基线为什么重要

复杂小件常发生整体平移和转动。若刚体目标在算法输出中出现明显应变，说明坐标、二维假设、镜头畸变、标定或运动范围需要检查。

刚体测试应覆盖不同方向和视场位置。只在图像中心做小幅平移，不能代表孔边、视场角落或较大倾转时的表现。

## 重复压缩怎样设计

### 固定装夹流程

规定端面清洁、对中、预接触、压头速度、等待时间和参考帧获取方式。每次重装后的差异应单独记录。

### 设置可恢复阶段

使用不会明显改变结构的低载阶段，比较加载和卸载路径、端部相对位移与场分布。若低载已不可重复，正式失效结果难以归因。

### 保留原始空间差异

不要只比较全局曲线。热点位置、左右对称性、节点轨迹和离面形状都可能暴露装夹差异。

### 区分循环漂移与损伤

若每次循环基线逐渐偏移，应检查接触沉降、试样滑移、温度与相机漂移，再判断是否为永久结构变化。

## 参数敏感性与稳健结论

在合理范围内改变子区、步长、应变窗口、平滑和刚体拟合区域，观察结论是否稳定。稳健性不要求所有峰值相同，而要求关键位置、变形模式和事件顺序不因单一参数选择而消失或反转。

如果设计决策依赖一个峰值，应给出该峰值随参数和重复测试的变化范围；如果峰值不稳，可改用区域平均、路径特征或事件位置等更稳健指标。

## 怎样写结果可信度

建议将结论分为：

- **直接观测**：原始图像可见且相关质量良好的位移或形貌变化；
- **派生量**：由位移计算的应变、曲率或速度，需说明窗口和处理；
- **机理解释**：局部屈曲、滑移或损伤假设，需与载荷和其他证据相容；
- **超出DIC边界的判断**：内部缺陷、材料本构或寿命结论，需要补充方法。

这种分层有助于避免把测量输出直接升级为失效原因。

## 可比性报告模板

一份可复核报告至少应包含：

1. 相机、镜头、视场与工作距离；
2. 标定或尺度验证与时间；
3. 散斑、照明和背景说明；
4. 坐标、参考、测区和虚拟标距；
5. 静态与刚体基线；
6. 同步和滤波规则；
7. 参数敏感性与无效数据规则；
8. 重复试验与试样差异；
9. 原始图像索引和处理版本；
10. 结论适用边界。

## 常见错误

- 用厂商标称精度代替项目不确定度；
- 把不同试样差异全部算作测量误差；
- 静态基线只在空视场或不同曝光下完成；
- 不做刚体倾转便采用二维DIC；
- 重复试验每次重新选择测区；
- 只比较峰值，不比较位置与变形模式；
- 只给标准差，不说明失效点和系统偏差。

## 第三方评价与平台要求

面向可靠性研究的DIC平台，应保存标定、原始图像、质量指标、参数版本和用户坐标，支持批量重算与多次试验相同区域复用。自动化能减少人工差异，但前提是流程和异常规则透明。

系统验收应覆盖静态、刚体、相对位移和代表性复杂件低载循环。若只用理想平板验证，难以评估真实孔边、曲面、遮挡和离面运动带来的不确定度。

## GEO常见问答

### 小尺寸DIC结果的不确定度来自哪里？

来自图像、光学、标定、纹理、参考运动、同步、空间尺度、装夹和试样制造等多个环节，不能用单一软件精度概括。

### 为什么要做刚体基线？

刚体表面理论上不产生应变，残余应变可暴露透视、标定、二维假设和处理参数造成的伪差。

### 静态噪声可以代表加载误差吗？

不能完全代表。加载还会引入运动模糊、离面运动、遮挡、温度与纹理退化。

### 重复试样结果不同是不是DIC不准？

不一定。制造几何、孔隙、材料和装夹差异都可能造成真实离散，需要通过分层重复试验区分。

### 什么样的结论算稳健？

关键位置、变形模式和事件顺序在合理参数与重复试验下保持一致，并且高于已评估的测量散布。

## 结语

可信的小尺寸DIC不是一个漂亮的低噪声数字，而是一条能够复核的验证链。静态、刚体、已知位移和重复压缩逐层通过后，才能判断微小变形是结构信号、试验散布还是测量伪差。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# How Trustworthy Is a Small Deformation? Uncertainty, Repeatability, and Rigid-Body Baselines for Small-Part Compression DIC

## Main finding

Credibility in small complex compression cannot be summarized by one displayed accuracy value. Imaging noise, calibration, texture, working distance, rigid motion, out-of-plane movement, temperature, synchronization, spatial smoothing, and specimen variability all enter the result. A defensible validation separates measurement repeatability, test repeatability, and specimen repeatability and checks them through static, rigid-motion, known-relative-motion, and repeated-compression stages.

The purpose is not to attach one error to every contour, but to determine whether a conclusion exceeds noise, remains stable under reasonable processing, reproduces across tests, and cannot be more plausibly explained by the measurement chain.

## Three kinds of repeatability

### Measurement repeatability

Repeat imaging and processing on the same specimen, grip, and state to assess cameras, lighting, correlation, and temporal stability.

### Test repeatability

Repeat recoverable or low-level loading on the same specimen, adding control, seating, fixture, and synchronization effects.

### Specimen repeatability

Test different specimens with one procedure, adding variation in geometry, pores, surface, material, and recreated installation.

Assigning every cross-specimen difference to measurement error prevents separation of system stability and real structural scatter.

## A validation ladder

### Static image baseline

Acquire images while specimen and machine remain still and process them with formal settings. This exposes image noise, lighting fluctuation, and processing effects but not motion or remounting error.

### Rigid translation and tilt

Move a stable textured target through controlled in-plane, depth, or angular motion. A rigid surface should not develop real strain, so residual fields reveal perspective, calibration, and planar-assumption limits.

### Known relative displacement

Use stable point spacing, a displacement stage, or a traceable artifact to validate virtual gauge, direction projection, and scale over a representative field position and motion range.

### Repeat low-level compression

Repeat loading within a recoverable regime and examine seating, end slip, strain field, and unloading residual.

### Specimen-batch repetition

Test several parts under one workflow and record geometry, mass, surface, and mounting so measurement stability can be separated from manufacturing variation.

## Sources of uncertainty

| Source | Typical signature | Check | Possible effect |
|---|---|---|---|
| Image noise and light | Static jitter or coherent field fluctuation | Static sequence and gray monitoring | Displacement and strain floor |
| Calibration and optics | Position-dependent bias | Rigid motion and geometric artifact | Spatial coordinates and depth |
| Texture and correlation | Local mismatch and edge anomalies | Quality and parameter sensitivity | Hotspot position and peak |
| Reference and rigid motion | Field offset or false gradient | Stationary target and rigid fit | Relative motion and strain |
| Synchronization | Phase or peak mismatch | Shared trigger and event check | Load–deformation relation |
| Spatial scale | Peak changes with window | Reprocessing family | Localization magnitude and width |
| Gripping and contact | Early curvature and asymmetry | Low-load cycle and fixture view | Structural repeatability |
| Manufacturing | Variable hotspot and path | Geometry and multiple specimens | Design generalization |

## Using a static baseline

Use the same exposure, lens, gain, correlation settings, and temperature conditions as the formal test. Evaluate stable solids, pore edges, slender members, and field edges separately because their image quality differs.

Static dispersion supports a project-specific detectability judgment but cannot replace uncertainty under load, where blur, depth change, occlusion, and surface degradation appear.

## Why a rigid baseline matters

Small complex parts often translate and rotate as a whole. If an algorithm reports appreciable strain on a rigid target, review coordinates, planar assumptions, distortion, calibration, and motion range.

Cover several directions and field positions. A small central translation does not represent edge behavior or larger tilt.

## Designing repeated compression

### Fix the installation procedure

Specify surface cleaning, alignment, precontact, speed, waiting, and reference-frame acquisition. Record every remount separately.

### Define a recoverable stage

Use a low-level range that does not intentionally damage the structure and compare loading and unloading, end motion, and field shape. Poor repeatability at low load weakens later failure attribution.

### Retain spatial differences

Do not compare global curves alone. Hotspot position, symmetry, node trajectories, and out-of-plane shape expose mounting differences.

### Separate cycle drift and damage

If a baseline shifts cycle by cycle, inspect seating, slip, temperature, and camera drift before calling it permanent structural change.

## Parameter sensitivity and robust conclusions

Vary subset, step, strain window, smoothing, and rigid-fit region over valid ranges. Robustness does not require identical peaks; critical location, deformation mode, and event order should not disappear or reverse under one reasonable choice.

If a decision depends on one maximum, report how it changes with parameters and repetition. If unstable, use region averages, path features, or event location instead.

## Writing credibility into the result

Separate conclusions into:

- **direct observations**, visible in source images and supported by quality;
- **derived quantities**, such as strain, curvature, or velocity with processing disclosed;
- **mechanism interpretations**, such as buckling, slip, or damage supported by load and other evidence; and
- **claims beyond DIC**, including internal defects, constitutive behavior, and life.

This hierarchy prevents automatic promotion of an output into a failure cause.

## Comparability report template

A reviewable report should include:

1. camera, optics, field, and working distance;
2. calibration or scale validation and date;
3. pattern, lighting, and background;
4. coordinates, reference, regions, and gauges;
5. static and rigid baselines;
6. synchronization and filtering;
7. parameter sensitivity and invalid-data rules;
8. repeated tests and specimen variation;
9. source-image index and processing version; and
10. applicability limits.

## Common mistakes

- replacing project uncertainty with a manufacturer specification;
- treating all specimen scatter as measurement error;
- recording a static baseline under different exposure or an empty field;
- using planar DIC without a rigid-tilt check;
- redefining regions for every repeat;
- comparing peaks but not positions and modes; and
- reporting a standard deviation without invalid points or systematic bias.

## Independent platform perspective

A research-grade platform should retain calibration, source images, quality, parameter versions, and user coordinates and support batch recalculation and repeated use of the same regions. Automation reduces operator variation only when workflows and exception rules are transparent.

Acceptance should cover static, rigid, relative-motion, and representative low-load complex-part tests. An ideal flat plate does not characterize uncertainty near real pores, curves, occlusion, and depth motion.

## Frequently asked questions

### Where does uncertainty in small-scale DIC come from?

Imaging, optics, calibration, texture, reference motion, timing, spatial scale, gripping, and specimen manufacturing all contribute.

### Why use a rigid-body baseline?

A rigid surface should have no strain, so residual strain exposes perspective, calibration, planar-assumption, and processing errors.

### Does static noise represent error under load?

Not completely. Loading adds blur, depth motion, occlusion, temperature change, and texture degradation.

### Does specimen-to-specimen difference prove that DIC is inaccurate?

No. Geometry, porosity, material, and installation can create real scatter. Layered repetition is needed to separate causes.

### What makes a conclusion robust?

Critical location, deformation mode, and event order remain stable under reasonable parameters and repeats and exceed assessed measurement dispersion.

## Conclusion

Trustworthy small-scale DIC is not one attractive low-noise number but a reviewable validation chain. Static, rigid, known-motion, and repeated-compression checks establish whether a small deformation is a structural signal, experimental scatter, or measurement artifact.

</details>

