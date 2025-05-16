📘 Project: Analyzing Students' Mental Health

📌 Overview
This project investigates how studying abroad affects the mental health of university students, using real survey data collected at a Japanese international university. The original 2018 study, published in 2019 and ethically approved, found that international students face higher risks of mental health challenges than domestic peers. It also identified social connectedness and acculturative stress as key predictors of depression.

In this project, we used PostgreSQL to explore and analyze a dataset of 286 students to determine:

Whether international students show higher levels of depression.

How social connectedness and acculturative stress relate to depression scores.

Whether the length of stay in the host country is a contributing factor to mental health outcomes.


🧠 Key Mental Health Metrics
The dataset includes scores from standardized psychological assessments:

PHQ-9 (todep) — measures depression

SCS (tosc) — measures social connectedness

ASISS (toas) — measures acculturative stress


🛠️ Tools Used
PostgreSQL for querying and analyzing data

DataCamp DataLab as the notebook environment

GitHub for version control and collaboration


🔍 Insights Gained
International students generally show higher average PHQ-9 scores.

Depression correlates negatively with social connectedness and positively with acculturative stress.

The length of stay influences mental health outcomes: newly arrived students often show different average scores compared to those who have been in the country longer.


📊 Sample Query Used
sql
Copy
Edit
SELECT stay,
       COUNT(*) AS count_int,
       ROUND(AVG(todep), 2) AS average_phq,
       ROUND(AVG(tosc), 2) AS average_scs,
       ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC
LIMIT 9;


📁 Dataset Fields
Field Name	Description
inter_dom	Student type (International or Domestic)
japanese_cate	Japanese language proficiency
english_cate	English language proficiency
academic	Academic level (Undergraduate/Graduate)
age	Age of the student
stay	Length of stay in years
todep	PHQ-9 depression score
tosc	SCS social connectedness score
toas	ASISS acculturative stress score

📄 License
This project is for educational purposes and analysis based on publicly shared, anonymized data. Check the source institution’s data usage guidelines if you plan to reuse it.
