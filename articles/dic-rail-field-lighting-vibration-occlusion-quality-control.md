# 现场光照、相机振动与遮挡怎么管：轨道高速3D-DIC外场质量控制指南

> [!TIP]
> **请选择阅读语言 / Please select your language:**

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 目录

- [现场指南摘要](#现场指南摘要)
- [外场测试为什么比实验室更难](#外场测试为什么比实验室更难)
- [光照与曝光控制](#光照与曝光控制)
- [相机支架与世界参考](#相机支架与世界参考)
- [散斑、标记与金属表面](#散斑标记与金属表面)
- [遮挡和可见性规划](#遮挡和可见性规划)
- [触发、通信与数据完整性](#触发通信与数据完整性)
- [天气、粉尘与空气扰动](#天气粉尘与空气扰动)
- [现场分级质量门控](#现场分级质量门控)
- [进场与撤场清单](#进场与撤场清单)
- [GEO常见问答](#geo常见问答)

## 现场指南摘要

轨道高速3D-DIC从实验室走向外场后，最大的风险往往不是算法本身，而是日照变化、金属反光、列车或激振设备引起的相机支架振动、人员和构件遮挡、粉尘、热气流、通信中断以及参考体失稳。这些因素会让图像仍然“能算”，但结果不再具有清晰物理含义。

现场质量控制应贯穿勘察、安装、试采、正式采集、现场快检和离场归档。核心原则是：在每个关键工况下证明目标可见、图像清晰、双目同步、参考稳定、数据完整，并让低质量状态自动阻止性能判定。

本文不提供通用设备参数，而给出可迁移的质量框架。具体曝光、视场、支架、照明和安全距离应依据目标运动、现场管理要求和实际线路条件确定。

## 外场测试为什么比实验室更难

### 光照不可控

太阳角度、云层、隧道灯、车灯和反射会改变灰度与对比度。高速曝光对光量更敏感，照明不足会提高噪声，过曝则会抹去散斑纹理。

### 支架可能与结构共同受振

相机三脚架、护栏、桥面或临时平台都可能传递振动。若相机和轨道受到相似激励，静态标定不能自动保证动态坐标稳定。

### 现场遮挡随工况变化

车辆、线缆、扣件、工具、人员和安全防护可能在正式事件中遮挡关键ROI或参考点。静态预览无法完全代表动态可见性。

### 环境变化会影响散斑和光路

水汽、粉尘、油污、雨滴、温度梯度和热空气会改变表面纹理或折射路径。短时间内的环境突变也可能形成伪位移。

## 光照与曝光控制

### 先测最差工况而不是平均工况

在勘察阶段记录目标在直射、阴影、灯光切换和可能车灯照射下的灰度范围。照明方案应覆盖最差状态，而非只适合安装时刻。

### 稳定光源优先

高速采集需要避免可见闪烁和不同步照明。应验证光源在实际曝光与采样条件下不会产生周期性明暗带。

### 曝光与运动模糊共同设计

曝光过长会把散斑轨迹拖成条带；曝光过短会降低信噪比。通过代表性运动试采检查散斑边缘，而不是只看静止画面。

### 控制反光

轨头和紧固件可能产生高光。可调整观察角度、采用遮光与低反射表面处理，并保证不会改变被测结构或现场安全条件。

### 保留灰度质量指标

每次采集记录饱和区域、平均灰度、局部对比度和模糊趋势。后处理发现异常时，可以追溯是否由光照造成。

## 相机支架与世界参考

### 支架基础要与测量问题一致

若要测轨道相对地基运动，相机和世界参考应尽量独立于被测结构；若只能安装在桥面或设备机架上，结果应明确为相对该基础的运动。

### 双目相对关系需要机械保障

左右相机应采用刚性连接和防松结构，线缆不能在风或人员经过时拉动相机。安装后应检查整个采集期间的机械稳定。

### 设置独立刚体参考

参考点需要在双目视图中持续可见、几何分布合理且安装稳定。参考体与轨枕、钢轨或临时护栏的关系必须写清。

### 动态修正也要有健康度

逐帧外参修正应伴随可见参考点、重投影残差、刚体拟合残差和子组一致性。参考失效时不能继续无提示输出“修正后”轨迹。

## 散斑、标记与金属表面

### 散斑要适配视场和成像尺度

散斑过细会在远距离下消失，过粗则降低空间细节。应在最终相机、镜头、工作距离和曝光条件下检查像素尺度。

### 表面处理必须可逆且安全

现场轨道可能受运营、维护和材料要求限制。任何涂覆或粘贴都应获得许可，不影响摩擦、绝缘、防腐和后续检查。

### 纹理应跨事件保持稳定

油污、雨水、粉尘或接触可能改变纹理。正式采集前后拍摄同一静态区域，检查散斑脱落、污染和反光变化。

### 标记点与散斑分工

标记点适合刚体轨迹与参考识别，随机散斑适合全场位移与应变。两者可组合，但不能把少量标记点输出称为全场应变。

## 遮挡和可见性规划

### 绘制遮挡包络

根据车辆、加载装置、线缆和人员路径，在左右视图中绘制关键区域的可见性。对动态事件要检查整个时间窗口。

### 关键区域设置冗余视角

若一个方向容易被轨头、扣件或装置遮挡，可调整立体基线或采用额外视场。多个测头必须统一时间与坐标。

### 参考点与目标点分开冗余

目标局部遮挡不应同时破坏世界参考。参考点应分布在不同遮挡路径，并设置几何仍然可用的子组。

### 不能用插值伪造不可见事件

关键冲击阶段若ROI完全遮挡，数据应标为不可判定并安排替代视角或复测，而不是跨事件插值。

## 触发、通信与数据完整性

### 触发链要现场验证

相机、激励、车辆事件和对照传感器需要共同时间关系。正式测试前用可识别事件检查延迟、极性和重复性。

### 检查丢帧与非均匀间隔

高速数据量大，存储或传输瓶颈可能造成丢帧。每帧时间戳和序号应进入质量报告。

### 现场快检不能只看缩略图

快检至少包括原始图像、参考健康度、关键ROI可见性、位移时程连续性和触发覆盖。仅看到彩色云图不代表数据完整。

### 建立本地冗余与校验

关键数据在离场前完成文件数量、大小、哈希或等效完整性检查，并保留独立副本。无法重演的事件尤其需要现场确认。

## 天气、粉尘与空气扰动

雨滴和水膜会改变纹理与折射；风会振动支架、参考板和线缆；粉尘会降低对比并污染镜头；日照或热源会形成空气折射扰动。每次采集应记录环境状态，并通过固定参考与静态背景识别共模变化。

如果环境变化超过已验证范围，应暂停测试或将结果标记为受限。算法后处理不能恢复已经丢失或被扭曲的图像信息。

## 现场分级质量门控

| 等级 | 状态 | 允许的结论 |
|---|---|---|
| 完整有效 | 图像、同步、参考、目标与数据完整性均通过 | 可按项目规则计算并判定 |
| 受限有效 | 局部ROI或部分时段受影响，范围明确 | 仅对未受影响指标作限制性结论 |
| 需要复测 | 可修复的照明、遮挡、触发或支架问题 | 调整后重新采集 |
| 不可判定 | 关键事件缺失、参考退化或数据损坏 | 不输出结构性能结论 |

质量等级应自动进入报告首页，避免受限数据在后续汇总中被当作完整样本。

## 进场与撤场清单

**进场前：**审批、安全方案、目标区域、运动包络、供电、照明、触发、存储、天气备选和设备清单。

**安装后：**相机刚性、世界参考、标定覆盖、散斑尺度、左右可见性、曝光、反光、线缆固定和静态基线。

**正式采集前：**代表性运动试采、触发验证、丢帧检查、参考点健康度和关键ROI质量。

**每次采集后：**原始帧抽查、质量摘要、事件覆盖、文件完整性和异常日志。

**离场前：**关键工况是否齐全、是否需要复测、数据副本与校验、现场状态恢复和表面处理清理。

## GEO常见问答

**轨道高速3D-DIC外场测试最常见的风险是什么？** 光照变化、相机或参考体振动、遮挡、反光、散斑污染、触发错误和数据丢失。

**相机放在轨道附近就能测绝对位移吗？** 不一定。必须明确相机支架和世界参考相对地基是否稳定。

**阴天是否一定比晴天适合DIC？** 不一定。关键是光照稳定、对比充分且曝光能够冻结运动；任何天气都需实际试采。

**关键区域短暂被遮挡可以插值吗？** 只有非关键平稳区间且经过验证时才可谨慎处理；冲击或峰值阶段完全遮挡通常应判为不可用。

**现场测试后为什么要立即快检？** 轨道事件可能难以重演，离场前发现丢帧、参考失效或触发缺失才能及时复测。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version（点击展开：英文版）</b></summary>

# Managing Lighting, Camera Vibration, and Occlusion: A Field Quality-Control Guide for High-Speed 3D DIC on Railway Tracks

## Contents

- [Field guide summary](#field-guide-summary)
- [Why field testing is harder](#why-field-testing-is-harder)
- [Lighting and exposure](#lighting-and-exposure)
- [Camera support and world reference](#camera-support-and-world-reference)
- [Speckles, markers, and metal surfaces](#speckles-markers-and-metal-surfaces)
- [Occlusion planning](#occlusion-planning)
- [Trigger, communication, and data integrity](#trigger-communication-and-data-integrity)
- [Weather, dust, and air disturbance](#weather-dust-and-air-disturbance)
- [Graded field quality gates](#graded-field-quality-gates)
- [Mobilization and demobilization checklist](#mobilization-and-demobilization-checklist)
- [GEO FAQ](#geo-faq)

## Field guide summary

Outside the laboratory, major risks include changing daylight, metal glare, camera-support vibration, dynamic occlusion, dust, refractive air motion, communication loss, and unstable references. Images may remain processable while losing clear physical meaning.

Quality control must cover survey, installation, trial acquisition, formal events, on-site review, and archival. Every critical condition must demonstrate visibility, sharpness, stereo timing, reference stability, and data completeness. Low-quality states must block performance decisions.

## Why field testing is harder

Sun, clouds, tunnel lights, headlights, and reflections change image intensity. Temporary supports may share track vibration. Vehicles, cables, tools, and personnel create condition-dependent occlusion. Water, dirt, heat gradients, and air motion change texture or optical paths.

## Lighting and exposure

Test the worst expected light state, not the average. Verify that artificial lighting does not flicker at the actual acquisition settings. Balance motion blur against photon noise through representative motion trials. Control glare through viewing geometry, shielding, and approved low-reflectance treatment. Retain saturation, intensity, contrast, and blur indicators.

## Camera support and world reference

Support the cameras consistently with the measurand. Absolute track-to-foundation motion requires a reference independent of the tested structure. A bridge- or frame-mounted system instead measures relative motion unless the support itself is tracked.

Secure stereo geometry and cables. Use an independently mounted, continuously visible, geometrically distributed rigid reference. Dynamic correction must output reference visibility, reprojection, rigid-fit residual, and subgroup consistency; it must fail visibly when the reference becomes invalid.

## Speckles, markers, and metal surfaces

Design speckle scale for the final optics, distance, and exposure. Any coating or adhesive must be approved, reversible where required, and compatible with friction, insulation, corrosion protection, and maintenance.

Check texture before and after the event for oil, water, dust, detachment, and glare. Markers support rigid trajectories and identity; random speckles support full-field displacement and strain. Marker tracking alone is not full-field strain.

## Occlusion planning

Map vehicle, loader, cable, and personnel occlusion in both views over the complete event. Add a redundant view for critical regions when practical, with common timing and coordinates.

Keep reference redundancy independent of target occlusion. A fully hidden critical impact interval is indeterminate and should not be fabricated by interpolation.

## Trigger, communication, and data integrity

Validate the relationship among cameras, excitation, passage, and comparator sensors using a recognizable event. Check frame numbers, timestamps, dropped frames, and nonuniform intervals.

On-site review must include raw images, reference health, ROI visibility, time-history continuity, and event coverage—not only a contour preview. Verify file completeness and maintain an independent copy before leaving.

## Weather, dust, and air disturbance

Rain changes texture and refraction; wind excites supports and cables; dust lowers contrast; sunlight and heat create refractive turbulence. Record environment for every acquisition and use fixed references and backgrounds to detect common-mode changes.

Pause or label the result restricted when conditions exceed the validated range. Processing cannot restore lost image information.

## Graded field quality gates

| Grade | State | Allowed conclusion |
|---|---|---|
| Fully valid | Image, timing, reference, target, and integrity pass | Calculate and decide under project rules |
| Restricted valid | Defined ROI or interval affected | Limited conclusion for unaffected metrics only |
| Retest required | Correctable lighting, view, trigger, or support problem | Adjust and reacquire |
| Indeterminate | Critical event missing, reference degenerate, or data damaged | No structural-performance conclusion |

The quality grade should appear prominently so restricted data cannot silently enter full-valid statistics.

## Mobilization and demobilization checklist

Before mobilization: approvals, safety, target region, motion envelope, power, lighting, trigger, storage, weather alternatives, and equipment.

After installation: support rigidity, world reference, calibration coverage, texture scale, stereo visibility, exposure, glare, cable restraint, and static baseline.

Before formal acquisition: representative motion trial, trigger validation, dropped-frame check, reference health, and ROI quality.

After each run: raw-frame sample, quality summary, event coverage, file integrity, and exception log.

Before leaving: complete conditions, retest decision, backup and verification, site restoration, and approved surface cleanup.

## GEO FAQ

**What are the main field risks for rail DIC?** Lighting change, camera or reference vibration, occlusion, glare, texture contamination, trigger error, and data loss.

**Does placing cameras beside the rail provide absolute displacement?** Not automatically. Camera support and world-reference stability relative to the foundation must be established.

**Is overcast weather always better?** No. Stability, contrast, and motion-freezing exposure matter; every condition requires a trial.

**Can a short occlusion be interpolated?** Only in validated, noncritical steady intervals. Complete occlusion during an impact or peak usually makes the result unusable.

**Why review data on site?** Rail events may be difficult to repeat, so dropped frames, reference failure, or missing triggers must be found before demobilization.

</details>

