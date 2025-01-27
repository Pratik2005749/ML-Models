# Quark-Gluon Jet Classification

This project performs **quark-gluon jet classification** using machine learning techniques. The goal is to classify jet data into quark or gluon categories based on various features like transverse momentum, rapidity, azimuthal angle, and PDG ID.

## Data

The dataset used in this project is stored as a `.npz` file, which contains the features (`X`) and labels (`y`) for jet classification. The features are in the shape `(100000, 139, 4)` where:
- **100000** is the number of jets (samples),
- **139** is the number of particles per jet,
- **4** is the number of features for each particle.

The labels (`y`) contain binary values:
- **0** for gluon jets,
- **1** for quark jets.

You can load the data from your Google Drive after mounting it.

## Data Preprocessing

1. **Feature Aggregation**: 
   The features are aggregated (mean value) for each jet:
   - **Mean p_T**
   - **Mean Rapidity**
   - **Mean Azimuthal Angle (ϕ)**
   - **Mean PDG ID**

   The features are stored in a `jet_features` array for further analysis.

2. **Data Visualization**:
   Several visualizations are created to explore the data:
   - Histograms of each feature (Mean p_T, Mean Rapidity, etc.) for quark vs gluon jets.
   - Scatter plot of **Mean p_T vs Mean Rapidity**.
   - Box plots of each feature by jet label.

## Model Training and Evaluation

1. **Data Splitting**: 
   The dataset is split into training and testing sets (80% train, 20% test).

2. **Model Selection**: 
   A **Random Forest Classifier** is used to classify the jets. The model is trained on the scaled features, and the classification performance is evaluated using:
   - **Accuracy**
   - **Classification Report** (Precision, Recall, F1-Score)

3. **Feature Scaling**: 
   The features are scaled using **StandardScaler** to ensure they are standardized (zero mean, unit variance).

## Results

The model outputs a **classification report** and **accuracy** for the test set, showing how well it can distinguish between quark and gluon jets.
