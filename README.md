# Software-Metrics---Assignment-6
This repository contains the implementation developed for Assignment 6 of the Software Metrics and Measurements course. The objective of this project is to build an automated software measurement program that extracts data from a software repository, computes software metrics, and visualizes the results through an interactive dashboard.

# Software Metrics Measurement Program

This repository contains the implementation developed for Assignment 6 of the Software Metrics and Measurements course.

The objective of this project is to build an automated software measurement program that extracts data from a software repository, computes software metrics derived from research literature, stores measurements over time, and visualizes the results through an interactive dashboard.

---

# Repository Under Analysis

The measurement program monitors the FastAPI open-source repository:

https://github.com/fastapi/fastapi

The repository was selected because it is an actively maintained software project with a large development history and multiple contributors, making it suitable for Mining Software Repositories (MSR) analysis.

---

# Implemented Metrics

The measurement system computes the following metrics:

| Metric                          | Description                                          |
| ------------------------------- | ---------------------------------------------------- |
| Stability Index                 | Measures how frequently files are modified over time |
| Change Frequency                | Number of commits within the analysis window         |
| Code Ownership                  | Distribution of contributions among developers       |
| Developer Activity              | Number of active contributors                        |
| Change Coupling                 | Frequency with which files change together           |
| Cyclomatic Complexity           | Structural complexity of the source code             |
| Hotspot Index                   | Concentration of changes in specific files           |
| Code Review Activity            | Proxy measure based on merge commits                 |
| Continuous Integration Activity | Proxy measure based on integration-related commits   |
| Lead Time for Changes           | Approximation of change integration time             |

---

# Project Structure

```text
software-metrics-system/

├── pipeline/
│   ├── run.py
│   ├── git_data.py
│   └── github_pr.py

├── metrics/
│   ├── stability.py
│   ├── complexity.py
│   ├── ownership.py
│   ├── dev_activity.py
│   ├── coupling.py
│   ├── change_frequency.py
│   ├── review.py
│   ├── ci.py
│   ├── lead_time.py
│   └── hotspot.py

├── dashboard/
│   └── app.py

├── data/
│   └── metrics.csv

└── README.md
```

---

# Installation

## 1. Clone this repository

```bash
git clone https://github.com/YOUR_USERNAME/software-metrics-system.git
cd software-metrics-system
```

## 2. Install dependencies

```bash
pip install pandas
pip install streamlit
pip install radon
```

If additional dependencies are required:

```bash
pip install -r requirements.txt
```

---

# Clone the Target Repository

Clone FastAPI into the project directory:

```bash
git clone https://github.com/fastapi/fastapi.git fastapi_repo
```

The resulting structure should look like:

```text
software-metrics-system/

├── fastapi_repo/
├── pipeline/
├── metrics/
├── dashboard/
└── data/
```

---

# Running the Measurement Pipeline

Execute the measurement pipeline:

```bash
python -m pipeline.run
```

The script will:

1. Read Git history from the FastAPI repository
2. Compute all software metrics
3. Append the measurements to:

```text
data/metrics.csv
```

Example output:

```csv
date,stability,change_frequency,ownership,dev_activity_count,coupling,complexity,hotspot_index
2026-05-19,1.0,123,0.49,9,15.58,1263,0.24
```

---

# Running the Dashboard

Start the Streamlit dashboard:

```bash
streamlit run dashboard/app.py
```

After launch, open:

```text
http://localhost:8501
```

The dashboard displays:

* Latest metric values
* Historical trends
* Raw measurement data

---

# Daily Data Collection

To collect data daily, execute:

```bash
python -m pipeline.run
```

once per day.

Each execution appends a new row to:

```text
data/metrics.csv
```

allowing longitudinal analysis of software evolution.

---

# Example Dashboard

The dashboard provides:

* KPI overview
* Time-series metric visualization
* Historical measurement records
* Repository evolution trends

Screenshots collected during the assignment are available in the report.

---

# References

The metric definitions implemented in this project are based on software engineering and Mining Software Repositories (MSR) literature, including work by:

* Hassan (2009)
* Bird et al. (2011)
* Kalliamvakou et al. (2014)
* Vasilescu et al. (2015)
* Bacchelli and Bird (2013)
* Hilton et al. (2016)
* Forsgren et al. (2018)
* Tornhill (2014)

Full citations are provided in the assignment report.

---
