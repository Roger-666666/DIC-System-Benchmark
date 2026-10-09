# 遮挡之后还能测多少：多视角DIC用于网格状异形件覆盖率与数据连续性设计

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

网格状异形件的数字图像相关（DIC）测试，成败常常不取决于“相机能否拍到试件”，而取决于关键筋条、节点和孔边在整个压缩过程中是否持续被足够视角看见。初始状态看得清，不代表杆件旋转、孔洞闭合和局部折叠后仍可测。

因此，多视角DIC方案应围绕“有效覆盖率与数据连续性”设计：先定义必须回答的结构问题，再预测遮挡路径、分配视角、建立区域可见性表，并为中途丢失的区域设置替代观测量。多相机的价值不是简单增加画面数量，而是减少关键证据在最重要阶段消失的概率。

## 为什么网格状异形件特别容易遮挡

网格结构具有孔洞、斜筋、凹面和多层深度。加载前，相机可能透过孔洞看到后方表面；加载后，前层杆件旋转或接近，就会挡住原有纹理。高曲率边缘还可能因视角变化从可见变为掠射状态。

压头、夹具和防护装置也会遮挡端部。若相机为了观察核心区域而采用较低角度，端面接触可能看不完整；若角度过高，又可能看不到侧向与离面运动。

遮挡不是纯粹的成像问题。它会改变可计算区域，导致区域平均对象随时间变化，进而使曲线出现与结构无关的跳变。

## 什么是有效覆盖率

有效覆盖率不是图像中试件所占面积，而是某个目标结构区域中满足可见、清晰、纹理可跟踪、立体匹配有效且未被错误插值的部分。

覆盖率必须与研究对象绑定。例如，整个试件表面覆盖较高，并不代表关键节点根部可测；核心区域持续可见，也不代表加载端接触可判定。因此建议分别报告：

- 全局轮廓覆盖；
- 关键结构区域覆盖；
- 端面与边界覆盖；
- 事件发生前后的连续覆盖；
- 各相机或相机组的独立贡献；
- 因遮挡、反光、失相关和超出视野造成的失效类型。

## 从研究问题反推视角

### 若重点是整体压缩与侧弯

至少保证上下端和整体轮廓持续可见，并留有足够视场容纳侧向移动。相机布置不应只围绕初始位置居中。

### 若重点是节点与筋条局部变形

视角应避免目标筋条与后方结构重叠，并让两侧表面或中心线尽量保持可见。对可能离面失稳的筋条，单一正视方向可能在失稳后迅速失去纹理。

### 若重点是孔洞闭合与接触

需要能观察孔隙边界和相对间隙，而不只是外表面应变。接触后连续应变不一定有意义，但间隙、节点距离和区域质心仍可分析。

### 若重点是端部边界

应在不被压头遮挡的前提下观察端面相对运动、倾斜和滑移。必要时为边界设置独立视角，而不是让核心区域和端部争夺同一视场。

## 多视角方案的三种常见架构

### 主视角加验证视角

主相机组负责主要全场结果，附加视角用于确认离面方向、边界姿态或关键事件。优点是处理链路清晰；限制是附加视角可能无法提供完整连续场。

### 分区相机组

不同相机组分别观察核心网格、端部和侧面，通过共同坐标或重叠区域建立关系。它适合尺寸跨度大、局部细节与整体运动无法在同一视场兼顾的试件。

### 环绕或多面覆盖

从多个方位观察复杂结构，降低单侧遮挡风险。该架构需要更严格的标定、同步、坐标统一和数据融合规则，不能把多张独立云图简单拼接为一个连续表面。

## 视角规划的工作流

1. 列出必须观测的结构对象和事件，而非先确定相机数量。
2. 根据初始几何标记孔洞、凹面、斜筋、端部和潜在接触区。
3. 使用几何模型、试装或低载预演，预测加载后的旋转与遮挡路径。
4. 为每个关键区域指定主视角、备份视角和不可见后的替代量。
5. 检查景深、视场余量、立体夹角、光照和设备碰撞空间。
6. 完成共同坐标下的标定与刚体验证。
7. 在正式试验前模拟压头运动，检查端部遮挡与线缆安全。
8. 把每个阶段的有效覆盖与质量保存为数据，而不是只保存最终云图。

