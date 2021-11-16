# School_District_Analysis 
## Module 4- Using Anaconda, Pandas, and Jupyter Notebook 

## Purpose of Module 4
In this module, we were introduced to Jupyter Notebook and were instructed to use the pandas library to read raw data in efforts to inspect and manipulate the data to visualize trends. Through this module, we are able to retrieve data so that we can merge, filter, sort, slice, perform mathematical calculations and functions on said data. 

## Overview of Assignment 
For this assignment, we were challenged to visualize the results of standardized tests for a school district so that we could provide insights on performance trends. Our goal was to provide a snapshot of the district's key metrics so board members can make informed decisions on budget allocations. The district metrics were provided through a general district summary and an in-depth school summary where we provided information regarding the top and bottom performing schools, average scores for each student by grade level, and performance based on school budgets, school size, and the type of school. To display accurate results, we repeated the analysis once more after removing the results for Thomas High School’s 9th grade students as there were suspicions of academic dishonesty. 

## Resources 
The data for Module 4 was from the **_schools_complete.csv_** and **_student_complete.csv_** files. 
#### Software used:
   - Python 3.7 
   - Anoconda 4.10.1
   - Jupyter Notebook 6.3.0

## School District Analysis Results 

### Flow of Script 
Our script begins by importing necessary dependancies (pandas and numpy) and locating and reading the files needed to perform our analysis. After an initial visual analysis of our data, we found that the names of some students had unnecessary prefixes and suffixes so we cleaned our data by removing those and replaced them with an empty space. 

<img width="793" alt="Mod4_CleaningData" src="https://user-images.githubusercontent.com/92558842/141924978-5c35380f-f285-4480-a8b7-843dfe64db5d.png">

With clean data, we then began our challenge analysis by replacing the reading and math scores for Thomas High School’s 9th grade students with null values (NaNs)-- as they were suspected to be altered-- by using the loc method containing conditional and logical operators. With the altered data, we completed a school district analysis on a DataFrame containing both the student data and school data files. We calculated the total student and school count, total school budget, the average math and reading scores for each school, and the passing rates and percentages and displayed the information in the District Summary DataFrame, **_district_summary_df_**. 
We took the analysis further and analyzed the data more in depth by creating a School Summary DataFrame, **_per_school_summary_df_**. For each school, we determined its type (district or charter), calculated its total students, total budget, per student spending, average test scores, and passing and percent passing scores. We then updated this data frame to reflect the 10th-12th graders of Thomas High School using the loc method and comparison operators. With the summary visualizing an accurate reflection of Thomas High School, we then displayed the top 5 and bottom 5 performing schools using the sort method. Then, using conditionals and the groupby method, we grouped each school by grade level to compute the average math and reading scores for each grade. By analyzing the per student spending for each school, we created bins to sort the spending on each student to visualize the effects in a new DataFrame— **_spending_summary_df_**—using the cut and groupby methods. Following similar methods, we sorted the scores by school size and school type and displayed those in new DataFrames— **_size_summary_df_** and **_type_summary_df_**, respectively. 

### District Summary
  
   - How is the district summary affected?
      - Our District Summary DataFrame initially had the following results: 
      - <img width="843" alt="OG_DistrictSummary" src="https://user-images.githubusercontent.com/92558842/141925323-3ab24c55-cb0f-4f19-b4a5-4036da5c4595.png">
      - After removing Thomas High Schools 9th grade class, our results changed slightly to the following:
      - <img width="844" alt="ChallengeDistrictSummary" src="https://user-images.githubusercontent.com/92558842/141925349-fa8af29f-d28c-4e7d-a216-a83801c5c46c.png">
      - By comparing the original to the new district summary, we can see that the effects of Thomas High Schools 9th grade class were minimal. The average math score decreased by 0.1 and the percentage of students who passed math decreased by 0.2%. The percentage of students who passed reading decreased by 0.1% and the percentage of students who passed both math and reading decreased by 0.3%. 
    
### School Summary 

  - How is the school summary affected?
    - The following images display the original and updated detailed summary of each school in the district. 
      - Original School Summary:
      - <img width="901" alt="OG_SchoolSummary" src="https://user-images.githubusercontent.com/92558842/141925448-897a53e1-8944-477e-9c08-4dad0d96adb1.png">
   
      - Updated School Summary with Thomas High Schools 9th grade class replaced with NaNs:
      - <img width="903" alt="Challenge_SchoolSummary" src="https://user-images.githubusercontent.com/92558842/141925459-671e9eb7-257a-4d68-8216-fc8ac7567350.png">
    
      - As expected, the only change reflected when comparing the two DataFrames is within the results for Thomas High School. Since Thomas High School’s 9th grade class is only 28.2% percent of the school population, the effects of replacing their scores with null values is fractional. The average math score for the school decreased by 0.067 points and the average reading score increased by 0.47 points. Meanwhile, the percentage of students passing math decreased by 0.086% and that of reading decreased 0.290%. The overall passing percentage for students decreased by 0.317%. 

