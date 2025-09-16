# Age Detection from Speech

Estimate a speaker's age from voice recordings using audio feature extraction and supervised regression.  
This project was developed as part of the **Data Science Lab: Process and Methods** course at Politecnico di Torino.

## Repository structure

Age-Detection-Audio-Features/
├── Datasets/
│   ├── Original Data/
│   │       ├── audios_development/     # audios
│   │       ├── development.csv         # audio feature values with age indicated
│   └── Preprocessed Data/              # preprocessed features for training
│
├── Input/                              # evaluation.csv (test data without target)
│     ├── evaluation.csv                # audio feature values used for evaluation
│
├── Model/
│   ├── flowchart.ipynb                 # workflow overview and preprocessing steps
│   └── model.ipynb                     # main notebook: feature engineering + training + predictions
│
├── Predictions/
│     ├── submission.csv                # final model output
│
├── report.pdf                          # project report (methodology and results)
├── requirements.in                     # main dependencies (unpinned versions)
├── requirements.txt                    # full environment with pinned versions
└── README.md

---

## Environment setup

### 1. Clone the repository
```bash
git clone https://github.com/Mastr0203/Age-Detection-Audio-Features.git
cd Age-Detection-Audio-Features

2. Create and activate a virtual environment

python3 -m venv .venv
source .venv/bin/activate   # macOS/Linux
.venv\Scripts\activate      # Windows

3. Install dependencies
	•	Lightweight install (unpinned versions): pip install -r requirements.in

	•	Reproduce my exact setup (pinned versions): pip install -r requirements.txt

⸻

How to reproduce experiments
	1.	Open the main notebook: jupyter notebook Model/model.ipynb

	2.	Run the cells in sequence:
	    •	Load data (development.csv from Datasets/Original Data/)
	    •	Preprocessing (normalizations, log-transform, gender encoding, etc.)
	    •	Feature engineering (MFCCs, mel-spectrogram, pitch, jitter, shimmer, etc.)
	    •	Model selection (Random Forest, SVR, Ridge Regression)
	    •	Final training (Ridge + PolynomialFeatures degree=2 + α tuning)
	    •	Prediction on evaluation.csv → output saved to Predictions/submission.csv

Main results

    Model	            RMSE	    R²
    Random Forest	    10.595	    0.300
    SVR	                10.785	    0.297
    Ridge + Poly(2)	    9.463	    0.349

The final model is Ridge Regression with PolynomialFeatures(degree=2) and α=178, achieving the best leaderboard score (RMSE=9.463).

⸻

Tech stack
	•	Python 3.12
	•	Core libraries: numpy, pandas, scikit-learn, scipy
	•	Audio processing: librosa, soundfile, numba
	•	Visualization: matplotlib, seaborn
	•	Utilities: prettytable, tqdm, pyyaml

⸻

Documentation

For a detailed explanation of methodology, preprocessing, and results, see report.pdf.

⸻

License

This project is released under the MIT License.
Feel free to reuse or adapt the code, with proper attribution.