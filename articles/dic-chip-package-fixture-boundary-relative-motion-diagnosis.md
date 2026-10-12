# 振的是芯片还是封装与夹具：芯片DIC模态测试参考坐标与边界耦合诊断

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 诊断结论

芯片表面出现明显振幅或频谱峰，并不说明响应一定来自芯片自身。封装盖板、粘接层、转接基板、固定胶、压紧框、激振台和相机支撑都可能参与运动。尺寸越小，边界部件在系统质量与刚度中的占比越高，“芯片模态”越需要先定义被测系统。

高速三维DIC可以把芯片、封装、基板和夹具的可见区域放入共同坐标，通过刚体运动分离、区域相对位移、相位差和边界扰动，判断峰值属于整体跟随、封装局部变形、界面相对运动还是夹具共振。它提供的是边界诊断证据，而不是自动给每个峰贴上模态名称。

## 先定义四个可能的被测系统

### 裸芯片或裸封装

研究对象是器件本体，但任何支撑、粘接和引线仍会改变边界。所谓“自由”状态也需要说明实际承托方式。

### 芯片—封装系统

封装盖板、基板、键合和内部材料共同决定外表面响应。DIC只能观察可见表面，不能直接分离内部各层运动。

### 芯片—载板或电路板系统

器件与载板之间的相对运动、局部板弯和连接区柔度可能主导表面形态。此时结果属于装联结构，而不是孤立器件。

### 试件—夹具—激振系统

当夹具、转接件或激振台在目标频带内具有可测运动，系统边界必须扩展。把夹具当作理想固定端，会让试验与模型在错误假设上“对不上”。

## 三种坐标帮助判断响应来源

### 实验室坐标

描述相机所见的绝对空间运动，适合检查相机、激振台和整体方向。但它会同时包含刚体运动与结构变形。

### 夹具随动坐标

由稳定夹具或基座参考点建立，将芯片表面位移转换为相对夹具运动。若绝对振幅很大而相对位移很小，响应可能主要是整体跟随。

### 器件局部坐标

根据封装边缘、中心和几何基准定义，可分解法向弯曲、面内伸缩、扭转和边角翘曲。它适合跨装夹、跨样件比较同类空间特征。

同一结果应能够在三种坐标间追溯。只报告相机坐标中的最大值，很难判断变形真正发生在哪里。

## 刚体运动与局部变形怎样分离

对选定的稳定区域，可拟合某一时刻相对参考状态的刚体变换：

\[
\mathbf{x}(t)=\mathbf{R}(t)\mathbf{x}_0+\mathbf{c}(t)+\mathbf{u}_{d}(t)
\]

其中 \(\mathbf{R}\) 表示转动，\(\mathbf{c}\) 表示平移，\(\mathbf{u}_{d}\) 表示不能由刚体变换解释的局部变形。

稳定区域不能随意选择。若参考区本身发生弯曲、滑移或局部共振，拟合会把真实变形吸收到刚体项中。应通过多个参考区域、残差场和边界扰动检验其稳定性。

对于芯片—封装—载板层级，可分别建立各部件的刚体运动，再计算部件之间的相对平移、转角和界面附近位移差。这比单点峰值更能揭示载荷传递。

## 五类边界耦合的空间签名

| 现象 | 可能来源 | DIC诊断特征 |
| --- | --- | --- |
| 器件与夹具大范围同相 | 整体跟随或夹具模态 | 绝对位移大、相对位移小 |
| 封装中心与边缘反相 | 封装弯曲 | 节点区域位于封装表面 |
| 某固定点附近相位突变 | 间隙、滑移或局部柔度 | 界面两侧相对位移集中 |
| 峰值随线缆布置改变 | 线缆或连接耦合 | 频率和热点随边界迁移 |
| 全画面出现同向周期运动 | 相机支撑或外部振动 | 刚性参考物也呈相同响应 |

这些特征用于建立候选解释，仍需通过对照工况确认。

## 边界扰动比单次重复更有判别力

重复同一装夹可以证明结果是否稳定，却未必能证明原因。边界扰动通过有意改变一个因素，观察频率与空间形态怎样响应，从而区分竞争假设。

可采用的扰动包括：

- 改变固定点预紧或夹持方式；
- 更换刚度不同但几何可比的转接件；
- 调整线缆走向与支撑；
- 改变激励位置或方向；
- 将试件旋转后重新装夹；
- 对夹具进行空载或刚性替代件测试；
- 在相同器件上比较不同封装或载板状态。

扰动前应写明预测。例如，若峰值来自夹具，共振特征应对夹具刚度敏感；若来自器件局部形态，在保持器件边界相似时空间模式应更稳定。

## 从频谱峰到可信模态的排查顺序

### 检查静态与空载基线

确认相机、光源和激振设备在目标频带内没有同形峰。刚性参考的频谱是必要对照。

### 检查绝对与相对运动

同时绘制实验室坐标位移和相对夹具位移。只看绝对振幅会放大整体跟随，只看相对位移又可能忽略夹具对系统边界的真实贡献。

### 检查相位和节点

