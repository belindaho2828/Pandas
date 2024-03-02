# Summary #
PyCitySchools Analysis parses data from two csv files containing information about schools in the district and student performances throughout those schools respectively. 

The analysis uses Pandas functions to read the csvs files, merge the two datasets together, provide a district summary, a school summary, and different slices of the data to determine relationships between specific variables. 

## District Summary ##
The district summary uses DataFrame functions df.unique (where df is alias for dataframe), len(df), df.mean(), and df.sum() to get the total number of unique schools represented in the district, the total number of students represented, total budget across all schools, and average math & reading scores for the district. Additionally, .loc is used to filter reading scores to calculate % overall passing and for each subject across all schools. A new dataframe is then created to display the summary.

## School Summary ##
The school summary uses DataFrame functions set_index to get the school type, total students, and total school budget from the "school data" dataframe since it was already listed by school (i.e., no calculation or aggregation needed). Budget per student is then calculated by dividing each school's budget by student population. Groupby (and aggregations) are used to calculate the average math and reading scores by school and .loc (+groupby) is used to filter, calculate, and group by school the % passing rates for math, reading, and overall. A new dataframe is then created to display the summary data for each of the 15 schools across the district.

## Slicing Data ##
For further analysis, the following was performed:
### sorting ###
Sorting was performed to identify the highest and lowest performing schools by overall % pass rate.
###groupby###
Groupby grade on average math and reading scores separately per school to identify any trends by grade or by school.
###binning###
Binning by budget per student and school size to identify any relationship between test scores and budget or school size. 

#C onclusions #
## Conclusion 1 - Scores by School Type ##
Based on the "Scores by School" summary, there seems to be a relationship between test scores/passing rates and the type of school. Charter schools tend to have higher average math and reading scores and much higher % passing rates in math, reading, and overall when compared to district schools. The district should take care in researching the differences between resources being offered at charter schools vs. district schools and use that to emulate charter school restuls in district schools, whether that's providign more funding or changing structures in place.

## Conclusion 2 - Scores by chool Size ##
Based on the "Scores by School Size" summary, there appears to be a negative correlation between the per student budget and average test scores/passing rates. This means the higher the budget per student, the lower the the scores/passing rates and vice versa (the lower the bduget per student, the higher the scores/passing rates). That is, the highest average scores and passing rates across subjects and overall seem to be schools that have less than $585/student budget while the lowest average scores and passing rates across the board are from schools that have $645-$680/student budget (the upper bound of the per student budget). This is surprising since I expected that more resources spent per student would lead to higher performance. Although this looks to be a negative relationship, correlation does not mean causation. The district will need to conduct further research as to why this might be the case. For example, this could be due to the type of school (see school type conclusion above), behaviors outside of budget alone, or schools are using the resources they have efficiently vs. frivolously spending. The budget per student also does not necessarily mean that amount is actually spent per student. This could be spent on overhead expenses, which may or may not impact students directly. A deeper look at budget spending is needed to draw that conclusion.
