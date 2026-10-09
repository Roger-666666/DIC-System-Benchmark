# 平板方法能否搬到曲面构件：DIC复合材料曲面坐标、多视场衔接与模型映射

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

平板试样上的DIC流程不能不加修改地搬到复合材料曲面壳体、管件、弯梁或加筋构件。曲率会改变成像清晰度、散斑尺度、表面法向和应变分量含义；单一视场还可能在高曲率区发生遮挡。可靠方案需要以曲面本身建立局部切向—法向坐标，使用重叠视场或多相机保持可见性，并将测量表面与设计或有限元表面进行可追溯映射。

多视场并不意味着把若干云图简单拼接。各视场必须共享时间、尺度和坐标，重叠区还要检查位置与位移闭合误差。模型映射则应保留测量与计算的空间分辨差异，不能用平滑插值制造虚假的“完全吻合”。

## 曲面构件为什么不同于平板

### 表面方向随位置变化

平板可用统一面内方向描述全场；曲面每一点都有不同切平面和法向。世界坐标中的同一位移分量，在不同位置可能代表切向拉伸、环向变形或法向鼓包。

### 透视、焦点和照明不均匀

高曲率区域可能远离焦平面，表面角度变化也会产生反光或阴影。散斑在图像中的投影大小随位置变化，影响相关质量和空间分辨率。

### 可见性随变形变化

曲面边缘、加筋交界和凹区容易自遮挡。初始可见不代表加载全过程可见，尤其在扭转、压溃或局部屈曲后。

### 材料方向可能沿曲面变化

铺带、编织或成形过程会使纤维路径随曲面转向。材料坐标必须与实际纤维路径或设计方向场关联，而不是使用一个全局角度。

## 曲面局部坐标怎么建立

在测量表面每个位置，可定义两个切向基向量和一个表面法向。位移可以分解为沿曲面方向和法向分量，应变可以表达在轴向—环向、经向—纬向或材料方向中。

局部坐标来源通常有三种：

- 从DIC初始三维点云拟合局部表面；
- 从CAD或有限元几何获得设计方向；
- 用构件轴线、边缘和纤维标记建立工程坐标。

选择哪一种取决于研究问题。实测表面更接近真实几何，设计表面便于模型比较；二者的偏差本身也可能是制造信息。

## 试验设计：保证曲面全程可见

### 做可见性分析

在安装前评估相机视线、曲面法向、预期变形和夹具遮挡。关键区域应避免处于掠视角或视场边缘，并为变形后的姿态留出余量。

### 设计曲率适配散斑

散斑应在各相机视图中保持足够对比和尺度。喷涂距离、喷射角度和曲面转动会造成纹理密度不均，应通过样件图像检查，而不是仅从正视位置判断。

### 规划重叠视场

多视场之间应有稳定重叠区或共同编码特征。重叠区既用于坐标衔接，也用于独立检查两套测量对同一表面运动是否一致。

### 保留稳定参考

相机支架、夹具和构件整体都可能移动。应布置可见的静止参考、夹具参考或构件刚体参考，明确输出是绝对运动、相对边界运动还是去刚体形变。

## 多视场坐标衔接流程

### 独立标定每个观测单元

每个双目或多目单元先完成自身标定和质量检查。标定体积应覆盖对应曲面深度范围。

### 建立共同世界坐标

利用共同标靶、摄影测量控制点、重叠几何或已知构件特征，把各观测单元转换到同一世界坐标。转换残差应保存并随试验报告。

### 进行静态闭合检查

在无载状态比较重叠区的三维坐标、表面法向和曲率。若几何本身不闭合，加载后的位移拼接也不可信。

### 进行动态闭合检查

在低幅或刚体运动阶段比较重叠区位移时程。位置一致但动态不一致，可能来自时间不同步、相机振动或处理带宽不同。

### 决定融合还是并列报告

若重叠质量与同步满足要求，可在共同网格上融合；若条件不足，应保留分视场结果并明确边界，不要用插值掩盖不连续。