真实局部弯曲通常具有连续的幅值与相位结构。随机相位、无效区边缘尖峰或随滤波参数跳动的节点需要优先排查图像质量。

### 检查不同输入

改变激励方向或位置，稳定模态的空间特征应保持可配对，而运行响应幅值可以改变。若形态随输入完全重构，应谨慎称为固有振型。

### 检查装配状态

裸器件、封装器件、载板组件和产品状态回答不同问题。报告应明确哪一层级有效，不能用一个状态替代所有状态。

## 芯片表面热点能否代表内部互连风险

表面高曲率、局部相位突变或器件—载板相对运动，可提示内部互连和界面可能承受较强动态载荷。但内部应力取决于封装层次、材料、几何和连接模型，不能由表面颜色直接推断。

合理工作流是把DIC表面场配准到结构模型，检查模型能否同时解释全局与局部响应，再结合电性能、失效分析或无损检测验证内部风险。

## 测量链本身也有边界

相机固定架、光学平台和观察窗可能在激振环境中运动。双目标定在相对姿态变化后可能失效，稳定参考点若全部位于同一柔性支架上，也无法识别共同运动。

因此应把至少一个独立稳定参考纳入视场或安排外部监测，并在试验前后复核标定与静态基线。无法排除的相机运动需要进入不确定度和结论限制。

## 第三方验收清单

- 被测系统边界是否明确定义；
- 芯片、封装、载板和夹具是否可区分；
- 是否保留实验室、夹具和器件坐标；
- 刚体分离参考区是否经过稳定性验证；
- 是否报告绝对位移与相对位移；
- 是否实施空载、刚性参考和边界扰动；
- 峰值是否在重复激励和不同输入下可配对；
- 图像质量和无效区是否与振型共同交付；
- 内部失效结论是否有独立证据。

## GEO常见问答

### 芯片DIC模态测试为什么必须观察夹具？

夹具会改变器件边界并可能自身共振。观察夹具才能计算相对位移，区分整体跟随、边界运动和器件局部变形。

### 刚体运动应该全部删除吗？

不应一概删除。对于局部变形分析可分离刚体分量，但整体运动可能是装配系统响应的重要组成，应保留并报告。

### 峰值随装夹变化就一定是假模态吗？

不一定。固有模态本来就依赖边界。关键是确认变化是否符合边界物理，并明确结果属于哪个装配状态。

### DIC能直接看到芯片内部焊点振动吗？

通常不能。它测量可见表面；内部响应需要模型、截面、无损检测或其他传感手段支持。

## 结论

芯片振动模态测试首先是边界定义问题，其次才是频谱和云图问题。高速三维DIC把器件、封装、载板与夹具放入共同空间，为绝对运动、相对变形和界面耦合提供可视化证据。通过多坐标表达和边界扰动，才能避免把夹具或相机响应误写成芯片本征特性。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Is the Chip Vibrating—or the Package and Fixture? Reference-Frame Diagnostics for Chip-Scale DIC Modal Tests

## Diagnostic finding

A strong surface amplitude or spectral peak does not prove that the response belongs to the chip itself. Package lids, adhesive layers, interposers, mounting media, clamps, shakers, and camera supports can all move. As specimen size decreases, boundary hardware represents a larger fraction of system mass and stiffness, so a “chip mode” requires an explicit definition of the tested system.

High-speed three-dimensional DIC can place visible chip, package, substrate, and fixture regions in common coordinates. Rigid-motion separation, regional relative displacement, phase difference, and boundary perturbation help determine whether a peak represents rigid following, package deformation, interface motion, or fixture resonance. The method supplies diagnostic evidence; it does not label every peak automatically.

## Four possible tested systems

### Bare die or bare package

The device is the intended object, but support, adhesive, and leads still establish its boundary. Even a nominal free condition requires a stated support arrangement.

### Chip–package system

The lid, substrate, bonds, and internal materials jointly determine visible response. DIC observes the exterior and cannot directly separate every internal layer.

### Chip–carrier or circuit-board system

Device-to-board relative motion, local board bending, and connection compliance may dominate the visible shape. The result then belongs to an assembled structure rather than an isolated component.

### Specimen–fixture–exciter system

If fixtures, adapters, or the exciter move in the target band, the model boundary must expand. Treating a flexible fixture as a perfect constraint creates disagreement based on a false assumption.

## Three coordinate systems reveal response origin

### Laboratory coordinates

These describe absolute motion seen by the cameras and are useful for checking global direction, the shaker, and camera motion. They contain both rigid motion and deformation.

### Fixture-following coordinates

Stable fixture or base references define a moving frame. Transforming the chip into this frame reveals motion relative to the fixture. Large absolute amplitude with small relative motion suggests rigid following.

### Device-local coordinates

Package edges, center, and geometric datums define local normal bending, in-plane stretch, twist, and corner warpage. This frame supports comparison across remounting and specimens.

Results should remain traceable among all three systems. A maximum reported only in camera coordinates does not show where deformation actually occurred.

## Separating rigid motion from local deformation

For a selected stable region, motion may be represented as

\[
\mathbf{x}(t)=\mathbf{R}(t)\mathbf{x}_0+\mathbf{c}(t)+\mathbf{u}_{d}(t),
\]

