# Capstone Case Study: How Can a Wellness Technology Company Play It Smart?
## A Google Data Analytics Professional Certificate Capstone Project
## Introduction 

Welcome to the **Bellabeat Data Analysis Capstone Case Study**, a project developed as part of the **Google Data Analytics Professional Certificate**.

In this case study, I take on the role of a junior data analyst working for **Bellabeat**, a high-tech company that manufactures health-focused smart products for women. Under the guidance of Bellabeat’s cofounder and Chief Creative Officer, **Urška Sršen**, this project explores how smart device usage data can be leveraged to drive meaningful marketing insights and support strategic growth.

The goal of this project is to analyze smart device fitness data to uncover user behavior trends and recommend data-driven marketing strategies that can help Bellabeat become a larger player in the global wellness technology market.

Throughout this analysis, I follow the six steps of the data analysis process:
**Ask → Prepare → Process → Analyze → Share → Act**  
These steps provide a structured framework to guide the case study and deliver actionable insights.

By the end of this project, the findings and recommendations presented here will serve as a **portfolio-ready example** of how data analytics can impact business decisions and growth strategies in the real world.

For this case study, I utilized **R**, including **RStudio** and **R Markdown**, due to its versatility in handling data cleaning, analysis and visualization, as well as its effectiveness in documenting the entire workflow. Throughout the Google Data Analytics Certificate program, I also gained experience with additional tools such as **Spreadsheets**, **SQL**, and **Tableau**, which have further enhanced my data analysis capabilities.

