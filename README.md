# Machine Learning Personality Predictor

This machine learning model utilizes the scikit-learn and pandas Python libraries, in addition to Kaggle's "Extrovert vs. Introvert Behavior Data," in order to make predictions about individuals' personalities.\
\
The Kaggle dataset that was used can be accessed here → https://www.kaggle.com/datasets/rakeshkapilavai/extrovert-vs-introvert-behavior-data

# How the Model Works

The goal of this model is to predict if a user has more or less friends, based on the other data about each individual provided.\
\
After loading the required modules and the dataset, the model first checks for the presence of null values in the dataset.\
Then, the numeric data called "Friends_circle_size" is sorted into two bins (more_friends and less_friends) using pandas' "cut" method.\
**For this model, a friend group of 0-3 friends is considered having "less friends," while a group of 4-15 friends is considered as having "more friends."**\
\
<img width="747" height="227" alt="Screenshot 2025-07-16 at 11 06 10 AM" src="https://github.com/user-attachments/assets/1000634e-a057-41bf-88da-8f89fc07ecd2" />
\
Scikit-learn's "LabelEncoder" is then utilized to alter the dataset by using a "0" for the "less_friends" bin and a "1" for the "more_friends" bin.\
The other string features in the dataset (Stage_fear, Drained_after_socializing, and Personality) are then also encoded to numeric values.\
\
To train and test the data, scikit-learn's "train_test_split" function is used by separating the data into X and y variables.\
These variables hold the dataset without "Friends_circle_size" and just the "Friends_circle_size" column respectively.\
Scikit-learn's "StandardScaler" is then applied for further preprocessing.\
\
Three classifiers are tested in this model to compare the accuracy of their predictions.\
The classifiers include RandomForest, SVM, and MLP.\
\
By comparing their predictions to the "y_test" data (via scikit-learn's "accuracy_score" function), it was evident that the accuracy of all three classifiers were very close:\
\
<img width="909" height="335" alt="Screenshot 2025-07-16 at 11 05 21 AM" src="https://github.com/user-attachments/assets/c38687da-3c56-4bd3-9bbd-7a5ad3cf71c3" />
