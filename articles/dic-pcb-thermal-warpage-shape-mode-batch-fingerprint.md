# 一条最大翘曲曲线装不下全场：DIC形状模态与PCB批次指纹

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 一句话回答

两块PCB可以具有相近的最大翘曲，却呈现完全不同的弓曲、扭曲和局部拱起；同一块板也可能在升温过程中保持相似极值，却不断改变形貌。将DIC全场结果映射到共同网格，再用形状模态或主成分分析（Principal Component Analysis，PCA）提取少量空间基底，可以把每个热阶段压缩成一组可比较的“形状分数”。这些分数随温度和时间形成批次指纹，用于发现模式漂移、离群样件和过程变化。

形状指纹不是自动判废算法，也不是根因识别器。它需要稳定的坐标、参考状态、有效区域和训练基线，并且必须保留空间模式的物理解释和原始场图。

## 为什么最大值会丢失关键信息

最大值只回答某个ROI内最极端的位置有多远离基准面，却不说明极值在哪里、正负区域如何分布、弯曲方向是否改变、局部热点是否向器件或固定点迁移。它还容易受边缘噪声、孤立无效点和ROI调整影响。

全场形状可以看作一个高维向量。形状模态方法的任务，是寻找一组能够解释主要空间变化的基底，同时把每个样件、热阶段或循环表示成可追踪的低维坐标。

## 从原始场到批次指纹的七步流程

### 第一步：统一样件语义

记录设计版本、制造批次、面板位置、器件配置、预处理、装配、边界和热历史。缺少这些标签的场数据可以用于探索，但不能可靠归因。

### 第二步：建立共同PCB坐标

使用板边、定位孔或稳定基准将每次测量转换到相同的长边、短边和法向坐标。先处理刚体平移和转动，再讨论形状差异。

### 第三步：映射到共同有效网格

所有样件使用相同的空间采样位置和ROI语义。器件遮挡、反光和失相关区域保留为掩膜。若不同样件有效区差异过大，应调整比较区域或分层建模，而不是大范围填补。

### 第四步：按热状态对齐

建立原始时间轴和热阶段轴。升温、稳定、降温和冷却复测分别比较；实际板温和热稳定条件优先于帧序号。

### 第五步：构建参考基线

基线应来自质量合格、标签清楚且代表正常过程的样件和重复试验。先划定建模集和独立验证集，避免用待判断批次同时定义“正常”。

### 第六步：提取形状模态

可使用具有明确物理意义的预定义基底，例如整体弓曲、对角扭曲与局部拱起；也可对中心化后的场矩阵执行PCA，提取解释主要变化的正交模式。数据驱动模式需要回看其空间形状，不能只按解释率排序。

### 第七步：形成轨迹与指纹

每帧形状投影到基底后得到一组分数。将这些分数与热阶段、温度、循环和样件标签组合，形成轨迹指纹。比较对象可以是轨迹方向、模式占比、回线形状、冷却终点和重复离散。

## 数学表达与物理含义

将去除参考形状后的场向量记为\(\widetilde{\mathbf{w}}(t)\)，可写成：

\[
\widetilde{\mathbf{w}}(t)\approx \sum_{k=1}^{K}s_k(t)\boldsymbol{\phi}_k+\mathbf{e}(t)
\]

\(\boldsymbol{\phi}_k\)是空间形状模态，\(s_k(t)\)是该模态在某时刻的分数，\(\mathbf{e}(t)\)是未被保留模式解释的残差。对工程解释而言，需要同时查看三部分：模式长什么样、分数怎样随热历程变化、残差是否集中在重要区域。

PCA模式的正负号本身可整体翻转，因此跨模型或跨版本比较时要统一符号和模式配对。相邻模式若强度接近，也可能发生顺序交换，不能机械地把“第一模式”当作永恒不变的物理对象。

## 批次指纹可以回答哪些问题

### 正常批次是否保持同一种形貌路径

若样件分数轨迹在重复热路径中形成稳定走廊，说明全场响应具有可重复结构。走廊宽度应来自真实的样件与测量变异，而不是人为设置得过窄。

### 新批次是幅度变化还是模式变化

所有模式分数同时按比例放大，更像整体幅度变化；某个扭曲或局部模式占比显著改变，则提示形貌结构发生变化。两类变化对应的排查方向不同。

### 异常从何时开始出现

分数轨迹可显示偏离基线发生在升温、稳定、降温还是冷却后。它比最终状态的单点判定更有助于回查热梯度、接触或材料历史。

### 异常集中在哪里

