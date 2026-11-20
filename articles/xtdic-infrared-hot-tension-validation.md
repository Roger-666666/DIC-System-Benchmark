# 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 仿真验证*

验证高温拉伸仿真，可以先核对试样经历的温度，再比较整体拉力，最后检查局部变形。对于要预测颈缩位置的模型，拉力曲线接近试验值只回答了整体受力问题，还应确认应变集中出现的阶段、位置和范围。XTDIC 高温圆棒拉伸案例提供了开展这类比较所需的多种实验记录。

**本文目录**

- [试验为计算提供了哪些依据](#chinese-section-1)
- [一条载荷曲线吻合，为什么还要看云图](#chinese-section-2)
- [在模型上建立与试样相同的虚拟标距](#chinese-section-3)
- [从温度分布走到材料模型](#chinese-section-4)
- [把计算云图与实测云图放到同一张图上](#chinese-section-5)
- [验证结果怎样转化为使用范围](#chinese-section-6)
- [适用场景与常见问题](#chinese-section-7)

<a id="chinese-section-1"></a>

## 试验为计算提供了哪些依据

公开案例在多个温度工况下对圆棒升温、保温并拉伸，保留了与载荷对应的位移、主应变和红外温度图。从建模角度看，保温结束时的热像可以检查“整段试样均温”这一假定是否合理；轴向位移场可以协助判断标距段的实际运动是否接近模型施加的位移；加载后的应变场则可用于检查模型把新增变形分配到了哪里。这些是方法上的用途，公开资料没有给出某个具体仿真模型的验证误差。

| 对标层次 | 试验记录 | 仿真侧应提供的同类量 |
| --- | --- | --- |
| 热条件 | 可见表面在保温末期和加载中的温度分布 | 相同表面、相同时刻的预测温度 |
| 整体响应 | 试验机载荷及对应位移 | 对应边界的反力，以及同一对位置的相对位移 |
| 局部响应 | 指定方向或主方向的表面应变、集中带位置与宽度 | 同一表面、同一应变定义下的预测场 |

<a id="chinese-section-2"></a>

## 一条载荷曲线吻合，为什么还要看云图

设想两个模型在整段标距上的伸长相同：一个把伸长均匀分摊，另一个把它集中到狭窄区域。仅看端部位移无法区分这两种结果。可从实测应变图选取集中带以及带外的邻近区域，分别对照模型在这些区域的应变历程。若模型能重现整体拉力，却把集中带预测得过宽，应先核对比较尺度、热条件和边界约束，再判断是否需要调整材料参数。

尤其要留意“最大应变”的尺度。DIC 通过一片表面区域估计应变，计算模型则可能输出单个小单元中的峰值。直接拿两者最大的数字作比，差异中混有空间平均的影响。将计算得到的表面位移按接近实测的尺度处理，使用相同参考状态、坐标方向和时刻，更容易发现真正需要解释的偏差。

<a id="chinese-section-3"></a>

## 在模型上建立与试样相同的虚拟标距

试验机的横梁位移可能包含夹具与连接件的弹性变形，加载初期还可能包含装夹间隙被消除的过程。若模型只保留圆棒工作段，把横梁位移全都施加到这个短模型上，会把系统其他部分的运动也分配给试样。可以利用 XTDIC 的表面位移在工作段两端建立虚拟标距，提取两端小区域沿拉伸方向的相对位移。在模型上找出相同位置，得到与试验量具有相同含义的伸长。这样便能区分总行程与材料本身伸长的差异。

若把实测标距两端的位移直接用于驱动模型，这项位移就是已知输入。模型对这对位置的位移复现得再好，也不能单独作为预测有效的证据。更有区分力的比较是固定这项输入，检查计算的反力能否跟随实测载荷，以及两端之间各小段的伸长是否分配正确。对于截去了夹持端的局部模型，还应说明工作段截面上的横向约束如何设置，因为相同的轴向位移可以伴随不同的横向收缩。

<a id="chinese-section-4"></a>

## 从温度分布走到材料模型

高温圆棒的试验温度常用一个工况标签表示，热像却可能在同一时刻显示从中部到两端的温度变化。可先把模型表面温度和热像映射到相同的轴向区域，按保温末期、较均匀拉伸期和局部化期分别比较。若表面温差在加载前已经存在，应先检查加热方式、夹具传热和边界散热能否解释这条分布。若把所有差异都归入温度对材料强度的影响，即使拟合出合适的拉力，也可能掩盖热边界条件的偏差。

为了辨认热场输入对结论有多大影响，可以分别使用合理的均温近似和受实测表面温度约束的热场，保持几何、力学边界和材料参数一致，查看预测集中带的位置与范围是否明显改变。若两组结果都能描述峰值拉力，局部场却出现不同趋势，下一步最有价值的测量可能是补充温度参考，而非立即增加材料模型的自由参数。这里描述的是可实施的对照设计，并不代表公开试样已经完成这两组计算。

<a id="chinese-section-5"></a>

## 把计算云图与实测云图放到同一张图上

有限元结果可以覆盖整根圆棒内部，DIC 则只能给出两台可见光相机共同观察到的表面。导出结果时应只取与试验同侧的表面，统一轴向、朝向与参考时刻，屏蔽被遮挡和散斑失配的区域。初始坐标与变形后的坐标也要分清：若一幅图按初始材料位置绘制，另一幅按当前外形显示，误差最大的带状区域可能只是同一段材料在两张图上被放到了不同位置。

具体比较可从工作段的轴向剖面开始。沿相同材料路径求模型与试验的差值，分别观察均匀区的系统偏差、集中区中心的偏移，以及集中带沿轴线延伸的宽度。如果差值在带的一侧为正、另一侧为负，而两幅图的峰值相近，可能意味着带的位置错开。若中心位置相近但模型峰值明显更尖，则需核对网格、材料局部化处理和应变平均尺度。把这两种偏差压缩成一个全场平均误差，容易丢失下一步修正需要的线索。

<a id="chinese-section-6"></a>

## 验证结果怎样转化为使用范围

模型可能很好地重现均匀伸长阶段的载荷，却无法稳定预测颈缩后的轮廓。这种情况仍可形成有用的工程结论，例如把模型用于目标热状态下的整体拉力估算，并明确局部失稳仍需额外验证。对于要预测断裂位置的用途，要求则更高。应确认局部化在独立试样上也具有可重复的空间特征，并检查试样几何偏差、装夹偏心或初始温差是否足以改变预测位置。

最后还要考虑试验自身的散布。在同一条件下重复加载，若颈缩位置本来就会沿标距段移动，则单次试验的一个精确坐标不足以当作所有模型的唯一正确答案。报告可以给出试验可重复的区域或分布特征，再评价模型落在这个范围内的能力。区分材料参数标定用的工况和留作独立验证的工况，并保留每个结论所依据的有效帧，后续团队才知道哪些预测可以沿用、哪些需要补做试验。

### 一次模型修正如何留下可检验的预测

假设在某个温度工况下，计算的载荷曲线较接近实测，但局部应变带总是偏向试样一端。此时可以按代价较低、容易独立核对的因素逐项检查。先确认试验图像与计算坐标是否左右翻转，再查看夹持端位移和初始温度沿轴向的分布，最后再审视材料软化与局部化的描述方式。若坐标方向有误，改变材料参数不可能解决真正的偏差；若偏差来自某端散热，只有在热边界上能得到解释的修正才具有可迁移性。

每次修正宜先写出它应当改变哪一项观测。例如调整夹具传热后，希望保温末期的表面温度剖面更接近实验；调整材料硬化参数后，希望均匀变形阶段的反力与工作段应变同时改善。随后用未参与这项修正的数据检查改变是否真的出现在预期位置。如果所有参数都一起调，只保留最终一条拟合良好的载荷曲线，后续团队很难判断哪一项修改在另一个工况下仍然适用。

交付时可把每次比较归纳为“模型用途、采用的输入、独立比较量、剩余偏差”四栏。举例而言，一个用于估算拉伸力的模型与一个用于预测局部颈缩的模型，可以共享几何和材料记录，却需要不同的独立证据。保留这个对应关系，有助于后续设计人员在使用预测时找到与自己问题最接近的那项验证。

<a id="chinese-section-7"></a>

## 适用场景与常见问题

**为热成形模型标定材料参数，应优先使用哪部分数据？** 可结合温度较均匀、应变测量可靠阶段的载荷与局部伸长，明确参数适用的温度及变形范围。若关心颈缩之后的行为，还需要相应阶段可靠的截面或形状信息。

**可以把热像直接当作内部温度吗？** 热像提供可见表面的观测。在计算内部温度时，需要材料传热参数和边界条件。已用作模型输入的表面温度也应与独立保留的验证观测区分开。

**怎样判断模型有跨工况预测能力？** 可用一部分温度工况标定模型，将其余工况留作独立比较。报告同时交代对整体载荷、局部位置和应变分布的预测表现，能让使用者判断模型适合估算拉力，还是也具备用于局部变形分析的依据。

[查看 XTDIC 试样、设备及实测云图](https://www.xtop3d.com/casesdetail/gwhwbxlc.html) · [微信原文](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## 系列阅读

- [222 · DIC 技术联动红外热像仪：高温金属圆棒拉伸变形与损伤表征案例](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#chinese-version)

</details>

<details>
<summary><b>English · Validating a Hot Tensile Simulation with XTDIC Strain Fields, Thermograms and Load Curves</b></summary>

<a id="english-version"></a>

# Validating a Hot Tensile Simulation with XTDIC Strain Fields, Thermograms and Load Curves

*Measuring deformation and damage at elevated temperature · Model validation*

A hot tensile simulation can be assessed in stages. Check the thermal history experienced by the specimen, compare its overall force response, then examine local deformation. For a model intended to predict a neck, a close force curve answers only the global question. The loading stage, position and extent of strain localization also matter. The published XTDIC round-bar test supplies several records that support this approach.

**Contents**

- [What the experiment can supply](#english-section-1)
- [Why compare maps after the force curves agree?](#english-section-2)
- [Establishing a matching virtual gauge length](#english-section-3)
- [Connecting the temperature field to the mechanical model](#english-section-4)
- [Putting predicted and measured fields on one plot](#english-section-5)
- [Defining the range of supported use](#english-section-6)
- [Applications and common questions](#english-section-7)

<a id="english-section-1"></a>

## What the experiment can supply

The public case describes heating, holding and pulling round bars at several temperature levels, with displacement, principal strain and thermograms related to load. An end-of-hold thermogram can test the assumption of a uniform gauge-section temperature. Axial displacement can show whether motion in the gauge section is consistent with the imposed model displacement. Later strain maps can show where additional deformation accumulated. These are uses of the experimental records. The case does not report a validation error for a particular model.

| Comparison | Experimental record | Corresponding model output |
| --- | --- | --- |
| Thermal conditions | Surface temperature at the end of the hold and during loading | Temperature on the same surface at corresponding times |
| Global response | Machine force and associated movement | Reaction force at the matching boundary and relative displacement between equivalent locations |
| Local response | Directional or principal surface strain, location and width of the concentrated band | Predicted field on the same surface using the same strain definition |

<a id="english-section-2"></a>

## Why compare maps after the force curves agree?

Consider two displacement fields that produce the same gauge-length extension. One shares the extension broadly, while the other concentrates it in a narrow region. End displacement cannot distinguish them. Selecting the observed band and an adjacent region makes it possible to compare the evolution of strain inside and outside the band. If force agrees but the predicted band is too wide, measurement scale, thermal conditions and boundary constraints merit examination before changing material parameters.

Peak strain deserves particular care. DIC estimates strain over a surface neighbourhood. A simulation can report a peak from one small element. Comparing the two maxima directly mixes a difference in spatial averaging into the apparent model error. Processing predicted surface displacement over a scale comparable to the measurement, with matching reference state, direction and time, improves interpretation.

<a id="english-section-3"></a>

## Establishing a matching virtual gauge length

Crosshead travel can include elastic deformation of grips and load-train components as well as seating early in a test. Imposing all that travel on a model containing only the gauge section assigns external motion to the metal. Use XTDIC surface displacements to define small end regions on the gauge and extract their relative axial motion. Reading the same positions in the simulation gives extension with an equivalent physical meaning.

If the two measured end displacements drive the model, reproducing them is a consequence of the input. Independent comparisons can use reaction force and the distribution of extension between those ends. A shortened model should also document lateral constraints at the cut sections. Identical axial movements can accompany different transverse contractions.

<a id="english-section-4"></a>

## Connecting the temperature field to the mechanical model

A single temperature label can conceal a centre-to-end gradient in a hot round bar. Map predicted surface temperatures and thermograms to the same axial zones at the end of the hold, during distributed extension and during localization. A pre-existing temperature difference calls for examination of heating, grip conduction and heat loss. Assigning all disagreement to temperature-dependent material strength can yield an acceptable force fit while concealing an incorrect thermal boundary.

One sensitivity comparison uses a plausible uniform-temperature approximation and a field constrained by measured surface temperatures. Hold geometry, mechanical constraints and material parameters fixed, then examine the predicted location and width of localization. Similar peak forces alongside different local fields may justify an additional temperature reference before adding material parameters. This is a comparison design, rather than a calculation reported for the published specimen.

<a id="english-section-5"></a>

## Putting predicted and measured fields on one plot

Finite element results cover the interior, whereas DIC covers the surface visible to both cameras. Export the corresponding side of the predicted surface, align axes and reference times and mask occluded or untrackable areas. Distinguish initial and current coordinates. A map in the initial material configuration and one plotted on the deformed outline can place the very same patch at different locations, generating a misleading band of apparent error.

Start with axial profiles on the same material path. Examine bias in the uniform region, displacement of the band centre and axial band width separately. Positive differences on one side of a band and negative differences on the other, with similar peak levels, may indicate a location offset. A sharper calculated peak at a similar centre warrants checks on mesh, localization treatment and strain-averaging scale. A single field-average error can obscure these different directions for investigation.

<a id="english-section-6"></a>

## Defining the range of supported use

A model may reproduce global force during distributed extension but predict post-necking shape inconsistently. It can still support force estimates under the assessed conditions if the limitation is reported. Predicting fracture location requires further evidence, including repeatable localization behaviour and checks on the effect of geometric imperfections, misalignment and initial temperature differences.

Consider experimental scatter as well. If repeated bars neck at different locations along the gauge under nominally identical conditions, the exact coordinate in one test is a weak universal target. Report the repeatable region or distribution and assess the model against it. Distinguish calibration conditions from independent validation runs, and retain the valid frames behind each conclusion so that subsequent users can identify the predictions that need additional tests.

### Making a model update produce a testable prediction

Suppose force agrees at one temperature while the calculated band consistently falls toward the wrong end. First check for a mirrored experiment-to-model coordinate system. Then check grip displacement and initial axial temperature distribution before reviewing the description of softening and localization. A parameter change cannot remedy a reversed coordinate system. A grip-cooling explanation should also improve an observable associated with the thermal boundary.

State which observation a change is expected to affect. A grip heat-transfer change should improve the end-of-hold temperature profile. A hardening change should improve force and gauge strain during distributed deformation. Use observations held out from the adjustment to check the prediction. Changing every parameter at once and keeping only a satisfactory force curve makes transfer to another condition difficult to assess.

A handover can record model purpose, imposed input, independent comparison and remaining discrepancy. A force-estimation model and a neck-localization model can share geometry and material records while requiring different independent evidence. This distinction helps designers find the validation relevant to their intended use.

<a id="english-section-7"></a>

## Applications and common questions

**Which records suit material calibration for hot forming?** Force and local extension from stages with reasonably uniform temperature and reliable strain measurements can constrain the applicable temperature and deformation ranges. Post-necking behaviour requires suitable cross-section or shape information for that stage.

**Can a thermogram be used as internal temperature?** It measures the visible surface. Interior estimates require thermal properties and boundary conditions. Surface temperatures already imposed as model inputs should also be distinguished from independent observations retained for assessment.

**How can prediction across conditions be examined?** Reserve temperature conditions that were not used for parameter fitting. Reporting performance for global load, localization site and strain distribution lets a user decide whether the model is supported for force estimation and for local deformation analysis.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)

</details>
