# 压板摩擦还是材料记忆：DIC边界诊断避免误判海绵恢复性能

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 先给结论

海绵卸载后出现慢恢复、边缘滞后或残余凹陷，未必全部来自材料“记忆”。压板摩擦、压板不平行、试样滑移、表面散斑层、相机漂移和离面运动都可能制造相似的全场图像。

可靠的DIC方案不只是测量试样，而是同步观察试样、接触边界和稳定参考，并通过对照工况主动证伪伪差。只有当异常跟随材料而不是跟随夹具、相机或处理参数变化时，才适合把它解释为材料恢复特征。

## “材料记忆”与“测试系统记忆”

材料记忆是材料在加载历史作用下表现出的时间依赖和路径依赖。测试系统也可能保留历史：夹具回差、压板粘附、机架顺应性、相机支架松动、自动曝光变化以及处理参考更新，都可能让后一次状态依赖前一次状态。

二者在单点曲线上可能十分相似。例如，压板缓慢脱离会被看作海绵延迟回弹；相机缓慢漂移会产生虚假的残余位移；摩擦限制横向扩张会改变中心区域的压缩形态。

DIC的优势在于这些误差通常具有不同的空间签名。诊断目标是先找到签名，再设计能使竞争解释产生不同预测的对照试验。

## 五类常见误判及其空间特征

### 压板摩擦

摩擦会限制接触面的横向运动，使边缘、中心和厚度方向形成复杂梯度。加载与卸载时摩擦状态还可能不同，产生类似滞回的路径差。

典型检查包括：比较不同接触面处理；观察贴近压板区域与自由侧面的横向位移；检查上下接触是否对称；记录试样是否相对压板滑动。若改变接触条件后“材料记忆”显著改变，原结论必须重新界定为材料—边界耦合响应。

### 压板不平行与偏心加载

压板轻微倾斜可让一侧先接触，形成斜向压缩带、侧向弯曲和不对称恢复。整体压缩量仍可能正常，因此仅看试验机位移无法识别。

三维DIC可测量上表面或侧面的倾转与空间位移。也可在刚性或高刚度对照件上检查压板运动，并将试样旋转后复测：若异常固定在实验室方向，边界因素更可疑；若异常随材料区域旋转，材料非均匀性更可疑。

### 试样整体滑移与转动

软材料在压缩中可能平移或扭转。若直接相对初始图像计算，整体运动会进入局部位移和应变。应在试样坐标中分解刚体运动与形变，并使用接触外参考或稳定夹具区域复核。

### 散斑层影响

过厚涂层可能形成表面硬壳，胶性标记可能堵塞孔隙或限制表面伸缩。散斑层滑移、裂纹和脱落又会造成相关结果突变。

应通过未标记对照、不同轻量标记方式、加载前后显微检查和图像质量场验证。散斑制备的目标是随材料运动，而不是把柔软表面改造成新的复合层。

### 光学漂移与离面伪应变

相机支架温漂、焦点变化、照明波动和二维成像中的离面运动都可引入慢变偏置。稳定参考物、重复静态采集、双目三维重建和曝光锁定是关键控制手段。

若试样与画面中的刚性参考同时出现相似趋势，应先排查光学系统，而不是讨论材料机制。

## DIC边界诊断的四层证据

| 证据层 | 观测对象 | 主要目的 |
| --- | --- | --- |
| 试样场 | 位移、应变、恢复与残余 | 描述材料表面响应 |
| 接触场 | 压板附近横向位移、滑移、接触线 | 识别摩擦与脱离过程 |
| 刚体场 | 压板姿态、试样刚体运动、参考物位移 | 排除装置与相机漂移 |
| 图像质量场 | 相关质量、亮度、纹理尺度、遮挡 | 排除光学与算法伪差 |

四层证据应共享坐标和时间轴。只在结果异常后临时查看原始图像，容易遗漏触发、接触和参考状态的关键变化。

## 一套从现象到根因的诊断路径

### 现象一：中心恢复明显慢于边缘

先检查中心初始压缩是否更大，再检查压头几何和接触摩擦。若归一化后仍存在迟滞，并且更换接触条件不改变位置与路径，才进一步考虑材料结构差异。

### 现象二：一侧始终残余更大

检查压板平行度、试样厚度、照明梯度和相机视角。旋转试样是高价值对照：异常随试样旋转支持材料原因，异常留在原方向支持装置原因。

### 现象三：全场缓慢向同一方向漂移

优先检查刚性参考、相机支架和温度。真实压缩恢复通常与接触区域和试样几何相关，而整幅画面同向移动更符合外部漂移。

### 现象四：局部出现尖锐高应变

回看原始纹理、相关质量和应变窗口。真实局部化应在邻近帧连续演化；散斑裂纹或失相关常表现为突发、边界状或随参数剧烈变化。

### 现象五：重复装夹后热点换位置

判断热点是否固定在材料坐标、压板坐标还是图像坐标。三种坐标中的稳定性，是区分材料、边界和光学因素的重要线索。

