# Movie Memory Analysis Summary

## Data Inputs and Preprocessing
- **Demographics:** `Demographic data.xlsx` supplied age, gender, handedness, and vision metadata. Columns were standardized and merged back to participant IDs (AB/NB) for descriptive stats and regressions.
- **Recognition Trials:** All CSVs in `BRSM data csv/` were concatenated, filtered for rows with valid recognition responses, and tagged with target types (BB = before-boundary frames, EM = event-middle frames).
- **Derived Metrics:** Response-time scalars were flattened from PsychoPy outputs, participant-level accuracy/confidence summaries were computed, and demographic features were joined to these summaries. Vigilance windows were calculated from `instruction_2.stopped` → `Videos.stopped` timestamps with a 27.05 min attentiveness ceiling (21.45 min base + 5.6 min repeats + 5 × 25 s skip buffer).

## Figure Guide (analysis_plots/)
1. **demographics_overview.png** – Violin plot of age plus stacked bar charts for gender and vision distributions across AB vs NB groups.
2. **recognition_accuracy.png** – Participant-level mean accuracy by condition and target type, highlighting BB vs EM performance spread.
3. **confidence_by_condition.png** – Confidence ratings (1–5) grouped by condition and target type, revealing higher certainty for natural cuts.
4. **recognition_dashboard.png** – Three-panel view: accuracy bars, response-time boxes (correct vs incorrect), and confidence boxes to compare full recognition dynamics.
5. **demographics_vs_recognition.png** – Regression plots mapping age onto accuracy, median RT, and confidence; slopes are shallow, indicating minimal age effects.
6. **demographic_effects.png** – Bar charts showing how gender × condition pairs differ on mean accuracy, RT, and confidence metrics.
7. **encoding_vigilance.png** – Counts of participants meeting the ≤27.05 min encoding window. All tracked participants fell within tolerance, so no attentional exclusions were triggered.
8. **rec_ldi_boxplots.png** – Distribution of log-linear REC indices and BB–EM LDI scores per condition; both groups perform above chance with LDI medians near zero.
9. **rec_vs_ldi_scatter.png** – Participant-level scatter contrasting overall recognition strength with lure discrimination to show boundary sensitivity independence from REC.

## Analytical Takeaways
- **Condition Effects:** Natural-cut viewers (NB) exhibit slightly higher mean REC (0.725) and hit rates (~90%) than abrupt-cut viewers (AB) without a systematic BB advantage.
- **Boundary Sensitivity:** LDI values center near zero, implying BB frames are neither consistently easier nor harder than EM frames once responses are forced-choice. Individual differences dominate the spread (±0.2 range).
- **Demographic Stability:** Age, gender, and vision distributions are balanced, and regressions reveal negligible age-based modulation of accuracy/RT/confidence.
- **Attention Compliance:** Encoding durations remained within the theoretical limit, supporting the validity of subsequent recognition comparisons.

Use this document together with the PNG outputs in `analysis_plots/` when assembling slides, manuscripts, or supplementary materials.