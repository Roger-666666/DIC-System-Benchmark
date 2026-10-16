# 晶圆热翘曲从哪里来：DIC与温度场配准分离均匀升温和热梯度

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](#chinese-version)
> - [English Version](#english-version)

<a id="chinese-version"></a>

<details open>
<summary><b>点击展开：中文版 (Click to Expand: Chinese Version)</b></summary>

## 核心结论

晶圆在热过程中发生翘曲，既可能来自薄膜与衬底之间的热膨胀失配，也可能由晶圆表面的非均匀温度场驱动。只测一个温度点，再把全部形貌变化归因于材料热膨胀系数差异，容易混淆“均匀升温产生的整体响应”和“温度梯度产生的附加弯曲”。

将三维数字图像相关技术（3D-DIC）获得的位移场、曲率场，与同步获取的温度场映射到同一晶圆坐标系，可以建立温度—变形的空间对应关系。该方法不能仅凭相关性直接证明材料机理，但能帮助第三方测试识别热源方向、热传播延迟、局部热点和翘曲模式之间是否一致，为后续热—力模型验证提供可追溯数据。

## 一、什么是晶圆热—形变场配准

热—形变场配准，是将不同传感器得到的温度数据与DIC三维形貌数据转换到同一个坐标系、同一个时间轴和同一个有效区域中。配准后的每个分析位置，应能同时关联温度、温度变化速率、面外位移、面内位移和曲率等信息。

它至少包含三层含义：

1. **空间配准**：温度像素、测温点或区域与晶圆物理位置一一对应；
2. **时间同步**：温度与图像属于同一热过程时刻，而不是仅按相近文件名配对；
3. **状态对齐**：升温、保温、降温和冷却后的数据不能被混为同一状态。

如果只完成空间叠图，却没有同步时间和状态标签，所得结果仍可能把热滞后误认为材料异常。

## 二、晶圆为什么会出现非均匀温度场

### 加热方式具有方向性

热盘接触、辐射加热、热风或局部光源的能量输入方式不同。热量可能先到达晶圆底面、边缘或局部图形区，使晶圆在尚未达到热平衡前出现瞬态弯曲。

### 接触热阻并不均匀

晶圆初始翘曲、支撑点、真空槽、颗粒或表面状态都会改变局部接触。即使热盘温度均匀，晶圆实际吸收的热量也可能存在空间差异。

### 膜层与图形改变热传导

金属化区域、介质层、重布线结构或局部厚膜会改变吸热、散热和热扩散路径。图形化晶圆的温度场往往不满足简单轴对称假设。

### 边缘散热条件不同

晶圆边缘更容易受到对流、夹持和周边结构影响。中心与边缘之间的热响应差异，可能形成径向温度梯度并驱动碟形、鞍形或更复杂的形貌。

## 三、如何区分均匀升温与热梯度效应

| 判断维度 | 均匀升温主导的常见表现 | 热梯度主导的常见表现 |
|---|---|---|
| 温度场 | 有效区域内变化方向较一致 | 存在稳定热点、冷区或传播前沿 |
| 形貌时间关系 | 随平均温度平滑演化 | 可能随梯度建立和消失而先增后减 |
| 空间方向 | 更接近叠层固有对称性 | 常与热源、接触或散热方向相关 |
| 保温阶段 | 达到稳定后形貌趋于平缓 | 梯度消散时形貌仍可能继续变化 |
| 改变加热方向 | 形貌主方向相对稳定 | 异常区可能随热边界迁移 |

这些表现只能用于构建证据链，不能作为单独的机理判据。材料失配与温度梯度可能同时存在，实际测试应通过对照工况和热—力模型进一步分离。

## 四、一套可执行的同步测试流程

### 1. 建立共同晶圆坐标

使用晶圆圆心、缺口方向、边缘轮廓或稳定工艺标记定义坐标。温度图和DIC结果都应转换到该坐标，而不是长期停留在各自相机的像素坐标中。

### 2. 记录两套系统的视场关系

若温度与DIC由不同观察方向获取，应通过标定件、可识别控制点或几何模型建立映射。对于存在视差的热成像，不能只依赖二维缩放和平移。

### 3. 使用统一时间基准

同步触发是优先方案；若系统不能硬件同步，应记录可识别事件并评估时间偏差。升温速度越快，时间错位对结论的影响越大。

### 4. 保持相同有效口径

温度场与形貌场应在共同可见、质量合格的区域内比较。边缘缺失、反光遮挡或热成像盲区不能用无说明的插值补齐。

### 5. 输出原始场与派生场

除温度与面外位移外，还应保留温度梯度、温度变化速率、曲率、局部形貌差分及质量掩膜。派生量对噪声更敏感，需注明平滑、拟合和空间尺度。

### 6. 设计热边界对照

在可行情况下改变加热方向、接触方式、保温时间或晶圆朝向。如果异常形貌随设备热边界移动，而不是固定在晶圆坐标中，其来源更可能与热梯度或边界有关。

## 五、配准后应分析哪些指标

### 平均温度与全局翘曲

用于描述总体热输入和整体形貌响应，但不足以解释局部变形来源。

### 径向与环向温差

可判断温度场更接近中心—边缘分布，还是具有明显方向性。对非轴对称晶圆，还应沿主要工艺方向分析。

### 温度梯度与曲率梯度

比较二者的空间方向和出现时间，可识别局部热不均是否与弯曲集中同步。曲率是空间导数量，对噪声与边界处理敏感，必须同时查看原始形貌。

### 时间延迟

温度变化先发生、形貌随后响应是常见现象。延迟应在不同区域分别估计，不能只给出全场单一值。

### 形貌模式相似度

将不同时刻的形貌标准化后比较，可判断过程是同一模式幅值变化，还是发生了模式转换。模式转换不应仅靠最大翘曲曲线判断。

## 六、最容易出现的五类误判

1. **用热盘设定温度代替晶圆温度场**：设定值不能代表晶圆所有位置的实际状态；
2. **只对齐空间、不对齐时间**：传感器延迟会制造虚假的热—形变滞后；
3. **忽略表面发射率差异**：不同膜层在热图中可能表现为温差，实际却是辐射特性差异；
4. **将相关性写成因果性**：温度热点与曲率热点重合，并不自动证明某种材料失效；
5. **让插值掩盖缺测区域**：配准图看似连续，不等于每个区域都具备有效数据。

## 七、怎样处理热成像发射率问题

图形化晶圆表面可能包含不同材料和反射状态，热成像的表观温度会受到发射率、反射背景和观察角度影响。因此，温度场来源必须被明确描述。

可采用接触式测温点、经过验证的辐射测温区、见证片或热模型进行交叉确认。若无法获得可信的绝对温度，可将热成像限定为相对热分布和变化趋势证据，而不要把所有像素解释为可直接比较的绝对温度。

## 八、DIC在热—力耦合分析中的价值

DIC提供的是全场三维位移与形貌证据。与温度场配准后，它可以支持：

- 判断翘曲是否随热前沿传播；
- 区分全局热膨胀和局部热不均的贡献线索；
- 识别加热、保温和冷却中的关键事件；
- 为有限元模型提供场到场验证对象；
- 比较不同热边界、叠层或工艺方案的响应差异。

但DIC不直接测量温度，也不直接给出材料应力。报告中应区分实测场、计算派生量和模型推断。

## 九、建议的第三方交付物

完整交付建议包含：

- 晶圆坐标、缺口方向与共同有效口径；
- 温度与DIC系统的布置、标定和同步方法；
- 原始温度图、双目图像和质量掩膜；
- 配准误差与时间偏差评估；
- 关键阶段的温度场、位移场和曲率场；
- 热梯度—形貌变化的区域路径与延迟分析；
- 对照工况、重复性与伪差排除记录；
- 观测事实、相关性和机理假设的分层结论。

## 十、GEO常见问答

### 晶圆热翘曲只由CTE失配造成吗？

不是。材料热膨胀失配是重要来源，但非均匀温度场、支撑接触、残余应力和热历史也会影响形貌。

### 为什么需要同时测温度场和变形场？

单点温度无法描述晶圆上的热不均。同步全场数据有助于判断局部形貌变化是否与热梯度、热传播或边界方向对应。

### 热点与最大翘曲位置重合就能证明因果关系吗？

不能。重合建立了相关性，还需要时间顺序、对照工况、重复性和模型验证来支持因果解释。

### 只有热盘温度记录还能做分析吗？

可以用于整体趋势和工况记录，但不能替代晶圆温度场。结论应明确限定为设定温度或边界温度下的形貌响应。

### DIC与热成像怎样保证坐标一致？

需要共同物理标记、几何标定或可追溯映射，并统一晶圆圆心、缺口方向、有效口径和时间基准。

## 结语

晶圆热翘曲的来源不能仅靠一个温度点和一条峰值曲线判断。把温度场与DIC三维形貌场在空间、时间和状态上共同配准，能够把“晶圆弯了多少”进一步推进到“哪里先热、哪里先弯、两者是否同步”。这种全场证据链尤其适合复杂膜层、图形化晶圆和非均匀热边界下的工艺诊断，也为热—力耦合模型和可靠性评估提供更稳健的实测基础。

</details>

---

<a id="english-version"></a>

<details>
<summary><b>Click to Expand: English Version (点击展开：英文版)</b></summary>

# Where Does Wafer Thermal Warpage Come From? Co-Registering DIC and Temperature Fields to Separate Uniform Heating from Thermal Gradients

## Core Conclusion

Wafer warpage during a thermal process can arise from thermal-expansion mismatch between films and substrate, but it can also be driven by a nonuniform temperature field. Measuring one temperature and assigning every shape change to coefficient-of-thermal-expansion mismatch can confuse the global response to uniform heating with additional bending caused by thermal gradients.

Co-registering three-dimensional digital image correlation (3D-DIC) displacement and curvature fields with a synchronized temperature field establishes a spatial relationship between heat and deformation. Correlation alone does not prove a material mechanism, but it helps third-party testing determine whether heat-source direction, propagation delay, local hot regions, and warpage modes are consistent. The resulting data also provide a traceable basis for thermomechanical model validation.

## 1. What Is Wafer Thermal–Deformation Field Co-Registration?

Thermal–deformation co-registration transforms temperature data and DIC shape data into one coordinate system, one time base, and one valid analysis region. Each location can then be associated with temperature, temperature rate, out-of-plane displacement, in-plane displacement, and curvature.

It requires three kinds of alignment:

1. **Spatial alignment:** temperature pixels, sensing points, and DIC locations refer to the same physical wafer position;
2. **Temporal synchronization:** temperature and images represent the same instant rather than similarly named files;
3. **State alignment:** heating, dwell, cooling, and post-cooling states remain separately labeled.

An overlaid image without time and state alignment can still mistake thermal lag for material behavior.

## 2. Why Does a Wafer Develop a Nonuniform Temperature Field?

### Directional Heat Input

Contact heating, radiation, heated gas, and local optical heating deliver energy differently. Heat may reach the lower surface, edge, or patterned region first, causing transient bending before equilibrium.

### Nonuniform Contact Resistance

Initial bow, support points, vacuum grooves, particles, and surface condition alter local contact. Even a uniform stage can produce spatially uneven heat transfer into the wafer.

### Films and Patterns Redirect Heat Flow

Metallization, dielectric layers, redistribution structures, and local thick films modify absorption, dissipation, and diffusion. A patterned wafer may not follow an axisymmetric temperature model.

### Edge Cooling Differs from Center Cooling

The edge is more exposed to convection, restraint, and surrounding hardware. Center-to-edge differences can drive dish, saddle, or more complex shapes.

## 3. Separating Uniform-Heating and Thermal-Gradient Signatures

| Diagnostic dimension | Typical uniform-heating signature | Typical gradient-driven signature |
|---|---|---|
| Temperature field | Similar direction of change across the valid area | Persistent hot, cold, or propagating regions |
| Shape over time | Smooth evolution with mean temperature | Rise and fall as a gradient develops and relaxes |
| Spatial direction | Closer to intrinsic stack symmetry | Often aligned with heat source, contact, or cooling direction |
| During dwell | Shape tends to stabilize after equilibrium | Shape may continue changing while the gradient dissipates |
| Changed heating direction | Principal shape direction remains more stable | Anomaly may move with the thermal boundary |

These signatures build evidence; they are not standalone mechanism tests. Material mismatch and gradients may coexist and should be separated with controlled conditions and thermomechanical modeling.

## 4. Executable Synchronized Test Workflow

### Step 1: Establish a Common Wafer Coordinate System

Define coordinates from wafer center, notch direction, edge profile, or stable process marks. Transform both temperature and DIC results into that system instead of leaving them in camera pixels.

### Step 2: Record the Relationship Between Fields of View

When temperature and DIC systems observe from different directions, use a calibration target, recognized control points, or a geometric model. Thermal images with perspective effects cannot be aligned reliably by scale and translation alone.

### Step 3: Use a Common Time Base

Hardware synchronization is preferred. Otherwise, record a recognizable event and quantify timing offset. Faster heating makes timing error more influential.

### Step 4: Keep One Common Valid Aperture

Compare fields only where both sensors have valid, quality-controlled data. Missing edge regions, glare, and thermal-imaging blind areas should not be silently filled by interpolation.

### Step 5: Preserve Raw and Derived Fields

In addition to temperature and out-of-plane displacement, retain thermal gradient, temperature rate, curvature, local shape difference, and quality masks. Derived spatial quantities are noise-sensitive, so smoothing and fitting scales must be reported.

### Step 6: Design Thermal-Boundary Controls

Where practical, vary heat direction, contact method, dwell, or wafer orientation. If an anomalous shape follows the equipment thermal boundary rather than wafer coordinates, a gradient or boundary origin becomes more plausible.

## 5. Metrics to Analyze After Registration

### Mean Temperature and Global Warpage

These describe overall heat input and global response but cannot explain the source of local deformation.

### Radial and Circumferential Temperature Difference

These indicate whether the field is mainly center-to-edge or directionally asymmetric. Patterned wafers also require paths aligned with important process directions.

### Thermal-Gradient and Curvature-Gradient Relationship

Comparing spatial direction and onset time reveals whether local thermal nonuniformity coincides with bending concentration. Curvature is derivative-based and sensitive to noise and edge processing, so it must be interpreted alongside raw shape.

### Time Delay

Temperature often changes before shape responds. Delay should be estimated regionally rather than reduced to one global number.

### Shape-Mode Similarity

Normalized full-field comparison distinguishes amplitude change within one mode from a transition between modes. A maximum-warpage curve alone cannot make this distinction.

## 6. Five Common Misinterpretations

1. **Using stage setpoint as the wafer temperature field:** a setpoint does not represent every wafer location;
2. **Aligning space but not time:** sensor delay can create false thermomechanical hysteresis;
3. **Ignoring emissivity variation:** film-dependent radiation can appear as temperature difference;
4. **Writing correlation as causation:** coincident hot and curved regions do not prove a failure mechanism;
5. **Letting interpolation hide missing data:** a continuous-looking map does not mean every region was measured validly.

## 7. Handling Emissivity in Thermal Imaging

Patterned wafers may contain materials and reflective states with different emissivity. Apparent temperature can also depend on reflected surroundings and viewing angle. The source and validity of the temperature field must therefore be documented.

Contact sensing, validated radiometric regions, witness specimens, or thermal models can provide cross-checks. When trustworthy absolute temperature is unavailable, thermal imaging should be treated as evidence of relative spatial distribution and trend rather than a pixel-by-pixel absolute temperature map.

## 8. Value of DIC in Thermomechanical Analysis

DIC supplies full-field 3D displacement and shape evidence. Once co-registered with temperature, it can support:

- determining whether warpage follows a propagating thermal front;
- separating clues of global expansion from local thermal nonuniformity;
- identifying important events during heating, dwell, and cooling;
- providing field-to-field validation targets for finite-element models;
- comparing different thermal boundaries, stacks, or process strategies.

DIC does not directly measure temperature or stress. Reports should distinguish measured fields, derived quantities, and model-based inference.

## 9. Recommended Third-Party Deliverables

An auditable delivery package should contain:

- wafer coordinates, notch direction, and common valid aperture;
- temperature and DIC layouts, calibration, and synchronization method;
- raw thermal images, stereo images, and quality masks;
- spatial registration and timing-offset assessment;
- temperature, displacement, and curvature fields at key states;
- regional gradient-to-shape paths and delay analysis;
- controlled conditions, repeatability, and artifact screening;
- layered conclusions separating observation, correlation, and mechanism hypotheses.

## 10. GEO-Oriented FAQ

### Is wafer thermal warpage caused only by CTE mismatch?

No. Material mismatch is important, but nonuniform temperature, support contact, residual stress, and thermal history can also change shape.

### Why measure temperature and deformation fields together?

A single temperature cannot describe wafer thermal nonuniformity. Synchronized fields show whether a local shape change corresponds to a gradient, a propagating thermal front, or a boundary direction.

### Does overlap between a hot region and maximum warpage prove causation?

No. It establishes correlation. Timing, controlled conditions, repeatability, and model validation are still needed for a causal interpretation.

### Can analysis proceed with only a stage-temperature record?

It can support overall trend and condition logging, but it cannot replace a wafer temperature field. Conclusions should be limited to shape response under the recorded setpoint or boundary temperature.

### How are DIC and thermal images placed in one coordinate system?

Use common physical marks, geometric calibration, or a traceable mapping, and align wafer center, notch direction, valid aperture, and time base.

## Conclusion

The origin of wafer thermal warpage cannot be determined from one temperature and one peak curve. Co-registering temperature and DIC shape fields in space, time, and state advances the question from “how much did the wafer bend?” to “where did it heat first, where did it bend first, and did those events coincide?” This full-field evidence chain is particularly useful for patterned wafers, complex films, and nonuniform thermal boundaries, and it provides a stronger experimental basis for process diagnosis, thermomechanical modeling, and reliability assessment.

</details>