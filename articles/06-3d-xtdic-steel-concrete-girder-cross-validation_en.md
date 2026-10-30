# Cross-Validating 3D-XTDIC, Displacement Sensors, and Finite Element Analysis on a Scaled Steel–Concrete Girder

> **Abstract:** Staged static tests on a scaled steel–concrete main girder require different forms of evidence. Displacement sensors provide point histories, 3D-XTDIC resolves surface displacement and strain fields, and finite element analysis supplies mechanics-based predictions. This article presents a cross-validation framework based on common coordinates, time references, load stages, and spatial scales. It covers point, section, and regional comparisons, residual analysis, uncertainty, boundary and material updates, and the limits of surface measurements. The purpose is not to rank methods, but to build a traceable interpretation that can support later engineering translation.

> **Keywords:** 3D-XTDIC; digital image correlation; steel–concrete girder; scaled model; full-field strain measurement; finite element cross-validation

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](06-3d-xtdic-steel-concrete-girder-cross-validation_zh.md)
> - [English Version](06-3d-xtdic-steel-concrete-girder-cross-validation_en.md)

## Contents

- [1. Three methods, three questions](#1-three-methods-three-questions)
- [2. Establish a common basis for comparison](#2-establish-a-common-basis-for-comparison)
- [3. A cross-validation workflow from points to regions](#3-a-cross-validation-workflow-from-points-to-regions)
- [4. Use residuals and uncertainty diagnostically](#4-use-residuals-and-uncertainty-diagnostically)
- [5. Respect the limits of contour maps](#5-respect-the-limits-of-contour-maps)
- [6. From model validation to engineering translation](#6-from-model-validation-to-engineering-translation)
- [FAQ](#faq)

## 1. Three methods, three questions

The test context is a scaled steel–concrete main girder for a combined road-and-rail bridge, subjected to staged static loading to reproduce the girder's loading state. During loading, full-field DIC contour maps present the distribution of deformation and strain and help locate strain-concentration zones. That spatial view is valuable, but it is only one part of the evidence required to interpret the test.

A displacement sensor answers a temporal question at a fixed location: how does a selected displacement component change as load is applied, held, and removed? 3D-XTDIC uses stereo images and digital image correlation to measure surface displacement and calculate strain fields. It addresses a spatial question: where do gradients develop, and how do concentrated regions relate to their surroundings? A finite element model answers a predictive question under stated assumptions: how should load be transferred through the specified geometry, materials, connections, and restraints?

These roles are complementary. A sensor cannot reconstruct the response between its installation points. A full-field map does not independently establish the material law or internal load path. A finite element calculation is not an observation, even when its output is displayed on the same geometry. Cross-validation therefore means testing whether different forms of evidence support a common mechanical interpretation, not replacing one method with another.

| Method | Information supplied | Primary question | Important limitation |
| --- | --- | --- | --- |
| Displacement sensor | Time history at a fixed point and in a defined direction | When and how does this point move? | Sparse coverage; mounting direction and support movement affect readings |
| 3D-XTDIC | Surface 3D displacement and calculated strain fields | How is response distributed, and where is it concentrated? | Calibration, image quality, occlusion, and surface representation affect results |
| Finite element analysis | Calculated response under explicit assumptions | What load path and parameter sensitivity are expected? | Geometry, materials, connections, and restraints idealize the test |

## 2. Establish a common basis for comparison

Many apparent disagreements are comparison errors rather than mechanical discrepancies. The first task is to establish one coordinate convention. Global directions, girder-local axes, sensor polarity, and DIC displacement components must be documented. The location of every sensor should be mapped to the corresponding finite element nodes or elements. A sensor measuring along one axis cannot be compared directly with a full-field component along another axis simply because both are expressed as displacement.

The second task is temporal alignment. Staged static loading provides a natural common index: start of loading, end of each load increment, holding period, and unloading. Camera frames, sensor samples, and numerical load steps may use different time origins, so event markers and test logs are needed. Readings taken during an increment should not be mixed with readings after stabilization unless that difference is explicitly part of the analysis.

Spatial representation must also be aligned. A point comparison concerns the same location and displacement direction. A section comparison uses the same cross-section or longitudinal slice. A regional comparison applies a defined averaging window, line, or area to each dataset. A finite element nodal value, a DIC subset-based estimate, and a sensor reading do not necessarily represent the same physical neighborhood. Documenting interpolation and smoothing is therefore part of the comparison, not a post-processing detail.

## 3. A cross-validation workflow from points to regions

### Step 1: Freeze the reference state

Before comparing results, record the initial geometry, restraints, loading sequence, material-parameter sources, and measurement zeros. Generate numerical load steps that correspond to the actual stages. If a restraint or loading fixture changes during the test, that change defines a new state and should be reflected in the model. Continuing to use the original setup would mix different mechanical problems.

### Step 2: Compare point histories

Extract the DIC displacement at each sensor location and project it onto the sensor direction. A small averaging area may be used when it better represents the sensor contact or reduces local image noise, but its size should remain explicit. Compare zero drift, direction of motion, and increments at each load stage rather than relying on a single final reading.

If a sensor history is continuous while the local DIC result changes abruptly, inspect occlusion, correlation quality, speckle condition, and camera images first. If the two measurements provide similar point evidence while the finite element result departs from both, the next priority is to examine model assumptions. This sequence prevents a measurement artifact from being absorbed into a material parameter.

### Step 3: Compare sections and regions

Place the three datasets on the same section at the same load stage. Examine whether concentrated strain, displacement gradients, and the inferred load-transfer path have a consistent spatial explanation. DIC can identify locations that warrant closer inspection. The finite element model can relate those locations to adjacent components and restraints. Sensor histories provide independent temporal references at selected positions.

Regional comparison is particularly useful when the exact location of a numerical peak depends on mesh discretization or when local DIC strain is sensitive to differentiation and smoothing. A defined area or characteristic line can make the comparison more representative, but it must not be enlarged merely to conceal a local disagreement.

### Step 4: Update with evidence and check independently

When discrepancies remain, investigate in order: measurement quality, coordinate and time mapping, restraints and connections, and then material parameters. Every update should have a physical rationale and a traceable source. After updating, examine a load stage or region that was not used to adjust the model. This separates explanatory adjustment from simple curve fitting and clarifies which parts of the interpretation remain supported by independent evidence.

## 4. Use residuals and uncertainty diagnostically

For a common physical quantity, location, and load stage, residuals can be formed between DIC and sensor measurements, DIC and finite element results, and sensor and finite element results. Retain the sign, location, direction, and stage associated with each residual. A single aggregate value can hide a localized discrepancy or a systematic offset that develops only during particular stages.

A growing residual does not identify its own cause. It may reflect a genuine local response, an incorrect spatial map, a shifted zero, or an inadequate boundary assumption. The diagnostic path should return to the source evidence: raw sensor histories, camera images, correlation-quality measures, test logs, and model settings.

Uncertainty should be described by source. Sensor contributions include mounting, resolution, zero stability, and movement of the support. DIC contributions include stereo calibration, focus, illumination, speckle quality, correlation settings, smoothing, and three-dimensional reconstruction. Numerical contributions include uncertain parameters, mesh representation, and idealized connections or restraints. When a difference is close to the measurement resolution, a detailed mechanical explanation is not warranted.

The outcome of cross-validation is therefore more than a statement of similarity. It should identify which stages have multi-source support, which regions rely on a single observation, and which discrepancies remain open. Those boundaries determine how far the results can be interpreted.

## 5. Respect the limits of contour maps

3D-XTDIC directly measures displacement on the visible surface. Strain is calculated from the displacement field through differentiation or local fitting. A strain contour is not a direct stress measurement. Stress interpretation requires a constitutive relationship, material parameters, and assumptions that must be stated separately.

Likewise, a sharp color transition does not by itself identify a crack or a failure state. The original images, displacement continuity, correlation quality, and other observations should be examined before assigning a physical meaning. Surface preparation, reflections, defocus, or partial occlusion can create features that resemble mechanical localization.

Instrumentation also has a physical footprint. Sensor brackets may introduce support movement, and loading fixtures may block part of the stereo view. Missing areas cannot be converted into observations through interpolation. Nor does full-field surface coverage establish full-field internal coverage. These limitations should remain attached to the maps throughout interpretation.

## 6. From model validation to engineering translation

A useful test deliverable preserves load-stage definitions, coordinate maps, raw sensor histories, image-quality information, DIC processing settings, model-parameter versions, and residual records. This allows another analyst to distinguish measurement, calculation, and interpretation, and to revisit a decision when additional evidence becomes available.

The objective is not to declare one method universally preferable. Point histories, full-field measurements, and mechanics-based predictions become more informative when their differences are examined systematically. For later use in rail-transit engineering, the validated model evidence still requires similarity relations, load-case mapping, repeated tests, and uncertainty propagation. Cross-validation is the bridge from observation to interpretation; engineering translation is the next, separate step.

## FAQ

### 1. Do similar DIC and finite element contour patterns complete the validation?

No. Coordinates, load stages, directions, and spatial scales must first be aligned. Independent sensor histories and residual analysis provide additional evidence that a visual comparison cannot supply.

### 2. Why use an averaging area in a point comparison?

A sensor, a DIC calculation region, and a finite element result may represent different spatial neighborhoods. A documented averaging area can align those scales, but it should not be chosen merely to reduce disagreement.

### 3. Can measured stress be read directly from a DIC strain map?

No. DIC measures surface displacement and derives strain. Stress requires a constitutive model and material parameters, so it belongs to a subsequent interpretation step.

### 4. Should finite element parameters be changed whenever the three datasets disagree?

Not immediately. First check synchronization, direction projection, sensor mounting, image quality, and occlusion. Then examine restraints, connections, and material assumptions so that measurement problems are not hidden by parameter adjustment.
