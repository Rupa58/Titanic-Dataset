📊 Titanic Dataset - Exploratory Data Analysis (EDA)
This project performs Exploratory Data Analysis (EDA) on the famous Titanic dataset using Python, NumPy, Pandas, Matplotlib, and Seaborn. The goal is to understand the patterns behind passenger survival by analyzing various features such as age, sex, passenger class, fare, etc.

📁 Dataset
File name: titanic.csv

Records: 418 passengers

Features:

PassengerId

Survived (0 = No, 1 = Yes)

Pclass (1 = 1st class, 2 = 2nd class, 3 = 3rd class)

Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked

🛠️ Tools Used
Python 3.x

NumPy – for numerical computations

Pandas – for data manipulation

Matplotlib – for data visualization

Seaborn – for advanced plots

📌 Steps Performed
1. Loading and Understanding the Data
Used .info(), .describe(), .value_counts() to get data overview.

Identified missing values (Age, Cabin, Fare) and outliers.

2. Statistical Analysis
Calculated mean, median, mode, standard deviation using NumPy:

python
Copy
Edit
np.mean(), np.median(), np.std(), .mode()
3. Data Cleaning
Handled missing values:

Filled Age with mean

Filled Fare with median

Dropped rows with too many missing values

4. Data Visualization
✅ Using Matplotlib:
Histogram of Age

Boxplot of Fare vs Pclass

Scatterplot of Age vs Fare (colored by Survival)

✅ Using Seaborn:
Countplot: Survival by Gender and Class

KDE Plot: Age distribution by Survival

Heatmap: Correlation between features

📈 Key Insights
Women and 1st Class passengers had a higher survival rate.

Fare and Pclass are highly correlated with survival.

Most passengers were aged between 20-40 years.

📋 Summary of Findings – Titanic EDA
🔹 1. Survival Rate
Overall survival rate: ~36%

Females had a much higher survival rate than males.

1st class passengers survived at a higher rate than 2nd and 3rd class.

🔹 2. Passenger Class (Pclass)
Pclass 1: Highest survival (~63%)

Pclass 3: Lowest survival (~24%)

Fare distribution showed higher fares in 1st class passengers.

🔹 3. Gender (Sex)
Female passengers: ~75% survived

Male passengers: ~20% survived

Sex is one of the most influential features for survival.

🔹 4. Age
Most passengers were aged 20–40 years.

Children and young adults had relatively higher survival rates.

The elderly (above 60) had lower chances of survival.

🔹 5. Fare
Passengers who paid higher fares had better survival chances.

Many high-fare passengers were in 1st class, often with cabins assigned.

🔹 6. Family Relationships (SibSp & Parch)
Moderate family size (1–2 relatives aboard) had slightly higher survival.

Too many family members (5+) or none at all had lower survival rates.

🔹 7. Embarked Location
Most passengers embarked from Southampton (S).

Cherbourg (C) passengers had the highest survival rate among ports.

🔹 8. Missing Values
Cabin had many missing values (~78%).

Age had moderate missing values (~20%).

These were handled via imputation (mean/median) or dropped for plotting.

🔹 9. Correlation Matrix
Positive correlation:

Fare and Survived

Parch and Survived

Negative correlation:

Pclass and Survived

Sex (converted to numeric) would also show strong correlation if included.

✅ Final Observations
Women, children, and 1st class passengers were prioritized during evacuation.

Socioeconomic factors like class and fare played a major role in survival.

Gender was the strongest predictor of survival in the dataset.

📊 1. Count Plot – Survival Distribution
python
Copy
Edit
sns.countplot(x='Survived', data=df)
🔍 Observation:
The number of passengers who did not survive (0) is significantly higher than those who survived (1).

Indicates that the overall survival rate was low (~36%).

📊 2. Count Plot – Survival by Gender
python
Copy
Edit
sns.countplot(x='Survived', hue='Sex', data=df)
🔍 Observation:
Females had a much higher survival rate compared to males.

Most male passengers did not survive, indicating gender played a major role in survival.

📊 3. Count Plot – Passenger Class Distribution
python
Copy
Edit
sns.countplot(x='Pclass', data=df)
🔍 Observation:
Most passengers belonged to 3rd class, followed by 1st and 2nd.

Implies that 3rd class was the most populated.

📊 4. Count Plot – Survival by Class
python
Copy
Edit
sns.countplot(x='Pclass', hue='Survived', data=df)
🔍 Observation:
1st class passengers had the highest survival rate.

3rd class passengers had the lowest survival rate.

Reflects social class impact on survival chances.

📊 5. Histogram – Age Distribution
python
Copy
Edit
sns.histplot(df['Age'].dropna(), bins=30)
🔍 Observation:
Most passengers were aged between 20 and 40 years.

Some children (aged 0–10) and elderly passengers were also on board.

📊 6. KDE Plot – Age vs Survival
python
Copy
Edit
sns.kdeplot(df[df['Survived']==1]['Age'], label='Survived')
sns.kdeplot(df[df['Survived']==0]['Age'], label='Not Survived')
🔍 Observation:
Survivors were generally younger, with a spike in children surviving.

Elderly passengers had lower survival rates.

📊 7. Count Plot – Survival by Embarkation Port
python
Copy
Edit
sns.countplot(x='Embarked', hue='Survived', data=df)
🔍 Observation:
Passengers from Cherbourg (C) had the highest survival rate.

Most passengers embarked from Southampton (S).

📊 8. Violin Plot – Age by Class
python
Copy
Edit
sns.violinplot(x='Pclass', y='Age', data=df)
🔍 Observation:
1st class passengers were typically older than those in 3rd class.

3rd class had a wide spread of younger passengers, including children.

📊 9. Box Plot – Fare by Class
python
Copy
Edit
sns.boxplot(x='Pclass', y='Fare', data=df)
🔍 Observation:
1st class passengers paid significantly higher fares.

Fare range decreases with class: 1st > 2nd > 3rd.

📊 10. Heatmap – Correlation Matrix
python
Copy
Edit
sns.heatmap(df.corr(), annot=True)
🔍 Observation:
Fare and Pclass have strong negative correlation (higher class → higher fare).

Survived has positive correlation with Fare, and negative with Pclass.

Sex was not included here numerically; converting it to numeric would show strong correlation with survival.

Very few Cabin values are available (only ~20%).