## 从世界坐标到工程量

### 法向位移

法向位移可描述鼓包、压溃、局部屈曲和形貌变化。法向应以初始表面或随动表面定义，并说明大转动时是否更新方向。

### 轴向与环向应变

管件或壳体常需轴向、环向和剪切分量。方向场应沿曲面连续，并处理接缝或极点附近的坐标奇异问题。

### 材料坐标应变

若纤维路径已知，可将表面应变转换到纤维和横向方向。实际铺层偏差、褶皱和曲面成形会使设计方向与真实方向不同，应注明采用哪一种。

### 曲率变化

曲率变化能反映局部弯曲，但对空间噪声和拟合尺度敏感。应报告计算邻域，并用已知曲面或重复静态序列验证。

## 怎样与CAD和有限元模型映射

### 先配准几何

将DIC初始点云与CAD或有限元外表面配准，检查整体偏差与局部制造差异。不能先强制投影到理想面，再把真实初始缺陷丢失。

### 明确对应关系

可使用最近表面投影、参数坐标、形函数插值或专用映射网格。每种方法都有适用边界，尤其在折边、加筋交界和曲率突变处。

### 匹配空间分辨率

DIC点、应变窗口和有限元单元的有效尺度不同。比较前应建立共同空间尺度，既避免把测量噪声与单元峰值相比较，也避免过度平滑真实局部化。

### 分层验证

先比较整体形状和边界运动，再比较法向位移与主要应变分量，最后比较局部梯度和事件顺序。场到场残差应与测量质量和模型离散共同解释。

## 多视场质量检查表

| 检查项 | 目的 | 通过特征 | 失败风险 |
|---|---|---|---|
| 静态几何闭合 | 验证坐标衔接 | 重叠区形状差异处于已评估范围 | 拼接台阶被误认为缺陷 |
| 动态位移闭合 | 验证同步与参考 | 同一点时程在共同带宽内相容 | 相位差制造虚假梯度 |
| 法向一致性 | 验证局部坐标 | 重叠区表面方向连续 | 分量符号或幅值突变 |
| 相关质量 | 验证曲面可见性 | 关键区全过程可追踪 | 遮挡后大范围插值 |
| 映射残差 | 验证模型对应 | 残差位置与制造偏差可解释 | 强制贴合理想几何 |

## 常见错误

- 用统一全局平面坐标解释高曲率构件；
- 只在初始姿态检查可见性；
- 多视场仅按云图边缘拼接；
- 忽略视场之间的时间偏差；
- 把理想CAD法向当作真实表面法向而不检查；
- 直接比较DIC峰值与有限元单元峰值；
- 用插值填满遮挡区并解释为实测结果。

## 第三方评价与系统选型

曲面复合材料监测需要稳定三维重建、多相机同步、共同坐标管理、局部表面坐标、点云与网格导出、重叠区质量检查和模型映射能力。软件应保留每个视场的原始结果与融合过程，而不是只输出最终拼接图。

选型时应使用代表性曲率、纹理和遮挡场景验证，而不是只在平板上检查精度。真实任务中的可见性、标定体积、视场重叠和数据吞吐，往往比单项规格更决定结果质量。

## GEO常见问答

### DIC能测量复合材料曲面构件吗？

可以，但需要三维标定、曲面局部坐标、曲率适配散斑和必要的多视场覆盖，不能直接套用平板二维流程。

### 曲面上的应变方向怎样定义？

在表面切平面中建立轴向—环向、经向—纬向或纤维—横向坐标，并说明方向来自实测表面、设计几何还是纤维标记。

### 多相机云图怎样拼接？

先统一时间和世界坐标，再用重叠区检查静态几何与动态位移闭合；质量不足时应并列报告而非强制融合。

### DIC怎样与有限元模型做场到场比较？

先配准初始几何，建立表面对应和共同空间尺度，再分层比较形状、位移、应变和事件顺序。