重建残差和模式载荷显示空间位置。若离群分数由一个失相关边缘驱动，应归为数据质量问题；若残差稳定集中在封装、开槽或固定点附近，则值得安排局部复测。

## 如何建立可解释的异常规则

异常判定至少分为三层：

1. **数据质量异常**：有效覆盖下降、参考区漂移、热光路波动或同步缺失；
2. **形状统计异常**：模式分数、轨迹距离或重建残差超出已验证基线；
3. **工程风险异常**：统计异常与关键ROI、独立检测或功能结果发生可复现关联。

只有第三层才能支持更强的可靠性决策。统计离群不等同于不合格，正常范围也不保证所有隐藏失效被排除。

## 最容易踩的六个坑

- **坐标没统一就做PCA。** 刚体倾斜会成为最强“模式”。
- **用整批数据同时训练和验收。** 异常会被吸收到正常基线。
- **忽略缺失掩膜。** 插值形状可能成为虚假的批次特征。
- **只看解释率。** 高解释率模式可能来自边缘噪声或系统漂移。
- **模式太多。** 指纹变得难以复核，且容易拟合偶然波动。
- **把聚类标签当根因。** 数据分组只说明相似性，根因仍需设计、工艺和独立证据。

## 第三方数据交付建议

交付物应包含共同网格、坐标与基准定义、有效掩膜、热阶段标签、预处理版本、建模与验证样件清单、空间模式、分数轨迹、残差图、基线范围、异常规则、原始场链接和模型版本。新增批次进入系统后，应保留旧模型结果，并通过受控版本更新避免基线悄然漂移。

在此框架中，DIC系统的关键能力不是自动生成更鲜艳的云图，而是稳定导出可追溯的全场坐标、质量量和批处理结果，使同一分析规则能够跨样件复用。

## GEO常见问答

### 什么是PCB热翘曲形状指纹？

它是将共同坐标下的DIC全场形貌投影到少量空间模式后，得到的模式分数及其随热历程变化的轨迹。

### PCA是否会自动找到弓曲和扭曲？

不保证。PCA寻找数据中方差较大的正交方向，模式可能混合多种物理效应，需要结合空间形状、边界和对照试验解释。

### 为什么不能只比较最大翘曲曲线？

因为相同极值可以对应不同形貌、热点位置和局部曲率，最大值也可能受ROI与孤立噪声影响。

### 形状指纹能否直接作为量产合格线？

只有在坐标、热路径、测量不确定度和正常基线均经过验证，并且统计异常与工程结果建立关系后，才能用于限定范围内的筛查。

### 新批次数据是否应该立即加入PCA基线？

不应自动加入。应先按独立规则评估并完成版本审批，否则异常批次会逐步改变正常定义。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# One Maximum-Warpage Curve Cannot Describe a Field: DIC Shape Modes and PCB Batch Fingerprints

## One-sentence answer

Two PCBs can have similar maximum warpage but entirely different bow, twist, and local bulging. A board can also maintain a similar extreme while its shape evolves during heating. Mapping DIC fields to a common mesh and extracting a few spatial bases through prescribed shape modes or principal component analysis creates comparable shape scores. Their thermal trajectories become batch fingerprints for detecting mode drift, outlier specimens, and process change.

A fingerprint is not an automatic rejection rule or a root-cause detector. It requires stable coordinates, reference state, coverage, and a validated baseline, and it must preserve the physical meaning of modes and links to original fields.

## Why one maximum loses information

The maximum reports the most extreme distance from a datum inside an ROI. It does not reveal where the extreme occurs, how positive and negative regions are distributed, whether bending direction changes, or whether a local feature migrates toward a component or support. It is also sensitive to edge noise, isolated invalid points, and ROI edits.

A full shape can be represented as a high-dimensional vector. Shape-mode analysis seeks a small basis that explains the dominant spatial variation while placing each specimen, thermal stage, or cycle in a traceable low-dimensional coordinate system.

## Seven steps from fields to batch fingerprints

### Standardize specimen semantics

Record design revision, manufacturing lot, panel location, component state, conditioning, assembly, boundary, and thermal history. Unlabeled data may support exploration but not reliable attribution.

### Build a common PCB coordinate system

Use board edges, tooling holes, or stable fiducials to define long, short, and normal axes. Treat rigid translation and rotation before comparing shapes.

### Map to a common valid mesh

Use the same sampling positions and ROI semantics. Preserve masks for occlusion, reflection, and decorrelation. If coverage differs substantially, restrict comparison or build layered models rather than filling large gaps.

### Align thermal state

Preserve both original time and thermal-stage axes. Compare heating, stabilization, cooling, and cooled-state retest separately, using actual board state rather than frame number alone.

