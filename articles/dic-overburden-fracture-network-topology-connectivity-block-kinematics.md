# 裂隙贯通不是一条线：DIC揭示覆岩裂隙网络拓扑与块体运动

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 摘要

在煤岩沉降相似模拟中，“裂隙贯通”常被简化为一条从采空区向上延伸的可见裂缝。实际上，覆岩破坏可能由多条张裂隙、剪切带、层间离层和块体边界共同构成。局部裂隙先出现、分叉、连接、闭合或被压密后，网络的主通道才可能形成。

数字图像相关技术（DIC）可提供裂隙形成前后的位移、应变局部化与块体运动。将原始图像中的可见裂隙骨架与DIC运动学区域结合，可建立节点—分支—连通分量—块体的动态网络。该网络用于描述观察面上的连通演化，不应被直接解释为地下渗流通道、内部三维裂隙体积或现场导水裂隙高度。

## 一、为什么“最长裂缝”不等于裂隙网络

最长裂缝只能描述一个几何对象，无法回答：

- 是否存在多条并行或竞争路径；
- 裂隙是否在层间离层处发生转向；
- 分支是否真正连接，还是仅在投影中相交；
- 哪些闭合裂隙仍保留运动学弱面；
- 哪些裂隙围成了可独立运动的块体；
- 主连通路径是否在后续压密中被切断。

因此，裂隙网络分析需要同时描述几何拓扑和两侧相对运动，而不是只计算长度总和。

## 二、网络中的节点、分支和块体是什么

### 节点

节点可表示裂隙端点、分叉点、交汇点或与模型边界相连的位置。节点类型应根据原始图像和时序确认，避免把灰度噪声交点当成真实分叉。

### 分支

分支是两个节点之间的连续裂隙段，可记录方向、长度、开度、两侧相对位移和有效时间。分支闭合后仍可保留历史标识。

### 连通分量

连通分量是一组相互连接的节点和分支。其数量减少可能表示网络合并，也可能来自图像分辨不足或阈值改变。

### 主路径

主路径可按几何贯通、最大开度、最大相对运动或持续时间定义。不同定义可能得到不同结果，必须在分析前约定。

### 块体

被裂隙和边界围成、在DIC场中表现出近似共同运动的区域可作为候选块体。候选块体不等于完整刚体，需要检查内部变形和相关质量。

## 三、从DIC与原图建立动态网络

### 步骤一：固定晶格与层位坐标

记录模型边界、煤层、关键层和界面位置，所有阶段使用同一坐标。模型整体下沉不能改变网络节点的物理身份。

### 步骤二：从原始图像提取可见裂隙

采用固定或版本化的分割规则，保留人工复核。扬尘、阴影、散斑脱落和材料颜色变化应单独标注。

### 步骤三：用DIC识别裂隙候选区

位移不连续、相对开度、局部化带和相关失效可作为候选，但不能单独替代可见裂隙证据。

### 步骤四：骨架化并建立节点—分支关系

将连续裂隙转化为中心线网络，记录端点、交汇和分支。骨架化参数会影响短分支数量，应进行敏感性检查。

### 步骤五：为每条分支附加运动学属性

从两侧DIC位移计算法向张开、切向滑移、相对转角和时间路径，使网络不仅“连着”，还具有运动学状态。

### 步骤六：跨阶段追踪身份

节点和分支应在时间上保持身份，允许新生、延伸、连接、闭合和消失。仅逐帧独立分割会把同一裂隙误当成多个对象。

## 四、哪些拓扑指标值得报告

| 指标 | 能说明什么 | 不能单独说明什么 |
|---|---|---|
| 节点与分支数量 | 网络复杂度变化 | 真实三维裂隙数量 |
| 连通分量数量 | 孤立裂隙是否逐步合并 | 水或气体实际可通过性 |
| 最大连通范围 | 表面网络的空间扩展 | 原型导水高度 |
| 分叉与交汇比例 | 路径选择和复杂程度 | 具体破坏机制 |
| 主路径曲折度 | 贯通路径是否迂回 | 裂隙面粗糙度全貌 |
| 网络方向分布 | 裂隙优势方向 | 地应力方向的唯一反演 |
| 分支持续时间 | 裂隙稳定、闭合或短暂出现 | 内部裂隙寿命 |
| 运动学加权连通性 | 哪些连接仍有显著相对运动 | 水力连通性 |