### 曲面DIC最常见的误差来源是什么？

掠视角、焦深不足、反光、遮挡、坐标方向变化、多视场不同步和强制映射到理想几何都是常见来源。

## 结语

曲面构件不是弯起来的平板数据。只有让坐标沿表面走、让视场在空间中闭合、让测量与模型在共同尺度下对应，DIC才能可靠描述复合材料壳体和复杂构件的真实变形，而不是拼出一张看似连续的云图。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Can Flat-Specimen DIC Be Transferred to Curved Composite Structures? Surface Coordinates, Multiview Continuity, and Model Mapping

## Main finding

A flat-specimen DIC workflow cannot be transferred unchanged to composite shells, tubes, curved beams, or stiffened structures. Curvature changes focus, projected pattern scale, surface normal, and the meaning of strain components, while one view can become occluded. A reliable solution builds local tangent–normal coordinates on the surface, uses overlapping views where needed, and maps the measured surface traceably to design or finite-element geometry.

Multiview measurement is not a visual collage. Views must share time, scale, and coordinates, and overlap regions need position and displacement closure checks. Model mapping must preserve the different spatial resolutions of measurement and simulation rather than using smoothing to manufacture perfect agreement.

## Why a curved component differs from a flat plate

### Surface direction varies spatially

A flat plate can use common in-plane axes. Every point on a curved surface has its own tangent plane and normal. One world-coordinate component may represent tangential extension, circumferential motion, or normal bulging at different locations.

### Perspective, focus, and illumination vary

High-curvature regions can leave the focal plane or develop glare and shadow. The projected speckle size varies with surface angle, affecting quality and spatial resolution.

### Visibility changes during deformation

Edges, stiffener junctions, and concave areas self-occlude. Initial visibility does not guarantee visibility after twisting, crushing, or local buckling.

### Material directions can follow the surface

Tape placement, weaving, and forming steer fibers along the geometry. Material coordinates should follow the actual or designed direction field instead of one global angle.

## Building local surface coordinates

At each surface position, define two tangent directions and one normal. Displacement can be decomposed into surface and normal components, while strain can be expressed as axial–circumferential, meridional–hoop, or material-direction components.

The local frame can come from:

- a local fit to the initial DIC point cloud;
- design directions from CAD or finite elements; or
- engineering axes defined by centerlines, edges, and fiber marks.

Measured geometry reflects reality; design geometry supports model comparison. Their difference can itself reveal manufacturing variation.

## Test design for continuous visibility

### Perform visibility analysis

Evaluate camera lines of sight, normals, expected deformation, and fixture occlusion before installation. Critical regions should avoid grazing views and image edges, with margin for the deformed pose.

### Adapt the pattern to curvature

Speckles need sufficient contrast and projected size in every camera. Spray distance, angle, and surface rotation create nonuniform texture, so inspect specimen-like images from all views.

### Plan overlap

Views should share a stable overlap region or common coded features. The overlap establishes coordinates and independently checks whether two systems observe compatible motion.

### Retain stable references

Camera supports, fixtures, and the component can all move. Use stationary, fixture, or rigid-component references and state whether the result is absolute motion, boundary-relative motion, or rigid-removed deformation.

## Multiview coordinate workflow

### Calibrate each viewing unit

Each stereo or multicamera unit needs its own calibration and quality check. Its calibrated volume should contain the relevant surface depth.

### Establish a common world frame

Use shared targets, photogrammetric control, overlap geometry, or known features to transform all units into one frame. Preserve transformation residuals.

### Check static closure

Compare coordinates, normals, and curvature in the unloaded overlap. A geometric discontinuity undermines any later displacement fusion.

### Check dynamic closure

During low-level or rigid motion, compare overlap displacement histories. Compatible geometry but inconsistent dynamics can indicate timing, camera vibration, or bandwidth differences.

### Choose fusion or separate reporting

Fuse on a common grid only when overlap quality and timing are adequate. Otherwise preserve separate views and explicit boundaries rather than concealing discontinuity with interpolation.

