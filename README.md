# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import required libraries
 Import libraries such as pandas, sklearn, and numpy.
2. Load the dataset Read the email dataset containing email text and labels (Spam or Ham).

3. Preprocess the data Remove unwanted characters and symbols.
4. Convert text into lowercase.
5. Convert text into numerical form
   Use TF-IDF Vectorizer to convert email text into numerical feature vectors. Split the dataset
6. Divide the dataset into training data and testing data using train_test_split().
7.  Train the SVM mode Apply Support Vector Machine classifier (SVC) and train it using the training dataset. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Hari Ramesh
RegisterNumber:212225100016
# Import required libraries
import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score, classification_report

# Step 1: Create a sample dataset
data = {
    "Email": [
        "Win a free lottery now",
        "Meeting scheduled for tomorrow",
        "Congratulations you won money",
        "Project discussion today",
        "Claim your free gift card",
        "Lunch meeting at office",
        "You have won a free ticket",
        "Important update about your account"
    ],
    "Label": [
        "Spam",
        "Ham",
        "Spam",
        "Ham",
        "Spam",
        "Ham",
        "Spam",
        "Ham"
    ]
}

df = pd.DataFrame(data)

# Step 2: Convert labels to numeric values
df['Label'] = df['Label'].map({'Spam': 1, 'Ham': 0})

# Step 3: Convert text emails into numerical features
vectorizer = TfidfVectorizer()
X = vectorizer.fit_transform(df['Email'])

# Step 4: Define target variable
y = df['Label']

# Step 5: Split dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Step 6: Train SVM model
model = SVC(kernel='linear')
model.fit(X_train, y_train)

# Step 7: Predict on test data
y_pred = model.predict(X_test)

# Step 8: Evaluate the model
print("Accuracy:", accuracy_score(y_test, y_pred))
print("\nClassification Report:\n", classification_report(y_test, y_pred))

# Step 9: Test with a new email
new_mail = ["Congratulations! You have won a free prize"]
new_mail_vec = vectorizer.transform(new_mail)
prediction = model.predict(new_mail_vec)

if prediction[0] == 1:
    print("\nThe email is Spam")
else:
    print("\nThe email is Not Spam")
*/
```

## Output:


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
