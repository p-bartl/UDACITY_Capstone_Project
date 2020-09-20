# UDACITY Nano Degree - Become a Data Scientist Term 2

## Project #7 - Capstone Project: What types of financial aid are most effective in maximizing degree completion rates?
An end-to-end Data Science project.
Data provided by the Integrated Postsecondary Education Data System (IPEDS)

### Content
1. Python Libraries
2. Overview
3. Files
4. Summary of the results of the analysis
9. Licensing, Authors, and Acknowledgements

### 1. Python Libraries
Mainly the Libraries were used which are included in a Standard Anaconda Installation.

- Python 3
- numpy 1.18.4
- pandas 1.0.4
- matplotlib 3.2.1
- Seaborn 0.10.1
- statsmodels 0.12.0
- patsy 0.5.1

### 2. Overview

The Integrated Postsecondary Education Data System (IPEDS) provides the "Delta Cost Project Database" where they collect IPEDS finance, enrollment, staffing, completions and student aid data for for the 2000–2012 academic years. I wanted to focus my analysis on the most recent years and limit the file size I have to work with as well. I therefore have chosen to analyze explicitly the 2000–2012 academic years.<br>
<br>
By collecting the data stated above they allow us to perform, among other things, longitudinal analyses of trends in postsecondary education with a focus on revenues (such as financial aid) and expenditures. A University is an example for such a postsecondary education institution.<br>
The database was originally created by the Delta Cost Project (an independent, nonprofit organization) in 2007. The maintenance and hosting of the Delta Cost Project Database was taken over by the National Center for Education Statistics (NCES) in 2012.<br>
<br>
The NCES is the primary federal entity for collecting, analyzing, and reporting data related to education in the United States and other nations. It fulfills a congressional mandate to collect, collate, analyze, and report full and complete statistics on the condition of education in the United States; conduct and publish reports and specialized analyses of the meaning and significance of such statistics; assist state and local education agencies in improving their statistical systems; and review and report on education activities in foreign countries.<br>
<br>
Specifically, there are 974 variables derived from the institutional characteristics, finance, enrollment, completions, graduation rates, student financial aid, and human resources IPEDS survey components and a limited number of outside sources. The database contains one observation per institution for each year of data that is available; it includes all institutions that reported institutional characteristic data to IPEDS in the fall of each academic year. Some of the data have been adjusted to harmonize changes in financial reporting standards that occurred over time, by employing industry-accepted manipulations of the data. When possible, missing data were replaced via imputation.<br>
IPEDS provides the data in various different form (e.g. CSV-file) as well as a MS Excel-based data dictionary.<br>
<br>
<br>
Specifically, I will focus on the Relation between different grant types (e.g. state grants) and the degree completion rates (all degrees combined). There is also data available on award and certificate completion rates, but in my opinion the degree completion rate are the most important measure because, in general, the students who strive to complete a degree form the majority of all students and are of highest interest for postsecondary education institutions.<br>
<br>
I will perform descriptive statistic analysis and visualize the results.<br>
<br>
To finally answer the question: "What types of financial aid are most effective in maximizing degree completion rates?" the degree completion rates [%] will become our dependent variable and the ratios between each different grant-type and the sum of all grants [%] will become our independent variables. I will then use Machine Learning techniques. Specifically, I will perform a multiple linear regression and compute the Variance Inflation Factor (VIF) for each  feature in order to check for multicollinearity.<br>
<br>
I expect that I will gain most insight by using machine learning techniques. At first the descriptive statistic analysis and creating visualizations will be a necessary step to explore the data and to get an understanding of how the data is structured.<br>
<br>
<br>
I will measure the performance of the overall multiple linear regression model by computing the R-Squared. This informs us about the proportion of variance in the dependent variable that is predictable from the independent variable.<br>
<br>
Moreover, I will compute the P-Value for each feature to check if I can reject the null-hypothesis stating that the value of this specific feature is zero. In other words I check for the significance of this feature. Furthermore, I will compute the Variance Inflation Factor (VIF) for each feature in order to check for multicollinearity. If multicollinearity seems to be present I will remove certain features from the model.<br>
<br>

### 3. Files

- README.MD: Provides a Project Overview
- ANALYSIS.IPYND: Share my code and data wrangling/modeling techniques
- The Data set and the Data dictionary can be downloaded from the IPEDS Website. Specifically there is a "delta_public_00_12.csv"-File which has been used in my case. The Data is provied by IPEDS: https://nces.ed.gov/ipeds/deltacostproject/<br>


### 4. Summary of the results of the analysis

For in-depth-analysis please refer to my MEDIUM Blog Post: https://medium.com/@p.bartl/the-pisa-assessment-its-way-more-than-just-a-conventional-school-test-7b6c884d7f2a

By analyzing the Delta Cost Project Data I came up with some findings regarding the degree completion rates as well as different grant-types and their ratios. The exploratory analysis showed that over time the pell-grant-ratio decreases while the other grant-type-ratios as well as the overall degree completion rate increases. On a lower level of data analysis we could observe that there is a variance regarding the distribution of the pell-grant-ratios. On the other hand all other grant-type-ratio had a much lower variance.<br>
<br>
When it comes to performing machine learning techniques it's all about preventing multicollinearity. I therefore computed the VIFs and improved the model by removing the unfunded-institutional-grant-ratio variable. After doing so the R-squared did not decline, but at the same time the measure for multicollinearity improved drastically. Only one of the remaining features proofed not to be statistically significant. The state-grant-ratio seems to have a positive effect on the degree completion rate. However this effect is rather weak. The local- as well as the pell-grant-ratio has a much stronger effect, but in these cases in negative direction.<br>
<br>
One could change this model by adding more relevant features to further improve the explanatory power. At the same time this could cause multicollinearity issues again because one added a variable that is (highly) related to another one. When you consider changing or adding variables you should always checking the VIFs again as well. By doing so there are no limits for your creativity.<br>
<br>


### 9. Licensing, Authors, and Acknowledgements

There are no references to other websites, books, and other resources. I did enjoy working on this project. Thanks UDACITY!