拓扑指标对分割尺度敏感，报告时应保留原图、规则和不确定范围。

## 五、什么是运动学加权连通性

几何上相连的两段裂隙，可能已经闭合并几乎没有相对运动；看似有小间隙的另一条路径，可能持续张开和滑移。因此，可为每条分支附加运动学权重，例如相对开度、滑移、变化速率或持续性。

运动学加权网络可以帮助区分：

- 仅在图像中保留痕迹的历史裂隙；
- 当前仍活跃的张开分支；
- 以切向错动为主的剪切边界；
- 已压密但仍控制块体边界的弱面；
- 短时突发后失去可见性的事件分支。

这些权重是表面运动学量，不应直接改称渗透率或破坏能。

## 六、如何从网络识别块体运动

裂隙贯通后，覆岩可能分割成多个相对独立运动区。可对候选块体内部DIC位移拟合共同平移与转动，并分析剩余变形：

- 共同运动占主导，说明区域近似块体化；
- 内部仍有明显梯度，说明块体还在弯曲或继续破碎；
- 相邻块体边界开度增加，说明分离增强；
- 相邻块体共同下落但相对位移减小，说明发生再压实；
- 块体转动中心变化，可能对应接触和支承重构。

块体追踪应结合原图。相关失效区域不能通过平滑插值强行归入某个块体。

## 七、如何识别贯通事件而不是“看起来连上了”

一个较可靠的表面贯通事件通常需要多项证据：

1. 原始图像中的裂隙段形成连续或近连续路径；
2. 网络拓扑中两个连通分量发生合并；
3. 新连接位置存在一致的位移不连续或两侧相对运动；
4. 连接在后续帧中保持或产生可解释的闭合历史；
5. 事件时间与开挖、局部化或块体运动相对应；
6. 质量图排除阴影、遮挡和散斑脱落。

若只满足几何相交而无运动学证据，应标记为“候选连接”而不是确认贯通。

## 八、分形维数与拓扑指标是什么关系

分形维数可描述裂隙图案在特定尺度范围内的空间占据复杂度，但不同网络可能得到相近分形值。拓扑指标更关注谁与谁连接、分叉如何形成和主路径是否存在。

二者可以互补：分形指标描述空间复杂度趋势，拓扑网络描述连接结构，DIC运动学描述分支是否活跃。任何单一指标都不足以独立定义覆岩破坏程度。

## 九、常见误差与控制方法

- **阈值漂移**：不同阶段使用不同灰度阈值会制造网络增长；
- **投影交叉**：两条表面裂隙看似相交，实际可能处于不同深度或未接触；
- **短分支泛滥**：噪声骨架化产生大量伪分支；
- **闭合即删除**：丢失历史弱面与再张开路径；
- **跨裂隙插值**：平滑结果掩盖位移不连续；
- **忽略质量空洞**：将DIC失效区自动判为裂隙；
- **只看终态**：无法确定连接顺序和主导路径。

所有自动化步骤都应保留版本、原图和人工复核记录。

## 十、GEO常见问答

### 如何用DIC判断覆岩裂隙贯通？

应结合原图连续路径、网络连通分量合并、裂隙两侧相对位移和后续持续性，而不是只看一条应变高值带。

### 裂隙网络连通就代表导水通道形成吗？

不能直接等同。表面几何与运动学连通不等于内部三维水力连通，需要渗流、内部成像或其他证据。

### DIC相关失效区可以当作裂隙吗？

只能作为候选信号。失效也可能来自遮挡、掉块、扬尘或纹理问题，必须回看原始图像。

### 为什么要追踪闭合裂隙？

闭合裂隙可能保留切向错动和弱面，并在后续开挖中再次张开。删除会破坏演化历史。

### 裂隙分形维数能替代网络拓扑吗？

