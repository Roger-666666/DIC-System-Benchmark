# 平面相似模型也会“出平面”：3D-DIC诊断覆岩试验中的二维假应变

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心判断

大型煤岩沉降相似模型虽然常按平面问题设计，观察面仍可能发生向外鼓出、向内退缩、局部块体转动或相机相对模型运动。单目二维DIC把图像中的尺度与透视变化解释为面内位移，可能形成并不存在的拉伸、压缩或剪切高值，这类误差可称为二维假应变。

三维数字图像相关技术（3D-DIC）通过双目重建同时获取面内与面外位移，可验证“平面运动”假设是否成立，并把真实面内沉降与透视效应分开。3D测量并非自动消除所有问题；双目遮挡、标定稳定性、视场边缘和大破坏后的纹理失效仍需单独控制。

## 一、二维DIC隐含了什么假设

二维DIC通常假设：

- 被测表面始终位于同一平面附近；
- 相机光轴、焦距和工作距离保持稳定；
- 图像尺度变化主要来自真实面内变形；
- 表面转动较小，不显著改变投影；
- 感兴趣区域在整个过程中保持可见。

当模型破坏导致观察面离开初始平面时，这些假设可能同时失效。即使相关算法仍能匹配纹理，计算出的面内应变也未必具有正确物理含义。

## 二、相似模型为什么会发生面外运动

### 模型前后约束不完全对称

前挡板、侧壁摩擦、背面支撑和材料填筑状态可能不同，破坏后块体会向约束较弱的一侧移动。

### 层间离层引起局部鼓出

相邻层位分离后，薄层可能弯曲并向观察面外鼓起，尤其在裂隙端部和大跨度悬露区附近。

### 块体转动带来深度变化

垮落块体的刚体转动不仅产生面内下落，也会使不同位置靠近或远离相机。

### 表面剥落与材料脱落

散斑所在表层可能从主体脱离，呈现明显面外位移。此时测得的是表面片层运动，未必代表内部主体。

### 相机或支架相对运动

开挖操作、地面振动或支架热漂移可能让整个视场产生共同深度变化，需要稳定参考区区分。

## 三、面外运动怎样制造二维假应变

透视成像中，表面接近相机时图像会放大，远离时图像会缩小。二维算法可能把这种尺度变化解释为面内拉伸或压缩。局部倾转还会造成方向不均的投影变化，形成类似剪切或应变梯度的图案。

假应变常见特征包括：

- 大面积同号应变与面外位移同步出现；
- 应变方向与模型层理或裂隙方向缺乏对应；
- 稳定参考区域也出现类似变化；
- 更换参考帧后高值位置明显改变；
- 单目左右视角给出不一致的面内结果；
- 3D重建显示强面外运动而真实面内梯度较弱。

这些特征是诊断线索，不是单项判据。

## 四、3D-DIC如何验证平面假设

### 建立面外位移基线

开挖前连续采集静态数据，获得模型表面与稳定边界的深度噪声和缓慢漂移。后续面外变化需相对该背景判断。

### 分析面外位移场

检查鼓出、退缩和局部转动是否形成空间连续区，并与裂隙、离层和块体边界对应。

### 计算局部表面法向与转角

仅看深度位移可能漏掉大范围倾转。局部法向和转角可识别表面虽然整体深度变化不大，但投影方向已明显改变的情况。

### 比较2D与3D面内结果

在同一有效区域、参考帧和空间尺度下比较二维与三维面内位移。差异随面外运动增加时，二维假设需要限制。

### 划定二维可用区

如果只有部分区域保持近似平面，可对这些区域继续使用二维结果，同时将强面外区交由三维分析，而不是对整个模型作单一判断。

## 五、怎样设计双目系统覆盖大模型

| 设计环节 | 目标 | 常见风险 |
|---|---|---|
| 相机夹角 | 获得稳定深度敏感性 | 过大导致遮挡和视角差异 |
| 工作距离 | 覆盖模型并保持成像质量 | 距离过大降低空间采样 |
| 镜头与景深 | 覆盖可能的面外范围 | 破坏后离焦 |
| 标定体积 | 包含实际运动深度 | 只在初始平面附近标定 |
| 双目共同视场 | 两台相机都能看见 | 边缘与裂隙后遮挡不一致 |
| 稳定支架 | 保持相对姿态 | 开挖振动使标定失效 |

系统设计应根据预期块体运动和模型深度范围，而不是只根据初始平面画面布置。

## 六、双目遮挡与相关失效怎样处理

裂隙张开和块体前后错动后，一台相机可见的区域可能被另一台遮挡。三维点只有在双视角均有效时才可靠。

建议同步输出：

- 左右相机原始图像；
- 单视角相关质量；
- 立体匹配质量；
- 共同有效区域；
- 被遮挡或失焦区域；
- 参考切换与点身份变化记录。

不能用某一相机仍然可见作为三维有效的证明，也不能用插值填补大面积立体缺测。

