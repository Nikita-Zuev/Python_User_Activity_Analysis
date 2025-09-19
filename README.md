# User Churn and Activity Metrics Analysis

## Project Description

This project is dedicated to a comprehensive analysis of user data to find the key factors that affect churn. It also aims to monitor user activity using these main metrics:
* DAU (Daily Active Users)
* WAU (Weekly Active Users)
* MAU (Monthly Active Users)

**Main stages of the project:**

* Collecting data on user activity and characteristics by parsing a webpage. 
* Cleaning and transforming data for analysis, including combining datasets, processing dates, and removing outliers. 
* Visualizing key activity metrics (DAU, WAU, MAU) and identifying user behavior patterns. 
* Conducting a cohort analysis to evaluate user retention. 
* Calculating and visualizing the Churn Rate for each game separately. 
* Developing and implementing a machine learning model to predict churn. 
* Identifying the most important factors that contribute to churn, to help develop effective retention strategies.

  

## Cohort Analysis

A cohort is a group of users who started using a product (or had their first interaction) in the same defined period (in this project, one month).

1. Cohort Formation: Users are grouped by the month of their first activity (cohort_month). This allows you to track the behavior of that specific group over time. 
2. Tracking Retention: After the cohorts are formed, we analyze what part of these users stay active in the next months. This is shown with two heatmaps that present: 
    * The number of active users in each cohort (absolute values). 
    * The percentage of user retention in the periods after their first activity.
3. Identifying Trends: Cohort analysis helps to discover how the long-term retention of different user groups changes. For example, you can see if newer cohorts have better or worse retention rates than older ones.



## Аналіз Відтоку (Churn Rate) за Іграми

1.  Розрахунок метрик активності: Для кожного користувача визначається дата першої та останньої активності, а також загальна тривалість його "життя" у продукті.
2.  Визначення відтоку (Churn): Користувач вважається "відтіклим", якщо виконуються дві умови:
    * Його остання активність була більше ніж 7 днів тому.
    * Він був активним у грі щонайменше 7 днів (це дозволяє відфільтрувати користувачів, які лише спробували гру і не повернулися, від тих, хто був залучений, але згодом пішов).
3.  Розрахунок Churn Rate: Відсоток відтоку обчислюється для кожної гри шляхом ділення кількості "відтіклих" користувачів на загальну кількість унікальних користувачів у цій грі.
4.  Візуалізація: Результати представлені у вигляді стовпчастої діаграми, що дозволяє наочно порівняти показники відтоку між іграми.



## Модель, що визначає вплив метрик на відтік клієнтів

1.  **Формування ознак (Features)**: Для моделі використовуються такі характеристики користувача:
    * `age` (вік)
    * `language` (мова)
    * `has_older_device_model` (наявність старого пристрою)
    * `activity_variety` (різноманітність ігрових дій)
    * `n_days_active` (загальна кількість днів активності)
2.  Навчання моделі: Для аналізу використовується алгоритм Random Forest Classifier, який навчається на підготовлених даних для прогнозування відтоку.
3.  Виявлення ключових факторів: Після навчання модель дозволяє оцінити важливість (importance) кожної ознаки. Результати візуалізуються на графіку, що наочно демонструє, які фактори мають найбільший вплив.

**Ключовий висновок з моделі:**
Hайважливішими факторами, що впливають на відтік, є кількість днів активності та вік гравця. Натомість мова, модель пристрою та різноманітність дій мають значно менший вплив.
