# 📓 Jupyter notebooks

| Notebook | Purpose | Typical running time |
|----------|---------|----------------------|
| **01_Data_Acquisition_and_Cleaning.ipynb** | End-to-end ETL: raw → harmonised → master analytical dataset. Shows country-name reconciliation, multi-source merges, and final imputations. | ~5 min (mostly I/O) |
| **02_Analysis_and_Recommendation.ipynb** | Exploratory analysis, PCA pillar scoring, sensitivity testing, clustering, and final gigafactory recommendations. Generates all figures used in the accompanying report. | 2-3 min |

### 🏃‍♂️ Quick-start

```bash
# (inside a fresh venv / conda env)
pip install -r ../requirements.txt
jupyter lab        # or jupyter notebook
