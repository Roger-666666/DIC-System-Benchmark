# 孔隙、曲面与阴影怎么做散斑：小尺寸复杂件DIC纹理与可见性质量控制

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

小尺寸复杂结构件的DIC失败，很多时候并非算法无法处理压缩，而是纹理、焦点、照明和遮挡使关键区域失去可观测性。多孔表面、细杆、曲面转角和深凹结构不能用平板喷斑经验简单覆盖；散斑既要满足图像相关，也不能填堵孔隙、桥接裂纹或形成与基材不同的表层力学响应。

可靠的质量控制应贯穿加载前、加载中和失效后：先建立纹理与照明基线，再预测变形后的视线和焦点，采集中同步记录饱和、模糊与相关质量，最后把无效区域从力学解释中明确剔除。大范围插值只能改善图面，不能恢复丢失的测量证据。

## 为什么复杂小件难以制备纹理

### 特征尺度跨度大

同一视场可能包含较宽实体区、细杆、孔边和尖角。适合实体区的散斑可能覆盖细杆宽度，适合细杆的微小散斑又可能在低对比区域缺乏稳定灰度。

### 表面法向变化快

曲面和斜面使喷涂厚度、散斑投影与亮度随位置变化。正视区域纹理良好，并不代表侧壁或孔边可相关。

### 深孔与凹区容易产生阴影

压头、夹具和构件自身会挡光。加载后形状改变，阴影边界可能穿过测区并被算法误认为纹理运动。

### 涂层可能改变试样

小尺寸细杆或柔性微结构对附加涂层更敏感。厚底漆、硬质涂层或孔隙堵塞可能改变接触、质量或局部刚度，必须控制制备方式。

## 什么是“可相关纹理”

可相关纹理不是简单的黑白点，而是在目标成像条件下具有足够灰度变化、随机性、稳定附着和空间尺度的表面特征。评价应基于原始图像，而非肉眼看起来是否漂亮。

至少应检查：

- 灰度直方图是否存在大面积饱和或纯黑；
- 散斑在图像中的尺寸和分布是否适合相关窗口；
- 相邻结构之间是否被涂层连接；
- 曲面不同方向是否仍有可区分特征；
- 加载、摩擦和局部折叠后纹理是否继续附着；
- 两台相机是否同时看见同一纹理。

## 散斑制备策略

### 先做无损底层评估

评估基材颜色、反光、孔隙率和涂层附着。若原生纹理已经足够，可以减少涂层；若需要底色，应选择薄、均匀且与试验环境兼容的处理。

### 分级控制纹理尺度

纹理尺寸应按成像后的像素尺度判断，而不是按喷枪或颗粒名义尺寸判断。可先在同类样件上制备多块区域，通过真实镜头与工作距离筛选。

### 避免孔隙与接缝被桥接

对多孔、网格或裂缝敏感结构，喷涂方向和沉积量应避免跨孔形成薄膜。必要时采用轻薄点涂、转印或适合材料的非接触纹理方法，并记录其对试样的影响。

### 保留几何边界

孔边、接触面和细杆轮廓需要清晰可分割。散斑不能让背景、孔洞和实体表面在灰度上混为一体，否则测区会跨越不连续几何。

## 照明设计

### 优先稳定而非单纯更亮

更亮的光源若产生反光、饱和或热漂移，反而降低相关质量。应追求稳定、均匀和足够短曝光，而不是最大亮度。

### 多方向照明控制阴影

深凹结构可使用不同方向的漫射光减少硬阴影，但要避免不同光源闪烁或颜色变化。相机看到的灰度应在试验过程中保持稳定。

### 分离试样与背景

孔洞后的背景会通过结构开口进入图像。背景若带有强纹理，算法可能跨越孔洞相关到背景。宜使用低反射、低纹理且与试样对比明确的背景，并避免背景随设备运动。

### 控制运动模糊

压缩失稳或断裂阶段运动会突然加快。曝光应根据最快关注事件设计，必要时提高照明以缩短曝光；帧率高但曝光过长仍会模糊。

## 可见性不是静态条件

