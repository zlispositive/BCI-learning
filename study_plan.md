# Brain–Computer Interface (BCI) Study Plan — Copy-Ready Checklist

A blunt, practical roadmap to pivot from OR/control/signal processing into BCI. Start with code, data, and math; produce tangible artifacts; iterate based on feedback.

---

## How to use this plan

* Check off items as you complete them.
* Fill in each `Completion date:` and jot 1–2 lines in `Feedback / plan updates:` so we can adjust scope quickly.
* If you fall behind, cut scope the following week rather than stacking tasks.

Status legend:

* [ ] Not started \[\~] In progress \[x] Done


---

## Week 1 — Foundations you can execute now (explicit resources)

**Objectives:** get the tooling working; complete your first EEG pipeline pass; start one structured course.

* [ ] Create repo `bci-journey` with folders: `notebooks/`, `data/`, `src/`, `reports/`, `docs/`
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

* [ ] Install Python env and MNE-Python; verify with `mne.sys_info()`
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

* [ ] MNE Tutorials (finish these 3 and save each as a notebook in `notebooks/`)

  * [ ] “EEG processing overview”
  * [ ] “Filtering + artifact removal (ICA/SSP)”
  * [ ] “Epochs + ERPs (event-related potentials)”
    Completion date: \_\_\_\_\_\_\_\_
    Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

* [ ] Course: “Computational Neuroscience” (UW on Coursera) — Week 1 videos + quiz
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

* [ ] Reading (skim, not deep dive): Dayan & Abbott — Poisson spikes, GLMs (keep notes in `docs/notes-week1.md`)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

* [ ] Download BCI Competition IV–2a dataset; write a loader that returns `(X, y)` per subject
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

* [ ] Draft pipeline skeleton for motor imagery: band-pass (8–30 Hz) + notch → CSP → LDA; commit with a CLI entry point
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

**Resource box (fill in links you choose to use):**

* MNE-Python tutorials — link: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Course (Computational Neuroscience, UW) — link: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Dayan & Abbott (Theoretical Neuroscience) — link: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* BCI Competition IV–2a — link: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

---

## Weeks 2–12 (3-month plan) — Concrete weekly checklists

### Week 2 — Solidify preprocessing and baselines

* [ ] Finish CSP+LDA baseline per subject with 5× CV; record accuracy + CI
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Add SVM (linear) baseline; compare to LDA
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Course: Week 2 (neuron models, coding exercises)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 3 — Robustness + documentation

* [ ] Implement train/val/test split by session to expose non-stationarity
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Add simple CNN baseline (1D conv); document all hyperparameters
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Write `README` with dataset, metrics, and pitfalls (data leakage)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 4 — Cognitive-control on-ramp (ERN)

* [ ] Identify a public ERN/FRN dataset OR script a simple flanker/go-no-go task
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] MNE ERP pipeline: epoch around errors, compute ERN; plot grand average
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Course: Week 3 (population coding / decoding)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 5 — Single-trial ERN decoding

* [ ] Features: time–frequency (Morlet) around 0–150 ms post-error; classifier: regularized LR
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Sanity metrics (AUROC, PR-AUC) + permutation test
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 6 — Packaging + evaluation discipline

* [ ] Create `src/bci_utils/` with: filtering, epoching, ERP, metrics; add unit tests
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Add confidence intervals via bootstrap; export results table to `reports/`
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 7 — Write and review

* [ ] Draft 2–3 page technical note: ERN pipeline, figures, failure modes
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Ask 1–2 peers for code/notes review; integrate feedback
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 8 — Motor-imagery repo polish

* [ ] Finalize `eeg-motor-imagery-baselines` repo: badges, clear `README`, `make reproduce` script
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 9 — Transfer learning hooks

* [ ] Add cross-subject experiments (leave-one-subject-out)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 10 — Error-monitoring deepening

* [ ] Compare ERN across conditions; add within-subject reliability analysis
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 11 — Presentation

* [ ] 10-slide deck summarizing motor imagery + ERN results; dry run 10 minutes
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Week 12 — 3-month milestone

