# Group3_Project1_DataAnalytics
Data Analytics Bootcamp - Project 1 - Group 3

Group Members: Jalaj Sharma, Pedro Azpurua, Richard Thornton, Shelly Wong, Shrushti Shah

# Project Title:
Exploring and identifying potential healthcare holes in Victoria

# Project Description:

This project investigates the relationship between the growing Victorian population and the various health services available to its people. Access to tertiary and primary healthcare facilities are considered and corresponding health outcomes and mortality rates are explored. 

The focus of this project is Victoria, Australia and the datasets analysed are from the years 2016 - 2022. 

Major sources of the datasets:
     - The Australian Bureau of Statistics (ABS)
     - The Australian Institute of Health and Welfare (AIHW)
     - GeoAPIfy is used for querying geo-coordinates of the various hospitals and Local Government Areas (LAGs) for the analysis.
     

# GitHub:
https://github.com/j13s3/Group3_Project1_DataAnalytics

# Research Question 1 (Shelly Wong):
Identify areas of population growth in Victoria and understand the health services available to the areas

Jupyter Notebook: Q1_Population_health.ipnyb

Data Sources:
Population growth data 2021 from ABS

References:
https://www.shanelynn.ie/pandas-drop-delete-dataframe-rows-columns/
https://www.statology.org/pandas-set-first-row-as-header/
https://www.geeksforgeeks.org/plotting-multiple-bar-charts-using-matplotlib-in-python/
https://www.statology.org/valueerror-cannot-convert-float-nan-to-integer/
https://www.geeksforgeeks.org/bar-plot-in-matplotlib/

    Step 1:

     - Process raw data, by getting rid of all unwanted information, and select population data from only 2016 to 2021.
     - Then, calculating the growth of population within these 5 years by subtracting population 2021 to 2016.
     - The data is then sorted according to the biggest growth cities (in terms of local government area (LGA)) to the lowest growth cities.
     - In our study, we will only be looking for the Top 14th most growing cities in the whole Victoria. 
     This is to ensure melbourne suburbs, metropolitan CBD, and regional areas are mostly included in the studies.

    Step 2:

     - Bar plot is then used to depict the growth of population in 2 different years (2016 and 2021) in this 14th cities.
     - Geoview map is also used to depict the location of the cities and its growth in terms of the size of the points on the map. 

    Step 3:
     - After narrowing the cities data, next is to search for nearest health facilities in the proximity.
     - Using Geoapify method to identify nearest hospitals and pharmacies in the research LGAs. 

    Step 4:
     - Obtaining the health facilities distance from JSON format file from geoapify, horizontal bar plot is then used to depict how far is the nearest hospital and pharmacy for each cities. 
     - Similarly, geoview map is also used to illustrate how far apart are the hospital and pharmacy from each given cities location to each other.

    Step 5:
     - From all these generated and tables, it is obvious that study needs to be done on 2 cities which are Baw Baw and Whittlesea that have shown no available of hospitals at nearby location. 
     - Cities such as Mitchell, Hume and Cardinia that takes longer to reach nearest hospitals would also be considered
     - Top 4 most populated cities would also be further explored to ensure they are capable to adapt to the increasing population growth.
 

# Research Question 2 (Richard Thornton):

Jupyter Notebook: Q2_GP_Analysis.ipynb

<p>Determine the available health services in Victoria - tertiary hospitals and primary healthcare services providers (general practitioners and pharmacies)</p><ul>
<li>General Practice Workforce providing Primary Care services in Australia Information, Dept of Health and Aged Care (Australian Federal Government):
https://hwd.health.gov.au/resources/data/dataset-gp-financial-years-201516-to-202122.xlsx</li>
<li>Medicare Benefits Schedule GP and specialist attendances and expenditure 2010-11 to 2016–17 Medicare Benefits Schedule (MBS) data collection, Australian Institue for Health and Welfare: https://www.aihw.gov.au/reports-data/health-welfare-overview/health-welfare-expenditure/data</li>
<li>Population grouth (Estimated Resident Population) by the ABS: https://www.abs.gov.au/statistics/people/population/national-state-and-territory-population/sep-2022</li>
<li>MyHospitals mapping details: https://www.aihw.gov.au/reports-data/myhospitals/content/data-downloads</li></ul></p>

