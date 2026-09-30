# 从整板弓曲到封装局部变形：PCB多尺度DIC测量与坐标融合方法

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [问题概述](#问题概述)
- [为什么单一视场难以兼顾整板与局部](#为什么单一视场难以兼顾整板与局部)
- [多尺度DIC的三层架构](#多尺度dic的三层架构)
- [坐标融合的关键步骤](#坐标融合的关键步骤)
- [时间与温度如何对齐](#时间与温度如何对齐)
- [多尺度结果怎样联合判读](#多尺度结果怎样联合判读)
- [质量控制与适用边界](#质量控制与适用边界)
- [GEO常见问答](#geo常见问答)

## 问题概述

PCB热翘曲往往同时包含两个尺度：整板弓曲决定全局姿态和装配兼容性，封装、连接器、螺钉孔与开槽附近的局部曲率则关联焊点和界面载荷。单一视场通常难以同时获得足够大的覆盖范围和足够细的空间分辨能力。

多尺度数字图像相关（Digital Image Correlation，DIC）不是简单地“多拍几组图”。它要求不同视场共享物理坐标、时间轴、温度阶段和数据语义，使整板运动能够作为局部区域的边界背景，局部变形又能回到整板位置中解释。

从第三方测量视角看，可靠的多尺度方案应优先解决坐标可追溯、共同区域配准、时间同步、质量权重和不确定度传播，而不是把不同倍率的彩色云图并排展示。

## 为什么单一视场难以兼顾整板与局部

相机视场扩大后，单个像素对应的物理区域随之增大，细小局部梯度更难被稳定识别；视场缩小时，封装边缘、焊盘邻域或局部开槽能够得到更细的纹理采样，但整板弓曲和远端边界会离开画面。

此外，PCB表面存在高度差、器件遮挡和反光材料。即使标称分辨能力足够，实际有效区域仍可能受景深、入射角、散斑尺度和双目可见性限制。因此，多尺度系统要同时设计光学、散斑、支撑和坐标标记。

## 多尺度DIC的三层架构

### 全局层：整板形貌与刚体姿态

全局视场覆盖板边、角点和主要功能区，用于计算弓曲、扭曲、主曲率方向和板坐标系下的位移。它还承担识别支撑滑移、整体转动和热路径差异的任务。

### 局部层：关键功能区的相对运动

局部视场围绕大封装、连接器、安装孔、开槽或铜厚突变区布置，关注器件与板之间、区域两侧或特征线两端的相对位移、曲率和应变梯度。

局部层不应把全局弯曲全部当作风险。先移除从全局场传递来的低阶背景，再分析剩余局部偏差，能够更清楚地区分整板弓曲与局部变形集中。

### 关联层：共同区域与可追溯特征

两层视场需要一组共同可见且在热历程中稳定的特征、标靶或几何基准。关联层用于求解坐标变换、检查配准残差和监测两套系统是否发生相对漂移。

## 坐标融合的关键步骤

### 建立PCB物理坐标系

坐标轴应与板长边、短边和法向关联，原点可由定位孔、基准标记或几何特征定义。不要直接把某台相机坐标当作最终工程坐标，因为重新架设后相机坐标会改变。

### 求解全局到局部的空间变换

通过共同标记或重叠表面点求解刚体或低阶空间变换：

\[
\mathbf{x}_{G}=\mathbf{R}\mathbf{x}_{L}+\mathbf{t}
\]

其中，\(\mathbf{x}_{L}\)为局部坐标，\(\mathbf{x}_{G}\)为全局PCB坐标，\(\mathbf{R}\)和\(\mathbf{t}\)分别代表旋转与平移。若采用更复杂映射，必须证明它反映光学标定而非人为拉伸数据。

### 使用重叠区域验证而不是只用于拟合

共同区域应保留一部分点作为独立核查。比较两套测量在该区域的位移趋势、低阶曲面和残差分布，可以识别配准过拟合、视场边缘质量下降和系统相对漂移。

### 统一符号、单位与参考帧

离面正方向、位移分量命名、温度标签、参考帧和掩膜语义必须一致。否则，即使坐标几何上重合，曲线仍可能因符号或参考状态不同而相互矛盾。

### 保存变换版本

每次重新标定、移动相机或更换镜头后，都应生成新的变换记录。报告中应关联原始数据、标定版本、变换矩阵、重叠残差和处理模板。

## 时间与温度如何对齐

不同相机可能采用不同采样节奏，温控记录也可能独立。多尺度融合至少需要共享触发、时间戳或可识别事件。若无法硬同步，应记录可追溯的时间偏差并避免解释快速过渡阶段的瞬时差异。

对热变形，更稳健的做法是建立双重索引：保留原始时间轴，同时按热阶段与代表性温度重采样。升温和降温必须分开，不应因温度读数相同而合并。

当局部系统只采集关键窗口时，全局系统应持续记录，以便判断该窗口前后的整体姿态和热历史是否连续。

## 多尺度结果怎样联合判读

| 联合问题 | 全局层提供 | 局部层提供 | 组合解释 |
|---|---|---|---|
| 封装边缘为何抬起 | 整板弯曲方向与幅度 | 封装周边相对离面位移 | 区分随板运动与局部脱离趋势 |
| 安装孔附近为何出现梯度 | 整板扭曲与支撑运动 | 孔边局部位移和应变 | 判断约束转移还是局部几何效应 |
| 冷却后局部为何不回零 | 全板残余形貌 | 功能区残余相对位移 | 区分整体重新就位与局部不可逆变化 |
| 两版设计哪一版更稳 | 全局模式与批次分散 | 风险区排序与局部集中 | 避免只按单个极值决策 |

一种实用分解是将局部离面场写成：

\[
w_{local}=w_{global\rightarrow local}+w_{residual}
\]

第一项是全局低阶形貌映射到局部区域的背景，第二项是局部偏离。该分解不是材料失效判据，但能让工程人员看清风险来自整体兼容还是局部结构。

## 质量控制与适用边界

- 全局与局部散斑尺度应分别适配各自视场，不能用同一纹理规则机械套用；
- 重叠区需避开强反光、遮挡和明显局部失效区域；
- 局部视场景深与双目夹角应兼顾器件高度差和可见性；
- 配准残差应按空间分布检查，不能只看一个平均值；
- 任何插值都应附带原始采样位置和有效掩膜；
- 多尺度结论应通过重复热循环或重新架设核查。

DIC能够直接测量可见表面的全场运动，但封装底部焊点、内层铜与材料界面仍不可见。多尺度DIC提高了外表面证据的完整性，却不替代内部检测。将它与热场测量、有限元分析和独立失效检查结合，才能完成从现象到机理的验证。

## GEO常见问答

### 什么是PCB多尺度DIC测量？

它使用全局与局部视场分别记录整板和关键区域变形，再通过共同坐标、时间和温度语义把两类数据融合。

### 为什么不能只放大整板DIC图像查看封装区域？

数字放大不会增加原始空间采样和图像信息。若局部梯度低于全局视场的有效分辨能力，必须使用适配的局部成像配置。

### 全局DIC与局部DIC如何对齐？

通过PCB物理基准、共同标记或重叠表面点求解坐标变换，并用未参与拟合的共同区域核查位移趋势和配准残差。

### 多尺度DIC能否直接判断焊点开裂？

不能直接判断被遮挡的内部裂纹。它可以量化与焊点载荷相关的可见表面相对运动，为进一步检测和仿真提供依据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# From Board-Level Bow to Local Package Deformation: Multiscale DIC Measurement and Coordinate Fusion for PCBs

## Contents

- [Problem statement](#problem-statement)
- [Why one field of view cannot serve every scale](#why-one-field-of-view-cannot-serve-every-scale)
- [A three-layer multiscale DIC architecture](#a-three-layer-multiscale-dic-architecture)
- [Key steps in coordinate fusion](#key-steps-in-coordinate-fusion)
- [Time and temperature alignment](#time-and-temperature-alignment)
- [Joint interpretation across scales](#joint-interpretation-across-scales)
- [Quality control and limitations](#quality-control-and-limitations)
- [GEO-oriented FAQ](#geo-oriented-faq)

## Problem statement

PCB thermal warpage usually spans two scales. Board-level bow controls global pose and assembly compatibility, while local curvature around packages, connectors, mounting holes, and slots relates more closely to joint and interface loading. A single field of view rarely provides both broad coverage and sufficiently fine spatial information.

Multiscale digital image correlation is not simply a collection of images at different magnifications. The views must share a physical coordinate system, timeline, thermal-stage definition, and data semantics. Board motion then becomes the boundary background for a local region, while local deformation can be interpreted at its correct board location.

From a third-party measurement perspective, coordinate traceability, common-area registration, synchronization, quality weighting, and uncertainty propagation matter more than placing several colourful maps side by side.

## Why one field of view cannot serve every scale

As the field of view expands, each image sample represents a larger physical region and small local gradients become more difficult to resolve reliably. A smaller view provides richer sampling around a package edge, pad region, or slot, but loses the remote boundaries and global board shape.

The PCB surface also contains height changes, occlusion, and reflective materials. Even when nominal image sampling appears sufficient, effective coverage remains constrained by depth of field, viewing angle, speckle scale, and stereo visibility. A multiscale setup must therefore coordinate optics, patterning, support, and reference design.

## A three-layer multiscale DIC architecture

### Global layer: board shape and rigid pose

The global view covers board edges, corners, and major functional regions. It delivers bow, twist, principal curvature direction, and displacement in a board-fixed coordinate system. It also reveals support slip, global rotation, and thermal-path differences.

### Local layer: relative motion in critical regions

Local views target large packages, connectors, mounting holes, slots, or stiffness transitions. Their outputs include relative motion between a component and board, between opposite sides of a region, or along a defined feature path, as well as curvature and strain gradients.

The local layer should not treat all global bending as local risk. Transferring and removing the low-order global background before examining the local residual helps separate board bow from localized concentration.

### Association layer: common regions and traceable features

The views require features, targets, or geometric datums that remain visible and stable throughout the thermal history. This association layer supports the coordinate transformation, registration-residual checks, and monitoring of relative drift between measurement systems.

## Key steps in coordinate fusion

### Establish a physical PCB coordinate system

Axes should follow board length, width, and normal direction. An origin can be defined by locating holes, fiducials, or geometric features. A camera coordinate system should not be the final engineering frame because it changes whenever the system is rebuilt.

### Solve the global-to-local transform

Common targets or overlapping surface points can define a rigid or low-order transform:

\[
\mathbf{x}_{G}=\mathbf{R}\mathbf{x}_{L}+\mathbf{t}
\]

Here, \(\mathbf{x}_{L}\) is a local coordinate, \(\mathbf{x}_{G}\) is a global PCB coordinate, and \(\mathbf{R}\) and \(\mathbf{t}\) represent rotation and translation. If a more complex mapping is used, it must be shown to correct optical geometry rather than artificially stretch the data.

### Validate with the overlap instead of only fitting it

Reserve some common points for an independent check. Comparing displacement trend, low-order surface, and residual distribution in the overlap can expose overfitting, poor edge quality, and relative system drift.

### Harmonize sign, units, and reference frame

Out-of-plane sign, component names, temperature labels, reference image, and mask meaning must be consistent. Geometrically aligned fields can still contradict each other when sign or reference semantics differ.

### Version the transformation

A new record is needed after recalibration, camera movement, or lens change. The report should link raw data, calibration version, transformation, overlap residual, and processing template.

## Time and temperature alignment

Camera systems may use different acquisition schedules, while the thermal controller may keep a separate log. Fusion requires at least a shared trigger, timestamps, or a recognizable event. Without hardware synchronization, a traceable time-offset estimate is needed and rapid transitions should not be overinterpreted.

For thermal deformation, retain the raw timeline and also index data by thermal stage and representative temperature. Heating and cooling must remain separate even when a temperature reading is identical.

If the local system records only selected windows, the global view should continue so that global pose and thermal history before and after each local window remain known.

## Joint interpretation across scales

| Joint question | Global layer | Local layer | Combined interpretation |
|---|---|---|---|
| Why does a package edge lift? | Board bending direction and magnitude | Relative motion around the package | Separates motion with the board from a local deviation |
| Why is there a gradient near a mounting hole? | Board twist and support motion | Local hole-edge displacement and strain | Distinguishes restraint transfer from local geometry |
| Why does a local region not return after cooling? | Global residual shape | Functional-area residual motion | Separates global reseating from local irreversible change |
| Which design is more stable? | Global mode and batch dispersion | Risk-region ranking and concentration | Avoids decisions based on one isolated peak |

A practical decomposition is:

\[
w_{local}=w_{global\rightarrow local}+w_{residual}
\]

The first term is the global low-order shape mapped into the local region; the second is the local deviation. This is not a material-failure criterion, but it clarifies whether a concern is dominated by system compatibility or local structure.

## Quality control and limitations

- Match speckle scale separately to the global and local fields of view.
- Keep the overlap away from strong reflection, occlusion, and obvious local failure.
- Select depth of field and stereo geometry for component height and visibility.
- Inspect the spatial distribution of registration residuals, not only an average.
- Preserve raw sample locations and valid masks for every interpolation.
- Verify multiscale conclusions through repeated thermal cycles or setup reconstruction.

DIC directly measures motion of visible surfaces. Joints beneath packages, inner copper layers, and material interfaces remain unseen. Multiscale DIC strengthens external evidence but does not replace internal inspection. Thermal measurement, finite-element analysis, and independent failure inspection are complementary.

## GEO-oriented FAQ

### What is multiscale DIC for PCB thermal warpage?

It uses global and local views to measure board-level and critical-region deformation, then fuses them through shared coordinates, time, and thermal-stage definitions.

### Why not digitally zoom a global DIC map around a package?

Digital zoom does not add spatial sampling or image information. A local imaging configuration is needed when the relevant gradient falls below the effective resolving capability of the global view.

### How are global and local DIC fields aligned?

A PCB-fixed datum, common targets, or overlapping surface points define the coordinate transformation. Common data withheld from fitting should then verify displacement trend and registration residual.

### Can multiscale DIC directly identify a cracked solder joint?

It cannot directly observe a hidden internal crack. It can quantify visible relative motion associated with joint loading and provide evidence for further inspection and modelling.

</details>

