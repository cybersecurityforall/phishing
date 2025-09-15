[![License: CC BY-ND 4.0](https://img.shields.io/badge/License-CC_BY--ND_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nd/4.0/)

Paper title: **Linguistic Hooks: Investigating The Role of Language Triggers in Phishing Emails Targeting African Refugees and Students**


## Overview

This repository contains data, figures, and scripts used in the phishing study accepted to PoPETs 2026. It includes Jupyter notebooks for analysis, CSV files with cleaned and anonymized data, and scripts for statistical results and producing visualizations in the PoPETs submission. Experimental `Study 1` focuses on African Refugees (Group A) and `Study 2` on African Immigrant Students and US-born Students (Groups B and C respectively).

 **Citation**: *Linguistic Hooks: Investigating The Role of Language Triggers in Phishing Emails Targeting African Refugees and Students*, [Author Names Redacted for Review], PoPETs 2026.

### Security/Privacy Issues and Ethical Concerns

- This artifact does **not** include real emails, credential content, or any personally identifiable information (PII). All participant identifiers and sensitive columns are anonymized.  
- This project was reviewed and approved by the full committee of a University's Institutional Review Board (IRB). All participants were provided the option to opt out of the study, and data sharing is restricted to anonymized, non-traceable formats.

## Repository Structure

-   **data/**: Anonymized version of the main datasets for study 1 and study 2.
-   **figures/**: Generated plots and figures for publication.
-   **scripts/**: Main analysis, statistical analysis and result generation.

## Basic Requirements

### Hardware Requirements

- Can run on a laptop (No special hardware requirements)
- For reproduction: experiments were executed on a system with:
  - 4-core Intel i7 CPU
  - 16GB RAM
  - 256GB SSD

### Software Requirements

- OS: Ubuntu 22.04 LTS or macOS 13+
- Python 3.8+
- Required packages listed in `requirements.txt`, including:
  - pandas
  - numpy
  - seaborn
  - matplotlib
  - jupyter
- Datasets:
  - Anonymized partial datasets are included under `data/`
  - No external downloads are required

### Estimated Time and Storage Consumption

- Setup time: ~15 minutes
- Full result reproduction: ~15 minutes CPU time
- Disk space required: <500MB total

## Environment

### Set up the environment

```bash
# Native (requires Python 3.8+)
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```


### (Re)Run Analysis

1.  Launch Jupyter Notebook:

    ``` bash
    jupyter notebook
    ```

2.  Open any notebook ending in **.ipynb** from `scripts/` folder and Select `Cell -> Run All` to reproduce the analysis.


## Dataset Columns Description

**File(s):** `data/masterfile-study*.csv` 

| Column name             | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `Simulation Name`       | Identifier for the specific simulation or scenario configuration.           |
| `PID`                   | Participant identifier (anonymized across studies).                         |
| `eventName`             | Type of email-related action recorded during the simulation.                |
| `eventDateTime`         | Full timestamp of when the event occurred.                                  |
| `isPartOfCompromise`    | Indicates whether the event was part of an eventual compromise.             |
| `order`                 | Sequential position of the scenario presented to the participant.           |
| `scenario`              | Identifier for the specific phishing scenario.                              |
| `infoRequested`         | Identifier for the information requested from the participant.              |
| `emailSubject`          | Email subject line used in the phishing message.                            |
| `MANIPULATION`          | Labels describing the 2x2 manipulation (linguistic x legitimacy) strategy.  |
| `Group`                 | Experimental group to which the participant was assigned.                   |
| `country`               | Participant’s country of birth.                                             |
| `age_bin`               | Age group category assigned to the participant.                             |
| `read`                  | Participant's English reading proficiency level (1–5, with 5 being highest).|
| `EventDate`             | Date portion extracted from `eventDateTime`.                                |
| `EventTime`             | Time portion extracted from `eventDateTime`.                                |
| `EventDay`              | Day of the week on which the event occurred.                                |
| `EventTimeBin`          | Coarse time-of-day bin (e.g., Morning, Evening).                            |
| `EventHour`             | Hour of the day (0–23) extracted from `eventDateTime`.                      |
| `EventTimeBin_OneHour`  | Fine-grained 1-hour time bin for detailed temporal grouping.                |

**Note:** In a 24-hour time format, the `EventTimeBin` has value `Morning` if the hour is between 5 and 11, `Afternoon` if it is between 12 and 16, `Evening` if it is between 17 and 20, and `Night` for all other hours. 

## Limitations

- While most data is reproducible, real email logs, participant responses, questionnaire and interview datasets were not included to preserve participant privacy.

## License

This repository (including all code and datasets) is licensed under the [Creative Commons Attribution-NoDerivatives 4.0 International License](LICENSE). You may share the work with attribution, but you may not remix, transform, or build upon it.
