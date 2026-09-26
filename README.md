# 4DRisk — Project Page

Project page for **4D Risk Assessment for Anticipated Safety Evaluation of Autonomous
Vehicle Behaviors**, submitted to *Reliability Engineering & System Safety*.

Live at <https://robosafe-lab.github.io/4DRisk/>.
Method code: <https://github.com/RoboSafe-Lab/Riskfield>.

A risk field indexed by two spatial dimensions, the prediction horizon, and the ego's
candidate behaviour. Risk stays factored into occurrence likelihood, an exact normalized
density from conditional normalizing flows, and consequence, a kinetic-energy-loss
severity in joules — so candidate ego actions can be ranked before one is taken.

## Repository layout

Static site, no build step.

| Path | Contents |
| --- | --- |
| `index.html` | the whole page — embedded CSS, Google Fonts from CDN, vanilla JS |
| `static/images/` | method diagram, qualitative risk fields, precision–recall curves, four-readout comparison |
| `static/videos/` | risk-field animations for InD, AD4CHE ×2 and rounD, plus the three counterfactual maneuvers, H.264 MP4 |
| `.nojekyll` | stops GitHub Pages running Jekyll over the static files |

## Publishing

GitHub → **Settings → Pages → Source: deploy from branch → `main` / root**. A push to
`main` republishes within a minute or two.

## Keeping the page honest

The results table and the figures mirror the manuscript, so the two drift apart easily.
When a number in the paper changes, check all of:

- the detection table — AUROC, AP and **Warn**, the share of all conflicts alarmed before
  the encroachment begins at a matched 10% false-alarm budget
- the conflict counts and base rates in the table caption
- `static/images/pr_curves.png` and `static/images/qual_compare.png`, both regenerated
  from `scripts/fig_pr.py` and `scripts/qual_compare.py` in the method repo
- the closing paragraph under the table, which states which regimes the field wins and
  which it does not

EDRF is reported with one correction to its published readout, noted on the page. Its
trajectory-relative projection assigns every cell behind a predicted path the peak
amplitude of the whole tube, so the scene maximum is frequently attained on road a
vehicle has already left.

## Still to fill

The **Paper** button in the hero links to `#`. Point it at the DOI or preprint once the
manuscript is live, and update the `journal` field of the BibTeX block near the bottom
of `index.html`, which currently reads `Preprint`.