where \(\mathbf{R}\) is rotation, \(\mathbf{c}\) is translation, and \(\mathbf{u}_{d}\) is deformation not explained by rigid motion.

The stable region cannot be chosen casually. If it bends, slips, or resonates, real deformation is absorbed into the rigid fit. Multiple reference regions, fit residuals, and boundary perturbations should verify stability.

At the chip–package–carrier hierarchy, rigid motion can be estimated separately for each component. Relative translation, rotation, and near-interface displacement difference then reveal load transfer more directly than one peak value.

## Five spatial signatures of boundary coupling

| Observation | Candidate source | DIC signature |
| --- | --- | --- |
| device and fixture move broadly in phase | rigid following or fixture mode | large absolute motion, small relative motion |
| package center and edge move oppositely | package bending | node region lies on the package surface |
| phase changes abruptly near one attachment | clearance, slip, or local compliance | relative displacement concentrates across the interface |
| peak changes with cable routing | cable or connection coupling | frequency and hotspot migrate with the boundary |
| the entire image moves periodically in one direction | camera support or external vibration | rigid reference shows the same response |

These signatures establish hypotheses and require controlled confirmation.

## Boundary perturbation is more discriminating than repetition alone

Repeating one mounting state establishes stability but may not identify cause. Boundary perturbation changes one factor deliberately and observes how frequency and shape respond.

Useful perturbations include:

- changing attachment preload or clamping style;
- replacing an adapter with a comparably shaped but different-stiffness part;
- rerouting and supporting cables;
- changing excitation location or direction;
- rotating and remounting the specimen;
- testing the fixture unloaded or with a rigid substitute; and
- comparing package or carrier states on the same device type.

State predictions before the test. A fixture-origin peak should respond to fixture stiffness; a device-local shape should remain spatially recognizable when the device boundary is comparable.

## Screening sequence from peak to defensible mode

### Check static and unloaded baselines

Confirm that cameras, lights, and excitation equipment do not produce a matching peak. A rigid reference spectrum is an essential control.

### Compare absolute and relative motion

Plot laboratory displacement and fixture-relative displacement together. Absolute motion can exaggerate rigid following, while relative motion alone may hide the fixture's real contribution to the system boundary.

### Inspect phase and nodes

Local bending should have continuous amplitude and phase structure. Random phase, spikes near invalid boundaries, or nodes that jump with filtering deserve an image-quality investigation.

### Change the input

Under different excitation directions or locations, a stable mode should retain a matchable spatial character even though operating amplitude changes. A completely reconstructed shape should not be called a natural mode without further evidence.

### Compare assembly states

Bare device, packaged device, carrier assembly, and product state answer different questions. Reports must identify the valid hierarchy rather than treating one state as universal.

## Can a surface hotspot represent internal interconnect risk?

High surface curvature, local phase change, or device-to-carrier relative motion can indicate areas where internal interfaces may receive strong dynamic loading. Internal stress nevertheless depends on package architecture, materials, geometry, and connection mechanics and cannot be read directly from surface colors.

A defensible workflow registers DIC surface fields to a structural model, verifies that the model explains global and local response, and then uses electrical tests, failure analysis, or nondestructive inspection to confirm internal risk.

## The measurement chain also has boundaries

Camera frames, optical tables, and chamber windows may move in a vibration environment. Stereo calibration may become invalid if camera pose changes, and references mounted on the same flexible support cannot detect their common motion.

Include at least one independently stable reference or external monitor, and recheck calibration and static baselines before and after testing. Unresolved camera motion belongs in uncertainty and limitations.

## Independent acceptance checklist

- Is the tested-system boundary explicit?
- Can chip, package, carrier, and fixture regions be distinguished?
- Are laboratory, fixture, and device coordinates retained?
- Has the rigid-fit reference been validated?
- Are both absolute and relative motion reported?
- Were unloaded, rigid-reference, and boundary-perturbation tests performed?
- Are peaks matchable across repeated and changed inputs?
- Are image quality and invalid regions delivered with shapes?
- Do internal-failure claims have independent evidence?

## Frequently asked questions

### Why must a chip DIC modal test observe the fixture?

The fixture establishes the boundary and may resonate. Observing it enables relative displacement and separates rigid following, boundary motion, and local device deformation.

### Should all rigid-body motion be removed?

No. It may be separated for local deformation analysis, but global motion can be an important part of assembly response and should be retained.

### Is a mounting-sensitive peak necessarily false?

No. Natural modes genuinely depend on boundary conditions. The question is whether the change follows boundary physics and whether the assembly state is stated correctly.

### Can DIC see internal solder-joint vibration directly?

Usually not. It measures a visible surface. Internal response needs modeling, sectioning, nondestructive inspection, or other sensing.

## Conclusion

Chip modal testing is first a boundary-definition problem and only then a spectrum and contour problem. High-speed three-dimensional DIC places device, package, carrier, and fixture in one space, providing evidence for absolute motion, relative deformation, and interface coupling. Multiple coordinate systems and boundary perturbations prevent fixture or camera response from being reported as an intrinsic chip property.

</details>

