# 应变窗口跨过一个孔还可信吗：小尺寸多孔件DIC空间尺度与虚拟标距

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

小尺寸多孔、网格或异形结构的DIC“应变”并非天然唯一。相关子区、计算步长、应变窗口、虚拟标距和几何掩膜共同决定结果代表的是材料局部变形、单元平均变形，还是跨越孔洞后的结构等效变形。若计算窗口同时覆盖实体与孔隙，所得数值不能不加说明地称为材料应变。

可靠报告应至少区分三类量：实体材料表面的局部应变、杆件或连接的构件变形、多个单元范围内的结构等效应变。不同尺度可以同时有价值，但必须采用不同名称、空间定义和不确定度，不能用一个峰值在各尺度之间替代。

## 为什么多孔结构的应变定义复杂

连续材料中，应变通常表示邻近材料点之间的相对变形。多孔结构包含实体、孔隙、接触和断开的拓扑；一个大窗口可能跨过没有材料的区域。此时数值更接近几何单元的平均变化，而不是孔隙中的“材料应变”。

同一图像序列使用不同参数，可能得到：

- 细杆表面的局部轴向或剪切应变；
- 杆件弯曲引起的表面拉压分布；
- 节点之间的相对位移；
- 单元尺寸或孔径的变化；
- 整个试样标距内的等效压缩应变。

这些结果回答不同问题，数值不应直接互换。

## 五个空间尺度参数

### 相关子区

子区用于跟踪灰度纹理。过小可能缺少唯一特征，过大可能跨越孔边、接触面或高梯度区，产生混合运动。

### 计算步长

步长决定输出点密度，但更密的点不等于更高的独立空间分辨率。相邻结果若共享大量图像信息，会具有明显相关性。

### 应变窗口

应变由位移场在一定邻域内求导或拟合得到。窗口越大通常越平滑，但会扩大局部化带宽并降低峰值；窗口越小则更敏感于位移噪声和缺失点。

### 虚拟标距

虚拟引伸计通过两个区域或点的相对位移计算平均应变。标距可以对应一根杆、一个单元、多个单元或整个试样，含义随范围变化。

### 几何掩膜

掩膜决定哪些像素属于实体表面。孔边掩膜错误会让相关与应变计算跨越背景，造成虚假高梯度。

## 建立三层量值体系

### 材料局部应变

只在连续实体表面内计算，窗口不跨孔、不跨裂纹、不跨接触边界。用于分析细杆局部弯曲、孔边集中和材料局部化。

### 构件变形

用杆件轴线、边缘或节点区域提取轴向缩短、横向挠度、转角和曲率趋势。它描述结构单元的运动，不必强制转换成连续表面应变。

### 结构等效应变

在多个节点或端面之间建立标距，以总体尺寸变化除以初始标距。它适合比较整体压缩和设计等效性能，但不能代表每根细杆的材料应变。

## 虚拟标距该怎样选

虚拟标距应与研究尺度一致，并避开会改变参考含义的区域。

- **端面标距**：描述试样有效区总体压缩，需扣除压头就位与夹具柔度；
- **节点标距**：描述一个或多个单元的几何变化，适合结构等效响应；
- **杆件标距**：沿中心线两端计算轴向变化，需同时检查杆件转动和弯曲；
- **裂纹或接缝标距**：测量开口与滑移，不应称为连续材料应变；
- **多标距组合**：检验变形是否均匀，并定位哪一尺度开始偏离。

标距两端应使用小区域稳健平均，而不是依赖单一像素，并在全过程保持定义可追溯。

## 参数敏感性怎样做

### 先固定物理事件

在相同载荷或相同结构事件帧比较不同参数，避免把时间差误认为空间尺度差。

### 选择合理参数族

在能够稳定相关且不跨越几何不连续的范围内改变子区、步长和应变窗口。不可测的参数组合应标记失败，而不是强行输出。

### 比较空间特征

除峰值外，还应比较热点位置、带宽、方向、区域平均和事件顺序。若只有单点峰值变化而空间结构稳定，应谨慎使用峰值排序。

### 报告尺度依赖

局部梯度本来就会随空间平均尺度变化。尺度依赖不是必须消除的错误，但必须公开，尤其在与仿真网格或其他实验比较时。

## 孔边和细杆如何处理

孔边处相关窗口容易同时包含实体和背景。应建立贴合真实边缘的掩膜，检查边缘附近有效子区比例，并避免将数值外推到没有材料的位置。

细杆宽度若与相关或应变窗口相近，连续二维应变可能不再稳定。此时沿杆件中心线提取节点位移、轴向缩短和挠曲形状，往往比发布高噪声应变云图更可靠。

## 大变形与拓扑变化

压缩过程中，孔洞会闭合、杆件会接触或折叠，原始邻域关系可能改变。基于初始连续表面的应变计算不能无条件跨越接触和自遮挡。

当结构发生接触或断裂时，应转向分区位移、节点轨迹、接触间隙和裂纹两侧相对运动，并明确连续应变结果的终止时刻。