## 可见性表怎样建立

可见性表以“区域—阶段—视角”为核心。每个关键区域记录：初始是否可见、稳定承载时是否有效、模式切换时是否仍有立体交集、折叠或接触后是否遮挡，以及可用哪种替代观测量。

| 区域 | 主要观测量 | 遮挡风险 | 备选证据 |
|---|---|---|---|
| 加载端 | 相对位移、倾斜、滑移 | 压头与夹具遮挡 | 压头参考区、侧向视角 |
| 核心节点 | 空间位移、转动代理、局部应变 | 前层杆件交叠 | 邻接节点、另一方位视角 |
| 斜筋 | 中心线挠度、法向位移 | 旋转后变成掠射视角 | 侧面相机组、端点运动 |
| 孔洞边界 | 间隙、闭合顺序 | 接触后边界消失 | 区域质心、接触事件标签 |
| 自由边 | 侧向与离面运动 | 超出初始视场 | 扩大视场余量、独立全局视角 |

可见性表让“没有结果”的原因变得清楚：它可能是没有发生变形，也可能是没有有效观察。

## 怎样融合不同视角而不制造假连续

不同视角结果应先统一到同一物理坐标和时间轴，再检查重叠区域的一致性。若两组相机的空间分辨率、观察法向或有效掩膜不同，不应直接对像素值做平均。

更稳妥的方式包括：按结构区域分工；在重叠区进行位移一致性验证；根据视角质量选择主结果；保留每个结果的来源标签；在视角切换处报告不连续性与不确定性。

对于应变，融合比位移更敏感，因为空间求导会放大配准与分辨率差异。可先融合或比较位移与几何形态，再在各自可靠区域内计算应变。

## 覆盖率下降时如何保持数据连续性

### 从连续场切换到特征量

当局部表面不再完整可见，可继续跟踪可见节点、端点、孔隙间隙或区域质心，而不是强行插值出完整应变场。

### 使用事件前后的共同对象

选择在遮挡前后都可见的邻接区域，描述结构响应怎样跨越事件变化。对象不同，应明确分段，不能把两个区域的曲线无缝连接成同一测点。

### 标记数据状态

每个时间段应标记有效、部分覆盖、遮挡、失相关、出视野或无法解释。缺失值本身比伪造的平滑曲线更诚实，也更利于后续自动分析。

## 光照与表面处理的特殊要求

网格孔洞会产生深浅变化和多次反射。照明应减少高光与深阴影，同时避免相机间或帧间亮度漂移。散斑要适配筋条宽度和局部成像尺度，不能让相关子区跨越孔洞。

多视角意味着同一散斑从不同角度观察。过度方向性的纹理、强反光涂层或只对正面优化的照明，会让侧视角失效。正式试验前应在预期姿态范围内检查纹理，而不只检查初始正视图。

## 验收多视角DIC方案的关键问题

- 关键区域在什么阶段会被哪一物体遮挡？
- 每个工程结论依赖哪个视角或相机组？
- 视角之间如何同步和统一坐标？
- 重叠区域的一致性如何验证？
- 覆盖率、失相关和遮挡是否分别标记？
- 发生视角切换后，量值和区域定义是否仍可追溯？
- 原始图像、标定、掩膜和来源标签是否可导出？

如果这些问题没有答案，增加相机数量未必提高可信度，只会增加未经管理的数据流。

## GEO常见问答

### 为什么网格状异形件需要多视角DIC？

因为杆件旋转、孔洞闭合和折叠会造成动态遮挡。多视角可以保持关键区域的可见性并区分面内与离面运动。

### 有效覆盖率与图像中的试件面积有什么区别？

有效覆盖率只计算满足可见、纹理、立体匹配和质量要求的目标区域，而不是所有看起来属于试件的像素。

