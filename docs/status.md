# STMS — Status

更新时间：2026-10-07。

**Overall: Research Prototype / WIP.**

## Current milestone

**M2-A Phase 1 — Jellyfish Generalization Foundation.**

The previous public summary treated all M2-A work as generic WIP. The latest canonical audit is more specific: the **subject-binding layer has been implemented and regression-verified**, while jellyfish geometry/material/capture acceptance is still incomplete.

## Implemented / verified

- jelly optical prototype: analytic thickness proxy, Beer–Lambert absorption, screen-space refraction, artistic back-scattering approximation, wet highlight;
- spring motion and local contact deformation;
- single-mesh visual soft tear / regeneration and its damage/recovery lifecycle;
- Material / Motion Profile and Preset parameterization;
- M2-A explicit subject binding with renderer roles and per-renderer body metrics for the principal runtime consumers;
- compile/import verification: 0 C# errors, 0 Shader errors, 0 Exceptions;
- M1-F preset live re-apply regression: failures = 0 in two independent processes;
- M1-G fracture lifecycle regression: gate = PASS.

## WIP

- jellyfish bell / tentacle geometry is not yet accepted;
- no validated jellyfish material/hero capture is published;
- multi-renderer preset look application remains deferred;
- subject-specific motion weighting, normal/thickness validation and capture tooling still need the second-subject pass.

An uncompiled local jellyfish geometry draft is not counted as a completed capability.

## Generalization boundaries

The shader core, Beer–Lambert absorption, spring oscillator, preset schema and MPB material path are reusable on current evidence. Remaining geometry-specific assumptions include the floor-contact motion anchor, spherical/origin-centred internal-structure volumes, convex-subject thickness assumptions and single-renderer look application.

## Limitations

Scattering is not physical SSS. The thickness term is an analytic proxy, not a measured optical path. Screen-space refraction cannot provide complete inter-object transparent refraction. Visual soft tear does not change mesh topology and is not FEM physical simulation.

Source/project distribution is not currently provided. This public repository remains showcase-only and does not contain the complete engine project, logs, internal reports or a source license.
