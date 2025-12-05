# Hotel Matching & Canonical ID System

### Overview
A complete prototype system that deduplicates hotel records from multiple sources (GDS, OTAs, Direct) and assigns unique canonical IDs for downstream reporting, pricing, and analytics.

### Contents
- `hotel_matching_assignment.ipynb` – Full Jupyter notebook with data cleaning, similarity scoring, clustering, and matching logic
- `mlops_system_design.pdf` – Detailed answers to all 7 MLOps system design questions + system architecture diagram
- `hoteldata_raw.csv` – Provided dataset (100 hotel records)
- `requirements.txt` – Minimal Python dependencies
- `images/architecture_diagram.png` – Visual system architecture

### Problem Statement
Hotels appear with different names and addresses across suppliers. This system:
1. Identifies duplicate listings of the same physical hotel
2. Assigns a stable `canonical_hotel_id` to each unique hotel
3. Provides a real-time API to match new hotel records

### Tech Stack
- Python (pandas, scikit-learn, fuzzywuzzy)
- Jupyter Notebook (prototyping)
- MLOps Tools (Airflow, MLflow, Feast, Docker, Kubernetes – designed for production)

### Results
- 100 raw records → clustered into 25 unique physical hotels
- Duplicate detection: Known duplicates score >0.8 (MATCHED), different hotels score <0.2 (NEW)
- Production-ready design with batch + real-time serving

### How to Run
```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Launch Jupyter
jupyter notebook hotel_matching_assignment.ipynb

# 3. Run cells sequentially