<div align="center" style="border: 2px solid #ccc; padding: 20px; border-radius: 12px; width: 80%; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.15);">
    <img
        width="180"
        height="220"
        alt="Logo - SURE ProEd"
        src="https://github.com/user-attachments/assets/88fa5098-24b1-4ece-87df-95eb920ea721"
        style="border-radius: 10px;"
    />

  <h1 align="center" style="font-family: Arial; font-weight: 600; margin-top: 15px;">SURE ProEd (formerly SURE Trust) 
      </h1>
<h2 style="color: #2b6cb0; font-family: Arial;">Skill Upgradation for Rural youth Empowerment Trust</h2>
</div>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<div style="padding: 20px; border: 2px solid #ddd; border-radius: 12px; width: 90%; margin: auto; background: #fafafa; font-family: Arial;">

<h2 style = "color:#333;"> Student Details </h2>
<div align = "left" style ="margin: 20px; font-size: 16px;">
    <p><strong>Name:</strong> Yashveer Singh </p>
    <p><strong>Email ID:</strong> yashveersingh37python@gmail.com </p>
    <p><strong>College Name:</strong> Dr. Sudhir Chandra Sur Institute of Technology & Sports Complex </p>
    <p><strong>Branch/Specialization :</strong> B.Tech in Computer Science and Engineering (AI & ML) </p>
    <p><strong>College ID:</strong> 25500123169 </p>
</div>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<h2 style="color:#333;"> Course Details </h2>
<div align="left" style="margin: 20px; font-size: 16px;">
    <p><strong>Course Opted:</strong> 6-Month Project-Based Internship in Artificial Intelligence & Machine Learning </p>
    <p><strong>Instructor Name:</strong> Gaurav Sir </p>
</div>

<div align="left" style="margin: 20px; font-size: 16px;">
    <p><strong>Duration:</strong> 6 Months </p>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<h2 style="color:#333;"> Trainer Details </h2>

<div align="left" style="margin: 20px; font-size: 16px;">

<p><strong>Trainer Name:</strong> Gaurav Patel </p>
<p><strong>Trainer Email ID:</strong>gaurav.patel.gpp@gmail.com </p>
<p><strong>Trainer Designation:</strong>Data Science Instructor</p>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<h2 style="color:#333;"> Projects Completed </h2>



# Fake Review Detection Project

