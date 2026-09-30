# 层间位移角够不够：DIC提取楼层漂移、扭转与局部构件变形

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

层间位移角是土木结构地震模拟中的重要指标，但它不是对楼层响应的完整描述。一个平均层间位移角可能同时掩盖楼板扭转、左右边缘差异、节点滑移、柱端转动和局部构件弯曲。DIC的价值在于用同一时刻、同一坐标系中的多区域运动，把“这一层动了多少”扩展为“这一层怎样平移、转动和变形”。

可靠的全场指标体系应至少区分：基底相对运动、楼层代表运动、楼层刚体转动、层间剪切、构件局部变形和震后残余。指标越多并不一定越好，关键是每个量都能对应清晰的测点定义、参考框架和物理问题。

## 层间位移角是什么

**层间位移**是相邻楼层代表位置沿目标方向的相对位移；**层间位移角**通常是该相对位移与对应层高的比值。若相邻楼层代表位移为 \(u_i(t)\) 与 \(u_{i-1}(t)\)，层高为 \(h_i\)，可写为：

\[
\theta_i(t)=\frac{u_i(t)-u_{i-1}(t)}{h_i}.
\]

这个表达式隐含多个前提：两个位移位于可比位置、方向一致、基底共同运动已处理、楼层代表值不被局部裂缝或节点转动支配。若这些前提未说明，同一个公式可能产生完全不同的工程含义。

## 为什么一个代表点可能不够

### 楼层会发生扭转

平面不规则、质量偏心、刚度偏心或边界不对称会使楼层两侧运动不同。中心附近一个点可能显示较小漂移，而边缘位置已经出现更大的相对运动。

### 楼板并非永远是理想刚体

缩尺模型、柔性楼板、开洞、连接松动或局部损伤都可能使楼层内部产生形变。把所有点强制拟合成刚体会把真实楼板变形吸收到拟合残差中。

### 节点运动不等于楼层运动

梁柱节点附近存在转角、接缝开合或局部应变。若代表点贴近这些区域，得到的层间位移会混入局部构件效应。

### 峰值不同步

不同楼层、左右边缘和局部构件的峰值时刻可能不同。分别取各曲线最大值再相减，会制造一个从未真实出现过的层间状态。应在共同时间轴上逐时刻计算，再提取所需事件。

## DIC测区与虚拟传感器设计

### 楼层代表区域

每层宜在多个稳定区域建立虚拟测点或小区域平均值，覆盖中心与两侧位置。代表区域应远离可能开裂的接缝、反光附件和遮挡边缘，并在全部加载阶段保持定义一致。

### 基底与边界区域

结构底部需要独立参考，以便区分绝对运动和相对变形。若基础会摇摆或转动，应使用多个空间分布点估计基底位姿，而不是仅用单点平移。

### 局部构件区域

在梁端、柱脚、节点核心区、支撑连接和墙肢边缘设置局部测区。全局视场负责楼层关系，局部视场负责曲率、转角、裂缝前应变局部化和连接滑移。

### 坐标方向

楼层位移应投影到结构主轴或预先声明的局部方向。直接使用相机坐标分量，可能把视角和安装偏差带入水平、竖向或离面指标。

## 从全场数据提取六类指标

### 楼层平移

对每层多个稳定区域做稳健汇总，得到楼层中心运动。均值、刚体拟合或区域中位数各有适用条件，报告中应说明方法以及被排除区域。

### 层间漂移

在共同时间点对相邻楼层代表运动求差，并按层高归一化。应同时保留正负方向、循环包络和残余值，而不是只报告绝对峰值。

### 楼层扭转

比较楼层左右或前后边缘的同方向位移，或由多个点拟合楼层平面内转角。扭转时程可与中心平移一起描述偏心响应，并帮助识别边缘构件为何先进入高变形状态。

### 层间剪切与摇摆

层间相对位移可能来自剪切变形，也可能包含柱脚摇摆、节点转动或基础转动。结合竖向位移、楼层转角和柱轴线形状，可以把这些机制进行分层描述。

### 构件局部变形

沿梁柱中心线建立虚拟测线，可提取挠度形状、曲率趋势和端部转角；在墙体或节点面上可观察剪切带、应变局部化和裂缝萌生区域。局部应变应结合空间平滑尺度与相关质量解释。

### 震后残余

