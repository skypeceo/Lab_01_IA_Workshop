# Lab 1 · Runbook

1. Extract the complete package into your course repository; preserve labs/lab_01 and data/samples/lab01_v1.
2. Use your Week 2 Python environment. If needed: `python -m pip install -r requirements_lab01_v1.txt` from the package root.
3. Open labs/lab_01/Lab01_EDA_Baselines_Student_v1.ipynb with that environment's Python kernel. Default MODE is snapshot; no network is used by the notebook.
4. Work through train, then calibration. Complete the written evidence and freeze record before enabling RUN_TEST.
5. Restart and Run All after completing the notebook. Save its outputs. Confirm that you can reproduce the frozen evaluation without modifying decisions.
6. Record your actual Python/package versions, operating system, any changes to this procedure, the submitted commit and the date/result of your check below. Keep the source CSVs unchanged.

Actual environment and execution evidence: TO COMPLETE.

Submission uses GitHub + Canvas as stated in the brief. Include support code and the six CSVs plus lab01_manifest_v1.json. No API credentials are needed. If your environment is blocked, record the exact error and contact the teaching team; do not label synthetic practice as real data.


## Actual environment and execution evidence

**Martin Olivares:**
- OS: Debian 13 (trixie)
- Python: 3.13.5 
- Virtual environment: created with `python3 -m venv .venv` at the package root, activated with
  `source .venv/bin/activate`
- Package installation: `requirements_lab01_v1.txt` pins numpy==1.26.4, which has no precompiled
  wheel for Python 3.13 and failed to build from source (missing Python.h / python3-dev). We
  resolved this by letting pip install compatible newer versions instead of the exact pinned
  ones: python -m pip install "numpy>=1.26,<2.3" pandas matplotlib ipykernel "notebook>=7,<8"

  Actual installed versions confirmed at runtime: Python 3.13.5, pandas 3.0.6 (numpy/matplotlib
  versions as resolved by pip on this date).
- An additional dependency, `seaborn`, was used in the EDA heatmap cells but was missing from the
  original `requirements_lab01_v1.txt`. This caused a `ModuleNotFoundError` on a fresh environment.
  It was installed manually (`pip install seaborn`) and the exact version added to
  `requirements_lab01_v1.txt` so future clones of the repository do not hit the same error.
- Jupyter kernel registered with:
  `python -m ipykernel install --user --name lab1-iit414w --display-name "Python (IIT414W Lab1)"`


**Benjamin Levit:**
- OS: MacOS 27
- Python: 3.11.5
- pandas: 2.0.3
- Virtual environment: created with `python3 -m venv .venv` at the package root, activated with
  `source .venv/bin/activate`
- No issues reported installing the pinned `requirements_lab01_v1.txt` versions on this Python
  version.

**Note on environment differences:** the two members ran the notebook on different Python
versions (3.13.5 vs 3.11.5) and different pandas versions (3.0.6 vs 2.0.3). Both environments
executed the full notebook successfully end to end, which supports — but does not by itself
guarantee — that the analysis is not sensitive to this version difference. No behavioral
differences between the two environments were observed in the audit, EDA, baseline or evaluation
outputs.

**No random seed was required.** All computations in this notebook (audits, baselines, evaluation
metrics) are deterministic given the fixed source data; no `random` or `np.random` calls were
introduced, so RANDOM_SEED = 414 from `lab01_support_v1.py` was not separately invoked by our
added code.

**Restart and Run All confirmation:** the notebook was saved, then executed via
restart kernel and run all on 23 September on Martín's machine. All cells completed without an
unexpected error, including the health-check imports, the three EDA analyses (with seaborn
heatmaps), the calibration evaluation, and the frozen test evaluation.





