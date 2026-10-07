# SoftMatter / STMS

**Soft Material / Technical Art / Real-time Rendering Research System** · Tuanjie / Unity URP

STMS explores how one reusable real-time system can represent **soft translucent materials across different subjects** instead of hard-coding one jelly look. The current evidence-backed baseline is the purple konjac jelly; the active milestone is **M2-A Jellyfish Generalization Foundation**.

![STMS procedural jelly optical study: front, high-angle and back views](media/jelly-optics-cover.png)

## Current System

The current system is evidence-backed for:

- parameterized translucent optics: analytic thickness proxy, Beer–Lambert absorption, screen-space refraction, wet highlight and artistic back-scattering;
- spring-based whole-body motion and local contact deformation;
- damage / recovery lifecycle driving single-mesh visual soft tear and regeneration;
- Material Profile / Motion Profile / Preset authoring;
- explicit multi-renderer **subject binding** for motion, contact, fracture-role, breakage, bubble-field and internal-noise target resolution;
- debug / calibration capture used to separate appearance claims from implementation claims.

The goal is not a single “jelly shader”, but a reusable soft-material research framework whose assumptions can be exposed, tested and replaced.

## Latest Milestone

**M2-A Phase 1 — Jellyfish Generalization Foundation: subject binding implemented and regression-verified.**

The latest canonical evidence records a new subject declaration layer with renderer roles and per-renderer body metrics, while keeping the pre-M2-A fallback path intact. Headless verification reported:

- compile / import: **0 C# errors, 0 Shader errors, 0 Exceptions**;
- M1-F preset live re-apply: **0 failures** in two independent processes;
- M1-G fracture lifecycle regression: **gate = PASS**.

This upgrades the old public statement “M2A generalization = WIP” into a more precise state: **generalization infrastructure is now partially implemented and verified; jellyfish geometry/material/capture are not yet validated.**

## Material / Optical Model

STMS uses an analytic convex-subject thickness proxy to modulate optical response, Beer–Lambert absorption for transmittance, screen-space refraction for the visible background, and an artistic back-scattering term for soft translucent readability.

![Analytic thickness proxy debug: brighter centre, thinner rim](media/thickness-proxy.png)

![Screen-space refraction against a procedurally generated checker](media/refraction-debug.png)

These are rendering models, not measurements of a real optical path. Screen-space refraction also cannot reconstruct off-screen information or full transparent-object inter-refraction.

## Motion & Interaction

A spring controller drives squash / lean motion. Local contact adds a dent and surrounding bulge around a contact point, then combines that result with whole-body motion.

Profiles and presets keep look and response data outside the shader core. M2-A adds explicit subject membership and per-renderer metrics so a future multi-part subject does not have to inherit jelly-specific hierarchy assumptions.

![Recorded STMS spring motion, medium profile](media/spring-motion.gif)

The GIF above is a recorded spring-motion experiment. It is not evidence of jellyfish motion or a full tear lifecycle.

## Damage / Recovery

Damage and recovery are driven as a visual lifecycle. The current tear model produces necking, seam appearance, two-lobe visual separation and regeneration on the same mesh.

![Soft-tear debug: partition, seam and regeneration channels](media/soft-tear-debug.png)

**Accuracy boundary:** visual soft tear ≠ topology fracture; it does not create a new mesh topology, independent physical fragments, or FEM soft-body simulation.

## Generalization

M2-A asks whether STMS can describe a visually and structurally different soft translucent subject **without creating a second shader core**.

Current evidence says **yes, provisionally**:

- the shader core, Beer–Lambert absorption, spring oscillator, preset schema and MPB-based material path remain reusable;
- explicit subject binding is now implemented for the main runtime consumers;
- existing jelly preset and fracture evidence still pass after the binding change.

What is **not** complete yet:

- no validated jellyfish hero render is published;
- jellyfish bell / tentacle geometry has not passed compile + runtime + capture acceptance;
- the preset look path is still primarily single-renderer and needs a multi-renderer authoring pass;
- the current motion anchor model is floor-contact oriented;
- internal bubble / structure volumes are still spherical and origin-centred;
- thin/open-sheet subjects would need additional two-sided-normal / thickness work.

The latest unvalidated jellyfish geometry draft is intentionally excluded from the public evidence set until it passes the same compile, debug and capture gates.

## Visual Evidence

This showcase keeps the evidence set deliberately small:

1. **HERO** — optical comparison cover;
2. thickness-proxy debug;
3. screen-space refraction debug;
4. soft-tear / regeneration debug;
5. one recorded spring-motion GIF.

More implementation detail and evidence scope: [Technical overview](docs/technical-overview.md) · [Current status](docs/status.md) · [Media attribution](docs/media-attribution.md).

## Current Limitations

- scattering is an artistic approximation, **not physical SSS**;
- thickness is an analytic proxy, not a measured ray path;
- refraction is screen-space and does not provide full transparent-object mutual refraction;
- visual tear is shader/deformation driven, **not topology fracture**;
- the system is **not FEM soft-body simulation**;
- the first fully validated subject is still the konjac jelly; second-subject visual validation remains active research.

## Next Research Step

Complete the first evidence-backed jellyfish subject:

1. compile and validate the closed bell geometry with consistent winding / normals;
2. add closed tube tentacles and subject-specific profiles;
3. verify thickness, normals, motion weighting and renderer-role binding with debug captures;
4. validate multi-renderer preset look application without regressing the locked jelly evidence;
5. only then promote a jellyfish frame to the public HERO position.

## Distribution

Source/project distribution is not currently provided. This repository is a **showcase-only** research entry: no full Tuanjie/Unity project, Library/Temp/logs, agent data, internal report archive, third-party asset bundle or unreviewed media is distributed here.

No open-source license has been assigned to the project source.

Rendering context: **Tuanjie 2022.3.62t16 / Unity URP 14.2.0-t1**. Compatibility with other engine versions or graphics APIs is not claimed.

[Lilith — Portfolio](https://github.com/lilith-techart)
