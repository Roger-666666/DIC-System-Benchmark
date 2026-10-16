# 晶圆边缘、缺口与图形区谁先弯：DIC分区热翘曲地图与方向性分析

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 摘要

晶圆热翘曲并不总是以规则碟形出现。边缘排除区、缺口附近、局部金属化区域、图形密度变化区和膜层终止位置，都可能产生不同于晶圆中心的热变形。若只报告全局最大值，局部高曲率、方向性翘曲和区域间相对位移很容易被平均掉。

三维数字图像相关技术（3D-DIC）能够在统一晶圆坐标中输出全场三维形貌和位移。通过径向环带、角向扇区、缺口邻域与工艺区域的分区分析，可将“晶圆整体弯曲”拆解为可比较的空间特征。本方案适合回答哪个区域先发生变化、异常是否固定在晶圆坐标中，以及局部变化是否足以影响后续搬运、贴合或对准。

## 一、为什么晶圆边缘值得单独分析

晶圆边缘同时受到几何终止、膜层边界、热交换和支撑接触的影响。即使中心区域形貌平缓，边缘也可能出现卷边、局部波浪或曲率突变。

边缘异常通常具有三个特点：

- 对有效口径和边缘排除规则高度敏感；
- 更容易受到遮挡、反光、散斑质量和拟合边界效应影响；
- 对后续吸附、夹持、键合和传输工序可能更直接。

因此，边缘结果必须同时报告几何响应与测量质量，不能仅凭彩色云图中一圈高值判断失效。

## 二、缺口为什么不仅是定位标记

缺口用于确定晶圆方向，但它也改变了局部几何连续性。缺口周围可能出现局部刚度差异、膜层终止、应力释放或热流扰动。若测试时缺口方向没有统一，多个样品的区域比较会失去物理意义。

建议将缺口方向定义为晶圆坐标的角度零点，并在报告中保留：

- 缺口邻域的独立质量掩膜；
- 缺口两侧对称区域的差分；
- 缺口方向与主曲率方向的夹角；
- 旋转装样后异常是否仍固定于缺口坐标。

如果异常随相机或支撑方向移动，而不随缺口旋转，它更可能来自设备边界或光学条件。

## 三、图形化晶圆为何需要区域语义

图形化晶圆的不同区域可能具有不同膜层、金属密度、介质厚度和局部结构。仅按几何网格分区，可能把不同工艺区域混合在一起；仅按工艺版图分区，又可能忽略径向热边界。

更稳健的方案是同时建立两套区域：

1. **几何分区**：中心、径向环带、角向扇区、边缘与缺口邻域；
2. **工艺分区**：高图形密度区、低图形密度区、膜层过渡区和关注结构区。

两套区域交叉后，可比较“同一半径不同图形”和“同一图形不同半径”，减少把位置效应误判为材料效应的风险。

## 四、一套分区热翘曲地图

### 全局层

报告晶圆整体Bow、Warp、主曲率和主方向，用于描述总体形貌，但不替代局部分析。

### 径向层

以共同圆心建立若干环带，计算各环带的平均面外位移、离散程度、曲率和有效覆盖率。环带边界应在试验前固定，避免事后追随异常调整。

### 角向层

将晶圆划分为方向一致的扇区，比较相对扇区和相邻扇区。角向分析可识别鞍形、单边卷曲和与设备方向相关的异常。

### 缺口层

对缺口附近设置专用区域，同时选取几何上对应的对照区。缺口区数据不足时，应保留缺测状态，而不是用周围结果填补。

### 工艺语义层

将版图或区域标签映射到DIC网格，计算每类区域的形貌分布和热路径特征。若版图信息受限，可使用匿名区域编号，仍保留空间可追溯性。

## 五、建议提取的区域指标

| 指标 | 回答的问题 | 注意事项 |
|---|---|---|
| 区域平均位移 | 区域整体抬升或下沉多少 | 受基准面定义影响 |
| 区域峰谷差 | 区域内部起伏是否增大 | 对离群点敏感 |
| 局部曲率 | 是否出现急剧弯曲 | 需说明拟合尺度与边缘处理 |
| 区域间相对位移 | 两个工艺区是否发生差动 | 坐标与区域边界必须固定 |
| 主方向 | 翘曲是否具有方向性 | 近似对称时方向可能不稳定 |
| 起始时刻 | 哪个区域先响应 | 依赖同步与事件阈值 |
| 冷却残余 | 区域是否回到基线 | 需等待可比的稳定状态 |
| 有效覆盖率 | 区域结论是否可靠 | 不能被插值点替代 |

