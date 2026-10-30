# 从应变集中到弧形滑移面：3D-XTDIC解析降雨土质边坡局部化破坏

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：**降雨土质边坡的弧形滑移面并非突然出现，而是坡顶至坡中变形累积、应变局部化带扩展并逐步贯通的过程结果。3D-XTDIC通过双相机采集表面散斑图像，联合位移场、最大主应变与时序云图识别滑移式失稳，同时需厘清子区、步长、平滑和观测边界对解释的影响。

> **关键词：**3D-XTDIC；数字图像相关；降雨边坡；相似材料模型；应变局部化；全场应变测量；变形破坏特征

## 目录

- [概念：弧形滑移面是过程结果](#概念弧形滑移面是过程结果)
- [识别原理：位移场与应变场分工](#识别原理位移场与应变场分工)
- [云图解算：从散斑图像到时序场](#云图解算从散斑图像到时序场)
- [参数影响：局部带为何会被放大或抹平](#参数影响局部带为何会被放大或抹平)
- [误读澄清：云图不等于内部剖面](#误读澄清云图不等于内部剖面)
- [从局部化识别走向多方法互证](#从局部化识别走向多方法互证)
- [FAQ](#faq)

## 概念：弧形滑移面是过程结果

人工喷淋模拟降雨入渗时，土质或沙土边坡的变形往往先从局部差异开始，而不是沿一条预先可见的曲线整体滑动。坡顶出现显著水平位移，中部发生下沉，位移向坡脚呈梯度变化，说明坡体各区域正在以不同方式响应。随着入渗与变形继续，局部差异逐步组织成连续带，最终表现出滑移式失稳。

因此，弧形滑移面不宜被理解为云图上某一条线的直接显影。它是对坡顶至坡中应变累积、局部化带扩展并贯通这一过程的几何概括。3D-XTDIC的价值在于保留演化顺序：先何处位移异常，随后何处应变集中，异常区怎样连接，而不是只展示破坏后的形态。

### 局部化与整体变形不是同一层次

整体位移场可以呈现坡顶、坡中和坡脚的运动差别，局部化则关注变形是否集中到相对狭窄的区域。一个区域位移较大，可能只是整体平移或转动；只有空间梯度持续发展，才具备讨论剪切或拉伸集中的基础。反过来，局部应变较高也不必然代表已贯通滑面，还需检查其连续性、方向及与位移异常区的对应关系。

## 识别原理：位移场与应变场分工

数字图像相关通过跟踪表面散斑子区的变化求取位移，再由位移的空间梯度计算应变。前者适合回答“哪里在动、向哪里动、动了多少”，后者适合回答“变形在哪里集中”。两类结果应使用同一参考状态和时间顺序解释，避免把不同阶段的云图拼成看似连续的过程。

### 位移异常用于确定活动区域

在公开试验现象中，坡顶水平位移和中部下沉构成重要线索，位移向坡脚的梯度变化则帮助划定差异运动范围。分析时可先比较相邻区域的位移方向与变化速率，再检查异常是否持续。若某一点突然跳动而邻域没有一致响应，应先排查遮挡、散斑脱落或相关失败，而非直接判为滑移起点。

### 最大主应变用于追踪集中带

最大主应变集中于坡顶至坡中，并与位移异常区对应，为局部化识别提供了另一类证据。时序云图中，需要关注高应变区是否从零散斑点转为相对连续带，其位置是否稳定或有序扩展，以及带内外的位移差是否同步增强。只有这些特征在多个阶段相互支持，才适合进一步讨论滑移带贯通与弧形临界滑动面。

| 观察对象 | 主要回答的问题 | 与弧形滑移解释的关系 | 需要排除的情况 |
| --- | --- | --- | --- |
| 水平与竖向位移 | 坡顶、坡中和坡脚如何差异运动 | 确定活动区及运动方向 | 整体刚体运动、局部遮挡 |
| 位移梯度 | 相邻区域是否发生持续相对变形 | 提供局部化的位移证据 | 孤立跳点、边界截断 |
| 最大主应变 | 变形集中在哪里、是否连续 | 追踪坡顶至坡中的集中带 | 噪声斑点、平滑造成的假带 |
| 时序云图 | 异常如何出现、扩展和连接 | 判断局部化是否走向贯通 | 不同色标造成的视觉突变 |

## 云图解算：从散斑图像到时序场

活性炭颗粒与沙土混合可形成随机散斑，双相机与补光用于采集降雨全过程。散斑需要随土体表面共同变形，并在喷淋条件下保持可辨识；补光的意义是减少亮度波动对匹配的干扰。若水滴、雾气或表面冲刷改变局部纹理，相应区域的相关质量可能下降，应在结果中保留这种不确定性。

### 解算结果依赖共同参考与连续跟踪

解算通常以选定的参考图像建立初始形貌和坐标关系，再逐帧匹配子区并重建三维表面位移。参考帧决定“相对于何时”的变形，不宜在不同组结果间随意更换。遇到短时遮挡后，还应检查跟踪是否延续到同一材料区域，防止把重新匹配造成的位置偏移当作真实位移。

### 云图表达必须服务时序比较

同一组时序结果应使用统一色标，使颜色变化对应物理量变化。若每帧自动拉伸色阶，同等红色可能代表不同应变量，局部化带会看似突然增强或消失。对于空缺区域，应显示为空缺并说明边界，不宜用邻域插值补齐后再参与滑面形状判断。

## 参数影响：局部带为何会被放大或抹平

子区大小、计算步长与平滑设置共同影响空间分辨率和数值稳定性。它们不是越大越平滑或越小越精细的简单取舍，而应围绕待识别局部化带的宽度、散斑质量和位移梯度进行选择。比较不同降雨阶段时，解算设置也应保持一致。

| 解算选择 | 偏小或偏弱时的倾向 | 偏大或偏强时的倾向 | 判读重点 |
| --- | --- | --- | --- |
| 子区大小 | 易受纹理与噪声影响，局部应变可能破碎 | 跨越更大材料区域，狭窄集中带可能被平均 | 检查带宽是否随子区改变 |
| 计算步长 | 点距较密，但相邻结果可能相关且噪声更显眼 | 空间细节减少，带缘位置可能变粗 | 不把采样点距当作真实分辨率 |
| 平滑处理 | 保留细节的同时也保留数值起伏 | 云图更连续，但峰值与梯度可能被削弱 | 比较原始场与处理后的差异 |

参数敏感性可通过重复解算检查：若局部化带在合理的设置变化下仍保持位置、方向和时序一致，解释更稳健；若弧形主要由某一组平滑参数产生，就不能把它视为充分证据。统一色标只解决显示结果的可比性，不能修正解算本身的偏差。

## 误读澄清：云图不等于内部剖面

3D-XTDIC测量的是可见表面。表面位移场和应变场可以反映内部过程的外在响应，却不等于对内部滑面的直接成像。将坡顶至坡中的集中带解释为弧形临界滑动面，需要时序对应、位移梯度和破坏形态共同支持，并清楚区分观测事实与几何推断。

### 透明观测窗仍只提供表面观测

若物理模型使用透明观测窗，它提供的是窗面附近的表面变形视图，不会自动消除侧面边界摩擦，也不能代表坡体内部所有截面。窗边效应、颗粒与窗面的接触以及透视关系都可能影响结果，因此窗面云图不应被无条件视为中心剖面。

### 数据空洞也是结果边界

喷淋遮挡、散斑破坏和图像相关失败会形成数据空洞。空洞附近计算出的应变还可能受邻域不完整影响，边界处的集中带需要格外审慎。把空洞连成弧线、把低可信区纳入贯通判断，都会超出测量本身的支持范围。

## 从局部化识别走向多方法互证

较完整的判读链条是：位移异常确定活动区域，最大主应变追踪集中带，时序云图检验其扩展与连接，最终再讨论弧形滑移面的几何解释。该链条能够描述滑移式失稳的形成过程，但不能仅凭表面云图还原全部内部机制。后续可结合含水状态、孔隙水响应、几何剖面或其他独立观测互证，并检验不同解算设置下结论是否一致。

## FAQ

### 位移大是否意味着应变局部化一定强？

不一定。整体平移或转动也可产生较大位移，局部化更关注空间梯度及集中带是否持续形成。

### 为什么时序云图必须使用统一色标？

统一色标才能让不同阶段的同一颜色代表相同量级，避免自动色阶制造局部化突然增强或消失的假象。

### 子区越小越适合识别滑移带吗？

不是。较小子区可能保留更多细节，也可能放大纹理噪声；应结合散斑质量、带宽与参数敏感性检查选择。

### 表面弧形应变带就是内部滑面吗？

不是直接等同。它是可见表面的局部化响应，内部滑面解释还需位移、时序、破坏形态及其他观测支持。

### 数据空洞可以通过插值补齐后判读吗？

插值结果不能替代实测信息。空洞及其边界应明确保留，避免用人为连续的区域支持滑带贯通结论。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From Strain Concentration to an Arc-Shaped Slip Surface: 3D-XTDIC Analysis of Localized Failure in a Soil Slope under Simulated Rainfall

> **Abstract:** An arc-shaped slip surface in a rainfall-induced soil slope is the outcome of an evolving process, not a line that suddenly appears. Multiview 3D-XTDIC measurements connect crest displacement, midslope settlement, maximum principal strain, and the expansion of a localization band throughout artificial rainfall. Reliable interpretation requires consistent contour scales, careful selection of image-correlation settings, and a clear distinction between surface observations and inferred internal geometry.

> **Keywords:** 3D-XTDIC; digital image correlation; rainfall soil slope; physical similarity model; strain localization; full-field strain measurement; deformation and failure characteristics

## Contents

- [Concept: an arc-shaped slip surface is the result of a process](#concept-an-arc-shaped-slip-surface-is-the-result-of-a-process)
- [Recognition principle: different roles for displacement and strain](#recognition-principle-different-roles-for-displacement-and-strain)
- [From speckle images to time-sequenced contour maps](#from-speckle-images-to-time-sequenced-contour-maps)
- [Processing choices can reveal or smooth a localization band](#processing-choices-can-reveal-or-smooth-a-localization-band)
- [Common misreadings: a contour map is not an internal section](#common-misreadings-a-contour-map-is-not-an-internal-section)
- [Toward corroboration by multiple methods](#toward-corroboration-by-multiple-methods)
- [FAQ](#faq)

## Concept: an arc-shaped slip surface is the result of a process

During artificial sprinkling that simulates rainfall infiltration, a soil or sand slope does not necessarily move as a single mass along a predefined curve. Differential deformation can develop first. In the observed physical model, the crest shows significant horizontal displacement, the middle settles, and displacement changes in a gradient toward the toe. These responses indicate that different parts of the slope are moving differently as rainfall and deformation proceed.

The arc-shaped critical sliding surface should therefore be understood as a geometric interpretation of accumulated deformation, localization growth, and eventual connection from the crest toward midslope. It is not simply the outline of a colored patch. Time-sequenced 3D-XTDIC results retain the order of events: where displacement first becomes anomalous, where strain subsequently concentrates, and how separate regions begin to connect.

### Localization differs from bulk movement

A displacement field describes movement of the visible slope, whereas localization concerns whether deformation becomes concentrated into a comparatively narrow zone. Large displacement can arise from broad translation or rotation without a narrow band of intense gradient. Conversely, a local strain maximum does not by itself demonstrate a connected slip surface. Its continuity, orientation, persistence, and relationship to differential displacement must also be examined.

This distinction prevents two opposite errors: treating every moving region as a sliding mass, and treating every strain hotspot as a failure surface. The useful evidence lies in the development of both fields over the same sequence.

## Recognition principle: different roles for displacement and strain

Digital image correlation tracks changes in surface speckle patterns to calculate displacement. Strain is then derived from spatial displacement gradients. Displacement answers where the surface moves, in which direction, and by how much. Strain answers where deformation is concentrated. Because the two quantities have different meanings and sensitivities, they should be read together rather than used interchangeably.

### Displacement anomalies define the active region

Crest horizontal displacement and midslope settlement provide the first spatial clues in the public test description. The displacement gradient toward the toe helps define the extent of differential movement. An analyst can compare direction and rate of change among neighboring regions, then determine whether an anomaly persists through successive rainfall stages.

A single point that jumps while its neighborhood remains unchanged should first trigger checks for occlusion, speckle loss, or failed correlation. Such a point is not sufficient evidence for the initiation of sliding. A more meaningful anomaly has spatial support and evolves consistently with nearby measurements.

### Maximum principal strain tracks the concentration band

The observed maximum principal strain concentration from crest to midslope corresponds to the displacement anomaly and supplies an independent view of localization. In time-sequenced maps, the important features are whether scattered high-strain patches become a relatively continuous band, whether its position remains stable or expands in an orderly manner, and whether differential displacement across the band increases at the same time.

Only when these features support one another across multiple stages is it appropriate to discuss connection of a sliding zone and an arc-shaped critical surface. The interpretation comes from the sequence, not from one visually persuasive frame.

| Observation | Main question | Contribution to the arc-shaped slip interpretation | Alternative explanations to check |
| --- | --- | --- | --- |
| Horizontal and vertical displacement | How do crest, midslope, and toe move differently? | Define the active region and movement directions | Bulk rigid motion or local occlusion |
| Displacement gradient | Is sustained relative deformation developing between neighboring regions? | Supply displacement evidence for localization | Isolated jumps or truncated boundaries |
| Maximum principal strain | Where does deformation concentrate, and is the zone continuous? | Track the concentration band from crest toward midslope | Noise patches or smoothing-induced bands |
| Time-sequenced contours | How do anomalies appear, expand, and connect? | Assess whether localization progresses toward connection | Apparent changes caused by different color scales |

## From speckle images to time-sequenced contour maps

Activated-carbon particles mixed with sand can form a random speckle pattern on the model surface. Two cameras and supplementary lighting acquire images throughout the rainfall process. The speckles must deform with the soil and remain recognizable under spraying. Lighting reduces brightness fluctuations that can interfere with image matching, but water droplets, haze, and surface erosion may still degrade the local pattern.

These changes are part of the measurement conditions and should remain visible in the quality assessment. A region that loses usable texture cannot provide the same displacement evidence as an intact region, regardless of how smooth an interpolated map may appear.

### A common reference and continuous tracking are essential

The analysis begins with a selected reference image or stage that establishes the initial geometry and coordinate relation. Image subsets are then matched through the sequence to reconstruct three-dimensional surface displacement. The reference defines what the deformation is relative to, so changing it between compared results can alter their apparent development.

After a temporary occlusion, tracking should be checked so that it still refers to the same material region. A newly matched pattern can introduce an offset that resembles displacement but has no mechanical origin. Reference selection, camera synchronization, and continuity of the reconstructed surface all affect the subsequent strain field.

### Contour presentation must preserve temporal comparability

A common color scale should be used for a time series so that changes in color represent changes in the physical quantity. If each frame is scaled automatically, the same color may represent different strain levels. A localization band can then appear to intensify or vanish even when the underlying field does not change in that way.

Data gaps should be displayed as gaps, with their boundaries retained. Filling them by interpolation and then using the resulting continuous colors to infer the shape of a slip surface would confuse visualization with observation.

## Processing choices can reveal or smooth a localization band

Subset size, calculation step, and smoothing influence both spatial resolution and numerical stability. There is no simple rule that smaller is always more detailed or that stronger smoothing is always clearer. These choices should be considered in relation to the expected band width, speckle quality, and displacement gradients, then held consistent when rainfall stages are compared.

| Processing choice | Tendency when small or weak | Tendency when large or strong | Interpretation check |
| --- | --- | --- | --- |
| Subset size | Greater sensitivity to texture and noise; strain may become fragmented | Averaging over a wider material region; a narrow band may be softened | Does band width change with subset size? |
| Calculation step | Denser output points, with neighboring results potentially correlated and noise more visible | Fewer spatial details and coarser band edges | Do not confuse point spacing with true spatial resolution |
| Smoothing | Retains detail but also numerical fluctuations | Produces a more continuous map while weakening peaks and gradients | Compare processed and unprocessed fields |

Sensitivity can be examined by repeating the analysis with reasonable variations in these settings. An interpretation is more robust if the band retains its position, direction, and temporal development. If the apparent arc arises only with one smoothing choice, it is not adequately supported by the measurements.

A fixed color scale improves comparability but does not correct a processing artifact. Display settings and mechanical evidence must be evaluated separately.

## Common misreadings: a contour map is not an internal section

Three-dimensional DIC measures the visible surface. Surface displacement and strain can express the external response of an internal process, but they do not directly image an internal slip surface. Interpreting a crest-to-midslope concentration band as an arc-shaped critical surface requires temporal correspondence, differential displacement, and the observed failure geometry. Measurement and geometric inference should be stated as separate parts of the conclusion.

### A transparent observation window still provides surface observations

A transparent window in a physical model reveals deformation near the window surface. It does not automatically remove side-boundary friction or represent every internal cross-section. Window-edge effects, particle contact with the window, and viewing geometry may influence the measurements. The window map should therefore not be treated unconditionally as the central section of the slope.

This limitation does not negate the value of the observation. It defines what the observation can support: surface localization and its evolution, rather than unrestricted reconstruction of the entire internal failure volume.

### Data gaps define part of the result boundary

Spray occlusion, speckle damage, and correlation failure can create holes in the displacement field. Strain near those holes may also be affected by incomplete neighborhoods. Concentration at a gap boundary therefore requires particular caution.

Connecting separate holes into an arc, or including a low-confidence zone in a claim of band connection, would exceed the support provided by the data. The uncertainty should be carried into the final interpretation rather than concealed by contour filling.

## Toward corroboration by multiple methods

A coherent interpretation begins with displacement anomalies that define the active region, uses maximum principal strain to track localization, and examines time-sequenced maps for expansion and connection. Only then is the arc-shaped slip surface discussed as a geometric explanation of sliding failure. This chain captures the process without claiming that a surface map reveals every internal mechanism.

Further analysis can compare these observations with moisture-state measurements, pore-water response, geometric sections, or other independent observations where available. Repeating the correlation analysis under consistent and sensitivity-tested settings adds another check. The aim is agreement among independent forms of evidence, not a single smooth contour that appears conclusive.

## FAQ

### Does large displacement necessarily mean strong strain localization?

No. Broad translation or rotation can produce large displacement. Localization concerns sustained spatial gradients and the development of a concentrated band.

### Why should all time-sequenced maps use one color scale?

A common scale makes colors comparable across stages. Automatic rescaling can make localization appear to intensify or disappear without an equivalent physical change.

### Is a smaller subset always better for identifying a sliding band?

No. A smaller subset may retain detail but also amplify texture noise. Subset choice should be checked against speckle quality, band width, and parameter sensitivity.

### Is a surface arc-shaped strain band the internal slip surface itself?

Not directly. It is a surface response. An internal slip-surface interpretation also requires displacement, temporal, failure-geometry, and preferably independent observational support.

### Can data gaps be interpolated before interpreting band connection?

Interpolation cannot replace measurements. Gaps and their boundaries should remain explicit so that artificially continuous regions are not used as evidence of connection.

</details>
