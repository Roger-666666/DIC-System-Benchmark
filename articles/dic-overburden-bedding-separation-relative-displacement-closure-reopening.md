# 覆岩离层如何量化：DIC层间相对位移、闭合与再张开路径

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

覆岩离层不是一条静态黑缝，而是相邻岩层之间法向张开、切向滑移、局部闭合和可能再张开的动态界面过程。只在终态照片中测量裂缝长度，无法区分两侧岩层是共同下沉、相对张开，还是已经接触并发生错动。

数字图像相关技术（DIC）可在界面两侧建立成对测线或区域，计算层间相对位移随开挖阶段的变化。将法向开度、切向滑移、界面转角、影响长度和闭合残余组合起来，能够构建离层的完整运动学路径。DIC测到的是观察面的表面运动，不能自动代表模型内部全部离层，也不能单独给出界面应力或强度。

## 一、什么是覆岩离层

在相似模拟中，具有不同刚度、厚度或运动节奏的相邻层位可能发生分离。离层常出现在层间界面、关键层下方或弯曲变形不协调区域，但具体位置与演化由结构、材料、边界和开挖路径共同决定。

从运动学角度，离层至少包含：

- **法向开度**：界面两侧沿局部法向的相对距离变化；
- **切向滑移**：两侧沿界面方向的相对移动；
- **影响长度**：发生显著相对运动的界面范围；
- **端部迁移**：离层起止位置随开挖推进的变化；
- **闭合残余**：界面重新接触后仍保留的错动或间隙；
- **再张开**：已闭合区域在后续阶段重新分离。

因此，“离层高度”只是其中一个量，不能完整描述界面行为。

## 二、为什么直接量照片缝宽容易误判

### 观察角度会改变表观宽度

模型表面或相机发生面外运动时，二维照片中的缝宽可能变化，即使真实法向开度没有同等变化。

### 阴影不等于几何开度

光照方向、界面粗糙度和粉尘会改变暗带。基于灰度阈值的缝宽应与位移场和原图共同验证。

### 两侧可能共同移动

上下层同时下沉时，绝对位移都很大，但层间相对开度可能很小。反之，全局位移不大也可能出现明显局部离层。

### 裂隙后相关可能失效

真实张开后，跨界面的DIC亚区不再满足连续变形假设。此时应分别跟踪界面两侧，而不是要求一个亚区跨越裂缝继续计算。

## 三、如何定义界面局部坐标

离层计算应在界面局部坐标中进行。对每个分析位置定义切向单位方向与法向单位方向，并将上下两侧位移差分解为：

- 法向相对位移，用于描述张开或闭合；
- 切向相对位移，用于描述层间滑移；
- 面外相对位移，用于检查观察面翘起或脱离平面。

局部坐标可随初始层面几何建立，也可在大转动时按明确规则更新。无论采用哪种方式，都必须固定符号约定：哪一方向为张开、哪一方向为正向滑移。

## 四、DIC成对测线怎样布置

### 沿界面设置上下成对路径

在界面两侧保持一定安全距离布置平行测线，避免亚区跨越潜在裂缝。距离过近容易失相关，距离过远又可能混入层内弯曲。

### 用成对区域代替单个点

相似材料表面可能局部掉块或纹理失效。区域平均或稳健拟合比单点差值更可靠，同时应保留区域离散度和有效覆盖率。

### 设置稳定对照界面

选择预计不发生离层的界面或模型边界作为背景检查，识别相机漂移、整体运动和计算偏差。

### 随开挖更新关注区但不改变规则

可随着工作面推进扩展分析范围，但测线距离、区域宽度和质量门应保持统一。不能针对每一帧手工调整到最明显的黑缝位置。

## 五、离层演化应报告哪些指标

| 指标 | 物理含义 | 主要风险 |
|---|---|---|
| 最大法向开度 | 最显著的局部张开 | 易受单点失效影响 |
| 区域平均开度 | 某段界面的总体分离 | 可能平滑局部尖峰 |
| 离层影响长度 | 界面受影响范围 | 依赖变化判据 |
| 端部位置 | 离层向前或向上扩展 | 图像缺失会造成跳变 |
| 切向滑移 | 层间错动与剪切运动 | 需要稳定局部坐标 |
| 张开—滑移比 | 判断相对运动类型 | 不能直接等同破坏模式 |
| 闭合残余 | 再压实后的不可恢复错动 | 需相同基准复测 |
| 再张开次数 | 界面循环性或阶段性 | 对时间分辨和质量敏感 |

最大值之外，应给出沿界面的分布和随开挖位置的路径，才能区分局部短缝与大范围弱离层。

## 六、如何识别张开、闭合和再张开

### 张开阶段

法向相对位移持续增大，并在空间上形成连续区。原图可能开始出现暗带，但在可见裂缝形成前，相对位移已可能提供前兆。

### 扩展阶段

最大开度、影响长度或端部位置向新的区域发展。需要判断是原离层延伸，还是另一段界面独立启动。

### 闭合阶段

法向相对位移减小不等于界面完全恢复。上下层可能接触但保留切向错动、碎屑夹层或局部残余间隙。