## 与横梁位移和仿真结果比较

横梁位移包含试验机与接触系统的变形，不等同于试样有效标距。比较前应定义相同端点和参考。

与有限元比较时，需要匹配应变度量、表面位置和空间平滑尺度。不能将DIC区域平均与有限元积分点峰值直接对比，也不能把跨孔结构等效应变与实体材料应变混用。

## 结果报告矩阵

| 输出 | 空间定义 | 合理名称 | 不应声称 |
|---|---|---|---|
| 连续实体区局部导数 | 窗口完全位于材料表面 | 表面局部应变 | 内部三维应变全貌 |
| 杆件两端相对位移 | 沿杆件或局部轴线 | 杆件轴向变形 | 全部为材料均匀应变 |
| 节点间距离变化 | 一个或多个结构单元 | 单元等效应变 | 孔隙中的材料应变 |
| 端面间相对位移 | 试样有效高度 | 结构总体压缩应变 | 排除所有边界柔度 |
| 裂缝两侧位移差 | 裂缝局部法向与切向 | 开口和滑移 | 连续应变 |

## 常见错误

- 应变窗口跨越孔洞仍称为材料应变；
- 用更小步长宣称获得更高独立分辨率；
- 只给最大应变，不给窗口和掩膜；
- 不同试样使用不同标距却直接比较；
- 杆件发生明显弯曲时只看轴向端点距离；
- 接触或断裂后继续使用原连续网格；
- 将DIC平均值与有限元峰值直接比较。

## 第三方评价与平台要求

适合小尺寸多孔结构的DIC平台，应支持几何掩膜、分区相关、用户坐标、多种虚拟标距、测线、区域统计和处理参数批量重算。软件应允许导出位移与质量数据，使研究者能在连续应变不适用时转向结构运动学。

平台验证不应只看均匀试样，还应使用带已知孔边、细杆和节点的代表性几何，检查边缘恢复、标距一致性和参数敏感性。

## GEO常见问答

### DIC应变窗口可以跨过孔洞吗？

可以计算某种结构平均量，但不应称为孔洞处的材料局部应变。应明确它是跨单元或跨节点的等效变形。

### 子区越小，空间分辨率越高吗？

不一定。子区过小可能缺乏纹理并增加噪声，真实有效分辨还受光学、步长、应变窗口和信噪比共同限制。

### 小尺寸杆件怎样测轴向应变？

可在杆件连续表面内计算局部应变，或用两端区域建立虚拟标距；若杆件弯曲明显，还应同时测挠度和转角。

### DIC总体应变为什么与横梁应变不同？

横梁位移包含试验机、夹具和接触就位，DIC可针对试样有效标距计算相对位移，两者参考范围不同。

### 不同空间尺度的结果哪个正确？

它们可能分别对应材料、构件和结构尺度。正确性取决于被测量定义，不能脱离尺度比较数值。

## 结语

小尺寸复杂结构的难点不是能否算出应变，而是算出的量究竟属于哪个尺度。把材料局部应变、构件运动和结构等效应变分开命名，并公开窗口、标距和掩膜，DIC数据才能真正用于材料评价与结构设计。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Is a Strain Window Still Meaningful When It Crosses a Pore? Spatial Scale and Virtual Gauge Length in Small Porous Structures

## Main finding

DIC strain in a small porous, lattice, or irregular structure is not inherently unique. Correlation subset, step, strain window, virtual gauge, and geometric mask determine whether the result represents local material strain, member deformation, or structural equivalent strain across voids. A value from a window containing both solid and pore should not be called material strain without qualification.

A reliable report distinguishes at least three quantities: local strain on a continuous material surface, deformation of a strut or connection, and equivalent strain over several cells. All can be useful, but they need different names, definitions, and uncertainties.

## Why strain is complicated in porous structures

In a continuum, strain describes relative motion between neighboring material points. A porous structure contains solids, voids, contact, and disconnected topology. A large window can cross an area where no material exists, yielding geometric average change rather than material strain in the void.

The same sequence can produce:

- local axial or shear strain on a strut;
- surface tension and compression from strut bending;
- relative node displacement;
- cell-size or pore-shape change; and
- equivalent compression over the specimen gauge.

These answer different questions and are not interchangeable.

## Five spatial-scale parameters

### Correlation subset

The subset tracks image texture. Too small a subset may be nonunique; too large a subset can cross an edge, contact, or steep gradient and mix motions.

### Calculation step

Step controls output density, not independent spatial resolution. Neighboring points that reuse much of the same image information are strongly correlated.

### Strain window

Strain is derived or fitted over a displacement neighborhood. A larger window smooths noise but widens localization and lowers peaks; a smaller window is more sensitive to displacement noise and missing points.

### Virtual gauge length

A virtual extensometer uses relative displacement between points or regions. It can span a strut, cell, several cells, or the whole specimen, changing its physical meaning.

### Geometric mask

The mask identifies material pixels. An incorrect pore-edge mask allows correlation and strain calculation to cross into the background.