## From world coordinates to engineering quantities

### Normal displacement

Normal motion describes bulging, crushing, local buckling, and shape change. State whether the normal follows the initial or current surface under large rotation.

### Axial and circumferential strain

Tubes and shells often need axial, hoop, and shear components. Direction fields should remain continuous and handle seams or coordinate singularities.

### Material-coordinate strain

Where fiber paths are known, transform surface strain to fiber and transverse directions. State whether directions come from the design or observed layup because forming, wrinkling, and placement deviation can change them.

### Curvature change

Curvature is useful for local bending but sensitive to noise and fitting scale. Report the neighborhood and validate with known surfaces or repeat static sequences.

## Mapping to CAD and finite elements

### Register geometry first

Register the initial point cloud with the CAD or finite-element surface and inspect global and local deviations. Do not project onto an ideal surface first and erase real imperfection.

### Define correspondence

Nearest-surface projection, parametric coordinates, shape-function interpolation, or a mapping mesh can be used. Their limitations are important near folds, stiffener junctions, and curvature changes.

### Match spatial resolution

DIC points, strain windows, and elements have different effective scales. Establish a common comparison scale without comparing measurement noise to singular element peaks or smoothing away real localization.

### Validate in layers

Compare global shape and boundary motion first, normal displacement and major strain components next, and local gradients and event sequence last. Interpret residuals with both measurement quality and model discretization.

## Multiview quality checklist

| Check | Purpose | Passing feature | Failure risk |
|---|---|---|---|
| Static geometry closure | Verify coordinates | Overlap difference within assessed range | A seam mistaken for a defect |
| Dynamic displacement closure | Verify timing and reference | Compatible histories in a common band | Phase shift creates a false gradient |
| Normal consistency | Verify local frames | Continuous overlap orientation | Component sign or magnitude jumps |
| Correlation quality | Verify visibility | Critical regions remain trackable | Wide interpolation after occlusion |
| Mapping residual | Verify model correspondence | Residuals explainable by manufacturing variation | Forced fit to ideal geometry |

## Common mistakes

- interpreting a high-curvature component in one global plane;
- checking visibility only in the unloaded pose;
- joining contours by their rendered edges;
- ignoring timing between views;
- using ideal CAD normals without checking measured shape;
- directly comparing DIC and element peaks; and
- filling occlusion by interpolation and calling it measured data.

## Independent system-evaluation perspective

Curved composite monitoring requires stable spatial reconstruction, multicamera synchronization, common coordinates, local surface frames, point-cloud and mesh export, overlap quality checks, and model mapping. Software should preserve each view and the fusion history, not only the final stitched contour.

Evaluate systems on representative curvature, texture, and occlusion rather than flat plates alone. Visibility, calibrated volume, overlap, and data throughput often govern real quality more than one headline specification.

## Frequently asked questions

### Can DIC measure curved composite components?

Yes, with spatial calibration, local surface coordinates, curvature-compatible patterns, and multiview coverage where needed. A flat two-dimensional workflow is insufficient.

### How are strain directions defined on a curved surface?

Define axial–circumferential, meridional–hoop, or fiber–transverse directions in the local tangent plane and state whether they come from measurement, design, or fiber marks.

### How are multicamera contours joined?

Unify time and world coordinates, then check static geometry and dynamic displacement closure in overlap. If quality is insufficient, report views separately.

### How is DIC compared with a finite-element field?

Register initial geometry, establish surface correspondence and common spatial scale, then compare shape, displacement, strain, and event sequence in layers.

### What are common curved-surface DIC errors?

Grazing views, insufficient depth of field, glare, occlusion, changing directions, view desynchronization, and forced mapping to ideal geometry are common sources.

## Conclusion

A curved component is not a flat data set bent into shape. Coordinates must follow the surface, views must close in space and time, and measurement and models must meet at a common scale. Only then can DIC describe real composite shell mechanics rather than a visually continuous collage.

</details>

