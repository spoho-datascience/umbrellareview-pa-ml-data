# Data: The Use of Machine Learning in Performance Analysis in Team Sports — An Umbrella Review

**Klemp, M., Bassek, M., Garnica Caparròs, M., Bakhtiar, L. A., & Memmert, D. (2026). The use of machine learning in performance analysis in team sports: Umbrella review of reviews. *Journal of Sports Sciences*. https://doi.org/10.1080/02640414.2026.2636863**

---

This repository contains the supplemental material accompanying the umbrella review manuscript *"The Use of Machine Learning in Performance Analysis in Team Sports: Umbrella Review of Reviews"*. The data support all quantitative analyses reported in the manuscript and are provided to ensure transparency and reproducibility.

---

## Dataset Overview

The umbrella review systematically identifies and synthesizes existing reviews on machine learning (ML) applications in team sports performance analysis. The review process resulted in three interconnected datasets described below.

---

## Files

### `included_reviews.csv`

**Description:** Bibliographic metadata for the 12 reviews retained for inclusion in the umbrella review after systematic screening (359 initial records → 12 included).

**Rows:** 12 (one per included review)

**Columns:**

| Column | Description |
|---|---|
| `Title` | Full title of the review article |
| `Authors (short)` | Short citation-style author reference (e.g., "Bunker & Susnjak (2022)") |
| `Authors` | Full author list |
| `Publication Year` | Year of publication |
| `Journal` | Journal name |
| `Journal Domain` | Subject area / discipline of the journal |
| `Journal Impact Factor` | Journal impact factor at time of data extraction |
| `Journal Quartile in Domain` | SCImago quartile ranking within the journal's domain (Q1–Q4, or "Not listed") |
| `Citations` | Number of citations at time of data extraction |
| `Type of Review` | Review methodology (Systematic Review, Narrative Review, Descriptive Review) |
| `Sport` | Sport(s) covered (e.g., Football, Basketball, Team Sports, All Sports) |
| `Number of studies included in review` | Number of primary studies included in the respective review |

---

### `primary_studies.csv`

**Description:** A complete list of primary studies extracted from the 11 reviews for which study lists were retrievable (the review by Elstak et al. (2024) could not be disaggregated). Each row represents one primary study and shows in which reviews it was included and whether it met the umbrella review's eligibility criteria.

**Rows:** 263 primary studies

**Columns:**

| Column | Description |
|---|---|
| `inclusion` | Whether the study met the umbrella review's eligibility criteria (`included` / `excluded`) |
| `Title` | Title of the primary study |
| `Author` | Author(s) of the primary study |
| `Date` | Publication year |
| `DOI` | Digital Object Identifier (link to original publication) |
| `Bunker & Susnjak (2022)` … `Keshtkar Langaroudi & Yamaghani (2019)` | Binary columns (1 = included in that review, 0 = not included), one column per review (11 columns total) |
| `Sum of Presence` | Total number of reviews that included this primary study (range: 1–4) |

**Notes:**
- Two studies were included in four reviews each; 16 were included in three reviews; 30 in two reviews; and 215 in only one review.
- 172 of the 263 studies met eligibility criteria (invasion team sports, within-scope ML task) and were carried forward to the ML application analysis.

---

### `ml_applications_primary_studies.csv`

**Description:** Application-level data extracted from the 172 eligible primary studies. Each row represents one individual ML application (i.e., one algorithm applied to one task in one study). A single primary study can contribute multiple rows if it tested multiple algorithms or reported multiple evaluation metrics.

**Rows:** 607 ML applications from 172 primary studies

**Columns:**

| Column | Description |
|---|---|
| `Title` | Title of the primary study |
| `Author` | Author(s) of the primary study |
| `Date` | Publication year |
| `DOI` | DOI of the primary study |
| `ML task` | ML task category (see taxonomy below) |
| `Sport` | Sport studied (e.g., football, basketball, ice hockey, handball) |
| `Gender` | Gender of the athlete sample (Male, Female, Mixed) |
| `Competition (National vs International)` | Level of competition of the sample |
| `Sample Country/Continent` | Country or continent of origin of the data sample |
| `Sample Region` | Broader geographic region (e.g., Europe, North America) |
| `Season` | Season(s) or year range covered by the data |
| `Sample Size` | Number of observations / matches / events in the dataset |
| `Data Modalities` | Type of data used (Notational Data, Tracking Data, or combination) |
| `Number of Features` | Number of input features used by the ML model |
| `Algorithm` | Specific ML algorithm (e.g., Random Forest, Logistic Regression, Neural Network) |
| `Algorithm Family` | Higher-level algorithm family (see taxonomy below) |
| `Evaluation Metric` | Metric used to assess model performance (e.g., Accuracy, F1 Score, RMSE, AUC) |
| `Performance` | Reported model performance value on the respective metric |

**ML Task Taxonomy:**

| Task | Description |
|---|---|
| Match Outcome Prediction | Predicting win/loss/draw outcome before or during a match |
| Performance Prediction | Forecasting player or team performance metrics |
| Performance Evaluation | Assessing or identifying patterns in past performance |
| Tactical Analysis | Analyzing formations, strategies, or behavior patterns |
| Injury Prevention | Predicting injury risk factors |
| Talent Identification | Player scouting and recruitment applications |

**Algorithm Family Taxonomy:**

| Family | Examples |
|---|---|
| Neural Networks | Feedforward networks, CNNs, LSTMs, deep learning |
| Ensemble Methods | Random Forest, XGBoost, AdaBoost, Gradient Boosting |
| Kernel-Based Models | Support Vector Machines (SVM) |
| Bayesian/Probabilistic Models | Naive Bayes, Bayesian Networks |
| Tree-Based Models | Single decision trees |
| Linear Models | Logistic Regression, Linear Regression |
| Instance-Based Models | k-Nearest Neighbors (k-NN) |
| Clustering / Unsupervised Models | k-Means, Hierarchical Clustering, SOM, Matrix Factorization |

---

### `search_strings.txt`

**Description:** The Boolean search strings used to query three academic databases during the systematic literature search. The search was conducted on 16th April 2025.

**Databases covered:**

| Database | Notes |
|---|---|
| PubMed | Title/Abstract field search; publication type filter (review, meta-analysis, systematic review) |
| IEEE Xplore | Title and Abstract field search; document type filter equivalent to review articles |
| SPORTDiscus | Cross-field (`XB`) search combining title and abstract |

All three strings follow the same two-part logic:
1. **ML terms**: machine learning, deep learning, artificial intelligence, data mining, clustering, classification, computer vision
2. **Sport terms**: team sports, invasion games, and specific sports (football, soccer, futsal, rugby, basketball, hockey, handball, water polo, lacrosse, softball, korfball, netball)

The strings were combined with `AND`, requiring records to mention both an ML concept and a relevant sport in their title or abstract, and to be classified as a review-type publication.

---

## Citation

If you use this dataset, please cite the accompanying manuscript:

> Klemp, M., Bassek, M., Garnica Caparròs, M., Bakhtiar, L. A., & Memmert, D. (2026). The use of machine learning in performance analysis in team sports: Umbrella review of reviews. *Journal of Sports Sciences*. https://doi.org/10.1080/02640414.2026.2636863

---

## License

Data are provided for academic and research use. Please refer to the manuscript for details on data provenance.
