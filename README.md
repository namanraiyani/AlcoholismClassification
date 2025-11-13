# AlcoholismClassification

This notebook analyzes EEG (Electroencephalography) data to classify subjects into two groups: Alcoholic and Control. Using signal processing techniques and machine learning, the goal is to identify patterns in brain wave activity that distinguish between the two conditions.

Methodology
1. Data Processing
Data Loading: The Large SMNI EEG Dataset (Train and Test sets) is loaded and concatenated into a single dataframe. Subjects are separated into 'Alcoholic' (a) and 'Control' (c) groups.

Signal Filtering: A Butterworth Bandpass Filter (1–30 Hz) is applied to the raw EEG sensor values to isolate relevant brain wave frequencies and remove noise/artifacts.

Feature Engineering: The data is aggregated by time and sensor position, calculating the mean filtered value. It is then pivoted to create a structure where rows represent time points and columns represent sensor positions (e.g., AF3, AF4, C1, etc.). This essentially treats instantaneous brain activity patterns (averaged across the group) as the samples for classification.

2. Machine Learning Model
Data Setup: The pivoted datasets for Alcoholic (labeled 1) and Control (labeled 0) groups are combined.

Splitting: The data is split into training and testing sets (70/30 split) with stratification.

Scaling: Features are standardized using StandardScaler to normalize sensor values.

Classifier: A Support Vector Machine (SVM) classifier is trained on the scaled data to discriminate between the two classes based on sensor activity patterns.

Results
The SVM model achieved high performance in distinguishing between the Alcoholic and Control groups based on the processed EEG time-points.

Accuracy: 92%

Precision (Weighted Avg): 0.92

Recall (Weighted Avg): 0.92

F1-Score (Weighted Avg): 0.92

AUC (Area Under Curve): ~0.92 (calculated in code)
