Correlation Analysis
Task 1
 
Before delving into predictive modeling with regression analysis, it’s essential to understand the relationships between variables. Correlation analysis is a simple yet effective way to determine if a linear relationship exists between two variables. Please open the Regression Analysis.xlsx file and navigate to the Task 1 sheet.

As part of a broader assignment to perform predictive modeling for The Trendy Shopper, the first task is to explore and understand the relationship between Discount and Total Amount Spent. You must ascertain whether there is a correlation between these two variables and, if so, how strong it is.

Visualize this relationship using a scatter plot to better understand the nature of the relationship.

What is the correlation coefficient between the Discount and Total Amount Spent?

How would you interpret this value?

Based on the scatter plot, how would you describe the relationship between Discount and Total Amount Spent?
Does the scatter plot suggest a positive, negative, or no correlation, and is the relationship linear or non-linear? Use the following hints (if necessary):
The first step is calculating the correlation between the Discount and Total Amount Spent. Use Excel’s CORREL() function to do this.
The next step is to create a scatter plot to better understand the nature of the relationship between the two variables. The following steps create a scatter plot in Excel using the Quick Analysis feature. 

Make sure to select both the Discount and Total Amount Spent columns;
Once you've selected your data, the tiny Quick Analysis button will automatically appear at the bottom right of your selected data. Click on this button;
Click on it to open the following menu. Select “Charts”, then “Scatter”. Excel will automatically generate a scatter plot from your selected data;



Simple Linear Regression
Task 2

Please open the Regression Analysis Dataset.xlsx file and navigate to Task 2.
The next task aims to create a linear regression model to better understand the relationship between the Discount and Total Amount Spent.
This analysis is necessary because it allows us to quantify the impact of discounts on the total amount spent. If there’s a significant relationship between these two variables, we can use this information to make informed decisions about discount strategies to maximize sales.

What are the independent and dependent variables in this analysis?
What is the equation of the regression line?
What are the values of the slope and intercept, and what do they represent in this context?
How well does the regression model fit the data?

Use the following hints (if necessary):

First, let’s determine the independent and dependent variables. A linear regression analysis uses the dependent variable (the response or outcome variable) to predict or explain.
At the same time, the independent variable (the predictor or explanatory variable) is used to predict or explain the dependent variable. In this case, you're trying to predict the Total Amount Spent based on the Discount given.

To perform linear regression in Excel, you can use the Data Analysis ToolPak:

1. Enable the Data Analysis ToolPak. If it's not already enabled, you can do so by clicking File > Options > Add-Ins. In the Manage box, select Excel Add-ins and click Go. In the Add-Ins box, check the Analysis ToolPak and click OK.
2. Prepare your data. Ensure your data is in two columns: one for your independent variable (Discount) and another for the dependent variable (Total Amount Spent). Each row should correspond to a single observation.
3. Start the regression analysis. Go to the Data tab on the Ribbon, and select Data Analysis in the Analysis group. If you have the Data Analysis ToolPak enabled, this should be available.
4. Select Regression: In the Data Analysis dialog box, select Regression and click OK.
5. Specify your data. In the Regression dialog box, specify the ranges for your dependent variable (Y Range) and the independent variable (X Range). If your data includes labels, check the Labels box.
6. Specify output options. Choose where you want your analysis to be output. Choose Output Range and specify a cell if you want it on the same worksheet. If you want it on a new worksheet, choose New Worksheet Ply.
7. Run the analysis. Click OK. Excel will perform the regression analysis and output the results.
The output will include various statistics, including the coefficients for your regression equation (intercept and slope), the standard errors of these coefficients, and the R-squared value.

Multiple Linear Regression
Task 3
Your next task is to refine the linear regression model by incorporating "Product Price" as an explanatory variable. Please open the Regression Analysis Dataset.xlsx file and navigate to the Task 3 sheet.

Using the dataset provided, perform the following steps:

1. Data Cleaning:
Check for missing values in Product Price, Discount, and Total Amount Spent. Handle these missing values appropriately, as they can distort the regression analysis results and lead to inaccurate conclusions.
2. Skewness Analysis:
Compute the skewness values for Product Price, Discount, and Total Amount Spent.
Create histograms for Product Price, Discount, and Total Amount Spent to visually inspect their distributions.
Consider a log transformation if the data deviates from normality.
3. Regression Analysis (Before Transformation):
Perform a multiple linear regression analysis using the original variables.
Examine the residuals plot against each predictor variable (especially Product Price) to check for heteroscedasticity. To do that check the "Residuals" box in the "Output Options" section. If there's a systematic pattern or a funnel shape, it indicates heteroscedasticity.
4. Regression Analysis (After Transformation):
Perform another multiple linear regression analysis using the transformed variables.
Examine the residuals plot to ensure the transformed model addresses any heteroscedasticity observed previously.
6. Interpretation:
Interpret the results of your analysis, focusing on:
The R-squared value of your model and its implications regarding the fit.
The coefficients of Product Price and Discount.
The significance of Product Price and Discount in predicting Total Amount Spent.

Questions for interpretation:

Based on the skewness values, do any variables appear to have distributions that deviate from normality?
Would a log transformation of any variable improve the linearity of the relationship?
How does the R-squared value change (if at all) after transformation? Why?
Are the coefficients interpretable in the context of the problem, especially after any transformations?
Remember, the goal of this task is not just to run the regression analysis, but to deeply understand the relationships between the variables and how they might influence Total Amount Spent. Reflect on the context of the data and the real-world implications of your findings.
Use the following hints (if necessary):

Data Cleaning

Your first step is to examine the dataset and eliminate missing data. If you wish to check whether a cell contains a number, is blank, or has an error, you can combine the ISNUMBER, ISBLANK, and ISERROR functions in the following way:

1. Suppose you want to check cells in column B. In cell E5 (or the first cell of another column), type the formula:

=IF(ISERROR(A1), "Error", IF(ISBLANK(A1), "Blank", IF(ISNUMBER(A1), "Number", "Non-Number")))

This formula checks cell E5 and returns the following:

‘Error’ if the cell contains an error value
‘Blank’ if the cell is empty
‘Number’ if the cell contains a number
‘Non-Number’ if the cell contains text or other non-number value
2. Press Enter. The function will return a text string based on the contents of the cell .

3. To check the entire column, click on the bottom-right corner of cell E5 (where the formula is) and drag it down to copy it to the whole column.
You can now quickly identify cells that contain numbers, are blank, have errors, or contain non-number values. If you want to delete rows, uncheck the boxes for Number so that only Blank, Non-Number, and Error are selected, and click OK. This will filter your data only to show the rows where the column is Blank, Error, or Non-Number. Select the visible (filtered) rows. You can do this by clicking on the row number for the first visible row, holding down the Shift key, and then clicking on the row number for the last visible row.
With the rows still selected, right-click on one of the selected rows and choose Delete Row from the context menu. Excel will delete all the visible (filtered) rows. To remove the filter and show all rows again, return to the Data tab and click the Filter button again.

Skewness Analysis:
Compute Skewness:

Using Excel, compute the skewness values for Product Price, Discount, and Total Amount Spent.
Enter your dataset into an Excel spreadsheet column.
Use the SKEW function to calculate skewness. For instance, if your data for Product Price is in cells A1 through A100, type =SKEW(A1:A100) in a blank cell.
Note the resulting skewness values for each variable.
Interpret Skewness:
Interpret the skewness values using the following guidelines:
A skewness value close to 0 indicates the distribution is approximately symmetric.
A positive skewness value indicates a right-skewed distribution.
A negative skewness value indicates a left-skewed distribution.
Visualize Distributions:
Create histograms for Product Price, Discount, and Total Amount Spent to visually inspect their distributions.
In Excel, highlight the data column you wish to visualize.
Go to the 'Insert' tab and choose 'Histogram' from the 'Charts' group.
Examine the shape of the histogram to visually corroborate your skewness findings.
Log Transformation in Excel (if needed)
If the scatter plots suggest non-linearity, you can use Excel's LN function for log transformations.
Insert a new column next to Product Price and name it Log_Product Price.
In the first cell of this column, type the formula =LN(A2) (assuming A2 is the first cell of the Product Price column). Drag the formula down to fill the column.
If Total Amount Spent also appears to have a non-linear relationship, repeat the process by creating a Log_Total Amount Spent column.
Run the Regression
Once the data is cleaned, you can use the Data Analysis ToolPak to perform the multiple linear regression.Make sure you check the "Residuals" box in the "Output Options" section. 
