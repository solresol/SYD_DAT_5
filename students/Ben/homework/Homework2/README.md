# SYD DAT 5 Lab 2 - Visualisation and Regression

Please refer to the folder Labs in this directory 

##Homework - Due July 8th, 2016


* For the following use the github repository you made for your project. 
* Load some data you have gathered for your project into Python.
As discussed & agreed, to protect the propritery information of the company, raw data will not be shared. 

## Identify some numeric and categorical features in your data. Write this up in a file called README.md 

The chosen data science project is to analyse the cost of robotic arms based on past supplier's offers 

The numeric features include: 
* Robot_Strength
* First_Arm_Size
* Second_Arm_Size
* Third_Arm_Size
* Second_Strength
* Enhanced_Strength
* Annoyance_Score
* First_Second_Link
* First_Third_Link
* First_Third_Link
* Instrument_No
* Oil_Consume_Cost
* Fuel_Consume_Cost
* First_Arm_Type_Score
* Second_Arm_Type_Score
* Control_Type_Score
* Warranty
* Quantity
* Supplier_Cost
* Oil_Consume_Rate
* Fuel_Consume_Rate
* Final_Cost 

The categorical features 
* Strink_Type
* High_Noise_Area
* Med_Sound_Withstand_Req
* High_Sound_Withstand_Req
* Control_Tech
* Supplier

## Run some summary statistics over the numeric data 

        Robot_Strength  First_Arm_Size  Second_Arm_Size  Third_Arm_Size  \
count      156.000000      156.000000       156.000000      156.000000   
mean        34.597756       42.897436        13.080609        2.072596   
std         35.837135       27.582484        15.069648        2.317435   
min          5.750000        5.750000         1.650000        0.000000   
25%         11.250000       33.000000         2.875000        0.000000   
50%         25.000000       33.000000         8.250000        2.287500   
75%         38.125000       55.000000        16.500000        2.750000   
max        200.000000      132.500000        82.500000        8.250000   

       Second_Strength  Enhanced_Strength  Annoyance_Score  Oil_Consume_Cost  \
count       156.000000         156.000000       156.000000        156.000000   
mean          2.579327          46.926442        82.275641       1402.575189   
std           4.022937          46.709577        12.236157        826.894699   
min           0.000000           8.125000        62.000000          0.000000   
25%           0.000000          14.625000        70.000000       1000.000000   
50%           0.250000          36.687500        85.500000       1812.500000   
75%           4.500000          56.250000        91.250000       1975.000000   
max          15.750000         260.000000       108.000000       2563.275000   

       Fuel_Consume_Cost  Warranty_Years    Quantity  Supplier_Cost  \
count         156.000000      156.000000  156.000000     156.000000   
mean          241.493881        2.961538    1.621795  256552.191491   
std           170.227702        1.274487    1.860777  139266.535286   
min             0.000000        1.000000    1.000000   71250.000000   
25%           207.500000        2.000000    1.000000  157161.187500   
50%           207.500000        3.000000    1.000000  227839.375000   
75%           318.181818        4.000000    2.000000  307812.500000   
max           519.750000        8.000000   20.000000  757500.000000   

       Oil_Consume_Rate  Fuel_Consume_Rate    Final_Cost  
count        156.000000         156.000000  1.560000e+02  
mean          14.928205          92.656538  5.098780e+05  
std           13.885560          61.327185  3.520304e+05  
min            2.500000          14.750000  7.125000e+04  
25%            7.500000          45.000000  2.549312e+05  
50%            9.875000          77.500000  3.946030e+05  
75%           16.750000         112.500000  7.079883e+05  
max           93.250000         345.500000  2.032136e+06  

## Are there any interesting features of the data that jump out?

The following features are interesting: 
* Robot_Strength has a correlation score of 90% with regards to the supplier offer. Therefore, the cost of robot is closely depend on the robot strength. 
* So Robot strength is the very key parameter. we should be able to generate a linear relationship between the supplier offer and robot strength. 



* Generate some data visualisations that would be useful for you to explore your data set, particularly the numeric data right now.
Histogram of Robot Count in terms of First Arm Size 
Histogram of Robot Strength in terms of First Arm Size
Scatter Matrix of overall numerical data 



* If you can find any good candidates for a regression, try some regressors out.

The following linear regression model were applied: 
* Ransac
* Theil-Sen Estimator 
* Lasso
* Ridge
* Elastic Net
* Ordinary Least Square 
The linear plots of relevant models are stored in the directory for reference. 