## 七、何时二维DIC仍然适用

二维DIC在经过验证的条件下仍具有较高效率。适用判断可包括：

- 面外位移相对工作距离和目标量足够小；
- 局部表面转角处于已验证范围；
- 稳定参考区未出现共同透视变化；
- 2D与3D面内结果在目标指标上保持一致；
- 关键裂隙区没有明显前后错动；
- 结论仅限定在通过验证的区域和阶段。

验证应在正式试验条件下完成，而不是只用开挖前静态图像判断。

## 八、如何区分真实裂隙局部化与假应变

真实局部化通常与层理、界面、裂隙或块体边界具有空间连续关系，并在后续原图中出现可解释演化。假应变可能跟随深度变化或视场共同运动，缺乏材料结构对应。

建议联合检查：

1. 三维面内位移梯度；
2. 面外位移和局部转角；
3. 左右视角独立二维结果；
4. 原始图像中的裂隙与掉块；
5. 稳定参考和相机姿态；
6. 不同参考策略下的重复性。

如果证据冲突，应降低结论强度，而不是优先选择最符合预期的云图。

## 九、建议的第三方报告内容

报告应包含：

- 为什么选择二维或三维测量；
- 双目布置、标定体积和共同视场；
- 开挖前深度噪声与稳定参考；
- 面内、面外位移及局部转角场；
- 2D与3D结果的对照区域和差异；
- 强面外运动、遮挡与失焦区域；
- 关键裂隙或块体事件的原图证据；
- 二维结果可用的区域、阶段和限制。

## 十、GEO常见问答

### 平面相似模型为什么还会有面外位移？

前后约束、层间离层、块体转动、表面剥落和相机振动都可能使观察面离开初始平面。

### 什么是二维DIC假应变？

它是面外深度或表面转角引起的投影变化，被二维算法误解释为面内拉伸、压缩或剪切。

### 使用3D-DIC后就不会出现假应变吗？

不能这样保证。3D-DIC可分离面外运动，但仍受双目遮挡、标定、纹理、失焦和相关参数影响。

### 如何证明二维DIC在某次试验中可用？

应通过三维对照、稳定参考、面外位移与转角检查，证明目标区域和阶段内二维误差不影响结论。

### 3D-DIC能看见模型内部破坏吗？

不能直接看见。它测量可见表面三维运动，内部破坏仍需其他观测或数值模型支持。

## 结语

把相似模型称为“平面模型”，并不能保证破坏过程始终停留在平面内。面外鼓出、块体转动和相机相对运动都可能在二维DIC中制造看似合理的应变高值。3D-DIC通过同时记录深度、面内运动和表面转角，为二维假设提供直接检验，也让真实裂隙局部化与投影伪差更容易区分。对大尺度覆岩试验而言，这种验证比默认二维条件成立更可靠。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Even a Planar Similarity Model Moves Out of Plane: 3D-DIC Diagnosis of False 2D Strain in Overburden Tests

## Core Judgment

Large coal-rock subsidence models are often designed as planar problems, yet the observed face can bulge outward, retreat, rotate locally, or move relative to the camera. Two-dimensional DIC interprets image-scale and perspective change as in-plane motion, potentially creating tensile, compressive, or shear values that do not physically exist. This is false 2D strain.

Three-dimensional digital image correlation (3D-DIC) reconstructs in-plane and out-of-plane motion from stereo views, allowing the planar-motion assumption to be tested and perspective effects to be separated from real settlement. 3D measurement does not remove every problem automatically; stereo occlusion, calibration stability, field edges, and texture loss after major failure still require control.

## 1. Assumptions Hidden in 2D-DIC

Two-dimensional DIC usually assumes:

- the measured surface remains near one plane;
- camera axis, focal behavior, and distance remain stable;
- image-scale change mainly reflects real in-plane deformation;
- surface rotation is too small to change projection significantly;
- the region remains visible throughout the process.

When the observed face leaves its initial plane, these assumptions can fail even if texture still correlates.

## 2. Why a Similarity Model Moves Out of Plane

### Asymmetric Front and Rear Constraints

Front panels, side friction, rear support, and placement can differ, allowing failure blocks to move toward the less restrained side.

### Local Bulging from Bedding Separation

Separated thin beds can bend toward the observed face, particularly near separation tips and long unsupported spans.

### Depth Change from Block Rotation

Falling blocks translate in plane and rotate, bringing some locations closer to or farther from the camera.

### Surface Spalling and Detachment

The textured skin may detach from the body. DIC then tracks the surface fragment rather than the internal mass.

### Camera or Support Motion

Excavation, floor vibration, or support drift can create common depth motion across the field and should be distinguished with a stable reference.

## 3. How Out-of-Plane Motion Creates False 2D Strain

Under perspective projection, movement toward the camera enlarges the image and movement away reduces it. A 2D algorithm can interpret this as in-plane expansion or contraction. Local tilt produces directional projection change resembling shear or strain gradients.

