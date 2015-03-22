# UCI-HAR-Dataset
Getting And Cleaning Data - Course Project

HOW THE SCRIPT WORKS?
run_analysis.R already has detailed comments. Here is the overview:
- activity_labels.txt and features.txt are read using read.table() functions
- Both the data frames are converted to data tables to be used later
- Similarly subject_test.txt is read into a data frame 
- y_test.txt and X_test.txt are also read. A new table called "test" is created using cbind that has y_test as the first column 
  and all 561 columns in X_test.txt. The new table has the same number of rows X_test.txt and y_test.txt
- Previous step is repeated for the train dataset. A combined table called "train" is created
- Another combined table called "final" combines "test" and "train" using rbind()
- finaldt is the corresponding data table for the final data frame
- column names for finaldt is replaced with activity, subject and transposed values of features
- column means for all columns in finaldt are calculated
- column standard deviations for all columns in finaldt are calculated
- column mean for every activity, subject and each of the variables is also calculated and output written to "output.txt"

CODE BOOK:
Information about variables:
Final output has all 561 variables; the same variables found in X_test.txt and X_train.txt
Their units have not been changed from the inputs files (X_test.txt and X_train.txt)

Information about summary choices:
Each variable is averaged by the first two rows  i.e., activity and subject.
Since there are 30 subject and 6 activities, each of the 561 variables have 180 rows. Result is 180x563 matrix
Was unable to replace activity code with activity description due to repetitions in column names among the 561 variables. This
tnrows an error
