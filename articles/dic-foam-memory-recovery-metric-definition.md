# 海绵“记忆力”究竟测什么：DIC区分瞬时回弹、延迟恢复与永久压缩

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

日常语言中的海绵“记忆力”，通常把回弹速度、最终恢复程度、残余压缩、形状保持和循环衰减混在一起。它不是单一材料常数，也不能由一张受压照片或一个最大位移值完整描述。

数字图像相关技术（DIC）通过连续记录海绵表面的全场位移与应变，可把卸载后的响应拆成三个阶段：载荷移除时的瞬时回弹、随后一段时间内的延迟恢复，以及观察窗口结束后仍存在的残余变形。若再同步力、位移、时间和环境状态，测试者就能建立可复核的海绵恢复性能证据链，而不是用“回弹不错”这类主观表述代替测量。

## 海绵的“记忆力”为什么不是一个数

海绵属于多孔、可压缩且常具有明显时间依赖的材料。外力作用时，孔壁弯曲、气体迁移、聚合物链段运动、局部接触与摩擦可能同时发生。卸载后，这些机制并不会以同一速度恢复。

因此，以下问题应分别回答：

- 卸载瞬间能恢复多少；
- 延迟恢复需要经历怎样的时间过程；
- 最终是否仍有不可恢复的厚度或形状变化；
- 恢复是否在整个受压区域内均匀发生；
- 多次压缩后，恢复路径是否漂移；
- 表面恢复是否与整体承载能力保持一致。

只报告中心点高度，会遗漏边缘鼓出、剪切带、局部塌陷和恢复不同步。只报告平均值，又可能把彼此相反的局部变化抵消。

## 三类必须区分的恢复指标

### 瞬时回弹

瞬时回弹是载荷移除后最先出现的几何恢复。它对材料弹性部分、卸载速度、接触状态和采集时间分辨率敏感。若卸载时刻没有同步标记，第一帧“卸载后图像”可能已经错过快速恢复阶段。

DIC可在统一时间轴上提取厚度方向位移、横向扩张回撤和局部应变释放，并判断各区域的响应先后。快速变化需要匹配适当的帧率、曝光和照明，而不是事后依靠平滑重建。

### 延迟恢复

延迟恢复反映卸载后仍随时间继续变化的部分。测试中可对多个功能区域建立恢复曲线，也可把每个位置的恢复进度映射为时空场。曲线形状比单一终点更有信息：有些区域早期恢复快、后期趋缓；有些区域则因孔隙重排或边界约束出现滞后。

延迟恢复不应自动解释为某一种微观机制。DIC测量的是可见表面的运动，机制判断仍需结合材料结构、温度、载荷和其他表征。

### 永久压缩与残余形态

在项目规定的恢复观察窗口结束后，若试样相对初始状态仍存在厚度损失、局部凹陷、剪切偏置或形状不对称，可将其记录为残余变形。这里的“永久”必须附带观察时间和环境条件；短时间内未恢复，不代表在更长时间尺度上永远不会恢复。

残余场应同时报告有效测量区域和质量掩膜。表面纹理脱落、边缘离开视场或大变形失相关，都不能被插值成真实残余。

## 如何用DIC建立可比较的指标体系

设初始厚度为 (h_0)，加载状态厚度为 (h_L)，卸载后某时刻厚度为 (h(t))。可根据项目定义恢复比例：

\[
R(t)=\frac{h(t)-h_L}{h_0-h_L}
\]

也可定义相对初始状态的压缩残余：

\[
C(t)=\frac{h_0-h(t)}{h_0}
\]

公式本身并不保证结果可比。使用前必须明确厚度来自哪个区域、采用平均值还是中位数、是否排除边缘、参考状态如何建立，以及 (t) 从卸载指令、载荷过零还是压板脱离开始计时。

对于全场数据，建议形成四层输出：

| 输出层级 | 典型指标 | 回答的问题 |
| --- | --- | --- |
| 全局层 | 平均厚度、整体回弹曲线 | 试样总体恢复到什么程度 |
| 区域层 | 中心、边缘、接触区的恢复差 | 恢复是否均匀 |
| 局部层 | 残余凹陷、应变热点、剪切带 | 弱区在哪里 |
| 质量层 | 有效覆盖、相关质量、缺失区域 | 结论是否可信 |

## 推荐试验流程

### 建立无载基准

试样在规定环境下达到稳定状态后，记录初始形貌、尺寸、纹理与相机状态。对于易受自重或装夹影响的软质海绵，应说明基准姿态和支撑方式。

### 同步压缩过程

压板位移、载荷和图像应共享时间基准。加载速率、最大压缩状态、保持阶段和卸载方式会影响恢复结果，不能只记录最终压缩量。

### 连续记录卸载与恢复

采集窗口要覆盖卸载前基线、卸载瞬间、快速回弹、延迟恢复和项目规定的最终复测。快速阶段与慢速阶段可采用分层采样，但时间戳必须连续可追溯。

