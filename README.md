# Pest Data Project Analysis Summary

# Introduction:
This report examines a pest population dataset collected across various locations in India (1959-2011). It investigates potential relationships between weather conditions and pest activity for ten pest species:

|  **Pestcides**       |
|:---------------------|
|Gall Midge            |
|Brownplanthopper|
|Greenleafhopper|
|LeafFolder|
|Yellowstemborer|
|Caseworm|
|Mirid Bug|
|ZigZagleafhopper|
|LeafBlast|
|NeckBlast|


# Objective:
The primary objective is to gain insights that can inform pest management strategies across Indian regions.



# Data Analysis:

Data Import: Data imported into a relational database (RDBMS) and stored in the "PESTDATA" table.


# Table Schema:

|**Column Name**               |  **Data Type**       | **Key**|                    **Description**                   |
| :----------------------------| :------------------- | :------|:-----------------------------------------------------|
|       OBSERVATIONYEAR        |   int                |YES     | Year of observation                                  |
| STANDARDWEEK                 | int                  | NO     | Standard week within the year (e.g., week 1, week 2) | 
| PESTVALUE                    | int                  | NO     | Number of pests found per unit (e.g., per hill)      |
| COLLECTIONTYPE               | varchar(20)          | NO     | Type of collection method used                       | 
| MAXT                         | decimal(5,2)         | NO     | Maximum Temperature in degrees Celsius               | 
| MINT                         | decimal(5,2)         | NO     | Minimum Temperature in degrees Celsius               | 
| RH1                          | decimal(5,2)         | NO     | Relative Humidity 1 as a percentage                  | 
| RH2                          | decimal(5,2)         | NO     | Relative Humidity 2 as a percentage                  |
| RF                           | decimal(5,2)         | NO     | Rainfall in millimeters                              |  
| WS                           | decimal(5,2)         | NO     | Wind Speed in kilometers per hour                    | 
| SSH                          | decimal(5,2)         | NO     | Sunshine Hours                                       |
| EVP                          | decimal(5,2)         | NO     | Evaporation in millimeters                           | 
| PESTNAME                     | varchar(20)          | NO     | Name of the pest species (e.g., Brownplanthopper)    |
| LOCATION                     | varchar(20)          | NO     | State name corresponding to the observation location |
| ID                           | int                  | PRI    | Unique identifier for each record                    | 
| STATE                        | varchar(20)          | NO  | Standardized state name based on location (e.g., ODISHA for Cuttack) | 
| SEASON                       | varchar(20)          | NO  | Season (Summer, Monsoon, Post-Monsoon, Winter) based on standard week | 
| TEMP_PEST_INTERACTION        | float                | NO  | Interaction term (MAXT * PESTVALUE)                 | 
| RAINFALL_PEST_INTERACTION    | float                | NO  | Interaction term (RF * PESTVALUE)                 |
| HUMIDITY_AVG                 | float                | NO  | Average relative humidity ((RH1 + RH2)/2)            | 
| TEMPERATURE_DIFFERENCE       | float                | NO  | Difference between maximum and minimum temperature (MAXT - MINT) |


# Data Cleaning After Transformation:
No null values were found in any column after data transformation.


# About the Data:
This report explores a dataset on pest populations collected across various locations in India from
1959 to 2011


# Data Exploration:
1. Total Observations: 17636 
>. (using SELECT COUNT(*) FROM PESTDATA;)
2. Observation Years: 48 
>. (using SELECT COUNT(DISTINCT(OBSERVATIONYEAR)) FROM PESTDATA;)
3. Distinct Pest Names: Identified using 
>. SELECT DISTINCT(PESTNAME) FROM PESTDATA;
4. Pest Species per Location: Determined using 
>. SELECT LOCATION, COUNT(PESTNAME) FROM PESTDATA GROUP BY LOCATION;


# Basic Descriptive Statistics:
1. Locations/States: ANDHRA PRADESH, CHHATTISGARH, Himachal Pradesh, MANIPUR, ODISHA, PUNJAB
2. Observation Years: 48
3. Seasons: MONSOON, WINTER, SUMMER, POST-MONSOON

# Questions for Further Analysis:
Pest Value Variation Across Locations: How does average pest value vary across locations?
Maximum Temperature vs. Average Pest Value
Seasonal Pest Value Variation: How does average pest value vary across seasons for each year?
Rainfall Impact on Summer Pest Value: Does rainfall affect average pest value during summer?
Weather Variables and Pest Value Over Time: How do weather variables and average pest value change across standard weeks?
Average Relative Humidity for High Pest Values: What is the average relative humidity for observations with pest values above the average?
Weather Variables and Pest Value Throughout the Year: How do weather variables and average pest value change across standard weeks?
Season with Highest Average Pest Value: Which season has the highest average pest value?
Weather Variable Variation Across Locations: How do average weather variables vary across different locations?
Pest Species with Highest Maximum Pest Value: Which species has the highest maximum pest value across all states?
Location-Specific Questions: Analyze pest value distribution and relationships with weather variables for each location (Cuttack, Maruteru, etc.).
Sunshine Hours and Pest Value: Is there a relationship between sunshine hours and average pest value?
Highest Total Pest Value by Year: Which five years have the highest total pest value?
Highest Total Pest Value by Location: Which five locations have the highest total pest value summed across all observation years?



# Future Considerations:
The data we have is a good starting point, but it's not enough to say for sure how weather affects pests. By looking at all the data instead of just a small piece, and using tools like pie charts and graphs, we can get a clearer picture of how weather affects pests.


THANK YOU

