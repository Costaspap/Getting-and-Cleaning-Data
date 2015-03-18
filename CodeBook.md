#CodeBook

In this CodeBook you can find the source of the dataset, a description of the dataset,
a description of the files and the variables as well as any transformations made in the run_analysis.R script.

##The source

Source: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip  
Description: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

##Description
Human Activity Recognition Using Smartphones Dataset

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years.  
Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING)
wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope  
we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz.  
The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned  
into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 
The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then  
sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window).  
The sensor acceleration signal, which has gravitational and body motion components, was separated  
using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force  
is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used.  
From each window, a vector of features was obtained by calculating variables from the time and frequency domain.  

For each record it is provided:

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

##The files
The dataset is contained in a folder named "UCI HAR Dataset".  

The dataset contains the following files:  
* README.txt  
Contains a full description of the dataset
* features_info.txt  
Shows information about the variables used on the feature vector.
* features.txt:  
List of all features.
* activity_labels.txt  
Links the activity numbers with the corresponding activity name  
(1=WALKING, 2=WALKING_UPSTAIRS, 3=WALKING_DOWNSTAIRS, 4=SITTING, 5=STANDING, 6=LAYING)
* train/X_train.txt  
Training set feature values.
* train/y_train.txt  
Training labels.
* test/X_test.txt  
Test set feature values.
* test/y_test.txt
Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

* train/subject_train.txt  
Each row identifies the subject who performed the activity for each window sample.  
Its range is from 1 to 30.
* test/subject_test.txt  
Each row identifies the subject who performed the activity for each window sample.  
Its range is from 1 to 30.
* train/Inertial Signals/total_acc_x_train.txt  
The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'.  
Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt'  
and 'total_acc_z_train.txt' files for the Y and Z axis. 
* train/Inertial Signals/body_acc_x_train.txt  
The body acceleration signal obtained by subtracting the gravity from the total acceleration. 
* train/Inertial Signals/body_gyro_x_train.txt  
The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

For the purposes of the project, the files in the Inertial Signals folders are not used.

Notes: 

- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

##The variables
Description of the variables. For more about file values read the "The files" section
 
variable: train_activities  
class: dataframe  
description: A dataframe containing the y_train.txt file values.  

variable: test_activities  
class: dataframe  
description: A dataframe containing the y_test.txt file values.  

variable: train_features  
class: dataframe  
description: A dataframe containing the X_train.txt file values.  

variable: test_features  
class: dataframe  
description: A dataframe containing the X_test.txt file values.  

variable: train_subject  
class: dataframe  
description: A dataframe containing the subject_train.txt file values.  

variable: test_subject  
class: dataframe  
description: A dataframe containing the subject_test.txt file values.  

variable: features  
class: dataframe  
description: A dataframe created after adding the train_features and the test_features  
variables together using the rbind function.  

variable: subject  
class: dataframe  
description: A dataframe created after adding the train_subject and the test_subject  
variables together using the rbind function.  

variable: activities  
class: dataframe  
description: A dataframe created after adding the train_activities and the test_activities  
variables together using the rbind function.  

variable: feature_names  
class: dataframe  
description: A dataframe containing the features.txt file values(only the 2nd column).  

variable: full_dataset  
class: dataframe  
description: The full dataframe created after adding the subject, the activities and the features  
variables together using the cbind function.  

variable: activity_labels  
class: dataframe  
description: A dataframe containing the activity_labels.txt file values.  

variable: mean_std_names  
class: integer(vector)  
description: A vector containing only the columns of full_dataset that include average and standard deviation values.  

variable: tidy_dataset  
class: dataframe  
description: The final dataframe created after grouping the full_dataset by subject and by activity
using the aggregate function and sorted by the subjects and the activities using the arrange function.  

For information about the features variables read the features_info.txt file included in the dataset.  

