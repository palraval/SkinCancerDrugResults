# SkinCancerDrugResults



## Data Cleaning, Filtering, & Plotting 
The two data files ("Mouse_metadata.csv" and "Study_results.csv") are merged to provide a single dataframe consisting of the
columns: "Mouse ID", "Timepoint", "Tumor Volume (mm3)", "Metastatic Sites", "Drug Regimen", "Sex", "Age_months", and Weight(g). The number of unique mice in the merged dataframe are counted according to the Mouse_ID column. After this, the unique values of "Mouse_ID" are found if they contain duplicate values for "Mouse_ID" and "Timepoint". The "Mouse_ID" that is located is then removed from the merged dataframe.  

The following statistics are calculated from the "Tumor Volume (mm3)" column in the cleaned dataframe for each drug: mean, median, variance, standard deviation, and standard error. These statistics are placed into a dataframe to form a statistics table. 

A bar graph is then created that displays the total amount of observed mouse timepoints for each drug. A pie plot is also implemented to show the distribution of the mice's sex. 

Next, a dataframe consisting of rows that contain only the final timepoints (highest timepoints) for each mouse is created. This dataframe is then merged with the cleaned dataframe. This new merged dataframe is then filtered to only include mice who are treated with: Capomulin, Ramicane, Infublinol, or Ceftamin. 

For each of the filtered drugs, the quartiles of the final tumor volume are calculated. From this, the IQR for each drug is arithmetically determined by subtracting the Q3 and Q1 values. The lowest and highest outliers are calculated using the information about the Q1 value, Q3 value, and the respective IQR for each drug. Ultimately, the following values are found for each drug based on the final tumor volumes: the IQR, the lowest outlier, and the highest outlier. Finally, a box plot of the final tumor volume for each of the four drugs is created.

A series containing the "Mouse_ID" values of mice that are treated with the drug called "Capomulin" is found. From this series, a single "Mouse_ID" value is selected. The cleaned dataframe is filtered to only contain the chosen "Mouse_ID" value. Using this filtered dataframe, a line plot is drawn containing the "Tumor Volume (mm3)" and "Timepoint (days)" columns. This plot shows the change in tumor volume over the course of the "Capomulin" drug treatment. 

A dataframe containing only the mice that were treated with "Capomulin" is made. From this new dataframe, another dataframe is created containing the Mice's IDs, their weights, and their average tumor volume. A scatterplot is generated from the data regarding weight and average tumor volume.

The correlation coefficient of scatterplot's data is calculated. The linear regression statistics (slope, intercept, r-value, p-value, standard error) are calculated to form the linear regression equation. From this equation, the predicted values of average tumor volume based on the linear regression equation is found for the mice's weights and plotted on the scatterplot. 

## Analysis

* The bar graph shows that the drugs "Capomulin" and "Ramicane" have the highest number of observed mouse timepoints, while "Propiva" has the lowest. 

* The pie chart shows that there is a slightly higher percentage of males in the data compared to females. 

* The box plot shows that "Ramicane" seems to be the most effective drug for dealing with this form of skin cancer. The final tumor volume is lower for mice who were treated with "Ramicane" than the rest. However, "Capomulin" seems to be very effective as well. The mice who were given "Capomulin" didn't have the lowest values for final tumor volume, but it was still lower than the other two drugs. In general, mice given "Capomulin" seem have lower tumor volumes compared to those who have not been given it. 

* Due to the strong correlation coefficient (0.84) between weight and average tumor volume, it can be concluded that there is a strong positive correlation between the mice's weight and their average tumor volume. 

* Plotting the linear regression on the scatterplot shows that the equation seems to do quite well at predicting the average tumor volume using the weights. 