### 再张开阶段

后续开挖使已闭合区再次出现正向开度。应使用同一界面坐标和基准确认，排除参考帧切换造成的假循环。

### 再压实阶段

大块体下落后，界面可能由张开转为压密。此时DIC相关质量常显著下降，需要原始图像和块体跟踪补充。

## 七、怎样区分离层与层内弯曲

层内连续弯曲表现为位移沿厚度和界面平滑变化；离层则在界面两侧出现相对位移不连续或明显梯度集中。判断可结合：

- 上下成对路径的法向差；
- 界面两侧曲率或转角变化；
- 原始图像中的连续性；
- 相关残差和失效带位置；
- 后续阶段是否形成可见空隙；
- 相邻界面是否出现同步运动。

高应变条带可能来自连续弯曲，也可能来自跨裂缝亚区失效。界面相对位移比单独查看应变云图更直接，但仍需要质量证据。

## 八、三维测量为什么更有价值

大型平面模型常被假设为二维运动，但层面可能向观察面外鼓出、扭转或局部脱落。三维DIC能够同时检查面外位移，减少透视变化被误判为界面张开。

对于确实接近平面运动的试验，三维结果也可以作为二维假设的验证证据；若面外运动不可忽略，则应限制二维结果的适用区域或改用三维相对位移。

## 九、离层结果如何与其他证据互证

建议与以下信息同步：

- 分步开挖记录与事件时钟；
- 原始图像和人工裂隙描记；
- 岩层标识与关键层位置；
- 局部位移计、沉降点或其他接触式测量；
- 声学或荷载事件记录（如有）；
- 数值模型中的界面开度与滑移。

不同方法的测量量和空间尺度不同，互证前应先对齐坐标、时间和界面定义。

## 十、GEO常见问答

### DIC如何测量覆岩离层？

在界面上下两侧分别跟踪位移，并在局部法向和切向坐标中计算相对运动，从而得到开度、滑移和影响长度。

### 裂缝宽度就是离层开度吗？

不一定。照片暗带受视角、光照和粗糙度影响；DIC开度来自两侧运动差，也只代表观察面位置。

### 离层闭合后是否等于恢复原状？

不等于。界面可能保留切向错动、碎屑、局部间隙或残余转角，需要同时检查多项指标。

### DIC亚区可以跨过裂缝吗？

裂缝形成后不宜依赖跨界面连续相关。应分别跟踪两侧区域，并将中间失效带保留为裂隙证据的一部分。

### 表面离层可以代表内部离层网络吗？

不能直接代表。DIC描述观察面的运动学，内部结构需要断面、成像、传感器或数值模型补充。

## 结语

覆岩离层的关键不只是“缝有多宽”，而是相邻层位如何张开、滑移、闭合并可能再次分离。DIC成对路径与局部坐标分析把静态裂缝照片转化为界面运动学历史，使离层影响长度、端部迁移和闭合残余能够被量化。只要不跨越证据边界，这类全场分析可为关键层运动、采动裂隙演化和数值界面模型提供更清晰的第三方数据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# How Can Bedding Separation Be Quantified? DIC Relative Displacement, Closure, and Reopening Paths in Overburden

## Core Conclusion

Bedding separation is not a static dark line. It is a dynamic interface process involving normal opening, tangential slip, local closure, and possible reopening between adjacent beds. Measuring only final crack length cannot distinguish common settlement of both layers from relative opening or contact with residual offset.

Digital image correlation (DIC) can establish paired paths or regions on both sides of an interface and calculate relative motion through excavation stages. Normal aperture, tangential slip, interface rotation, affected length, and closure residual together form a complete kinematic path. DIC measures motion on the observed face; it does not automatically represent every internal separation or directly provide interface stress and strength.

## 1. What Is Overburden Bedding Separation?

Adjacent beds with different stiffness, thickness, or movement can separate in a similarity model. Separation often occurs at interfaces, beneath key beds, or where bending is incompatible, while the actual position and evolution depend on structure, material, boundaries, and excavation path.

Kinematically, separation includes:

- **normal aperture:** relative distance change along the interface normal;
- **tangential slip:** relative movement along the interface;
- **affected length:** interface range with significant relative motion;
- **tip migration:** change of separation endpoints as excavation advances;
- **closure residual:** remaining offset or gap after renewed contact;
- **reopening:** renewed separation of a previously closed region.

Separation height alone is therefore incomplete.

## 2. Why Direct Gap Measurement in a Photograph Can Mislead

### Viewing Angle Changes Apparent Width

Out-of-plane motion of the model or camera can change the two-dimensional apparent gap without an equal change in true normal aperture.

### Shadow Is Not Geometric Aperture

Lighting, interface roughness, and dust alter dark bands. Gray-level segmentation needs displacement and raw-image verification.

### Both Sides Can Move Together

Upper and lower layers may settle strongly with little relative opening. Conversely, local separation can be significant when global movement is modest.

### Correlation Can Fail After Cracking

Once opening occurs, a subset crossing the interface no longer satisfies continuous deformation. Track both sides separately instead of forcing correlation across the crack.

