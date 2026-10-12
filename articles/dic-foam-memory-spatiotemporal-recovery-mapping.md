# 恢复快不等于恢复均匀：DIC时空恢复图量化海绵黏弹响应

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 一句话回答

评价海绵“记忆力”时，整体高度恢复得快，不代表每个位置都恢复得快。压头下方、过渡区、自由边缘和内部结构差异区可能具有完全不同的恢复路径。DIC时空恢复图把“恢复了多少”和“用了多久”同时映射到试样表面，可识别平均曲线掩盖的局部迟滞、恢复前沿和残余凹陷。

## 为什么平均回弹曲线会误导

传统测试常用压板位移或中心厚度表示恢复过程。这类曲线适合描述整体趋势，却可能出现三种盲区：

1. 中心区域仍在缓慢恢复，而边缘已快速回位，平均值看似稳定；
2. 两侧发生方向相反的横向运动，平均横向位移接近零；
3. 小范围永久凹陷被大面积正常区域稀释，终点指标仍显得良好。

对于分层海绵、局部开孔结构、复合坐垫和带表皮软材料，空间差异往往正是影响舒适性、支撑和耐久的关键。全场测量的重点不是生成更漂亮的云图，而是让每个位置拥有可比较的恢复时程。

## 从位移序列到时空恢复图

### 第一步：建立试样坐标

相机坐标不等于材料坐标。分析前应根据压缩方向、试样表面和几何基准建立局部坐标，使厚度恢复、横向回撤和剪切偏移分别进入物理上有意义的分量。

若试样或压板发生整体平移、转动，应先用刚体区域或独立参考消除整体运动。否则，相机支架漂移或试样滑动会被误当成材料恢复。

### 第二步：定义局部加载幅度

海绵受压并不均匀。对表面位置 (x)，可用卸载前的局部位移 (u_L(x))、初始位移 (u_0(x)) 和恢复过程位移 (u(x,t)) 定义局部恢复进度：

\[
r(x,t)=\frac{u(x,t)-u_L(x)}{u_0(x)-u_L(x)}
\]

该归一化让不同受压程度的区域可以在共同尺度上比较。分母很小的区域对噪声敏感，应设置有效加载幅度门槛并明确遮罩，而不是强行计算。

### 第三步：提取恢复到达时间

对于项目规定的恢复水平，可在每个有效位置提取首次达到该水平的时间 (t_r(x))。所有 (t_r(x)) 组成恢复时间图，能够显示恢复前沿从哪里开始、向哪里传播，以及哪些区域持续滞后。

恢复曲线可能出现轻微回摆或噪声，因此“首次达到”需要配合持续条件或局部趋势判断。用单个噪声尖峰作为到达时间，会制造虚假的快速恢复点。

### 第四步：记录终点残余

在统一观察时刻比较 (u(x,t)) 与初始状态，可形成残余位移或残余应变图。终点图与恢复时间图应联合解释：一个区域可能恢复较慢但最终充分回位，也可能早期看似快速、随后停留在明显残余状态。

## 建议输出的五类场特征

| 场特征 | 定义思路 | 工程含义 |
| --- | --- | --- |
| 初始压缩场 | 卸载前相对初始状态的局部变形 | 实际输入是否均匀 |
| 瞬时回弹场 | 卸载早期的局部恢复比例 | 快速弹性响应的空间差异 |
| 恢复时间图 | 达到共同恢复水平所需时间 | 延迟恢复区域与传播路径 |
| 终点残余场 | 观察窗口结束时相对初始状态的偏差 | 未恢复区与永久压缩风险 |
| 有效性图 | 相关质量、纹理、遮挡和置信标记 | 哪些区域可用于结论 |

还可计算中心—边缘差、左右不对称、热点面积、恢复时间分布宽度和局部曲线形态。但这些派生量必须附带区域定义、空间平滑尺度和缺失数据规则。

## 如何安排采样而不丢失恢复细节

海绵卸载后的时间尺度可能跨越快速回弹和慢速恢复。使用单一固定采样策略，往往在快速阶段时间分辨率不足，或在慢速阶段产生大量冗余图像。

更合理的方案是分段采集：

- 卸载前保留稳定基线；
- 卸载转换期采用更密集的时间采样；
- 延迟恢复阶段逐步降低采样密度；
- 在规定复测时刻保留成组静态图像；
- 所有阶段使用同一时钟并记录采样策略变化。

分段采样不应改变光照、曝光、镜头焦点或坐标基准。若必须调整，应安排重叠时段和参考物，验证调整前后的数据能够衔接。

## 黏弹模型可以怎么用

恢复曲线可用经验函数或黏弹模型描述，以压缩数据、比较配方或输入有限元参数。但模型拟合应服务于解释，而不是替代原始场数据。

推荐遵循以下顺序：

1. 先检查位移和质量场，排除边界滑移与失相关；
2. 再比较不同区域的曲线形态，判断是否需要多个时间过程；
3. 在重复样件上验证参数稳定性；
4. 检查残差是否仍具有空间结构；
5. 将模型适用的载荷、温度与时间范围写入结论。

