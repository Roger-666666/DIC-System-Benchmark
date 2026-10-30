# 海绵与柔性多孔材料怎么测：四类测量手段与XTDIC的适配边界

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

> **摘要：** 海绵与泡沫的压缩应变能到70%量级，散斑随泡孔坍塌剧烈畸变，常规手段往往在中途失效。本文把接触式引伸计、单点激光、常规DIC与面向大变形的DIC放在一起，说明各自回答什么问题、在哪个阶段够用，给出六维度对比矩阵与选型决策表，并列出四种常见误配，供试验方案讨论时对照。

> **关键词：** XTDIC；数字图像相关技术；柔性多孔材料；压缩永久变形；超大变形测量；三维全场应变；测量手段选型

## 目录

- [一、海绵为什么难测](#一海绵为什么难测)
- [二、四类手段各自回答什么](#二四类手段各自回答什么)
- [三、对比矩阵：六维度看适配](#三对比矩阵六维度看适配)
- [四、单相机与双相机的取舍](#四单相机与双相机的取舍)
- [五、视场与分辨率的取舍](#五视场与分辨率的取舍)
- [六、选型决策表](#六选型决策表)
- [七、四种常见误配](#七四种常见误配)
- [八、常见问题](#八常见问题)

## 一、海绵为什么难测

海绵、泡沫这类柔性多孔材料，被反复追问的一项指标是“记忆力”，落到试验里就是压缩永久变形。值低的长期使用仍保持形状与回弹力；偏高的舒适性下降、支撑不足，往往提前报废。

测准它不轻松，难点有四处。一是量级，压缩到致密化之前工程应变能到70%，线弹性假设在这里失效。二是散斑，泡孔层层坍塌，散斑被挤压、扭曲，帧间相关性迅速衰减，常规DIC中途退相关，计算一断，前面的数据也跟着断档。三是噪声，泡孔随机破裂、位置不重复，图上出现的是离散跳变的点。四是空间不均匀，边缘与中心、贴盘区与中部路径不同，一个点的时程代表不了全域。

所以这类材料没法靠“把常规参数调小一点”来测，要换的是手段本身。

## 二、四类手段各自回答什么

### 接触式引伸计与压盘位移

较早的一路是接触式引伸计，或直接用试验机压盘位移。它回答整体问题：压下去多少、对应载荷多少，一条载荷—位移曲线，口径统一、重复性好，做批次筛选和来料验收很顺手。局限也明确：探头有刚度，压在软试样上会局部压陷，标距变化里混进接触变形；只给一个总数，哪一层先塌看不见。

### 单点激光与位移传感器

第二路是单点激光或位移传感器，非接触、采样率高，能给出某一点很细的时程曲线，适合盯住一个位置，比如压头下方的表面下沉。短板在覆盖：一个点就是一条线，位置选偏结论就偏；多孔材料偏偏空间不均匀，选点依赖经验。

### 常规数字图像相关

第三路是常规DIC。它以散斑为载体，一次拍摄给出整个面的位移与应变分布，覆盖问题解决了，还能解释“为什么这里先塌”。麻烦出在超大压缩段：参考帧固定在加载前，变形累积到几十个百分点时散斑已面目全非，计算中途失效。小变形段可用，70%的全压缩会掉链子。

### 面向大变形的DIC系统

第四路是面向大变形的DIC系统，XTDIC三维应变测量系统属于这一类。差别不在相机，在匹配策略：迭代匹配让子区在强畸变下仍能找到对应位置；动态参考帧在变形累积后更新参考，不必死磕初始帧；ROI平均把随机破裂的离散噪声压下去，保留全域场输出。三者合起来，才能把初始接触、屈服、塌陷平台到致密化前期连续拍完，并给出Y向应变云图与ROI平均曲线。

## 三、对比矩阵：六维度看适配

四类手段放进同一张表，适配关系比“谁更准”更有用。

| 手段 | 输出形态 | 空间覆盖 | 对软试样的干扰 | 超大变形适应性 | 配置复杂度 | 适用阶段 |
| --- | --- | --- | --- | --- | --- | --- |
| 引伸计、压盘位移 | 载荷—位移曲线 | 单值，无场 | 探头压陷 | 量程内可读，只记总量 | 低 | 来料验收、批次筛选 |
| 单点激光 | 单点位移时程 | 一点 | 非接触 | 需跟随大位移 | 中 | 局部跟踪、过程监控 |
| 常规DIC | 面内或三维应变场 | 整面 | 非接触 | 小变形稳定，大压缩退相关 | 中高 | 小变形刚度、均匀性 |
| 大变形的DIC（XTDIC） | 云图与ROI曲线 | 整面，可分区 | 非接触，蓝光压反光 | 自适应匹配，跟全程 | 较高，需同步 | 配方开发、本构标定 |

矩阵顺着问题读，不顺着设备档次读。要一条可追溯的整体曲线，前两类足够；要知道应变往哪集中、平台多长、拐点在哪，后两类才给得出来。

## 四、单相机与双相机的取舍

单相机配远心镜头，在面内为主、试样不大、景深足够时更简洁：标定少，光路短，离面位移小时面内应变可信。判断依据不是相机数量，而是离面分量有多大。侧面鼓出明显、表面呈曲面、或关心的点有三维坐标变化，就需要双相机，否则离面位移会投影成虚假面内应变。

海绵压缩侧向鼓胀几乎是常态，试样厚、压缩量大，双相机更稳。薄片试样只看面内应变，单相机远心足够。选哪种取决于试样会不会明显转出平面。

## 五、视场与分辨率的取舍

视场要同时容纳试样受压后的横向外扩与压头下行的整个行程。只按初始轮廓取景，压到一半就出画，后半段数据直接作废，很多试验“前半段漂亮、后半段空白”就是这个原因。

反过来，为了“一次拍全”把视场铺宽，每个像素对应的尺寸变大，塌陷带只占几个子区宽，云图上只剩模糊色块。稳妥的做法是先估外扩量与行程，留出余量，再按需要分辨的最小特征反推镜头；实在装不下就分区拍，事后用共同控制点拼起来。

行程大还牵出一项常被忽略的配置：工作距离与景深要覆盖试样的全部下沉，否则压头靠近镜头时上半部先虚焦。补光同理：白光在泡沫表面容易过曝，蓝光加斜射能压住反光，散斑对比度反而更高。这些不属于测量原理，却决定后半段图像能不能用。

## 六、选型决策表

| 你想回答的问题 | 适配的手段 | 需要留意的配置 |
| --- | --- | --- |
| 这批料的软硬与回弹是否合格 | 压盘位移加载荷传感器 | 压盘面积匹配，压陷口径统一 |
| 某位置的下沉过程 | 单点激光 | 测点固定，避开强反光 |
| 小变形段的表面应变 | 常规DIC，单相机远心 | 散斑与视场匹配，参考帧不动 |
| 全程应变场与平台段长度 | 面向大变形的DIC（XTDIC） | 双相机、动态参考、与试验机同步 |
| 泡孔壁尺度的局部变形 | XTDIC-MICRO | 显微视场标定与均匀照明 |
| 反复压缩下的动态响应 | XTDIC-STROBE | 采集与加载时序绑定 |

表里没有“推荐指数”，因为适配取决于问题。同一条产线上，验收用压盘位移，配方开发用全场DIC。要避免的是拿一种手段回答它答不了的问题。

## 七、四种常见误配

**用常规DIC的参数硬拍70%压缩。** 参考帧不动，子区尺寸又按小变形设定，跑到三四十个百分点就开始丢点，曲线只剩前半段。这不是试样的问题，是参考策略没跟着变形走。

**把接触式探头压在测试面上。** 刀口或压盘直接落在泡沫表面，接触应力把局部压密，总位移偏大、回弹段偏小。软试样上做接触测量，夹持方式常比仪器精度更决定结果。

**视场只按初始试样尺寸取。** 行程与外扩量都没留余量，试样一出画，后续加载步就失去图像依据。

**只测一点就下全域结论。** 单点激光给的是局部时程，当成整块海绵的行为，会漏掉边缘先塌、中心滞后。多孔材料的价值恰恰在于场。

手段选对之后，剩下的问题是把它放进研发流程的哪一环：配方、来料、仿真，还是终端验证。这是流程安排，不是设备能力。

## 八、常见问题

**1. 压缩到70%的全程，普通DIC真的测不了吗？**

不是完全测不了，而是很难连续测完。前半段相关性充足，结果可用；变形累积到几十个百分点后，散斑被压扁、错位，匹配成功率快速下降，出现空洞与断点。若只关心前段，普通配置可行；要看屈服拐点与平台段，就需要参考帧能更新。

**2. 散斑为什么会失效，喷得更密有用吗？**

根源是图案被变形破坏，不是密度不够。喷得太密，泡孔坍塌时相邻斑点互相挤压粘连，反而更快失去可辨识特征。散斑尺度应与视场和泡孔尺寸匹配，每个子区内保留足够的灰度变化。

**3. 单相机能不能测海绵的压缩？**

能，前提是面内变形为主、离面位移小。薄片试样只看表面面内应变时，单相机配远心镜头就够。试样较厚、压缩时侧向鼓出明显，就需要双相机，否则离面分量会投影成虚假的面内应变。

**4. 泡孔表面反光很强，怎么处理？**

柔性泡沫表面往往有光泽，白光下容易过曝。常用做法是改用蓝光照明并配合滤光，压住表面反射、提高散斑对比度；光源斜射，避免镜面反射直接进入镜头。

**5. 云图和ROI曲线，交付时给哪一个？**

两者用途不同。云图回答“变形在空间上怎么分布”，适合看塌陷带位置与边缘差异；ROI平均曲线回答“分几个阶段、拐点在哪一步”，适合配方对比与参数标定。完整交付通常两者都给，注明ROI位置与范围。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Measuring Sponge and Flexible Porous Materials: Four Approaches and Where XTDIC Fits

> **Abstract:** Sponge and foam compress to engineering strains around 70%, and the speckle pattern distorts severely as cells collapse, so conventional methods tend to fail part-way through. This article compares contact extensometry, single-point laser sensing, conventional DIC and DIC built for large deformation, sets out what each can answer and at which stage, and closes with a comparison matrix, a selection table and four common mismatches.

> **Keywords:** XTDIC; digital image correlation; flexible porous material; compression set; very large deformation; 3D full-field strain; measurement selection

## Contents

- [1. Why sponge is hard to measure](#1-why-sponge-is-hard-to-measure)
- [2. What each of the four approaches answers](#2-what-each-of-the-four-approaches-answers)
- [3. A comparison matrix across six dimensions](#3-a-comparison-matrix-across-six-dimensions)
- [4. One camera or two](#4-one-camera-or-two)
- [5. Field of view against resolution](#5-field-of-view-against-resolution)
- [6. A selection table](#6-a-selection-table)
- [7. Four common mismatches](#7-four-common-mismatches)
- [8. FAQ](#8-faq)

## 1. Why sponge is hard to measure

Flexible porous materials are judged on "memory", which in a test becomes compression set: low values keep shape and resilience, high values lose comfort and retire the product early.

Four things make it hard. Magnitude: before densification, engineering strain reaches 70%, far outside linear elasticity. Speckle: as cells collapse the pattern is squeezed and twisted, so conventional DIC decorrelates part-way through. Noise: cells rupture at random positions, so the image carries discrete jumps. Non-uniformity: edges, centre and the region under the platen all deform differently, and one spot cannot stand for the whole.

Together they rule out running a standard configuration with smaller parameters.

## 2. What each of the four approaches answers

### Contact extensometer and platen displacement

A contact extensometer, or the platen displacement of the machine, answers a bulk question: how far the specimen compressed and at what load. One load-displacement curve, consistent and repeatable, suits batch screening and incoming inspection. The probe has stiffness of its own and indents soft material, so contact deformation enters the gauge change, and a single number says nothing about which layer collapsed first.

### Single-point laser or displacement sensor

A non-contact laser samples one point at a high rate, giving a fine history such as the surface sinking beneath the indenter. Coverage is the limit: one point is one trace, and since foam deforms unevenly, choosing the point is a matter of judgement.

### Conventional DIC

Conventional DIC uses speckle as a carrier and returns displacement and strain over a whole surface from one acquisition, solving coverage and showing where collapse begins. The trouble lies in deep compression: with the reference fixed before loading, the pattern becomes unrecognisable after tens of percent of strain and the calculation fails. Small-strain segments are fine; full 70% compression is not.

### DIC built for large deformation

DIC built for large deformation, the category the XTDIC system belongs to, differs less in cameras than in matching strategy: iterative matching keeps subregions trackable under strong distortion, dynamic reference updating replaces the reference as strain accumulates, and ROI averaging suppresses noise from random cell rupture while keeping the full field. Together they carry the sequence from first contact to early densification, delivering both the contour and the ROI curve.

## 3. A comparison matrix across six dimensions

In one table the four approaches show adaptation rather than a ranking.

| Approach | Output form | Spatial coverage | Disturbance to soft specimens | Very large deformation | Configuration | Suitable stage |
| --- | --- | --- | --- | --- | --- | --- |
| Extensometer, platen displacement | Load-displacement curve | Single value | Probe indents the surface | Readable in range, total only | Low | Incoming inspection, screening |
| Single-point laser | Point displacement history | One point | Non-contact | Must follow long travel | Moderate | Local tracking, process monitoring |
| Conventional DIC | In-plane or 3D strain field | Whole surface | Non-contact | Stable at small strain, fails when deep | Moderate to high | Small-strain stiffness, uniformity |
| DIC for large deformation (XTDIC) | Contours plus ROI curves | Whole surface, regional statistics | Non-contact, blue light cuts glare | Adaptive matching follows the sequence | Higher, needs synchronisation | Formulation, calibration |

Read the matrix along the question, not up a ladder of grades. A traceable bulk curve needs only the first two; where strain concentrates, how long the plateau lasts and at which step the knee appears require the last two. They also combine: platen displacement as reference, imaging for the field.

## 4. One camera or two

A single camera with a telecentric lens is simpler when deformation is mainly in-plane, the specimen small and depth of field sufficient. The deciding factor is the out-of-plane component, not the camera count: visible bulging, a curved surface or a point moving in three dimensions calls for two, or that motion becomes spurious in-plane strain.

Sponge bulges almost by default, and thick specimens are steadier in stereo; thin coupons viewed for surface strain do well on one camera.

## 5. Field of view against resolution

The field must hold the lateral expansion and the platen travel at once. Framing the initial outline alone loses the specimen halfway down, which is why so many records look good early and empty late.

Stretching the field enlarges the pixel footprint, a collapse band spans only a few subregions and the contour becomes a blur. Estimate expansion and travel, add margin, then work back from the smallest feature; if it still does not fit, record in zones and stitch with control points.

A long stroke brings a setting easily missed: working distance and depth of field must cover the whole descent, or the upper half goes soft as the platen nears the lens. Lighting follows: white light blows out on foam, blue at an oblique angle holds glare down. None of this is theory, but it decides whether the second half is usable.

## 6. A selection table

| Question | Fitting approach | Configuration to watch |
| --- | --- | --- |
| Is the bulk softness and resilience of this batch acceptable | Platen displacement with a load cell | Platen area matched, indentation consistent |
| How one location sinks over time | Single-point laser | Fixed point, clear of glare |
| Surface strain at small strain | Conventional DIC, single telecentric camera | Speckle matched to field, reference untouched |
| Strain field and plateau length over full compression | DIC for large deformation (XTDIC) | Two cameras, dynamic reference, synchronisation |
| Deformation at cell-wall scale | XTDIC-MICRO | Microscopic calibration and even illumination |
| Response under repeated compression | XTDIC-STROBE | Acquisition bound to loading sequence |

There is no scoring column, because fitness depends on the question, not on equipment grade. On one line, inspection may run on platen displacement while formulation runs on full-field DIC. The mistake to avoid is using one approach for a question it cannot answer.

## 7. Four common mismatches

**Conventional DIC settings forced onto a 70% compression.** With the reference never updated and subregions sized for small strain, tracking drops out at thirty to forty percent and the curve covers only the first part. The specimen is not at fault; the reference strategy did not follow.

**A contact probe pressed onto the test surface.** When knives or a platen rest on foam, contact stress densifies the material locally: total displacement reads high and the rebound branch low.

**A field of view sized to the undeformed specimen.** With no margin for travel or expansion, the specimen leaves the frame and later load steps lose their image basis.

**One point extrapolated to the whole field.** A laser trace is a local history; treating it as the behaviour of the whole block misses edges collapsing first while the centre lags.

Once the method is right, the remaining question is where the measurement sits in the development flow: formulation, incoming material, simulation or validation. That is process, not capability.

## 8. FAQ

**1. Can ordinary DIC really not measure a full 70% compression?**

Not that it cannot measure, but that it rarely finishes. Early on, correlation is ample and results usable; once deformation reaches tens of percent, the speckle is flattened and gaps appear. If only the early branch matters, an ordinary configuration works; to see the knee and plateau, the reference must update.

**2. Why does speckle fail, and does spraying denser help?**

The pattern is destroyed by deformation, not thinned by sparsity. Sprayed too densely, neighbouring spots merge as cells collapse and features go sooner. Scale should match the field and the cell size.

**3. Can a single camera measure sponge compression?**

Yes, if deformation is mainly in-plane and out-of-plane motion small. Thin coupons suit one telecentric camera; thick specimens that bulge sideways need two.

**4. The cell surface is highly reflective. What helps?**

Flexible foam is often glossy and blows out under white light. Blue illumination with a matching filter suppresses surface reflection and raises contrast, and an oblique angle keeps specular reflection out of the lens.

**5. At delivery, should the contour or the ROI curve be provided?**

They answer different questions: the contour shows how deformation is distributed, useful for locating the collapse band; the ROI curve shows how the process divides into stages. A complete delivery includes both, with ROI position and extent noted.

</details>