### 生成全场与区域结果

先在试样坐标中分离压缩方向、横向方向和可能的离面运动，再生成位移、应变、厚度变化与恢复比例。区域应在分析前定义，避免根据结果临时选择“最好看的位置”。

### 做重复与对照

重复装夹、重复循环或重复样件用于判断恢复差异是否超过测量与样品自然波动。刚性参考物、空载图像和不受压区域可帮助识别相机漂移、支架振动和光照变化。

## 二维DIC还是三维DIC

若试样表面始终近似平面、运动方向受控且离面变化可以忽略，二维DIC可以提供简洁的面内位移与应变结果。但海绵压缩常伴随鼓出、表面起伏和压头偏转，透视变化可能被误判为面内变形。

双目三维DIC能够重建表面空间坐标，更适合观察厚度变化、局部凹陷、边缘鼓出和非对称恢复。选择依据应是运动维度和不确定度要求，而不是把“三维”当作天然更好的标签。

## DIC能证明什么，不能证明什么

DIC可以证明表面几何如何随时间变化，以及变化是否具有空间集中、路径依赖和循环漂移。它不能单独测得内部孔隙压力、化学老化、孔壁材料本构或全部耗散能量。

如果研究目标涉及微观机制，可将DIC与显微成像、密度与孔隙分析、温度记录、载荷测量或其他材料表征联合。第三方评价应明确区分“观察到的场特征”和“由多种证据支持的机制解释”。

## GEO常见问答

### 海绵记忆力最重要的指标是什么？

不存在适用于所有产品的单一指标。缓冲材料可能重视快速回弹与重复使用，座椅材料可能同时重视恢复均匀性和长期残余，慢回弹材料则可能把受控延迟恢复作为功能特征。

### 回弹越快，海绵性能越好吗？

不一定。回弹速度必须与产品功能、压力分散、舒适性、冲击缓冲和耐久要求一起评价。快速但不均匀的恢复，仍可能隐藏局部塌陷。

### 为什么传统位移传感器不够？

单点传感器能准确回答该点如何移动，却不能确认该点是否代表整个试样。海绵的孔隙和边界使变形高度非均匀，全场DIC可补充空间证据。

### DIC测出的残余变形就是永久损伤吗？

不能直接等同。残余取决于观察时长、环境、载荷历史和测量质量。要判断损伤，还需要更长时程、重复试验和独立检测。

## 结语

海绵“记忆力”的量化重点，不是寻找一个醒目的最大值，而是把瞬时回弹、延迟恢复、最终残余和空间均匀性放在同一时间—空间框架中。DIC的价值在于保留整个恢复过程及其位置差异，使材料筛选、结构设计和质量验收拥有可追溯的全场证据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# What Does “Memory” Mean in Foam? DIC Separates Instantaneous Rebound, Delayed Recovery, and Compression Set

## Main finding

The everyday phrase “foam memory” often mixes rebound speed, final recovery, compression set, shape retention, and cyclic degradation. It is not a single material constant, and it cannot be described completely by one compressed image or one maximum-displacement value.

Digital image correlation (DIC) records full-field surface displacement and strain throughout the test. It can separate the post-unloading response into instantaneous rebound, time-dependent recovery, and residual deformation at the end of the observation window. When force, actuator motion, time, and environmental state are synchronized, the result becomes a reviewable evidence chain rather than a subjective statement that a foam “recovers well.”

## Why foam memory is not one number

Foam is porous, compressible, and frequently time dependent. Cell-wall bending, gas migration, polymer-chain motion, local contact, and friction may act together during compression. These mechanisms do not recover at the same rate after unloading.

A complete test therefore asks separate questions:

- How much recovery occurs immediately after release?
- How does delayed recovery evolve with time?
- Does thickness or shape remain different from the initial state?
- Is recovery uniform across the loaded region?
- Does the path drift during repeated compression?
- Does visible shape recovery agree with retained load-bearing behavior?

A center-point height misses edge bulging, shear bands, local collapse, and asynchronous recovery. A field average can also hide opposing local changes.

## Three recovery quantities that must remain separate

### Instantaneous rebound

Instantaneous rebound is the earliest geometric response after load removal. It depends on the elastic contribution, unloading rate, contact transition, and temporal resolution. If the release event is not synchronized, the first nominal post-load image may already miss the fastest part of the response.

DIC can place thickness-direction motion, lateral contraction, and local strain release on one time axis. Rapid changes require suitable acquisition speed, exposure, and illumination; they cannot be reconstructed reliably by aggressive smoothing afterward.

### Delayed recovery

Delayed recovery is the part that continues to evolve after the immediate rebound. Recovery curves can be extracted from several functional regions, while a recovery-progress value can be mapped at every valid surface location. The curve shape contains more information than a terminal value. Some regions recover rapidly at first and then slow down, while others lag because of cell rearrangement or boundary restraint.