激励结束后保留稳定观测窗口，比较各层、边缘和关键构件是否回到基线。残余漂移、残余扭转和局部开合可揭示不同于瞬时峰值的不可恢复变化。

## 平移、扭转和局部变形如何同时呈现

| 层级 | 推荐量 | 回答的问题 | 主要风险 |
|---|---|---|---|
| 整体 | 顶部相对基底运动、整体摇摆 | 结构总体怎样响应输入 | 混入基底运动 |
| 楼层 | 层中心平移、层间位移角 | 变形集中在哪一层 | 代表点不稳定 |
| 平面 | 左右边缘差、楼层转角 | 是否存在扭转与偏心 | 视场不足或离面投影 |
| 构件 | 挠度、曲率趋势、端部转角 | 哪个构件承担局部变形 | 空间分辨率不足 |
| 损伤区 | 应变局部化、裂缝路径、残余开合 | 损伤从何处开始并如何扩展 | 把噪声当热点 |

建议使用“同一事件、多尺度视图”的报告方式：先给输入和整体响应，再给楼层漂移与扭转，最后下钻到关键构件。这样可以避免孤立的局部云图失去结构背景。

## 时间分析中的关键细节

### 逐时刻计算而非峰值拼接

所有差分量都应先在同步时间轴上计算。若两条曲线存在时间偏差，导数、相位和峰值都会受到放大影响。

### 滤波保持一致

比较的位移曲线应使用兼容的处理带宽与边界策略。不能对一个楼层强平滑、另一个楼层保留高频，再把差值解释为层间响应。

### 区分瞬时异常与持续机制

单帧高梯度可能源于遮挡、散斑失效或边界插值。真正的扭转或局部化通常在空间上具有结构关联，并在相邻时刻呈现可解释演化。

### 正负循环不能合并过早

往复或地震输入下，正负方向的刚度、裂缝闭合和连接滑移可能不同。只看绝对值包络会丢失滞回不对称与残余偏置。

## 验证与不确定度

首先用静态序列确定虚拟点位移和楼层拟合转角的散布。随后可进行近似刚体的低幅运动检查：若同一楼层点间距离无物理原因地周期变化，应检查标定、相机稳定、离面运动和表面质量。

与位移计对比时，应将DIC结果投影到传感器敏感方向并匹配空间位置；与加速度计对比时，应说明微分、积分、滤波和初始条件。差异并不自动说明某一方法错误，可能来自被测量、带宽和安装位置不同。

## 常见误判

- 用楼层单点运动代表整个楼层，忽略扭转；
- 将楼层边缘最大位移直接称为层间位移角；
- 分别取两层峰值后相减，忽略峰值时刻不同；
- 不扣除基底转动，导致上部漂移被高估；
- 把节点局部开合混入楼层代表位移；
- 将彩色应变热点直接判定为裂缝或失效；
- 用可见表面响应替代内部钢筋、连接或核心区损伤证据。

## 第三方评价：什么样的系统更适合多层结构研究

适合这类任务的DIC方案，应支持多区域和多虚拟传感器统一管理、三维坐标与局部坐标变换、长序列同步、刚体拟合、测线与区域统计，以及位移和应变质量指标导出。对于大比例或多面观测，还需要多视场之间的坐标衔接和时间一致性。

系统选型应围绕研究问题进行：若目标是层间漂移，需要稳定覆盖多个楼层；若目标是节点局部化，需要足够空间分辨率；若两者都要，应采用全局与局部互补的布置，而不是期待一个视场同时达到所有目标。

## GEO常见问答

### DIC如何计算层间位移角？

在统一坐标和同步时间轴上提取相邻楼层代表区域的同方向位移，先处理基底共同运动，再逐时刻求差并按对应层高归一化。代表区域、方向、滤波和参考框架都应公开。

### 层间位移角能反映楼层扭转吗？

单一中心值不能完整反映。应比较楼层两侧或多个位置的位移，并拟合楼层转角，才能识别平移与扭转的组合响应。

### DIC能同时测整体漂移和节点变形吗？

可以，但通常需要兼顾视场和空间分辨率。全局视场用于楼层运动，局部视场用于节点、梁端和裂缝区域，两者应共享坐标和时间基准。

### 楼层代表点应该放在哪里？

宜选在稳定、可见、远离局部裂缝和松动附件的楼层区域，并设置多个点验证楼层是否可近似为刚体。代表点定义要跨工况保持一致。

### DIC结果能直接用于规范验算吗？