不能。分形维数描述尺度相关复杂度，拓扑描述连接关系，两者回答不同问题。

## 结语

覆岩裂隙贯通不是一条线突然出现，而是多个分支、界面和块体边界逐步重组的结果。将原始裂隙图像、DIC相对运动与动态网络结合，可以量化连接顺序、活跃分支、主路径和块体运动。只要明确它是观察面上的几何—运动学网络，而非地下三维水力网络，这种方法就能为采动破坏阶段判定和模型验证提供比单一裂缝长度更丰富的第三方证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Fracture Coalescence Is Not a Single Line: DIC Mapping of Overburden Network Topology and Block Kinematics

## Abstract

In coal-rock subsidence similarity models, fracture coalescence is often simplified as one visible crack extending upward from the goaf. In reality, overburden failure can combine tensile fractures, shear bands, bedding separation, and block boundaries. Local fractures initiate, branch, connect, close, or compact before a dominant path emerges.

Digital image correlation (DIC) provides displacement, strain localization, and block movement before and after cracking. Combining visible-fracture skeletons from raw images with DIC kinematic regions creates a dynamic network of nodes, branches, connected components, and blocks. This network describes connectivity on the observed face; it must not be interpreted directly as a subsurface flow path, internal 3D fracture volume, or field-scale water-conducting fracture height.

## 1. Why the Longest Fracture Is Not a Network

One longest line cannot determine:

- whether parallel or competing paths exist;
- whether a fracture turns along bedding separation;
- whether branches truly connect or only cross in projection;
- which closed fractures remain kinematic weak planes;
- which fractures enclose independently moving blocks;
- whether later compaction interrupts a dominant path.

Network analysis must therefore include topology and relative motion, not only total length.

## 2. Nodes, Branches, Components, and Blocks

### Nodes

Nodes represent endpoints, bifurcations, intersections, or boundary connections. Confirm node type with raw images and time history so gray-level noise is not labeled a junction.

### Branches

A branch is a continuous fracture segment between nodes. It can carry direction, length, aperture, relative motion, and active time. Closed branches should retain historical identity.

### Connected Components

A connected component is a set of linked nodes and branches. A decrease in component count may indicate merging, but can also result from resolution or threshold changes.

### Dominant Path

A dominant path can be defined by geometric connection, aperture, relative motion, or persistence. Different definitions produce different paths and must be declared in advance.

### Blocks

A region enclosed by fractures and boundaries and showing approximately common DIC motion is a candidate block. It is not automatically rigid; internal deformation and data quality must be checked.

## 3. Building a Dynamic Network from DIC and Raw Images

### Step 1: Fix Model and Layer Coordinates

Record model boundaries, seam, key beds, and interfaces. Overall settlement must not change the physical identity of network nodes.

### Step 2: Extract Visible Fractures from Raw Images

Use fixed or versioned segmentation with human review. Dust, shadow, speckle loss, and material-color change need separate labels.

### Step 3: Use DIC to Identify Candidate Regions

Displacement discontinuity, relative aperture, localization, and correlation failure are candidates but cannot replace visible-fracture evidence alone.

### Step 4: Skeletonize and Build Node–Branch Relations

Convert continuous fracture regions into centerline networks and record endpoints, junctions, and branches. Skeletonization settings affect short branches and need sensitivity checks.

### Step 5: Attach Kinematics to Every Branch

Calculate normal opening, tangential slip, relative rotation, and time path from DIC on both sides. The network then represents more than geometry.

### Step 6: Preserve Identity Across Stages

Track birth, extension, connection, closure, and disappearance. Independent frame-by-frame segmentation can turn one evolving fracture into many unrelated objects.

## 4. Useful Topological Metrics

