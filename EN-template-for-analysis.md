**6 November 2025**<br>
**MPAD 2003 - Introductory Data Storytelling**<br>
**Lainey Berry, Ryleigh Hillier, and Lily Moore**<br>
**Presented to Jean-Sébastien Marier**<br>

# Exploratory Data Analysis (EDA) & Pitch

## 1. Introduction

For our exploratory data analysis, we will be analyzing 2021 census data for the Ottawa region in order to examine the relationship between income versus education within the different wards across the city. This data was gathered by Statistics Canada and provided by the City of Ottawa.

The original dataset can be accessed through the [City of Ottawa's open data portal](open.ottawa.ca/datasets/59b3ea74ecea4a8a9d7fb797190bbdb8/explore).

The version of the dataset used for this analysis was provided by J-S. Marier and can be found [here](https://raw.githubusercontent.com/jsmarier/files-for-course-assignments/refs/heads/main/2021_Long_Form_Census_-_Ward_Data.csv).

The 2021 long form census dataset, collected by Canadians through electronic questionnaires, contains information about income, housing, language, religion, ethnicity, employment, education and more, and is incredibly important for government planning, such as creating policies. Additionally, for Ottawa specifically, the census demonstrates these different numbers across 24 different wards, for example Barrhaven West, Rideau-Rockcliffe or Kanata South. For our assignment, we will be explaining how we got the data, what the data comprises/understanding the data, and finally pitch a potential story about our findings.

## 2. Getting Data

The dataset we are working with is called “2021 Long Form Census - Ward Data”. The census data is publicly available; however, to access this specific dataset, we downloaded a CSV file using the link provided. Once the data is downloaded, we imported its contents to Google Sheets by clicking `File > Import > Upload` and selecting the downloaded CSV file.

![](import-screen-capture.png)<br>
*Figure 1: The "Import file" prompt on Google Sheets.*

![The Google Sheets created using the raw data](unclean-google-sheets.png)<br>
*Figure 2: The dataset immediately after being imported to Google Sheets.*

Our initial observations pertained to the cleanliness of the data. It was difficult to understand as the meaning of the variables (averages, counts, medians) changed without a clear indication.
These transitions were hard to distinguish from one another as the titles cut off due to their length.
There are 2603 rows, and columns from A-Z, containing the 24 wards across Ottawa. 

Column A contained the characteristics. These spanned several categories such as education, income, and languages. This data can't be quantified, therefore Statistics Canada (2021a) defines it as categorical data (para. 2).

Columns C-Z belonged to each ward (1-24), while column B refers to the whole city of Ottawa. Columns B-Z contain variables that are both discrete and continuous.

For example, the average household size is 2.5 for column B; this is a continuous value as “it can assume an infinite number of real values within a given interval”, including decimal numbers, yet within a positive range (Statistics Canada, 2021a, para. 7).

An example of a discrete variable is the number of people who spoke a particular language. There cannot be half a person, thus it will assume “a finite number of real values within a given interval” (Statistics Canada, 2021a, para. 8).

It was surprising to see the extensive list of languages. Several languages were extremely underrepresented. Where did Ottawa fall behind in diversifying the languages spoken? Is this trend reflected in other cities?

However, the data pertaining to education levels and fields per ward stood out to us more. Is there a connection between the fields commonly pursued by wards to the average income? How is the range of education levels so diverse throughout wards? What is being done to address this?

## 3. Understanding Data

### 3.1. VIMO Analysis

Before beginning our data analysis, we must assess the reliability of the data before making claims and sharing facts. A VIMO analysis checks if the data is valid, invalid, missing, or contains outliers. For the sake of our analysis, we will be focusing on column B, C, and D, which shows the data for the City of Ottawa, Ward 1 (Orléans East-Cumberland), and Ward 2 (Orléans West-Innes).

To confirm the data’s validity, we first made sure the data was formatted correctly and valid. For instance, if the data characteristic has to do with a percentage, it will be marked with (%) or a ($) when dealing with Canadian currency. Using this information, we carefully went through the data to make sure it follows the correct formats and nothing looks out of the ordinary.

For example, we made sure all income composition breakdowns represent valid percentages since all the numbers should between 0-100.

![An example of valid percentages between 0 and 100]()<br>
*Figure 3: An example of valid percentages between 0 and 100.*

Additionally, we made sure the percentages made mathematical sense and there were no random data like text in the cells. We also checked for possible data/empty boxes and outliers by making sure there was no super high, low, or unrealistic data. We found that numbers such as population counts may be off by 5-10 but that is just because the census rounds numbers to the closest 5. Therefore We would still consider this as valid data.

For example, the number of people with or without a high school diploma or equivalent always ends with either 0 or 5.

![A screenshot displaying numeric data rounded to the nearest multiple of 5.]()<br>
*Figure 4: A screenshot of our dataset illustrating how numeric data is round to the nearest multiple of 5.*

In conclusion, we found that the 2021 census dataset has no outliers, missing data or invalid data, therefore is valid and reliable enough to continue our analysis.

### 3.2. Cleaning Data

In order to clean the data, we needed to focus on just the characteristics we chose to analyze for our story. Because the original dataset had over 2600 rows, we used the find function on column A to locate any income-related characteristics by looking for dollar signs ($) and “income”, selecting all the rows that appeared in the results. This approach wasn’t perfect as some applicable rows did not contain either identifier so it required manual effort on our part to judge which rows should be included. After we selected the characteristics we wanted to focus on, we copied them to a blank sheet to make the data easier to clean.

We started by freezing column A and row 1. Row 1 needed to be frozen in order to identify the characteristics of each row when looking at data for roughly ward 5 and higher.

Then we used the find function to find any characteristic that contained “25% sample data”. When we looked at the dataset initially, we found that the characteristics created their own mini-categories, usually headed by a 25% sample data row. We added a row above each of these entries to make the difference between mini-categories clearer and bolded them the way we would a typical header.

Then we began reformatting the data in each row. Using the find function we looked for characteristics containing a dollar sign ($), selected all applicable rows minus column A and formatted them as currency. Because the data was all whole values, we removed all decimal places. We then did the same for numbers and percentages. The percentages were tricky because they were originally formatted as percentages without the percent symbol (%) so using Google Sheets’ built-in formatting resulted in skewed values due to the fact that the formatting actually acts as a mathematical conversion function. Instead, we played with the custom number format creator and found a custom number format that we used instead (see figures 5, 6, and 7).

![A screenshot of percentage values after applying Google Sheets' formatting]()<br>
*Figure 5: A screenshot of percentage values after applying Google Sheets' built-in formatting.*

![A screenshot of percentage values after applying the custom format]()<br>
*Figure 6: A screenshot of percentage values after applying a custom format.*

![A screenshot of the custom format prompt]()<br>
*Figure 7: A screenshot of the custom format prompt in Google Sheets.*

Finally, the custom format we used resulted in any 0% value to be converted to x% so we used find and replace to replace all “x%” with “0%”. We finished by trimming whitespace and using Sheets’ cleanup tool to remove extra spaces.

![A screenshot of the clean dataset]()<br>
*Figure 8: A screenshot of our dataset after cleaning.*

### 3.3. Exploratory Data Analysis (EDA)

We approached our data analysis using a question we asked after a quick glance at the data: “How does education impact the level of income throughout Ottawa?” We created a pivot table that compares the average income of wards and the highest levels of education.

We created a new sheet using only necessary rows. Following [this tutorial by Spreadsheet Point (2021)](https://www.youtube.com/watch?v=8RtwsPWuZ-4), we transposed the data using `Edit > Paste Special > Transposed`. This makes the sheet easier to analyze with a pivot table.

We wanted to focus on the number of people in Ottawa with each level of education so we used `=SUM([row]2:[row]25)` to add the counts from each of the wards.

#### Making the Pivot Table

First we set the rows of the pivot table to be our wards (yellow). Since we are comparing several levels of study to the average income, we ordered the income (purple)  before the levels of education (green), and ordered the wards from highest to lowest based on their average total income.

![A pivot table illustrating average total income and the sum of people with each level of education across the wards in Ottawa.]()<br>
*Figure 9: This pivot table shows the average total income and the number of people with each level of education for each ward in Ottawa. The last row displays the average for the whole city.*

The bottom row calculates the average total income across wards and the average recipients in each level of education.

#### Exploring the Data

![An exploratory bar chart comparing the number of people with each education level per ward with the wards organized from highest to lowest average income.]()<br>
*Figure 10: This exploratory bar chart compares the number of people with each level of education in each ward, with the wards organized from highest average income to lowest average income.*

We chose these variables because our most promising observations regarded the connection between income and education. We wanted to see if there was a significant correlation between a ward’s level of education and their average income (e.g. does a more educated ward make more money?).

In Ward 1 (Orleans East-Cumberland) — the ward with the highest average total income in 2020 — the ratio of bachelor's degree to no post-secondary education is substantial: 19,240 people to 2,550 people.

We also noticed a relation between the highest level of education received and the average income of wards. Our story would address where the educational support of wards fails and where they exceed. If the higher the income relates to the higher of education, what is put in place to provide additional support for those in pursuit of a higher level? Do the residents of these wards feel supported?

The pivot table does not include the number of recipients in each ward, which affects the results greatly. This is an element that would be beneficial  to the validity of our story as we continue to explore the data.

It would also be important for us to explore other levels of education, outside of the main 7. We cut the rest for efficiency and cleanliness of the data; however, there are large demographics removed because of this.

## 4. Potential Story

For our story, we wanted to focus on the income versus education level of the different wards across Ottawa to understand if there's a correlation between people's education level and salary and find potential patterns within the wards. In order to tell this story, we would first need the cleaned dataset to show people where our data is coming from before we begin the story. Accompanying the data, we could also include a visual element such as a scatter plot diagram, a grouped bar chart, or even create a map of Ottawa showing the education or income levels using Google My Maps. By providing readers with additional ways to understand the data can further help them understand the story. Additionally, to tell this story we would need to understand more in depth about the different wards and factors in different circumstances. This could possibly include research on housing costs, possible transportation issues, population ages, or job opportunities. By taking note of these factors, we could create a more in depth analysis. Finally, interviews from people in different areas would be very beneficial. Interviewing a resident from a lower-income ward versus someone from a higher-income ward about their education or job opportunities in the area can create a more credible story for readers. 

The following resources can help us provide more context and more information on our potential story:
* [Socio-demographic Data and Population Projections - Ottawa Public Health](https://www.ottawapublichealth.ca/en/reports-research-and-statistics/sociodemographics.aspx#Education-Employment-and-Income)
* [6 of Ottawa's worst transportation headaches, according to residents | CBC News](https://www.cbc.ca/news/canada/ottawa/6-of-ottawa-s-worst-transportation-headaches-according-to-residents-1.7309876)
* [Data on the current state of poverty in Ottawa, September 2024](https://documents.ottawa.ca/sites/default/files/povertydata2024_EN.pdf)
* [Disaggregated trends in poverty from the 2021 Census of Population](https://www12.statcan.gc.ca/census-recensement/2021/as-sa/98-200-X/2021009/98-200-x2021009-eng.cfm)

## 5. Conclusion

The most challenging part of this assignment was how overwhelming the original dataset was. It was very hard to read because there was no clear divide between the characteristic categories and the sheer volume of the data was intimidating. This made it hard for us to make initial observations. We decided to divide it up and decide what types of characteristics we wanted to look at closer and separated those data from the original dataset before deciding to move forward with analyzing the relationship between income and education.

The most rewarding aspect was getting to see the data in different ways. Separating out data, making pivot tables, and exploratory charts helped us see the data beyond the surface numbers and encouraged us to dig deeper.

We don’t think we can say we identified gaps in our knowledge since none of us really looked closely at census data in the past so this is all new knowledge to us. Because there was no knowledge in the first place, it’s all a gap. We did learn a bit about how the census works while trying to understand why some numbers weren’t adding up and researching the data collection process.

If we were to do something differently next time, we would have tried to do some initial research about the census to give us a jumping off point. We got overwhelmed by the dataset and struggled to figure out where to start exploring. Had we done some reading and looked at what others noticed about the data, we might have been able to get over the overwhelm and gain additional insight into the data.

## 6. References

City of Ottawa. (2024, September). *Data on the current state of poverty in Ottawa* [PDF]. City of Ottawa. [https://documents.ottawa.ca/sites/default/files/povertydata2024_EN.pdf.](https://documents.ottawa.ca/sites/default/files/povertydata2024_EN.pdf)

Ottawa Public Health. (n.d.). *Socio-demographic Data and Population Projections*. Ottawa Public Health. [https://www.ottawapublichealth.ca/en/reports-research-and-statistics/sociodemographics.aspx#Education-Employment-and-Income.](https://www.ottawapublichealth.ca/en/reports-research-and-statistics/sociodemographics.aspx#Education-Employment-and-Income)

Spreadsheet Point. (2021, August 1). *How to Transpose Data to Google Sheets* [Video]. Youtube. [https://www.youtube.com/watch?v=8RtwsPWuZ-4.](https://www.youtube.com/watch?v=8RtwsPWuZ-4)

Statistics Canada. (2021, September 2). *4.2 Types of Variables*. StatCan. [https://www150.statcan.gc.ca/n1/edu/power-pouvoir/ch8/5214817-eng.htm.](https://www150.statcan.gc.ca/n1/edu/power-pouvoir/ch8/5214817-eng.htm)

Statistics Canada. (2021, November 25). *Data Accuracy and Validation: Methods to ensure the quality of data* [Video]. StatCan. [https://www.statcan.gc.ca/en/wtc/data-literacy/catalogue/892000062020008.](https://www.statcan.gc.ca/en/wtc/data-literacy/catalogue/892000062020008)

Statistics Canada. (2024, December 4). *Disaggregated trends in poverty from the 2021 Census of Population*. StatCan. [https://www12.statcan.gc.ca/census-recensement/2021/as-sa/98-200-X/2021009/98-200-x2021009-eng.cfm.](https://www12.statcan.gc.ca/census-recensement/2021/as-sa/98-200-X/2021009/98-200-x2021009-eng.cfm)

White-Crummey, A. (2024, August 31). *6 of Ottawa’s worst transportation headaches, according to residents*. CBC News. [https://www.cbc.ca/news/canada/ottawa/6-of-ottawa-s-worst-transportation-headaches-according-to-residents-1.7309876.](https://www.cbc.ca/news/canada/ottawa/6-of-ottawa-s-worst-transportation-headaches-according-to-residents-1.7309876)

### AI Declaration
Grammarly was used to proofread portions of this analysis for grammar and spelling errors.