# Group3_Project1_DataAnalytics
Data Analytics Bootcamp - Project 1 - Group 3
Group Members: Jalaj Sharma, Pedro Azpurua, Richard Thornton, Shelly Wong, Shrushti Shah

# Project Title:
Exploring and identifying potential healthcare holes in Victoria

# Project Description:
This project investigates the relationship between the growing Victorian population and the various health services available to its people. Access to tertiary and primary healthcare facilities are considered and corresponding health outcomes and mortality rates are explored. 
The focus of this project is Victoria, Australia and the datasets analysed are from the years 2016 - 2022. Major sources of the datasets are the Australian Bureau of Statistics (ABS) and the Australian Institute of Health and Welfare (AIHW). Additionally, GeoAPIfy is used for querying geo-coordinates of the various hospitals and Local Government Areas (LAGs) for the analysis.

# GitHub:
https://github.com/j13s3/Group3_Project1_DataAnalytics

# Research Question 1 (Shelly Wong):
Identify areas of population growth in Victoria and understand the health services available to the areas

Please add your data analysis here which contains "ample and complete" information. This is a requirement of GitHub.

# Research Question 2 (Richard Thornton):
Determine the available health services in Victoria - tertiary hospitals and primary healthcare services providers (general practitioners and pharmacies)

Please add your data analysis here which contains "ample and complete" information. This is a requirement of GitHub.

# Research Question 3 (Pedro Azpurua):
Compare patient wait times at hospitals and evaluate trends in the population growth. Furthermore, perform hypothesis testing on the datasets to support any findings
Data Sources: 
Time Spent in emergency rooms by hospital: https://www.aihw.gov.au/reports-data/myhospitals/sectors/emergency-department-care
Population grouth by the ABS: https://www.abs.gov.au/statistics/people/population/national-state-and-territory-population/sep-2022
Victoria Population Forecast from DEWLP: https://www.planning.vic.gov.au/land-use-and-population-research/victoria-in-future#:~:text=Victoria%20in%20Future%202019&text=VIF2019%20shows%20Victoria%20remains%20the,reach%2011.2%20million%20by%202056.

Step 1: Using the data from the Department of Health, we have cleaned and analysed the figures into a presentable format displaying the average time spent by patients across Victorian hospitals between 2011 and 2021 in the emergency departments.  
This data was plotted and used as the foundation for the hypothesis testing where by analysing the average growth of wait time across years, we have noted a significant increase based on t-statistics. 
    Results for Hypothesis test 1: Comparing average wait time at Victorian hospitals between 2016 and 2021. 
        H0: No significant Increase Between Median Weight Times
        H1: Significant Increase between Median Weight Times
        t-statistic: -4.93344
        p-value: 4.829e-06 
    The results above display a significant increase in median weight times across the hospitals in Victoria between 2016 and 2021 thus allowing for the rejection of the Null Hypothesis (H0) as the p-value <= .05
    This results are also backed by a series of Data visualisations including:
        - a trend line for the average wait time across the Victorian hospitals. 
        - a range of box plots showcasing an increase in median weight times 
        - a trend line for the yearly average time spent in hospitals cross hospitals. 
Step 2: Using the ABS Data we began to test for trends in population growth between the analysed years of 2016 and 2021. 
This analysis indicated that there was NOT a significant increase in population between the sample years as the p value far exceeds 0.05. We continued to run this test from the start of the data set in 2001 and we noted a significant increase in population from the year 2002 and 2021 with a p-value of .045. This results in conjunction with recent macro condition in Australia due to Covid, made the team focus into a projected forecast approach searching for insights into future population growth. 
    Results for Hypothesis test 2 part 1: Comparing population growth between 2016 and 2021 in Victorian LGA's
        H0: No significant Increase in Population growth
        H1: Significant Increase in Population growth
        t-statistic: -0.3896897
        p-value: 0.6972907
        Failed to reject H0 as the p-value is >= .05
    
    Results for Hypothesis test 2 part 2: Comparing population growth between 2002 and 2021 in Victorian LGA's
        H0: No significant Increase in Population growth
        H1: Significant Increase in Population growth
        t-statistic: -2.01660
        p-value: 0.045431
        Failed reject H0 as the p-value is <= .05
