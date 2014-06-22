Codebook 
=================


##This codebook builds on top of the fatures_info.txt file found in the Samsung data file.

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). These signals were used to estimate variables of the feature vector for each pattern: '-XYZ' is used to denote 3-axial signals in the X, Y and Z directions. 

The colnames were created by the make.names() function in R. This removed the () and 
any other special character from the names. 
a subset was extracted using a regular expression that grabed all columns that were means and std's 
This was then averaged using the mean() function by a combination of the subject ID that is shown in Group.1 and 
the activity that is being performed, as established by the activity_labels.txt file found in the samsung dat files,
that is Group.2. Therefore each data point represents the mean of one of the means or std of that features given the 
individual and the activity performed at that moment the values represent the mean of such subsets. 

Group.1
Group.2
tBodyAcc.mean...X
tBodyAcc.mean...Y
tBodyAcc.mean...Z
tBodyAcc.std...X
tBodyAcc.std...Y
tBodyAcc.std...Z
tGravityAcc.mean...X
tGravityAcc.mean...Y
tGravityAcc.mean...Z
tGravityAcc.std...X
tGravityAcc.std...Y
tGravityAcc.std...Z
tBodyAccJerk.mean...X
tBodyAccJerk.mean...Y
tBodyAccJerk.mean...Z
tBodyAccJerk.std...X
tBodyAccJerk.std...Y
tBodyAccJerk.std...Z
tBodyGyro.mean...X
tBodyGyro.mean...Y
tBodyGyro.mean...Z
tBodyGyro.std...X
tBodyGyro.std...Y
tBodyGyro.std...Z
tBodyGyroJerk.mean...X
tBodyGyroJerk.mean...Y
tBodyGyroJerk.mean...Z
tBodyGyroJerk.std...X
tBodyGyroJerk.std...Y
tBodyGyroJerk.std...Z
tBodyAccMag.mean..
tBodyAccMag.std..
tGravityAccMag.mean..
tGravityAccMag.std..
tBodyAccJerkMag.mean..
tBodyAccJerkMag.std..
tBodyGyroMag.mean..
tBodyGyroMag.std..
tBodyGyroJerkMag.mean..
tBodyGyroJerkMag.std..
fBodyAcc.mean...X
fBodyAcc.mean...Y
fBodyAcc.mean...Z
fBodyAcc.std...X
fBodyAcc.std...Y
fBodyAcc.std...Z
fBodyAcc.meanFreq...X
fBodyAcc.meanFreq...Y
fBodyAcc.meanFreq...Z
fBodyAccJerk.mean...X
fBodyAccJerk.mean...Y
fBodyAccJerk.mean...Z
fBodyAccJerk.std...X
fBodyAccJerk.std...Y
fBodyAccJerk.std...Z
fBodyAccJerk.meanFreq...X
fBodyAccJerk.meanFreq...Y
fBodyAccJerk.meanFreq...Z
fBodyGyro.mean...X
fBodyGyro.mean...Y
fBodyGyro.mean...Z
fBodyGyro.std...X
fBodyGyro.std...Y
fBodyGyro.std...Z
fBodyGyro.meanFreq...X
fBodyGyro.meanFreq...Y
fBodyGyro.meanFreq...Z
fBodyAccMag.mean..
fBodyAccMag.std..
fBodyAccMag.meanFreq..
fBodyBodyAccJerkMag.mean..
fBodyBodyAccJerkMag.std..
fBodyBodyAccJerkMag.meanFreq..
fBodyBodyGyroMag.mean..
fBodyBodyGyroMag.std..
fBodyBodyGyroMag.meanFreq..
fBodyBodyGyroJerkMag.mean..
fBodyBodyGyroJerkMag.std..
fBodyBodyGyroJerkMag.meanFreq..
