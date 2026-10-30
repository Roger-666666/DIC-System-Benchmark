# From Model Contours to Engineering Criteria: Translating 3D-XTDIC Similar-Material Tests for Rail-Transit Design

> **Abstract:** A contour map from a similar-material model describes a surface response under a particular scale, material system, and boundary condition; it is not, by itself, a rail-transit design criterion. This article organizes engineering translation around the design question, similarity relations, load-case mapping, multi-method cross-validation, repeated tests, and uncertainty assessment. It explains how 3D-XTDIC evidence can support precursor-indicator research, support-parameter checks, and simulation updates while keeping surface observations, scale effects, and modeling limitations explicit. A traceable data package and decision table connect model measurements to bounded engineering interpretation.

> **Keywords:** 3D-XTDIC; similar-material model; digital image correlation; deformation and failure characteristics; rail transit; full-field strain measurement

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](07-3d-xtdic-model-test-engineering-translation_zh.md)
> - [English Version](07-3d-xtdic-model-test-engineering-translation_en.md)

## Contents

- [1. Engineering question: why a contour is not a criterion](#1-engineering-question-why-a-contour-is-not-a-criterion)
- [2. Translation rules: build a traceable chain](#2-translation-rules-build-a-traceable-chain)
- [3. Application checklist for three design uses](#3-application-checklist-for-three-design-uses)
- [4. Risk boundaries and delivery checks](#4-risk-boundaries-and-delivery-checks)
- [5. Series synthesis: measure, track, interpret, apply](#5-series-synthesis-measure-track-interpret-apply)
- [FAQ](#faq)

## 1. Engineering question: why a contour is not a criterion

A similar-material model makes deformation and failure characteristics observable under controlled, reduced-scale conditions. Using digital image correlation, 3D-XTDIC measures displacement on the visible surface and derives full-field strain. The resulting maps show location, gradient, and evolution in a way that sparse point measurements cannot. Nevertheless, a color band or contour line remains a model observation. It is not automatically an acceptance limit, a monitoring threshold, or a design rule for the prototype.

Translation should begin with the decision that the evidence is expected to inform. One team may be investigating candidate indicators that precede unstable deformation. Another may be comparing how support parameters change a response path. A third may need to revise material or boundary assumptions in a numerical simulation. These tasks require different combinations of temporal, spatial, and mechanical evidence. Treating every contour as a general answer removes precisely the context that gives the test meaning.

| Engineering purpose | Useful model evidence | Required translation | Interpretation to avoid |
| --- | --- | --- | --- |
| Precursor-indicator research | Timing and spatial migration of displacement, strain, and crack observations | Load-case mapping, repeated tests, and multi-indicator analysis | A universal numerical threshold for field use |
| Support-parameter checks | Differences in response paths and concentrated regions across defined cases | Similarity relations, boundary alignment, and uncertainty comparison | Direct prototype parameter conclusions without mapping |
| Simulation updates | Full-field distributions, point histories, and calculation residuals | Constrained parameter updates and independent checks | Treating one fitted case as a general model |

The decision question should also specify what would change if the evidence were inconclusive. If a concentrated region cannot be mapped to the prototype, the result may still guide further model analysis without supporting a field criterion. If repeated tests produce different sequences, the appropriate outcome may be a broader uncertainty description rather than a single indicator. Engineering translation includes the option to limit or defer a conclusion.

## 2. Translation rules: build a traceable chain

### Rule 1: Connect model quantity, similarity relation, and prototype interpretation

Start by defining each model quantity: displacement component, reference zero, strain algorithm, spatial averaging region, and load stage. Establish the relevant geometric, loading, material, and response similarity relations from similarity theory, then check whether the model actually satisfies the associated assumptions. Conceptually, a prototype interpretation is obtained through the appropriate similarity relation applied to the model quantity. The relation is quantity-specific; one scale factor cannot be applied mechanically to every response.

Similarity conversion does not remove scale effects by arithmetic. Local construction details, material heterogeneity, interfaces, and contact behavior may not scale according to the same relation. Where these features depart from the ideal model, their influence should remain visible in the interpretation. A formally correct conversion applied to an incomplete physical model still produces a bounded conclusion.

### Rule 2: Map the load case before discussing thresholds

The model and prototype must correspond in initial state, restraint, loading sequence, support-installation stage, and observation window. For staged loading, record the beginning and end of each increment and the holding condition. For comparisons across support schemes, keep unrelated factors consistent so that the observed difference can be associated with the parameter under study.

If the load cases do not correspond, similar contour shapes are not enough to establish equivalent mechanics. Threshold discussion should therefore come after load-case mapping, not before it. This ordering prevents an appealing spatial pattern from substituting for a defined engineering condition.

### Rule 3: Combine independent evidence and repetition

3D-XTDIC contributes spatial coverage, point sensors contribute independent time histories, and numerical analysis contributes an explicit mechanical hypothesis. Compare them using common coordinates, time references, load stages, and spatial scales. Preserve signed residuals and identify where evidence agrees, where it diverges, and where no direct observation exists.

Repeated tests address a different question from multi-method comparison. Cross-validation examines consistency among evidence types; repetition examines variability across specimens or test realizations. Reports should state the number of repetitions, reasons for excluding any data, and differences among repeated responses. Selecting only a representative contour can hide the dispersion that matters most when a precursor or threshold is proposed.

Uncertainty must travel with the conversion. Measurement resolution, stereo calibration, correlation settings, sensor installation, material properties, and boundary simplification all affect the prototype interpretation. The deliverable should distinguish measured values, calculated values, and inferred criteria, with assumptions attached to each layer.

## 3. Application checklist for three design uses

### Use 1: Precursor-indicator research

Displacement describes a change in position, strain describes local deformation, and cracking requires identification from original images or other observations. These quantities should not be collapsed into one label. Strain concentration, a change in displacement rate, or crack development may be a candidate precursor signal, but none is automatically a failure criterion.

A useful indicator definition includes amplitude, rate, persistence, spatial migration, and the load stage at which it is evaluated. Repeated cases can show whether the sequence is reproducible or merely one possible response. Combining indicators can also reduce dependence on a single surface feature, provided that each indicator retains a clear physical definition.

Any proposed threshold must remain specific to the structure, load case, baseline, and measurement definition. Baseline variability and measurement uncertainty should be included, and engineering decisions should retain a safety margin. Model tests can support the study of thresholds, but prototype monitoring and subsequent checks remain necessary before field use. No universal numerical field threshold follows from a model contour alone.

### Use 2: Support-parameter checks

Define comparison cases before interpreting differences. Examine how concentrated deformation, affected areas, and response sequences change with the support parameter. Full-field DIC supplies information between discrete sensors, while point measurements check selected moments and numerical analysis helps explain the mechanism.

A visually smaller contour region is not sufficient evidence by itself. The comparison should establish that similarity relations and boundary mappings remain applicable, that repeated responses support the difference, and that uncertainty does not reverse the interpretation. Only then can the comparison become a bounded reference for prototype design decisions.

### Use 3: Simulation updates

Use selected load stages or regions to constrain material parameters and boundary conditions, then examine stages or regions that were not used for the update. This helps distinguish a mechanically meaningful update from compensation among parameters. Visual resemblance between two full-field maps is not enough when different parameter combinations can produce similar patterns.

Record parameter versions, evidence used for each change, and subsequent residuals. If the updated model explains only the calibration case, its role should remain limited to that case. Traceability is more useful than an unqualified statement of agreement.

## 4. Risk boundaries and delivery checks

Surface DIC cannot represent every internal response. Occluded regions, the specimen interior, and areas with failed speckle patterns lack direct DIC observation. Interpolation may support visualization, but it does not create measured evidence. Internal interpretation therefore requires additional instrumentation or a mechanical model whose assumptions and checks are explicit.

Scale effects, heterogeneous materials, specimen fabrication differences, and boundary friction can alter deformation and failure characteristics. Sensor errors and numerical discretization errors belong to separate parts of the evidence chain. They should not be treated as canceling one another without justification.

| Decision check | Action when evidence is adequate | Action when evidence is incomplete |
| --- | --- | --- |
| Do similarity relations and load cases correspond? | Proceed to a bounded prototype interpretation | Retain a model-level qualitative finding and investigate the gap |
| Are independent measurements and repeated tests available? | Assess variability and study combined indicators | Do not use the result as a stand-alone criterion; add evidence |
| Are surface and internal responses distinguished? | State the surface scope and assumptions of any internal inference | Add internal observations or reduce the interpretation level |
| Has uncertainty been propagated through conversion? | Report intervals, residuals, and assumptions | Defer threshold language and return to the source data |

The final data package should include model geometry and material-batch records, similarity-relation versions, load-case and stage definitions, coordinate maps, original images and point histories, DIC processing settings, numerical parameters, repeated-test results, exclusion records, and uncertainty descriptions. This structure allows a reviewer to reconstruct why a result was converted, where it applies, and which steps remain inferential.

## 5. Series synthesis: measure, track, interpret, apply

Across the series, “measure reliably” depends on calibration, common references, and an explicit account of uncertainty. “Track continuously” means following point histories and spatial evolution through loading stages while acknowledging occlusion and surface limits. “Interpret mechanically” connects displacement, strain, and crack observations to a load path tested against independent evidence. “Apply traceably” adds similarity conversion, load-case mapping, repetition, and decision-ready documentation.

The move from a model contour to a rail-transit design reference is therefore not a visualization step. It is a controlled chain of evidence. With that chain intact, 3D-XTDIC results from similar-material tests can inform precursor research, support-parameter checks, and simulation updates without obscuring the difference between a model observation and an engineering criterion.

## FAQ

### 1. Can one strain-concentration map define a field threshold?

No. The indicator definition, load-case mapping, repeatability, and uncertainty must be established first. Prototype monitoring and multi-indicator checks are also needed for field interpretation.

### 2. Does an unremarkable surface strain map rule out internal change?

No. DIC observes the visible surface. Internal response requires additional measurements or a suitably checked mechanical model.

### 3. Can repeated tests be omitted when model and simulation trends are similar?

No. Similar trends do not quantify variability from fabrication, material heterogeneity, or boundary differences. Repetition addresses that separate source of uncertainty.

### 4. What records matter most for a support-parameter comparison?

Keep the comparison cases, controls on unrelated factors, similarity relations, coordinate and stage maps, raw measurements, parameter versions, and residual records so that each observed difference remains traceable to its conditions.