<p>Step 1: Processing data and cleaning.<p><ul>
<li> All data provided in excel workbooks and imported into Pandas Dataframes using Jupyter Notebook. Excel formats had n/a values, mulitple sheets and empty columns and rows.</li></ul></p>

<p>Step 2: Data exploration and analysis</p><ul>
<li>The data from the Dept of Health and Aged Care was based on remote area categories using the remote Monash Model, based on the ABS remoteness classification, which divides all of Australia into a number of catagories (Metropolitan areas, Regional centres, Large rural towns, Medium Rural Towns, Remote Communities, Very remote Communities). It was envisaged that this cold form the basis of exploration on how primary health care is affected by population growth and by remoteness. The data for Victoria was mapped, to identify the remoteness zones used with geogrphical area; however, geographically the data could not be broken down into constituent parts. The data was explored and graphed, but could not be compared with the datasets being analysed by the rest of the group, and did not readily provide data that could be meaningfully tested within the hypothesis.</li>
<li>Medicare data was explored, obtained from the Australian Institute of Health and Welfare. details medicare costs claimed by GPs in relation to patient attendances. This dataset has the advantage of being published by SA3 and by LGA. It is, however, out of date, with the latest detailed data being 2016/17. Itr was concluded that the data did not provide suffieint detail to be able to produce any statistically verifiable support for the hypothesis, simply because there are too many gaps in the data.</li></p></ul>

<p>Step 3:</p><ul>
<li>Mapping hospitals and pharmacies to areas of population growth. The map and analysis ofdistance to services was undertaken by Shelly Wong and her methodology is dealt with in Setion 5.</li></ul></p>

<p>Conclusions for Question 2:</p><ul>
<li>Pharmacies proved numerous and proximate to areas of interest and were dismissed as areas of concern</li><li>GPs as the primary healthcare providers are the first point of call for most patients, but assessing whether the accessibility to GPs lags behind population growht in areas of change is highly problematic. The publically data sources availble dataets available at small geographic areas are inconsistent in terms of time series and collection.<l/i><li>Whilst there are figures showing the number of full time equivalent GPs per 100,000 population over time, the question as to whether  the increase in numbers is of a level to ensure sufficient access and care to areas with increasing populations cannot be demonstrated because the data cannot be broken down into comparable areas. </li><li>Whilst the number of visits per patient has increased, without being able to correlate this to number of GPs (full time equivalent) and to smaller geographic areas, it is has not proved possible to draw statistically relevant conclusions as to whether there are any increasing gaps in areas of population growth.</li></ul></p>

# Research Question 3 (Pedro Azpurua):

Compare patient wait times at hospitals and evaluate trends in the population growth. Furthermore, perform hypothesis testing on the datasets to support any findings

Jupyter Notebook: Q3_Wait_Time.ipnyb

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
        Reject H0 as the p-value is <= .05
        
Conclusion of section 3: Based on the three different data sets we have sighted a significant increase in median wait time across Victorian hospitals emergency departments conducted through T-Test Hypothesis testing. In order to display a link between population growth to this issue we performed a second set of tests on the population data sets where the 2002 vs 2021 analysis indicated a significant change in median. However when comparing 2016 and 2021 we failed to make the same conclusion. For this reason we ventured into a projections path to look at the estimated population figures for the LGA's where we sighted a significant increase in population between 2016 and 2036. 

# Research Question 4 (Jalaj Sharma):

Compare the mortality rate (age-standardised adult deaths per 100,000) and access to hospitals of the LGAs in Victoria

