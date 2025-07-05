# ⚡ Gigapower — EV-Battery Site-Selection Framework
*Rank 80 countries on six strategic pillars to pinpoint the best place for a **$500 M / 15 GWh** gigafactory that is live by 2029.*

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)  [![Built with Plotly](https://img.shields.io/badge/Plotly-5.x-teal)](https://plotly.com/python/)  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  ![Last Update](https://img.shields.io/github/last-commit/arifpazhwak/gigapower-ev-battery-site-selection)

---

## 1 · Executive snapshot
A global tier-1 industrial client asked  
> **“Where can we commit \$500 M today and be shipping cells in 2029 with the lowest blend of cost, risk and supply-chain friction?”**

We answered with a **Gigafactory Attractiveness Index (GAI)** that:

1. Harmonises **5 open-source datasets** into a 2010-23 country panel.  
2. Scores each market on **4 weighted pillars** – see below.  
3. Runs **scenario stress-tests** (*Risk-heavy*, *Cost-heavy*, bespoke sliders).  
4. **Segments** countries (K-Means) and visualises the 2 × 2 risk/value map.  
5. Outputs a **Top-5 board shortlist** plus an interactive *weight-slider sandbox*.

Everything is _fully reproducible_ on a laptop in < 10 min.

---

## 2 · Methodology at a glance

<table>
  <thead>
    <tr>
      <th>Pillar (↑ good)</th>
      <th>Core metrics</th>
      <th>Source</th>
      <th>Weight †</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>1 Market scale</strong></td>
      <td>GDP, FDI, population, EV proxy, etc. </td>
      <td>WB WDI</td>
      <td>25&nbsp;%</td>
    </tr>
    <tr>
      <td><strong>2 Cost competitiveness</strong></td>
      <td>manufacturing wages, electricity price </td>
      <td>ILOSTAT + FX (WB)</td>
      <td>25&nbsp;%</td>
    </tr>
    <tr>
      <td rowspan="3"><strong>3 Supply-Chain Readiness</strong></td>
      <td><strong>Logistics &amp; infrastructure</strong> – LPI (customs, infra, timeliness)</td>
      <td>WB LPI</td>
      <td>15&nbsp;%</td>
    </tr>
    <tr>
      <td><strong>Industry depth</strong> – Manufacturing % of GDP</td>
      <td>WB WDI</td>
      <td>15&nbsp;%</td>
    </tr>
    <tr>
      <td><strong>Critical-minerals security</strong> – Li, Ni, Co, Mn, Graphite mine output</td>
      <td>BGS WMS</td>
      <td>15&nbsp;%</td>
    </tr>
    <tr>
      <td><strong>4 Risk &amp; stability</strong></td>
      <td>WGI Rule-of-Law &amp; Political Instability + ACLED disorder events</td>
      <td>WB WGI, ACLED</td>
      <td>5&nbsp;%</td>
    </tr>
  </tbody>
</table>

Scoring steps: log-transform → z-score → positive-direction harmonisation → weighted sum.
> *Implementation note:* the three Supply‑Chain sub‑metrics enter the clustering **separately** (z‑scored) so that mineral abundance cannot swamp logistics or industrial depth.
---

## 3 · Repo layout
```text
├── data/
│   ├── raw/            ← download scripts & manifest (200 MB ILO file in GDrive)
│   └── processed/      ← model-ready CSV / Parquet
├── notebooks/
│   ├── 01_Data_Acquisition_and_Cleaning.ipynb
│   └── 02_Analysis_and_Recommendation.ipynb
├── reports/            ← HTML exports (Plotly fully embedded)
├── requirements.txt    ← pinned env incl. scikit-learn | plotly | ipywidgets
└── README.md           ← you are here
```

---

## 4 · Quick preview

| Notebook | Live HTML | Nbviewer | Contents |
|----------|-----------|----------|----------|
| **01 Data Acquisition & Cleaning** | `reports/01_Data_Acquisition_and_Cleaning.html` | [▶ View](https://nbviewer.org/github/arifpazhwak/gigapower-ev-battery-site-selection/blob/207ed1b5a45b69f44aff08c0f91100973da0729b/notebooks/01_Data_Acquisition_and_Cleaning.ipynb) | ETL, harmonisation, QA |
| **02 Analysis & Recommendation**   | `reports/02_Analysis_and_Recommendation.html`   | [▶ View](https://nbviewer.org/github/arifpazhwak/gigapower-ev-battery-site-selection/blob/207ed1b5a45b69f44aff08c0f91100973da0729b/notebooks/02_Analysis_and_Recommendation.ipynb) | PCA, GAI build, clusters, stress-tests |

*Interactive slider:* the weight-tuning sandbox works only inside Jupyter (requires **ipywidgets**). The exported HTML shows the last slider state.

---

## 5 · Reproduce in three lines
```bash
git clone --depth 1 https://github.com/arifpazhwak/gigapower-ev-battery-site-selection.git
cd gigapower-ev-battery-site-selection
python -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt
jupyter lab  # run both notebooks top-to-bottom
```
Python 3.10+ recommended.

---

## 6 · Key outputs

| Artefact | Where | Format |
|----------|-------|--------|
| Country rankings (base + stress)            | Notebook 02 § 6 | Plotly tables |
| 2 × 2 risk/value map + K-Means overlay      | Notebook 02 § 7 | Interactive Plotly |
| Top-5 shortlist radar                       | Notebook 02 § 11 | Radar chart |

*A concise 2-page board deck (PDF) will be generated in **reports/**.*

---

## 7 · Limitations & next steps
- **Data freshness:** WDI 2023 provisional, ACLED coverage uneven pre-2017 (flagged via `acled_covered`).  
- **Single-factor PCA:** current GAI uses equal-share PCs; introduce Monte-Carlo weight sensitivity (#13).  
- **Container-isation:** add Docker for one-command spin-up (#15).  
- **UX:** Streamlit front-end for non-technical stakeholders (#18).

---

## 8 · License & author
**Code:** MIT.  Third-party datasets retain original licences (see `/data/raw/README_raw_data.md`).  

**Arif Pazhwak** · pazhwakarif@gmail.com · [LinkedIn](https://www.linkedin.com/in/arifpazhwak/)

> “Data beats opinion — but only if the data pipeline is bullet-proof.”
