# Media attribution / 发布范围

Only the project's own renders are published. Every image is a byte-identical copy of a committed calibration or hero capture in the research repository (verified by checksum), produced by the project's own Editor capture harness from procedurally generated geometry and authored profiles. No engine assets, third-party artwork, stock photography, course material or AI-generated reference is included.

| Published file | Class | Source capture | Milestone |
| --- | --- | --- | --- |
| `media/jelly-hero.png` | OWN_RENDER | Hero rig, three-quarter camera, final visual polish pass | M1-E |
| `media/internal-structure.png` | OWN_RENDER | Hero rig macro camera, pulp + bubble + internal noise visible | M1-E |
| `media/preset-lineup.png` | OWN_RENDER | Preset lineup capture, four authored presets, fixed camera and lighting | M1-F |
| `media/soft-tear.png` | OWN_RENDER | Canonical soft-tear profile, broken lifecycle frame | M1-G |
| `media/soft-tear-debug.png` | OWN_RENDER | Partition / seam / regeneration debug channels, canonical profile | M1-G |
| `media/thickness-proxy.png` | OWN_RENDER | Analytic thickness debug view, candidate calibration set | M0-A/R2 |
| `media/refraction-debug.png` | OWN_RENDER | Screen-space refraction debug view, procedural checker backdrop | M0-A/R2 |
| `media/spring-motion.gif` | OWN_CAPTURE | Recorded deterministic spring motion, medium motion profile | M1-A |
| `media/jelly-optics-cover.png` | OWN_RENDER | Multi-view optical study, calibration backdrop | M0-D |
| `docs/validation-frame.png` | OWN_RENDER | Laboratory calibration frame used for sorting / geometry checks | M1-E |

Rights: all entries are the project's own work (`OWN_RENDER` / `OWN_CAPTURE`). Unity, Tuanjie and related third-party technology remain the property of their respective owners; this repository redistributes no engine or package content and grants no new license over third-party material.

No open-source license is assigned to the project source. Publishing these images is a presentation decision, not a source release.

Course files, third-party references and unreviewed AI-generated references: **not published** (`NEEDS_RIGHTS_REVIEW` by policy — anything whose provenance is not established stays out of this repository).

## Correction record (2026-10-07)

`media/soft-tear-debug.png` previously pointed at a debug sheet generated from a **validation-only** tear candidate rather than the canonical profile. It has been replaced with the canonical-profile sheet so the published debug evidence matches the published behaviour. The superseded file remains in this repository's Git history; no other media changed meaning.