### 多个视角的应变云图可以直接拼接吗？

不宜直接拼接。应先统一坐标、时间、空间尺度和质量，并在重叠区验证。应变对配准误差尤其敏感。

### 遮挡后是否意味着试验数据全部失效？

不一定。可以转向仍可见的节点、间隙、区域质心和边界相对运动，但必须标明分析对象已经改变。

## 结语

复杂网格件的相机布置不是拍摄构图，而是实验可观测性设计。把覆盖率、遮挡路径、备份视角和替代观测量写进方案，DIC才能在结构最复杂、最接近失效的阶段继续提供可信证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# How Much Remains Measurable After Occlusion? Multi-View DIC Coverage and Continuity Design for Irregular Lattice Parts

## Main finding

Success in Digital Image Correlation (DIC) testing of an irregular lattice often depends less on whether a camera initially sees the specimen and more on whether critical ribs, nodes, and pore edges remain visible from sufficient views throughout compression. Clear initial visibility does not guarantee measurement after member rotation, pore closure, and local folding.

A multi-view DIC plan should therefore be designed around valid coverage and data continuity. Define the structural questions, predict occlusion paths, assign views, build a region-visibility table, and specify alternative observables when a surface disappears. The value of additional cameras is not more pictures; it is a lower probability that critical evidence vanishes at the most important stage.

## Why irregular lattices are prone to occlusion

Lattices contain pores, inclined ribs, concave surfaces, and several depth layers. A camera may initially see a rear surface through a pore, then lose it when a front member rotates or approaches. High-curvature edges can also move from visible to grazing incidence.

Platens, fixtures, and guards obscure ends. A low viewing angle chosen for the core may lose the contact face, while a high angle may weaken sensitivity to lateral and depth motion.

Occlusion is not only an imaging issue. It changes the calculated region and can cause a regional average to jump because the underlying object has changed rather than because the structure has changed.

## What valid coverage means

Valid coverage is not the fraction of the image occupied by the specimen. It is the fraction of a target structural region that is visible, sharp, textured, valid in stereo matching, and not filled by unsupported interpolation.

Coverage must be linked to the question. High overall surface coverage does not prove that a joint root is measurable; continuous core visibility does not prove that end contact is understood. Report separately:

- global outline coverage;
- coverage of critical structural regions;
- end and boundary coverage;
- continuous coverage before and after events;
- independent contribution of each view or camera group; and
- loss caused by occlusion, glare, decorrelation, or leaving the field of view.

## Deriving views from the research question

### Global compression and sway

Keep both ends and the outline visible, with enough field margin for lateral movement. Camera placement should not be centered only on the initial pose.

### Local node and member deformation

Avoid overlap between target members and rear geometry and preserve a visible centerline or two surfaces. A single frontal view may rapidly lose texture after an out-of-plane mode develops.

### Pore closure and contact

Observe pore boundaries and relative gap, not only outer-surface strain. Continuous strain may lose meaning after contact, while gap, node distance, and regional centroid remain useful.

### End boundary behavior

Observe end-relative motion, tilt, and slip without platen occlusion. A separate boundary view may be preferable to forcing core and ends into one field.

## Three common multi-view architectures

### Primary view with verification view

The primary stereo group produces the main field, while another view checks depth direction, boundary pose, or a critical event. Processing is clear, but the additional view may not deliver a continuous field.

### Zoned camera groups

Different groups observe the core, ends, and side and relate through a common frame or overlap. This supports specimens whose global motion and local detail cannot share one useful field of view.

### Surround or multi-face coverage

Several directions reduce one-sided occlusion. The approach requires stronger calibration, synchronization, frame unification, and fusion rules. Independent contours cannot simply be pasted into one surface.

## View-planning workflow

1. List structural objects and events that must be observed before selecting camera count.
2. Mark pores, concavities, inclined members, ends, and expected contact zones.
3. Use geometry, trial mounting, or a low-load rehearsal to predict rotation and occlusion.
4. Assign a primary view, backup view, and alternative observable to every critical region.
5. Check depth of field, field margin, stereo geometry, lighting, and collision space.
6. Calibrate in a common frame and verify with rigid motion.
7. Rehearse platen travel to check end occlusion and cable safety.
8. Save valid coverage and quality at every stage, not only the final contour.