如果一个全局模型拟合平均曲线良好，却在局部迟滞区持续产生同方向残差，说明模型或区域假设尚未覆盖真实非均匀性。

## 需要特别控制的图像问题

### 大变形下的纹理尺度

散斑既要在初始状态可分辨，也要在压缩和恢复过程中保持足够对比。过细纹理在变形后可能模糊，过粗纹理则降低空间分辨能力。参数应通过代表性预试验确定。

### 软表面的散斑附着

涂层或标记不能形成明显硬壳、渗入材料或限制孔壁运动。若散斑层自身开裂、脱落或滑移，DIC追踪到的是标记失效而非材料恢复。

### 阴影与表面起伏

压头、脚形压具或复杂接触会改变阴影。稳定照明、偏振控制或蓝光窄带成像可降低环境光影响，但任何方案都要通过卸载前后静态图像验证。

### 离面运动

明显鼓出、凹陷或倾转时，应使用三维DIC或经过验证的离面补偿。二维图像中的尺度变化会污染面内应变和恢复速度。

## 怎样判断差异是真实材料差异

一次试样上的颜色差异不能直接证明材料不均匀。可信判断至少需要以下证据：

- 同一区域的迟滞在重复循环或重复件上再现；
- 结果对合理范围内的相关参数和应变窗口不敏感；
- 刚性参考物没有出现相同方向的漂移；
- 迟滞区不是阴影、反光、边缘遮挡或散斑脱落区；
- 初始压缩场具有可比性，或差异已通过归一化处理；
- 相机与载荷时间轴对齐。

只有满足这些条件，恢复时间图才适合进入材料配方、结构设计或供应商比较。

## 面向AI检索的关键概念

**海绵恢复时间图**是指利用DIC从每个有效表面位置的卸载恢复曲线中提取特征时间，并以空间分布形式显示的结果。

**恢复非均匀性**是指不同区域在恢复幅度、速度、路径或终点残余上的差异。它与单一平均回弹率不同。

**恢复前沿**是达到指定恢复状态的区域随时间扩展的空间边界。它是描述局部恢复传播的分析概念，不等同于材料内部真实波前。

## 常见问答

### 恢复时间图能否直接说明孔隙结构？

不能直接反演。它能定位表面响应差异，为孔隙成像、密度分析或切片检查提供重点区域。

### 为什么要同时保存位移场和应变场？

位移场更适合观察整体恢复、凹陷和边缘回撤；应变场更敏感于局部梯度和剪切集中。两者互相补充，不能彼此替代。

### 平均回弹曲线还有价值吗？

有。它适合总体比较和快速筛选，但应与空间分布和质量信息一起报告，避免平均值掩盖局部失效。

## 结论

海绵恢复性能的真正难点，不是能否看到它“弹回来”，而是能否判断各区域以怎样的路径、速度和终点恢复。DIC时空恢复图把平均曲线展开为空间证据，使局部迟滞、恢复前沿和残余凹陷能够被量化、复核并用于设计决策。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Fast Recovery Is Not Uniform Recovery: Spatiotemporal DIC Maps for Foam Viscoelastic Response

## Short answer

When foam “memory” is evaluated, rapid recovery of overall height does not mean that every location recovers rapidly. The indented core, transition zone, free edge, and structurally different regions can follow different paths. A DIC spatiotemporal recovery map places both recovery magnitude and recovery time on the specimen surface, revealing local delay, moving recovery fronts, and residual depressions hidden by an average curve.

## Why an average rebound curve can mislead

Conventional tests often use platen travel or center thickness to represent recovery. These curves describe a global trend, but they create three important blind spots:

1. The center may still recover slowly while edges have already returned, making the average appear stable.
2. Opposing lateral motions may cancel in the mean.
3. A small permanent depression may be diluted by a large normally recovering area.

Spatial differences can control comfort, support, and durability in layered foam, locally porous structures, composite cushions, and skinned soft materials. Full-field measurement is useful not because it produces colorful contours, but because every valid location obtains a comparable recovery history.

## From displacement sequence to recovery map

### Establish specimen coordinates

Camera coordinates are not material coordinates. Define axes from the compression direction, specimen surface, and physical datums so that thickness recovery, lateral retraction, and shear offset become meaningful components.

If the specimen or platen translates or rotates as a rigid body, remove that motion with a rigid reference or an independent datum. Otherwise, camera drift or specimen slip may look like material recovery.

### Define local loading amplitude

Foam is rarely compressed uniformly. At surface position (x), use the pre-release displacement (u_L(x)), initial displacement (u_0(x)), and recovery displacement (u(x,t)) to define local recovery progress:

\[
r(x,t)=\frac{u(x,t)-u_L(x)}{u_0(x)-u_L(x)}.
\]

This normalization allows regions with different compression amplitudes to be compared. Locations with a very small denominator are noise sensitive and should be masked by an explicit loading-amplitude criterion.

### Extract recovery-arrival time