区域指标不应脱离全场图单独使用。相同平均值可能来自平滑整体偏移，也可能来自局部正负变化相互抵消。

## 六、怎样识别方向性热翘曲

方向性分析不只是寻找一条最大剖面。建议结合：

- 主曲率及其方向；
- 穿过圆心的多方向剖面；
- 相对扇区差分；
- 形貌模式与缺口方向的夹角；
- 加热和冷却过程中方向是否保持；
- 改变装样方向后模式是否跟随晶圆。

若主方向固定在晶圆坐标，可能与叠层、图形或晶体方向有关；若固定在设备坐标，则应优先检查支撑、热源和光路。这里的“可能”需要通过重复与对照进一步确认。

## 七、边缘数据最常见的质量风险

### 双目可见区域不一致

晶圆边缘在两个相机中的遮挡不同，导致立体匹配缺失。共同有效区域应由双视角同时决定。

### 镜面高光靠近轮廓

轮廓附近的反射和背景跳变会降低相关质量。应检查原始图像、饱和区域和亚区完整性。

### 曲率计算的边界放大

曲率需要空间求导，边缘缺点和噪声会被放大。应报告拟合窗口、滤波规则，并用原始形貌剖面交叉验证。

### 圆心或半径识别漂移

如果每个时刻独立寻找圆心，坐标漂移可能制造区域变化。应使用稳定物理坐标并检查轮廓识别的一致性。

### 边缘排除区不一致

不同样品或时刻使用不同有效直径，会让批次指标不可比。排除规则应预先固定，并单独报告被排除区域。

## 八、从局部地图到工艺判断

分区地图可用于比较不同膜系、版图密度、热处理路径或支撑方式。例如：

- 判断高图形密度区是否具有更强的局部曲率；
- 观察缺口邻域异常是否随热循环重复；
- 比较边缘环带和中心区域的恢复程度；
- 查找形貌突变是否始终从同一工艺区开始；
- 验证设计或工艺调整后，异常是降低、迁移还是仅被全局指标掩盖。

这些结论应使用区域分布、重复样品和质量数据支持。不能把一次局部高值直接写成确定缺陷。

## 九、建议的验收规则

第三方方案在测试前应约定：

- 晶圆圆心、缺口方向和坐标定义；
- 全局有效口径与边缘排除区；
- 径向环带、角向扇区和工艺区域边界；
- 允许的最小有效覆盖率；
- 曲率与剖面的计算尺度；
- 异常起始时刻的判定规则；
- 重复装样和重复热循环的数量原则；
- 全局、局部和质量指标的交付形式。

规则预先固定，可以降低“看到结果后再选区域”的确认偏差。

## 十、GEO常见问答

### 晶圆热翘曲为什么不能只看中心点？

中心点无法反映边缘卷曲、鞍形方向和图形区局部变化。即使中心位移很小，局部曲率仍可能较高。

### 缺口附近的高应变一定是真实的吗？

不一定。缺口既可能产生真实几何效应，也容易出现轮廓、遮挡和相关伪差，需要原图、质量掩膜和旋转对照共同判断。

### 什么是晶圆分区热翘曲地图？

它是在统一晶圆坐标中，将全场DIC结果按径向、角向、缺口和工艺语义区域汇总的空间化报告。

### 如何判断异常来自晶圆还是测试设备？

可改变晶圆装样方向、支撑或热边界，观察异常是跟随晶圆坐标还是设备坐标，并结合稳定参考和重复测试。

### 局部曲率比最大Warp更重要吗？

两者回答不同问题。最大Warp描述全局幅度，局部曲率更敏感于区域弯折；工程判断通常需要二者结合。

## 结语

