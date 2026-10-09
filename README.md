<p align="center"><img src="media/stms-title.svg" width="100%" alt="STMS — Soft Translucent Material System, technical art research title"/></p>

<p align="center"><strong>Soft, wet, light-carrying matter — engineered and art-directed in real time.</strong></p>

<p align="center"><sub>Unity / Tuanjie · URP 14.2 · Real-time rendering · Procedural materials · Soft-body interaction</sub></p>

<p align="center"><img src="media/jelly-hero.png" width="940" alt="Actual STMS jelly render with translucent purple gel, wet highlights and internal inclusions"/></p>
<p align="center"><sub>Actual engine capture from the validated Jelly baseline. No synthetic Unity screenshots.</sub></p>

<p align="center">
  <a href="#the-material">THE MATERIAL</a> ·
  <a href="#motion--interaction">MOTION</a> ·
  <a href="#material-identities">PRESETS</a> ·
  <a href="#m1-h--visual-research">M1-H REVIEW</a> ·
  <a href="#architecture--technical-evidence">ENGINEERING</a>
</p>

---

## An authored material, not a one-off effect

**STMS — Soft Translucent Material System** is a reusable technical-art research framework for expressing translucent, deformable matter with one shader core and a set of material, motion, damage, bubble and contact profiles.

> **Research question**  
> How can one real-time rendering and deformation architecture describe multiple soft, translucent subjects without building a separate shader for each one?

The first subject is a fruit / konjac jelly. The next subject, a jellyfish, is a separate **in-progress generalization test**, not a published validated visual result.

<table>
<tr>
<td width="50%" align="center"><img src="media/internal-structure.png" width="100%" alt="Real close-up of translucency, pulp and internal structure"/><br/><sub><strong>01 / Internal structure</strong><br/>Pulp, volume cues and bubbles inside a translucent shell</sub></td>
<td width="50%" align="center"><img src="media/jelly-optics-cover.png" width="100%" alt="Real multi-angle optical study"/><br/><sub><strong>02 / Optical study</strong><br/>The same subject across controlled viewpoints</sub></td>
</tr>
</table>

## The material

Thickness-driven absorption, screen-space refraction, Fresnel, artistic scattering and a wet highlight form the optical base. The art direction values *thick, coloured gel and light-transmitting edges*, rather than a polished glass ball.

<table>
<tr>
<td width="50%" align="center"><img src="media/thickness-proxy.png" width="100%" alt="Real analytic thickness channel"/><br/><sub>Analytic thickness debug</sub></td>
<td width="50%" align="center"><img src="media/refraction-debug.png" width="100%" alt="Real checker-backed refraction debug"/><br/><sub>Screen-space refraction check</sub></td>
</tr>
</table>

<sub>These are authored approximations, **not** measured physical thickness, multi-layer refraction or a physical subsurface-scattering simulation.</sub>

## Motion & interaction

<p align="center"><img src="media/spring-motion.gif" width="700" alt="Actual frame-recorded spring motion showing jelly overshoot and damping"/></p>
<p align="center"><sub><strong>Recorded engine motion</strong> · spring wobble, overshoot and settle.</sub></p>

The framework includes drag, collision response, local contact, damage/recovery and visual fracture. However, M1-H's closer review found that **local finger contact is not yet convincing in the rendered picture**, even though pressure and contact parameters change. Motion implementation and visual readability are different acceptance tests.

## Material identities

<p align="center"><img src="media/preset-lineup.png" width="940" alt="Actual four-preset jelly comparison in controlled lighting"/></p>
<p align="center"><sub>Balanced Fruit · Clear Konjac · Cloud Jelly · Firm Clear Gel — shared architecture, authored profiles.</sub></p>

A single core provides different soft-material identities through ScriptableObject profiles and per-renderer material property blocks. Some identities remain too similar at Hero distance in greyscale; the showcase does not claim every preset is instantly distinguishable.

---

## M1-H / Visual research

<p align="center"><img src="media/m1h-review-map.svg" width="940" alt="Research verdict graphic: presentation improved, microstructure not met, lifecycle partial"/></p>

