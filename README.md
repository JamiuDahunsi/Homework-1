# Assignment 1: Mobile Data Analytics
## Github Link: https://github.com/JamiuDahunsi/Homework-1
## Overview of Approach

This project analyzes mobile phone activity data from Milan, Italy across three days in November 2013 (the 2nd, 4th, and 6th). The goal was to understand communication patterns by examining SMS, call, and internet usage across different times of day and comparing domestic versus international activity.

The analysis follows a straightforward workflow:
1. **Data Loading**: Combined three separate CSV files into one dataset
2. **Data Cleaning**: Handled missing values by filling them with column means
3. **Feature Engineering**: Created aggregate columns and extracted time features
4. **Analysis**: Answered specific questions about activity patterns using pandas and numpy

## Key Decisions

### Handling Missing Values
The dataset had significant missing values, particularly in the `smsout` column (over 5 million missing entries). I chose to fill missing values with the **mean of each column** rather than dropping rows. This decision was made because:
- Dropping rows would have removed nearly 90% of the data
- Using the mean preserves the overall distribution of the data
- It allows us to work with the full spatial coverage (all 10,000 grid squares)

### Time Definitions
- **Daytime**: 6am to 8pm (06:00 - 20:00)
- **Nighttime**: 8pm to 6am (20:00 - 06:00)
- **Domestic**: Country code 39 (Italy)
- **International**: All other country codes

These definitions align with typical working hours and Italy's country code system.

### Activity Metrics
For peak hour analysis, I focused on **total call volume** as the primary metric since calls are a clear indicator of active communication. The analysis groups data by hour across all grid squares to identify city-wide patterns.

## Summary of Key Findings

### Dataset Size
- **Total records**: 6,564,031 across three days
- **Grid coverage**: 10,000 unique cells covering Milan
- **Geographic reach**: 302 different country codes

### Missing Data Impact
- Most missing values were in the `smsout` column
- 5,880,441 rows (about 90%) had at least one missing value
- All missing values were successfully filled with column means

### Temporal Patterns
- **Peak hour**: 5 PM (hour 17)
- **Lowest activity**: 3 AM (hour 3)
- **Daytime dominance**: 73.55% of all activity happens during daytime hours

### Call Volume Statistics (by hour)
- Average: 3.67 million calls per hour
- Median: 4.15 million calls per hour
- Standard deviation: 1.88 million
- Range: 0.97M to 5.80M calls per hour

### International vs Domestic Activity
- **Calls**: 67% international, 33% domestic
- **SMS**: Similar pattern to calls
- **Direction**: International calls are 1.67x more incoming than outgoing, suggesting Milan receives more international calls than it makes

### Correlation Between Activity Types
### SMS and Call Correlation
There is a **strong positive correlation** (around 0.99) between SMS volume and call volume at the grid level.
### Hourly Pattern Comparison
When comparing domestic and international call patterns throughout the day, both follow similar trends with peaks during business hours. However, international calls show slightly different timing, which could be related to time zone differences with other countries.

## Conclusion

The analysis reveals that mobile activity in Milan follows predictable patterns tied to daily routines, with clear peaks during evening hours and minimal activity at night. The high proportion of international activity reflects Milan's role as an international business hub. The strong correlation between different types of communication (SMS and calls) suggests that mobile usage patterns are consistent across communication methods.

