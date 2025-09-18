# Customer Segmentation

This project applies unsupervised machine learning to segment credit card customers into distinct groups based on their financial and behavioral characteristics. The analysis combines a rigorous data science pipeline — including preprocessing, dimensionality reduction (PCA, t-SNE), and clustering algorithms (K-Means, GMM, Agglomerative) — with business-oriented interpretation of results.

From a technical perspective, the project demonstrates how to evaluate and validate clustering models using multiple metrics, and how to translate raw cluster outputs into interpretable segments. From a business perspective, the identified segments (e.g., high-value digital-first customers, balanced traditional users, and support-dependent low-tier users) illustrate how data-driven segmentation can inform targeted marketing strategies, product personalization, and customer service optimization.

## Problem Statement
The objective is to identify and characterize distinct customer segments from a credit card customer dataset. The primary challenges include:
1. **Data Preparation**: Handling duplicate entries and skewed features to ensure reliable modeling.  
2. **Determining Optimal Clusters**: Selecting the right number of clusters using quantitative evaluation metrics.  
3. **Interpreting Clusters**: Profiling each cluster to transform raw groupings into actionable business insights.  

## Dataset Details
The dataset contains information on 660 credit card customers.  
- **Source**: Provided as an Excel file, *Credit Card Customer Data.xlsx*.  
- **Size**: 660 rows × 7 columns.  
- **Features**: `Avg_Credit_Limit`, `Total_Credit_Cards`, `Total_visits_bank`, `Total_visits_online`, and `Total_calls_made`.  
- **Preparation**:  
  - Removed duplicate customer keys and identical rows.  
  - Applied log transformation (`np.log1p`) to skewed features.  
  - Standardized all features using `StandardScaler` to ensure balanced influence across models.  

## Methods and Algorithms
A structured unsupervised learning pipeline was developed:  
- **Dimensionality Reduction**:  
  - **PCA** (capturing ~80% of variance) for dimensionality reduction and visualization.  
  - **t-SNE** for non-linear visualization of clusters.  
- **Optimal Cluster Selection**: Evaluated with the **Elbow Method**, **Silhouette Score**, and **Calinski-Harabasz Index**.  
- **Clustering Models**:  
  - **K-Means**  
  - **Gaussian Mixture Model (GMM)**  
  - **Agglomerative Clustering**  
- **Cluster Validation**: Results cross-validated and visualized in 2D projections to confirm separation and interpretability.  

## Key Results
- **Optimal Clusters**: A segmentation into **three distinct clusters** was found to be most appropriate.  
- **Model Selection**: All models performed similarly, but **Agglomerative Clustering** was chosen for its interpretability and hierarchical insights.  
- **Identified Customer Segments**:  
  1. **Balanced Traditional Users** — mid-tier customers with a preference for physical bank visits and moderate use of other channels.  
  2. **Support-Dependent Low-Tier Users** — low credit limits, frequent support calls, requiring greater assistance.  
  3. **High-Value Digital-First Customers** — profitable, self-sufficient users with high credit limits and strong online engagement.  

These personas demonstrate how clustering outputs can be translated into **actionable strategies** for marketing, product design, and resource allocation.  


## Tech Stack
- **Libraries**:  
  - `pandas`, `numpy` — data manipulation  
  - `matplotlib`, `seaborn` — visualization  
  - `scikit-learn` — preprocessing, PCA, t-SNE, clustering, evaluation metrics  
  - `scipy.cluster.hierarchy` — hierarchical clustering & dendrograms  