# PEER-ASIGMENT

The run_analysis.R script follows the 5 steps required by the course instructions, starting by the preparation of the data. 

First we download the dataset, given by the folder UCI HAR Dataset

Then we assign the variables to the data given

features <- features.txt : 561 rows, 2 columns 
activities <- activity_labels.txt : 6 rows, 2 columns 
subject_test <- test/subject_test.txt : 2947 rows, 1 column 
x_test <- test/X_test.txt : 2947 rows, 561 columns 
y_test <- test/y_test.txt : 2947 rows, 1 columns 
subject_train <- test/subject_train.txt : 7352 rows, 1 column 
x_train <- test/X_train.txt : 7352 rows, 561 columns 
y_train <- test/y_train.txt : 7352 rows, 1 columns 

Merging the datasets to create one data set
x is created by merging x_train and x_test using rbind() function
y is created by merging y_train and y_test using rbind() function
subject is created by merging subject_train and subject_test using rbind() function
merged is created by merging Subject, Y and X using cbind() function

measurements on the mean and standard deviation for each measurement
tidy is created by subsetting merged, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

Label the dataset
code column in tidy renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

Given this new dataset, we create a new dataset as order in the steps, with the average of each variable

The final dataset is created by grouping by subject and activity with the mean of each

FInally,wxport final into final.txt file.