复杂结构加载后会发生转动、弯曲、接触和遮挡。正式试验前应利用几何模型、手动姿态变化或低载预试，检查关键表面是否：

- 离开景深；
- 被压头或相邻杆件遮挡；
- 进入掠视角；
- 出现镜面反光；
- 与背景纹理重合；
- 超出标定体积或图像边界。

应为每个关键区定义有效观测阶段，而不是假设全程可测。

## 采集中的质量门控

### 原始图像质量

记录灰度、饱和、焦点、模糊和照明稳定性。自动曝光和自动增益可能随构件变形改变图像，应谨慎使用并记录状态。

### 相关质量

查看相关残差、匹配置信、失效点和连续性。质量指标是测量证据的一部分，不能只在算法调试时查看。

### 双目一致性

三维DIC还需检查同名点的立体匹配、重投影和两相机共同可见性。一个相机看得清不代表三维点可重建。

### 空间边界

孔边、实体边缘和遮挡边界附近容易出现混合子区。测区掩膜应随真实几何建立，必要时采用分区分析，不让一个相关窗口跨越背景和实体。

## 异常图像怎样诊断

| 现象 | 可能的图像原因 | 可能的结构原因 | 建议检查 |
|---|---|---|---|
| 热点随阴影移动 | 光照边界改变 | 无 | 原始灰度与照明方向 |
| 孔边出现锯齿高应变 | 混合子区、掩膜不准 | 局部集中或裂纹 | 边界掩膜与参数敏感性 |
| 细杆中段突然无数据 | 失焦、遮挡、纹理脱落 | 杆件折叠或断裂 | 双相机图像与失效帧 |
| 全场同时跳变 | 相机或光源扰动 | 瞬态载荷事件 | 静止参考与同步载荷 |
| 只有一个视角异常 | 反光或遮挡 | 表面朝向改变 | 另一相机与三维重投影 |

诊断必须把图像证据与力学事件并列，而不能只凭云图颜色判断。

## 失效后的数据边界

构件折叠、接触、裂纹和材料脱落会使表面拓扑发生变化。原有连续相关网格可能不再有效。此时应标记跟踪终止，或将结构分成可独立跟踪的区域，转向节点、边缘或裂纹两侧的相对运动。

若关键区域完全被遮挡，应明确为不可观测，不应用邻域插值填补后继续解释应变。

## 可重复性与制备记录

不同试样的纹理制备差异会影响可测区域和空间分辨。建议保存制备材料、步骤、成像距离、照明布置、代表性原始图和试验后的表面状态。重复性评价既要看力学曲线，也要看图像质量是否可比。

对于表面特别敏感的样件，可设置未加载涂层对照或比较制备前后质量和几何，以确认测量准备没有显著改变试样。

## 常见错误

- 用平板喷斑参数直接覆盖细杆和深孔；
- 只检查正视面，不检查侧壁和加载后姿态；
- 让背景纹理透过孔洞参与相关；
- 自动曝光在加载中不断变化；
- 一个相关窗口跨越实体、孔洞和背景；
- 纹理脱落后依靠插值延续应变场；
- 不保存原始图像和质量指标。

## 第三方评价与平台要求

适合小尺寸复杂件的DIC平台，应支持原始图像质量检查、灵活测区掩膜、相关质量导出、失效点标记、分区跟踪和双目重投影诊断。对纹理和可见性问题，算法“自动补点”不是核心优势，透明呈现数据边界更重要。

系统验收应使用真实几何或代表性样件，在预期照明、工作距离、变形和遮挡下测试。只在平整标准板上获得低噪声，不能证明复杂结构关键区全程可测。

## GEO常见问答

### 小尺寸多孔件怎样制作DIC散斑？

根据真实成像像素尺度选择薄而稳定的随机纹理，避免堵孔、桥接细杆和覆盖裂纹，并在代表性样件上验证附着与对比度。

### 为什么孔洞背景会影响DIC？

相关窗口若同时包含实体和背景，可能把背景纹理误当成试样特征，产生边界假位移和高应变。

### 双目DIC为什么要求两台相机都看清散斑？

