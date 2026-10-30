# Calibration and Synchronization for 3D-XTDIC in Large-Scale Shield Tunneling Similar-Material Models: From Field Partitioning to Timeline Alignment

> **Abstract:** In a large shield-tunneling similar-material model, the first measurement challenges are often coordinate registration, field coverage, and timeline consistency rather than the settlement curves themselves. This article presents a practical 3D-XTDIC workflow for multi-camera layout, joint zonal calibration, overlapping fields of view, physical vibration isolation, and hardware-pulse triggering. It separates spatial registration from temporal synchronization, explains how excavation and retreat events can be aligned with image sequences, and summarizes checks for calibration drift, dropped frames, static displacement, and overlap consistency. The aim is to establish traceable surface-deformation evidence before interpreting settlement patterns or discussing possible mechanisms.

> **Keywords:** 3D-XTDIC; digital image correlation; similar-material model; multi-camera calibration; timeline alignment; full-field strain measurement

[中文版](01-3d-xtdic-shield-model-calibration_zh.md)

## Contents

- [1. The calibration problem behind a large field of view](#1-the-calibration-problem-behind-a-large-field-of-view)
- [2. A system layout with separate spatial and temporal controls](#2-a-system-layout-with-separate-spatial-and-temporal-controls)
- [3. Implementation from camera networking to event alignment](#3-implementation-from-camera-networking-to-event-alignment)
- [4. Quality checks before settlement interpretation](#4-quality-checks-before-settlement-interpretation)
- [5. FAQ](#5-faq)

## 1. The calibration problem behind a large field of view

A large similar-material model can be used in rail-transit research to observe surface deformation during shield excavation and retreat. As the model grows, one stereo pair may no longer cover the tunnel axis, the ground-surface region of interest, and the area around an overlying structure at the same time. Adding camera pairs expands coverage, but it also introduces three questions: do all pairs share one coordinate system, can adjacent zones be reconciled at their boundaries, and does every image frame correspond to the same physical stage?

Digital image correlation estimates displacement by matching image subsets before and after deformation. A stereo system then reconstructs three-dimensional coordinates using its calibration. If every camera pair retains an independent local frame, an individual displacement map may look plausible while the assembled map contains inconsistent directions or discontinuities. The first task is therefore to establish a traceable spatial and temporal reference, not to make the color maps look continuous.

### 1.1 Define coordinates and process events together

The test plan should state model axes, the surface reference, tunnel-axis direction, displacement signs, and events such as excavation, pauses, and retreat. Coordinates support spatial registration, while events support curve segmentation; neither replaces the other. Observation zones around an overlying structure should be tied to physical locations, not selected later from contour appearance.

## 2. A system layout with separate spatial and temporal controls

A multi-camera 3D-XTDIC configuration can be managed in two layers. The spatial layer uses zonal calibration and overlapping views to express measurements in a common three-dimensional frame. The temporal layer uses common triggering and event records to construct a consistent frame sequence. Each layer needs its own verification: synchronized images can still have incompatible coordinates, and registered cameras can still acquire frames at different process events.

### 2.1 Camera zones need useful overlap

Camera placement should follow regions of interest and occlusions rather than equal surface divisions. Adjacent zones need useful overlap so two stereo pairs observe the same area, providing checks for displacement direction, trend, boundary continuity, and local calibration. A camera-to-region map prevents files from being assigned to the wrong model area.

Each stereo pair needs its own relative geometry and a traceable relationship to the common model frame, so that coordinates for the same physical point are comparable across views. A target may be applied zone by zone when it cannot cover the model, but reference transfer must remain explicit and be checked across adjacent zones.

### 2.2 Isolate the supports and synchronize the triggers

Loading equipment, foot traffic, or nearby machinery can introduce relative camera-to-model motion. Stable supports, no unintended loading-frame contact, and control of cable pull can reduce this effect. Isolation does not replace a static test: apparent motion while the model is stationary still requires investigation.

Where the acquisition architecture permits, all camera pairs can receive pulses from the same hardware source. Frame numbers, timestamps, and trigger logs should be retained. A common pulse train makes dropped frames and sequence offsets easier to detect than alignment based only on separate software clocks. If some cameras cannot share the trigger, the acquisition record should at least contain cross-checkable events and a check for drift during the test.

## 3. Implementation from camera networking to event alignment

The order of work matters. Fix the mechanical arrangement and coordinate conventions first, perform calibration second, verify synchronization third, and only then begin the process sequence. Camera movement, a support impact, or a focus change can invalidate the previous geometric relationship and should trigger a calibration review.

| Workflow step | Main action | Evidence to retain | Reason to revisit the setup |
| --- | --- | --- | --- |
| Coordinate and camera planning | Define axes, observation zones, overlaps, and occlusion limits | Camera map, zone identifiers, sign convention | Missing coverage or ambiguous zone identity |
| Joint zonal calibration | Establish stereo geometry and transfer the common reference | Calibration images, residual distribution, shared points | Local residual anomalies or inconsistent overlap response |
| Static and isolation check | Acquire a stationary sequence and inspect apparent drift | Static displacement record, support and cable condition | Coherent motion without a process change |
| Synchronization check | Compare pulses, frame numbers, timestamps, and dropped frames | Trigger log, frame sequence, event record | Unequal sequences or displaced event positions |
| Process acquisition | Log excavation, pauses, and retreat while monitoring quality | Process log, image state, correlation status | Occlusion, matching loss, or timeline interruption |

### 3.1 Align both frames and excavation stages

Frame alignment and stage alignment are different tasks. Common triggering establishes correspondence among image frames, while the process log links those frames to excavation and retreat. Before the formal test, an identifiable event can be used to check whether every camera records the same sequence position. During the test, the frame numbers associated with stage transitions should be logged instead of inferred later from file creation times.

Excavation and retreat need explicit boundaries. Dropped frames can be matched by frame number, but missing intervals are not continuously observed deformation. Interpolation across a stage change also requires caution because the boundary response may be meaningful. Aligned data should have consistent event positions, no artificial steps in stationary intervals, and traceable stage-transition records.

### 3.2 Calibration review continues during the test

Calibration describes camera geometry at one point in time. Static and overlap checks during a long test can indicate whether it remains applicable. If the geometry changes, the affected interval should be identified; a later calibration cannot simply replace the earlier one.

## 4. Quality checks before settlement interpretation

Quality control should cover four kinds of evidence. Image review addresses exposure, focus, occlusion, and speckle condition. Correlation review addresses matching loss, outliers, and gaps. Three-dimensional review addresses overlap consistency and static drift. Timeline review addresses missing frames, duplicates, and event offsets. When an anomaly appears, the original images and processing history should be retained so that a surface change can be distinguished from an imaging or calibration change.

An overlap difference does not identify which camera pair is wrong; view angle, occlusion, or texture may also contribute. Review the shared-region images and correlation status before checking calibration and triggers. Isolated jumps should not merely be smoothed, while sustained offsets require a review of supports and coordinate registration.

The available observations illustrate the interpretation order. In that model, settlement extrema were concentrated directly above the tunnel axis; displacement increased during excavation, followed by a small rebound during retreat. These are model-specific observations, not universal rules. Axis and transverse sections should be compared only after their curves share the excavation-and-retreat timeline.

### 4.1 Keep measurement and mechanism separate

Digital image correlation measures the observable surface and derives displacement and strain from image sequences. It does not directly measure internal stress or the structural condition of the model. Full-field strain measurement can help locate concentrations, but interpretation still depends on material similarity, boundary conditions, and process control. Conclusions should therefore be bounded by the observed model, the valid coverage, the usable time intervals, and the documented treatment of anomalies.

Once the spatial and temporal references are consistent, attention shifts to the measured surface itself. The next article examines speckle quality, subset selection, and the control of data gaps around cracks and boundaries.

## 5. FAQ

**1. Can displacement maps from different camera pairs be stitched directly?**

Not without checks. Stereo calibration, the shared coordinate frame, and overlap consistency should be reviewed first. A common color scale alone does not remove registration differences.

**2. Is a process log still necessary with common hardware triggering?**

Yes. Trigger records align acquisition frames, while the process log identifies which frames correspond to excavation, pauses, or retreat.

**3. What should be done when overlap-zone measurements differ?**

Review viewing conditions, occlusion, speckle quality, correlation status, and calibration evidence. Smoothing the boundary before identifying the cause can hide a real acquisition problem.

**4. Does rebound during retreat demonstrate recovery of internal stress?**

No. It is an observed surface-displacement response in that model. An internal mechanism requires additional evidence from the material, boundaries, and process conditions.
