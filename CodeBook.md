# Code Book for Samsung Acceleration Analysis #
## Terminology ##
The following table lists the variable names for all 88 columns of the resulting tidy data set on the Samsung Phone data.  A brief explanation, based on the descriptive name in column three will clarify the meaning of these data.  The first two columns list the subjects, by number (1-30) and the task they were performing while that data were collected.  The task names are self explanatory. 

 The remaining 86 columns are all the features that contained either mean or std (standard deviation) in their original names. They are all derived from the original linear acceleration data measured by the accelerometer or angular acceleration measured by the gyroscope. They are appropriately labeled either Acc or Gyro within their names  Further the data are the result of a time domain statistic or frequency domain statistic with either time or freq as part of their name.  Finally data is either directional, labeled X,Y, or Z, or the magnitude- combining all three vectors geometrically.  It was not explicitly stated in the original documentation, but traditional the meaning of X is across the body , while Y is from front to back, and Z is the vertical axis. However, since the orientation of the phone relative to the subject was not know, these descriptions may not be valid.  So, for example, the variable TimeBodyACCMeanX is the average value of the linear acceleration in the X direction while a subject was performing a particular task. Similarly, the variable FreqBodyGyroMeanFreqY is the average frequency of angular acceleration in the Y direction. 

The authors also derived  "jerk" features from both the accelerometer and gyroscopic data, representing sudden linear or angular accelerations and analyzed these in a similar matter. How these signals were computed is not stated, but given the descriptive nature of the term one would expect either a time derivative or high pass frequency filter to generate such signals. 

Finally the last seven features are all measurements of angles between two features. How they were computed is not described Since they all contain the word gravity as one of features it is likely that they are useful for ascertaining the orientation of the subject and/or phone.

## Units ##
 The original units of the sampled data were g's (one g is 9.8 meter/second^2 and radians/second^2. The features are all normalized to fall within the range negative one to positive one, and therefore unit-less.
 
 
 


