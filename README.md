# Promise+

Promise+ is an extension of the Promise_exp Software Requirements database. Requirement databases can assist in creating automatic requirement classification models. The dataset contains requirements in English, and the classes included in Promise+ are: F (Functional), A (Availability), L (Legal), LF (Look and Feel), MN (Maintainability), O (Operational), PE (Performance), SC (Scalability), US (Usability), FT (Fault Tolerance), and PO (Portability).

Promise+ was built following the guiding principles of the first expansion (PROMISE_exp). After a web search, 42 software requirements documents were selected. These documents had their requirements analyzed by six experts. To validate the classification, five experts had their classifications compared to the sixth expert. From this comparison, the kappa index was derived.

The image below shows the details of the methodology:

![Methodology Flow of the Database](https://github.com/user-attachments/assets/4caa0d20-bf41-4bd0-bad0-0c8a5091336a)

Promise+ represented a significant quantitative increase in data, as shown in the table below:

![Quantitative Comparison between the Databases](https://github.com/user-attachments/assets/450a0717-d378-4e12-aad4-a24a04addc3e)

To enhance the understanding of the added software requirements documents, an analysis was conducted regarding the type of software. The following software classifications were used: system, application, scientific/engineering, embedded, product line, web, and artificial intelligence. In the file "Lista dos tipos de software.xlsx," each software type is linked to the requirement document ID. The chart below shows the distribution of these different types:

![Chart (2)](https://github.com/user-attachments/assets/370e8ee4-20e5-4d27-acaf-e7f239e653a6)

Another analysis conducted was to determine whether the requirements document was from academia or industry, with 18 from academia and 24 from industry.

The Promise+.arff file is available for use with the Weka tool. This file contains all the requirements, the list of industry project IDs, the list of academic project IDs, and the label for each requirement. The Promise+.csv file contains only the requirement text and the label.

For citation purposes, Promise+ is also hosted on Zenodo under the following DOI: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.12805484.svg)](https://doi.org/10.5281/zenodo.12805484). The article is available at: https://shorturl.at/heyS5

Promise+ can be used for the following tasks:

    - Binary Classification between Functional and Non-Functional requirements
    - Multiclass Classification among Non-Functional requirements
    - Multiclass Classification with all classes

Below is an example of using Promise+ in a Multiclass Classification pipeline with all classes, implemented in Python. The process involves importing Promise+ into a dataframe, transforming textual classes into numerical classes, splitting the data into training and testing sets, and finally, defining the machine learning algorithm:

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.neighbors import KNeighborsClassifier
from sklearn.pipeline import Pipeline
from sklearn.metrics import classification_report

# Load the Promise+ file into a pandas DataFrame
df = pd.read_csv('Promise+.csv')

# Separate the features (requirement text) and the target (label)
X = df['Requirement']
y = df['Label']

# Encode the labels (Label)
label_encoder = LabelEncoder()
y_encoded = label_encoder.fit_transform(y)

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y_encoded, test_size=0.2, random_state=42)

# Create a pipeline with TF-IDF for text vectorization and KNN as the classifier
pipeline = Pipeline([
    ('tfidf', TfidfVectorizer()),  # Vectorize the requirement text
    ('knn', KNeighborsClassifier(n_neighbors=3))  # KNN with 3 neighbors
])

# Train the model
pipeline.fit(X_train, y_train)

# Make predictions
y_pred = pipeline.predict(X_test)

# Classification report
print(classification_report(y_test, y_pred, target_names=label_encoder.classes_))


