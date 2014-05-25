# Code Book for Human Activity Recognition Using Smartphones Dataset

This code book describes the variables, the data, and  transformations or work that we performed to clean up the data. 

Data can be downloaded by url https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip.

## Human Activity Recognition Using Smartphones Dataset

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:


- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.


## The dataset includes the following files:


- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

### The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

## For this project, we only use:

Training data set - 'train/X_train.txt'
Test data set - 'test/X_test.txt'
Training labels - 'train/y_train.txt'
Test labels - 'test/y_test.txt'

* Two files with row identifies the subject who performed the activity for each window sample in range from 1 to 30. 
- 'train/subject_train.txt'
- 'test/subject_test.txt'

* Activity: factor with 6 levels, in order: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING, indicated the activity being performed at the moment of data gathering,

* SubjectID: numeric value from 1 to 30 indicating the subject Id.

### For variables 3 to 68 the variable is numeric and the name indicates:

* Acc and Gyro: data origin, accelerometer and gyroscope, respectively.
* -XYZ: the three dimensional axis, X,Y, or Z, respectively (3-axial)
* Body and Gravity: Acceleration signal source, Body or Gravity, determined using low pass Butter worth filter with a corner frequency of 0.3 Hz.
* Mean and Std: Mean value or Standard deviation, respectively.
* t of f: t denotes time domain signals, these were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butter worth filter with a corner frequency of 20 Hz to remove noise. On the other hand, f denotes the use of a Fast Fourier Transform (FFT) was applied.

* The tidy data set includes 180 (=30*6) observations of 30 subjects' 6 activities.Each subject has 6 activities. Each activity has 66 features as following shows.

```r
"names(tidy_data)" 

[1] "Activity" "SubjectID" "tBodyAccMeanX" "tBodyAccMeanY" "tBodyAccMeanZ" "tBodyAccStdX"
[7] "tBodyAccStdY" "tBodyAccStdZ" "tGravityAccMeanX" "tGravityAccMeanY" "tGravityAccMeanZ" "tGravityAccStdX"
[13] "tGravityAccStdY" "tGravityAccStdZ" "tBodyAccJerkMeanX" "tBodyAccJerkMeanY" "tBodyAccJerkMeanZ" "tBodyAccJerkStdX"
[19] "tBodyAccJerkStdY" "tBodyAccJerkStdZ" "tBodyGyroMeanX" "tBodyGyroMeanY" "tBodyGyroMeanZ" "tBodyGyroStdX"
[25] "tBodyGyroStdY" "tBodyGyroStdZ" "tBodyGyroJerkMeanX" "tBodyGyroJerkMeanY" "tBodyGyroJerkMeanZ" "tBodyGyroJerkStdX"
[31] "tBodyGyroJerkStdY" "tBodyGyroJerkStdZ" "tBodyAccMagMean" "tBodyAccMagStd" "tGravityAccMagMean" "tGravityAccMagStd"
[37] "tBodyAccJerkMagMean" "tBodyAccJerkMagStd" "tBodyGyroMagMean" "tBodyGyroMagStd" "tBodyGyroJerkMagMean" "tBodyGyroJerkMagStd"
[43] "fBodyAccMeanX" "fBodyAccMeanY" "fBodyAccMeanZ" "fBodyAccStdX" "fBodyAccStdY" "fBodyAccStdZ"
[49] "fBodyAccJerkMeanX" "fBodyAccJerkMeanY" "fBodyAccJerkMeanZ" "fBodyAccJerkStdX" "fBodyAccJerkStdY" "fBodyAccJerkStdZ"
[55] "fBodyGyroMeanX" "fBodyGyroMeanY" "fBodyGyroMeanZ" "fBodyGyroStdX" "fBodyGyroStdY" "fBodyGyroStdZ"
[61] "fBodyAccMagMean" "fBodyAccMagStd" "fBodyBodyAccJerkMagMean" "fBodyBodyAccJerkMagStd" "fBodyBodyGyroMagMean" "fBodyBodyGyroMagStd"
[67] "fBodyBodyGyroJerkMagMean" "fBodyBodyGyroJerkMagStd" 
```