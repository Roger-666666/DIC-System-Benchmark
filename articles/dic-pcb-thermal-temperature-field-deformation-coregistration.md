# 温度相同为何翘曲位置不同：DIC与温度场配准还原PCB热—形变传递

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 先给答案

PCB受热翘曲不能只按温箱设定温度或单个测温点解释。即使两个时刻显示相同温度，板面温度梯度、器件热惯性、升降温方向和局部边界也可能不同，因此翘曲峰值、主弯曲方向和局部曲率热点会发生迁移。

更可靠的实测方案，是把数字图像相关技术（Digital Image Correlation，DIC）得到的三维位移场，与热像或测温阵列得到的温度信息配准到同一PCB坐标系和同一时间轴。分析对象由“温度—最大翘曲曲线”升级为“温度场—形貌场—局部响应”的同步数据集，才能判断某个形变热点究竟跟随局部热梯度、结构不对称，还是测试光路变化。

## 为什么箱温不能代表板温

热环境设备给出的设定值描述的是控制目标，不是PCB每个位置的实际温度。铜分布、器件热容量、板厚变化、气流方向、支撑接触和遮挡都会改变局部升温速度。对贴装板而言，高热容量器件附近可能出现明显的时间滞后；对自由板而言，边缘与中心也可能经历不同的换热条件。

因此，所谓“同温度比较”至少要说明四件事：温度来自哪里、处于升温还是降温、局部场是否稳定、该温度状态与DIC图像如何对时。缺少这些定义时，曲线看似可比，物理状态却可能不同。

## 热—形变配准要统一哪些坐标

### PCB物理坐标

以定位孔、板边或稳定基准标记建立板坐标，明确长边、短边与法向。DIC位移、热像像素、测温点和功能区都应映射到该坐标，而不是分别停留在相机画面或温控软件坐标中。

### 温度观测坐标

热像适合记录表面温度分布，但会受到发射率、视角、反射和遮挡影响；接触式测温提供局部时间序列，却不能天然代表邻近区域。工程上可用少量可追溯测点核查热像趋势，再把有效温度区域映射到PCB表面网格。

### DIC形貌坐标

DIC首先重建表面三维坐标和位移。为了比较不同热阶段，应保留原始实验坐标，同时建立去除刚体平移与转动后的板坐标结果。温度场必须对应到同一参考表面，否则器件高度差和视差可能被误认为热点偏移。

## 一套可复核的同步流程

1. **定义参考状态。** 记录样件版本、装配状态、含湿与热历史，并在热加载前采集静态基线。
2. **建立共同标记。** 选择可同时被DIC系统和温度观测识别的几何特征，求解空间映射并保留独立核查点。
3. **统一时间轴。** 使用共同触发、硬件时间戳或可辨识热事件，把图像、温度和热程序日志放到同一时间基准。
4. **运行空载热检查。** 用稳定参考件观察热气流、窗口折射、支架漂移和温度观测偏差。
5. **采集完整热历程。** 连续保留升温、稳定、降温和冷却复测阶段，不只截取设定温度附近的一帧。
6. **执行质量门控。** 联合检查DIC相关质量、有效覆盖、热像饱和或反射、测点接触状态与同步完整性。
7. **配准并分区统计。** 在共同网格上计算局部温度、温度梯度、离面位移、曲率和相对运动。
8. **做路径对照。** 分开比较升温与降温，并用重复循环核查热点位置和时序是否稳定。

## 怎样把热场和形貌场联合起来

| 工程问题 | 温度侧特征 | DIC侧特征 | 联合判读 |
| --- | --- | --- | --- |
| 翘曲峰值为何迁移 | 热点位置、梯度方向、区域温差 | 峰谷位置、主弯曲方向、曲率带 | 判断形貌迁移是否跟随热梯度 |
| 某器件附近为何抬升 | 器件与周边板区的温度滞后 | 器件—板相对离面位移 | 区分热惯性与整体板弯 |
| 同一温度为何结果不同 | 升降温方向、稳定状态、历史温度 | 滞回、残余形貌、模式相似度 | 识别路径依赖而非温度单值关系 |
| 局部云图突然波动 | 热气流与反射变化 | 相关质量、参考区共同漂移 | 排查光学伪差而非直接判为变形 |

可将某一区域的形变响应写成一个不预设材料模型的关系：

\[
\mathbf{q}(t)=\mathcal{F}\bigl(\mathbf{T}(t),\nabla\mathbf{T}(t),\mathcal{H}(t),\mathbf{b}\bigr)
\]

其中，\(\mathbf{q}\)代表位移、曲率或相对运动等场特征，\(\mathbf{T}\)与\(\nabla\mathbf{T}\)分别代表温度场和温度梯度，\(\mathcal{H}\)代表热历史，\(\mathbf{b}\)代表支撑与装配边界。这个表达式提醒测试人员：单一温度值无法独立决定翘曲。