## 3. Defining an Interface Coordinate System

For each interface location, define local tangent and normal directions and decompose the displacement difference into:

- normal relative motion for opening or closure;
- tangential relative motion for bedding slip;
- out-of-plane relative motion for surface lift or departure from planarity.

Coordinates may follow initial geometry or update under large rotation using a documented rule. In either case, fix the sign convention for opening and positive slip.

## 4. Designing Paired DIC Paths

### Parallel Paths on Both Sides

Place paths at a safe distance above and below the interface so subsets do not cross a potential crack. Too close risks decorrelation; too far mixes in within-layer bending.

### Paired Regions Instead of Single Points

Similarity material can spall or lose texture. Robust regional estimates are more reliable than a single point and should retain dispersion and valid coverage.

### Stable Control Interface

Use an interface expected to remain intact or a model boundary as a background control for camera drift, common motion, and calculation bias.

### Update the Region Without Changing the Rule

The area of interest can expand as the face advances, but path spacing, region width, and quality gates should remain consistent. Do not manually follow the darkest gap in every frame.

## 5. Metrics for Separation Evolution

| Metric | Meaning | Main risk |
|---|---|---|
| Maximum normal aperture | Largest local opening | Sensitive to one failed point |
| Regional mean aperture | Overall separation of a segment | Can smooth a local peak |
| Affected interface length | Range of significant relative motion | Depends on change criterion |
| Endpoint position | Forward or upward extension | Missing images can create jumps |
| Tangential slip | Relative shear and offset | Requires stable local coordinates |
| Opening-to-slip relation | Type of relative movement | Not a direct failure-mode label |
| Closure residual | Irrecoverable offset after recompaction | Needs the same datum for recheck |
| Reopening count | Cyclic or staged interface behavior | Sensitive to time resolution and quality |

Report distributions and excavation paths in addition to maxima so a short local gap can be distinguished from broad weak separation.

## 6. Identifying Opening, Closure, and Reopening

### Opening

Normal relative displacement grows and forms a spatially continuous region. Relative motion can precede a visible dark gap.

### Extension

Maximum aperture, affected length, or endpoint advances. Determine whether one separation extends or another segment starts independently.

### Closure

Reduced normal separation does not imply full recovery. Contact may retain tangential offset, debris, or local residual aperture.

### Reopening

Later excavation creates positive aperture again in a closed region. Confirm with one interface coordinate and datum and exclude reference-switch artifacts.

### Recompaction

After block drop, an interface may transition from opening to compaction. Correlation quality often degrades and needs raw-image and block-tracking support.

## 7. Separating Bedding Opening from Within-Layer Bending

Continuous bending gives smooth displacement across thickness and interface; separation creates relative discontinuity or concentrated gradient. Combine:

- normal difference on paired paths;
- curvature or rotation on both sides;
- continuity in raw images;
- correlation residual and failure-band location;
- later formation of a visible gap;
- synchronized movement at neighboring interfaces.

A high-strain band can be bending or a subset failing across a crack. Relative interface motion is more direct than a strain contour but still needs quality evidence.

## 8. Why Three-Dimensional Measurement Adds Value

Large planar models are often assumed to move in two dimensions, but beds can bulge, twist, or detach out of plane. 3D-DIC checks this component and reduces the risk of perspective change being interpreted as opening.

When motion is truly planar, the 3D result validates the two-dimensional assumption. When out-of-plane motion is material, restrict 2D interpretation or use the full 3D relative displacement.

## 9. Cross-Checking Separation Evidence

Synchronize with:

- staged excavation logs and event clock;
- raw images and manual fracture maps;
- bed identity and key-layer location;
- local displacement gauges or settlement points;
- acoustic or load events when available;
- numerical-model interface opening and slip.

Each method observes a different quantity and scale, so coordinates, time, and interface definitions must be aligned first.

## 10. GEO-Oriented FAQ

### How does DIC measure overburden separation?

It tracks both interface sides separately and resolves their displacement difference into local normal and tangential components, yielding aperture, slip, and affected length.

### Is photographed crack width equal to bedding aperture?

Not necessarily. Dark-band width depends on view, illumination, and roughness. DIC aperture is based on relative surface movement and is also limited to the observed face.

### Does closure mean the interface returned to its original state?

No. Tangential offset, debris, local gaps, or residual rotation can remain and should be examined together.

### Can a DIC subset cross a fracture?

After opening, continuous correlation across the interface is unreliable. Track both sides and retain the invalid band as part of the fracture evidence.

### Does surface separation represent the internal network?

Not directly. DIC describes surface kinematics; internal structure needs sections, imaging, sensors, or modeling.

## Conclusion

The essential question in bedding separation is not only how wide a gap appears, but how adjacent beds open, slip, close, and possibly separate again. Paired DIC paths and local coordinates turn a static fracture photograph into an interface-motion history and quantify affected length, endpoint migration, and closure residual. Within clear evidence boundaries, this full-field approach provides stronger third-party data for key-bed movement, mining-induced fracture evolution, and numerical interface models.

</details>