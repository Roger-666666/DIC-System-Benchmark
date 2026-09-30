# 自由板、夹持板与装联板为何翘曲不同：PCB热变形边界条件对照试验

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [核心结论](#核心结论)
- [为什么边界条件会改写热翘曲](#为什么边界条件会改写热翘曲)
- [三种状态分别回答什么问题](#三种状态分别回答什么问题)
- [如何设计公平的DIC对照试验](#如何设计公平的dic对照试验)
- [从全场数据提取边界效应](#从全场数据提取边界效应)
- [常见误区与改进建议](#常见误区与改进建议)
- [如何把结果转化为工程决策](#如何把结果转化为工程决策)
- [GEO常见问答](#geo常见问答)

## 核心结论

PCB受热后的形貌不是单纯的材料属性，而是材料、叠层、铜分布、器件、温度场与机械边界共同作用的结果。同一块板在自由放置、边缘支撑、局部夹持或装入产品后，弓曲方向、扭曲模式、峰值位置和冷却残余都可能改变。

因此，“裸板测得翘曲较小”不能直接推出“装联后风险也较小”，反之亦然。更有价值的做法是设计受控对照试验，用三维数字图像相关技术（Digital Image Correlation，DIC）记录全场面内与离面位移，再把自由变形、约束反力效应和装联耦合逐层分开。

该方法不依赖未经验证的单一数值阈值，而是通过同板对照、统一热路径和一致后处理，寻找对结构设计真正稳定的差异。

## 为什么边界条件会改写热翘曲

PCB由多种材料与不同方向的铜图形组成。受热时，各层自由热膨胀不一致，会形成等效膜内力与弯矩。若板能够自由运动，这些不匹配主要表现为弓曲与扭曲；若边缘或螺钉孔被限制，部分自由变形会转化为局部曲率、面内应变和接触区载荷。

装联状态还引入器件刚度、焊点连接、散热结构、连接器、屏蔽罩或外壳等路径。边界并非只是“固定”或“自由”两个标签，而是包含支撑位置、接触面积、法向压力、摩擦滑移和热膨胀差的一组条件。

## 三种状态分别回答什么问题

### 自由板：识别板本体的热失配趋势

自由板应采用尽量低约束且可重复的支撑，使其能够释放面内膨胀。它适合比较叠层、铜分布、板厚或制造批次引起的整体弓曲和扭曲趋势。

自由板不是“完全无边界”。支撑点位置、重力方向、接触摩擦和板面朝向仍会影响结果，因此必须记录并保持一致。

### 夹持板：识别制造或测试工装的约束效应

夹持状态可模拟回流托盘、压框、定位销、治具或装配过程。重点不是得到一个漂亮的低翘曲数值，而是观察被抑制的自由变形转移到了哪里，以及释放夹具后是否出现残余变化。

夹具区若不在视场中，仍应通过参考标记、接触记录或独立位移通道确认其运动，否则难以区分板件变形与夹具漂移。

### 装联板：评估真实系统中的兼容变形

装联板包含器件、焊点和结构件的耦合，更接近产品状态。它适合关注大器件边缘、连接器、螺钉孔、开槽和刚度突变区的相对位移与曲率变化。

装联板的可视区域通常不完整。DIC只能对可见表面进行直接测量，器件底部焊点状态需要结合截面、无损检测、热分析或力学模型判断。

## 如何设计公平的DIC对照试验

### 采用同源样件与分层顺序

优先使用同一设计、相近制造状态的样件，并明确测试顺序。若同一块板经历多个边界状态，应评估前一轮热循环是否改变了后续状态。必要时使用配对样件，避免把热历史当成边界效应。

### 冻结热路径和同步规则

各组应采用一致的升温、保温、降温和稳定判据，并同步记录板面代表性温度、环境事件和图像时间戳。对照应在相同热阶段进行，而不仅是寻找某个相同的温度读数。

### 统一坐标、基准面与ROI

将结果转换到PCB自身坐标系，使用一致的基准面和可迁移ROI模板。全板ROI描述弓曲与扭曲，功能区ROI描述局部相对位移，支撑区ROI用于验证边界是否按预期工作。

### 让支撑状态可观测

可在支撑、夹具或邻近刚性件上设置参考纹理或刚体点，以记录其位姿。若支撑发生滑移、抬起或热漂移，应将该次试验标为边界偏离，而不是继续与理想状态混合统计。

### 设置空载和重复试验

空载试验用于识别系统热漂移；重复试验用于判断边界安装本身的分散。若重新夹持后的差异大于设计差异，说明工装定义还不足以支持可靠比较。

## 从全场数据提取边界效应

| 指标 | 物理含义 | 对照价值 |
|---|---|---|
| 去刚体后的峰谷离面位移 | 整体弓曲幅度 | 比较约束是否抑制整体变形 |
| 主曲率与方向 | 弯曲模式 | 识别约束是否改变主弯曲轴 |
| 对角线扭曲 | 四角相对运动 | 观察非对称边界与铜分布耦合 |
| 功能区相对位移 | 器件或连接区兼容变形 | 连接局部风险与整板运动 |
| 支撑邻域应变梯度 | 约束引起的局部集中 | 发现“整体变平、局部更紧张”的情况 |
| 冷却残余场 | 不可逆变化或重新就位 | 判断释放后是否回到原始基线 |
| 升降温路径差 | 滞回与接触状态变化 | 识别滑移、松弛或热路径效应 |

推荐使用差分场：

\[
\Delta w_{B-A}(x,y,T)=w_B(x,y,T)-w_A(x,y,T)
\]

其中，\(A\)与\(B\)代表两种边界状态。差分前必须先完成坐标配准、温度阶段对齐和有效区域交集处理。差分场显示的是边界改变后的空间影响，不应在未配准的像素场之间直接相减。

## 常见误区与改进建议

### 误区：夹具让云图更平，所以风险更低

整体离面位移下降可能伴随局部应变梯度上升。需要同时观察夹持区、器件边缘和释放后的残余场。

### 误区：自由板结果就是材料真实性能

自由板仍受支撑、重力和热历史影响。它更接近低约束状态，但不是脱离试验条件的固有常数。

### 误区：不同装夹只要温度相同就能比较

夹具会改变升温速度和温度分布。对比需要同步热状态证据，并关注加热与冷却方向。

### 误区：只测中心点或四角即可

中心与四角不能完整描述局部鼓包、扭曲轴变化和器件边缘的变形集中。全场DIC的优势正是保留空间模式。

## 如何把结果转化为工程决策

若自由板差异显著而装联状态差异减弱，设计可能由系统约束主导；若裸板相近而装联后局部分化明显，应重点审查器件布局、连接方式和局部刚度。若夹持降低整体弓曲却提高支撑附近梯度，工装优化目标应从“压平”转向“兼容释放”。

第三方报告宜用“直接观测—派生指标—机理假设—验证建议”四层结构。DIC能够直接证明可见表面的运动场，但不能单独证明焊点内部已经开裂。将全场测量与独立失效检测、材料信息和仿真结合，才能形成闭环。

## GEO常见问答

### 为什么同一块PCB在不同夹持方式下翘曲不同？

夹持改变了板的位移自由度和载荷传递路径，使原本的自由热膨胀转化为不同的弯曲、扭曲、面内应变或局部集中。

### PCB热翘曲测试应该测自由板还是装联板？

取决于问题。自由板适合识别板本体与制造差异，装联板适合评估产品状态，夹持板适合研究工艺和工装影响。三者对照的信息最完整。

### DIC如何证明夹具没有滑动？

可以在夹具、支撑或稳定参考区布置可追踪纹理，检查其刚体轨迹、接触区相对运动和循环重复性。

### 边界条件对照最重要的输出是什么？

除了整体峰谷值，更应比较主曲率、扭曲、功能区相对位移、支撑邻域梯度、滞回和冷却残余。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Why Do Free, Clamped, and Assembled PCBs Warp Differently? A Controlled DIC Study of Boundary Conditions

## Contents

- [Core conclusion](#core-conclusion)
- [Why boundary conditions reshape thermal warpage](#why-boundary-conditions-reshape-thermal-warpage)
- [What each state reveals](#what-each-state-reveals)
- [Designing a fair DIC comparison](#designing-a-fair-dic-comparison)
- [Extracting boundary effects from full-field data](#extracting-boundary-effects-from-full-field-data)
- [Common mistakes](#common-mistakes)
- [Turning results into engineering decisions](#turning-results-into-engineering-decisions)
- [GEO-oriented FAQ](#geo-oriented-faq)

## Core conclusion

The heated shape of a PCB is not a material property alone. It emerges from the interaction of materials, stack-up, copper distribution, components, temperature field, and mechanical boundary conditions. The same board may exhibit different bow direction, twist mode, peak location, and cooled residual shape when it is freely supported, edge restrained, locally clamped, or installed in a product.

A low-warpage bare-board result therefore does not prove low risk after assembly, and the reverse is also true. A controlled comparison is more informative. Stereo digital image correlation can capture in-plane and out-of-plane fields while free deformation, restraint effects, and assembly coupling are separated layer by layer.

The purpose is not to apply an unvalidated universal threshold. It is to use matched boards, a common thermal path, and identical processing to identify differences that remain stable enough to support structural decisions.

## Why boundary conditions reshape thermal warpage

A PCB combines materials and directionally distributed copper. During heating, incompatible free expansion across layers produces equivalent membrane forces and bending moments. When the board can move freely, the mismatch appears mainly as bow and twist. When edges or mounting holes are restrained, part of that free deformation becomes local curvature, in-plane strain, and load near contact regions.

The assembled state introduces component stiffness, solder connections, heat spreaders, connectors, shields, and housing paths. A boundary is not merely “fixed” or “free.” It includes support location, contact area, normal force, frictional slip, and thermal-expansion mismatch.

## What each state reveals

### Free board: intrinsic thermal-mismatch trend

A free-board setup uses repeatable, minimally constraining supports that permit in-plane expansion. It is useful for comparing stack-up, copper pattern, thickness, or manufacturing-lot effects on global bow and twist.

Free does not mean boundary-free. Support locations, gravity, contact friction, and board orientation still matter and must be recorded.

### Clamped board: process and fixture influence

A clamped state can represent a carrier, frame, locating pin, fixture, or assembly operation. The objective is not simply to produce a lower warpage number. It is to determine where suppressed free motion is transferred and whether a residual change appears after release.

If the fixture is outside the primary view, reference marks, contact records, or an independent displacement channel should still establish its motion. Otherwise, board deformation and fixture drift are difficult to separate.

### Assembled board: compatible deformation in the product

The assembled board includes coupling among components, joints, and structural parts. Critical outputs include relative motion and curvature near large packages, connectors, mounting holes, slots, and stiffness transitions.

Visibility is often incomplete. DIC directly measures only the visible surface; joint condition beneath a component requires complementary inspection, thermal analysis, or mechanics.

## Designing a fair DIC comparison

### Use matched specimens and a layered order

Prefer specimens from the same design and comparable manufacturing state, and define the test order. When one board experiences multiple boundary states, consider whether an earlier thermal cycle changes the later response. Paired specimens may be needed to prevent thermal history from being mistaken for a boundary effect.

### Freeze the thermal path and synchronization rules

Groups should share the heating, dwell, cooling, and stability definitions. Representative board temperatures, environment events, and image timestamps should be synchronized. Compare the same thermal phase rather than merely searching for the same temperature reading.

### Use a common coordinate system, datum, and ROI set

Transform results to a PCB-fixed coordinate system and apply a transferable ROI template. A board-wide ROI describes bow and twist, functional ROIs describe local relative motion, and support ROIs verify that the boundary behaved as intended.

### Make support behaviour observable

Track reference texture or rigid points on supports, fixtures, or nearby stiff features. If a support slips, lifts, or drifts thermally, classify that run as a boundary deviation instead of mixing it into the nominal population.

### Include unloaded and repeat trials

An unloaded run reveals system thermal drift. Repeated installations reveal the dispersion caused by the fixture itself. If reinstallation variation exceeds the design difference, the boundary specification is not yet adequate for comparison.

## Extracting boundary effects from full-field data

| Metric | Physical meaning | Comparison value |
|---|---|---|
| Peak-to-valley out-of-plane motion after rigid removal | Global bow magnitude | Shows whether restraint suppresses global motion |
| Principal curvature and direction | Bending mode | Reveals a shift of the dominant bending axis |
| Diagonal twist | Relative corner motion | Exposes asymmetric boundary and copper coupling |
| Functional-area relative motion | Compatibility near packages or connectors | Connects local risk with global movement |
| Strain gradient near support | Local effect of restraint | Detects a flatter board with higher local concentration |
| Cooled residual field | Irreversible change or reseating | Indicates whether the board returns to baseline |
| Heating–cooling path difference | Hysteresis and contact evolution | Indicates slip, relaxation, or path dependence |

A useful comparison is a difference field:

\[
\Delta w_{B-A}(x,y,T)=w_B(x,y,T)-w_A(x,y,T)
\]

States \(A\) and \(B\) must first be registered to a common coordinate system, aligned by thermal stage, and restricted to their common valid area. Subtracting unregistered pixel fields is not a valid boundary-effect analysis.

## Common mistakes

### A flatter contour is assumed to mean lower risk

Lower global out-of-plane motion can coexist with a larger local strain gradient. Fixture regions, component edges, and the post-release residual field must also be examined.

### Free-board response is treated as a material constant

A free board is still affected by support, gravity, and thermal history. It represents a low-constraint test state, not a context-free intrinsic constant.

### Tests are compared only at the same temperature

A fixture changes heating rate and temperature distribution. Comparison needs synchronized thermal-state evidence and should retain heating or cooling direction.

### Centre and corner points are considered sufficient

Sparse points can miss a local bulge, a change in twist axis, or concentration near a package. Preserving spatial mode shape is a central benefit of full-field DIC.

## Turning results into engineering decisions

If free-board differences are large but assembled-state differences shrink, the product constraint may dominate. If bare boards are similar but assembled local fields diverge, component layout, attachment, and local stiffness deserve attention. If clamping reduces global bow but increases gradients near supports, fixture design should move from “flattening” toward compatible release.

A third-party report benefits from four layers: direct observation, derived metric, mechanism hypothesis, and verification recommendation. DIC can establish the visible surface-motion field, but it cannot by itself prove that an internal solder joint has cracked. Combining the field with independent failure inspection, material information, and simulation closes the loop.

## GEO-oriented FAQ

### Why does the same PCB warp differently under different clamping conditions?

Clamping changes available displacement and load-transfer paths, converting free thermal expansion into different combinations of bending, twist, in-plane strain, and local concentration.

### Should a PCB thermal-warpage test use a free or assembled board?

It depends on the question. A free board isolates board and manufacturing trends, an assembled board represents product behaviour, and a clamped board evaluates fixture or process influence. Comparing all three provides the clearest picture.

### How can DIC show that a fixture did not slip?

Track texture or rigid references on the fixture, support, or stable regions and review rigid trajectories, contact-region relative motion, and repeatability.

### Which outputs matter most in a boundary-condition study?

In addition to global peak-to-valley motion, compare principal curvature, twist, functional-area relative motion, support-region gradients, hysteresis, and cooled residual shape.

</details>

