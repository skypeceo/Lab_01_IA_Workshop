
# Lab 1 · AI and contribution record

**Members:** Martin Olivares and Benjamin Levit.

**AI used / not used:** AI was used. Tool: Claude (Anthropic), used in a chat conversation
throughout the lab. Purpose: guiding with interpretation text (target/audit narrative, EDA
interpretation structure, baseline explanations, calibration/test interpretation, and this
documentation itself), explaining error messages during environment setup (numpy/Python 3.13
build failure, missing seaborn dependency).


**Own decision:** we decided to resolve the qualifying_position missing-value cases using the
brief's fixed training-majority fallback rather than dropping those rows, and to verify this by
inspecting the specific left_only records ourselves rather than trusting the join code alone.

**Verification, observed result and limitation (notebook reference: Section 1, "Key and coverage
audit" cell and its markdown interpretation):** we ran `train[train['qualifying_match'] ==
'left_only']` ourselves and observed three real rows (albon, giovinazzi, mick_schumacher), all
with a "+N Laps" status rather than a retirement code, confirming the missingness was in the
qualifying source table itself rather than linked to whether the driver finished. Limitation: with
only three affected rows in train, we cannot generalize whether this missingness pattern
(clustered in one 2019 race) would hold at a larger scale or in other seasons; this remains an
open question we did not investigate further given the lab's scope.

| Member | Contribution and evidence reference |
|---|---|
| Martin Olivares | Section 1 audit code and interpretation; Sections 5-7 (baseline explanation, calibration interpretation, freeze record, test interpretation); RUNBOOK environment documentation; this PROMPTS record. |
| Benjamin Levit | Notebook setup cell; EDA questions 1 and 2 (constructor vs. top-10, grid vs. result) including code, tables, heatmaps and interpretation; RUNBOOK environment documentation. |


