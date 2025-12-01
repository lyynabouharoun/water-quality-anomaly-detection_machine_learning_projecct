# Water Potability Classification – Machine Learning Project

## Overview
This project applies several Machine Learning techniques to classify water samples as potable (1) or not potable (0). The work includes data preprocessing, PCA, clustering, supervised classification, and model evaluation.

The project was completed for the Machine Learning module at Université M’Hammed Bougara de Boumerdès (2024–2025).

## Dataset
The dataset contains 3276 samples with the following physicochemical features:
pH, Hardness, Solids, Chloramines, Sulfate, Conductivity, Organic Carbon, Trihalomethanes, Turbidity.

Target variable:
Potability (0 = not drinkable, 1 = drinkable).

## Preprocessing
- Handling missing values (mean or median)
- Outlier detection using IQR
- Feature scaling (StandardScaler)
- Train/Test split with stratification
- PCA for dimensionality analysis and visualization

## Unsupervised Learning (K-Means)
- Applied after PCA transformation
- Evaluated using Silhouette Score, Inertia, and Calinski–Harabasz index
- Best k = 2
- ~60% alignment with true labels
- Confirms weak natural separation in the dataset

## Supervised Models

### KNN
- Best k = 28
- Accuracy ~65%
- Low recall for class 1
- SMOTE improves recall but reduces accuracy

### SVM
- RBF kernel, C=1, gamma="scale"
- Accuracy ~67%
- SMOTE significantly increases recall for potable water

### ANN
Architecture: Dense(32, ReLU) → Dense(16, ReLU) → Dense(1, Sigmoid)  
- Accuracy ~65.3%
- Stable training, no overfitting
- Confirms limited discriminative power of features

## Key Insights
- PCA helps visualize structure but shows no clear separation
- SMOTE improves minority class recall
- SVM and ANN deliver the best performance
- Overall accuracy remains limited due to weak dataset features
- The dataset lacks biological or microbiological indicators needed for reliable potability prediction
