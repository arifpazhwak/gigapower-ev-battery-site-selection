# Project notebooks 📓

These Jupyter notebooks contain the full end-to-end analysis:

| Notebook | Live preview (interactive Plotly) | What it covers |
|-----------|------------------------------------|----------------|
| **01_Data_Acquisition_and_Cleaning.ipynb** | [▶ View](https://nbviewer.org/github/arifpazhwak/gigapower-ev-battery-site-selection/blob/207ed1b5a45b69f44aff08c0f91100973da0729b/notebooks/01_Data_Acquisition_and_Cleaning.ipynb) | Data ingestion, cleaning & harmonisation pipeline |
| **02_Analysis_and_Recommendation.ipynb**   | [▶ View](https://nbviewer.org/github/arifpazhwak/gigapower-ev-battery-site-selection/blob/207ed1b5a45b69f44aff08c0f91100973da0729b/notebooks/02_Analysis_and_Recommendation.ipynb) | EDA, PCA-based indices, clustering & final site shortlist |

> **Why Nbviewer?**  
> GitHub’s native renderer strips JavaScript, so Plotly charts won’t display.  
> Nbviewer serves the notebook as a fully functional HTML page with Plotly JS enabled.

---

### How to run locally

```bash
git clone https://github.com/arifpazhwak/gigapower-ev-battery-site-selection.git
cd gigapower-ev-battery-site-selection
pip install -r requirements.txt      # minimal env
jupyter lab                           # or jupyter notebook
