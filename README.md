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