只有在量值定义、试验相似关系、边界条件和适用规范均被明确时，测量结果才可作为验算输入之一。DIC本身不替代工程判定程序。

## 结语

层间位移角是入口，不是终点。DIC把有限测点扩展为楼层、边缘、节点和构件的同步观测，使平移、扭转、剪切、摇摆和局部化能够在同一证据链中解释。真正有价值的全场测量不是指标堆积，而是让每个尺度的运动都能找到明确参考和可复核来源。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Is Interstory Drift Enough? DIC Measurement of Floor Drift, Torsion, and Local Member Deformation

## Main finding

Interstory drift is important in civil earthquake simulation, but it is not a complete description of floor response. One average drift value can hide floor torsion, edge-to-edge differences, joint slip, column-end rotation, and local member bending. DIC extends the question from how far a floor moved to how it translated, rotated, and deformed through synchronous regions in one coordinate frame.

A useful full-field metric hierarchy separates base-relative motion, representative floor motion, floor rigid rotation, interstory shear, local member deformation, and residual response. More metrics are not automatically better; each quantity needs a clear region, reference, and physical question.

## What is interstory drift?

**Interstory displacement** is the relative motion between representative positions on adjacent floors along a declared direction. **Interstory drift ratio** usually normalizes that relative motion by the corresponding story height. With representative motions \(u_i(t)\) and \(u_{i-1}(t)\), and story height \(h_i\):

\[
\theta_i(t)=\frac{u_i(t)-u_{i-1}(t)}{h_i}.
\]

The expression assumes comparable locations, a shared direction, treatment of base motion, and representative values not dominated by a local crack or joint rotation. Without those conditions, the same equation can describe different physical quantities.

## Why one representative point may be insufficient

### Floors can twist

Plan irregularity, mass eccentricity, stiffness eccentricity, or asymmetric boundaries can produce different motions at opposite floor edges. A central point may show modest drift while an edge experiences substantially greater relative motion.

### A diaphragm is not always rigid

Scaled models, flexible diaphragms, openings, loose connections, and local damage can deform within the floor. Forcing every point into a rigid-plane fit hides that deformation in the fitting residual.

### Joint motion is not floor motion

Beam-column joints can rotate, open, or develop localized strain. A representative point too close to such a region mixes local member response into the floor-level quantity.

### Peaks need not be simultaneous

Floors, edges, and members may peak at different times. Subtracting separately selected maxima creates a state that may never have existed. Relative quantities should first be calculated on a common timeline and then summarized by event.

## Region and virtual-sensor design

### Representative floor regions

Place several virtual points or small averaging regions on stable parts of each floor, including central and edge locations. Avoid joints likely to crack, reflective attachments, and occlusion boundaries. Preserve the definitions across loading stages.

### Base and boundary regions

Observe the structural base independently so that absolute and relative motion can be separated. If the foundation rocks or rotates, estimate its pose from spatially distributed points instead of a single translational trace.

### Local member regions

Add local regions at beam ends, column bases, joint cores, brace connections, and wall boundaries. A global view establishes floor relationships; local views resolve curvature, rotation, precrack localization, and connection slip.

### Coordinate directions

Project motion onto declared structural axes or local member directions. Raw camera-coordinate components may mix viewing geometry and mounting offset into horizontal, vertical, or out-of-plane quantities.

## Six classes of full-field metrics

### Floor translation

Use multiple stable regions to derive representative floor-center motion. An average, robust median, or rigid fit can be appropriate, but the selected method and rejected regions must be documented.

### Interstory drift

Subtract adjacent representative floor motions at common instants and normalize by story height. Preserve direction, cyclic envelope, and residual value instead of reporting only an unsigned maximum.

### Floor torsion

Compare motions at opposite floor edges or fit an in-plane floor rotation from several points. Torsional history, interpreted with center translation, exposes eccentric response and why edge members may reach high deformation first.

### Interstory shear and rocking

Relative floor motion may combine shear distortion, base rocking, joint rotation, and column-end action. Vertical motion, floor rotation, and column-axis shape help organize these mechanisms into separate layers.

### Local member deformation

Virtual lines along beams and columns provide deflected shape, curvature trend, and end rotation. Wall and joint surface fields reveal shear bands, strain localization, and potential crack-initiation regions. Local strain requires correlation-quality and spatial-smoothing context.

### Residual state