## 最小对照矩阵

在不显著扩大试验规模的情况下，可设置以下对照：

- 空载静态序列：评价成像噪声与漂移；
- 刚性参考序列：评价装置运动和二维离面敏感性；
- 接触面变化：评价摩擦耦合；
- 试样旋转或翻面：区分材料坐标与装置坐标；
- 重新装夹重复：评价定位与边界再现性；
- 代表性参数重算：评价结果对相关尺度和滤波的依赖；
- 延长恢复观察：区分短时延迟与稳定残余。

每个对照都应在试验前写明预期：如果假设成立，哪个空间特征应改变，哪个应保持。没有预期的对照容易变成事后挑选解释。

## 不确定度应如何报告

海绵DIC报告不应只给出彩色结果图。至少应说明：

- 相机与镜头配置、视场和标定状态；
- 二维或三维测量的适用理由；
- 散斑方法与对材料影响的验证；
- 参考状态、坐标系和刚体运动处理；
- 载荷、位移、图像和环境的同步方式；
- 子区、步长、应变窗口及质量门槛；
- 无效区域和插值规则；
- 重复性、重新装夹和对照结果；
- 结论仅适用的时间与载荷范围。

不确定度不是一个附在末尾的数字，而是从图像采集、边界控制、数据处理到解释范围的完整链条。

## 第三方判断规则

第三方审核海绵恢复测试时，可以使用一个简单原则：结论必须在材料坐标中稳定、在合理处理设置下稳定、在独立重复中稳定，同时不能由刚性参考或边界变化解释。

若任一条件不满足，结果仍可作为探索性观察，但不宜被写成确定的材料性能差异。

## 常见问答

### 压板摩擦可以完全消除吗？

通常难以完全消除，更现实的目标是控制、记录并量化其影响。产品实际接触条件本身有时也是研究对象。

### 为什么试样旋转能帮助诊断？

旋转改变材料特征相对装置和相机的方向。异常若随材料旋转，更可能与材料相关；若固定在装置方向，则应优先检查压板、光照和成像几何。

### 二维DIC一定不能测海绵压缩吗？

不是。经过验证的平面运动可以使用二维DIC。若存在明显鼓出、凹陷、倾转或相机视角变化，应采用三维方案或明确其限制。

### 看到残余凹陷后还需要其他检测吗？

需要。DIC确认表面几何残余，内部孔隙塌陷、材料老化或界面变化仍需相应表征支持。

## 结论

海绵“记忆力”测试最容易犯的错误，是把测试系统的历史效应写成材料属性。DIC既能测量全场恢复，也能成为边界和误差的诊断工具。把试样场、接触场、刚体场和图像质量场放进同一证据链，才能让慢恢复、残余凹陷与局部热点经得起复核。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Platen Friction or Material Memory? DIC Boundary Diagnostics for Reliable Foam Recovery Tests

## Bottom line

Slow recovery, edge delay, or a residual depression after foam unloading may not arise entirely from material “memory.” Platen friction, nonparallel loading, specimen slip, the surface pattern, camera drift, and out-of-plane motion can create similar field images.

A reliable DIC arrangement observes the specimen, contact boundary, and a stable reference together. Controlled changes actively challenge artifact explanations. Only an anomaly that follows the material rather than the fixture, camera, or processing setting should be treated as a material recovery feature.

## Material memory and test-system memory

Material memory is time and path dependence created by load history. A test system can also retain history through fixture backlash, platen adhesion, frame compliance, camera-support motion, exposure changes, or reference updates in processing.

The two can look similar in a point curve. Slow platen separation may appear to be delayed foam rebound. Camera drift may create a false residual. Friction may restrain lateral expansion and alter the apparent compression of the center.

DIC is valuable because these error sources often have distinct spatial signatures. The diagnostic task is to recognize those signatures and design controls under which competing explanations predict different outcomes.

## Five common misinterpretations and their field signatures

### Platen friction

Friction restrains lateral motion near the interface and creates gradients among the edge, center, and thickness direction. Friction may also differ during loading and unloading, creating apparent hysteresis.

Compare contact treatments, observe lateral motion near the platen and on free sides, inspect top-to-bottom symmetry, and record specimen slip. If a contact change strongly alters the apparent memory, the result must be described as material–boundary interaction rather than a pure material property.

### Nonparallel or eccentric loading

A small platen tilt can create early contact on one side, an oblique compression band, lateral bending, and asymmetric recovery. Global compression may still look normal.

Three-dimensional DIC can measure surface tilt and spatial motion. A rigid comparison object can verify platen travel. Rotating the specimen provides another strong control: a feature fixed in the laboratory direction suggests the apparatus, while one that rotates with the material suggests material nonuniformity.

### Specimen slip and rotation

Soft material may translate or twist during compression. If motion is calculated directly from the initial image, rigid movement contaminates local displacement and strain. Separate rigid-body motion from deformation in specimen coordinates and confirm it with an external reference.