Step 3: Using the DELWP Data we began to test for trends in population growth based on population forecasts between 2016 and 2036. 
After cleaning the data from the department into a  more manageable data set, we found a significant expected growth in Victorian LGA's based om the  2016 figures and the projected dataset. 
    Results for Hypothesis test 3 part: Comparing population projected growth between 2016 and 2036 in Victorian LGA's
        H0: No significant Increase in forecasted Population growth
        H1: Significant Increase in forecasted Population growth
        t-statistic: -2.096759
        p-value: 0.0376077
        Failed reject H0 as the p-value is <= .05
Conclusion of section 3: Based on the three different data sets we have sighted a significant increase in median wait time across Victorian hospitals emergency departments conducted through T-Test Hypothesis testing. In order to display a link between population growth to this issue we performed a second set of tests on the population data sets where the 2002 vs 2021 analysis indicated a significant change in median. However when comparing 2016 and 2021 we failed to make the same conclusion. For this reason we ventured into a projections path to look at the estimated population figures for the LGA's where we sighted a significant increase in population between 2016 and 2036. 

# Research Question 4 (Jalaj Sharma):
Compare the mortality rate (age-standardised adult deaths per 100,000) and access to hospitals of the LGAs in Victoria

Data Sources:
Mortality Rates by LGAs: https://www.aihw.gov.au/reports/life-expectancy-death/mort-books/contents/mort-books
Specialised Services: https://www.aihw.gov.au/reports-data/myhospitals/content/data-downloads?search=%7B%22SearchTerm%22:%22Hospital%20services%20data%20extract%22,%22ShowRelatedTopics%22:false%7D

Online References:
https://stackoverflow.com/questions/13411544/delete-a-column-from-a-pandas-dataframe
https://www.freecodecamp.org/news/how-to-substring-a-string-in-python/
<https://www.who.int/data/gho/indicator-metadata-registry/imr-details/78>

Step 1:
Read the mortality rates data from the excel file. The mortality rates excel file holds data on the various parameters to evaluate the mortality in Victoria from the years 2016 to 2020. The metrics are categorised into Local Government Areas (LGAs).
The metric of interest for the analysis is the age-standardised deaths (per 100,000) from 2016 to 2020.
The data is cleaned and the metric of interest is isolated into a data frame.

Side note: What is age standardised data?
The numbers of deaths per 100 000 population are influenced by the age distribution of the population. Two populations with the same age-specific mortality rates for a particular cause of death will have different overall death rates if the age distributions of their populations are different. Age-standardized mortality rates adjust for differences in the age distribution of the population by applying the observed age-specific mortality rates for each population to a standard population.
The age-standardized mortality rate is a weighted average of the age-specific mortality rates per 100 000 persons, where the weights are the proportions of persons in the corresponding age groups of the WHO standard population.

Step 2:
Read the specialised hospital services data from the excel file. The hospital services excel file holds data on the reporting units active in Victoria from the years 2017 to 2020.
The metric of interest is the number of active reporting units in Victoria from 2017 to 2020. This will allow for seeing whether the number of active hospitals has changed over the years of interest.
The data is cleaned and the metric of interest is isolated into a data frame.
PLEASE NOTE: 2020 is the year of the Covid-19 pandemic and various stringent safety protocols were in place in Victoria. This will affect the data as atypical factors are in effect.

Step 3:
Plot a bar graph to visually show the number of active reporting units (hospitals) in Victoria from 2017 to 2020. This will illustrate whether the number of reporting units have changed drastically or not. If there has not been a significant change, we can make a crude assumption that the overall proximity of hospitals to the LGAs is the same over the years.
The plot titled "Number of Reporting Units from 2017 to 2020 in Victoria" shows that, as the number of active reporting units has not changed drastically over the years, a crude assumption can be made that the overall proximity of hospitals to the LGAs is the same over the years of interest for the sake of data analysis. This allows for the GeoAPIfy data, although queried in this year, to be applied to all years.
PLEASE NOTE: 2020 is the year of the Covid-19 pandemic and various stringent safety protocols were in place in Victoria. This will affect the data as atypical factors are in effect.
The Covid-19 pandemic would explain why there are lesser reporting units active in 2020.

Step 4:
Find the latitude and longitude data (geo-coordinates) for the LGAs of interest for the mortality rates analysis.
GeoAPIfy is used to query JSON messages and the geo-data is updated into the data frame.
Furthermore, with the assumption that the number of hospital services is the same over the years of interest, use GeoAPIfy again to determine the number of hospitals active within 25km of the LGAs and their council areas. This data (hospitals in close proximity (<25km) to Victorian LGAs) then can be applied to all the years of interest for determining the relationship between age-standardised deaths (per 100,000) and access to hospitals.

