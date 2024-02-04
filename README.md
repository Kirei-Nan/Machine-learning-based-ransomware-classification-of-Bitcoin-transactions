# Ransomware Detection in Cryptocurrency Transactions: A Code Companion

This repository houses the codebase and supporting data for our research on ransomware detection in cryptocurrency transactions using a multistage machine learning framework. It builds on the Bitcoinheist dataset, containing data for 28 ransomware families, categorized into Princeton, Montreal, and Padua, alongside a 'white' category representing legitimate transactions. For an overview of our research, please refer to our paper abstract in the repository.

## Repository Structure

### 1. `Data`
This folder includes:

- `BitcoinHeistData.csv`: Raw data retrieved from the [UCI Machine Learning Repository](http://archive.ics.uci.edu/dataset/526/bitcoinheistransomwareaddressdataset).
- `BitcoinHeistDataPreProcessed.csv`: Preprocessed data post scaling and pre handling of class imbalance(https://www.dropbox.com/s/nqbasz68nihmuvz/BitcoinHeist-Dataset.zip?dl=0).

### 2. `Data Exploration & Preprocessing Figures`
This folder comprises plots and associated code that illustrate the data distribution of both the raw and preprocessed datasets. 

### 3. `Figures used in Journal`
This folder includes key plots used in the research paper, demonstrating:

- Data distribution of raw and preprocessed data (via boxplots)
- Correlation matrix of raw attributes
- Feature importance during the feature selection process
- Data distribution by labels
- Variance Inflation Factor (VIF) of the raw dataset

Detailed explanations for these plots can be found in the `Signature-based IDS` code file.

### 4. `Overall Description of Dataset`
It provides a detailed overview of both the raw and preprocessed datasets through various plots such as Pie plot, KDE plot, Histogram, Violin plot, and Q-Q plot.

> **Note:** In the context of this project, "Feature" is synonymous with "Attribute". For further details, delve into each folder and refer to the Python code within.

### 5. `Stage1_signature_based_RDS`
This folder houses the code for the first stage, the Signature-based RDS. It also contains tuned model files (`.pkl`) for decision tree, random forest, XGBoost, and stacking. Users can directly load these tuned models without having to retune. Additional documents detailing the experimental results of the Signature-based RDS are also included.

### 6. `Stage2_labeling_kmeans_anomaly_based_RDS`
In this folder, you will find the code for the second stage, the Anomaly-based RDS, and the simulation results named after ransomware families (Montreal, Padua, Princeton). For example, the Montreal folder refers to simulations where the Montreal ransomware family is excluded from the training data and used as simulated novel ransomware in the test data.

### 7. `Comparison Algorithms`
Several algorithms are benchmarked against our k-means labeling approach. These include:

- 2 Unsupervised Learning Algorithms:
   1. `Stage2_autoencoder`
   2. `Stage2_iForest`

- 3 Supervised Learning Algorithms:
   1. `Stage2_svm`
   2. `Stage2_xgboost`
   3. `Stage2_randomForest`

Each algorithm folder follows the same structure: code, three simulations results folders, and a Word document summarizing the experimental results.

### 8. `Stage2_Feature_Selection`
This folder contains the feature selection results for Stage2, which differ from Stage1 due to the unique data split method used. 

## Research Paper Abstract
Ransomware poses a significant threat to the security and integrity of cryptocurrency transactions. This research paper delves into the complexities of ransomware detection in cryptocurrency transactions using the Bitcoinheist dataset. Our proposed approach, a sophisticated hybrid of supervised and semi-supervised multistage machine learning framework, effectively classifies known ransomware families and accurately identifies previously unseen ransomware instances within the dataset. Rigorous evaluation employing comprehensive classification metrics, such as accuracy, precision, recall, F1 score, RoC score, and prediction time, underscores our approach's potential in enhancing ransomware detection within cryptocurrency transactions.