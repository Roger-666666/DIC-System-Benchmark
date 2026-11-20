# 高温材料本构与有限元验证：XTDIC 联动红外热像的多场试验方案

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温材料本构与有限元验证：XTDIC 联动红外热像的多场试验方案</b></summary>

<a id="chinese-version"></a>

高温材料模型决定热加工载荷、变形分布与局部失稳的预测结果。模型验证需要在相应热条件下同时考察整体受力和局部响应。XTDIC 三维应变测量系统联动红外热像，可提供位移场、应变场和表面温度历程，并与试验机载荷对应，为本构参数识别和有限元验证建立多种独立的比较量。

**目录**

- [仿真研发需要怎样的试验数据](#chinese-section-1)
- [XTDIC 与热像建立多场观测](#chinese-section-2)
- [从参数标定到独立验证](#chinese-section-3)
- [虚拟标距与模型边界对应](#chinese-section-4)
- [温度场输入与材料响应](#chinese-section-5)
- [有限元表面场与实测场比较](#chinese-section-6)
- [模型适用范围与跨工况验证](#chinese-section-7)
- [材料与结构设计中的应用](#chinese-section-8)
- [应用问答](#chinese-section-9)

<a id="chinese-section-1"></a>

## 仿真研发需要怎样的试验数据

整体载荷曲线能够约束模型的承载响应，局部场则检验变形在空间中的分配。两个模型可能给出接近的总伸长和反力，却预测出不同宽度或不同位置的集中带。设计任务涉及局部失效时，这种差异会直接影响模型的使用范围。

高温测试还需要明确材料实际经历的热条件。炉温设定、可见表面温度与试样内部温度属于不同信息。红外观测可用于检查表面温度分布，内部热状态则需通过相应传热模型或附加测量推定。将边界输入与独立观测说明清楚，后续模型比较才有明确依据。

<a id="chinese-section-2"></a>

## XTDIC 与热像建立多场观测

双目相机记录散斑运动，XTDIC 将其转换为表面位移和应变。研究人员可在试样上定义虚拟标距，也可针对集中带及邻近区域提取历程。红外通道同时记录表面热分布，通过共同时间把力、温度和局部伸长联系起来。

配置时需要确定观察表面、参考状态和载荷方向，并考虑试样在加载后的运动范围。热态标定与图像质量校核保证空间数据可用，时间对应则让模型输出和实测数据能够比较同一阶段。软件生成的图形之外，还应保留可导出的坐标、位移及有效区域。

<a id="chinese-section-3"></a>

## 从参数标定到独立验证

可先使用较均匀变形阶段的载荷和工作段伸长约束材料参数，再以局部化阶段的空间场检验模型对分布的预测。若某组实测位移直接用于施加模型边界，它就成为输入；模型反力与其他部位的运动则可以作为独立检验对象。

为了评价跨工况能力，可以将一部分温度或加载条件用于参数识别，其余条件用于预测比较。每次修正模型时记录希望改变的响应，例如均匀阶段反力、集中带宽度或表面温度梯度。用预先保留的观测检查这些变化，有助于识别修正是否具有可迁移性。

<a id="chinese-section-4"></a>

## 虚拟标距与模型边界对应

试验机的横梁位移可能包含夹具与连接件的弹性变形，加载初期还可能包含装夹间隙被消除的过程。若模型只保留圆棒工作段，把横梁位移全都施加到这个短模型上，会把系统其他部分的运动也分配给试样。可以利用 XTDIC 的表面位移在工作段两端建立虚拟标距，提取两端小区域沿拉伸方向的相对位移。在模型上找出相同位置，得到与试验量具有相同含义的伸长。这样便能区分总行程与材料本身伸长的差异。

若把实测标距两端的位移直接用于驱动模型，这项位移就是已知输入。模型对这对位置的位移复现得再好，也不能单独作为预测有效的证据。更有区分力的比较是固定这项输入，检查计算的反力能否跟随实测载荷，以及两端之间各小段的伸长是否分配正确。对于截去了夹持端的局部模型，还应说明工作段截面上的横向约束如何设置，因为相同的轴向位移可以伴随不同的横向收缩。

<a id="chinese-section-5"></a>

## 温度场输入与材料响应

高温圆棒的试验温度常用一个工况标签表示，热像却可能在同一时刻显示从中部到两端的温度变化。可先把模型表面温度和热像映射到相同的轴向区域，按保温末期、较均匀拉伸期和局部化期分别比较。若表面温差在加载前已经存在，应先检查加热方式、夹具传热和边界散热能否解释这条分布。若把所有差异都归入温度对材料强度的影响，即使拟合出合适的拉力，也可能掩盖热边界条件的偏差。

为了辨认热场输入对结论有多大影响，可以分别使用合理的均温近似和受实测表面温度约束的热场，保持几何、力学边界和材料参数一致，查看预测集中带的位置与范围是否明显改变。若两组结果都能描述峰值拉力，局部场却出现不同趋势，下一步最有价值的测量可能是补充温度参考，而非立即增加材料模型的自由参数。

<a id="chinese-section-6"></a>

## 有限元表面场与实测场比较

有限元结果可以覆盖整根圆棒内部，DIC 则只能给出两台可见光相机共同观察到的表面。导出结果时应只取与试验同侧的表面，统一轴向、朝向与参考时刻，屏蔽被遮挡和散斑失配的区域。初始坐标与变形后的坐标也要分清：若一幅图按初始材料位置绘制，另一幅按当前外形显示，误差最大的带状区域可能只是同一段材料在两张图上被放到了不同位置。

具体比较可从工作段的轴向剖面开始。沿相同材料路径求模型与试验的差值，分别观察均匀区的系统偏差、集中区中心的偏移，以及集中带沿轴线延伸的宽度。如果差值在带的一侧为正、另一侧为负，而两幅图的峰值相近，可能意味着带的位置错开。若中心位置相近但模型峰值明显更尖，则需核对网格、材料局部化处理和应变平均尺度。把这两种偏差压缩成一个全场平均误差，容易丢失下一步修正需要的线索。

<a id="chinese-section-7"></a>

## 模型适用范围与跨工况验证

模型可能很好地重现均匀伸长阶段的载荷，却无法稳定预测颈缩后的轮廓。这种情况仍可形成有用的工程结论，例如把模型用于目标热状态下的整体拉力估算，并明确局部失稳仍需额外验证。对于要预测断裂位置的用途，要求则更高。应确认局部化在独立试样上也具有可重复的空间特征，并检查试样几何偏差、装夹偏心或初始温差是否足以改变预测位置。

最后还要考虑试验自身的散布。在同一条件下重复加载，若颈缩位置本来就会沿标距段移动，则单次试验的一个精确坐标不足以当作所有模型的唯一正确答案。报告可以给出试验可重复的区域或分布特征，再评价模型落在这个范围内的能力。区分材料参数标定用的工况和留作独立验证的工况，并保留每个结论所依据的有效帧，后续团队才知道哪些预测可以沿用、哪些需要补做试验。

### 一次模型修正如何留下可检验的预测

假设在某个温度工况下，计算的载荷曲线较接近实测，但局部应变带总是偏向试样一端。此时可以按代价较低、容易独立核对的因素逐项检查。先确认试验图像与计算坐标是否左右翻转，再查看夹持端位移和初始温度沿轴向的分布，最后再审视材料软化与局部化的描述方式。若坐标方向有误，改变材料参数不可能解决真正的偏差；若偏差来自某端散热，只有在热边界上能得到解释的修正才具有可迁移性。

每次修正宜先写出它应当改变哪一项观测。例如调整夹具传热后，希望保温末期的表面温度剖面更接近实验；调整材料硬化参数后，希望均匀变形阶段的反力与工作段应变同时改善。随后用未参与这项修正的数据检查改变是否真的出现在预期位置。如果所有参数都一起调，只保留最终一条拟合良好的载荷曲线，后续团队很难判断哪一项修改在另一个工况下仍然适用。

交付时可把每次比较归纳为“模型用途、采用的输入、独立比较量、剩余偏差”四栏。举例而言，一个用于估算拉伸力的模型与一个用于预测局部颈缩的模型，可以共享几何和材料记录，却需要不同的独立证据。保留这个对应关系，有助于后续设计人员在使用预测时找到与自己问题最接近的那项验证。

<a id="chinese-section-8"></a>

## 材料与结构设计中的应用

热加工研究可利用联动测量评估温度差与变形不均匀之间的联系。材料开发可以比较不同工艺状态的局部化特征，结构设计则可关注截面过渡附近的应变分配。对每个任务，模型应接受与最终用途相匹配的试验检验。

XTDIC 的工程价值是使同一组试验数据具有多尺度用途。整体曲线用于反力与平均变形，局部历程用于关键区域，空间场用于分布与位置。加上可追溯的热条件后，实验室能够把模型的有效范围写清楚，为后续设计复用提供实测依据。

<a id="chinese-section-9"></a>

## 应用问答

**哪些实测量适合留作独立验证？**

模型使用某处位移作为边界输入时，可保留其他位置的响应与整体反力进行比较。参与调参的工况与独立预测工况应明确记录。

**不同网格与光学尺度怎样比较？**

可把计算位移投影到实际观测表面，按与实测接近的空间范围求应变，再比较位置、幅值与带宽。

**技术资料**

[设备与应用资料](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [应用素材](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>

<details>
<summary><b>English · Material Calibration and Finite Element Validation with XTDIC and Infrared Thermal Measurements</b></summary>

<a id="english-version"></a>

# Material Calibration and Finite Element Validation with XTDIC and Infrared Thermal Measurements

High-temperature material models predict process loads, deformation and local instability. Validation needs both global and local responses under the relevant thermal conditions. XTDIC linked with thermography supplies displacement, strain and surface temperature histories related to machine force for calibration and independent assessment.

**Contents**

- [Experimental evidence for modelling](#english-section-1)
- [Establishing mechanical and thermal observations](#english-section-2)
- [From calibration to independent validation](#english-section-3)
- [Establishing a matching virtual gauge length](#english-section-4)
- [Connecting the temperature field to the mechanical model](#english-section-5)
- [Putting predicted and measured fields on one plot](#english-section-6)
- [Defining the range of supported use](#english-section-7)
- [Applications in material and structural design](#english-section-8)
- [Application questions](#english-section-9)

<a id="english-section-1"></a>

## Experimental evidence for modelling

Global force constrains load response, while fields test spatial distribution. Similar reactions can conceal different localization sites. Distinguish furnace settings, measured surface temperature and inferred interior temperature when defining thermal inputs.

<a id="english-section-2"></a>

## Establishing mechanical and thermal observations

Stereo texture tracking supplies displacement and strain, virtual gauges and regional histories. Thermography adds surface conditions on the same timeline. Specify the observed surface, reference state, axes, motion coverage and exportable data with validity information.

<a id="english-section-3"></a>

## From calibration to independent validation

Use distributed deformation for parameter identification and spatial localization for further assessment. Imposed measured boundary motion is an input, leaving reaction and other regions as independent outputs. Hold out thermal or loading conditions and state what each model update is expected to improve.

<a id="english-section-4"></a>

## Establishing a matching virtual gauge length

Crosshead travel can include elastic deformation of grips and load-train components as well as seating early in a test. Imposing all that travel on a model containing only the gauge section assigns external motion to the metal. Use XTDIC surface displacements to define small end regions on the gauge and extract their relative axial motion. Reading the same positions in the simulation gives extension with an equivalent physical meaning.

If the two measured end displacements drive the model, reproducing them is a consequence of the input. Independent comparisons can use reaction force and the distribution of extension between those ends. A shortened model should also document lateral constraints at the cut sections. Identical axial movements can accompany different transverse contractions.

<a id="english-section-5"></a>

## Connecting the temperature field to the mechanical model

A single temperature label can conceal a centre-to-end gradient in a hot round bar. Map predicted surface temperatures and thermograms to the same axial zones at the end of the hold, during distributed extension and during localization. A pre-existing temperature difference calls for examination of heating, grip conduction and heat loss. Assigning all disagreement to temperature-dependent material strength can yield an acceptable force fit while concealing an incorrect thermal boundary.

One sensitivity comparison uses a plausible uniform-temperature approximation and a field constrained by measured surface temperatures. Hold geometry, mechanical constraints and material parameters fixed, then examine the predicted location and width of localization. Similar peak forces alongside different local fields may justify an additional temperature reference before adding material parameters.

<a id="english-section-6"></a>

## Putting predicted and measured fields on one plot

Finite element results cover the interior, whereas DIC covers the surface visible to both cameras. Export the corresponding side of the predicted surface, align axes and reference times and mask occluded or untrackable areas. Distinguish initial and current coordinates. A map in the initial material configuration and one plotted on the deformed outline can place the very same patch at different locations, generating a misleading band of apparent error.

Start with axial profiles on the same material path. Examine bias in the uniform region, displacement of the band centre and axial band width separately. Positive differences on one side of a band and negative differences on the other, with similar peak levels, may indicate a location offset. A sharper calculated peak at a similar centre warrants checks on mesh, localization treatment and strain-averaging scale. A single field-average error can obscure these different directions for investigation.

<a id="english-section-7"></a>

## Defining the range of supported use

A model may reproduce global force during distributed extension but predict post-necking shape inconsistently. It can still support force estimates under the assessed conditions if the limitation is reported. Predicting fracture location requires further evidence, including repeatable localization behaviour and checks on the effect of geometric imperfections, misalignment and initial temperature differences.

Consider experimental scatter as well. If repeated bars neck at different locations along the gauge under nominally identical conditions, the exact coordinate in one test is a weak universal target. Report the repeatable region or distribution and assess the model against it. Distinguish calibration conditions from independent validation runs, and retain the valid frames behind each conclusion so that subsequent users can identify the predictions that need additional tests.

### Making a model update produce a testable prediction

Suppose force agrees at one temperature while the calculated band consistently falls toward the wrong end. First check for a mirrored experiment-to-model coordinate system. Then check grip displacement and initial axial temperature distribution before reviewing the description of softening and localization. A parameter change cannot remedy a reversed coordinate system. A grip-cooling explanation should also improve an observable associated with the thermal boundary.

State which observation a change is expected to affect. A grip heat-transfer change should improve the end-of-hold temperature profile. A hardening change should improve force and gauge strain during distributed deformation. Use observations held out from the adjustment to check the prediction. Changing every parameter at once and keeping only a satisfactory force curve makes transfer to another condition difficult to assess.

A handover can record model purpose, imposed input, independent comparison and remaining discrepancy. A force-estimation model and a neck-localization model can share geometry and material records while requiring different independent evidence. This distinction helps designers find the validation relevant to their intended use.

<a id="english-section-8"></a>

## Applications in material and structural design

Applications include thermal processing, heat-treatment comparison and deformation at section transitions. Global curves, regional histories and spatial fields test different scales of prediction. Traceable thermal conditions help define where the resulting model can be reused.

<a id="english-section-9"></a>

## Application questions

**Which observations can remain independent?**

When a displacement drives the model, other locations and reaction force provide separate comparisons. Record calibration and held-out conditions.

**How should different spatial scales be compared?**

Project predictions onto the measured surface and evaluate strain over comparable neighbourhoods before comparing position, magnitude and band width.

**Technical resources**

[Equipment and application information](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [Application material in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

</details>
