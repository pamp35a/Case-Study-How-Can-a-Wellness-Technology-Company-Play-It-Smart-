# Case-Study-How-Can-a-Wellness-Technology-Company-Play-It-Smart-
This will be my case study about analyzing smart device data to gain insight into how consumers are using their smart devices.

Scenario: Bellabeat, a high-tech manufacturer of health-focused products for women, is a successful small company, but they have the potential to become a larger player in the global smart device market. Our job is to work on their marketing analyst team, and focus on one of Bellabeat’s products and analyze smart device data to gain insight into how consumers are using their smart devices. The insights we discover will then help guide marketing strategy for the company.

1. Ask

Business Task: Analyzing FitBit fitness tracker data to gain insights into how consumers are using the FitBit app and discover trends for Bellabeat marketing   strategy.

Who are the stakeholders for Bellabeat?

Urška Sršen: Bellabeat’s co-founder and Chief Creative Officer
Sando Mur: Mathematician and Bellabeat’s co-founder
Bellabeat marketing analytics team: A team of data analysts responsible for collecting, analyzing, and reporting data that helps guide Bellabeat’s marketing strategy.

2. Prepare

Sršen encourages you to use public data that explores smart device users’ daily habits. She points you to a specific data set: https://www.kaggle.com/datasets/arashnic/fitbit

In this phase, we find the limitations in this dataset to be: 
- Data was collected in 2016, so users’ daily activity, fitness and sleeping habits, diet and food consumption may have changed since then.
- The sample size of 30  users is not representative of the entire fitness population. A larger sample size would be preferred. 
- A lot of the data was recorded from Tuesday to Thursday, which may not be comprehensive enough to form an accurate analysis.

Does the data follow ROCCC?
- Reliability: Not very reliable as the dataset only shows for 30 users.
- Original: Data is from 30 FitBit users who consented to the submission of personal tracker data through Amazon Mechanical Turk.
- Comprehensive: Data given is for minute-level output for physical activity, heart rate, and sleep monitoring. While the data tracks some factors in the user activity and sleep, the sample size is too small and most of the data is recorded during certain days of the week
- Current: Data is from March 2016 to May 2016, so the data is not current. Users habits may have changed.
- Cited: Data collected from third party, so unknown.

Based on ROCCC, this would not be a good dataset to analyze.

3. Process

In this phase we will process the data by cleaning it. I will be using RStudio for data cleaning,data transformation,data analysis and visualization. We can begin by checking if data contains any missing or null values. Then we can transform the data into format we want for the analysis.

To begin the process, we must install and read the packages we need for the analysis: I have all packages installed, so I read all the packages simultaneously.

# Installing packages : 
install.packages("tidyverse")
install.packages("lubridate")
install.packages("dplyr")
install.packages("ggplot2")
install.packages("tidyr")
install.packages("here")
install.packages("skimr")
install.packages("janitor")

> library(tidyverse)
── Attaching packages ────────────────────────── tidyverse 1.3.2 ──
✔ ggplot2 3.3.6     ✔ purrr   0.3.4
✔ tibble  3.1.8     ✔ dplyr   1.0.9
✔ tidyr   1.2.0     ✔ stringr 1.4.0
✔ readr   2.1.2     ✔ forcats 0.5.1
── Conflicts ───────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()

Then I must load these packages. 

# Loading packages :

library(tidyverse)
library(lubridate)
library(dplyr)
library(ggplot2)
library(tidyr)
library(here)
library(skimr)
library(janitor)

Now I can import my dataset.

# Importing Activity dataset, :

Activity <- read.csv("../input/fitbit/Fitabase Data 4.12.16-5.12.16/dailyActivity_merged.csv")
head(Activity)
colnames(Activity)
str(Activity)