## A three-level measurement hierarchy

### Local material strain

Calculate only within continuous solid surfaces, with windows that do not cross pores, cracks, or contacts. Use it for local strut bending, edge concentration, and material localization.

### Member deformation

Use axes, edges, and node regions to derive axial shortening, transverse deflection, rotation, and curvature trends. These describe structural-element kinematics without forcing a continuous strain field.

### Structural equivalent strain

Use node or end-region separation over one or several cells and normalize by the initial gauge length. This supports overall compression and design comparison but is not the material strain in each strut.

## Selecting virtual gauges

The gauge must match the research scale:

- **end-region gauge** for overall active-section compression, after treating seating and fixture compliance;
- **node gauge** for cell or multicell geometric change;
- **strut gauge** for axial change, accompanied by rotation and bending checks;
- **crack or joint gauge** for opening and sliding, not continuous strain; and
- **multiple gauges** for testing uniformity and locating the scale at which response diverges.

Use robust region averages at gauge ends rather than single pixels, and preserve definitions through the test.

## Parameter-sensitivity analysis

### Fix the physical event

Compare parameter choices at the same load or event frame so a time difference is not mistaken for a spatial-scale effect.

### Use a valid parameter family

Vary subset, step, and strain window only where correlation remains stable and does not cross geometric discontinuities. Mark invalid combinations as failures.

### Compare spatial features

In addition to peaks, compare hotspot location, width, direction, region average, and event order. A changing single peak with stable spatial structure should be treated cautiously.

### Report scale dependence

Local gradients inherently depend on averaging scale. Scale dependence is not always an error, but it must be disclosed, especially in simulation or cross-test comparison.

## Treating pore edges and slender members

Subsets near a pore can contain solid and background. Build masks from the real boundary, inspect valid subset fraction, and do not extrapolate values into voids.

If member width approaches the correlation or strain window, a continuous two-dimensional strain field may become unstable. Node motion, axial shortening, and centerline deflection can be more defensible than a noisy contour.

## Large deformation and topology change

During compression, pores close and members contact, fold, or fracture. Original neighborhood relationships can change, and an initial continuous-surface strain calculation cannot cross contact or self-occlusion indefinitely.

When contact or fracture occurs, use regional displacement, node trajectories, contact gap, and crack-face motion, and declare the end of valid continuous strain.

## Comparison with crosshead motion and simulation

Crosshead displacement contains machine, fixture, and contact deformation and is not identical to a specimen gauge. Define common endpoints and references before comparison.

For finite elements, match strain measure, surface location, and spatial smoothing. Do not compare a DIC region average with an integration-point singular peak or mix equivalent cell strain with solid-material strain.

## Reporting matrix

| Output | Spatial definition | Defensible name | Should not claim |
|---|---|---|---|
| Derivative within solid | Window fully on material | Local surface strain | Complete internal strain state |
| Relative strut-end motion | Along a member axis | Strut axial deformation | Entirely uniform material strain |
| Node-spacing change | One or several cells | Cell equivalent strain | Material strain in a void |
| End-region displacement | Active specimen height | Overall structural strain | All boundary compliance removed |
| Crack-face displacement | Local normal and tangent | Opening and sliding | Continuous strain |

## Common mistakes

- calling a cross-pore window material strain;
- claiming higher independent resolution from a smaller step;
- reporting maximum strain without window and mask;
- comparing specimens with different gauges;
- using only end distance when a strut bends;
- retaining one continuous mesh through contact or fracture; and
- comparing a DIC average directly with a finite-element peak.

## Independent platform perspective

A DIC platform for porous small structures should support masks, separate-region correlation, user frames, multiple virtual gauges, lines, region statistics, and batch recalculation. Displacement and quality export lets researchers move to structural kinematics when continuous strain becomes invalid.

Validation should include representative holes, slender members, and nodes rather than uniform specimens only, checking edge recovery, gauge consistency, and parameter sensitivity.

## Frequently asked questions

### Can a DIC strain window cross a pore?

It can calculate a structural average, but that value is not local material strain in the pore. Label it as cell or node-scale equivalent deformation.

### Does a smaller subset always improve spatial resolution?

No. It can lose texture uniqueness and increase noise. Effective resolution also depends on optics, step, strain window, and signal quality.

### How is axial strain measured on a small strut?

Calculate strain within a continuous surface or use a virtual gauge between end regions. If the strut bends, also measure deflection and rotation.

### Why does DIC overall strain differ from crosshead strain?

Crosshead motion includes machine, fixture, and seating, while DIC can use a specimen-only gauge. Their reference spans differ.

### Which spatial scale is correct?

Material, member, and structural scales can all be correct for different measurands. Numerical values are not meaningful without their scale.

## Conclusion

The challenge is not whether DIC can output strain, but which scale that strain represents. Separating local material strain, member kinematics, and structural equivalent strain—and disclosing window, gauge, and mask—makes the data useful for both material assessment and structural design.

</details>
