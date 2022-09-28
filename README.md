## Linear Regression to Predict MPG
Different models of vehicles have different specifications including vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance.  To determine if these each of these variables affects the number of mpg a vehicle gets, a t-test can be performed. For each variable, the specification will either: 
  -	H0 : Affect the number of miles per gallon at random
  -	Ha : Affect the number of miles per gallon predictably
  
The results were as follows:

![multiple_linear_regression_results](https://user-images.githubusercontent.com/106559768/192905571-cf13cb7b-dc0b-4459-9eaf-b599e15d4ab1.png)

When the test is conducted, the p-values for vehicle length and ground clearance were smaller than significance value of 0.05; This means the results reject the null hypothesis that these variables randomly effect on the number of miles per gallon a vehicle gets, which means these variables predictably impact the number of miles per gallon a vehicle gets. The remaining variables vehicle weight, spoiler angle, and AWD all had p-values that were greater than the significance value of 0.05; This means it is likely that these variables have a more random affect the number of miles per gallon a vehicle gets. The slope of the line would be 0 because of the diversity of the variables does not describe a discernable pattern; It would be more effective to graph each variable independently as the slope for each variable differs. Although the Multiple r-squared value of .71 indicates the data explains about 70% of the data, The linear model does not effectively predict the MechaCar prototypes effectively because the data lacks significant variables; this could lead to accuracy errors when predicting future data because the current model lacks evidence to support the impact some variables have on the number of miles per gallon. 

## Summary Statistics on Suspension Coils
For MechaCar suspension coils are designed to withstand 1500 pounds per square inch. To ensure safety remains a priority, the variance for each coil produced must not exceed 100 pounds per square inch. In this section of the analysis, summary statistics for all manufacturing lots as well as summary statistics for each manufacturing lot individually and are produced to investigate whether this standard is being met. 
Looking at the total_summary data frame, the average indicates that manufacturing practices are generally good; on average, coils are within 2 pounds per square inch of the standard, and the median is exactly the industry standard of 1500 PSI. Although these are promising numbers, the variance and standard deviation indicate there is some variance. 

When the data is grouped by the manufacturing lots, it is apparent there is a difference in how consistently the coils were produced for each lot. Lot 1 is a wonderful example of a very high standard of production. The mean and the median are exactly the industry standard of 1500 PSI. Additionally, the variance is less than 1, meaning there is very little fluctuation in the values, and a small standard deviation means that the values are close to the center.  

The coils from Lot 2 also appears to have a fairly high standard of production. On average, the coils produced withstand 1500.20 PSI, just  0.20 PSI more than the industry standard, and the median is exactly 1500 PSI. Lot 2 differs from lot 1 because the variance is slightly higher; this means that the PSI fluctuates slightly more, but since the standard deviation is still fairly small, most of the values are close to the middle of the data set, and given that the average is almost exactly the industry standard, the coils from Lot 2 are again high quality products. 

When looking at lot 3, the PSI of the coils average slightly lower that the industry standard, with capacity to handle 1496.14 PSI on average. The median of the dataset is also slightly just below the industry standard at 1498.5 PSI. Although these numbers are less exact than the first 2 lots, the average and the median are demonstrate that generally the coils being produced are of acceptable quality. Lot 3 differs significantly from the first 2 with a higher variance; The variance for Lot 3 is about 23 times greater than lot 2, and about 169 times greater than lot 1; This means comparatively the PSI fluctuates the most in this Lot 3. The standard deviation in this lot is also higher, meaning that the data is spread further away from the middle of the data set. Although the variance exceeds 100 it does not necessarily indicate the PSI does not meet the criteria for acceptable standards. 

To verify that all coils meet the standard in this lot, code could be written to calculate the minimum and maximum PSI for the lots Using the following code:
```
coils_min_max <- suspension_coil %>% group_by(Manufacturing_Lot) %>% summarize(Min_PSI=min(PSI), Max_PSI=max(PSI), .groups='keep')
```
![Screenshot (247)](https://user-images.githubusercontent.com/106559768/192906613-f0f59fd5-e9cd-49a5-a483-1cb99309227c.png)

When run, a table showing the minimum and maximum values is produced. The table verifys that all coils produced are within 100PSI of the standard for all lots. Alternatively, the PSI values for Lot 3 could be graphed to visually show the distribution of PSI of all the coils from that lot. 

