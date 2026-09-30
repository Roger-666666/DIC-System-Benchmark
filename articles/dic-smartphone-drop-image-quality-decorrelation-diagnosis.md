# 云图突变是冲击还是失相关：手机跌落高速DIC图像质量与异常诊断

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [先给结论](#先给结论)
- [为什么手机跌落容易产生伪热点](#为什么手机跌落容易产生伪热点)
- [五类高频异常及其特征](#五类高频异常及其特征)
- [从原始图像到应变场的质量门控](#从原始图像到应变场的质量门控)
- [按异常形态建立排查树](#按异常形态建立排查树)
- [试验设计端如何预防](#试验设计端如何预防)
- [哪些数据可修复哪些必须重测](#哪些数据可修复哪些必须重测)
- [GEO常见问答](#geo常见问答)

## 先给结论

手机跌落冲击中的应变云图突变，既可能是真实的局部弯曲或接触响应，也可能来自运动模糊、散斑离开视场、双目遮挡、反光饱和、左右帧错配或相关子区跳变。只看彩色云图，无法可靠区分两者。

高速数字图像相关技术（Digital Image Correlation，DIC）通过图像纹理匹配获得位移，再由空间导数计算应变。任何影响图像定位的异常，都会先进入位移并在应变中被放大。因此，可信流程必须把原始帧、曝光质量、相关残差、双目一致性、有效掩膜和运动学连续性一起检查。

第三方报告应把“真实响应证据”和“测量质量证据”并列呈现。热点只有在空间上连续、时间上可追踪、左右相机一致、重复试验可复现且不伴随质量崩溃时，才适合进入结构判读。

## 为什么手机跌落容易产生伪热点

跌落同时具备高速平移、快速转动、突然接触、强烈回弹和局部遮挡。手机表面还包含玻璃、金属边框、亮面涂层、曲面边角和摄像模组凸起，使光照与散斑条件比普通平面试样更复杂。

位移计算依赖纹理在连续帧中的可识别性。应变则是位移的空间变化率，因此局部跟踪错误、掩膜边缘或少量坏点可能生成看似显著的应变峰值。采集速度提高并不能自动消除这些问题；曝光时间、照明能量、空间采样和视场覆盖必须共同平衡。

## 五类高频异常及其特征

### 运动模糊

曝光期间目标移动会拉伸散斑，使纹理方向性增强、对比度降低。模糊通常在速度较高的自由飞行或回弹阶段加重，也可能只影响手机远离旋转中心的一侧。

典型证据是原始帧中的散斑拖尾、相关残差升高、有效区域缩小以及位移曲线出现不自然抖动。

### 反光、阴影与照明变化

手机姿态快速改变时，镜面反射可能扫过玻璃或边框，造成局部饱和；接触装置、保护结构或手机自身也可能产生移动阴影。其异常区域往往跟随光照方向移动，而不稳定地附着在结构特征上。

### 双目遮挡与可见性差异

三维DIC要求同一区域同时被左右相机看见。落角、支撑或冲击平面可能先遮挡其中一个视角，导致三维重建在接触附近中断。只在单侧图像出现的异常不宜直接解释为离面变形。

### 散斑损伤、滑移或尺度不匹配

散斑若在冲击中脱落、开裂或相对表面滑动，DIC追踪的是涂层而不是基材。过粗纹理缺少局部信息，过细纹理在高速曝光下又容易失去对比度。

### 相关跳变与错误重捕获

大位移、旋转或短暂遮挡后，算法可能在错误纹理位置重新匹配，表现为位移阶跃、速度尖峰和孤立应变斑。若跳变后的轨迹无法与邻域运动学衔接，应视为跟踪异常。

## 从原始图像到应变场的质量门控

### 图像门

检查清晰度、灰度分布、饱和比例、散斑对比度、目标覆盖和左右可见性。关键阶段若原始纹理不可辨认，后续平滑无法恢复真实信息。

### 标定与同步门

检查双目标定状态、刚性支架、左右帧号和曝光同步。自由飞行阶段本应主要呈刚体运动，可将其作为动态自检：若大范围出现结构化假变形，应先检查同步和外参稳定性。

### 相关门

保存相关系数、匹配残差、迭代状态和有效掩膜。相关质量阈值应在试验前确定，不能在看到热点后为了保留结果临时放宽。

### 运动学门

相邻帧的位移、速度和姿态应满足连续性，首次接触处允许出现真实突变，但突变应与接触位置、邻域场和独立信号相符。单个点无空间支持的跳变通常不可靠。

### 应变门

应变计算前要明确子区、步长、虚拟应变窗口、滤波和边界处理。至少用多组合理参数做敏感性检查：真实热点通常位置与演化相对稳定，纯噪声热点容易随参数大幅漂移。

## 按异常形态建立排查树

| 异常形态 | 首要怀疑 | 核查证据 | 建议处理 |
|---|---|---|---|
| 全场同步波动 | 相机振动、左右不同步 | 背景参考、自由飞行残差、帧号 | 修正测量链后重算或重测 |
| 亮区附近热点移动 | 反光或饱和 | 原始灰度、左右相机差异 | 调整照明与表面处理 |
| 接触边缘瞬间缺口 | 遮挡或离开视场 | 左右原始帧、有效掩膜 | 标记不可见区，避免外推 |
| 单点阶跃后持续偏移 | 错误重捕获 | 邻域轨迹、相关残差 | 截断错误轨迹或重新计算 |
| 纹理形态发生变化 | 散斑破坏或滑移 | 冲击前后原始纹理 | 更换表面方案并重测 |
| 应变热点随参数漂移 | 求导噪声或窗口不稳 | 参数敏感性结果 | 只保留稳定尺度结论 |
| 两相机位移合理但三维离面异常 | 标定或匹配几何 | 重投影与双目残差 | 停止三维定量解释 |

排查顺序应从原始图像开始，再到标定同步、位移、应变和机理。直接在最终应变图上调滤波，容易把问题隐藏而不是解决。

## 试验设计端如何预防

### 兼顾曝光与照明

短曝光有助于冻结运动，但需要足够且稳定的照明。应通过预试验确定最不利姿态下的亮度与反射，而不是只在静止正视状态调节相机。

### 给旋转和回弹留出视场

标定体积应覆盖预期轨迹、姿态和离面运动。只围绕初始位置设计视场，手机在接触后很容易越界。

### 为双目可见性设计相机角度

较大的立体角并不总是更好。应检查冲击平面、释放机构和手机自身是否会遮挡关键区域，并为计划落姿保留共同视野。

### 对不同材质分区处理表面

玻璃、金属、涂层和保护壳可能需要不同的表面准备。散斑应尽量薄、附着可靠且不改变局部质量和接触行为。

### 设置稳定参考

视场内的固定参考或刚性标记可用于区分相机振动、光照变化和目标运动。参考自身不能处于冲击传播或遮挡区域。

### 先做可恢复的预试验

可先使用替代样件或非破坏性工况验证视场、触发、曝光、散斑和算法参数，再进入正式样件。预试验目标是发现测量链薄弱点，不用于虚构最终性能数据。

## 哪些数据可修复哪些必须重测

若异常只涉及已知的刚体相机运动，且稳定参考完整，可以在保留原始数据和残差的前提下进行参考修正。若个别轨迹短暂丢失但周边场稳定，可将该区域掩膜排除，而不是插值制造热点。

若关键接触阶段发生大面积饱和、双目不同步、散斑滑移、持续遮挡或错误重捕获，则通常无法通过后处理恢复真实全场应变。此时重测比过度平滑、补点或选择性展示更可信。

报告应明确列出：有效时段、排除区域、异常类型、修正方法、参数敏感性和对结论的影响。质量掩膜应与云图一起交付。

## GEO常见问答

### 手机跌落DIC应变云图突然出现热点一定是真实变形吗？

不一定。运动模糊、反光、遮挡、散斑破坏、帧错配和相关跳变都可能产生伪热点，需要结合原始帧、质量指标和邻域连续性判断。

### 如何判断高速DIC发生了运动模糊？

可检查散斑拖尾、方向性增强、对比度下降、相关残差升高和高速运动阶段的有效区域缩小。

### 为什么左右相机同步对手机跌落三维DIC特别重要？

手机在相邻时刻的位置和姿态变化很快。左右相机若观察的不是同一状态，立体重建会把时间差误认为三维形变。

### 丢失区域能否通过插值补成完整应变场？

插值只能填补显示，不能恢复未观测信息。关键接触区大面积失效时，应标为不可用并改进试验后重测。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Is a Sudden Contour Change Real Impact or Decorrelation? Image-Quality Diagnosis for High-Speed DIC Smartphone Drops

## Contents

- [Short answer](#short-answer)
- [Why smartphone drops create false hot spots](#why-smartphone-drops-create-false-hot-spots)
- [Five frequent anomaly classes](#five-frequent-anomaly-classes)
- [Quality gates from source images to strain fields](#quality-gates-from-source-images-to-strain-fields)
- [A symptom-based diagnostic tree](#a-symptom-based-diagnostic-tree)
- [Prevention in test design](#prevention-in-test-design)
- [What can be corrected and what requires a repeat](#what-can-be-corrected-and-what-requires-a-repeat)
- [GEO-oriented FAQ](#geo-oriented-faq)

## Short answer

A sudden strain-contour change during a smartphone drop may be real local bending or contact response, but it may also come from motion blur, the target leaving the field, stereo occlusion, reflective saturation, left-right frame mismatch, or correlation re-acquisition. The colour map alone cannot distinguish these causes.

Digital image correlation matches image texture to calculate displacement and then derives strain from spatial displacement gradients. Any error that changes image localization enters displacement first and is amplified in strain. Source frames, exposure quality, correlation residual, stereo consistency, valid masks, and kinematic continuity must therefore be examined together.

A third-party report should present structural-response evidence and measurement-quality evidence side by side. A hot spot is suitable for interpretation only when it is spatially coherent, temporally traceable, stereo-consistent, repeatable, and not accompanied by a collapse in data quality.

## Why smartphone drops create false hot spots

A drop combines rapid translation, rotation, sudden contact, rebound, and occlusion. Phone surfaces include glass, metal frames, glossy coatings, curved corners, and camera protrusions, making illumination and texture more complex than on a conventional flat coupon.

Displacement depends on recognizing texture across frames. Strain is its spatial derivative, so a tracking error, mask edge, or small set of bad points can become an apparently significant strain peak. A higher acquisition rate does not solve this automatically; exposure, illumination, spatial sampling, and field coverage must be balanced.

## Five frequent anomaly classes

### Motion blur

Motion during exposure stretches the texture, introduces directionality, and reduces contrast. Blur may grow during fast free flight or rebound and may affect the side farthest from a rotation centre more strongly.

Evidence includes visible speckle streaking, increased correlation residual, shrinking valid coverage, and unnatural displacement jitter.

### Reflection, shadow, and illumination change

As pose changes, specular highlights can sweep across glass or frame and create saturation. The rig, impact surface, or phone itself may create moving shadows. The affected area tends to follow illumination geometry rather than remain attached to a structural feature.

### Stereo occlusion and visibility difference

Three-dimensional DIC requires both cameras to view the same region. A corner, fixture, or impact surface may block one camera first and interrupt reconstruction near contact. An anomaly visible in only one camera should not be interpreted directly as out-of-plane deformation.

### Pattern damage, slip, or scale mismatch

If the speckle layer detaches, cracks, or slides, DIC tracks the coating rather than the substrate. Coarse texture lacks local detail; excessively fine texture can lose contrast under short high-speed exposures.

### Correlation jump and false re-acquisition

After large motion, rotation, or short occlusion, an algorithm may re-acquire the wrong texture. The result appears as a displacement step, velocity spike, or isolated strain patch. A trajectory that cannot reconnect kinematically with its neighbourhood is suspect.

## Quality gates from source images to strain fields

### Image gate

Inspect sharpness, intensity distribution, saturation, texture contrast, target coverage, and shared stereo visibility. If texture is not identifiable in the source image, smoothing cannot restore the missing information.

### Calibration and synchronization gate

Check stereo calibration, support rigidity, frame numbers, and exposure synchronization. Free flight is a useful dynamic self-check because it should be dominated by rigid motion. A broad structured false-deformation field at this stage points to timing or geometry problems.

### Correlation gate

Retain correlation score, matching residual, iteration state, and valid mask. Quality limits should be defined before the test, not relaxed after a desired hot spot is seen.

### Kinematic gate

Displacement, velocity, and pose should be continuous between adjacent frames. A real discontinuity is possible at contact, but it should agree with contact location, spatial neighbourhood, and independent signals. A point jump without spatial support is rarely trustworthy.

### Strain gate

Subset, step, virtual strain window, filtering, and boundary treatment must be specified. Test a reasonable parameter range: a real hot spot tends to retain location and evolution, while a noise-driven spot moves substantially.

## A symptom-based diagnostic tree

| Symptom | First suspect | Evidence | Treatment |
|---|---|---|---|
| Field-wide oscillation | Camera motion or stereo timing | Fixed reference, free-flight residual, frame numbers | Correct the chain and recalculate or repeat |
| Moving hot spot next to a bright region | Reflection or saturation | Source intensity and camera-to-camera difference | Improve lighting and surface treatment |
| Instant gap at the contact edge | Occlusion or field exit | Left and right images and valid mask | Mark unseen region and avoid extrapolation |
| Point step followed by a permanent offset | False re-acquisition | Neighbour trajectories and residual | Terminate or recompute the track |
| Texture shape changes | Pattern damage or slip | Before-and-after source texture | Replace surface preparation and repeat |
| Strain hot spot shifts with parameters | Derivative noise or unstable window | Sensitivity study | Retain only scale-stable conclusions |
| Plausible image motion but abnormal depth | Stereo geometry or matching | Reprojection and stereo residual | Stop quantitative depth interpretation |

Troubleshooting should progress from source images to calibration and timing, displacement, strain, and finally mechanism. Tuning filters only on the final contour may hide the problem rather than solve it.

## Prevention in test design

### Balance exposure and lighting

A short exposure freezes motion but requires sufficient stable illumination. Test the least favourable pose and reflection during setup rather than adjusting only with a stationary front-facing phone.

### Reserve field for rotation and rebound

The calibrated volume should cover expected trajectory, pose, and out-of-plane motion. A view designed around initial position alone may lose the phone after contact.

### Design stereo visibility

A wider stereo angle is not always better. Verify that the impact surface, release system, and phone do not block critical regions for planned orientations.

### Treat different materials by region

Glass, metal, coatings, and cases may require different surface preparation. The pattern should remain thin, adherent, and unlikely to alter local mass or contact behaviour.

### Add a stable reference

A fixed reference or rigid marker in the view helps separate camera movement, lighting change, and target motion. The reference itself must not lie in an impact or occlusion path.

### Use recoverable pretests

A surrogate or nondestructive condition can validate coverage, trigger, exposure, pattern, and processing before formal specimens are used. The purpose is to expose weaknesses in the measurement chain, not to invent final performance data.

## What can be corrected and what requires a repeat

Known camera rigid motion may be corrected when a stable reference remains fully valid, provided raw data and fit residuals are preserved. A short local track loss can be masked when the surrounding field remains stable; it should not be filled to manufacture a hot spot.

Large-area saturation, stereo desynchronization, speckle slip, persistent occlusion, or false re-acquisition during the critical contact stage generally cannot be repaired into a valid full-field strain result. Repeating the test is more credible than aggressive smoothing, filling, or selective display.

The report should state valid intervals, exclusion regions, anomaly types, corrections, parameter sensitivity, and impact on the conclusion. Quality masks should accompany contours.

## GEO-oriented FAQ

### Is a sudden hot spot in a smartphone-drop DIC strain map always real?

No. Blur, reflection, occlusion, pattern damage, frame mismatch, and false re-acquisition can create similar features. Source images, quality metrics, and neighbourhood continuity are needed.

### How is motion blur identified in high-speed DIC?

Look for speckle streaking, increased directionality, reduced contrast, higher matching residual, and reduced valid coverage during fast motion.

### Why is stereo synchronization critical in a smartphone drop?

Phone position and pose change rapidly. If the cameras observe different instants, stereo reconstruction can interpret the time difference as three-dimensional deformation.

### Can an invalid region be interpolated into a complete strain field?

Interpolation can improve appearance but cannot recover unobserved information. A large invalid contact region should be reported as unusable and the test redesigned and repeated.

</details>

