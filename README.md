# SENTIMENT-ANALYSIS-OF-AMAZON-ALEXA-REVIEWS-USING-MACHINE-LEARNING


Here’s a refined and structured explanation of your **Amazon Alexa Review Analysis** project, which you can use for revision or explanation during interviews:  

---

### **Amazon Alexa Review Analysis**  

#### **Overview**  
This project aimed to analyze customer reviews of Amazon Alexa, explore patterns in the dataset, and build predictive models to classify feedback as positive or negative.

---

### **Steps Undertaken**  

#### **1. Data Exploration and Preprocessing**  
- **Dataset**:  
  - Size: 3,150 rows and 5 columns (`rating`, `feedback`, `date`, `variation`, `verified_reviews`).  

- **Initial Analysis**:  
  - Checked for missing values: Found one null value in the `verified_reviews` column, which was dropped due to its negligible impact.  

- **Feature Engineering**:  
  - Added a new column `length`, storing the length of each string in the `verified_reviews` column.  

#### **2. Exploratory Data Analysis (EDA)**  
- **Rating Analysis**:  
  - Counted occurrences of different ratings.  
  - Visualized data with bar graphs (counts) and pie charts (percentages).  

- **Feedback Analysis**:  
  - Feedback had two categories: Positive (1) and Negative (0), with a distribution of 92% and 8%, respectively.  
  - Plotted bar graphs and pie charts to visualize counts and percentages.  
  - Mapped ratings to feedback values:  
    - Negative feedback (0): Ratings 1 and 2.  
    - Positive feedback (1): Ratings 3, 4, and 5.  

- **Variation Analysis**:  
  - Analyzed the count of each product variation.  
  - Calculated mean ratings for each variation and plotted a bar graph in ascending order of mean ratings.  

- **Verified Reviews Analysis**:  
  - Analyzed the distribution of review lengths.  
  - Visualized relationships between review length, feedback values, and ratings using histograms.  

#### **3. Text Processing**  
- Used **CountVectorizer** to convert text into a bag-of-words model.  
- Generated **word clouds** for:  
  - Top 50 frequent words in all reviews.  
  - Unique words for each feedback category:  
    - **Positive Words**: amazing, love, great, learning, alexa.  
    - **Negative Words**: echo, repair, back, working, cycle.  

#### **4. Preprocessing for Modeling**  
- Cleaned and processed text data:  
  - Replaced non-alphabetic characters with spaces.  
  - Converted text to lowercase.  
  - Removed stopwords (e.g., "is," "the").  
  - Applied stemming to reduce words to their root forms (e.g., "running" → "run").  

- Built a **corpus** of processed words for modeling.  

#### **5. Modeling**  
- **Target Variable (`Y`)**: Feedback (0 or 1).  
- **Features (`X`)**: Bag-of-words representation of the corpus.  
- Split data using **train_test_split** (70% training, 30% testing).  

- **Model 1: Random Forest**  
  - Achieved **94.5% accuracy**.  
  - Evaluated performance with a confusion matrix.  
  - Used **K-fold cross-validation**: Average accuracy of **93.3%**.  
  - Tuned hyperparameters with **Grid Search CV**:  
    - Best parameters:  
      ```  
      {'bootstrap': True, 'max_depth': 100, 'min_samples_split': 10, 'n_estimators': 300}  
      ```  
    - Final accuracy: **94.5%**.  

- **Model 2: XGBoost**  
  - Training Accuracy: **97.1%**.  
  - Testing Accuracy: **93.4%**.  
  - Evaluated performance using a confusion matrix.  

---

### **Key Outcomes**  
- Identified and visualized patterns in customer feedback and ratings.  
- Built robust classification models with high accuracy to predict customer feedback.  
- Highlighted the importance of hyperparameter tuning and cross-validation in improving model performance.  

---
