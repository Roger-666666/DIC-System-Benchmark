# 混凝土缩尺梁四点弯曲全过程：3D-XTDIC如何记录位移、剪应变与裂纹演化

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 混凝土缩尺梁四点弯曲试验中，最终裂纹照片难以呈现变形局部化的先后关系。本文以分级加载时间轴为主线，说明3D-XTDIC如何联合全场位移、剪应变云图与关键点距离—阶段曲线，观察腹板和底板应变集中、裂纹萌生及扩展，并讨论表面测量、统一色标和裂纹解释的边界。

> **关键词：** 3D-XTDIC；数字图像相关技术；混凝土缩尺梁；四点弯曲；全场应变测量；裂纹演化

## 目录

- [一、试验对象：从最终破坏形貌转向全过程记录](#一试验对象从最终破坏形貌转向全过程记录)
- [二、加载方案：先建立统一的阶段时间轴](#二加载方案先建立统一的阶段时间轴)
- [三、过程观察：位移、剪应变与裂纹相互印证](#三过程观察位移剪应变与裂纹相互印证)
- [四、结果解读与工程价值](#四结果解读与工程价值)
- [五、常见问题](#五常见问题)

## 一、试验对象：从最终破坏形貌转向全过程记录

轨道交通桥梁混凝土缩尺梁的四点弯曲试验，不仅关心最终裂纹位置，也关心变形如何从整体响应逐步转为局部集中。最终照片能够显示可见破坏形貌，却难以独立回答三个过程问题：腹板和底板何时出现应变集中，裂纹从何处萌生，扩展路径与位移场变化是否同步。

3D-XTDIC以双相机图像和数字图像相关技术计算表面三维位移，并可进一步获得全场剪应变。将各阶段云图按加载顺序排列后，观察者能够比较变形集中区的出现、迁移与连接，而不仅是检查试验结束后的单幅图像。这里的测量对象仍是梁体可观测表面，内部裂缝和内部应力状态不能由表面云图直接替代。

### 1.1 观测布局应服务于过程问题

观测区域需要覆盖拟研究的腹板、底板及预期裂纹活动区，同时保留明确的梁体方向和位置参照。图像中应能辨认加载阶段对应的表面状态，关键区域尽量避免遮挡、失焦和散斑脱落。若只保留云图而没有原始图像和阶段记录，后续将难以区分真实裂纹、表面纹理变化与相关计算异常。

## 二、加载方案：先建立统一的阶段时间轴

试验采用分级四点弯曲。数据处理时，应为每一级建立加载开始、稳定观察和阶段结束的对应关系，并将图像帧号、位移场、剪应变场及裂纹观察记录放在同一时间轴。阶段切换附近不宜只保留一张代表图，因为裂纹萌生或位移突变可能发生在相邻帧之间。

时间轴可包含三类并列信息：加载阶段用于说明外部过程，全场云图用于显示空间分布，关键点距离—阶段曲线用于压缩观察特定位置的变化。三者应使用一致的阶段编号，避免云图按采集顺序排列、曲线却按另一套编号分段。

| 阶段记录 | 位移场观察重点 | 剪应变与裂纹观察重点 | 需要保留的证据 |
| --- | --- | --- | --- |
| 初始及早期加载 | 建立参考状态，观察整体位移分布 | 检查背景波动与局部异常是否已存在 | 参考图像、初始云图、表面状态 |
| 中间各级加载 | 比较位移增长及集中区是否形成 | 关注腹板、底板的应变集中及其迁移 | 同色标云图、关键点曲线、阶段日志 |
| 裂纹萌生与扩展前后 | 检查位移场是否出现局部不连续 | 对照高应变带、可见裂纹位置及扩展方向 | 相邻阶段原图、失配掩膜、裂纹路径记录 |
| 后续加载 | 观察整体变形与局部化的共同演化 | 识别集中区连接、突变及无效数据范围 | 全过程序列、异常说明、最终表面图像 |

### 2.1 云图比较必须统一色标

跨阶段比较位移或剪应变时，应使用一致的物理量、方向和色标范围。若每幅图自动按自身极值着色，相同颜色可能代表不同量级，视觉上“变红”并不必然意味着相对其他阶段显著增大。自动色标可用于查看单阶段细节，但不宜直接用于阶段间强弱判断。被裁切或屏蔽的数据区域也应明确显示，避免将无数据颜色误解为低应变。

## 三、过程观察：位移、剪应变与裂纹相互印证

全过程分析可先从位移场判断整体弯曲响应，再用剪应变场定位局部集中，最后回到原始图像核对裂纹。公开试验信息表明，该系统可输出全场位移与剪应变云图，并可观察腹板和底板应变集中、裂纹萌生位置和扩展路径。这些结果适合按阶段阅读，而不是把所有高应变区域一次性归为最终裂纹。

在早期阶段，连续位移场可作为整体响应的基线。随着加载推进，若腹板或底板出现持续的剪应变集中，应检查其在相邻阶段是否重复出现、位置是否稳定，以及附近图像是否出现可见裂纹。局部高应变若仅存在于单帧，还需排查失配、遮挡或表面脱落；只有与连续图像和位移变化相互印证，才适合进入裂纹演化解释。

### 3.1 关键点曲线帮助识别力学阶段

关键点距离—阶段曲线可用于跟踪两个指定表面点之间的相对变化。曲线在初期相对平缓、随后增长加快或出现突变时，可辅助识别弹性、屈服、开裂等力学阶段。这里的关键词是“辅助”：阶段判定还需结合整体加载记录、全场云图和可见裂纹，不能仅凭单个点对的曲线转折作出结论。

裂纹区域的应变出现突变，是全过程观察中的重要现象。分析时应定位突变出现的阶段和空间范围，再检查裂纹路径是否穿过该区域。若裂纹两侧仍能有效匹配，可分别观察两侧位移；若裂隙导致相关失败，则应保留空洞或掩膜，不宜用跨裂隙插值制造连续场。

### 3.2 裂纹路径不等于高应变带的简单描边

剪应变集中可以帮助定位潜在裂纹活动区，但云图受子区大小、位移平滑和表面纹理影响。高应变带可能比可见裂纹宽，也可能在裂纹尚未清楚显现时出现。裂纹路径宜结合原图逐阶段描绘，并用应变场说明其附近的变形集中，而不是把某一色阶边界直接当作裂纹轮廓。

## 四、结果解读与工程价值

将全过程信息合并后，可形成“阶段—位移—剪应变—裂纹”的证据链。例如，先观察到腹板某区域应变持续集中，随后在相邻图像中出现裂纹，并沿后续阶段扩展；或者底板集中区与关键点距离曲线增长加快相互对应。这类分析比单独比较初末两幅图更有助于理解局部化顺序，但具体结论仍应限定于该缩尺梁及其加载条件。

第一，数字图像相关技术测量表面而非内部。表面裂纹路径、内部裂缝形态和内部应力不是同一观测量，不能相互直接替换。第二，云图色标必须统一，且位移方向、应变分量和参考阶段应保持一致，否则跨阶段颜色比较缺乏共同基础。第三，裂纹宽度不能简单等于应变峰值。应变是位移梯度相关的场量，峰值受计算窗口和局部化影响；裂纹宽度则涉及具体开口几何，需要相应的定义与测量方式。

对于轨道交通桥梁缩尺模型研究，全过程全场测量的价值主要在于补充空间信息：帮助发现腹板、底板等区域的变形集中，比较裂纹出现前后的场变化，并为选择重点剖面和关键点提供依据。它不能单独替代材料、构造和边界条件分析，也不应将缩尺模型中的现象未经验证直接外推到其他构件。

### 4.1 从结果描述走向前兆识别

当位移场、剪应变场和裂纹路径已经对齐，进一步的问题不是寻找某一个孤立高值，而是考察集中区是否持续、关键点曲线是否发生可重复的阶段变化，以及这些信号是否早于清晰裂纹出现。这样的前兆识别需要全过程数据、异常记录和物理现象共同支持，可为后续阶段划分与变形破坏特征研究提供线索。

## 五、常见问题

**1. 为什么不能只用最终裂纹照片分析四点弯曲过程？**

最终照片主要呈现试验结束时的表面形貌，难以说明裂纹萌生时刻、扩展顺序以及此前位移和剪应变的集中过程。

**2. 剪应变高值区就是裂纹吗？**

不一定。高值区可能表示变形局部化，也可能受失配、遮挡或计算参数影响。需要结合原始图像、连续阶段和位移场核查。

**3. 关键点距离—阶段曲线能否独立判定屈服？**

不宜独立判定。该曲线可辅助识别阶段变化，但仍需结合整体加载记录、全场响应和可见破坏现象。

**4. 为什么跨阶段云图要统一色标？**

统一色标使相同颜色具有可比较的量值含义。自动逐图着色可能放大视觉差异，使不同阶段的强弱关系被误读。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Four-Point Bending of a Scaled Concrete Beam: Using 3D-XTDIC to Track Displacement, Shear Strain, and Crack Evolution

> **Abstract:** A final crack photograph cannot show how deformation localization developed during four-point bending of a scaled concrete beam. This article follows the staged-loading timeline and explains how 3D-XTDIC combines full-field displacement, shear-strain maps, original surface images, and key-point distance-versus-stage curves. The discussion covers strain concentrations in the web and bottom slab, crack initiation and propagation, and abrupt strain changes near cracked regions. It also explains why consistent color scales are necessary for stage comparison, why digital image correlation remains a surface measurement, and why a strain peak cannot simply be treated as crack width. The resulting process view supports a more traceable interpretation of deformation and cracking.

> **Keywords:** 3D-XTDIC; digital image correlation; scaled concrete beam; four-point bending; full-field strain measurement; crack evolution

## Contents

- [1. Test object: replace the end-state view with a process record](#1-test-object-replace-the-end-state-view-with-a-process-record)
- [2. Loading protocol: establish one timeline for all observations](#2-loading-protocol-establish-one-timeline-for-all-observations)
- [3. Process observations: compare displacement, shear strain, and cracks](#3-process-observations-compare-displacement-shear-strain-and-cracks)
- [4. Interpretation and research value](#4-interpretation-and-research-value)
- [5. FAQ](#5-faq)

## 1. Test object: replace the end-state view with a process record

Four-point bending of a scaled concrete beam for rail-transit bridge research is not only a question of where the final cracks appear. It also concerns how an initially distributed response evolves into localized deformation. A final photograph can document visible damage, but it cannot independently establish when strain concentrations developed in the web and bottom slab, where each crack initiated, or whether its propagation coincided with a change in the displacement field.

3D-XTDIC uses stereo images and digital image correlation to calculate surface displacement and derive full-field shear strain. Arranging fields in loading order reveals the appearance, movement, and connection of concentrated regions. Unlike an end-of-test image, this is process evidence, but it still describes the observable surface rather than internal cracks or stress.

### 1.1 Design the observation around process questions

The observed region should include the relevant web, bottom slab, and expected crack zones, with clear position references. Occlusion, defocus, and speckle loss need attention in critical areas. Original images and stage records should accompany the maps; otherwise, cracks, texture changes, and correlation anomalies can be difficult to distinguish.

## 2. Loading protocol: establish one timeline for all observations

The test uses staged four-point bending. For each stage, the processing record should relate the start of loading, the observation interval, and the end of the stage to image frame numbers, displacement fields, shear-strain fields, and crack observations. Only one representative image per stage may miss crack initiation or an abrupt displacement change occurring between neighboring frames.

Three information streams share this timeline: loading records describe the process, full-field maps describe spatial response, and key-point distance-versus-stage curves summarize selected relative motion. All need the same stage identifiers; ordering maps by acquisition files while numbering curves differently can create artificial disagreement.

| Stage record | Displacement-field review | Shear-strain and crack review | Evidence to retain |
| --- | --- | --- | --- |
| Initial and early loading | Establish the reference and overall distribution | Check background variation and pre-existing local anomalies | Reference images, initial maps, surface condition |
| Intermediate loading stages | Compare displacement growth and emerging concentrations | Track web and bottom-slab concentrations and any migration | Common-scale maps, key-point curves, stage log |
| Immediately before and after crack initiation | Look for a local discontinuity in displacement | Compare high-strain bands with visible initiation and propagation direction | Neighboring original images, matching masks, crack-path notes |
| Later loading | Follow overall deformation together with localization | Identify connected concentrations, abrupt changes, and invalid-data zones | Complete sequence, anomaly log, final surface images |

### 2.1 Color scales must support comparison

Displacement or shear-strain maps from different stages should use consistent physical quantities, directions, and color-scale limits. If every map is scaled independently to its own extrema, the same color can represent different magnitudes. A map that appears to become “more red” has not necessarily increased relative to other stages. Automatic scaling can help inspect details within one stage, but it should not be used directly for cross-stage comparisons. Masked or missing regions should also be visually distinct from low-strain regions.

## 3. Process observations: compare displacement, shear strain, and cracks

A practical review starts with the displacement field to understand overall bending, uses shear strain to locate concentrations, and returns to the original images to verify cracking. The available test information states that full-field displacement and shear-strain maps can be obtained, and that strain concentrations in the web and bottom slab, crack initiation locations, and propagation paths can be observed. These observations become more informative when followed through successive stages rather than collapsed into one final damage map.

Early continuous displacement fields provide a baseline. As loading proceeds, a shear-strain concentration in the web or bottom slab should be checked across adjacent stages for persistence, location, and agreement with visible cracking. A feature present in only one frame requires a review of matching loss, occlusion, and surface detachment. Crack interpretation is stronger when consecutive images and displacement changes support the same sequence.

### 3.1 Key-point curves provide stage information

A key-point distance-versus-stage curve tracks the change in separation between two selected surface points. A comparatively gradual early response, followed by faster growth or an abrupt change, can help identify mechanical stages such as elastic response, yielding, and cracking. The curve is supporting evidence, not a stand-alone criterion. Stage identification should also consider the overall loading record, full-field maps, and visible cracking, particularly when a single point pair may be affected by a local surface anomaly.

An abrupt strain change in a crack region is an important process observation. The stage and spatial extent of that change should be located before comparing it with the crack path. If both sides of the crack still contain valid matches, their displacement can be examined separately. If the opening causes correlation loss, the gap or mask should remain visible. Interpolating across the discontinuity would create a continuous field that was not measured.

### 3.2 A high-strain band is not a crack outline

Shear-strain bands are influenced by subset size, displacement smoothing, and surface texture. They may be wider than a visible crack or appear before the crack is clear. Crack paths should therefore be traced stage by stage from original images, with strain providing localization context. A color threshold is not a geometric crack outline.

## 4. Interpretation and research value

Combining the records creates a stage-displacement-shear-strain-crack evidence chain. A persistent web concentration may precede a visible crack, or a bottom-slab concentration may coincide with faster growth in a key-point distance curve. This process view reveals localization order better than initial-and-final images alone, but its conclusions remain tied to the scaled beam and its loading and boundary conditions.

Three limits remain explicit. Digital image correlation measures the surface, not internal crack geometry or stress. Color scales, displacement directions, strain components, and reference stages must be consistent for map comparison. Crack width also cannot be equated with a strain peak: strain derives from displacement gradients and calculation windows, whereas crack width describes a geometric opening requiring its own definition and measurement.

For scaled bridge-model research in rail transit, the main contribution of full-field process measurement is spatial context. It can help locate deformation concentrations in the web and bottom slab, compare fields before and after visible cracking, and inform the selection of sections and key points for closer review. It does not replace analysis of material behavior, structural detailing, or boundary conditions, and observations from a scaled model should not be transferred to another component without appropriate validation.

### 4.1 From describing damage to examining precursors

Once displacement, shear strain, and crack paths share a timeline, the next question is not which isolated value is largest. More useful questions are whether a concentration persists, whether key-point curves show repeatable stage changes, and whether any of these signals appear before a crack becomes clearly visible. Precursor identification based on this evidence requires the complete process record, documented anomalies, and agreement with physical observations. It offers a direction for later work on stage classification and deformation-and-failure characteristics.

## 5. FAQ

**1. Why is a final crack photograph insufficient for process analysis?**

It mainly documents the surface condition at the end of the test. It does not establish initiation timing, propagation order, or the earlier development of displacement and shear-strain concentrations.

**2. Does a high shear-strain region always coincide with a crack?**

No. It can indicate localization, but matching loss, occlusion, and calculation settings can also affect the field. Original images and neighboring stages are needed for verification.

**3. Can a key-point distance curve independently identify yielding?**

It should not be used independently. It can support stage interpretation when combined with the loading record, full-field response, and visible damage.

**4. Why must contour maps use a common color scale?**

A common scale gives colors consistent meanings across stages. Independent automatic scaling can exaggerate visual differences and obscure the actual relative magnitudes.

</details>