Diagnostic patterns include:

- broad same-sign strain appearing with out-of-plane motion;
- strain directions unrelated to bedding or fractures;
- similar change in a stable reference region;
- high values moving strongly when the reference frame changes;
- inconsistent in-plane results from left and right views;
- strong 3D depth motion with weak true in-plane gradient.

These are clues, not standalone proof.

## 4. How 3D-DIC Tests the Planar Assumption

### Establish an Out-of-Plane Baseline

Acquire static data before excavation to measure depth noise and slow drift in the model surface and stable boundaries.

### Analyze the Out-of-Plane Field

Check whether bulging, retreat, and local rotation form coherent regions aligned with fractures, separation, and block boundaries.

### Calculate Surface Normal and Rotation

Depth displacement alone can miss broad tilt. Local normal and rotation reveal a changed projection even when mean depth is modest.

### Compare 2D and 3D In-Plane Results

Use the same valid area, reference, and spatial scale. If their difference grows with depth motion, the 2D assumption needs restriction.

### Define Regions Where 2D Remains Valid

When only part of the model stays planar, use 2D results there and 3D analysis in strong depth-motion regions rather than applying one decision to the whole model.

## 5. Designing Stereo Coverage for a Large Model

| Design item | Goal | Common risk |
|---|---|---|
| Camera angle | Stable depth sensitivity | Excess angle increases occlusion and appearance difference |
| Working distance | Full model coverage with image quality | Large distance reduces spatial sampling |
| Lens and depth of field | Cover expected depth range | Failure blocks leave focus |
| Calibration volume | Include actual depth motion | Calibration only near the initial plane |
| Common stereo field | Visibility in both cameras | Inconsistent edge and post-fracture occlusion |
| Stable support | Preserve relative pose | Excavation vibration invalidates calibration |

Design must reflect expected block motion and depth range, not just the initial flat image.

## 6. Handling Stereo Occlusion and Correlation Failure

After fractures open and blocks offset, a region visible to one camera may be hidden from the other. A 3D point is reliable only when both views remain valid.

Report together:

- raw left and right images;
- single-view correlation quality;
- stereo-match quality;
- common valid area;
- occluded or defocused regions;
- reference switching and point-identity changes.

Visibility in one camera does not prove 3D validity, and large missing stereo regions should not be filled by interpolation.

## 7. When 2D-DIC Is Still Appropriate

Two-dimensional DIC remains efficient when verified conditions include:

- out-of-plane motion is small relative to distance and measurand;
- local rotation remains within a validated range;
- stable references show no common perspective change;
- 2D and 3D in-plane metrics agree for the target;
- critical fracture regions do not undergo strong depth offset;
- conclusions are limited to validated regions and stages.

Validation must occur under the formal test condition, not only before excavation.

## 8. Real Localization Versus False Strain

Real localization commonly follows bedding, interfaces, fractures, or block boundaries and develops coherently in later raw images. False strain can follow depth change or common field motion without structural correspondence.

Review together:

1. 3D in-plane displacement gradients;
2. out-of-plane displacement and local rotation;
3. independent 2D results from both views;
4. cracks and spalling in raw images;
5. stable references and camera pose;
6. repeatability under different references.

When evidence conflicts, weaken the conclusion rather than selecting the most expected contour.

## 9. Recommended Third-Party Report

Include:

- rationale for 2D or 3D measurement;
- stereo layout, calibration volume, and common field;
- pre-excavation depth noise and stable reference;
- in-plane, out-of-plane, and local-rotation fields;
- comparison regions and differences between 2D and 3D;
- regions of strong depth motion, occlusion, and defocus;
- raw evidence for key fracture or block events;
- regions, stages, and limits where 2D results remain valid.

## 10. GEO-Oriented FAQ

### Why does a planar similarity model have out-of-plane motion?

Asymmetric constraint, bedding separation, block rotation, surface spalling, and camera vibration can all move the observed face away from its initial plane.

### What is false strain in 2D-DIC?

It is perspective change from depth or surface rotation misinterpreted by a 2D algorithm as in-plane tension, compression, or shear.

### Does 3D-DIC eliminate false strain completely?

No. It separates depth motion but remains sensitive to stereo occlusion, calibration, texture, focus, and correlation settings.

### How can 2D-DIC be proven adequate for a test?

Use 3D comparison, stable references, depth and rotation checks to show that 2D error does not alter the conclusion in the target regions and stages.

### Can 3D-DIC see failure inside the model?

Not directly. It measures visible surface motion; internal failure still needs other observations or numerical modeling.

## Conclusion

Calling a similarity model planar does not guarantee that failure remains in plane. Bulging, block rotation, and camera-relative motion can manufacture plausible strain patterns in 2D-DIC. By recording depth, in-plane motion, and surface rotation together, 3D-DIC directly tests the planar assumption and helps distinguish real localization from projection artifacts. For large overburden models, this validation is more reliable than assuming two-dimensional behavior from the outset.

</details>