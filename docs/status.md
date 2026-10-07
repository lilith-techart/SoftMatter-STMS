# STMS — Status

Updated 2026-10-07. **Overall: research prototype, in development.**

Status vocabulary is fixed: `PASS` (implemented + recorded acceptance run) · `PARTIAL` (implemented, named untested path) · `WIP` (actively being built) · `FAIL` (attempted and rejected) · `NOT STARTED` · `UNVERIFIED` (exists, no evidence it works).

## Current milestone

**M2-A Phase 1 — generalization foundation.** The milestone question is whether the existing architecture can carry a second, structurally different soft translucent subject without a second shader core.

M2-A is no longer a single "WIP". It splits:

- **Generalization infrastructure — PARTIAL / verified-inert.** An explicit subject-binding layer (renderer membership, roles, optional per-renderer body metrics) is implemented across the motion, contact, fracture-role, breakage, bubble-field and internal-noise consumers, with the pre-existing fallback path preserved. Headless verification: 0 C# errors, 0 shader errors, 0 exceptions; preset live re-apply 0 failures in two independent processes; fracture lifecycle gate `PASS`. The binding is therefore proven *not to change* current behaviour — the positive path on a real second subject is still untested, which is why this row is `PARTIAL` and not `PASS`.
- **Jellyfish visual subject — WIP / UNVERIFIED.** Bell mesh generation code exists as a local draft only: it has not been imported or compiled by the editor, has no call sites, and no geometry validation has been run. There are no tentacles, no jellyfish material or motion profile, and **zero captured jellyfish frames**. No jellyfish image is published here.

## Subsystem matrix

| Subsystem | Status | Evidence basis |
| --- | --- | --- |
| Optical core (single pass, one CBUFFER) | PASS | M0-A calibration sweeps; re-run in later regression passes |
| Analytic thickness proxy | PARTIAL | Validated as a proxy on convex closed bodies; boundary recorded for thin/open tissue |
| Beer–Lambert absorption | PASS | M0-A absorption variant captures, authored per material profile |
| Screen-space refraction | PASS | Checker calibration captures; limitation recorded, not solved |
| Wet highlight | PASS | Specular variant captures, hero frames |
| Artistic back-scattering | PASS (approximation) | Scatter variant captures; explicitly not physical SSS |
| Spring motion | PASS | M1-A damped sweeps, curve CSVs, recorded GIF/MP4 per profile |
| Drag / collision interaction | PASS | M1-B grab → drag → overshoot → settle sequence |
| Local contact deformation | PASS | M1-C directional contact captures + containment checks |
| Damage lifecycle | PASS | M1-D press/damage/recovery timeline with per-frame CSV |
| Visual soft tear + regeneration | PASS | M1-G lifecycle frames, debug channels, 20-frame lifecycle gate |
| Soft-tear first-glance readability | FAIL (parked) | Measured on the broken frame: no candidate produced a readable central opening; canonical profile left unchanged, awaiting human review |
| Material / motion profile authoring | PASS | Authored profile assets + identity comparisons |
| Preset system | PASS | M1-F preset identity, lineup, determinism and live re-apply CSVs |
| Subject binding | PARTIAL | Implemented; verified inert (compile, preset, fracture regressions) |
| Multi-renderer distribution (motion/contact/fracture) | PASS | The jelly rig already drives 5–8 renderers through one push loop |
| Multi-renderer preset look application | PARTIAL | Resolves a single renderer; deliberately deferred to avoid changing frozen apply semantics |
| Jelly baseline (case study) | PASS | Full M0-A → M1-G evidence chain, used as the regression reference |
| Jellyfish bell | UNVERIFIED | Local draft code only; never compiled, validated or rendered |
| Jellyfish tentacles | NOT STARTED | No code |
| Jellyfish material profile | NOT STARTED | No asset |
| Jellyfish motion | NOT STARTED | No profile, no capture |
| Jellyfish capture | NOT STARTED | Zero frames |
| Second-subject generalization | WIP | The remaining work of this milestone |

## Recorded generalization boundaries

- Transparent siblings cannot refract each other: the opaque texture is captured before transparents render.
- The motion anchor model is a floor-contact model; geometry below the anchor receives no lean, so a floating subject behaves as near-rigid translation unless anchors are authored per renderer.
- Internal structure volumes are spherical and origin-centred.
- The thickness proxy assumes a convex closed body; closed tubes are its best case, open ribbons its worst.
- Thin or open-sheet tissue would need two-sided normal handling that the single `Cull Back` pass does not provide.

## Accuracy boundaries

Scattering is not physical SSS. Thickness is not a measured optical path. Refraction is screen-space. Visual tear is not topology fracture. The system is not FEM soft-body simulation. No production-readiness, cross-engine compatibility, or GPU benchmark claim is made.

## Distribution

Showcase only: selected documentation and rendered evidence. The engine project, source, packages, logs, internal research archives and agent data are not distributed, and no source license is granted.
