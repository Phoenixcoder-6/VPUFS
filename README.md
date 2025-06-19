## VPUFS
This repository contains the implementation of VPUFS, a novel unsupervised feature selection framework designed to effectively reduce the high dimensionality of microarray gene expression data for cancer sample clustering.

## 📌 Overview


Gene expression datasets are highly dimensional, with only a small fraction of features (genes) being truly informative for classifying or clustering cancer samples. VPUFS addresses this issue by selecting the most relevant and non-redundant features using:

-Variance Score: Measures relevance based on statistical variability.

-Pearson Similarity: Identifies and eliminates redundant features by measuring pairwise correlations.

-The selected features can then be used to improve performance in clustering algorithms such as K-Means, Spectral Clustering, GMM, etc., providing better insights into cancer subtypes.


## ⚙️ Features


-Unsupervised feature selection (no class labels needed)

-Efficient reduction of high-dimensional microarray gene data

-Improved clustering results using selected features

-Evaluated on multiple datasets: Leukemia, Colon, Prostate, Breast

-Tested against established techniques (Laplacian Score, MCFS, JELSR, NDFS, LDFS)


## 📁 Dataset Info

![image](https://github.com/user-attachments/assets/7c35a5e6-5cda-4338-9079-d74692f7a8e6)


## 🧮 Methodology

1. Data Preprocessing
-Remove null/duplicate rows and columns

-Separate target labels (if available)

2. Feature Scoring
-Variance Score: High variance = high relevance

-Pearson Similarity: Measures redundancy between features

-Non-Redundant Score: 1 - max(Pearson Correlation)

-Final Score: Variance × Non-Redundant Score

3. Feature Selection
-Sort features by score

-Select top-𝑞 ranked features

Output: reduced gene expression matrix

## 📊 Performance Evaluation

--Classifier: SVM with LOOCV, 5-fold, and 10-fold cross-validation

--Clustering: K-Means, GMM, Agglomerative, SOM, Spectral

--Metrics: Rand Index (RI), Adjusted Rand Index (ARI)

VPUFS outperforms most traditional unsupervised methods in terms of both classification accuracy and clustering performance.

## 🔍 Key Results
![image](https://github.com/user-attachments/assets/736b74a4-3cba-4431-8062-8b985bec892e)


## 📦 Installation & Usage

# Clone the repository
git clone https://github.com/your-username/VPUFS.git
cd VPUFS
# Install dependencies
pip install -r requirements.txt
# Run the VPUFS pipeline
python vpufs_main.py
Replace vpufs_main.py with the actual script name used.

## 🧠 Future Work

-Extend the framework to RNA-seq datasets

-Integrate deep learning-based feature selectors

-Deploy as a web-based cancer clustering tool


