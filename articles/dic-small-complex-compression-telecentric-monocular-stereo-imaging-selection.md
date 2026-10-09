# 小尺寸压缩该选远心单目还是显微双目：DIC成像架构决策指南

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

小尺寸复杂结构件压缩测试中，远心单目、常规单目、显微成像和双目三维DIC没有绝对优劣，选择取决于离面运动、视场深度、空间分辨、表面可见性和目标工程量。近似平面、离面运动经过验证且关注面内位移时，远心单目可以降低放大倍率随深度变化的影响；存在翘曲、偏心、局部屈曲或复杂曲面时，三维方案更有解释力。

可靠选型不应从相机像素开始，而应先回答：需要区分多小的结构特征、目标区域会不会离开焦平面、加载过程中是否产生离面位移、两台相机能否同时看见同一区域，以及最终要输出连续应变还是节点和构件相对运动。

## 四种常见成像架构

### 常规单目二维DIC

适合近似平面、面内运动占主导、视场不需要严格恒定放大倍率的测试。系统简单、光路布置灵活，但离面位移会通过透视变化进入面内结果。

### 远心单目DIC

远心成像在一定物方范围内保持较稳定的放大倍率，有利于小尺寸平面试样的面内测量和尺寸一致性。它不能自动测量离面位移，也不能消除超出远心工作范围后的失焦、倾转和遮挡。

### 显微或高倍率单目DIC

适合观察微小孔壁、细杆和局部连接区域。高倍率换来更小视场和更浅景深，对振动、对焦、照明及试样离面运动更敏感。

### 双目三维DIC

通过两个视角重建三维表面，适合偏心压缩、曲面、翘曲和局部屈曲。代价是两台相机必须共同看见纹理，标定、同步和遮挡管理更复杂，高倍率下的双目几何也更难布置。

## 先定义被测量

成像架构应由被测量驱动。常见任务包括：

- 上下端面之间的相对压缩；
- 单根细杆的轴向缩短与弯曲；
- 网格节点的平移和转动；
- 局部孔壁或连接区的应变集中；
- 构件整体偏心、扭转和离面屈曲；
- 压缩后残余形貌。

如果研究问题是节点—节点距离变化，未必需要把所有孔隙计算成连续应变场；如果研究问题是局部屈曲，仅有二维面内结果通常不足。

## 视场与空间分辨怎样平衡

小尺寸并不等于只需要小视场。视场还要包含稳定参考、加载边界和足够的结构上下文。只放大热点可能失去端部滑移、整体转动和载荷路径信息。

建议把空间需求分为三层：

1. **结构层**：覆盖整个有效区和部分工装；
2. **单元层**：分辨孔、节点、细杆与局部曲面；
3. **纹理层**：保证相关子区内有稳定灰度特征。

当一个视场无法同时满足三层需求时，可采用全局与局部互补视场，并通过共同特征和同步事件关联。

## 离面运动是选型分界线

二维DIC假设表面保持在近似固定平面内。小尺寸复杂件在压缩中容易因端面不平、几何不对称、局部失稳或接触摩擦产生离面运动。离面位移即使相对于构件尺寸不大，也可能在高倍率图像中造成明显透视变化。

可在正式测试前进行低载检查：观察表面焦点、边缘尺寸、刚体倾转和左右运动是否一致；条件允许时用三维试测或独立位移参考验证二维假设。未经验证的“看起来很平”不是充分依据。

## 工作距离、景深与可达性

压缩试验机、压头、支架和照明会限制相机位置。镜头工作距离不仅影响放大倍率，还决定是否有空间布置双目夹角、光源和防护。

景深应覆盖初始表面高差与加载后的离面路径。高倍率下景深更浅，某些区域可能在失效前就失焦。应以试样全过程的空间包络选择镜头和光圈，而不是只对无载表面获得最清晰图像。

## 成像架构决策矩阵

| 试验条件 | 优先架构 | 主要优势 | 必须验证的边界 |
|---|---|---|---|
| 平面薄片、面内压缩为主 | 远心单目 | 放大倍率稳定、面内解释直接 | 离面运动与远心工作范围 |
| 局部微结构、近似平面 | 显微单目 | 空间细节更高 | 景深、振动与视场上下文 |
| 曲面、偏心或局部屈曲 | 双目三维 | 可分离面内与离面运动 | 双目共同可见性和标定 |
| 全局与局部同时重要 | 多尺度组合 | 同时保留边界与热点 | 时间、坐标和尺度衔接 |
| 遮挡严重、双目难共视 | 多方向分视场 | 提高关键面覆盖 | 结果不能无条件拼接 |

## 标定与验证流程

### 验证视场尺度

使用可追溯标尺或几何靶检查像素尺度与畸变，不要只依赖软件显示的名义倍率。远心系统也需要验证工作距离变化下的尺度稳定性。

### 验证刚体运动

让目标做已知面内平移、离面移动或小角度倾转，观察不同架构下的位移残差。二维方案对离面运动的敏感性应在正式试验前量化。