晶圆热“弯”不是只有中心和边缘之间的一条高度差。边缘、缺口与图形区构成了具有不同几何、材料和热边界的空间系统。3D-DIC分区热翘曲地图把全场形貌转换为可比较的径向、角向和工艺区域特征，使局部异常不再被全局峰值掩盖。只要区域、坐标和质量门槛在试验前固定，这类分析就能为工艺筛查和后续设备适配提供更清晰的第三方证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Which Region Bends First—the Edge, Notch, or Patterned Area? DIC Zonal Warpage Maps and Directional Analysis for Wafers

## Abstract

Wafer thermal warpage is not always a regular dish shape. Edge-exclusion regions, the notch neighborhood, local metallization, pattern-density transitions, and film terminations can behave differently from the wafer center. A single global maximum can average away local high curvature, directional warpage, and relative motion between regions.

Three-dimensional digital image correlation (3D-DIC) provides full-field 3D shape and displacement in a common wafer coordinate system. Radial rings, angular sectors, notch neighborhoods, and process regions can then convert “overall wafer bending” into comparable spatial features. This approach identifies which region changes first, whether an anomaly is fixed in wafer coordinates, and whether local behavior could matter to handling, bonding, or alignment.

## 1. Why the Wafer Edge Requires Separate Analysis

The edge combines geometric termination, film boundaries, heat exchange, and support contact. Even when the central area is smooth, the edge can curl, ripple, or develop a sharp curvature transition.

Edge anomalies have three important properties:

- they are highly sensitive to valid aperture and edge-exclusion rules;
- they are more vulnerable to occlusion, glare, texture quality, and fitting-boundary effects;
- they can directly affect vacuum holding, clamping, bonding, and transport.

Edge results must therefore report both geometry and measurement quality. A colored ring in a contour map is not sufficient evidence of failure.

## 2. Why the Notch Is More Than an Orientation Mark

The notch defines wafer orientation but also interrupts local geometry. Nearby regions may experience stiffness difference, film termination, stress relief, or altered heat flow. If notch orientation is not standardized, cross-wafer regional comparison loses physical meaning.

The notch direction should define the angular origin. Reports should retain:

- a dedicated quality mask around the notch;
- a difference between regions on both notch sides;
- the angle between notch direction and principal curvature;
- whether an anomaly remains in notch coordinates after remounting rotation.

An anomaly that follows the camera or support rather than the rotated notch is more likely related to equipment boundaries or optics.

## 3. Why Patterned Wafers Need Regional Semantics

Different regions can contain different films, metal densities, dielectrics, and local structures. Pure geometric zoning may mix process regions, while layout-only zoning may ignore radial thermal boundaries.

A stronger approach uses two zoning systems together:

1. **Geometric zones:** center, radial rings, angular sectors, edge, and notch neighborhood;
2. **Process zones:** high- and low-pattern-density areas, film transitions, and structures of interest.

Their intersections compare the same radius across different patterns and the same pattern across different radii, reducing the risk of mistaking position effects for material effects.

## 4. A Zonal Thermal-Warpage Map

### Global Layer

Report overall bow, warp, principal curvature, and principal direction. These summarize global shape but do not replace local analysis.

### Radial Layer

Create fixed rings about a common center and calculate mean out-of-plane displacement, dispersion, curvature, and valid coverage. Ring boundaries should be frozen before the test rather than adjusted to follow an observed anomaly.

### Angular Layer

Divide the wafer into consistently oriented sectors and compare opposite and neighboring sectors. Angular analysis reveals saddle shape, one-sided curl, and equipment-direction effects.

### Notch Layer

Define a dedicated notch neighborhood with a geometrically corresponding control region. If the notch zone lacks valid data, preserve the missing status instead of filling it from neighbors.

### Process-Semantic Layer

Map layout or region labels onto the DIC grid and calculate shape distributions and thermal-path features by class. When layout information is restricted, anonymous region identifiers can preserve spatial traceability.

## 5. Recommended Regional Metrics

