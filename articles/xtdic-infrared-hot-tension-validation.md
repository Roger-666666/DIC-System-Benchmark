# 热力耦合仿真如何用 XTDIC 和红外热像验证？从温度边界到应变残差

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

<a id="chinese-version"></a>

**关键词**　热力耦合仿真、温度边界、全场残差

同一条拉力曲线可能对应不同的标距段温度分布和局部变形。高温拉伸模型如需预测颈缩位置，可以把红外表面温度历程和 XTDIC 位移场作为约束。建模前应写清哪些观测用于规定输入，哪些观测保留为预测检验。

## 先判断热边界是否合理

从模型中提取与热像观察面对应的表面温度，比较升温、保温和加载阶段的轴向温度梯度。若已把实测温度作为该表面的给定边界，该处曲线可用于核查输入传递。评价热模型的预测能力，需要留出独立测温位置或另一次加载条件。表面温度记录对厚度方向的温差约束有限。

## 再把力学结果投到相同标距段

对齐试样轴线、加载前参考帧和试验机时间轴。选取相同表面、应变分量和应变定义，将仿真位移按接近 DIC 拟合长度的范围采样，再比较局部化带的位置、宽度与出现阶段。断口、夹具遮挡和失相关区域应从共同可比范围中排除。

## 残差能缩小哪一类问题的范围

若温度梯度已出现系统偏差，应先复核传热边界。若温度与载荷预测均合理，但应变带总靠近一侧夹具，可检查对中、夹持或试样初始几何。保留一个未参与调参的温度工况再做预测，并同时交付温度剖面、位移残差图和有效区域。这样，材料参数在哪些阶段得到试验支持，会比一个拟合误差值清楚得多。

[返回系列导读](xtdic-infrared-hot-tension-case.md#chinese-version)

案例来源：[原文入口](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC 公开试验说明](https://www.xtop3d.com/casesdetail/gwhwbxlc.html)

</details>

---

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

<a id="english-version"></a>

# Validating a Thermomechanical Tensile Model with XTDIC and Infrared Data

**Keywords**　Thermomechanical validation, temperature boundary, field residuals

Similar force histories can accompany different gauge temperatures and local deformation patterns. For a model intended to predict the location of a neck, infrared surface temperatures and XTDIC displacements provide complementary constraints. Specify which observations supply the inputs and which are held back to test a prediction.

## Check the thermal boundary first

Extract the simulated temperature on the face viewed by the thermal camera. Compare axial temperature gradients during heating, dwell and loading. If the measured temperature was prescribed on that face, agreement there checks transfer of the input. Evaluate predictive performance at an independent sensor location or in a held-out loading condition. Surface data alone place limited constraints on the through-thickness gradient.

## Compare the same part of the gauge

Align the specimen axis, unloaded reference and test-machine time base. Select the same face, strain component and strain definition. Sample model displacements over a length comparable to the DIC strain fit, then compare the location, width and loading stage of localization. Exclude fracture openings, grip occlusion and decorrelated regions from the common comparison area.

## Use residuals to guide inspection

A persistent error in the thermal gradient calls for a review of heat-transfer boundaries. If temperature and force predictions are adequate but the strain band is consistently displaced toward one grip, inspect alignment, grip conditions and initial specimen geometry. Predict a temperature condition withheld from parameter adjustment. Report temperature profiles, displacement residuals and the valid comparison area so readers can see the stages over which the model has experimental support.

[Back to the case overview](xtdic-infrared-hot-tension-case.md#english-version)

Case documentation: [Original article](https://mp.weixin.qq.com/s/fac1eqMF2A5h3gOePYX3Yg) · [XTDIC test description](https://www.xtop3d.com/en/casesdetail/high-temperature-tensile-testing-dic-infrared-thermography.html)

</details>
