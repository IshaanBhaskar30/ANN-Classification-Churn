💼 Project Overview: Customer Churn Prediction using Artificial Neural Network (ANN)

This project is an end-to-end pipeline for predicting customer churn using a bank dataset. It includes data preprocessing, model building with TensorFlow, and deployment via a Streamlit web app. The objective is to classify whether a customer will exit (churn) or stay, based on various demographic and financial features.

The complete workflow consists of:

->experiment.ipynb – model development and training

->prediction.ipynb – testing the model with sample inputs

->app.py – interactive web application for real-time predictions



📊 Dataset Summary

The dataset Churn_Modelling.csv contains 10,000 customer records from a bank, with information such as:

->Demographics (Age, Gender, Geography)

->Bank usage (Balance, Tenure, Number of Products)

->Behavior (IsActiveMember, HasCrCard)

->Target label: Exited (1 if the customer left, 0 otherwise)



🔧 Key Steps & Workflow

🔹 1. Data Preprocessing (experiment.ipynb)
->Dropped irrelevant features (RowNumber, CustomerId, Surname)

->Encoded categorical variables:

   o Gender → LabelEncoder

   o Geography → OneHotEncoder

->Saved all encoders (.pkl files) for inference use

->Split data into training and test sets (80/20)

->Standardized the data using StandardScaler



🔹 2. Model Building with ANN

->Built a 3-layer ANN:

   o 2 hidden layers: 64 and 32 neurons with ReLU activation

   o 1 output layer with sigmoid activation for binary classification

->Used Adam optimizer and binary crossentropy as loss function

->Implemented:

   o EarlyStopping to avoid overfitting

   o TensorBoard for performance visualization

->Achieved ~88% accuracy on training and ~85% on validation data

->Saved the final model as model.keras



🔹 3. Model Inference (prediction.ipynb)

->Loaded the trained model and pickled encoders

->Created a sample customer input dictionary

->Performed:

   o Label encoding and one-hot encoding

   o Feature scaling

   o Final churn probability prediction

->Displayed prediction with a clear message based on threshold (0.5)



🔹 4. Web Application (app.py)

->Built an intuitive Streamlit UI to collect user inputs

->Dynamically:

   o Encodes Gender and Geography

   o Applies saved StandardScaler

   o Feeds data to the ANN model

->Displays churn probability and user-friendly output message

->Supports real-time predictions in a lightweight frontend