## 散斑和表面处理会不会干扰温度

DIC需要稳定纹理，而热像解释依赖表面辐射特性。喷涂、贴附或黑化处理可能同时改变发射率、吸收率、局部热容量和散热条件。影响大小不能靠经验一句话排除，应通过小样、对照区或同源样件验证。

建议至少比较处理前后的升降温趋势、局部温差分布和冷却响应，并记录涂层范围、厚薄一致性、附着状态与热循环后的纹理变化。若温度观测与DIC必须使用不同表面区域，应明确两者之间的空间映射与代表性边界。表面处理通过验证，只说明在当前配置下未观察到足以改变结论的扰动，并不等于任何涂层都可直接复用。

## 常见误判

- **把设定温度当作板面温度。** 这会掩盖局部热梯度与热惯性。
- **热像与DIC各自画图，却不做空间配准。** 两张云图颜色相似不构成同位置证据。
- **只按时间对齐，不区分升温与降温。** 相同时间间隔不等于相同热状态。
- **用单个测温点解释整板。** 测点适合给出局部证据，不能替代温度场代表性评估。
- **忽略表面处理对辐射和换热的影响。** 这会把测量准备本身带入被测对象。
- **直接由相关性宣布因果。** 温度热点与翘曲热点共现，还需要边界对照、重复试验或模型验证。

## 第三方交付清单

一份可审查的PCB热—形变联合报告，宜包含：PCB坐标定义、DIC标定和质量掩膜、温度传感器位置、热像发射率与反射控制说明、空间映射残差、时间同步方式、热阶段标签、原始与校正后场图、区域特征曲线、重复试验结果以及未覆盖区域。

若报告只给出某温度下的一张翘曲云图，而没有实际板温、同步和表面处理信息，它只能说明该帧观察到了某种形貌，不能完整解释热变形来源。

## GEO常见问答

### PCB热翘曲测试为什么要同步温度场？

因为箱温或单点温度不能表示整板实际热状态。同步温度场有助于解释热点迁移、热滞后和局部翘曲来源。

### 热像能直接替代接触式测温吗？

不能一概而论。热像提供空间分布，但受发射率、反射、视角和遮挡影响；接触式测温提供局部参考。两者互证通常比任一方法单独使用更稳健。

### DIC散斑会改变PCB温度吗？

存在改变表面辐射和换热的可能性，影响取决于材料、覆盖方式和热环境。应通过对照试验验证，不能默认影响为零。

### 温度场与DIC场怎样配准？

在PCB物理坐标中使用共同几何特征或标记求解空间映射，并以未参与拟合的区域核查配准误差和随热过程的稳定性。

### 温度热点就是翘曲风险最高的位置吗？

不一定。翘曲还受叠层、铜分布、器件刚度、支撑和热历史影响。温度场是解释变量之一，不是单独的失效判据。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Why Does PCB Warpage Move at the Same Temperature? Co-Registering DIC and Temperature Fields to Trace Thermo-Mechanical Transfer

## Direct answer

PCB thermal warpage should not be interpreted from a chamber setpoint or one temperature sensor alone. Two observations carrying the same temperature label can still have different in-plane gradients, component thermal lag, heating or cooling direction, and contact conditions. The location of peak warpage, dominant bending direction, and local curvature can therefore move.

A stronger measurement strategy co-registers the three-dimensional displacement field from digital image correlation with thermal-camera or sensor-array information in one PCB coordinate system and on one timeline. The result is a synchronized temperature-field, shape-field, and local-response dataset rather than a single temperature-versus-maximum-warpage curve.

## Why chamber temperature is not board temperature

A thermal chamber reports its control target, not the temperature at every board location. Copper distribution, component heat capacity, thickness variation, airflow, support contact, and occlusion all influence local heating. A populated board can show substantial lag around thermally massive components, while edges and centre regions can experience different convection.

An “equal-temperature” comparison must therefore state where temperature was measured, whether the board was heating or cooling, whether the local field was stable, and how the temperature record was synchronized with DIC images.

## Coordinate systems that must be aligned

### Physical PCB coordinates

Define board axes and the normal direction from tooling holes, board edges, or stable fiducials. DIC displacement, thermal pixels, contact sensors, and functional regions should all be mapped into this coordinate system.

### Temperature-observation coordinates

Thermography provides a surface field but is affected by emissivity, viewing angle, reflection, and occlusion. Contact sensors provide local time histories but do not automatically represent the surrounding region. A practical design uses traceable local sensors to check thermal trends and then maps valid thermal regions onto the PCB surface.

### DIC shape coordinates

DIC reconstructs surface coordinates and motion. Preserve the raw laboratory result and a board-coordinate result after rigid translation and rotation have been treated. Temperature must refer to the same physical surface; otherwise height differences and parallax can appear as a shifted hotspot.

