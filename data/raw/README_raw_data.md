# Raw Data (External Hosting)

> **Why isn’t the data stored in Git?**  
> * One of the source files is ≈ 200 MB, exceeding GitHub’s 100 MB file limit.  
> * Keeping bulky CSV/XLSX files outside the repo avoids Git LFS friction and keeps clone size small for reviewers.  
> * All raw datasets are therefore hosted in a public, read-only Google Drive folder.

---

## 📂 Google Drive location  
<https://drive.google.com/drive/folders/1TJBYg6ouR49KL13BcLOD0o5dauq3cND8?usp=sharing>

| File | Size | Source / Notes |
|------|------|----------------|
| `raw_acled_demonstrations.xlsx` | 47 KB | ACLED – demonstration events |
| `raw_acled_political_violence.xlsx` | 44 KB | ACLED – political violence |
| `raw_bgs_minerals.csv` | 640 KB | British Geological Survey – mineral tonnage |
| `raw_comtrade_data.csv` | 2.9 MB | UN Comtrade – battery & mineral imports |
| `raw_ilo_wages.csv` | **196.7 MB** | ILOSTAT – manufacturing wages *(large file)* |
| `raw_wdi_data.csv` | 608 KB | World Bank WDI – macro indicators |
| `raw_wdi_exchange_rates.csv` | 125 KB | World Bank – annual FX rates |
| `raw_wdi_governance.csv` | 242 KB | World Bank – governance indicators |
| `raw_wdi_logistics.csv` | 144 KB | World Bank – Logistics Performance Index |

<sup>(File sizes as of 5 Jul 2025.)</sup>
---
## 🏺 Licence & usage  

All raw datasets retain their original licences:

| Source | Licence | Link |
|--------|---------|------|
| World Bank WDI & LPI | CC BY 4.0 | <https://datacatalog.worldbank.org/public-licenses> |
| UN Comtrade | CC BY 4.0 | <https://comtrade.un.org/sources-and-methods/> |
| ILOSTAT | CC BY 4.0 | <https://ilostat.ilo.org/resources/ilostat-user-guide/> |
| BGS Minerals | Open Government Licence v3.0 | <https://www.bgs.ac.uk/open-government-licence/> |
| ACLED | Academic licence | <https://acleddata.com/data-access/> |

*Reuse outside this project must comply with each provider’s terms.*
---

## 🔄 How to retrieve

```bash
# clone the repo (shallow clone)
git clone --depth=1 https://github.com/arifpazhwak/gigapower-ev-battery-site-selection.git
cd gigapower-ev-battery-site-selection/data/raw

# download the raw files from Drive  (requires:  pip install gdown)
gdown --folder 1TJBYg6ouR49KL13BcLOD0o5dauq3cND8 -O .
