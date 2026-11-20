# 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标

> [中文版](#chinese-version) · [English version](#english-version)

<details open>
<summary><b>中文版 · 高温拉伸仿真如何验证？用 XTDIC 应变场、红外温度场与载荷曲线对标</b></summary>

<a id="chinese-version"></a>

*高温材料变形与损伤测量系列 · 仿真验证*

验证高温拉伸仿真，可以先核对试样经历的温度，再比较整体拉力，最后检查局部变形。对于要预测颈缩位置的模型，拉力曲线接近试验值只回答了整体受力问题，还应确认应变集中出现的阶段、位置和范围。XTDIC 高温圆棒拉伸案例提供了开展这类比较所需的多种实验记录。

## 试验为计算提供了哪些依据

公开案例在多个温度工况下对圆棒升温、保温并拉伸，保留了与载荷对应的位移、主应变和红外温度图。从建模角度看，保温结束时的热像可以检查“整段试样均温”这一假定是否合理；轴向位移场可以协助判断标距段的实际运动是否接近模型施加的位移；加载后的应变场则可用于检查模型把新增变形分配到了哪里。这些是方法上的用途，公开资料没有给出某个具体仿真模型的验证误差。

| 对标层次 | 试验记录 | 仿真侧应提供的同类量 |
| --- | --- | --- |
| 热条件 | 可见表面在保温末期和加载中的温度分布 | 相同表面、相同时刻的预测温度 |
| 整体响应 | 试验机载荷及对应位移 | 对应边界的反力，以及同一对位置的相对位移 |
| 局部响应 | 指定方向或主方向的表面应变、集中带位置与宽度 | 同一表面、同一应变定义下的预测场 |

## 一条载荷曲线吻合，为什么还要看云图

设想两个模型在整段标距上的伸长相同：一个把伸长均匀分摊，另一个把它集中到狭窄区域。仅看端部位移无法区分这两种结果。可从实测应变图选取集中带以及带外的邻近区域，分别对照模型在这些区域的应变历程。若模型能重现整体拉力，却把集中带预测得过宽，应先核对比较尺度、热条件和边界约束，再判断是否需要调整材料参数。

尤其要留意“最大应变”的尺度。DIC 通过一片表面区域估计应变，计算模型则可能输出单个小单元中的峰值。直接拿两者最大的数字作比，差异中混有空间平均的影响。将计算得到的表面位移按接近实测的尺度处理，使用相同参考状态、坐标方向和时刻，更容易发现真正需要解释的偏差。

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

## What the experiment can supply

The public case describes heating, holding and pulling round bars at several temperature levels, with displacement, principal strain and thermograms related to load. An end-of-hold thermogram can test the assumption of a uniform gauge-section temperature. Axial displacement can show whether motion in the gauge section is consistent with the imposed model displacement. Later strain maps can show where additional deformation accumulated. These are uses of the experimental records. The case does not report a validation error for a particular model.

| Comparison | Experimental record | Corresponding model output |
| --- | --- | --- |
| Thermal conditions | Surface temperature at the end of the hold and during loading | Temperature on the same surface at corresponding times |
| Global response | Machine force and associated movement | Reaction force at the matching boundary and relative displacement between equivalent locations |
| Local response | Directional or principal surface strain, location and width of the concentrated band | Predicted field on the same surface using the same strain definition |

## Why compare maps after the force curves agree?

Consider two displacement fields that produce the same gauge-length extension. One shares the extension broadly, while the other concentrates it in a narrow region. End displacement cannot distinguish them. Selecting the observed band and an adjacent region makes it possible to compare the evolution of strain inside and outside the band. If force agrees but the predicted band is too wide, measurement scale, thermal conditions and boundary constraints merit examination before changing material parameters.

Peak strain deserves particular care. DIC estimates strain over a surface neighbourhood. A simulation can report a peak from one small element. Comparing the two maxima directly mixes a difference in spatial averaging into the apparent model error. Processing predicted surface displacement over a scale comparable to the measurement, with matching reference state, direction and time, improves interpretation.

## Applications and common questions

**Which records suit material calibration for hot forming?** Force and local extension from stages with reasonably uniform temperature and reliable strain measurements can constrain the applicable temperature and deformation ranges. Post-necking behaviour requires suitable cross-section or shape information for that stage.

**Can a thermogram be used as internal temperature?** It measures the visible surface. Interior estimates require thermal properties and boundary conditions. Surface temperatures already imposed as model inputs should also be distinguished from independent observations retained for assessment.

**How can prediction across conditions be examined?** Reserve temperature conditions that were not used for parameter fitting. Reporting performance for global load, localization site and strain distribution lets a user decide whether the model is supported for force estimation and for local deformation analysis.

[XTDIC specimen, equipment and measured fields](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html) · [Original article in Chinese](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg)

## In this series

- [222 · XTDIC and Infrared Thermography for Hot Tensile Testing of Metal Round Bars](https://github.com/Roger-666666/DIC-System-Benchmark/blob/master/articles/xtdic-infrared-hot-tension-case.md#english-version)

</details>
