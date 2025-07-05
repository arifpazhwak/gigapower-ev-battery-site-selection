# Model-ready / Processed Data

These files are the **clean, feature-engineered outputs** of Notebook 01  
(*01_Data_Acquisition_and_Cleaning.ipynb*) and early steps of Notebook 02.  
They are small enough to live in-repo, so no external download is needed.

| File | Size\* | 
|------|-------:|
| `model_ready_data.csv` | 301 KB | 
| `model_ready_data.parquet` | 166 KB | 
| `Pillar1_Market_Opportunity.csv` | 362 KB | 
| `Pillar2_Cost_Competitiveness.csv` | 44 KB | 
| `Pillar3_SupplyChain_Readiness.csv` | 169 KB | 
| `Pillar4_Governance_Risk.csv` | 212 KB | 

\*sizes as of **5 Jul 2025**

---

## 📑 What’s inside?

* **`model_ready_*`** – the **merged master table** used for PCA, clustering, and index construction.  
  * *Rows* = country-year observations (2010-2023).  
  * *Columns* = scaled pillar features + a few IDs (`country`, `year`).

---

## 🔄 Re-generating

If you ever need to recreate them:

```bash
# from repo root
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute notebooks/01_Data_Acquisition_and_Cleaning.ipynb
jupyter nbconvert --to notebook --execute notebooks/02_Analysis_and_Recommendation.ipynb