### Effects of Replacing Thomas High School’s 9th Graders 
  - How does replacing the ninth graders’ math and reading scores affect Thomas High School’s 	Performance relative to the other schools?
    - Thomas High School is the second best performing school when ranked by the percentage of students who passed both math and reading, before and after replacing the 9th grade scores with null values. Meanwhile, there is no affect on the ranking of the bottom performing schools or the ranking of any school for that matter. 
    - Top 5 Schools:
    - <img width="905" alt="TopSchools" src="https://user-images.githubusercontent.com/92558842/141929845-30fc8bbf-ff2f-44b7-8f06-17124420f120.png">
    - Bottom 5 Schools:
    - <img width="903" alt="BottomSchools" src="https://user-images.githubusercontent.com/92558842/141929880-0043c250-d145-4051-9d74-c141800fe675.png">


   
  - Affects on math and reading scores by grade 
    - From the following images we can see that the only change regarding the students average math and reading scores by grade is that the grades for Thomas High School’s 9th grade class contains “nan” or not a number in the updated analysis. 
      - The math scores from the initial analysis: 
      - <img width="285" alt="OG_MathScores" src="https://user-images.githubusercontent.com/92558842/141925573-4eef8564-6bb6-447b-b429-227d1cad4d85.png">
      - The reading scores from the initial analysis:
      - <img width="281" alt="OG_ReadingScores" src="https://user-images.githubusercontent.com/92558842/141925582-c30ec3e5-5687-4431-8093-d057c1e4e93f.png">
      - Math scores after replacing Thomas High School’s 9th grade scores with null values:
      - <img width="278" alt="Challenge_MathScores" src="https://user-images.githubusercontent.com/92558842/141925612-6692ebea-3fd4-4229-98de-12a847348f9b.png">
      - Reading scores after replacing Thomas High School’s 9th grade scores with null values:
      - <img width="292" alt="Challenge_ReadingScores" src="https://user-images.githubusercontent.com/92558842/141925622-b9c3be1f-79be-46b9-a36d-6925088e5078.png">

	- Affects on scores by school spending 
	  - After creating arbitrary bins associated with the range of spending per student across each school for both analyses, we find minimal to no difference between the original analysis and that without values for Thomas High School’s 9th grade class. This is because, even with altered test results, the 9th grade students for Thomas High School are still accounted for in the total student count as spending was still allocated to them. However, after expanding the amount of significant figures reflected in the DataFrame, nominal differences are detected. Regardless of minimal to no change, the results are displayed in the DataFrame below where we see a negative relation between amount spent and performance where the highest success rates are associated with the lowest spending bin.
	    - <img width="748" alt="Challege_spending" src="https://user-images.githubusercontent.com/92558842/141925690-33dd3c1b-b196-4dc6-8b39-792c697cff8b.png">


	- Affects on scores by school size
	  - Replacing Thomas High School’s ninth grade class had minimal to no effect on the average score associated with each school size as reflected in the DataFrame below. However, if you do not format the DataFrame, nominal differences between the original and altered analyses are detected. This could be due to the ninth grade class being only about 1% of the entire school population, thus resulting in minimal to no effect on the scores across the medium sized schools. As expected, we find from this DataFrame that smaller school sizes typically perform better across reading and math- however, not by much as the results for medium school sizes are similar, if not better than small schools. 
	  - <img width="698" alt="Challenge_Size" src="https://user-images.githubusercontent.com/92558842/141925761-851871d9-16c4-4c9f-925a-b9cc9ebb0441.png">


	- Affects on scores by school type 
	  - Similar to the effects on scores by school size, there appears to be minimal to no effect on the average scores by school type, charter or district, after replacing the 9th grade class scores with null values. Regardless of no effect, the results of the DataFrame are displayed below, showing that Charter Schools typically perform better than district schools. 
	  - <img width="647" alt="Challenge_Type" src="https://user-images.githubusercontent.com/92558842/141925772-a55ca06f-2df9-477e-a8b4-3c859eb97941.png">


## Summary 
The analysis of the school district provides a snapshot of key metrics necessary to make decisions on school performance and insight on potential improvements. We captured each schools performance and evaluated them across multiple metrics. We repeated this analysis after replacing the reading and math scores for 9th grade students at Thomas High School after suspicions of academic dishonesty. Replacing the class’s scores with null values had minimal effects on the overall analysis as they were a fraction of the overall student count for the district. One change we did discover in the analysis was variations in the average math score, percentage of students who passed math, percentage of students who passed reading, and the percentage of students who passed both math and reading for the results of the District Summary DataFrame. Although the results were not significant, they were still present since 461 (number of students in the 9th grade class at Thomas High School) scores were changed across each category and that student count is no longer included in the total student count for the district analysis. Although Thomas High School remains the second best performing school, the score metrics for Thomas High School have changed as a result of changing the scores of the 9th grade class to null values. Specifically, Thomas High School’s students average math and reading score, along with the associated percentage of students passing math and reading and percentage of students who passed both math and reading have changed as they are now a reflection of the 10th - 12th grade students instead of the entire school. We also see in an evaluation of math and reading scores by grade one of the most obvious changes in the analysis where Thomas High Schools 9th grade average math and reading scores no longer reflect an average of 83.6 and 83.7, respectively, but rather show “NaN” or no value. Lastly, we find that, after increasing the amount of significant digits reflected in the metrics for the $630-$644 spending range per student bin of the Spending Summary DataFrame and the medium school size of the Size Summary DataFrame that there are nominal differences from the original analysis. 