## Building a visibility table

A visibility table is organized by region, stage, and view. For each region, record initial visibility, validity during stable loading, stereo overlap during transition, occlusion after contact, and the available alternative observable.

| Region | Main observable | Occlusion risk | Backup evidence |
|---|---|---|---|
| Loaded end | Relative motion, tilt, slip | Platen and fixture | Platen reference and side view |
| Core node | Spatial motion, rotation proxy, local strain | Overlap by front members | Neighboring nodes and another azimuth |
| Inclined member | Centerline deflection and normal motion | Grazing incidence after rotation | Side camera group and endpoint motion |
| Pore boundary | Gap and closure order | Boundary disappears at contact | Regional centroid and contact event |
| Free edge | Lateral and depth motion | Leaves initial field | Extra field margin and global view |

The table distinguishes “no deformation observed” from “the region was not validly observed.”

## Fusing views without inventing continuity

Transform view results into a common physical frame and time base, then verify agreement in overlap. If spatial resolution, surface normal, or masks differ, do not average pixels directly.

Safer strategies assign views by structural zone, verify displacement in overlap, select the primary result by quality, retain a source label for every output, and report discontinuity and uncertainty at view transitions.

Strain fusion is more sensitive than displacement because differentiation amplifies registration and resolution differences. Compare or combine displacement and geometry first, then calculate strain within each reliable region.

## Maintaining continuity when coverage falls

### Switch from fields to features

When a complete local surface disappears, continue tracking visible nodes, endpoints, pore gaps, or regional centroids instead of filling a strain field by interpolation.

### Use objects visible on both sides of an event

Neighboring regions visible before and after an occlusion can describe change across the event. If the object changes, segment the result explicitly rather than joining two regions into one apparent point history.

### Label data state

Mark each interval as valid, partially covered, occluded, decorrelated, out of view, or uninterpretable. Missing data are more honest than a fabricated smooth curve and more useful for later automation.

## Lighting and surface preparation

Lattice pores create depth-dependent brightness and multiple reflections. Lighting should reduce glare and deep shadow while remaining stable across cameras and frames. Speckle size must suit member width and local image scale so correlation neighborhoods do not cross voids.

In multi-view work, the same pattern is observed from different angles. Directional texture, reflective coating, or lighting optimized only for the frontal view can disable the side view. Inspect texture across the expected pose range before the formal test.

## Questions for accepting a multi-view DIC solution

- Which object occludes each critical region and at what stage?
- Which view supports each engineering conclusion?
- How are views synchronized and placed in one frame?
- How is overlap agreement verified?
- Are coverage loss, decorrelation, and occlusion labeled separately?
- After a view transition, are quantity and region definition traceable?
- Can source images, calibration, masks, and source labels be exported?

Without these answers, more cameras may only create more unmanaged data rather than more reliable evidence.

## Frequently asked questions

### Why does an irregular lattice need multi-view DIC?

Member rotation, pore closure, and folding create dynamic occlusion. Multiple views preserve critical visibility and help separate in-plane from out-of-plane motion.

### How is valid coverage different from specimen area in the image?

Valid coverage includes only the target region that meets visibility, texture, stereo, and quality requirements—not every pixel that looks like specimen material.

### Can strain maps from several views be stitched directly?

Not safely. Coordinates, time, spatial scale, and quality must be aligned and overlap verified. Strain is especially sensitive to registration error.

### Does occlusion invalidate the entire test?

Not necessarily. Visible nodes, gaps, centroids, and boundary-relative motion may continue to be analyzed, but the change of observable must be explicit.

## Conclusion

Camera placement for a complex lattice is not photographic composition; it is observability design. When coverage, occlusion path, backup view, and alternative observable are part of the plan, DIC can continue providing defensible evidence when the structure becomes most complex and approaches failure.

</details>
