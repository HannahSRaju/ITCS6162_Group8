# Assessing Students Health🩺 & Academic📖 Performance🎗️

## Deliverable 1

### Team Members:
- Hannah Raju
- Harshith Vemula
- Sai Manikanta Karnati
- Sai Sri Mohan Da

![Students-Phones](https://github.com/user-attachments/assets/e948fd67-f636-4624-b30c-cd6b582ceda7)


### Project Introduction:
This project investigates the impact of mobile phone usage on students' health and academic performance. The dataset comprises various attributes related to students' demographics, mobile phone usage patterns, health symptoms, and academic outcomes. By analyzing these data points, we aim to understand how mobile phone usage affects students' academic success and well-being. The goal of this project is both descriptive and predictive: to describe current trends and predict potential outcomes based on mobile phone usage. We plan to use supervised learning techniques, specifically classification and regression analysis, to identify significant predictors of academic performance and health outcomes. This involves exploring relationships between mobile phone usage patterns (e.g., time spent, activities, and educational app usage) and variables such as performance impact, distraction, attention span, and health symptoms.

### Research Question:
How does mobile phone usage influence students' academic performance and health, and what are the key predictors of these outcomes?
 
### Relevant Domain Information:
- [Does mobile phone usage really impact students’ academic performance?](https://elismurcia.com/blog/mobile-phone-usage-impact-students-academic-performance/)
- [The Relationship between Cellphone Usage on the Physical and Mental Wellbeing of University Students: A Cross-Sectional Study](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9368281/pdf/ijerph-19-09352.pdf)

### Data Source and Description:
The [dataset](https://www.kaggle.com/datasets/innocentmfa/students-health-and-academic-performance?resource=download) is sourced from a survey conducted on students' mobile phone usage, health, and academic performance.
The attributes include:

- Names: Student names
- Age: Student ages (in years)
- Gender: Male/Female
- Mobile phone: Do students own a mobile phone? (Yes/No)
- Mobile Operating System: Type of mobile operating system used (e.g., Android, iOS, Other)
- Mobile phone use for education: Frequency of mobile phone usage for educational purposes (Sometime/Frequently/Rarely)
- Mobile phone activities: List of mobile phone activities used for educational purposes (e.g., online research, educational apps, email, online learning platforms)
- Helpful for studying: Do students find mobile phone use helpful for studying? (Yes/No)
- Educational Apps: List of educational apps used
- Daily usages: Average daily time spent using mobile phone for educational purposes (in hours)
- Performance impact: How does mobile phone use impact academic performance? (Agree/Neutral/Strongly agree)
- Usage distraction: Does mobile phone use distract from studying? (During Exams/Not Distracting/During Class Lectures/While Studying)
- Attention span: Has mobile phone use affected attention span? (Yes/No)
- Useful features: What features of mobile phones are useful for learning? (e.g., Internet Access, Camera, Calculator, Notes Taking App)
- Health Risks: Are students aware of potential health risks associated with excessive mobile phone use? (Yes/No/Only Partially)
- Beneficial subject: Which subjects benefit most from mobile phone use? (e.g., Accounting, Browsing Material, Research)
- Usage symptoms: Are students experiencing any physical or mental symptoms related to mobile phone use? (e.g., Sleep disturbance, headaches, Anxiety or Stress, All of these)
- Symptom frequency: How often are symptoms experienced? (Sometimes/Never/Rarely/Frequently)
- Health precautions: Are students taking precautions to mitigate potential health risks? (Taking Break during prolonged use/Using Blue light filter/Limiting Screen Time/None of Above)
- Health rating: How would students rate their overall physical and mental health? (Excellent/Good/Fair/Poor)

### Data Understanding and EDA:
We created several different visualizations to gain an understanding on the dataset we are working with.

This first visualization looks at the age distribution of the students in the dataset. We see that the majority of the students fall into the range of 21-25 with just under 70 of the 100 students falling into that category.

![download](https://github.com/user-attachments/assets/bac8541f-a3b4-4eb7-acef-f6461881bd04)<br/>

Next, we wanted to see how the gender distribution looked and found that most of the students were males.

![download](https://github.com/user-attachments/assets/0a0d924b-f5eb-46ac-846b-77173fc162f7)<br/>

One of the attributes in the data is 'Usage symptoms' which has the following symptom categories: 'Headache', 'All of these', 'Sleep disturbance', 'Anxiety or Stress', 'Sleep disturbance;Anxiety or Stress', and 'Headache;Sleep disturbance;Anxiety or Stress;All of these'. We see that most students spend about 4-6 hours on their phones daily and experience all of the symptoms. Sleep disturbance and headache were common and high-frequency symptoms across the higher daily usage ranges.  

![download](https://github.com/user-attachments/assets/12e9652b-c766-478e-82c5-56e794470d3b)<br/>

Another area we explored was the type of mobile activities that each age category ranged in. Keeping in mind that the majority of the students fall into the 21-25 age category, we see that this age group engages in all the following activities 'Messaging', 'Social Media', and 'Web-browsing'. 

![download](https://github.com/user-attachments/assets/6008c08d-2393-41fc-9fd7-6e505261b5c0)<br/>

The graph provides a clear picture of the mobile operating system landscape among your respondents, highlighting the relative prevalence of each platform. The students in this dataset mainly have Androids.

![download](https://github.com/user-attachments/assets/2f1969ab-5e49-4b8c-945a-0e4e9a390b97)<br/>

This analysis helps in understanding user perceptions and can be used to address potential issues related to mobile phone usage and performance in educational or work settings. The majority of students believe that mobile phone use has an impact on performance or feel neutral. 

![download](https://github.com/user-attachments/assets/4a89453a-dc89-43fb-8fde-95d533a2a14d)<br/>

The pie chart displays the proportion of different symptom frequencies reported by respondents.

![download](https://github.com/user-attachments/assets/39e317e0-726c-4d3a-9a54-570515962f86)<br/>

Here we compare the types of distractions experienced by males and females, providing a clear picture of how mobile phone usage impacts attention.

![download](https://github.com/user-attachments/assets/bd28d87d-8347-47a8-96de-7e224bf6b2a0)<br/>

We can see if students are aware of potential health risks associated with excessive mobile phone use through this visualization.

![download](https://github.com/user-attachments/assets/45699707-9314-4d78-a1ad-92a728dfceba)<br/>

## Deliverable 2

### Data Preparation:
The data preparation process in the notebook begins with importing essential libraries such as numpy, pandas, seaborn, and matplotlib for data manipulation and visualization. The dataset is then loaded from a CSV file hosted on GitHub into a pandas DataFrame using the pd.read_csv function. Basic information about the dataset, including the number of non-null entries, data types of the columns, and memory usage, is displayed using the df.info() command. The data was checked for null values and the small number of null values were dropped. When trying to use a certain column to create a visualization, there was an error due to the column name having extra space so the data frame columns were cleaned with the .strip function. These initial steps ensure that the data is ready for further analysis and manipulation. Before creating models, the data was encoded using LabelEndcoder() because all the variables were categorical. SMOTE was also applied to balance the data. 

### Modeling:  
For the initial models, we chose all the variables except for the target variable ('Performance Impact') as the predictors. We trained and evaluated the following models: Logistic Regression, Decision Tree, Random Forest, and K-Nearest Neighbors. This resulted in the following accuracy scores: Logistic Regression-0.52, Decision Tree-0.65, Random Forest0-0.73, and K-Nearest Neighbors-0.50. Then we tried using the feature selection SelectKBest() to choose the best 10 features and trained the models again. We narrowed the best features down further to 'Daily usages', 'Usage distraction', 'Usage symptoms', 'Symptom frequency', and 'Health rating'. This resulted in the following accuracy scores: Logistic Regression-0.34, Decision Tree-0.73, Random Forest0-0.71, and K-Nearest Neighbors-0.60. We also used GridSearchCV() to see if the models could be improved more with all the variables except for the target variable but got lower scores. Then we tried again with the narrowed-down predictors list, resulting in the following accuracy scores: Logistic Regression-0.23, Decision Tree-0.65, Random Forest-0.71, and K-Nearest Neighbors-0.63. Pycaret was also implemented and explored.

### Evaluation: 
Target: Performance Impact --> 0: Agree, 1: Neutral, 2: Strongly agree, 3: Strongly disagree, 4: Disagree<br/>

Accuracy: measures the overall correctness of a classification model. It is the proportion of total correct predictions (both true positives and true negatives) to the total number of predictions. In other words, it tells you how often the model is correctly classifying the instances in the dataset.<br/>
Recall: For each performance impact category (e.g., Agree, Neutral, Strongly agree, Strongly disagree, Disagree), recall measures how well the model identifies students correctly in that category out of all the actual students in that category. For example, if there are 100 students who "Agree" that mobile phone usage impacts performance, and the model correctly identifies 80 of them, the recall for the "Agree" category is 80%.<br/>
Precision: Precision measures the accuracy of the model’s predictions for each category. For instance, if the model predicts 90 students as "Agree," but only 80 of them are actually in the "Agree" category, the precision for the "Agree" category is 89% (80 out of 90).<br/>
F1-Score: The F1-score combines precision and recall into a single metric for each category. It is particularly useful when there is an imbalance in the dataset. For example, if the "Strongly agree" category has fewer instances, the F1-score provides a balanced measure of the model's performance for that category.<br/>
Support: Support indicates the number of students in each performance impact category in the dataset. For example, if there are 100 students who "Agree," 50 who are "Neutral," 30 who "Strongly agree," 20 who "Strongly disagree," and 40 who "Disagree," these numbers provide the context for evaluating recall, precision, and F1-score.<br/>

The accuracy scores and classification reports for the highest-performing models can be seen below. <br/>

<img width="500" alt="image" src="https://github.com/user-attachments/assets/289ec1bd-202f-44ba-b36c-9f9dffebe9c7"><br/>

The evaluation metrics for several other models using Pycaret are provided in the below diagram. From this, we can observe that Extra Trees Classifier and Extreme Gradient Boosting have the best accuracy.<br/>

<img width="550" alt="image" src="https://github.com/user-attachments/assets/8c8ea1c7-13ec-4249-9cd8-36171cfa4767"><br/>

### Conclusion/Results:  
Best Model(s): The Decision Tree and Random Forest Classifier models achieved the highest accuracy of 73% and 71% when trained using the limited selected features as predictors.<br/>
Significant Predictors: The most influential predictors of academic performance included daily mobile phone usage, usage distraction, usage symptoms, symptom frequency, and health rating.<br/>
Health Symptoms: Prolonged mobile phone usage was strongly correlated with symptoms like sleep disturbances and headaches.<br/>
Educational Benefit: Mobile phones were beneficial for subjects such as research and accounting.

### Known Issues: 
Data Imbalance: Smaller datasets often suffer from data imbalance, which can be partially mitigated using techniques like SMOTE or by adding more rows to the dataset.<br/>
Overfitting: Smaller datasets are more prone to overfitting. Cross-validation and simpler models might help in reducing overfitting.<br/>
Bias in Self-reported Data: Self-reported data might introduce bias. Incorporating objective measures can improve the reliability of the analysis.<br/>
Generalizability: The findings from a small dataset might not be generalizable. Expanding the dataset in future studies can help improve generalizability.
