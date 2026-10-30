# Four-Point Bending of a Scaled Concrete Beam: Using 3D-XTDIC to Track Displacement, Shear Strain, and Crack Evolution

> **Abstract:** A final crack photograph cannot show how deformation localization developed during four-point bending of a scaled concrete beam. This article follows the staged-loading timeline and explains how 3D-XTDIC combines full-field displacement, shear-strain maps, original surface images, and key-point distance-versus-stage curves. The discussion covers strain concentrations in the web and bottom slab, crack initiation and propagation, and abrupt strain changes near cracked regions. It also explains why consistent color scales are necessary for stage comparison, why digital image correlation remains a surface measurement, and why a strain peak cannot simply be treated as crack width. The resulting process view supports a more traceable interpretation of deformation and cracking.

> **Keywords:** 3D-XTDIC; digital image correlation; scaled concrete beam; four-point bending; full-field strain measurement; crack evolution

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](03-3d-xtdic-concrete-beam-deformation-cracking_zh.md)
> - [English Version](03-3d-xtdic-concrete-beam-deformation-cracking_en.md)

## Contents

- [1. Test object: replace the end-state view with a process record](#1-test-object-replace-the-end-state-view-with-a-process-record)
- [2. Loading protocol: establish one timeline for all observations](#2-loading-protocol-establish-one-timeline-for-all-observations)
- [3. Process observations: compare displacement, shear strain, and cracks](#3-process-observations-compare-displacement-shear-strain-and-cracks)
- [4. Interpretation and research value](#4-interpretation-and-research-value)
- [5. FAQ](#5-faq)

## 1. Test object: replace the end-state view with a process record

Four-point bending of a scaled concrete beam for rail-transit bridge research is not only a question of where the final cracks appear. It also concerns how an initially distributed response evolves into localized deformation. A final photograph can document visible damage, but it cannot independently establish when strain concentrations developed in the web and bottom slab, where each crack initiated, or whether its propagation coincided with a change in the displacement field.

3D-XTDIC uses stereo images and digital image correlation to calculate surface displacement and derive full-field shear strain. Arranging fields in loading order reveals the appearance, movement, and connection of concentrated regions. Unlike an end-of-test image, this is process evidence, but it still describes the observable surface rather than internal cracks or stress.

### 1.1 Design the observation around process questions

The observed region should include the relevant web, bottom slab, and expected crack zones, with clear position references. Occlusion, defocus, and speckle loss need attention in critical areas. Original images and stage records should accompany the maps; otherwise, cracks, texture changes, and correlation anomalies can be difficult to distinguish.

## 2. Loading protocol: establish one timeline for all observations

The test uses staged four-point bending. For each stage, the processing record should relate the start of loading, the observation interval, and the end of the stage to image frame numbers, displacement fields, shear-strain fields, and crack observations. Only one representative image per stage may miss crack initiation or an abrupt displacement change occurring between neighboring frames.

Three information streams share this timeline: loading records describe the process, full-field maps describe spatial response, and key-point distance-versus-stage curves summarize selected relative motion. All need the same stage identifiers; ordering maps by acquisition files while numbering curves differently can create artificial disagreement.

| Stage record | Displacement-field review | Shear-strain and crack review | Evidence to retain |
| --- | --- | --- | --- |
| Initial and early loading | Establish the reference and overall distribution | Check background variation and pre-existing local anomalies | Reference images, initial maps, surface condition |
| Intermediate loading stages | Compare displacement growth and emerging concentrations | Track web and bottom-slab concentrations and any migration | Common-scale maps, key-point curves, stage log |
| Immediately before and after crack initiation | Look for a local discontinuity in displacement | Compare high-strain bands with visible initiation and propagation direction | Neighboring original images, matching masks, crack-path notes |
| Later loading | Follow overall deformation together with localization | Identify connected concentrations, abrupt changes, and invalid-data zones | Complete sequence, anomaly log, final surface images |

### 2.1 Color scales must support comparison

Displacement or shear-strain maps from different stages should use consistent physical quantities, directions, and color-scale limits. If every map is scaled independently to its own extrema, the same color can represent different magnitudes. A map that appears to become “more red” has not necessarily increased relative to other stages. Automatic scaling can help inspect details within one stage, but it should not be used directly for cross-stage comparisons. Masked or missing regions should also be visually distinct from low-strain regions.

## 3. Process observations: compare displacement, shear strain, and cracks

A practical review starts with the displacement field to understand overall bending, uses shear strain to locate concentrations, and returns to the original images to verify cracking. The available test information states that full-field displacement and shear-strain maps can be obtained, and that strain concentrations in the web and bottom slab, crack initiation locations, and propagation paths can be observed. These observations become more informative when followed through successive stages rather than collapsed into one final damage map.

Early continuous displacement fields provide a baseline. As loading proceeds, a shear-strain concentration in the web or bottom slab should be checked across adjacent stages for persistence, location, and agreement with visible cracking. A feature present in only one frame requires a review of matching loss, occlusion, and surface detachment. Crack interpretation is stronger when consecutive images and displacement changes support the same sequence.

### 3.1 Key-point curves provide stage information

A key-point distance-versus-stage curve tracks the change in separation between two selected surface points. A comparatively gradual early response, followed by faster growth or an abrupt change, can help identify mechanical stages such as elastic response, yielding, and cracking. The curve is supporting evidence, not a stand-alone criterion. Stage identification should also consider the overall loading record, full-field maps, and visible cracking, particularly when a single point pair may be affected by a local surface anomaly.

An abrupt strain change in a crack region is an important process observation. The stage and spatial extent of that change should be located before comparing it with the crack path. If both sides of the crack still contain valid matches, their displacement can be examined separately. If the opening causes correlation loss, the gap or mask should remain visible. Interpolating across the discontinuity would create a continuous field that was not measured.

### 3.2 A high-strain band is not a crack outline

Shear-strain bands are influenced by subset size, displacement smoothing, and surface texture. They may be wider than a visible crack or appear before the crack is clear. Crack paths should therefore be traced stage by stage from original images, with strain providing localization context. A color threshold is not a geometric crack outline.

## 4. Interpretation and research value

Combining the records creates a stage-displacement-shear-strain-crack evidence chain. A persistent web concentration may precede a visible crack, or a bottom-slab concentration may coincide with faster growth in a key-point distance curve. This process view reveals localization order better than initial-and-final images alone, but its conclusions remain tied to the scaled beam and its loading and boundary conditions.

Three limits remain explicit. Digital image correlation measures the surface, not internal crack geometry or stress. Color scales, displacement directions, strain components, and reference stages must be consistent for map comparison. Crack width also cannot be equated with a strain peak: strain derives from displacement gradients and calculation windows, whereas crack width describes a geometric opening requiring its own definition and measurement.

For scaled bridge-model research in rail transit, the main contribution of full-field process measurement is spatial context. It can help locate deformation concentrations in the web and bottom slab, compare fields before and after visible cracking, and inform the selection of sections and key points for closer review. It does not replace analysis of material behavior, structural detailing, or boundary conditions, and observations from a scaled model should not be transferred to another component without appropriate validation.

### 4.1 From describing damage to examining precursors

Once displacement, shear strain, and crack paths share a timeline, the next question is not which isolated value is largest. More useful questions are whether a concentration persists, whether key-point curves show repeatable stage changes, and whether any of these signals appear before a crack becomes clearly visible. Precursor identification based on this evidence requires the complete process record, documented anomalies, and agreement with physical observations. It offers a direction for later work on stage classification and deformation-and-failure characteristics.

## 5. FAQ

**1. Why is a final crack photograph insufficient for process analysis?**

It mainly documents the surface condition at the end of the test. It does not establish initiation timing, propagation order, or the earlier development of displacement and shear-strain concentrations.

**2. Does a high shear-strain region always coincide with a crack?**

No. It can indicate localization, but matching loss, occlusion, and calculation settings can also affect the field. Original images and neighboring stages are needed for verification.

**3. Can a key-point distance curve independently identify yielding?**

It should not be used independently. It can support stage interpretation when combined with the loading record, full-field response, and visible damage.

**4. Why must contour maps use a common color scale?**

A common scale gives colors consistent meanings across stages. Independent automatic scaling can exaggerate visual differences and obscure the actual relative magnitudes.