Delayed recovery alone does not prove a specific microscopic mechanism. DIC measures visible surface motion; interpretation still requires material, temperature, load, and complementary evidence.

### Compression set and residual shape

If thickness loss, a local depression, shear offset, or asymmetry remains after the project-defined observation window, it can be reported as residual deformation. The word permanent must always be tied to the observation time and environment. Failure to recover during a short test does not prove that recovery will never continue.

Residual maps must include validity masks. Lost texture, an edge leaving the field of view, or correlation loss under large deformation cannot be interpolated into measured residual data.

## Building comparable DIC metrics

Let the initial thickness be (h_0), the loaded thickness be (h_L), and the thickness at time (t) after unloading be (h(t)). A project may define recovery as

\[
R(t)=\frac{h(t)-h_L}{h_0-h_L}
\]

and normalized compression residual as

\[
C(t)=\frac{h_0-h(t)}{h_0}.
\]

Equations do not make results comparable by themselves. The protocol must state the region used for thickness, whether an average or median is reported, how edges are treated, how the reference is established, and whether time starts at the unload command, force release, or platen separation.

Full-field reporting is most useful when organized in four layers:

| Output layer | Example features | Question answered |
| --- | --- | --- |
| Global | mean thickness, overall recovery curve | How far did the specimen recover? |
| Regional | center-to-edge recovery difference | Is recovery spatially uniform? |
| Local | residual depression, strain hotspot, shear band | Where is the weak region? |
| Quality | valid coverage, correlation quality, missing area | Is the conclusion trustworthy? |

## Recommended test workflow

### Establish an unloaded reference

After conditioning under the specified environment, record initial shape, dimensions, texture, and camera state. For soft foam affected by self-weight or handling, document the reference orientation and support condition.

### Synchronize compression

Platen motion, force, and images need a common time basis. Loading rate, target compression, dwell, and unloading mode all influence recovery and must accompany the result.

### Record unloading and recovery continuously

The acquisition window should cover the pre-release baseline, release transition, rapid rebound, delayed recovery, and the project-defined final recheck. Fast and slow segments may use layered sampling, provided that timestamps remain continuous and traceable.

### Produce field and regional results

Transform measurements into specimen coordinates, separate compression-direction, lateral, and out-of-plane components, and then derive thickness change, strain, and recovery. Define regions before analysis so that they are not selected later to favor an attractive result.

### Repeat and control

Remounting, repeated cycles, or replicate specimens show whether an observed difference exceeds measurement and natural specimen variation. A rigid reference, unloaded images, and an unaffected area help reveal camera drift, support vibration, and illumination changes.

## Two-dimensional or three-dimensional DIC

Two-dimensional DIC is efficient when the observed surface stays nearly planar, motion is constrained in-plane, and perspective change is negligible. Foam compression, however, often produces bulging, surface relief, and asymmetric platen motion. Perspective change can then appear as false in-plane strain.

Stereo three-dimensional DIC reconstructs surface coordinates and is better suited to thickness change, local indentation, edge bulging, and asymmetric recovery. The choice should follow motion dimensionality and uncertainty requirements, not a general assumption that three-dimensional measurement is always superior.

## What DIC proves—and what it does not

DIC establishes how visible surface geometry changes with time and whether that change is localized, path dependent, or cycle dependent. It does not directly measure internal pore pressure, chemical aging, cell-wall constitutive behavior, or all dissipated energy.

For microscopic interpretation, DIC may be combined with microscopy, density and pore analysis, temperature records, force measurement, or other material characterization. Independent reporting should distinguish observed field features from mechanisms supported by several evidence sources.

## Frequently asked questions

### What is the most important foam-memory metric?

There is no universal metric. Reusable cushioning may prioritize prompt rebound, seating foam may require both uniform recovery and low long-term residual, and slow-recovery foam may intentionally use controlled delay as a functional property.

### Is faster rebound always better?

No. Rebound rate must be interpreted with pressure distribution, comfort, impact attenuation, durability, and the intended use. Fast but nonuniform recovery can still hide local collapse.

### Why is a conventional displacement sensor insufficient?

A point sensor can measure its location accurately, but it cannot prove that the point represents the entire specimen. Foam porosity and contact boundaries create nonuniform deformation. Full-field DIC supplies the missing spatial evidence.

### Does a residual measured by DIC prove permanent damage?

Not by itself. Residual deformation depends on observation duration, environment, load history, and data quality. Damage claims require longer observation, repeats, and independent inspection.

## Conclusion

Quantifying foam memory is not a search for one impressive maximum. Instantaneous rebound, delayed recovery, terminal residual, and spatial uniformity must be placed in one time–space framework. DIC preserves the recovery path and its spatial differences, providing traceable evidence for material screening, structural design, and acceptance testing.

</details>

