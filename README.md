


# Mobile Data Analytics - Assignment 1
Github link: https://github.com/JamiuDahunsi/Homework-1
# Overview

This assignment analyzes mobile communication data from Milan, Italy, focusing on three specific days in November 2013 (November 2nd, 4th, and 6th). The dataset includes SMS, call, and internet usage records across 10,000 grid cells covering the city.

The main objectives were to:
1. Identify peak usage hours and activity patterns
2. Compare daytime versus nighttime activity levels
3. Analyze differences between domestic and international communications
4. Explore relationships between different types of mobile activity

# Methodology

# Data Processing

The analysis began by loading and merging three CSV files containing the mobile activity data. After combining the datasets, I performed basic data cleaning and preparation:

1. **Data Integration**: Concatenated the three daily datasets into a single dataframe
2. **Missing Value Treatment**: Filled missing values with column means to preserve data distribution
3. **Feature Creation**: Generated aggregate metrics (total SMS, total calls) and extracted temporal features (hour of day)
4. **Data Validation**: Verified data types and checked for any anomalies

# Analytical Approach

**Missing Data Handling**

The dataset contained substantial missing values, especially in the smsout column (approximately 5.9 million missing entries). Rather than removing these records, I filled missing values with their respective column means. This approach was chosen because:
1. Removing rows with any missing values would eliminate roughly 90% of the dataset
2. Mean imputation maintains the overall statistical properties of the data
3. It ensures complete spatial coverage across all grid cells

**Time Period Definitions**

For the temporal analysis, I defined:
1. Daytime: 6:00 AM to 8:00 PM
2. Nighttime: 8:00 PM to 6:00 AM
3. Domestic calls: Country code 39 (Italy)
4. International calls: All other country codes

These definitions were selected based on standard working hours and Italy's international dialing code.

# Results

## Dataset Characteristics

1. Total records analyzed: 6,564,031
2. Spatial coverage: 10,000 unique grid cells
3. International reach: 302 different country codes represented

# Activity Patterns

**Peak Usage Times**

The analysis revealed that mobile activity peaks at 5:00 PM (hour 17), with the lowest activity occurring at 3:00 AM (hour 3).

**Daytime vs. Nighttime Distribution**

Approximately 73.55% of all mobile activity occurs during daytime hours (6 AM - 8 PM), while 26.45% happens during nighttime hours (8 PM - 6 AM).

**Call Volume Statistics**

Hourly call volumes showed the following characteristics:
1. Mean: 3.67 million calls per hour
2. Median: 4.15 million calls per hour  
3. Standard deviation: 1.88 million
4. Range: 0.97 million to 5.80 million calls per hour

# Geographic Patterns

**Domestic vs. International Activity**

The data shows interesting patterns in international versus domestic communications:
1. Approximately 67% of calls are international, with 33% being domestic
2. SMS activity follows a similar distribution
3. International calls show a 1.67:1 ratio of incoming to outgoing calls, which means Milan receives more international calls than it initiates


# Activity Type Correlations

There is a strong positive correlation (r = 0.99) between SMS volume and call volume at the grid level. This indicates that areas with high call activity also tend to have high SMS activity.

When comparing hourly patterns, both domestic and international calls follow similar daily trends, with peaks during business hours. However, international calls show slightly different timing patterns, possibly due to time zone differences with other countries.

# Discussion

The analysis demonstrates that mobile communication activity in Milan follows predictable patterns that correspond to daily human routines. The evening peak at 5 PM likely represents the end of the workday when people are most actively communicating. The minimal activity during early morning hours (3 AM) is expected given typical sleep schedules.

The dominance of international communications is noteworthy and distinguishes Milan from cities with less international connectivity. This pattern reinforces Milan's role as a global business hub with extensive international connections.

The strong correlation between SMS and call volumes suggests that mobile users who are active in one form of communication tend to be active in others as well. This could indicate that certain areas or times have generally higher mobile engagement across all communication types.

# Limitations

Several limitations should be noted:
- The analysis covers only three days, which may not capture weekly or seasonal variations
- Mean imputation for missing values assumes data is missing at random, which may not be accurate
- The grid-based aggregation doesn't account for population density variations across cells
- No demographic or contextual data is available to explain observed patterns

# Conclusion

This analysis identified key patterns in Milan's mobile communication data, including peak usage times, the distribution of daytime versus nighttime activity, and the prevalence of international communications. The findings provide insights into how mobile networks are utilized in a major metropolitan area and could inform network planning and resource allocation decisions.

Future work could extend this analysis to include more days of data, investigate seasonal patterns, or incorporate additional contextual information about the grid cells (such as whether they cover residential, commercial, or mixed-use areas).