Jupyter Notebook: Q4_Adult_Deaths_Hospitals_Access.ipynb

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
Create a boxplot of the age-standardised deaths (per 100,000) across the years to compare the distributions.

    From the box plot, it can be observed that:
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

    As seen from the average correlation over the years, the negative value shows an inverse relationship. The magnitude of about 0.6 signifies a moderately strong relationship. In simple terms, higher access to hospital services results in fewer adult deaths per 100,000.

Conclusion of Research Question 4:

    With the correlations calculated/plotted for the relationship between hospitals in close proximity (<25km) to LGAs vs. age-standardised deaths (per 100,000), yearly (2016 - 2020) and the average across those years, it can be concluded with a high degree of certainty that an inverse relationship exists. In other words, as the number of hospitals in close access increases, the number of deaths in the population (per 100,000) decreases.

# Research Question 5 (Shelly Wong, Shrushti Shah):

Identify the areas where healthcare services are lacking and therefore a need for healthcare services exists.

Jupyter Notebooks:

     Q5a_aged populated.ipynb
     Q5b_Hospital beds.ipynb
     Q5c_Hospital mapping and analysis.ipynb
     Q5d_BawBaw and Whittlesea analysis.ipynb

Few considerations to made:
     - Considering 2 types of aged groups that need hospitals the most, this is the growing family population looking at the from age 0 to 4 years old, and services needed aged group above 70 years old age.
     - Considering the size of hospital if expansion is needed, by looking at their hospital beds

Source:
MyHospitals mapping details: https://www.aihw.gov.au/reports-data/myhospitals/content/data-downloads
Victoria in Future: https://discover.data.vic.gov.au/dataset/vif2019-population-5yr-ages-vifsa-lga-2036/resource/de6fc077-f0c6-46b8-a6cb-66a911eb06aa
Hospital resources 2020–21 data tables: https://www.aihw.gov.au/reports-data/myhospitals/content/data-downloads?search=%7B%22SearchTerm%22:%222020%22,%22Subtopics%22:%5B%222%22%5D,%22ShowRelatedTopics%22:false%7D

References:
https://berkeley-stat159-f17.github.io/stat159-f17/lectures/10-matplotlib_beyond_basics/image_tutorial..html

This Question is divided into 4 sections:

Question 5a: 

Identify aged group population for 0-4 years old and above 70 years old population across top 14th growing LGAs.

    Step 1: Process raw data, and only select aged group 0-4 years old, and all aged group above 70s for the respective 14th LGAs (defined in Q1)

    Step 2:Finding percentages of these population so we can compare across each LGAs which city has the most proportion of these aged groups.

    Step 3:Generate a bar graph that shows 2 series of column across 14 LGAs that has the percentage amount for children (aged group 0-4 years old) with the elderly group. 

    Step 4: From bar graph, select top cities that has the most elderly proportions which are Bass coast and Mornington Peninsula, and also city that has the most younger children which is Wyndham.

Question 5b:

Identify Hospital size by considering their hospital beds

   References for hospital size vs beds definition(city): https://www.rasmussen.edu/degrees/health-sciences/blog/types-of-hospitals/

     - Small hospitals: fewer than 100 beds
     - Medium hospitals: between 100 to 499 beds
     - Large hospitals:  500 or more beds

   References for hospital size vs beds definition(rural)
     - Hospitals size smaller, often less than 100 beds

     Step 1: Incooperate with hospital mapping data (process in Q5c), using geoview map to identify each studied LGA of their nearest and nearby hospitals.

     Step2: Select the name of the main hospital of each LGAs from geoview map, manually filter the name of the hospital into the data and create new dataframe. 
     
     Step 3: Also checking hospital local network health data to ensure these hospitals have any links to other big equipped hospitals in the municipality. 

     Step 3: In combination with the use of Google map to identify travel time needed for further analysis. 
     
     Step 4: Categorised hospitals by regional and major cities into 2 different dataframe.
     
     Step 5: Plot bar graph to visualise the number of hospital beds for each cities, and identify city concerns with hospital beds below 250. 
     