**Latest reviewed checkpoint: M1-H — Jelly Final Art & Lifecycle, 2026-10-09.** The engineering capture and human-review package are complete; **final visual approval has not been granted**.

| Goal | What the tests actually established |
| --- | --- |
| Clean studio hero | Real captured and reproducible, awaiting artistic selection |
| Surface micro-detail | **Not met** — all 8 macro candidates missed the project-defined contrast gate |
| Interior appearance | **Needs polish** — pulp reads as separate blocks; bubbles often as flat rings |
| Local contact | **Visual limitation** — parameters move; many successive frames do not |
| Damage → Recovery | **Partial** — real animation and return-to-rest, weak transition readability |
| Soft fracture → Regeneration | **Partial** — one mesh, no true tear; transparency/sorting boundary remains |
| Formation / Growth | **Concept only, not accepted** — must not be described as a finished growth system |
| GPU performance | **Unmeasured** — CPU and synchronization measurements are not GPU times |

The M1-H review intentionally distinguished **successful reproducible captures** from **an approved final look**. See the [visual findings and next-step priorities](docs/m1h-visual-review.md).

> **Visual study disclosure**  
> The photographs above are selected *existing repository engine captures* and are preserved without beauty retouching. The new M1-H high-fidelity capture package is undergoing a separate provenance-preserving media sync; this page will show those specific frames only after the files themselves are published. The status text already reflects the M1-H evidence.

## Damage / fracture study

<table>
<tr>
<td width="50%" align="center"><img src="media/soft-tear.png" width="100%" alt="Real single-mesh visual soft tear"/><br/><sub>Soft tear — single mesh, field-driven visual separation</sub></td>
<td width="50%" align="center"><img src="media/soft-tear-debug.png" width="100%" alt="Real fracture partition and seam debug views"/><br/><sub>Partition · Seam · Regeneration debug channels</sub></td>
</tr>
</table>

The effect does **not** split topology, make separate rigid pieces, or use FEM. The original first-glance tear target was not achieved under the current single-pass unsorted transparent shell constraints. This is a measured limitation, not an unreleased success.

## Architecture & technical evidence

```mermaid
flowchart LR
  A["Material / Motion / Contact /<br/>Damage / Bubble profiles"] --> P["STMS preset + runtime binding"]
  P --> MPB["Per-renderer MaterialPropertyBlock"]
  MPB --> SH["STMS/Core<br/>thickness · absorption · refraction<br/>wet spec · artistic scatter"]
  R["Spring + local contact + damage"] --> MPB
  SH --> E["Beauty captures / debug views<br/>regression & determinism evidence"]
  E -.->|controlled review| A
```

**Engineering principles:** controlled candidate comparisons, stable evidence hashes, independent editor reruns, original-profile immutability, explicit technical limits. M1-H produced authentic 30-fps encoded sequences from 1/120-s simulation steps and captured renders — not generated intermediate frames.

**Open engineering issue:** the M1-H historical regression ran 19/19 collectors without C#/shader errors, yet **66 locked rendered files did not reproduce byte-identically**. They are not silently re-locked or declared passed.

**Current research tracks:**
- **Jelly:** M0–M1-G capabilities established; M1-H final-art review shows explicit visual gaps.
- **Jellyfish / M2-A:** second-subject generalization is in progress; no final validated result is claimed on this page.
- **Jelly Island × Water:** concept direction only. Integration readiness is **not met**; scale-aware thickness, transparency authority, runtime binding, assembly boundaries and GPU timing remain prerequisites.

Read more: [Technical breakdown](docs/technical-overview.md) · [Milestone status](docs/status.md) · [M1-H visual review](docs/m1h-visual-review.md) · [Media attribution](docs/media-attribution.md).

---

<p align="center"><strong>STMS / Technical Art R&amp;D</strong><br/><sub>One shader core · authored identities · measurable evidence · visible limitations</sub></p>

<sub>**Distribution:** public showcase and selected renders only. The Unity/Tuanjie project files, source assets, private evidence archives and third-party content are not redistributed. No open-source license is granted to the engine project. Tested context: Tuanjie 2022.3.62t16 / URP 14.2.0-t1.</sub>