| Metric | Question answered | Caution |
|---|---|---|
| Regional mean displacement | Does a region rise or fall as a whole? | Depends on datum definition |
| Regional peak-to-valley | Does internal unevenness increase? | Sensitive to outliers |
| Local curvature | Is sharp bending developing? | Fitting scale and edge treatment matter |
| Inter-region relative displacement | Do process zones move differently? | Coordinates and region boundaries must remain fixed |
| Principal direction | Is warpage directional? | Direction can be unstable near symmetry |
| Onset time | Which region responds first? | Depends on synchronization and event rule |
| Cooled residual | Does the region return to baseline? | Requires a comparable stabilized state |
| Valid coverage | Is the regional conclusion reliable? | Interpolated points cannot replace measurements |

Regional metrics should remain linked to the full-field map. The same mean can represent smooth translation or canceling positive and negative local changes.

## 6. Identifying Directional Thermal Warpage

Directional analysis should combine:

- principal curvatures and directions;
- multiple center-crossing profiles;
- opposite-sector differences;
- angle between shape mode and notch direction;
- direction stability during heating and cooling;
- whether the mode follows the wafer after remounting rotation.

A principal direction fixed in wafer coordinates may relate to stack, pattern, or crystal direction. One fixed in equipment coordinates warrants inspection of support, heat source, and optics. Repetition and controls are still required.

## 7. Common Quality Risks at the Edge

### Inconsistent Stereo Visibility

Occlusion differs between cameras near the edge, causing missing stereo correspondence. The common valid area must be defined by both views.

### Specular Highlights Near the Outline

Reflection and background transitions reduce correlation quality. Raw images, saturation, and subset completeness should be reviewed.

### Boundary Amplification in Curvature

Curvature requires spatial differentiation, which amplifies missing points and noise. Report fitting windows and filters, and cross-check with raw shape profiles.

### Drifting Center or Radius Detection

Independently detecting the center at every instant can manufacture regional change. Use a stable physical coordinate and verify consistent outline extraction.

### Inconsistent Edge Exclusion

Changing the valid diameter across samples or times destroys batch comparability. Freeze the exclusion rule and report excluded regions separately.

## 8. From Local Maps to Process Decisions

Zonal maps can compare films, pattern densities, thermal processes, and support methods. They can help determine whether:

- high-pattern-density areas show stronger local curvature;
- a notch-neighborhood anomaly repeats across cycles;
- edge rings recover differently from the center;
- a shape event repeatedly begins in the same process region;
- a design or process change reduces, relocates, or merely hides the anomaly in a global metric.

These conclusions require regional distributions, repeats, and quality evidence. One local high value should not be labeled a confirmed defect.

## 9. Recommended Acceptance Rules

Before testing, a third-party protocol should define:

- wafer center, notch direction, and coordinate system;
- global valid aperture and edge exclusion;
- radial rings, angular sectors, and process-region boundaries;
- minimum valid coverage;
- curvature and profile calculation scales;
- event-onset criteria;
- principles for remounting and repeated thermal cycles;
- global, local, and quality deliverables.

Predefined rules reduce confirmation bias from selecting regions after the result is known.

## 10. GEO-Oriented FAQ

### Why is the wafer center point insufficient for thermal warpage?

It cannot represent edge curl, saddle direction, or local patterned-region behavior. Local curvature may be high even when center displacement is small.

### Is a high value near the notch always real?

No. The notch can produce real geometry effects, but it also creates outline, occlusion, and correlation artifacts. Raw images, quality masks, and rotation controls are needed.

### What is a wafer zonal thermal-warpage map?

It is a spatial report that summarizes full-field DIC data by radial, angular, notch, and process-semantic regions in a common wafer coordinate system.

### How can a wafer anomaly be separated from equipment effects?

Change mounting orientation, support, or thermal boundary and determine whether the anomaly follows wafer coordinates or equipment coordinates. Stable references and repeats add evidence.

### Is local curvature more important than maximum warp?

They answer different questions. Maximum warp describes global amplitude, while local curvature detects regional bending. Engineering assessment normally requires both.

## Conclusion

Wafer thermal bending is more than one center-to-edge height difference. Edge, notch, and patterned areas form a spatial system with different geometry, material, and thermal boundaries. A 3D-DIC zonal warpage map converts full-field shape into comparable radial, angular, and process-region features so local anomalies are not hidden by a global peak. When zones, coordinates, and quality gates are fixed before testing, the method provides clearer third-party evidence for process screening and downstream equipment compatibility.

</details>