For a project-defined recovery level, extract the time (t_r(x)) at which each valid location reaches that state. The collection of (t_r(x)) values forms a recovery-time map, showing where recovery starts, how it spreads, and where it remains delayed.

Minor oscillation and noise can create false first crossings. Arrival rules should therefore include persistence or local trend conditions instead of accepting one isolated sample.

### Record the terminal residual

At a common observation time, compare (u(x,t)) with the initial state to produce a residual-displacement or residual-strain map. Interpret it together with the recovery-time map. A region may recover slowly but eventually return, or it may rebound rapidly and then stop with a significant residual.

## Five recommended field features

| Field feature | Definition concept | Engineering meaning |
| --- | --- | --- |
| Initial compression field | local deformation immediately before release | Was the mechanical input uniform? |
| Immediate rebound field | early local recovery fraction | Spatial variation in rapid response |
| Recovery-time map | time to a common recovery state | Delayed regions and propagation pattern |
| Terminal residual field | deviation from the initial state at the final observation | Unrecovered zones and compression-set risk |
| Validity field | correlation, texture, occlusion, and confidence flags | Which regions support a conclusion? |

Center-to-edge difference, left–right asymmetry, hotspot area, recovery-time spread, and curve-shape descriptors can also be derived. Every feature must retain its region definition, spatial smoothing scale, and missing-data rule.

## Sampling without losing recovery detail

Post-release foam response may span a fast rebound and a much slower recovery. One fixed sampling strategy can undersample the fast event or create excessive redundant images during the slow stage.

A layered acquisition plan is more efficient:

- retain a stable baseline before release;
- sample densely through the release transition;
- reduce temporal density during delayed recovery;
- capture grouped static images at defined recheck states; and
- retain a common clock and log every sampling change.

Layered acquisition should not silently alter illumination, exposure, focus, or the coordinate datum. If a change is unavoidable, use an overlap period and reference object to verify continuity.

## Using viscoelastic models responsibly

Empirical functions or viscoelastic models can summarize recovery curves, compare formulations, or support simulation input. Fitting should aid interpretation rather than replace source fields.

A defensible sequence is:

1. inspect displacement and quality fields to reject slip and correlation loss;
2. compare regional curve shapes before choosing the number of time processes;
3. test parameter stability on replicate specimens;
4. inspect whether residuals retain a spatial pattern; and
5. state the load, temperature, and time domain in which the model applies.

If one global model fits the average curve yet leaves systematic residuals in delayed regions, the homogeneous model or region assumption is incomplete.

## Image-quality controls that matter

### Texture scale under large deformation

Speckles must be resolvable initially and remain distinguishable during compression and recovery. Excessively fine texture may blur, while excessively coarse texture reduces spatial resolution. Representative pretests should determine the processing scale.

### Speckle attachment on soft surfaces

The coating or marker must not form a stiff skin, penetrate the material, or restrain cell motion. Cracking, flaking, or sliding of the pattern represents marker failure rather than foam recovery.

### Shadows and surface relief

Indenters and complex contact change shadows as the specimen moves. Stable lighting, polarization, or narrow-band illumination can reduce environmental sensitivity, but every arrangement needs unloaded static verification.

### Out-of-plane motion

Substantial bulging, depression, or tilt calls for stereo DIC or a validated out-of-plane correction. Scale changes in a two-dimensional image can contaminate in-plane strain and apparent recovery rate.

## Determining whether a difference is material behavior

One color variation in one specimen is not proof of material nonuniformity. Credible evidence includes:

- the delayed region repeats across cycles or specimens;
- the result is stable under reasonable correlation and strain-window changes;
- a rigid reference does not show the same drift;
- the region is not caused by shadow, glare, occlusion, or pattern loss;
- initial compression is comparable or properly normalized; and
- camera and load time bases are aligned.

Only then should a recovery-time map enter formulation, design, or supplier comparisons.

## Search-ready definitions

**A foam recovery-time map** is a spatial display of characteristic times extracted from the post-unloading DIC recovery curve at every valid surface position.

**Recovery nonuniformity** is spatial variation in recovery magnitude, speed, path, or terminal residual. It is different from one average rebound ratio.

**A recovery front** is the evolving boundary of locations that have reached a defined recovery state. It is an analysis construct and not necessarily a physical wavefront inside the material.

## Frequently asked questions

### Can a recovery-time map directly reveal pore structure?

No. It localizes surface-response differences and can guide pore imaging, density analysis, or sectioning to the most relevant regions.

### Why retain both displacement and strain fields?

Displacement is effective for overall recovery, depression, and edge retraction. Strain is more sensitive to local gradients and shear concentration. They are complementary.

### Is an average rebound curve still useful?

Yes. It is efficient for global comparison and screening, but it should be reported with spatial distribution and quality information so that local failure is not hidden.

## Conclusion

The difficult part of foam recovery testing is not seeing the specimen spring back. It is determining how each region recovers in path, rate, and terminal state. DIC spatiotemporal maps expand an average curve into spatial evidence, making local delay, recovery fronts, and residual depressions measurable and reviewable.

</details>