Welcome to the comprehensive documentation for our Fake Review Detection project. This project is designed to distinguish between computer-generated (fake) reviews and original (human-written) reviews by leveraging a variety of natural language processing (NLP) techniques, traditional machine learning models, and deep learning methods. In this document, we detail the project background, data processing, feature engineering, model experimentation, experiment tracking using MLflow, and finally, the deployment of our application.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Data Collection & Preprocessing](#data-collection--preprocessing)
3. [Feature Engineering & Embeddings](#feature-engineering--embeddings)
4. [Modeling Approaches](#modeling-approaches)
   - [Traditional Machine Learning Models](#traditional-machine-learning-models)
   - [Deep Learning Models](#deep-learning-models)
5. [Experiment Tracking with MLflow](#experiment-tracking-with-mlflow)
6. [Deployment](#deployment)
7. [Docker Image](#docker-image)
8. [Conclusion](#conclusion)

---

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />


## Project Overview

Fake reviews are a growing problem in the online ecosystem, impacting consumer trust and business reputations. Our project aims to automatically detect and flag these computer-generated reviews by analyzing textual content. To achieve this, we have employed various techniques including:

- **Text Preprocessing:** Cleaning and normalizing text data.
- **Feature Engineering:** Extracting useful metrics such as lexical diversity, sentiment scores, and syntactic patterns.
- **Embeddings:** Generating different embeddings using methods such as TF-IDF, Count Vectorization, and precomputed embeddings from models like BERT and GloVe.
- **Model Training:** Experimenting with a range of traditional machine learning models (Logistic Regression, Random Forest, SVC) and a more complex deep learning model using a two-layer LSTM.
- **Experiment Tracking:** Logging every experiment with detailed metrics, hyperparameters, and artifacts using MLflow.

---

## Data Collection & Preprocessing

Our data consists of review texts along with corresponding labels indicating whether a review is computer-generated or original. The preprocessing pipeline includes:

- **Text Cleaning:** Removing unwanted characters, punctuation, and noise.
- **Normalization:** Converting text to lower case, tokenizing sentences and words, and applying techniques such as stemming, lemmatization, and stop word removal.
- **Feature Extraction:** Calculating metrics like lexical diversity, average word length, sentiment polarity, subjectivity, Flesch Reading Ease, sentence length, and various part-of-speech counts.

Processed data files are stored in our `../Data/Feature-Engineered/` folder.

---

## Feature Engineering & Embeddings

To capture the nuances of textual data, we explored several embedding techniques:

- **TF-IDF Embeddings:** Transforming text into weighted term-frequency representations.
- **Count Vectorization:** Creating basic term-frequency vectors.
- **Precomputed Embeddings:** Using models such as BERT and GloVe to generate embeddings, which are stored as CSV files in the `../../embeddings/` folder.

These methods provide diverse representations of the data, enabling our models to learn both syntactic and semantic patterns.


## Modeling Approaches

### Traditional Machine Learning Models

We experimented with several scikit-learn models:

- **Logistic Regression**
- **Random Forest Classifier**
- **Support Vector Classifier (SVC)**

For each model, we performed hyperparameter tuning using GridSearchCV with feasible parameter grids. Experiment results, including confusion matrices and metrics (accuracy, precision, recall, F1 score), are logged in MLflow.

### Deep Learning Models

To capture complex patterns, we built a deep learning model using TensorFlow Keras:

- **Two-Layer LSTM:** The model includes an embedding layer, two LSTM layers, and dense layers with dropout for regularization.
- **Text Tokenization & Padding:** We convert raw text into sequences using Keras’ Tokenizer and pad them to a uniform length.
- **Evaluation:** Model performance is evaluated on standard metrics and confusion matrices are logged.

---

## Experiment Tracking with MLflow

Our experiments are fully tracked using MLflow. For every run, we log:

- **Parameters:** File names, model types, hyperparameters, and embedding types.
- **Metrics:** Accuracy, precision, recall, and F1 score.
- **Artifacts:** Confusion matrices (as PNG images) and model artifacts.
- **Datasets:** Using the `mlflow.data` API, our dataset information is logged and appears under the MLflow UI's "Datasets" tab (for MLflow ≥ 2.4). When unavailable, the CSV files are logged as artifacts.




---




## Conclusion

Our project integrates advanced NLP techniques, comprehensive feature engineering, rigorous experimentation, and robust MLflow-based tracking to build a reproducible system for fake review detection. This documentation provides an end-to-end overview of our process, from data preprocessing and model training to deployment. We encourage you to explore the code repository and MLflow experiment dashboard for more details.



<hr style="height:1px; border-top:1px solid #ccc; width:80%;" />

<h2 id="project-report" style="color:#333;"> Project Report </h2>

<p>
  <a href="https://github.com/yyashh03/Fake-review-detection/blob/main/Fake_Review_Detection_Project_Report.pdf" target="_blank">
    <strong>→ View Full Project Report</strong>
  </a>
</p>

<hr style="height:1px; border-top:1px solid #ccc; width:80%;" />

## **References**


[![Python](https://img.shields.io/badge/Python-3.8-orange)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-2.0.2-blue)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.2.3-blue)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.5.2-yellow)](https://scikit-learn.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.18-yellow)](https://www.tensorflow.org/)
[![MLflow](https://img.shields.io/badge/MLflow-2.20.3-lightblue)](https://mlflow.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.7.6-green)](https://xgboost.readthedocs.io/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.43.0-red)](https://streamlit.io/)


## **Learnings from LST and SST**

LST and SST sessions played an important role in improving both my technical understanding and professional development throughout the internship period. These sessions provided valuable exposure to industry-oriented practices, communication techniques, and structured learning methodologies which helped me become more confident and disciplined in my approach towards project development and teamwork.

Through these sessions, I improved my communication skills, presentation abilities, and interpersonal interaction skills. Participating in discussions, collaborative activities, and learning exercises helped me develop confidence while expressing ideas, explaining technical concepts, and working effectively in team-oriented environments.

The sessions also helped me understand the importance of problem-solving, analytical thinking, time management, and proper documentation practices in real-world project development. I learned how structured planning, consistency, and systematic execution contribute significantly towards successful completion of technical projects and assignments.

In addition, LST and SST sessions provided guidance regarding professional ethics, workplace expectations, collaborative learning, and continuous self-improvement. These learnings helped me maintain a more organized and professional workflow during the development of the IntelliLearn-AI project and strengthened my understanding of practical implementation strategies.

Overall, the LST and SST sessions contributed significantly to my personal growth, professional readiness, and understanding of real-world project environments. The experience gained from these sessions enhanced both my technical confidence and my ability to work responsibly and effectively in academic as well as professional settings.

---

## **Community Services**

During my internship period, I actively participated in community-oriented activities focused on social responsibility and public welfare. These activities helped me understand the importance of contributing positively to society and working collaboratively for community development.

### **Activities Involved**

- **Tree Plantation Drive** – Participated in tree plantation activities near Dunlop, Kolkata and contributed towards promoting environmental awareness and greener surroundings.

- **Food Distribution Activity** – Participated in food distribution activities near Dunlop, Kolkata as part of social service and community support initiatives for needy people.

### **Impact / Contribution**

- Contributed towards environmental improvement through plantation activities.
- Supported community welfare initiatives by helping in food distribution activities.
- Improved communication, coordination, teamwork, and social responsibility skills.
- Gained practical exposure to community service and collaborative volunteering activities.
--- 
### **Photos**

<div align="center">

<img src="https://github.com/user-attachments/assets/b8744b2e-de2b-4298-9853-945f9cd665b7" alt="Community Service Photo 1" width="41%">

<img src="https://github.com/user-attachments/assets/e757c5f8-09c6-4e83-88f5-46864d38b89f" alt="Community Service Photo 2" width="41%">

</div>
---

## **Certificate**

The internship certificate serves as an official acknowledgment of the successful completion of my training period. It will be issued by the organization upon fulfilling all required tasks and meeting the performance expectations of the program. The certificate validates the skills, experience, and contributions made during the internship.

<!-- add your certificate image url below (inside src='')-->

<p align="center">
<img src="https://github.com/Lord-Rahul/Practice-Programs/blob/main/react/1/public/Gemini_Generated_Image_a6w8rda6w8rda6w8.png?raw=true" alt="Internship Certificate" width="80%">
</p>

---

## **Acknowledgments**

<!-- you can add Acknowledgments over here in same syntax as below . eg trainer name , company name , role etc -->

- [Prof. Radhakumari Challa](https://www.linkedin.com/in/prof-radhakumari-challa-a3850219b) , Executive Director and Founder - [SURE Trust](https://www.suretrustforruralyouth.com/)