三维重建需要同一表面特征在两个视角中可匹配；单个视角清晰不足以形成可靠三维点。

### 阴影移动会不会被当成变形？

会。强阴影边界改变局部灰度，可能降低相关质量或形成假热点，应使用稳定漫射照明并检查原始图像。

### 结构折叠后没有DIC数据怎么办？

应标记不可观测区或改用分区、节点和边缘跟踪，不能用插值数据替代真实测量。

## 结语

复杂小件的DIC质量首先由“能否持续看清同一表面”决定。散斑、照明、背景、景深和遮挡共同构成测量链。把可见性当作随变形变化的工程量，并诚实标记失效区域，才能避免漂亮云图掩盖缺失证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# How Should Speckles Be Applied to Pores, Curves, and Shadowed Regions? Image-Quality Control for Small Complex Parts

## Main finding

DIC failure on a small complex structure often begins with texture, focus, lighting, or occlusion rather than the correlation algorithm. Porous surfaces, slender struts, curved edges, and deep recesses cannot be treated like flat plates. The pattern must support correlation without filling pores, bridging cracks, or creating a mechanically different surface layer.

Quality control should span the entire test: establish texture and illumination baselines, predict deformed visibility and focus, monitor saturation, blur, and correlation quality during acquisition, and exclude invalid regions from mechanical interpretation. Wide interpolation improves appearance but cannot restore missing evidence.

## Why small complex parts are difficult to pattern

### Structural feature sizes vary widely

One view may include solid areas, slender members, pore edges, and sharp corners. A pattern suitable for a solid face can cover a strut, while a finer pattern may not create stable gray variation elsewhere.

### Surface normals change rapidly

Curvature and oblique faces change coating thickness, projected spot size, and brightness. A good front surface does not guarantee a measurable sidewall.

### Deep pores and recesses create shadows

Platens, fixtures, and the structure itself block light. As the geometry changes, a shadow boundary can move through the region and mimic texture motion.

### Coatings can alter the specimen

Slender or compliant microstructures can be sensitive to added layers. Thick primer, stiff coating, or clogged pores can change contact, mass, or stiffness.

## What is a correlatable texture?

A correlatable texture has sufficient gray variation, randomness, adhesion, and spatial scale under the actual imaging conditions. It should be judged in source images, not by visual attractiveness.

Check whether:

- large areas are saturated or black;
- projected feature size suits the correlation window;
- coating bridges neighboring members;
- oblique faces retain distinguishable features;
- texture survives friction, folding, and loading; and
- both stereo cameras observe the same texture.

## Pattern-preparation strategy

### Evaluate the native surface first

Assess color, reflectivity, porosity, and coating adhesion. Preserve usable natural texture where possible. If a base coat is needed, keep it thin, uniform, and compatible with the environment.

### Control scale in the image

Pattern size should be evaluated in pixels under the real lens and working distance, not by nominal spray-particle size. Prepare trial regions on a comparable artifact and select from real images.

### Avoid bridging pores and joints

For lattices and crack-sensitive parts, control spray direction and deposit so that a film does not bridge voids. Light stippling, transfer, or another material-compatible method may be preferable, with its influence documented.

### Preserve geometric boundaries

Pore edges, contact faces, and slender-member outlines must remain segmentable. The background, void, and specimen should not merge in gray appearance.

## Illumination design

### Prefer stability over raw brightness

A brighter source that creates glare, saturation, or thermal drift reduces quality. Seek stable, uniform illumination and an exposure short enough for the event.

### Use directional diversity to control shadows

Diffuse light from several directions can reduce hard shadows, but sources must not flicker or change color. Image gray levels should remain stable through the test.

### Separate specimen and background

The background appears through openings. Strong background texture can be correlated instead of the specimen. Use a low-reflectance, low-texture, contrasting background that does not move with the machine.

### Control motion blur

Buckling and fracture can accelerate suddenly. Design exposure for the fastest event of interest. A high frame rate does not compensate for an exposure that is too long.

## Visibility changes with deformation

Rotation, bending, contact, and occlusion evolve during compression. Before the formal test, use geometry, manual pose changes, or a low-load trial to check whether critical surfaces:

- leave the depth of field;
- become blocked by platens or neighboring members;
- approach a grazing view;
- develop specular reflection;
- overlap background texture; or
- exit the calibrated volume or image.

Define a valid observation stage for each critical region rather than assuming complete visibility.

## Quality gates during acquisition

### Source-image quality

Monitor gray distribution, saturation, focus, blur, and lighting stability. Automatic exposure and gain can change with specimen shape and should be used cautiously and logged.

### Correlation quality

Review residuals, confidence, failed points, and continuity. Quality metrics belong in the measurement evidence, not only in algorithm setup.

### Stereo consistency

Spatial DIC also needs stereo matching, reprojection, and common visibility. A clear image from one camera does not guarantee a reconstructable point.

### Spatial boundaries

Mixed subsets occur near pores, edges, and occlusion boundaries. Build masks from actual geometry and use separate regions when necessary so one subset does not cross specimen and background.

## Diagnosing image anomalies

| Observation | Possible image cause | Possible structural cause | Check |
|---|---|---|---|
| Hotspot follows a shadow | Moving illumination boundary | None | Source gray levels and light direction |
| Jagged edge strain | Mixed subset or mask error | Local concentration or crack | Mask and parameter sensitivity |
| Data disappears on a strut | Defocus, occlusion, texture loss | Folding or fracture | Both camera views and event frame |
| Entire field jumps | Camera or light disturbance | Transient load event | Stationary reference and synchronized load |
| Only one view changes | Glare or occlusion | Surface orientation change | Other camera and reprojection |

Image evidence and mechanical events must be reviewed together.

## Data boundaries after failure

Folding, contact, cracking, and material loss change surface topology. The original continuous correlation mesh may no longer apply. Mark tracking termination or divide the structure into independently trackable regions and move toward node, edge, or crack-face relative motion.

A fully occluded area is unobservable. Do not fill it with neighboring interpolation and interpret the result as measured strain.

## Repeatability and preparation records

Pattern variation between specimens changes measurable area and spatial resolution. Save preparation materials and steps, imaging distance, lighting, representative source images, and posttest surface condition. Repeatability should include image-quality comparability, not only mechanical curves.

For sensitive parts, use an unloaded coated control or compare mass and geometry before and after preparation to confirm that measurement preparation has not materially altered the specimen.

## Common mistakes

- applying flat-plate pattern settings to slender members and deep pores;
- checking only the frontal face and unloaded pose;
- allowing background texture to appear through voids;
- leaving automatic exposure uncontrolled during loading;
- letting one subset cross solid, void, and background;
- interpolating after texture loss; and
- failing to preserve source images and quality metrics.

## Independent platform perspective

A suitable DIC platform should support source-image checks, flexible masks, exportable quality metrics, invalid-point flags, separate-region tracking, and stereo reprojection diagnostics. Automatic filling is not a substitute for transparent data boundaries.

Acceptance should use representative geometry under expected light, distance, deformation, and occlusion. Low noise on a flat calibration plate does not prove that a complex structure remains measurable through failure.

## Frequently asked questions

### How should a small porous part be patterned for DIC?

Choose a thin, stable random texture based on projected pixel scale, avoid blocking pores or bridging struts, and validate adhesion and contrast on a representative artifact.

### Why does the background behind a pore matter?

A subset containing both specimen and background may correlate to the background, creating false edge displacement and strain.

### Why must both stereo cameras see the pattern?

Spatial reconstruction requires the same surface feature to be matched in both views. One clear view is insufficient.

### Can a moving shadow look like deformation?

Yes. It changes local gray values and can reduce quality or create a false hotspot. Stable diffuse lighting and source-image review are essential.

### What if the structure becomes occluded after folding?

Mark the region unobservable or use separate node and edge tracking. Interpolation cannot replace actual measurement.

## Conclusion

The first requirement for small-complex-part DIC is sustained visibility of the same surface. Pattern, illumination, background, depth of field, and occlusion form one measurement chain. Treating visibility as a deformation-dependent quantity—and marking failure honestly—prevents attractive contours from hiding missing evidence.

</details>