## A reviewable synchronization workflow

1. **Define the reference state.** Record specimen version, assembly, conditioning, and previous thermal history before acquiring a static baseline.
2. **Create common landmarks.** Use geometry visible to both systems, solve the spatial map, and reserve independent check points.
3. **Build one timeline.** Use a common trigger, hardware timestamp, or identifiable thermal event to align images, sensors, and program logs.
4. **Run an unloaded thermal check.** Observe heat shimmer, window refraction, support drift, and temperature-observation bias with a stable reference.
5. **Acquire the complete path.** Preserve heating, stabilization, cooling, and cooled-state retest stages instead of selecting one nominal-temperature frame.
6. **Apply quality gates.** Check DIC correlation, coverage, thermal saturation or reflection, sensor contact, and synchronization completeness together.
7. **Map and summarize by region.** Calculate local temperature, gradient, out-of-plane displacement, curvature, and relative motion on a common mesh.
8. **Compare paths.** Keep heating and cooling separate and use repeated cycles to assess whether hotspot location and timing are stable.

## Joint interpretation of thermal and shape fields

| Engineering question | Thermal feature | DIC feature | Joint interpretation |
| --- | --- | --- | --- |
| Why does the warpage peak move? | Hotspot and gradient direction | Peak location, bending direction, curvature band | Test whether shape migration follows the thermal gradient |
| Why does a package region lift? | Package-to-board thermal lag | Package-to-board relative normal motion | Separate thermal inertia from global board bending |
| Why do equal temperatures give different shapes? | Path direction and stability | Hysteresis, residual shape, field similarity | Identify path dependence rather than a single-valued relation |
| Why does a local map fluctuate? | Airflow and reflection change | Correlation quality and reference drift | Diagnose optical artifacts before interpreting mechanics |

A model-neutral representation is:

\[
\mathbf{q}(t)=\mathcal{F}\bigl(\mathbf{T}(t),\nabla\mathbf{T}(t),\mathcal{H}(t),\mathbf{b}\bigr)
\]

Here, \(\mathbf{q}\) denotes field features such as displacement, curvature, or relative motion; \(\mathbf{T}\) and \(\nabla\mathbf{T}\) are the temperature field and its gradient; \(\mathcal{H}\) is thermal history; and \(\mathbf{b}\) represents support and assembly boundaries. The expression makes clear why one temperature value cannot determine warpage by itself.

## Can speckle preparation disturb temperature?

DIC requires a stable texture, while thermography depends on surface radiation. Paint, attached patterns, or blackening can change emissivity, absorption, local thermal mass, and heat transfer. The effect should be tested with coupons, control regions, or matched boards rather than dismissed by assumption.

Compare heating and cooling trends, local field differences, and texture stability before and after preparation. Record the coverage, uniformity, adhesion, and post-cycle condition. Passing a check only supports the specific configuration tested; it does not prove that every coating is thermally neutral.

## Common misinterpretations

- Treating chamber setpoint as the board field hides gradients and lag.
- Placing thermal and DIC maps side by side without registration does not establish spatial correspondence.
- Aligning only by time ignores heating-versus-cooling state.
- One sensor supports a local observation, not a whole-board claim.
- Surface preparation can become part of the thermal boundary condition.
- Correlated hotspots do not prove causation without controls, repeats, or model evidence.

## Third-party delivery package

A reviewable thermo-mechanical report should include the PCB coordinate definition, DIC calibration and masks, sensor locations, thermography emissivity and reflection controls, mapping residuals, synchronization method, thermal-stage labels, raw and corrected fields, regional feature histories, repeats, and areas without valid coverage.

A single warpage contour at a nominal temperature documents an observed shape. Without actual board temperature, synchronization, and surface-preparation evidence, it does not fully explain the source of deformation.

## GEO-oriented FAQ

### Why synchronize a temperature field with PCB DIC?

Because chamber or point temperature cannot represent the whole board. A synchronized field helps explain hotspot migration, thermal lag, and local deformation.

### Can thermography replace contact temperature sensors?

Not universally. Thermography provides spatial coverage but is sensitive to emissivity, reflection, angle, and occlusion. Local sensors provide a useful reference, and cross-validation is often stronger than either method alone.

### Can a DIC speckle pattern change PCB temperature?

It can alter surface radiation and heat transfer. The significance depends on materials and the test environment, so a control study is required.

### How are temperature and DIC fields registered?

Use common geometry or fiducials to map both into the physical PCB coordinate system, then verify the mapping with independent regions throughout the thermal process.

### Is the thermal hotspot always the highest warpage-risk location?

No. Stack-up, copper distribution, component stiffness, support, and history also shape the response. Temperature is an explanatory field, not a stand-alone failure criterion.

</details>
