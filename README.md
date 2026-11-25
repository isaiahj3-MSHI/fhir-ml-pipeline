# FHIR-to-ML Pipeline

Pulling synthetic patient records from a FHIR R4 server, turning them into analysis-ready tables, and training a simple risk model on them.

**Status:** In progress, Winter Break 2026 (target finish: Jan 10, 2027)

## Why

FHIR (Fast Healthcare Interoperability Resources) is the standard US health systems use to share electronic health record data. Before I start the M.S. in Health Informatics (Data Science track) at the University of Pittsburgh, I'm building a full pipeline from raw FHIR resources to a working machine learning model.

## What it does (planned)

1. **Extract:** Query a public FHIR R4 server (HAPI FHIR) and synthetic Synthea patients for `Patient`, `Condition`, `Observation`, `MedicationRequest`, and `Encounter` resources.
2. **Transform:** Flatten nested FHIR JSON into tidy pandas DataFrames (one row per patient, with demographics, diagnoses, labs and vitals).
3. **Analyze:** Explore the cohort (counts, distributions, missingness) and visualize it.
4. **Model:** Train and evaluate a scikit-learn classifier (for example, predicting a diabetes diagnosis from vitals and labs), with honest metrics and notes on its limits.

## Roadmap

- [ ] **Week 1:** FHIR basics, explore the HAPI test server, first API calls with `requests`
- [ ] **Week 2:** Extract patients and observations into pandas; first EDA notebook
- [ ] **Week 3:** Generate a larger Synthea cohort; build the feature table
- [ ] **Week 4:** Train and evaluate the model; write up the results

## Tech stack

- Python, `requests`, pandas, NumPy
- scikit-learn, matplotlib
- [HAPI FHIR R4 public test server](https://hapi.fhir.org/baseR4)
- [Synthea](https://github.com/synthetichealth/synthea) synthetic patient generator
- Jupyter notebooks

## Repository layout

```
notebooks/   step-by-step Jupyter notebooks
src/         reusable extraction and transformation code
data/        local data (git-ignored; never real patient data)
```

## Getting started

```bash
git clone https://github.com/isaiahj3-MSHI/fhir-ml-pipeline.git
cd fhir-ml-pipeline
pip install -r requirements.txt
jupyter notebook
```

## Results

Coming soon.

## Data note

This project uses only synthetic data (Synthea) and public test servers. It contains no real patient information.

## About me

Isaiah Jefferson III: B.S. Engineering Science (Pitt, Dec 2026), incoming M.S. Health Informatics, Data Science track (Pitt, Jan 2027). Interested in health data, machine learning, and interoperability.
