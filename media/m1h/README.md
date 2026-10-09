# M1-H / Curated Visual Evidence

The files in this directory are selected **real Unity/Tuanjie captures** from the M1-H human-review package. The original source files were not edited to change the rendered material, geometry, state, or motion.

The authoring and source review package remains the canonical evidence. Public display is **not** a final visual acceptance verdict.

## Original, byte-identical captures

| Public file | Source review-package path | Source MD5 |
|---|---|---|
| [hero-product.png](hero-product.png) | `02_Hero_A_B/Hero_A_Product.png` | `7b179b2574e632f07ba2f92ebb6649f1` |
| [macro-study.png](macro-study.png) | `02_Hero_A_B/Hero_B_Macro.png` | `ced363c92ae9a20a8d58ac46cea5fc3a` |
| [m1e-vs-m1h.png](m1e-vs-m1h.png) | `02_Hero_A_B/M1E_vs_M1H_MatchedCrops.png` | `1be052b76b41b9de3a0c7b5b50fc7dc3` |
| [living-cloud.mp4](living-cloud.mp4) | `03_Hero_C_option1_CloudJelly/HeroC_option1_CloudJelly.mp4` | `1cd9960949f963c64201d8c2ad765bb1` |
| [damage-recovery.gif](damage-recovery.gif) | `05_Lifecycle_TrackA/TrackA_DamageRecovery.gif` | `1fb968cea68e34c5ecf646fe8176c055` |
| [damage-recovery.mp4](damage-recovery.mp4) | `05_Lifecycle_TrackA/TrackA_DamageRecovery.mp4` | `bae4fc7dd533fcb01f5b20a9d018a163` |
| [fracture-regeneration.gif](fracture-regeneration.gif) | `06_Lifecycle_TrackB/TrackB_FractureRegeneration.gif` | `1895fef9a3809dd4759dd6151691171f` |
| [fracture-regeneration.mp4](fracture-regeneration.mp4) | `06_Lifecycle_TrackB/TrackB_FractureRegeneration.mp4` | `35dd846c5bfc129c699f103c16cc411b` |

**Each original binary Git blob SHA was checked against its locally computed blob SHA before publishing.**

## Web display derivatives

| File | Derivation | Published SHA-256 |
|---|---|---|
| [preset-gallery.webp](preset-gallery.webp) | Source: `08_Material_Gallery_4Presets/MaterialGallery_4Presets.png`, resized to 1600 × 697, Pillow Lanczos, WebP quality 84 | `61c23b1aa572e652f8fb1502398c7ca39bb6d72d483deca07210b96bf6a1a65b` |
| [m1e-vs-m1h.webp](m1e-vs-m1h.webp) | Source: `02_Hero_A_B/M1E_vs_M1H_MatchedCrops.png`, original 1048 × 1084, WebP quality 84 | `c91af5f3c24407a98d76608ed959d4c3409ae5e6c6bd8d8832479847d4fbdb87` |

WebP derivatives are **display optimizations**, not replacements of study originals. The gallery's 5.5 MB full-resolution PNG stays in the original M1-H source package; its public derivative is 23.7 KB.

## Review verdicts

- Hero A: acceptable clean-product candidate, **not human-selected final cover**.
- Macro: documentation of failed microstructure target, not proof of superior close-up material detail.
- Living Cloud: one temporal warning, rests at end, **candidate**.
- Damage/Recovery: real render loop, local press remains weak.
- Fracture: field-driven one-mesh representation, sorting/readability limitation.
- Four-preset gallery: different authored identities; some similarities remain at Hero distance.

Status: `M1-H ENGINEERING READY FOR HUMAN REVIEW`. Do not rewrite to `VISUAL PASS` without a reviewer decision.