Question 5d:

Further analysis made on City of Bawbaw and Whittlesea (from Q5c step 4)

    Step 1: Both Baw Baw and Whittlesea shown no closest hospitals nearby, by observing hospital mapping data processed in Q5c, it is found out that the geocoordinates points given were located in the village and surrounding nature reserve. It does not depicts overall population of each city.
    
    Step 2:  Alternative ways need to be used to get appropriate city points coordinates.
    
    Step 3: The address of local shire council is used as the main city reference point that depicts most population located.

    Step 4: Then the geocoordinates of local shire are used to find the nearest hospitals in the municipality.

    Step 5: Geoview map is also used to identify location of population vs hospitals locations.


Question 5c: 
 
 Combine all data and make final analysis.

     Step 1: Process raw data of the hospital mapping. This data has all the public hospitals in whole Australia, only select Victoria.

     Step 2: Using the provided geocoordinates given, plot data using hvplot to identify hospitals location across victoria map. 

     Step 3: Import data from Q5a (aged group bar graph) and Q5b(hospital beds barplots), combine all these data to be used into analysis

     Step 4 :LGA studied derived from analysis in Q1 and Q5a
      - Cities with no hospital found: BawBaw and Whittlesea
      - Cities with aged groups concern: Bass Coast, Mornington, and Wyndham
      - Cities with longest hospital distance to reach: Mitchell, Hume and Cardinia 
      - Top populated cities: Casey, Melton

   Step 5: Final analysis

 City with no concern for health facilites: 

      - The analysis made in Q5d has improved our data observations made in Q1 (distance of hospitals). 
      However, a special study needs to be made for City of Baw Baw since it is a regional area which made up of different rurals town. 
      Hence, studies were made to identify if the rural town where shire council located represents most of its population. 
      It is found out that most populated town is located in Warragul and Traralgon where the latter has biggest hospital in baw baw region is located. It has capacity of medium sized to 253 beds which combined with other hospitals, it is well-equiped and adequate for its own population.
    
    - Same for Whittlesea, most of its population located in the south. This is also where main hospital is located with 461 beds (medium to large sized) and is adequate for its own population. 

       - Both Bass Coast and Mornington have good number of hospitals around, well equipped large hospital also located at its main populated area. Hence, these LGAs have no major issues to handle elderly population. 

City with growing concerns for health facilities: 

       - Wyndham is a growing family oriented city, but it has only 1 medium sized hospital in the municipality. This is a huge concern for growing population. 

       - Similar for Casey and Cardinia, being top growing cities, they are both sharing same hospital, at only 233 beds capacity. 

       - Same for Hume and Melton, being top growing cities, they do not have nearby hospitals that could treat major treatments. Both have to travel around 25mins to access bigger hospital at capacity of 575 beds and has to share facility within Western Health regions. 

       - As for Mitchell, even though is a small population compared to other LGAs, it does not have a small sized hospital within region, and even have to travel 20mins to access for a basic treatment. 

Therefore, it in concluded if any considerations to invest hospital facilities, top major growing cities such as Wydnham, Casey, Hume and  Melton should be the most priority, and next comes to Cardiania and Mitchell. 

# Conclusion and Recommendations (Shrushti Shah):

Based on the data sets analysed, we have the following conclusions:

        There is an increase in population in Victoria.

        There is evidence to show as the population increases there are longer hospital wait times, and an increase in GP health services required. 

        The greatest growth in Victoria is located in the outer ring suburbs of Melbourne.

        There is evidence that the mortality rate has a negative correlation to access to a hospital. 

        Evidence that four of the top growth LGAs require resources as seen in the number of hospital beds available in these areas. 
