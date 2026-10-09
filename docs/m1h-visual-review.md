# M1-H / Visual Review

**2026-10-09** · Curated technical-art review · **Final visual approval pending**

The human-review worktree includes the original selected PNGs, videos, diagnostic captures and checksums. This public page publishes a small verified selection under [media/m1h](../media/m1h/README.md), with the source attribution preserved.

## Hero / motion selection

<table>
<tr><td width="50%"><a href="../media/m1h/hero-product.png"><img src="../media/m1h/hero-product.png" width="100%" alt="Clean product view"/></a><br/><sub>Actual M1-H Hero A — current clean-product candidate</sub></td>
<td width="50%"><a href="../media/m1h/macro-study.png"><img src="../media/m1h/macro-study.png" width="100%" alt="M1-H close-up study"/></a><br/><sub>Actual M1-H Hero B — microdetail gate not met</sub></td></tr>
</table>

**Moving images:** [Living Cloud hero candidate](../media/m1h/living-cloud.mp4) · [Damage & Recovery](../media/m1h/damage-recovery.mp4) · [Fracture & Regeneration](../media/m1h/fracture-regeneration.mp4).

**Four profiles:** [real multi-view Material Gallery](../media/m1h/preset-gallery.webp).

## Why M1-H is still a research checkpoint

1. **Surface microstructure — NOT MET.** All eight macro candidates failed the project threshold (macro 0.00063–0.00096 vs floor 0.0010). Product framing and lighting improved, but the shader/authoring pipeline did not gain believable finer surface content.
2. **Local contact — VISUAL FAIL.** Pressure reached 0.45 and contactDepth 0.0293; the rendered dynamic diagnostic kept a constant 233,225 body pixels with 141/150 consecutive pairs unchanged. This is a major blocker to tactile believability.
3. **Internal appearance — NEEDS POLISH.** Pulp appears as separate translucent/plastic blocks and the bubble population often reads as flat rings.
4. **Damage / Recovery — PARTIAL.** Real continuous animation, closes its rest state accurately, but transitions and the direct finger press are weak. Damage uses haze/thinning/highlight suppression, not a pigmented bruise.
5. **Fracture / Regeneration — LIMITATION.** A field-driven notch and separation on one mesh; not a topological tear. Transparent sorting limits visual clarity. Abrupt rupture is visible over one exported frame.
6. **Formation / growth — NOT ACCEPTED.** A separate concept study, not a shipped growth feature; deliberately not bundled as an M1-H portfolio success.
7. **GPU — UNMEASURED.** CPU and readback/synchronization timings cannot be translated into GPU milliseconds or shipping frame rate.
8. **Historical regressions — OPEN.** All 19 historic collectors executed without C# or Shader errors but 66 locked rendered files did not reproduce byte-identically, pending root-cause classification.

## Next research iteration

- **P0:** Preserve uncommitted M1-H source evidence and classify the 66-file regression drift.
- **P1:** Fix contact-path visual reachability (dent, bulge, soft return) before another lifecycle beauty shoot.
- **P2:** Validate authored micro-normal/roughness control and richer interior depth without altering canonical profiles.
- **P3:** Reassess the art-direction heroes after those actual material improvements.

**Do not treat GIF generation, a clean regression collector, or a polished README as artistic acceptance.** Human visual verdicts remain pending.
