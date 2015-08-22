## Coursera - Getting and Cleaning Data Project

ROSTISLAV UHLIR

### Description
This file provides additional information about the variables, data and transformations processes used in the course project for the Johns Hopkins Getting and Cleaning Data course.

### Data Source
A full description of the data used in this project can be found at [The UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

[The source data for this project can be found here.](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

### Data Set Information
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

### Attribute Information
For each record in the dataset it is provided:
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope.
- A 561-feature vector with time and frequency domain variables.
- Its activity label.
- An identifier of the subject who carried out the experiment.

##### Step 1. Merges the training and the test sets to create one data set
Sets the source directory for the files and reads into tables the data located in
- features.txt
- activity_labels.txt
- subject_train.txt
- x_train.txt
- y_train.txt
- subject_test.txt
- x_test.txt
- y_test.txt

Assigns column names and merges to create one data set.

##### Step 2. Extracts only the measurements on the mean and standard deviation for each measurement. 
Uses grep pattern matching and replacement function to extract only the information from columns regarding the standard deviation and mean

##### Step 3. Uses descriptive activity names to name the activities in the data set
Merges and labels the dataset with subject, activity, variable called featureswanted

##### Step 4. Appropriately label the data set with descriptive activity names.
Uses the gsub function to label the data properly through a variable featureswanted

##### Step 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
We produce only a data set with the average of each variable for each activity and subject using a melt and dcast functions

### Activity Labels

* `WALKING` (value `1`): Walking during the test
* `WALKING_UPSTAIRS` (value `2`): Walking up a staircase during the test
* `WALKING_DOWNSTAIRS` (value `3`): Walking down a staircase during the test
* `SITTING` (value `4`): Sitting during the test
* `STANDING` (value `5`): Standing during the test
* `LAYING` (value `6`): Laying down during the test
