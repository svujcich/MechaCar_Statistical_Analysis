## Linear Regression to Predict MPG
Different models of vehicles have different specifications including vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance.  To determine if these each of these variables affects the number of mpg a vehicle gets, a t-test can be performed. For each variable, the specification will either: 
  -	H0 : Affect the number of miles per gallon at random
  -	Ha : Affect the number of miles per gallon predictably
  
The results were as follows:

![multiple_linear_regression_results](https://user-images.githubusercontent.com/106559768/192905571-cf13cb7b-dc0b-4459-9eaf-b599e15d4ab1.png)

When the test is conducted, the p-values for vehicle length and ground clearance were smaller than significance value of 0.05; This means the results reject the null hypothesis that these variables randomly effect on the number of miles per gallon a vehicle gets, which means these variables predictably impact the number of miles per gallon a vehicle gets. The p-value of the vehicle weight is only 0.02 above the significance of 0.05; even though this does not meet the criteria for a significant finding, it does register as having low importance. The remaining variables spoiler angle, and AWD all had p-values that were greater than the significance value of 0.05; This means it is likely that these variables have a more random affect the number of miles per gallon a vehicle gets. The slope of the line would be positive because there is a strong, positive correlation coefficient. The Multiple r-squared value of .71 indicates the data explains about 71% of the data. According to pearson correlation coefficient, thr r-values greater than 0.7 indicates the correlation is strong, which means this model is fairly effective at predicting the mpg of MechaCar vehicles.

## Summary Statistics on Suspension Coils
For MechaCar suspension coils are designed to withstand 1500 pounds per square inch. To ensure safety remains a priority, the variance for each coil produced must not exceed 100 pounds per square inch. In this section of the analysis, summary statistics for all manufacturing lots as well as summary statistics for each manufacturing lot individually and are produced to investigate whether this standard is being met. 

![total_summary](https://user-images.githubusercontent.com/106559768/192944376-098bb9df-ce66-4f8c-96c7-e72d0a9dfded.png)

The dataframe pictured above shows the total_summary dataframe, which summarizes the mean PSI, Median PSI, variance, and Standard deviation of the suspension coil data. The mean indicates that manufacturing practices are generally good; on average, coils are within 2 pounds per square inch of the standard, and the median is exactly the industry standard of 1500 PSI. Although these are promising numbers, the variance and standard deviation indicate there is some variance. 

![max_min_coil_PSI](https://user-images.githubusercontent.com/106559768/192944764-4b5e1986-f004-48b5-926c-9d637bf3d3a3.png)

The  dataframe above shows the same measures the previous dataframe (mean PSI, median PSI, variance, and standard deviation of the suspension coils) organized by lot number. When the data is grouped by the manufacturing lots, it is apparent there is a difference in how consistently the coils were produced for each lot. Lot 1 is a wonderful example of a very high standard of production. The mean and the median are exactly the industry standard of 1500 PSI. Additionally, the variance is less than 1, meaning there is very little fluctuation in the values, and a small standard deviation means that the values are close to the center.  

The coils from Lot 2 also appears to have a fairly high standard of production. On average, the coils produced withstand 1500.20 PSI, just  0.20 PSI more than the industry standard, and the median is exactly 1500 PSI. Lot 2 differs from lot 1 because the variance is slightly higher; this means that the PSI fluctuates slightly more, but since the standard deviation is still fairly small, most of the values are close to the middle of the data set, and given that the average is almost exactly the industry standard, the coils from Lot 2 are again high quality products. 

When looking at lot 3, the PSI of the coils average slightly lower that the industry standard, with capacity to handle 1496.14 PSI on average. The median of the dataset is also slightly just below the industry standard at 1498.5 PSI. Although these numbers are less exact than the first 2 lots, the average and the median are demonstrate that generally the coils being produced are of acceptable quality. Lot 3 differs significantly from the first 2 with a higher variance; The variance for Lot 3 is about 23 times greater than lot 2, and about 169 times greater than lot 1; This means comparatively the PSI fluctuates the most in this Lot 3. The standard deviation in this lot is also higher, meaning that the data is spread further away from the middle of the data set. Although the variance exceeds 100 it does not necessarily indicate the PSI does not meet the criteria for acceptable standards. 

To verify that all coils meet the standard in this lot, code could be written to calculate the minimum and maximum PSI for the lots Using the following code:
```
coils_min_max <- suspension_coil %>% group_by(Manufacturing_Lot) %>% summarize(Min_PSI=min(PSI), Max_PSI=max(PSI), .groups='keep')
```
![Screenshot (247)](https://user-images.githubusercontent.com/106559768/192906613-f0f59fd5-e9cd-49a5-a483-1cb99309227c.png)

When run, a table showing the minimum and maximum values is produced. The table verifys that all coils produced are within 100PSI of the standard for all lots. Alternatively, the PSI values for Lot 3 could be graphed to visually show the distribution of PSI of all the coils from that lot. 

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


