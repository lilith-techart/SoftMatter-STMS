# M1-H curated media — safe publishing handoff

**Purpose:** publish a small, attractive *selection of original Unity/Tuanjie evidence* under `media/m1h/` without altering the source worktree or falsely approving M1-H visually.

**Repository:** `lilith-techart/SoftMatter-STMS` · `main`. This is a showcase repository, not the Unity project. The artwork is a derived public presentation selection.

**Source package:** `M1H_HumanReview_Package` from the independent `unity_SoftMatter_jelly_M1H` worktree. A 9-file, 9.6 MB curated ZIP exists separately; it includes the original bytes and their SHA-256/MD5 provenance.

## Source → target mapping (do not rename the source originals)

| M1-H HumanReview relative path | Publish as | Role |
|---|---|---|
| `02_Hero_A_B/Hero_A_Product.png` | `media/m1h/hero-product.png` | Main M1-H clean-product candidate |
| `02_Hero_A_B/Hero_B_Macro.png` | `media/m1h/macro-study.png` | Macro R&D evidence, **not** validated enhanced microdetail |
| `02_Hero_A_B/M1E_vs_M1H_MatchedCrops.png` | `media/m1h/m1e-vs-m1h.png` | Honest before/after matched crops |
| `03_Hero_C_option1_CloudJelly/HeroC_option1_CloudJelly.mp4` | `media/m1h/living-cloud.mp4` | Recommended motion candidate, not a declared winner |
| `05_Lifecycle_TrackA/TrackA_DamageRecovery.gif` | `media/m1h/damage-recovery.gif` | Damage/recovery visual |
| `05_Lifecycle_TrackA/TrackA_DamageRecovery.mp4` | `media/m1h/damage-recovery.mp4` | Full video |
| `06_Lifecycle_TrackB/TrackB_FractureRegeneration.gif` | `media/m1h/fracture-regeneration.gif` | Single-mesh fracture with explicit readability limitation |
| `06_Lifecycle_TrackB/TrackB_FractureRegeneration.mp4` | `media/m1h/fracture-regeneration.mp4` | Full video |
| `08_Material_Gallery_4Presets/MaterialGallery_4Presets.png` | `media/m1h/preset-gallery.png` | Four-preset actual capture |

## Local agent execution contract

1. Verify exact repo root, `git branch --show-current`, `git status --short`, `git rev-parse HEAD`, remote URL, and no existing unrelated local changes. Work in a **separate showcase checkout**.
2. Verify the nine source paths exist in the M1-H HumanReview package; compare MD5 with `MANIFEST.csv` for each entry. If any differ, **STOP**. This is a per-file proof of source authenticity.
3. Copy only the listed nine files to `media/m1h/`. No AI replacement images, no artificial interpolation and no edit of the source files. Generate `media/m1h/provenance.json` with source path, published filename, MD5, SHA-256, bytes, category and **`VISUAL=PENDING_HUMAN`**.
4. Update `README.md` within its M1-H review section **after files exist**, keeping the previously published header and other image paths intact. Suggested GitHub Markdown markup follows. On a narrow screen use full-width rows rather than cropped thumbnails. Avoid extra large autoplay loops at the top of the page.
5. Optionally make *additional*, explicitly labelled web-optimized derivatives (e.g. WebP thumbnails) without overwriting these nine byte-identical original assets. Verify original md5 and derivatives separately. Never claim a retouched/generative shot is an engine render.
6. `git add README.md media/m1h/ docs/m1h-visual-review.md` only. Never `git add -A` in a shared workspace. Verify staged diff, commit as `docs(showcase): publish curated M1-H engine renders`, then ordinary `git push origin main`. **No force, no history rewrite.**
7. Reopen `README.md` on GitHub and check every image/video link after the push. If media is too heavy for fast README loading, move the GIFs below the first screen, keep MP4s as click links, and generate reversible thumbnails.
8. Never edit `Assets/`, `Docs/Screenshots/Calibration/`, `ProjectSettings/`, Unity/M2-A/Water code, or historical evidence in this publishing task.

### Gallery markup (only after media upload)

```html
<table>
<tr>
  <td width="50%" align="center"><img src="media/m1h/hero-product.png" width="100%" alt="M1-H Hero A actual product render"/><br/><sub><b>M1-H · Clean Product</b><br/>Curated engine render · visual review pending</sub></td>
  <td width="50%" align="center"><img src="media/m1h/macro-study.png" width="100%" alt="M1-H macro study, micro detail gate not met"/><br/><sub><b>Macro Study</b><br/>Micro-detail requirement not met</sub></td>
</tr>
<tr>
  <td width="50%" align="center"><img src="media/m1h/m1e-vs-m1h.png" width="100%" alt="M1-E and M1-H matched camera crop comparison"/><br/><sub>Honest matched crop · presentation changed, surface not yet refined</sub></td>
  <td width="50%" align="center"><img src="media/m1h/preset-gallery.png" width="100%" alt="Four material profiles"/><br/><sub>Four authored presets · one capture rig</sub></td>
</tr>
</table>
<p align="center"><img src="media/m1h/damage-recovery.gif" width="450" alt="Real Unity damage recovery animation"/></p>
<p align="center"><sub>Damage / Recovery — real captured frames, weak local press remains</sub></p>
<p align="center"><a href="media/m1h/living-cloud.mp4">Living Jelly hero candidate (MP4)</a> · <a href="media/m1h/fracture-regeneration.mp4">Soft Fracture &amp; Regeneration (MP4, visual limitation)</a></p>
```

## Disclosure to retain publicly

`M1-H ENGINEERING DELIVERABLES READY; FINAL VISUAL PASS NOT GRANTED.`

In particular do not hide: 8/8 micro-detail failures, weak local contact, partial lifecycle legibility, one-mesh fracture with sorting limits, unaccepted formation, unmeasured GPU time, and 66 unresolved locked-render regression differences.

**STOP once the public page loads correctly.** This publishing job does not authorize another rendering-development milestone.