Step 5:
Create a boxplot of the age-standardised deaths (per 100,000) across the years to compare the distributions. From the box plot, it can be observed that:
    1. All box plots are within the 450-650 adult deaths (per 100,000) range suggesting some consistency in the data, especially the medians being within 500-600.
    2. There are outliers and the box spread is differently across the years meaning the data is not exactly the same, although there are similarities. This is expected because factors change with time.
    3. There isn't any high degree of skewness in the data
    4. As the box plot are not vastly different, the data is comparable with one another.

Step 6:
With all the data collected and prepared, we can now do some analysis with the adults’ deaths per 100,000 and access to hospitals.
For the year 2016, we can calculate the correlation between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000). This quantifies the relationship.
Furthermore, a scatter plot can be created to qualitatively assess the relationship between the two variables of interest.
It can be seen from the correlation value for 2016, that there is an inverse relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), as denoted by the negative value. The value of about -0.61 shows that the inverse relationship is prevalent.
Similarly, looking at the scatter plot labelled "2016 Adult Deaths vs. Hospitals in Close Proximity (<25km)", the age-standardised deaths (per 100,000) is typically 500 or more. But as the number of hospitals within 25km increases to beyond 90, there is a shift in the deaths (per 100,000) to less than 500.
The results for 2017 are similar to 2016.
It can be seen from the correlation value for 2017, that there is an inverse relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), as denoted by the negative value. The value of about -0.55 shows that the inverse relationship is prevalent.
Similarly, looking at the scatter plot labelled "2017 Adult Deaths vs. Hospitals in Close Proximity (<25km)", the age-standardised deaths (per 100,000) is typically 500 or more. But as the number of hospitals within 25km increases to beyond 90, there is a shift in the deaths (per 100,000) to less than 500.
The results for 2018 are similar to 2016 and 2017.
It can be seen from the correlation value for 2018, that there is an inverse relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), as denoted by the negative value. The value of about -0.67 shows that the inverse relationship is prevalent.
Similarly, looking at the scatter plot labelled "2018 Adult Deaths vs. Hospitals in Close Proximity (<25km)", the age-standardised deaths (per 100,000) is typically 450 or more. But as the number of hospitals within 25km increases to beyond 100, there is a shift in the deaths (per 100,000) to less than 450.
The results for 2019 are similar to 2016, 2017, and 2018.
It can be seen from the correlation value for 2019, that there is an inverse relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), as denoted by the negative value. The value of about -0.61 shows that the inverse relationship is prevalent.
Similarly, looking at the scatter plot labelled "2019 Adult Deaths vs. Hospitals in Close Proximity (<25km)", the age-standardised deaths (per 100,000) is typically 450 or more. But as the number of hospitals within 25km increases to beyond 100, there is a shift in the deaths (per 100,000) to less than 450.
The results for 2020 are similar to 2016, 2017, 2018, and 2019.
It can be seen from the correlation value for 2020, that there is an inverse relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), as denoted by the negative value. The value of about -0.62 shows that the inverse relationship is prevalent.
Similarly, looking at the scatter plot labelled "2020 Adult Deaths vs. Hospitals in Close Proximity (<25km)", the age-standardised deaths (per 100,000) is typically 430 or more. But as the number of hospitals within 25km increases to beyond 100, there is a shift in the deaths (per 100,000) to less than 430.

Step 7:
Plot a bar graph to visually show the correlation between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000) for the years of interest. This will illustrate the relationship between the variables being investigated over the years. Finally, an average correlation can be computed to conclude the relationship based on the data over the years.

Conclusion of Research Question 4:
With the correlations calculated/plotted for the relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), yearly (2016 - 2020) and the average across those years, it can be concluded with a high degree of certainty that an inverse relationship exists. In other words, as the number of hospitals in close access increases, the number of deaths in the population (per 100,000) decreases.

# Research Question 5 (Shelly Wong, Shrushti Shah):
Identify the areas where healthcare services are lacking and therefore a need for healthcare services exists, especially for population dense Victorians in the >70 years old age bracket

Please add your data analysis here which contains "ample and complete" information. This is a requirement of GitHub.

# Conclusion and Recommendations (Shrushti Shah):

Please add the overall conclusion and future recommendations here.