# Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards


Keeping track of patient waitlists for both inpatient and outpatient services is essential in the field of contemporary healthcare. Enter Power BI, a potent technology that uses data-driven insights to enhance hospital operations. This post explores a Power BI dashboard intended to optimize patient waitlists, delving into the realm of healthcare data visualization. By utilizing its potential, healthcare providers can obtain essential data that helps them organize patient care, manage resources efficiently, and ultimately improve the standard of care given. Come see how this technology is revolutionizing waitlist management and enhancing patient experience and healthcare results.

![summary page](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/e395ef63-3ec1-49d3-9ff4-6c71522a514c)


## Detailed view

![detailed view](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/fd7fe9c6-ba31-496c-9af2-9be662ce495a)


## Summary with drilldown 
![sum with drilldown](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/265c63d0-56a0-476d-81c9-ec08963659d4)


The following are the five essential steps of this project:
1.Data Gathering
2.Data Transforming and Modelling
3.Table Connections
4.Layout and Designing
5.Analysis and Visualization

## 1.Data Gathering:
I collected precise and comprehensive patient information from Kaggle, including time stamps for patient entrance and discharge, age, adult status, visits by specialty (cardiology, general surgery, psychology), and length of stay. These rich datasets for inpatient and outpatient records from 2018 to 2021 were divided into two distinct tables, which enabled me to use Power BI for thorough analysis and the development of my healthcare analytics skills.

## 2.Data Transforming and Modelling:
I imported the data stored in the directory using Power BI's basic folder connection in order to start converting and modeling the data. I started data transformations in Power Query by making sure the right data types were there, estimating the amount of data, and removing duplicate values to maintain coherence. I fixed a difference by adding a new column, "case_type," specifically for the outpatient database and aligning it with the "day-case" and "inpatient" values in the inpatient table after merging both tables into "All_data." This made it easier to distinguish between the tables after adding. In the end, I loaded the table into the Power BI environment and stored it for more analysis.

![all data](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/6a3377f2-18a4-4ae7-9555-ab8c02390457)

## 3.Table Connections:
I created a specialty table by hand that divided patient specializations into discrete categories in order to improve dashboard clarity and optimize table linkages. This specialized table streamlines the dashboard's presentation by grouping specializations like orthopaedics under the "bones-related group" and haematology under the "blood-related group." Then, using the 'Speciality' column as a guide, I connected 'All_data' to the 'Mapping_Specialty' table so that the Power BI dashboard could provide a more logical and perceptive analysis.

![table connection](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/4cef8af9-826d-47ba-bd55-1552c5998d9e)


![speciality group](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/d4e75331-3b60-4ecf-b903-26b5db6b21a9)

## 4.Layout and Designing: 
Designing the layout of a dashboard requires thoughtful planning and strategic placement of visual elements to convey information effectively. To achieve this, I crafted a blueprint that begins with a title and Key Performance Indicators (KPIs), showcasing the current year’s total waitlist and a comparative view with the previous year. I incorporated a pie chart depicting the case type distribution alongside time bands, complemented by an age profile bar chart for contextual information. Additionally, I included a filtered display of the top 5 specialties based on average and median, considering outliers within the dataset. To offer a comprehensive overview, I integrated a monthly trend analysis of inpatient and outpatient cases categorized by case type from 2018 to 2021.

Background Layout: To become a proficient data analyst, understanding the art of design and color is vital. I began by browsing Google for dashboard designs, selecting one that appealed to me. Using a website that provides color extraction, I obtained the exact color palette from this dashboard. Moving to PowerPoint, I created a background by drawing boxes with the ‘Shapes’ tool, representing the spaces for individual charts and filters. To enhance these boxes, I experimented with gradients, borders, and formatting options under ‘Format Background’. This iterative process helped me to familiarize myself with design elements and refine my initial concept for the background design of the dashboard. This is what I came up with, just select all and right-click to save the background picture to use in the dashboard.

## 5.Analysis and Visualization

In initiating my analysis, I posed several pivotal questions to guide the exploration of the dataset:

1.How does the current year’s total waitlist compare to the previous year?
2.How many Patient falls under which Case Type?
3.How does the duration of hospital stays vary across different age groups of patients?
4.What are the top 5 wait lists by specialty?
5.What are the monthly trends observed among patients with different case types?

## How does the current year’s total waitlist compare to the previous year?
So as per the data to calculate the previous and Current year’s wait list I had to implement measures to showcase it in my KPIs.


Here’s the DAX

i)Current Year Wait List

Latest month Waiting List = CALCULATE(SUM(All_data[Total]),All_data[Archive_Date]=max(All_data[Archive_Date])) + 0

ii)Previous Year’s Wait List

PY latest month Waiting list = CALCULATE(SUM(All_data[Total]),All_data[Archive_Date]=edate(max(All_data[Archive_Date]),-12)) + 0


