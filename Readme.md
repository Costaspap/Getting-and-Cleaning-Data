# Getting and Cleaning Data project

Here are the data for the project: 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

 You should create one R script called run_analysis.R that does the following.  
1.Merges the training and the test sets to create one data set.  
2.Extracts only the measurements on the mean and standard deviation for each measurement.  
3.Uses descriptive activity names to name the activities in the data set.  
4.Appropriately labels the data set with descriptive variable names.  
5.From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.  

##How to run run_analysis.R

You will need to have R installed.
If so,just copy and paste run_analysis.R in your working directory  
and then source it in R using the command source("run_analysis.R").   
The script will download and unzip the dataset folder UCI HAR Dataset
in your working directory and then delete the zip file. Finally it  
will output the file Tidy_Dataset.txt in your working directory.  

run_analysis.R does the following steps(also included as comments in the script):

## Steps of the script

* Step 1: The script checks if the required dataset exists in your working directory.If not it downloads the zip file, unzips it and deletes the zip file.  
* Step 2: Checks if the package plyr is installed and if not installs it and loads it, if yes it just loads it.  
* Step 3: Sets your working directory to be the dataset folder.  
* Step 4: Reads the activity files (y_train.txt and y_test.txt) and stores them in the corresponding variables.  
* Step 5: Reads the features files (X_train.txt and X_test.txt) and stores them in the corresponding variables.  
* Step 6: Reads the subject files (subject_train.txt and subject_test.txt) and stores them in the corresponding variables
* Step 7: Merges the two datasets and names the variables accordingly.  
* Step 8: Creates the final dataset by adding the subject,features and activities dataframes together.  
* Step 9: Reads the activity labels from the activity_labels.txt file and changes activity labels class in the dataset to 
factor. Then changes the factor's levels from 1,2,3,4,5,6 to the appropriate label.  
* Step 10: Labels the data with descriptive variable names, changing the t to time, the f to frequency, the Acc to Accelerometer, the Gyro to Gyroscope, the BodyBody to Body,the Mag to Magnitude and the tBody to timeBody(some variables did't begin with the letter t so i needed to add this one,watch the code to understand this one).  
* Step 11: Extracts only the measurements on the mean and standard deviation for each measurement.  
* Step 12: Subsets the dataset based on the extracted measurements.  
* Step 13: Creates a second, independent tidy data set with the average of each variable for each activity and each subject.  

I include the resulting dataset in this repository under the name Tidy_Dataset.txt