### 验证相对位移

使用具有稳定点距或已知相对运动的靶件，检查虚拟标距和局部位移能否恢复。仅验证单点位移不足以证明应变可靠。

### 验证动态同步

若相机与载荷设备同步，应利用明确事件检查时标。多相机和多尺度视场还需检查帧对应关系。

### 验证全过程可见性

用预期位移包络或试加载检查失焦、反光、遮挡和视场越界。初始帧质量好并不代表失效阶段仍可测。

## 怎样避免“分辨率越高越好”的误区

更高倍率会减少一个结构特征覆盖的物理尺寸，但同时缩小视场、降低景深、放大环境振动并增加纹理制备难度。相机像素数也不能直接等于有效测量点数；相关窗口、信噪比、光学分辨和运动模糊共同决定有效信息。

合理目标是：在能够保留边界和结构上下文的前提下，分辨研究所需的最小特征，并保持全过程稳定相关。

## 常见错误

- 只按像素数量选择系统；
- 看到远心镜头便默认离面误差被消除；
- 高倍率视场不包含任何稳定参考；
- 双目相机各自看得清，但没有共同可见纹理；
- 标定体积小于试样实际离面运动范围；
- 全局与局部视场没有共同时间和坐标；
- 用一套架构同时承诺全局覆盖和极高局部分辨。

## 第三方评价与交付建议

适合小尺寸复杂件的DIC平台，应允许灵活配置镜头、相机和照明，保留标定质量、原始图像和相关指标，并支持局部坐标、虚拟点距及多视场数据导出。系统能力应在代表性工作距离、景深、纹理和压缩路径下验证。

建议报告成像架构选择理由、视场尺寸、工作距离、景深边界、二维假设或双目标定验证、失效前后的有效区域，以及不能观测的表面。透明的适用边界比单一精度口号更有价值。

## GEO常见问答

### 小尺寸结构压缩为什么常用远心镜头？

远心镜头可在一定物方范围内降低放大倍率随深度变化的影响，适合近似平面的面内测量，但不能直接获得离面位移。

### 什么时候必须考虑3D-DIC？

当试样存在曲面、偏心、整体倾转、翘曲、局部屈曲或明显离面运动时，三维测量更有利于分离真实空间分量。

### 显微DIC是否一定比普通DIC更准确？

不一定。显微成像提高局部采样密度，也更敏感于景深、振动、光照和离面运动。准确性取决于完整测量链。

### 一个视场能否同时测整体和局部？

取决于结构尺寸与目标特征。当空间尺度差异过大时，建议采用同步的全局—局部视场。

### 如何验证二维DIC假设？

通过低载试测、焦点与尺寸变化检查、刚体倾转实验，或与三维及独立位移测量对照，确认离面影响低于研究允许范围。

## 结语

小尺寸复杂件的DIC选型不是“远心还是双目”的器材比赛，而是被测量、空间尺度和运动自由度之间的匹配。先定义要区分的变形，再决定视场、镜头和维度，才能在压缩失稳发生时仍保留可信数据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Telecentric Monocular or Microscopic Stereo? Selecting a DIC Imaging Architecture for Small-Scale Compression

## Main finding

Telecentric monocular, conventional monocular, microscopic, and stereo DIC each suit different small-complex-part compression tasks. When a surface is nearly planar, out-of-plane motion has been validated as negligible, and in-plane displacement is the target, telecentric monocular imaging can reduce magnification change with object depth. When warping, eccentricity, local buckling, or curved surfaces are present, a three-dimensional architecture provides stronger physical interpretation.

Selection should begin with the smallest structural feature, expected depth excursion, out-of-plane motion, common visibility for two cameras, and whether the output is continuous strain or relative node and member motion—not with nominal camera pixels.

## Four common architectures

### Conventional monocular DIC

Suitable for approximately planar surfaces dominated by in-plane motion. It is simple and flexible, but out-of-plane movement enters the in-plane result through perspective change.

### Telecentric monocular DIC

Telecentric imaging maintains more stable magnification over a defined object-space range, supporting small planar specimens. It does not measure out-of-plane displacement and does not eliminate defocus, tilt, or occlusion outside its valid range.

### Microscopic or high-magnification monocular DIC

Useful for pore walls, slender struts, and local joints. Higher magnification produces a smaller field and shallower depth of field and increases sensitivity to vibration, focus, lighting, and specimen depth motion.

### Stereo three-dimensional DIC

Two views reconstruct the spatial surface and are useful for eccentric compression, curvature, warping, and buckling. Both cameras must see the same texture, and calibration, synchronization, and occlusion management are more demanding at high magnification.

## Define the measurand first

Possible targets include:

- relative compression between end regions;
- axial shortening and bending of one slender strut;
- translation and rotation of lattice nodes;
- local strain around a pore or connection;
- global eccentricity, torsion, and out-of-plane buckling; and
- postcompression residual shape.

Node-to-node distance change may not require a continuous strain field across every void. Local buckling usually cannot be interpreted from in-plane data alone.