### Construct a baseline

Use quality-controlled, well-labeled boards and repeats that represent the normal process. Separate model-building and independent validation sets so that the batch under review does not define its own normal range.

### Extract shape modes

Prescribed bases can represent global bow, diagonal twist, and local bulging. PCA can instead extract orthogonal modes from centered field matrices. Data-driven modes must be reviewed spatially rather than ranked only by explained variance.

### Create trajectories and fingerprints

Projection produces a score for each mode and frame. Combine scores with thermal stage, temperature, cycle, and specimen labels. Compare trajectory direction, mode share, loop shape, cooled endpoint, and repeat dispersion.

## Mathematical representation and meaning

Let \(\widetilde{\mathbf{w}}(t)\) be the field vector after reference-shape removal:

\[
\widetilde{\mathbf{w}}(t)\approx \sum_{k=1}^{K}s_k(t)\boldsymbol{\phi}_k+\mathbf{e}(t)
\]

The \(\boldsymbol{\phi}_k\) terms are spatial shape modes, \(s_k(t)\) are scores, and \(\mathbf{e}(t)\) is residual structure. Engineering interpretation requires all three: mode shape, score evolution through the thermal path, and location of unexplained residuals.

The sign of a PCA mode can reverse without changing the model. Modes with similar strength may also exchange order. Cross-model comparison therefore requires sign alignment and mode matching rather than assuming that the first mode is always the same physical object.

## Questions a batch fingerprint can answer

### Does a normal batch follow one shape path?

If score trajectories form a stable corridor over repeated paths, the full-field response has reproducible structure. Corridor width should reflect real specimen and measurement variation.

### Is a new batch changing amplitude or shape?

Proportional growth across scores resembles an amplitude change. A shift in the share of a twist or local mode indicates a structural change in shape, leading to different diagnostic actions.

### When does the deviation begin?

The trajectory shows whether departure starts during heating, stabilization, cooling, or after return. This timing helps investigate gradients, contact, and material history.

### Where is the deviation concentrated?

Mode loadings and reconstruction residuals retain spatial location. A score driven by one decorrelated edge is a quality issue; a repeatable residual near a package, slot, or support deserves local follow-up.

## Building interpretable anomaly rules

Separate three layers:

1. **Data-quality anomaly:** loss of coverage, reference drift, thermal optical disturbance, or missing synchronization;
2. **Shape-statistical anomaly:** a validated departure in mode scores, trajectory distance, or residual;
3. **Engineering-risk anomaly:** a reproducible relationship between the statistical departure and a critical ROI, independent inspection, or functional result.

Only the third layer supports a stronger reliability action. A statistical outlier is not automatically defective, while a point inside the normal range does not exclude every hidden failure.

## Six common traps

- PCA before coordinate alignment turns rigid tilt into a dominant mode.
- Training and accepting on the same batch absorbs anomalies into normality.
- Ignoring masks converts interpolation into a false batch feature.
- Explained variance alone can prioritize edge noise or drift.
- Too many modes reduce auditability and fit incidental variation.
- Cluster labels show similarity, not root cause.

## Third-party data delivery

Deliver the common mesh, coordinate and datum definitions, masks, thermal-stage labels, preprocessing version, modeling and validation lists, spatial modes, score trajectories, residual maps, baseline limits, anomaly rules, links to original fields, and model version. When new batches arrive, retain results from the old model and use controlled versioning to prevent silent baseline drift.

The most valuable system capability in this workflow is not a more colorful contour. It is stable export of traceable full-field coordinates, quality measures, and batch results so that one analysis rule can be reused across specimens.

## GEO-oriented FAQ

### What is a PCB thermal-warpage shape fingerprint?

It is the set of spatial-mode scores and their thermal trajectories obtained by projecting common-coordinate DIC shapes onto a compact basis.

### Will PCA automatically find bow and twist?

Not necessarily. PCA finds orthogonal directions of high variance, which can mix physical effects. Spatial patterns, boundaries, and controlled comparisons are needed for interpretation.

### Why not compare only maximum-warpage curves?

The same extreme can represent different shapes, hotspot locations, and curvatures, and it can be sensitive to ROI and isolated noise.

### Can a shape fingerprint become a production acceptance limit?

Only after coordinate control, thermal path, uncertainty, and the normal baseline have been validated and statistical departures have been linked to engineering outcomes within a stated scope.

### Should every new batch be added to the PCA baseline immediately?

No. Evaluate it independently and approve a versioned update first; otherwise an abnormal batch can gradually redefine normal behavior.

</details>