### Influence of the speckle layer

A thick coating can form a stiff skin, while an adhesive marker can block pores or restrain surface stretch. Pattern sliding, cracking, and flaking cause sudden correlation changes.

Use unmarked controls, alternative lightweight patterns, before-and-after inspection, and quality maps. A speckle layer should follow the material rather than convert a soft surface into a new composite layer.

### Optical drift and out-of-plane pseudo-strain

Thermal motion of the camera support, focus change, illumination variation, and out-of-plane motion in two-dimensional imaging can all create slow bias. Stable references, repeated static images, stereo reconstruction, and locked exposure are key controls.

If a rigid reference and the specimen show the same trend, investigate the optical system before proposing a material mechanism.

## Four evidence layers for boundary diagnosis

| Evidence layer | Observed item | Main purpose |
| --- | --- | --- |
| Specimen field | displacement, strain, recovery, residual | describe visible material response |
| Contact field | lateral motion, slip, and separation near the platen | identify friction and release behavior |
| Rigid-body field | platen pose, specimen rigid motion, reference displacement | reject apparatus and camera drift |
| Image-quality field | correlation, intensity, texture, occlusion | reject optical and processing artifacts |

All four layers should share coordinates and time. Looking at source images only after an anomaly appears can miss changes in trigger, contact, and reference state.

## A diagnostic path from symptom to cause

### The center recovers more slowly than the edge

Check whether the center received greater initial compression, then examine indenter geometry and friction. Only after normalization and a contact-control comparison should persistent delay be attributed to structural material variation.

### One side always has a larger residual

Check platen parallelism, specimen thickness, illumination gradient, and camera view. Rotate the specimen: an anomaly that rotates supports a material origin; one that stays in the original direction supports an apparatus origin.

### The entire field drifts in one direction

Inspect the rigid reference, camera support, and temperature first. Real compression recovery normally relates to contact and specimen geometry, whereas common motion across the image is more consistent with external drift.

### A sharp local strain peak appears

Review source texture, correlation quality, and strain-window sensitivity. Real localization evolves continuously in neighboring frames; pattern fracture or correlation loss is often abrupt, boundary shaped, and highly parameter sensitive.

### The hotspot moves after remounting

Determine whether it remains fixed in material, platen, or image coordinates. Stability in these coordinate systems is a powerful clue separating material, boundary, and optical sources.

## A minimum control matrix

Useful controls without a large expansion of test scope include:

- an unloaded static sequence for noise and drift;
- a rigid-reference sequence for apparatus motion and out-of-plane sensitivity;
- a contact-surface change for friction coupling;
- specimen rotation or inversion to separate coordinate systems;
- a remounting repeat for boundary reproducibility;
- representative reprocessing for correlation and filtering sensitivity; and
- a longer recovery observation to distinguish delay from stable residual.

State the prediction for every control before testing: which spatial feature should change if a hypothesis is true, and which should remain. A control without a prediction can become post-hoc selection of a preferred explanation.

## Reporting uncertainty

A foam DIC report should include more than contour images. It should state:

- camera and lens arrangement, field of view, and calibration state;
- justification for two-dimensional or three-dimensional measurement;
- the pattern method and evidence that it does not alter the material;
- reference state, coordinate system, and rigid-motion treatment;
- synchronization of force, motion, images, and environment;
- subset, step, strain-window, and quality rules;
- invalid-area and interpolation policy;
- repeatability, remounting, and control results; and
- the time and load domain to which conclusions apply.

Uncertainty is not merely a number added at the end. It is the chain from acquisition and boundary control through processing and interpretation.

## Independent decision rule

An independent reviewer can apply a simple rule: the conclusion should be stable in material coordinates, stable under reasonable processing choices, and repeatable, while remaining unexplained by rigid references or boundary changes.

If any condition fails, the observation may still guide exploration but should not be written as a confirmed material-performance difference.

## Frequently asked questions

### Can platen friction be eliminated completely?

Usually not. A practical objective is to control, record, and quantify its influence. In some products, the real contact condition is itself part of the research question.

### Why does specimen rotation help?

Rotation changes the orientation of material features relative to the apparatus and camera. An anomaly that rotates with the material is more likely material related; one fixed to the apparatus suggests the platen, lighting, or imaging geometry.

### Is two-dimensional DIC unsuitable for all foam compression?

No. Verified planar motion can be measured effectively in two dimensions. Significant bulging, indentation, tilt, or perspective change calls for three-dimensional measurement or an explicit limitation statement.

### Is other inspection needed after DIC finds a residual depression?

Yes. DIC confirms visible geometric residual. Internal cell collapse, aging, or interface change requires suitable complementary characterization.

## Conclusion

The easiest mistake in foam-memory testing is to report test-system history as a material property. DIC can measure recovery and diagnose boundaries and errors. A common evidence chain combining specimen, contact, rigid-body, and image-quality fields makes delayed recovery, residual depressions, and local hotspots defensible.

</details>