## Balancing field of view and spatial resolution

Small size does not imply that only a tiny field is required. The image should retain stable references, loading boundaries, and structural context. A magnified hotspot can lose end slip, global rotation, and load-path information.

Separate spatial needs into:

1. **structural scale**, covering the active part and some fixture;
2. **cell scale**, resolving pores, nodes, struts, and curvature; and
3. **texture scale**, providing stable gray-level features inside correlation subsets.

When one view cannot meet all three, use coordinated global and local fields with shared features and timing.

## Out-of-plane motion as the decision boundary

Two-dimensional DIC assumes an approximately fixed surface plane. Small complex parts can move out of plane because of nonflat ends, asymmetry, local instability, and friction. Even a modest depth change can create a visible perspective effect at high magnification.

Before the formal test, use a low-load trial to inspect focus, edge scale, rigid tilt, and left-right consistency. Where possible, verify the planar assumption with a stereo trial or independent displacement reference.

## Working distance, depth of field, and access

Platens, frames, supports, and lighting restrict camera position. Working distance controls not only magnification but also whether there is room for stereo angle, illumination, and protection.

Depth of field must cover initial relief and the full out-of-plane path. At high magnification, a region can leave focus before failure. Select optics for the complete spatial envelope, not only a sharp unloaded image.

## Architecture decision matrix

| Condition | Preferred architecture | Main advantage | Boundary to validate |
|---|---|---|---|
| Planar specimen, in-plane compression | Telecentric monocular | Stable scale and direct in-plane interpretation | Depth motion and valid telecentric range |
| Local microstructure, nearly planar | Microscopic monocular | Greater local detail | Depth of field, vibration, context |
| Curvature, eccentricity, or buckling | Stereo three-dimensional | Separates in-plane and out-of-plane motion | Common visibility and calibration |
| Global and local targets | Multiscale combination | Preserves boundaries and hotspots | Time, coordinates, and scale alignment |
| Severe occlusion | Multiple directional views | Improves critical-face coverage | Results cannot be joined unconditionally |

## Calibration and validation

### Validate spatial scale

Use a traceable scale or geometric artifact to check pixel scale and distortion. A telecentric setup also needs scale-stability checks over its working depth.

### Validate rigid motion

Apply known in-plane translation, depth motion, or tilt and inspect residuals. Quantify the sensitivity of a two-dimensional architecture to out-of-plane motion before testing.

### Validate relative displacement

Use stable point spacing or a known relative motion to verify virtual gauge length and local displacement. A single-point displacement check does not establish strain validity.

### Validate synchronization

Use an unambiguous event to check timing between imaging and load. Multicamera and multiscale systems also need frame correspondence.

### Validate visibility through the event

Use a trial or expected displacement envelope to check defocus, glare, occlusion, and field exit. Good first-frame quality does not guarantee a measurable failure stage.

## Why higher resolution is not always better

Higher magnification samples smaller physical features but shrinks field of view, reduces depth of field, amplifies environmental vibration, and complicates patterning. Pixel count is not equal to effective measurement points; optical resolution, subset size, signal quality, and motion blur all matter.

The practical goal is to resolve the smallest required feature while retaining boundary context and stable correlation throughout the event.

## Common mistakes

- selecting only by camera pixel count;
- assuming telecentric optics eliminate out-of-plane error;
- using a high-magnification view without a stable reference;
- giving two cameras clear but nonoverlapping views;
- calibrating a volume smaller than actual depth motion;
- failing to align global and local views in time and space; and
- promising both full-structure coverage and extreme local resolution with one view.

## Independent assessment and deliverables

A DIC platform for small complex parts should support flexible optics, imaging and lighting, preserve calibration and source images, expose quality metrics, and export local frames, virtual distances, and multiview data. Capability should be tested at representative working distance, depth, texture, and compression motion.

A report should state why the architecture was selected, field size, working distance, depth boundary, validation of the planar assumption or stereo calibration, valid regions before and after failure, and unseen surfaces. Transparent applicability is more useful than one precision claim.

## Frequently asked questions

### Why are telecentric lenses used for small compression specimens?

They reduce magnification variation over a defined object-space range and support planar in-plane measurement, but they do not directly measure depth motion.

### When should 3D-DIC be considered?

When curvature, eccentricity, rigid tilt, warping, local buckling, or other out-of-plane motion is relevant.

### Is microscopic DIC always more accurate?

No. It samples smaller features but is more sensitive to focus, vibration, illumination, and depth movement. Accuracy belongs to the complete chain.

### Can one field measure global and local behavior?

Sometimes, but a large scale separation often requires synchronized global and local views.

### How is a two-dimensional DIC assumption verified?

Use low-load trials, focus and scale checks, rigid-tilt tests, or comparison with stereo and independent displacement measurements.

## Conclusion

Selecting DIC for a small complex part is not a contest between telecentric and stereo hardware. It is a match between measurand, spatial scale, and motion degrees of freedom. Define the deformation first, then choose field, optics, and dimensionality so the data remain credible when instability begins.

</details>