* [ ] Publish repo #1 and the ERN note; write a 1-page retrospective (what worked, what didn’t)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

**3-Month Deliverables checklist**

* [ ] Repo #1: `eeg-motor-imagery-baselines` (with results/CI)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] ERN technical note (PDF in `reports/`)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

---

## Months 4–6 (mid-term) — State-space decoders + reusable pipeline

### Month 4

* [ ] Implement linear Kalman filter (LKF) cursor decoder on a public dataset
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Evaluate latency vs. accuracy; add steady-state KF variant
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Month 5

* [ ] Add RNN/LSTM baseline; same splits; compare to LKF
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Start packaging: `bci-pipeline` (pip-installable), with config files and tests
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Month 6

* [ ] Write tutorial article: “From CSP to Kalman: a pragmatic path into BCI decoding”
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] 20-min talk deck (ERN + decoders); record a dry-run video
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Repo #2: `state-space-decoders-for-neural-signals` published
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

**6-Month Deliverables checklist**

* [ ] Repo #2 (LKF + RNN, rigorous eval)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Tutorial article live
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Talk deck ready
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

---

## Months 7–12 (long-term) — Specialize, contribute, collaborate

### Choose one specialization lane (pick now; revisit at Month 9)

* [ ] Robustness to non-stationarity
* [ ] Real-time pipelines (latency budgets, monitoring)
* [ ] Cognitive-control signals (ERN/FRN for closed loop)
  Chosen lane: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Month 7–8

* [ ] Add domain adaptation / continual learning OR real-time streaming to `bci-pipeline`
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Contribute a small PR/example to MNE or related libs
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Month 9 — Collaboration starter

* [ ] Draft a 1-page IRB-friendly tooling proposal (e.g., ERN QC dashboard) aligned to human neurophysiology workflows
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Build a minimal demo on public data; share for feedback
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Month 10–11

* [ ] Prepare a workshop/poster submission (keep scope tight, fully reproducible)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Iterate `bci-pipeline` docs; add two exemplar notebooks (motor imagery + ERN)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

### Month 12 — Year milestone

* [ ] Release v1.0 of toolbox (pip/conda)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Public talk or poster delivered
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] “Position statement” page (your niche + evidence)
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

**12-Month Deliverables checklist**

* [ ] Polished toolbox + exemplars
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Public talk/poster
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_
* [ ] Collaboration artifact adopted by another group
  Completion date: \_\_\_\_\_\_\_\_
  Feedback / plan updates: \_\_\_\_\_\_\_\_\_\_

---

## Feedback & Iteration Log (use this every 1–3 weeks)

* Date: \_\_\_\_\_\_\_\_\_\_ | Scope reviewed: Week(s) \_\_\_\_ | What worked: \_\_\_\_\_\_\_\_\_\_ | What didn’t: \_\_\_\_\_\_\_\_\_\_ | Decision(s): \_\_\_\_\_\_\_\_\_\_ | Next change to plan: \_\_\_\_\_\_\_\_\_\_

* Date: \_\_\_\_\_\_\_\_\_\_ | Scope reviewed: Week(s) \_\_\_\_ | What worked: \_\_\_\_\_\_\_\_\_\_ | What didn’t: \_\_\_\_\_\_\_\_\_\_ | Decision(s): \_\_\_\_\_\_\_\_\_\_ | Next change to plan: \_\_\_\_\_\_\_\_\_\_

* Date: \_\_\_\_\_\_\_\_\_\_ | Scope reviewed: Week(s) \_\_\_\_ | What worked: \_\_\_\_\_\_\_\_\_\_ | What didn’t: \_\_\_\_\_\_\_\_\_\_ | Decision(s): \_\_\_\_\_\_\_\_\_\_ | Next change to plan: \_\_\_\_\_\_\_\_\_\_

---

## Evidence & Artifacts Index (paste links or paths)

* Repo #1 (motor imagery baselines): \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* ERN note (PDF): \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Repo #2 (state-space decoders): \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Tutorial article: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Talk deck: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Toolbox (pip/conda): \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
* Public talk/poster link: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

---
