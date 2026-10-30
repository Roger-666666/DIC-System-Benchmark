# From Strain Concentration to an Arc-Shaped Slip Surface: 3D-XTDIC Analysis of Localized Failure in a Soil Slope under Simulated Rainfall

> **Abstract:** An arc-shaped slip surface in a rainfall-induced soil slope is the outcome of an evolving process, not a line that suddenly appears. Multiview 3D-XTDIC measurements connect crest displacement, midslope settlement, maximum principal strain, and the expansion of a localization band throughout artificial rainfall. Reliable interpretation requires consistent contour scales, careful selection of image-correlation settings, and a clear distinction between surface observations and inferred internal geometry.

> **Keywords:** 3D-XTDIC; digital image correlation; rainfall soil slope; physical similarity model; strain localization; full-field strain measurement; deformation and failure characteristics

> [!TIP]
> **请选择阅读语言 / Please select your language:**
>
> - [中文版](05-3d-xtdic-rainfall-soil-slope-strain-localization_zh.md)
> - [English Version](05-3d-xtdic-rainfall-soil-slope-strain-localization_en.md)

## Contents

- [Concept: an arc-shaped slip surface is the result of a process](#concept-an-arc-shaped-slip-surface-is-the-result-of-a-process)
- [Recognition principle: different roles for displacement and strain](#recognition-principle-different-roles-for-displacement-and-strain)
- [From speckle images to time-sequenced contour maps](#from-speckle-images-to-time-sequenced-contour-maps)
- [Processing choices can reveal or smooth a localization band](#processing-choices-can-reveal-or-smooth-a-localization-band)
- [Common misreadings: a contour map is not an internal section](#common-misreadings-a-contour-map-is-not-an-internal-section)
- [Toward corroboration by multiple methods](#toward-corroboration-by-multiple-methods)
- [FAQ](#faq)

## Concept: an arc-shaped slip surface is the result of a process

During artificial sprinkling that simulates rainfall infiltration, a soil or sand slope does not necessarily move as a single mass along a predefined curve. Differential deformation can develop first. In the observed physical model, the crest shows significant horizontal displacement, the middle settles, and displacement changes in a gradient toward the toe. These responses indicate that different parts of the slope are moving differently as rainfall and deformation proceed.

The arc-shaped critical sliding surface should therefore be understood as a geometric interpretation of accumulated deformation, localization growth, and eventual connection from the crest toward midslope. It is not simply the outline of a colored patch. Time-sequenced 3D-XTDIC results retain the order of events: where displacement first becomes anomalous, where strain subsequently concentrates, and how separate regions begin to connect.

### Localization differs from bulk movement

A displacement field describes movement of the visible slope, whereas localization concerns whether deformation becomes concentrated into a comparatively narrow zone. Large displacement can arise from broad translation or rotation without a narrow band of intense gradient. Conversely, a local strain maximum does not by itself demonstrate a connected slip surface. Its continuity, orientation, persistence, and relationship to differential displacement must also be examined.

This distinction prevents two opposite errors: treating every moving region as a sliding mass, and treating every strain hotspot as a failure surface. The useful evidence lies in the development of both fields over the same sequence.

## Recognition principle: different roles for displacement and strain

Digital image correlation tracks changes in surface speckle patterns to calculate displacement. Strain is then derived from spatial displacement gradients. Displacement answers where the surface moves, in which direction, and by how much. Strain answers where deformation is concentrated. Because the two quantities have different meanings and sensitivities, they should be read together rather than used interchangeably.

### Displacement anomalies define the active region

Crest horizontal displacement and midslope settlement provide the first spatial clues in the public test description. The displacement gradient toward the toe helps define the extent of differential movement. An analyst can compare direction and rate of change among neighboring regions, then determine whether an anomaly persists through successive rainfall stages.

A single point that jumps while its neighborhood remains unchanged should first trigger checks for occlusion, speckle loss, or failed correlation. Such a point is not sufficient evidence for the initiation of sliding. A more meaningful anomaly has spatial support and evolves consistently with nearby measurements.

### Maximum principal strain tracks the concentration band

The observed maximum principal strain concentration from crest to midslope corresponds to the displacement anomaly and supplies an independent view of localization. In time-sequenced maps, the important features are whether scattered high-strain patches become a relatively continuous band, whether its position remains stable or expands in an orderly manner, and whether differential displacement across the band increases at the same time.

Only when these features support one another across multiple stages is it appropriate to discuss connection of a sliding zone and an arc-shaped critical surface. The interpretation comes from the sequence, not from one visually persuasive frame.

| Observation | Main question | Contribution to the arc-shaped slip interpretation | Alternative explanations to check |
| --- | --- | --- | --- |
| Horizontal and vertical displacement | How do crest, midslope, and toe move differently? | Define the active region and movement directions | Bulk rigid motion or local occlusion |
| Displacement gradient | Is sustained relative deformation developing between neighboring regions? | Supply displacement evidence for localization | Isolated jumps or truncated boundaries |
| Maximum principal strain | Where does deformation concentrate, and is the zone continuous? | Track the concentration band from crest toward midslope | Noise patches or smoothing-induced bands |
| Time-sequenced contours | How do anomalies appear, expand, and connect? | Assess whether localization progresses toward connection | Apparent changes caused by different color scales |

## From speckle images to time-sequenced contour maps

Activated-carbon particles mixed with sand can form a random speckle pattern on the model surface. Two cameras and supplementary lighting acquire images throughout the rainfall process. The speckles must deform with the soil and remain recognizable under spraying. Lighting reduces brightness fluctuations that can interfere with image matching, but water droplets, haze, and surface erosion may still degrade the local pattern.

These changes are part of the measurement conditions and should remain visible in the quality assessment. A region that loses usable texture cannot provide the same displacement evidence as an intact region, regardless of how smooth an interpolated map may appear.

### A common reference and continuous tracking are essential

The analysis begins with a selected reference image or stage that establishes the initial geometry and coordinate relation. Image subsets are then matched through the sequence to reconstruct three-dimensional surface displacement. The reference defines what the deformation is relative to, so changing it between compared results can alter their apparent development.

After a temporary occlusion, tracking should be checked so that it still refers to the same material region. A newly matched pattern can introduce an offset that resembles displacement but has no mechanical origin. Reference selection, camera synchronization, and continuity of the reconstructed surface all affect the subsequent strain field.

### Contour presentation must preserve temporal comparability

A common color scale should be used for a time series so that changes in color represent changes in the physical quantity. If each frame is scaled automatically, the same color may represent different strain levels. A localization band can then appear to intensify or vanish even when the underlying field does not change in that way.

Data gaps should be displayed as gaps, with their boundaries retained. Filling them by interpolation and then using the resulting continuous colors to infer the shape of a slip surface would confuse visualization with observation.

## Processing choices can reveal or smooth a localization band

Subset size, calculation step, and smoothing influence both spatial resolution and numerical stability. There is no simple rule that smaller is always more detailed or that stronger smoothing is always clearer. These choices should be considered in relation to the expected band width, speckle quality, and displacement gradients, then held consistent when rainfall stages are compared.

| Processing choice | Tendency when small or weak | Tendency when large or strong | Interpretation check |
| --- | --- | --- | --- |
| Subset size | Greater sensitivity to texture and noise; strain may become fragmented | Averaging over a wider material region; a narrow band may be softened | Does band width change with subset size? |
| Calculation step | Denser output points, with neighboring results potentially correlated and noise more visible | Fewer spatial details and coarser band edges | Do not confuse point spacing with true spatial resolution |
| Smoothing | Retains detail but also numerical fluctuations | Produces a more continuous map while weakening peaks and gradients | Compare processed and unprocessed fields |

Sensitivity can be examined by repeating the analysis with reasonable variations in these settings. An interpretation is more robust if the band retains its position, direction, and temporal development. If the apparent arc arises only with one smoothing choice, it is not adequately supported by the measurements.

A fixed color scale improves comparability but does not correct a processing artifact. Display settings and mechanical evidence must be evaluated separately.

## Common misreadings: a contour map is not an internal section

Three-dimensional DIC measures the visible surface. Surface displacement and strain can express the external response of an internal process, but they do not directly image an internal slip surface. Interpreting a crest-to-midslope concentration band as an arc-shaped critical surface requires temporal correspondence, differential displacement, and the observed failure geometry. Measurement and geometric inference should be stated as separate parts of the conclusion.

### A transparent observation window still provides surface observations

A transparent window in a physical model reveals deformation near the window surface. It does not automatically remove side-boundary friction or represent every internal cross-section. Window-edge effects, particle contact with the window, and viewing geometry may influence the measurements. The window map should therefore not be treated unconditionally as the central section of the slope.

This limitation does not negate the value of the observation. It defines what the observation can support: surface localization and its evolution, rather than unrestricted reconstruction of the entire internal failure volume.

### Data gaps define part of the result boundary

Spray occlusion, speckle damage, and correlation failure can create holes in the displacement field. Strain near those holes may also be affected by incomplete neighborhoods. Concentration at a gap boundary therefore requires particular caution.

Connecting separate holes into an arc, or including a low-confidence zone in a claim of band connection, would exceed the support provided by the data. The uncertainty should be carried into the final interpretation rather than concealed by contour filling.

## Toward corroboration by multiple methods

A coherent interpretation begins with displacement anomalies that define the active region, uses maximum principal strain to track localization, and examines time-sequenced maps for expansion and connection. Only then is the arc-shaped slip surface discussed as a geometric explanation of sliding failure. This chain captures the process without claiming that a surface map reveals every internal mechanism.

Further analysis can compare these observations with moisture-state measurements, pore-water response, geometric sections, or other independent observations where available. Repeating the correlation analysis under consistent and sensitivity-tested settings adds another check. The aim is agreement among independent forms of evidence, not a single smooth contour that appears conclusive.

## FAQ

### Does large displacement necessarily mean strong strain localization?

No. Broad translation or rotation can produce large displacement. Localization concerns sustained spatial gradients and the development of a concentrated band.

### Why should all time-sequenced maps use one color scale?

A common scale makes colors comparable across stages. Automatic rescaling can make localization appear to intensify or disappear without an equivalent physical change.

### Is a smaller subset always better for identifying a sliding band?

No. A smaller subset may retain detail but also amplify texture noise. Subset choice should be checked against speckle quality, band width, and parameter sensitivity.

### Is a surface arc-shaped strain band the internal slip surface itself?

Not directly. It is a surface response. An internal slip-surface interpretation also requires displacement, temporal, failure-geometry, and preferably independent observational support.

### Can data gaps be interpolated before interpreting band connection?

Interpolation cannot replace measurements. Gaps and their boundaries should remain explicit so that artificially continuous regions are not used as evidence of connection.