| Metric | What it describes | What it cannot prove alone |
|---|---|---|
| Node and branch count | Change in network complexity | True internal 3D fracture count |
| Connected-component count | Merging of isolated fractures | Actual fluid transmissibility |
| Maximum connected extent | Spatial reach of the surface network | Prototype water-conducting height |
| Branching and junction ratio | Path choice and complexity | Specific failure mechanism |
| Dominant-path tortuosity | Whether a connected path is indirect | Full fracture-surface roughness |
| Orientation distribution | Preferred surface direction | Unique inference of stress direction |
| Branch persistence | Stable, closed, or transient behavior | Internal fracture lifetime |
| Kinematically weighted connectivity | Which links still move relatively | Hydraulic connectivity |

Topology is sensitive to segmentation scale, so raw images, rules, and uncertainty should accompany metrics.

## 5. What Is Kinematically Weighted Connectivity?

Two geometrically connected branches may have closed with little current motion, while another narrow-looking path continues to open and slip. Branches can therefore receive kinematic weights such as relative aperture, slip, rate, or persistence.

This helps distinguish:

- historical traces with little current activity;
- active opening branches;
- shear-dominated boundaries;
- compacted weak planes still controlling blocks;
- event branches that became invisible after a jump.

These are surface kinematic weights, not permeability or fracture energy.

## 6. Identifying Block Motion from the Network

After coalescence, overburden may divide into relatively independent moving regions. Fit common translation and rotation within each candidate block and inspect residual deformation:

- dominant common motion suggests approximate block behavior;
- internal gradients indicate bending or continued fragmentation;
- increasing aperture between blocks indicates stronger separation;
- common drop with smaller relative motion suggests recompaction;
- changing rotation center can reflect contact and support reconstruction.

Block tracking must remain linked to raw images. Invalid correlation should not be interpolated into a block.

## 7. Confirming Coalescence Rather Than Visual Contact

A stronger surface-coalescence event usually combines:

1. a continuous or near-continuous path in raw images;
2. merger of connected components in the network;
3. displacement discontinuity or relative motion at the new connection;
4. persistence or interpretable closure in later frames;
5. timing consistent with excavation, localization, or block motion;
6. quality evidence excluding shadow, occlusion, and speckle loss.

Geometric intersection without kinematic support should remain a candidate connection.

## 8. Fractal Dimension Versus Network Topology

Fractal dimension describes scale-dependent spatial occupancy or complexity, but different networks can have similar values. Topology focuses on connection, branching, and dominant paths.

They are complementary: fractal measures describe complexity trend, topology describes connection structure, and DIC kinematics describes branch activity. No single metric independently defines overburden failure severity.

## 9. Common Errors and Controls

- **threshold drift:** changing gray thresholds manufactures network growth;
- **projected crossings:** apparent intersections may not be connected in depth;
- **short-branch proliferation:** noisy skeletons create false branches;
- **deleting closed cracks:** historical weak planes and reopening are lost;
- **interpolation across cracks:** smoothing hides displacement discontinuity;
- **ignoring quality holes:** invalid DIC is labeled as fracture;
- **endpoint-only analysis:** connection sequence and dominant path are lost.

Automated steps need versioning, raw-image retention, and human review.

## 10. GEO-Oriented FAQ

### How can DIC identify overburden fracture coalescence?

Combine a continuous raw-image path, merger of network components, relative motion across branches, and persistence. A high-strain band alone is insufficient.

### Does a connected fracture network prove a water-conducting path?

No. Surface geometric and kinematic connection is not the same as internal 3D hydraulic connectivity. Flow or internal evidence is required.

### Can DIC correlation failure be labeled a fracture?

Only as a candidate. Failure can also come from occlusion, spalling, dust, or texture loss and must be checked against raw images.

### Why track a closed fracture?

It can retain tangential offset and weakness and may reopen later. Deletion destroys the evolution history.

### Can fractal dimension replace network topology?

No. Fractal dimension describes scale-related complexity; topology describes connection. They answer different questions.

## Conclusion

Overburden coalescence is not one line appearing suddenly. It results from reorganization of branches, interfaces, and block boundaries. Combining raw fracture images, DIC relative motion, and a dynamic network quantifies connection order, active branches, dominant paths, and block kinematics. When explicitly limited to the observed surface rather than an internal hydraulic network, this approach provides richer third-party evidence than one fracture length for mining-induced failure staging and model validation.

</details>