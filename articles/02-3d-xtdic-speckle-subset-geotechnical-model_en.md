# Speckle Preparation for Geotechnical Similar-Material Models: 3D-XTDIC Patterning, Subset Selection, and Data-Gap Control

> **Abstract:** Geotechnical similar-material surfaces are heterogeneous, rough, and sometimes friable, so speckle and subset practices used on metal specimens cannot simply be transferred. This article provides a practical checklist for random, high-contrast patterns, gray-level quality, focus, coverage, adhesion, and illumination. It separates the roles of subset size and subset spacing, explains why denser output points do not necessarily add independent information, and reviews crack edges, spalling, reflective observation windows, and correlation loss. It also defines narrow conditions for local interpolation, emphasizing that filled values are derived estimates rather than recovered measurements. The workflow is intended to keep full-field displacement and strain interpretation traceable to image quality and processing decisions.

> **Keywords:** 3D-XTDIC; digital image correlation; similar-material model; speckle pattern; subset selection; data gaps

[中文版](02-3d-xtdic-speckle-subset-geotechnical-model_zh.md)

## Contents

- [1. Direct answer: make the surface trackable before tuning the analysis](#1-direct-answer-make-the-surface-trackable-before-tuning-the-analysis)
- [2. What the available test conditions establish](#2-what-the-available-test-conditions-establish)
- [3. Parameter guide: subset size and spacing do different jobs](#3-parameter-guide-subset-size-and-spacing-do-different-jobs)
- [4. Application checklist and the limits of gap filling](#4-application-checklist-and-the-limits-of-gap-filling)
- [5. FAQ](#5-faq)

## 1. Direct answer: make the surface trackable before tuning the analysis

Speckling a geotechnical similar-material model should create a random, high-contrast texture with suitable feature scale and stable adhesion, not simply the densest pattern. Digital image correlation tracks gray-scale patterns inside subsets. Particle loss, cracking, moisture, or coating failure can make texture changes look like deformation or cause matching loss.

A metal-specimen primer-and-spray routine should not be transferred automatically to layered soil or rock analogues containing pores, loose grains, and bedding interfaces. Thick coatings may bridge fine cracks or alter spalling, while pressing may disturb the surface. A small preparation trial should be checked after application, drying, and representative loading for adhesion and trackability.

### 1.1 A practical pattern and image checklist

A visual impression that the surface contains “enough dots” is not an adequate inspection. The following checks are more useful:

- **Randomness:** avoid regularly spaced dots or one-directional stripes that leave subsets with ambiguous patterns.
- **Contrast:** retain distinct dark and bright features without saturating the highlights or crushing the dark regions into a single level.
- **Feature scale and coverage:** features should be compatible with the subset size and image scale. Coverage should extend across layer boundaries, edges, and likely crack zones.
- **Focus:** inspect images from both cameras, since acceptable sharpness in one view does not establish sharpness in the other.
- **Adhesion:** inspect peeling, powder loss, detached texture, and new occlusions before loading and between load stages.
- **Illumination:** keep exposure conditions consistent and check whether reflections from a transparent observation window cover areas of interest.

These checks should be documented by stage. A later comparison of displacement fields is difficult to interpret if the surface texture or lighting changed without a corresponding record.

## 2. What the available test conditions establish

A layered geotechnical model used for metro-tunnel research presents two competing measurement needs. Continuous regions require stable tracking of the overall deformation, while crack neighborhoods require the analysis to retain possible displacement discontinuities. A pattern and subset arrangement should support both aims rather than optimize one contour map at the expense of the other.

A separate, publicly described large-model test provides scale context. The model was 2 m by 3 m, the observed field approximately 2 m, hydraulic loading was staged, and two cameras acquired images. Pattern inspection therefore needed to cover a broad surface, with repeated lighting and texture checks. Pattern preparation conclusions should remain bounded by that model's surface material and loading conditions.

### 2.1 A large field of view still requires local inspection

In a larger field of view, each physical speckle occupies fewer pixels, and local defocus or uneven illumination is harder to see in a thumbnail. Inspect patches at the center, edges, layer interfaces, and anticipated crack zones. Log any spray-scale or lighting change by load stage so comparisons do not cross an unrecorded imaging change.

## 3. Parameter guide: subset size and spacing do different jobs

Subset size controls how much local gray-scale information contributes to one correlation calculation. Subset spacing controls the distance between neighboring evaluation locations. They are not interchangeable. Reducing spacing produces more output points but does not make each match more stable. Increasing subset size can add useful texture to a match, but it also averages the estimated motion over a larger physical area.

| Parameter or condition | Primary effect | Possible symptom | Review and adjustment |
| --- | --- | --- | --- |
| Larger subset | Includes more gray-scale features and can improve matching stability | Crack-edge motion appears smoother or a concentration appears broader | Compare with a smaller subset in continuous and discontinuous regions |
| Smaller subset | Resolves more local spatial variation | More matching loss in weak texture and potentially noisier displacement | Check the number of useful features and gray-level variation inside the subset |
| Smaller spacing | Produces a denser output grid | More computation and more points that may still be strongly correlated | Use a density suited to the feature scale; do not equate density with independent information |
| Larger spacing | Reduces the number of evaluations and supports an overview | Narrow concentrations or boundaries may be skipped | Review crack and layer-interface neighborhoods for adequate sampling |
| Crack or spalling edge | Surface continuity and texture may change | Matching loss, outliers, or local gaps | Analyze valid regions separately and preserve the discontinuity |

Compare candidate settings on the same image sequence, using continuous, weak-texture, and crack-adjacent patches to reveal different failure modes. Zones may justify different settings, but their boundaries and parameters should remain attached to the results so that an analysis change is not mistaken for material response.

## 4. Application checklist and the limits of gap filling

A data gap is a measurement or processing state, not a region that must automatically be filled. Common causes include detached texture, occlusion, glare, defocus, a discontinuity at a crack, and points leaving the valid field. The first step is to classify the cause. Imaging problems call for an image and lighting review; physical damage should remain visible in the data mask; and algorithmic matching loss can be investigated through parameter comparisons.

### 4.1 Local interpolation has a narrow role

For a small number of isolated invalid points inside a region already judged to be continuously deforming, local interpolation can make a contour display or a subsequent operation more manageable. Interpolated values are derived from neighboring valid points. They are not new observations and do not restore the real measurement. The original gap mask, the filled region, and any exported dataset should retain that distinction.

Interpolation across a crack, a spalling zone, an occlusion, or a large region of failed correlation is a different matter. It can erase a displacement jump or create a deformation path that was never observed. Such regions should generally remain masked unless a separate, clearly stated analysis assumption justifies another treatment.

Transparent observation windows add reflection and adhesion risks. Glare can move with lighting or view angle, while separation or attached particles can change the visible surface. Lighting and viewing adjustments may reduce reflections, but the texture origin still needs checking. Features that cannot be associated with the model should be marked as limited-quality data rather than forced through correlation.

### 4.2 Review the chain before interpreting strain

Before analysis, review original images, pattern coverage, gray-scale quality, focus, correlation status, subset settings, gap masks, and interpolation records. Full-field strain measurement derives from displacement and is sensitive to local noise and smoothing, so gap treatment should match the strain interpretation. A high-strain band can locate a region of interest but does not define the complete crack geometry.

Once pattern quality, subset settings, and gap treatment are traceable, stage-by-stage interpretation becomes more meaningful. The next article applies this process view to a scaled concrete beam in four-point bending, placing displacement, shear strain, and crack evolution on one timeline.

## 5. FAQ

**1. Is a denser speckle pattern always better for a geotechnical model?**

No. Feature scale should be coordinated with image resolution, subset size, and the deformation features of interest. Very fine features may lose gray-scale definition in the acquired image, while very sparse features may leave too little texture inside a subset.

**2. Can smaller subset spacing compensate for an oversized subset?**

No. Spacing changes the density of evaluation locations, but each result still represents motion estimated over the full subset area.

**3. Do gaps near a crack make the entire dataset unusable?**

Not necessarily. A gap may represent a real discontinuity, matching loss, glare, or spalling. Classify the cause and preserve valid measurements on both sides where possible.

**4. Can interpolated regions be used for quantitative interpretation?**

Only with caution and explicit identification. Interpolated values depend on neighboring measurements and are not independent observations. They should not be created across cracks or large failed-correlation zones.

**5. Can reflections on a transparent window serve as speckles?**

They should not be assumed to do so. Reflections may move with the lighting or camera view rather than with the model surface, so their origin and behavior need to be checked.
