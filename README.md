🧓 Senior Citizen Identification System – Project Overview
This project focuses on the real-time identification of senior citizens in public spaces using computer vision and deep learning techniques. It is designed to be deployed in locations such as shopping malls, local stores, or waiting areas, where recognizing and attending to senior citizens is essential.

The system uses a webcam to continuously monitor people in the environment. It detects multiple faces in a frame, predicts their age and gender, and automatically labels individuals aged 60 or above as senior citizens. All detected information, including age, gender, and timestamp of detection, is logged in a structured format (CSV file) for future reference or analytics.

Dataset:https://www.kaggle.com/datasets/jangedoo/utkface-new

🔍 Problem Statement
Manual identification of senior citizens in busy environments is time-consuming and inefficient. To overcome this challenge, an automated system is needed that can:
Detect people in real-time
Predict their age and gender
Identify those aged 60 or above
Log data for record-keeping
This project provides a working solution using machine learning and computer vision.

🎯 Objectives of the Project
Build a real-time application that captures and processes webcam video feed.
Use deep learning to predict age (as a regression task) and gender (as a classification task).
Identify and label senior citizens based on the age threshold (≥ 60).
Store the detected information (age, gender, time of visit) in a CSV file.
Avoid repeated logging of the same person within a short time frame.

🛠️ Technologies and Tools Used
Python – Programming language used for implementation.
TensorFlow/Keras – For building and training the deep learning model.
OpenCV – For face detection and webcam feed processing.
NumPy and Pandas – For numerical operations and data logging.
Matplotlib – For visualizations (if needed).
Jupyter Notebook – For organizing and running the code in a structured way.

📂 Dataset Used
The model is trained using a version of the UTKFace dataset, organized into two folders: male/ and female/, where:
Each image filename starts with the age of the person (e.g., 45_male.jpg).
Images are preprocessed by resizing to 128×128 pixels and normalized.

🧠 Model Architecture
The project uses a Convolutional Neural Network (CNN) with a shared base and two separate output branches:
Age Prediction: Regression output using a single neuron (no activation).
Gender Prediction: Classification output using a softmax layer with two classes (Male, Female).

The model is compiled with:
Loss functions: mean squared error for age, categorical crossentropy for gender

Optimizer: Adam
Evaluation metrics: MAE for age, accuracy for gender

🏁 Workflow Summary
Data Preparation:
Images are loaded and labels (age, gender) extracted from filenames.
A custom Keras Sequence generator is used to handle large data efficiently.

Model Training:
The model is trained using the prepared dataset.
Early stopping is used to prevent overfitting.

Model Evaluation:
The model achieves over 91% accuracy in gender prediction and an MAE of ~6.9 years in age prediction on validation data.

Real-Time Inference:
The webcam feed is used to detect faces using OpenCV.
Each detected face is passed through the trained model.
The system displays the predictions on-screen and logs each new detection.

Data Logging:
Every time a new person is detected, their age, gender, and time of detection are saved into a file called visitor_log.csv.
The same person is not logged again within 10 seconds, preventing duplicate entries.

📝 Conclusion
This project successfully demonstrates a practical application of AI in public service environments. It uses real-time video processing and deep learning to detect and classify individuals by age and gender, highlighting those who may require special attention. It can be further extended with GUI support, multi-camera setups, or cloud-based analytics.