🔗 To learn more about the company behind this case study, visit the [Bellabeat website](https://bellabeat.com).

## Business Problem Scenario

Bellabeat is a growing wellness technology company with the potential to expand its presence in the global smart device market. Co-founder and Chief Creative Officer **Urška Sršen** believes that by analyzing data from their smart devices, Bellabeat can uncover valuable insights that will help identify new growth opportunities.

As part of the **marketing analytics team**, I have been tasked with analyzing **user behavior data from the Bellabeat app**. The goal is to discover trends in how consumers interact with Bellabeat’s products and use these insights to support a data-driven marketing strategy.

Bellabeat’s product ecosystem includes:

- **Bellabeat App**: Monitors user activity, sleep, stress, menstrual cycles, and mindfulness habits to promote a healthier lifestyle.
- **Leaf**: A wellness tracker that can be worn as a bracelet, necklace, or clip—tracks activity, sleep, and stress levels.
- **Time**: A smart wellness watch that blends fashion with functionality by tracking activity, sleep, and stress.
- **Spring**: A smart water bottle that tracks daily hydration to ensure proper water intake.
- **Bellabeat Membership**: A subscription service offering personalized guidance on wellness, including fitness, nutrition, sleep, mindfulness, and more.

Through this analysis, I aim to help Bellabeat better understand user behavior and make informed marketing decisions that support sustainable business growth.

## Ask

### Deliverable 1: Business task

Analyze smart fitness device usage data to gain insight into how people already use them and help guide future marketing strategies for the Bellabeat App. 

### Stakeholders:
- **Urška Sršen** – Chief Creative Officer and co-founder of Bellabeat  
- **Bellabeat marketing analytics team** – Responsible for using data to guide marketing strategy  
- **Bellabeat executive team** – Decision-makers who will use insights from this analysis to support company growth

## Prepare
### Deliverable 2: Data Source Description

#### Data: Introducing the Fitbit Fitness Tracker Data

**Brief**: The Fitbit Fitness Tracker dataset, collected through Amazon Mechanical Turk from 30 users in 2016, provides minute-level smart device data focused on physical activity, heart rate, and sleep monitoring. This dataset is publicly accessible on Kaggle.

- **Access the data**: [FitBit Fitness Tracker Data on Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit)
- **Contributor**: Möbius, a data scientist with a healthcare focus

---

#### Bias and Credibility Concerns

The data was collected via Amazon Mechanical Turk, which introduces several potential biases:

- **Sampling bias**: Small, non-random sample of only 30 users
- **Selection bias**: Participants opted in, potentially skewing user profiles
- **Demographic bias**: No gender or demographic data available
- **Incentive-driven bias**: Participation could be influenced by compensation, not natural usage

---

#### Data Quality Checks (ROCCC)

| **Data Quality Check** | **Assessment** |
|------------------------|----------------|
| **Reliable**           | Moderate – Easy to work with, but limited by small sample size and lack of diversity |
| **Original**           | No – Data was not collected directly by Fitbit, but via a third-party platform |
| **Comprehensible**     | Moderate – Structure is mostly clear, though variations in user data and missing entries impact usability |
| **Current**            | Outdated – Collected in 2016; technology and usage patterns may have evolved |
| **Cited**              | Yes – Properly cited on Kaggle, shared under public domain (CC0) license |

---

#### Licensing, Privacy, Security, and Accessibility

| **Data Aspect**  | **Assessment** |
|------------------|----------------|
| **Licensing**    | CC0 1.0 Universal Public Domain Dedication – Free to use, modify, and distribute |
| **Privacy**      | No personally identifiable information included |
| **Security**     | Data stored securely in a password-protected MySQL database |
| **Accessibility**| Freely accessible on Kaggle for analysis and public sharing |

---

#### Data Integrity Verification

Data integrity was maintained through a structured cleaning and preparation process, which included:

- Column renaming and standardization
- Data type conversion
- Removal of duplicate and zero-value rows
- Inspection for outliers and inconsistencies

---

#### Relevance to This Analysis

Although the dataset has limitations, it offers meaningful behavioral insights into how users interact with fitness trackers. These insights are relevant when examining product use cases for Bellabeat. However:

- The absence of gender-specific data limits precision for Bellabeat's female-focused offerings
- Biases in data collection should be considered when interpreting the results

> ⚠️ *Note*: Finding updated or alternative Fitbit datasets proved difficult.

## Process
### Deliverable 3: Data cleaning process 
As part of the data processing phase, I followed a structured cleaning and transformation workflow to ensure the dataset was accurate, consistent and ready for analysis. Below is a summary of the key cleaning and manipulation steps performed:

- Checked for missing values across all datasets to ensure data integrity.
- Standardized column names to lowercase using clean_names() for consistency.
- Converted data types (e.g., date and time formats, numeric fields) to allow proper analysis.
- Removed duplicate entries to eliminate redundancy and prevent skewed results.
- Filtered out rows with zero values in critical metrics like total_steps, assuming non-usage of the device on those days.
- Analyzed unique user IDs across datasets to detect discrepancies in data coverage and engagement.

This step ensured that the data was in the best possible shape for analysis, improving both the reliability and the interpretability of the insights drawn later in the project.

## Analyze
### Deliverable 4: A summary of your analysis

**General Observations**

Data discrepancies were noted between the Kaggle dataset description (which mentions 30 users) and the available datasets. 

For example, the user count varies across different datasets, such as:
"activity_clean" (33 IDs)
"steps_clean" (33 IDs)
"calories_clean" (33 IDs)
"intensities_clean" (33 IDs)
"sleep_clean" (24 IDs)
"heartrate_clean" (14 IDs)
"weight_clean" (8 IDs)

This discrepancy may be due to users owning multiple Fitbit devices or an inconsistency in the dataset description.

**Missing Data**

I observed a noticeable gap in activity data reporting, especially in early May. Users who consistently reported more than 75% of data had a steady activity record, while those below 75% experienced a decline in reporting starting in late April.


**Correlations**

Several activity metrics like total distance, tracker distance, and total steps are highly correlated, meaning they convey similar information. This suggests that users' activity levels are reflected across these metrics.

**User Behavior Insights**

- Activity Insights

Over half of the users (58%) log a healthy daily step count ranging from 5,000 to 10,000 steps, but only about one-fifth (21%) of users consistently achieve the 10,000-step goal.

A significant portion of users’ average intensity minutes is spent in sedentary or lightly active states, making up 97% of their daily activity. 

Specifically:
Sedentary minutes account for around 80%.
Lightly active minutes contribute to 17%.
Very active and fairly active minutes are only 2% and 1%, respectively. 

This suggests a lack of moderate to vigorous activity among most users.

Users took the most steps on Saturday and the least number of steps on Sunday

- Caloric Expenditure

Around 42% of users have an average daily calorie expenditure between 1,600 to 2,200 calories

- Sleep Insights
  
53% of users sleep less than 7 hours per night, indicating a possible sleep deficiency.

- Heart Rate
  
Heart rate readings for most users fall within the normal range, indicating typical heart health.

**Conclusions and Implications**
These insights can help Bellabeat tailor its marketing strategies and product improvements. By understanding users' activity and sleep patterns, as well as their interaction with the app, Bellabeat can refine strategies to increase engagement and maximize the utility of its product. 

**Key actions could include:**

Developing personalized fitness challenges for users based on their activity levels.
Enhancing sleep tracking features to better address the needs of users with irregular sleep patterns.
Encouraging more active behavior by targeting users with higher sedentary time, and offering suggestions for integrating more moderate-to-vigorous activity into their routines.
These insights could directly influence future product features and marketing approaches to better meet the needs of users and increase overall engagement.

## Share

## Deliverable 5: Supporting visualizations and key findings

The insights I discovered—especially around user activity patterns, sleep behavior, and heart rate trends—shed light on how users are engaging with the Bellabeat app and its features in real life.

To communicate these findings effectively, I adapted my approach based on the needs of different audiences:

**Audience-Focused Communication**

For Bellabeat stakeholders:
I created a PowerPoint presentation that visually summarizes the key findings. The presentation focuses on clear, standalone graphs that cover:
Average and median step count
Intensity of daily activity minutes
Sleep duration and consistency
Heart rate insights
This format was chosen to support quick, intuitive understanding for a non-technical audience.

For technical review and reproducibility:
A detailed R Markdown report accompanies the presentation. It includes:
Data cleaning and transformation steps
Statistical summaries and visualizations
Justifications for filtering or excluding data
Annotated code blocks for reproducibility
This dual-format approach ensures both accessibility and analytical transparency.

![Screenshot 2025-05-13 at 1 09 12 PM](https://github.com/user-attachments/assets/a9a89381-da55-49e4-874d-fff58fd16a78)
![Screenshot 2025-05-13 at 1 10 41 PM](https://github.com/user-attachments/assets/b9bd68ba-a479-4640-9bb5-53433d52d34d)
![Screenshot 2025-05-13 at 1 11 02 PM](https://github.com/user-attachments/assets/a3b0913c-9536-4045-82f0-0f7fe9cd183b)
![Screenshot 2025-05-13 at 1 11 19 PM](https://github.com/user-attachments/assets/e18dff61-0867-4146-b84e-399a833d60c6)
![Screenshot 2025-05-13 at 1 11 37 PM](https://github.com/user-attachments/assets/9cc3575c-ae3f-409f-9331-f936df481e76)
![Screenshot 2025-05-13 at 1 11 53 PM](https://github.com/user-attachments/assets/d8ebb79e-42a5-41df-9bb5-f8f96fbab997)
![Screenshot 2025-05-13 at 1 12 01 PM](https://github.com/user-attachments/assets/9608b1d0-a343-4cf5-9379-933866839250)
![Screenshot 2025-05-13 at 1 12 08 PM](https://github.com/user-attachments/assets/fe2c36b3-e597-43e6-befa-3fae21ae35f4)

## Act
## Deliverable 6: Your top high-level insights based on your analysis

After thoroughly examining user patterns in activity, sleep, heart rate, and engagement, I’ve identified a number of behavioral trends that can help Bellabeat refine its user experience and maximize retention. These insights open the door for strategic product enhancements and more focused marketing approaches.

**What the Data Tells Us**

Most users spend the majority of their day in sedentary or lightly active states — with very little time dedicated to moderate or vigorous activity.
Sleep durations for over half of the users fall below the recommended 7 hours per night.
Users display consistent heart rate patterns within a typical range, indicating that anomalies are rare but detectable.
There is minimal engagement with manual data logging (e.g., weight and body fat), suggesting a disconnect between users and tracking behaviors.
Engagement levels tend to follow daily life routines, with noticeable spikes in the early morning and after typical working hours.

**Key Recommendations for Bellabeat**

1. Encourage Physical Activity Through Smarter Personal Nudges

A large portion of users are not reaching minimum activity recommendations. Rather than taking a one-size-fits-all approach, Bellabeat can tailor encouragement based on current habits:

Introduce dynamic goals that adapt weekly based on prior performance.
Use friendly push notifications during low-activity hours to suggest movement.
Highlight progress toward small wins to keep motivation high.
The idea is to make healthy habits feel achievable — not overwhelming — while boosting long-term engagement.

2. Build Smarter Sleep Support Into the App

With sleep being such a critical part of well-being, the app can better support users by:

Identifying inconsistent sleep routines and providing practical guidance for improving sleep hygiene.
Offering a “sleep score” that rewards progress over time.
Sending gentle reminders to wind down based on user sleep patterns.
These features could help shift the majority of users into healthier sleep durations.

3. Integrate Real-Time Heart Health Monitoring

Since most users fall into a normal resting heart rate zone, there's an opportunity to take that further:

Implement an alert system that notifies users when their heart rate deviates from expected patterns.
Offer simple educational tips or encourage calming activities when elevated heart rates are detected.
Use heart rate zones to personalize fitness goals and recovery insights.
This feature not only adds value but reinforces trust in the app as a comprehensive health companion.

4. Reduce Friction in Manual Logging

Users show low interaction with manual data entry, especially in the weight logging dataset. Bellabeat can:

Incentivize consistent tracking through rewards or visual streaks.
Make syncing with external devices more seamless.
Use periodic prompts to encourage users to verify or update their data.
The goal is to make tracking feel effortless and clearly linked to user progress.

5. Tackle the May Drop-Off

Activity tracking dropped sharply at the end of May — likely due to seasonal change (e.g., summer vacations, schedule shifts).

Launch a “Summer Kickstart” campaign to re-engage users with seasonal content and challenges.
Use personalized messages that acknowledge the break and invite them back.
Offer incentives (like rewards, discounts, or exclusive insights) for users who return after inactivity.
Turning seasonal dips into reactivation points can dramatically improve long-term retention.

**Final Takeaway**
Users are showing interest, but their full potential is untapped. By responding to behavioral trends — like sedentary time, summer disengagement and inconsistent sleep — Bellabeat can strengthen user relationships and boost daily value. These data-driven strategies don’t just keep users active in the app — they build loyalty, trust and long-term satisfaction.