The increase in the current year’s waitlist to over 700,000 individuals, compared to the previous year’s 640,000, indicates a notable surge in demand for healthcare services. This growth of over 60,000 patients signifies a substantial uptick in the number of individuals seeking inpatient and outpatient care within the given timeframe. Several factors might contribute to this escalation, such as population growth, changes in healthcare needs, extended referral times, or variations in healthcare policies impacting access to services

![waitlist](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/4a76f997-b94f-47f0-8736-2aa3be6d0269)

## How many Patient falls under which Case Type?

The pie chart illustrates how patients are divided into different categories based on their treatment needs. It shows that a large majority, around 65.25%, fall under the ‘outpatient’ category, indicating that most people visit for treatments that don’t require a hospital stay. On average, this category accounts for nearly 80 patients seeking this type of care. Comparatively, ‘inpatient’ cases, needing hospital stays, represent a smaller share at 10.98%, while ‘day_case’ holds 23.78% of the distribution. This data emphasizes the high demand for outpatient services, suggesting a need for efficient management to cater to this significant portion of patients seeking care without hospital admission. Understanding these proportions helps healthcare facilities tailor their services better to meet patient needs effectively.

![donut](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/f3cc326f-ad67-40f9-a80d-100a3c3a2901)

## How does the duration of stays in hospital vary across different age groups of patients?
The stacked bar chart displays the duration of hospital stays categorized by age groups: 0–15, 16–64, and 65+. The data indicates that a substantial number of patients across various age brackets experience hospital stays lasting 18 months or more. This extended duration is notably prevalent among different age groups, with 66 individuals from the 65+ age group, 138 from the 16–64 age group, and 102 patients from the 0–15 age group.

Furthermore, a discernible pattern emerges, highlighting that the age group spanning 16–64 years represents the majority of admitted patients across different stay durations. This observation suggests a higher rate of hospitalization within the 16–64 age bracket compared to the other age groups. Understanding this pattern aids healthcare providers in tailoring specialized care and resources for this age range, potentially addressing specific health needs or conditions prevalent within this demographic.

![bar chart](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/85fb42be-bd38-4234-8bc8-33c821c9aee4)

## What are the top 5 wait lists by specialty?
The analysis of the top 5 waitlisted specialties reveals a notable trend towards pediatric-focused medical areas. Pediatric Dermatology emerges at the top of the list with an average waitlist of 172 patients, closely followed by Pediatric ENT with 149 patients. Additionally, Accident and emergency, Pediatric Cardiology, and Pediatric Orthopedic specialties follow suit in the ranking.

This trend underscores the significant concern and demand for pediatric medical services among patients. The higher waitlists in pediatric specialties indicate a substantial need for specialized care and attention for children and adolescents. It emphasizes the necessity for healthcare providers and facilities to focus on allocating resources, expertise, and timely access to these pediatric specialties to address the specific health needs of younger patient demographics.


![top5](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/c6318b28-8e4e-4732-9b67-d11d030f520b)

## What are the monthly trends observed among patients with different case types?

The line graph depicting trends from 2018 to 2021 illustrates relatively stable figures for day-case and inpatient cases, hovering around 57,000–60,000 for day-case and 22,000–23,000 for inpatient services. Contrastingly, there’s a noticeable and substantial upward trend in outpatient cases, rising from 0.5 million to 0.63 million over the same period.

![case type](https://github.com/Bhimashankark/Transforming-Healthcare-Patient-Waitlists-with-Power-BI-Dashboards/assets/124131684/8fedf063-ae58-43c3-ba5f-7aa2970e5598)

## The substantial rise in outpatient cases observed over the years could be influenced by several factors:

## 1.Advancements in Medical Technology: 
Medical advancements and technological innovations might allow for more procedures and treatments to be conducted on an outpatient basis, reducing the need for hospital stays.

## 2.Patient Preferences:
Many patients prefer outpatient care when possible due to convenience, lower costs, and the ability to recover in the comfort of their homes.
## 3.Healthcare Policies:
Changes in healthcare policies or insurance coverage might encourage outpatient care, making it more accessible and affordable for patients.
## 4. Efficiency and Effectiveness: 
Outpatient care is often associated with shorter waiting times and quicker access to services, making it a preferred option for certain medical conditions or treatments.
## 5.Shift in Healthcare Practices:
 Healthcare providers may be increasingly opting for outpatient treatments as they become more efficient and safe, allowing for the same level of care without the need for extended hospital stays.


# Conclusion:
In summary, our analysis unveiled key insights into healthcare trends. The data showcased a significant surge in outpatient cases over the years, indicating a shift towards non-hospital-stay treatments. Pediatric specialties emerged as focal points, with high waitlists, emphasizing the need for specialized care for children. Furthermore, stable figures were noted for inpatient and day-case services. Factors like technological advancements and patient preferences likely drive the rise in outpatient care. Understanding these trends is vital for healthcare providers to meet evolving patient needs effectively and allocate resources efficiently.