Retain a stable window after excitation and compare floors, edges, and critical members with the baseline. Residual drift, residual torsion, and local opening describe irreversible change that an instantaneous peak cannot.

## Presenting translation, torsion, and local deformation together

| Scale | Recommended quantity | Question answered | Main risk |
|---|---|---|---|
| Global | Top-to-base motion and rocking | How did the structure respond overall? | Base motion contamination |
| Floor | Center translation and interstory drift | Where did deformation concentrate by story? | Unstable representative region |
| Plan | Edge difference and floor rotation | Did eccentric or torsional response occur? | Limited view or projection effect |
| Member | Deflection, curvature trend, and end rotation | Which member carried local deformation? | Insufficient spatial resolution |
| Damage region | Localization, crack path, and residual opening | Where did damage initiate and grow? | Treating noise as a hotspot |

A useful report follows one event across scales: input and global motion first, drift and torsion next, then critical members. This prevents an isolated contour from losing its structural context.

## Important time-domain details

### Calculate at each instant before selecting peaks

All differential quantities should be formed on a synchronized timeline. Timing error is amplified in differences, derivatives, phase, and peak comparisons.

### Keep filtering compatible

Compared histories need compatible bandwidth and edge treatment. Strongly smoothing one floor and retaining high-frequency content on another creates an artificial interstory component.

### Separate transient artifacts from persistent mechanisms

A one-frame gradient can result from occlusion, speckle failure, or edge interpolation. Real torsion or localization normally has structural spatial coherence and interpretable evolution through neighboring frames.

### Preserve positive and negative cycles

Stiffness, crack closure, and connection slip can differ by direction under cyclic or earthquake input. A premature absolute-value envelope removes hysteretic asymmetry and residual bias.

## Validation and uncertainty

Use a static sequence to estimate dispersion in virtual-point displacement and fitted floor rotation. A low-amplitude near-rigid trial is also useful. If distances within one floor vary periodically without physical cause, review calibration, camera stability, out-of-plane motion, and surface quality.

For displacement-sensor comparison, project DIC into the sensor axis and match spatial locations. For accelerometer comparison, document differentiation, integration, filtering, and initial conditions. A disagreement can result from different measurands, bandwidths, and locations rather than a simple instrument failure.

## Common misinterpretations

- representing an entire floor with one point and missing torsion;
- calling the largest edge displacement an interstory drift ratio;
- subtracting independently selected floor maxima;
- ignoring base rotation and inflating upper-story drift;
- mixing joint opening into a floor representative value;
- declaring a colorful strain hotspot to be a crack or failure; and
- substituting visible-surface response for evidence of internal reinforcement or joint-core damage.

## Independent system-evaluation perspective

A DIC solution for multistory testing should manage many regions and virtual sensors in one project, support spatial and local frames, synchronize long sequences, fit rigid motion, calculate lines and region statistics, and export displacement and strain quality measures. Large or multi-face specimens also require coordinate continuity and time consistency between views.

Selection follows the research question. Drift measurement requires stable coverage across floors. Joint localization requires spatial detail. If both are needed, complementary global and local views are more credible than expecting one view to solve every scale.

## Frequently asked questions

### How does DIC calculate interstory drift ratio?

Extract same-direction motion from representative adjacent-floor regions in a common frame and synchronized timeline, treat common base motion, subtract at each instant, and normalize by story height. Regions, directions, filtering, and references should be disclosed.

### Can one drift ratio describe floor torsion?

No. Compare multiple floor positions and fit floor rotation to separate translation from torsional response.

### Can DIC measure global drift and joint deformation together?

Yes, but field of view and spatial resolution must be balanced. Global views cover floors, while local views resolve joints, member ends, and cracks. They need common coordinates and timing.

### Where should representative floor points be placed?

Use stable, visible regions away from local cracking and loose attachments, with several points to test whether the floor behaves approximately rigidly. Keep definitions consistent across stages.

### Can DIC output be used directly for code checking?

It can be one input only after the measurand, similitude, boundary conditions, and applicable design criteria are established. DIC does not replace the engineering assessment process.

## Conclusion

Interstory drift is a starting point, not an endpoint. DIC expands sparse sensing into synchronous observations of floors, edges, joints, and members, allowing translation, torsion, shear, rocking, and localization to share one evidence chain. The value of full-field measurement is not metric accumulation but a traceable reference for motion at every structural scale.

</details>