| Column | Original Name                        | Descriptive Name                   |
|--------|--------------------------------------|------------------------------------|
| 1      | Subject                              | Subject                            |
| 2      | Activity                             | Activity                           |
| 3      | tBodyAcc-mean()-X                    | TimeBodyAccMeanX                   |
| 4      | tBodyAcc-mean()-Y                    | TimeBodyAccMeanY                   |
| 5      | tBodyAcc-mean()-Z                    | TimeBodyAccMeanZ                   |
| 6      | tBodyAcc-std()-X                     | TimeBodyAccStdDevX                 |
| 7      | tBodyAcc-std()-Y                     | TimeBodyAccStdDevY                 |
| 8      | tBodyAcc-std()-Z                     | TimeBodyAccStdDevZ                 |
| 9      | tGravityAcc-mean()-X                 | TimeGravityAccMeanX                |
| 10     | tGravityAcc-mean()-Y                 | TimeGravityAccMeanY                |
| 11     | tGravityAcc-mean()-Z                 | TimeGravityAccMeanZ                |
| 12     | tGravityAcc-std()-X                  | TimeGravityAccStdDevX              |
| 13     | tGravityAcc-std()-Y                  | TimeGravityAccStdDevY              |
| 14     | tGravityAcc-std()-Z                  | TimeGravityAccStdDevZ              |
| 15     | tBodyAccJerk-mean()-X                | TimeBodyAccJerkMeanX               |
| 16     | tBodyAccJerk-mean()-Y                | TimeBodyAccJerkMeanY               |
| 17     | tBodyAccJerk-mean()-Z                | TimeBodyAccJerkMeanZ               |
| 18     | tBodyAccJerk-std()-X                 | TimeBodyAccJerkStdDevX             |
| 19     | tBodyAccJerk-std()-Y                 | TimeBodyAccJerkStdDevY             |
| 20     | tBodyAccJerk-std()-Z                 | TimeBodyAccJerkStdDevZ             |
| 21     | tBodyGyro-mean()-X                   | TimeBodyGyroMeanX                  |
| 22     | tBodyGyro-mean()-Y                   | TimeBodyGyroMeanY                  |
| 23     | tBodyGyro-mean()-Z                   | TimeBodyGyroMeanZ                  |
| 24     | tBodyGyro-std()-X                    | TimeBodyGyroStdDevX                |
| 25     | tBodyGyro-std()-Y                    | TimeBodyGyroStdDevY                |
| 26     | tBodyGyro-std()-Z                    | TimeBodyGyroStdDevZ                |
| 27     | tBodyGyroJerk-mean()-X               | TimeBodyGyroJerkMeanX              |
| 28     | tBodyGyroJerk-mean()-Y               | TimeBodyGyroJerkMeanY              |
| 29     | tBodyGyroJerk-mean()-Z               | TimeBodyGyroJerkMeanZ              |
| 30     | tBodyGyroJerk-std()-X                | TimeBodyGyroJerkStdDevX            |
| 31     | tBodyGyroJerk-std()-Y                | TimeBodyGyroJerkStdDevY            |
| 32     | tBodyGyroJerk-std()-Z                | TimeBodyGyroJerkStdDevZ            |
| 33     | tBodyAccMag-mean()                   | TimeBodyAccMagMean                 |
| 34     | tBodyAccMag-std()                    | TimeBodyAccMagStdDev               |
| 35     | tGravityAccMag-mean()                | TimeGravityAccMagMean              |
| 36     | tGravityAccMag-std()                 | TimeGravityAccMagStdDev            |
| 37     | tBodyAccJerkMag-mean()               | TimeBodyAccJerkMagMean             |
| 38     | tBodyAccJerkMag-std()                | TimeBodyAccJerkMagStdDev           |
| 39     | tBodyGyroMag-mean()                  | TimeBodyGyroMagMean                |
| 40     | tBodyGyroMag-std()                   | TimeBodyGyroMagStdDev              |
| 41     | tBodyGyroJerkMag-mean()              | TimeBodyGyroJerkMagMean            |
| 42     | tBodyGyroJerkMag-std()               | TimeBodyGyroJerkMagStdDev          |
| 43     | fBodyAcc-mean()-X                    | FreqBodyAccMeanX                   |
| 44     | fBodyAcc-mean()-Y                    | FreqBodyAccMeanY                   |
| 45     | fBodyAcc-mean()-Z                    | FreqBodyAccMeanZ                   |
| 46     | fBodyAcc-std()-X                     | FreqBodyAccStdDevX                 |
| 47     | fBodyAcc-std()-Y                     | FreqBodyAccStdDevY                 |
| 48     | fBodyAcc-std()-Z                     | FreqBodyAccStdDevZ                 |
| 49     | fBodyAcc-meanFreq()-X                | FreqBodyAccMeanFreqX               |
| 50     | fBodyAcc-meanFreq()-Y                | FreqBodyAccMeanFreqY               |
| 51     | fBodyAcc-meanFreq()-Z                | FreqBodyAccMeanFreqZ               |
| 52     | fBodyAccJerk-mean()-X                | FreqBodyAccJerkMeanX               |
| 53     | fBodyAccJerk-mean()-Y                | FreqBodyAccJerkMeanY               |
| 54     | fBodyAccJerk-mean()-Z                | FreqBodyAccJerkMeanZ               |
| 55     | fBodyAccJerk-std()-X                 | FreqBodyAccJerkStdDevX             |
| 56     | fBodyAccJerk-std()-Y                 | FreqBodyAccJerkStdDevY             |
| 57     | fBodyAccJerk-std()-Z                 | FreqBodyAccJerkStdDevZ             |
| 58     | fBodyAccJerk-meanFreq()-X            | FreqBodyAccJerkMeanFreqX           |
| 59     | fBodyAccJerk-meanFreq()-Y            | FreqBodyAccJerkMeanFreqY           |
| 60     | fBodyAccJerk-meanFreq()-Z            | FreqBodyAccJerkMeanFreqZ           |
| 61     | fBodyGyro-mean()-X                   | FreqBodyGyroMeanX                  |
| 62     | fBodyGyro-mean()-Y                   | FreqBodyGyroMeanY                  |
| 63     | fBodyGyro-mean()-Z                   | FreqBodyGyroMeanZ                  |
| 64     | fBodyGyro-std()-X                    | FreqBodyGyroStdDevX                |
| 65     | fBodyGyro-std()-Y                    | FreqBodyGyroStdDevY                |
| 66     | fBodyGyro-std()-Z                    | FreqBodyGyroStdDevZ                |
| 67     | fBodyGyro-meanFreq()-X               | FreqBodyGyroMeanFreqX              |
| 68     | fBodyGyro-meanFreq()-Y               | FreqBodyGyroMeanFreqY              |
| 69     | fBodyGyro-meanFreq()-Z               | FreqBodyGyroMeanFreqZ              |
| 70     | fBodyAccMag-mean()                   | FreqBodyAccMagMean                 |
| 71     | fBodyAccMag-std()                    | FreqBodyAccMagStdDev               |
| 72     | fBodyAccMag-meanFreq()               | FreqBodyAccMagMeanFreq             |
| 73     | fBodyBodyAccJerkMag-mean()           | FreqBodyBodyAccJerkMagMean         |
| 74     | fBodyBodyAccJerkMag-std()            | FreqBodyBodyAccJerkMagStdDev       |
| 75     | fBodyBodyAccJerkMag-meanFreq()       | FreqBodyBodyAccJerkMagMeanFreq     |
| 76     | fBodyBodyGyroMag-mean()              | FreqBodyBodyGyroMagMean            |
| 77     | fBodyBodyGyroMag-std()               | FreqBodyBodyGyroMagStdDev          |
| 78     | fBodyBodyGyroMag-meanFreq()          | FreqBodyBodyGyroMagMeanFreq        |
| 79     | fBodyBodyGyroJerkMag-mean()          | FreqBodyBodyGyroJerkMagMean        |
| 80     | fBodyBodyGyroJerkMag-std()           | FreqBodyBodyGyroJerkMagStdDev      |
| 81     | fBodyBodyGyroJerkMag-meanFreq()      | FreqBodyBodyGyroJerkMagMeanFreq    |
| 82     | angle(tBodyAccMean,gravity)          | angletBodyAccMean,gravity          |
| 83     | angle(tBodyAccJerkMean),gravityMean) | angletBodyAccJerkMean,gravityMean  |
| 84     | angle(tBodyGyroMean,gravityMean)     | angletBodyGyroMean,gravityMean     |
| 85     | angle(tBodyGyroJerkMean,gravityMean) | angletBodyGyroJerkMean,gravityMean |
| 86     | angle(X,gravityMean)                 | angleX,gravityMean                 |
| 87     | angle(Y,gravityMean)                 | angleY,gravityMean                 |
| 88     | angle(Z,gravityMean)                 | angleZ,gravityMean                 |
