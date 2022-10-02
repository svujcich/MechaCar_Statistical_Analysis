## Linear Regression to Predict MPG
Different models of vehicles have different specifications including vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance.  To determine if these each of these variables affects the number of mpg a vehicle gets, a t-test can be performed. For each variable, the specification will either: 
  -	H0 : Affect the number of miles per gallon at random
  -	Ha : Affect the number of miles per gallon predictably
  
The results were as follows:

![multiple_linear_regression_results](https://user-images.githubusercontent.com/106559768/192905571-cf13cb7b-dc0b-4459-9eaf-b599e15d4ab1.png)

When the test is conducted, the p-values for vehicle length and ground clearance were smaller than significance value of 0.05; This means the results reject the null hypothesis that these variables randomly effect on the number of miles per gallon a vehicle gets, which means these variables predictably impact the number of miles per gallon a vehicle gets. The p-value of the vehicle weight is only 0.02 above the significance of 0.05; even though this does not meet the criteria for a significant finding, it does register as having low importance. The remaining variables spoiler angle, and AWD all had p-values that were greater than the significance value of 0.05; This means it is likely that these variables have a more random affect the number of miles per gallon a vehicle gets. The slope of the line would be non-zero because overall, p=5.35e-11 < 0.05. A p-value less than 0.05 indicates the results are significant, meaning the results are dependant to changes in the independant varibles, so the line will have a slope that is not zero. Although a small value, the p-value is positive, so the slope of the line would be positive. The Multiple r-squared value of .71 indicates the data explains about 71% of the data. According to pearson correlation coefficient, thr r-values greater than 0.7 indicates the correlation is strong, which means this model is fairly effective at predicting the mpg of MechaCar vehicles.

## Summary Statistics on Suspension Coils
For MechaCar suspension coils are designed to withstand 1500 pounds per square inch. To ensure safety remains a priority, the variance for the coils produced must not exceed 100 pounds per square inch. In this section of the analysis, summary statistics for all manufacturing lots as well as summary statistics for each manufacturing lot individually and are produced to investigate whether this standard is being met. 

![total_summary](https://user-images.githubusercontent.com/106559768/192944376-098bb9df-ce66-4f8c-96c7-e72d0a9dfded.png)

The dataframe pictured above shows the total_summary dataframe, which summarizes the mean PSI, Median PSI, variance, and Standard deviation of the suspension coil data. The mean indicates that manufacturing practices are generally good; on average, coils are within 2 pounds per square inch of the standard, and the median is exactly the industry standard of 1500 PSI. The variance for the coils is within the 100 PSI threshold and appears to be acceptable, but to ensure quality, each production batch should be investigated indiidually. 

![lot summary](https://user-images.githubusercontent.com/106559768/193472972-3fd51650-a176-4668-acfe-47e2ef18e1ac.png)

The  dataframe above shows the same measures the previous dataframe (mean PSI, median PSI, variance, and standard deviation of the suspension coils) organized by lot number. When the data is grouped by the manufacturing lots, it is apparent there is a difference in how consistently the coils were produced for each lot. 

Lot 1 is a wonderful example of a very high standard of production. The mean and the median are exactly the industry standard of 1500 PSI. There is also a small standard deviation, meaning the PSI of units in this lot were clustered around the median. Since the variance is less than 1, there was very little fluctuation in production standards, and given the variance is less than 100 PSI, Lot 1 is well within the standards of the design specifications. 

The coils from Lot 2 also appears to have a fairly high standard of production. On average, the coils produced withstand 1500.20 PSI, just  0.20 PSI more than the industry standard, the median is exactly 1500 PSI, the standard deviation is still fairly small. In Lot 2, the variance in the coils is less than 100, which means these coils meet the design specifications. 

Although the average and the median PSI for the coils produced in Lot 3 appears to be of acceptable quality, the variance for the lot exceeds 100 PSI. This means the quality of the coils from lot 3 is inconsist, and does not meet the design specifications.

## T-Tests on Suspension Coils
Given the data about the suspension coils, a t-test can be used to compare whether the mean of a random PSI sample is representative of the whole. Conducting a t-test will show either:

  - H0: There is no statistical difference between the sample and the population data
  - Ha: There is statistical difference between the sample and population data exists 

When a random sample was collected from the population data, and used in a t-test against the population data, the results were as follows:

![t-test_population_sample](https://user-images.githubusercontent.com/106559768/192942644-b8eb5db7-ca50-430d-a944-6034fb966d3b.png)

The T-Test results show that the p-value for a random sample from the population data is greater than the significance value of 0.05, whichs provide grounds to accept the null hypothesis, meaning the population data and the sample data are not statistically different. 
A T-Test can also be conducted using subsets of the data from each Manufacturing lot to test whether or not the means are statistically similar to the mean or the population table. The test for subsets of each manufacturing lot would maintain the same hypotheses:

  - H0: There is no statistical difference between the sample and the population data
  - Ha: There is statistical difference between the sample and population data exists 
  
The results are as Follows:

![t-test_subset_mfg_lots](https://user-images.githubusercontent.com/106559768/192942689-616c06eb-7a9d-4581-bfcd-2346c958cd63.png)

The previous image shows the results of the T-Test for manufacturing Lot1, Lot 2, and Lot 3 respectively. Both lot 1 and Lot 2 have a p value that is greater than the significance value of 0.05. In both cases, the null hypothesis is accepted, and the there is no statistical difference between the mean of the subset and the mean of the population. This conclusion aligns with the mean values for each lot discovered using the summary statistics table. 
Looking at the T-Test results for Lot 3, the p-value is 0.04. Because the  p-value for Lot 3 is less than the significance value of 0.05, the null hypothesis is rejected and the alternate hypothesis is accepted; this means there is a statistical difference between the mean of the subset and the mean of the population. Again, this conclusion aligns with the findings from the summary statistic table, where the mean PDI of Lot 3 was determined to be less than the design specifications of 1500 PSI. 

## Study Design: MechaCar vs Competition
In a market full of competition, customers have many options about where to buy a vehicle. In order to capture vehicle sales, it would be beneficial conduct additional statistical studies to determine how MechaCar compares to its competitors. One statistical test that might be of interest to consumers is how does city fuel efficiency differ from highway fuel efficiency across brands. 
In this study, a pair t-test would be used; this is because the study would be comparing observations about fuel efficiency in two different settings; fuel efficiency in the city and fuel efficiency on the highway. The hypotheses would follow:

-	H0: the difference between the paired observations is equal to zero
-	Ha: the difference between the paired observations is not equal to zero

In order to conduct this test, the data about the competitors’ vehicles would first need to be compiled. The dataset which would include columns for brand, body type, city fuel efficiency, and highway fuel efficiency. Fortunately for MechaCar, this information that is available to the public, and could be obtained through web scraping competitors’ websites. The information for each brand would be tested to find the average city fuel efficiency and average highway efficiency for each brand to determine if there is a statistical difference for each brand. All the brands would then be analyzed for similarities and differences. The results could be graphed to visualize the data. If the parameters needed to be more specific, the same tests could be conducted about the fuel efficiency given the different body styles for each brand. 

