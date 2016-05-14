# Getting-and-Cleaning-Data-Assignment

## Introduction ##
The script in this repo is for manipulating data collected from a study using the accelerometer and gyroscope integrated into a Samsung Galaxy S II smartphone.  Thirty subjects were asked to perform six tasks multiple times.  These tasks were walking on level ground, walking up stairs, walking down stairs, sitting.,standing, and laying down.  A possible use for these data is to help develop an app that for an individual identifies and logs
 these activities, similar to commercial wrist worn activity monitors.  The advantage being that if it could be done on an individual basis, it could be more accurate than one designed with data averaged over a population. 

Further information regarding the protocol can be found here:

[http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones "Link to protocol description.")

The data accessed for the assignment  are available for download at this link: [https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip "Link to data zip file.")

The zip file obtained from this link contains the following:


1. A readme text, where much of this summary is taken.
2. A file named feature.txt with a list of all the derived feature variables.
3. A file named features_info.txt which contains brief descriptions of the various derived features.
4. A file named activity_labels.txt that links the numbering of the six activities in the Y_????.txt files to the actual activity performed. **Note ???? can be either training or test**.
5. Two sub-directories labeled training and test which contain separate data sets, to be combined in this assignment.  Within each of these directories is the following:
  6.  A subdirectory called Inertial Signals, which may be thought of as the "raw" data fromw which the feature variable test and training feature variabes are derived  In reality, however the Inertial Signals were actually processed  "by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window)" to the data from the phone. Inertial Signals were not used in this assignment.
  7.   A file named X_????.txt  which   contains the 561 feature  set variable data that were computed from the Inertial File Data.
  8.   A file named Y_????.txt which contain the ordered activities associated with the derived feature data point in the X_????.txt file
  9.   A file named subject_????.txt which contains the ordered subject list  associated with each data point in the x_????.txt file.

  
## First Task -Aggregate the Data##
As can be seen from the above description, looking at individual files it can be difficult to intepert the data since labels, activities and data are scattered among many different files.  Therefore the first part of the effort is to combine multiple files into a single file that is more easily understood. In particular we are to create one file with the following features:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set.
4. Appropriately labels the data set with descriptive variable names.

## Second Task -Summarize the Data over each Test Subject and Activity ##

From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Averaging the data for each activity and each subject is clear.  What is meant by making it a tidy data set merits some discussion.  In particular one has the choice of making it a wide set or long set depending on what will use the data for. In a long set each feature for each subject would be in a separate row.  Given that there are 86 features X 30 subject X 6 activities. This would create a long file with four columns (subject,activity,feature, and value).  Alternatively one could list all features in their own column for each subject and activity, resulting in 30 subjects x 6 activity rows with all 86 features listed per row.  Given that the data are most likely to be analyzed to see which are useful for distinguishing activities,  we will probably want to examine multiple features simultaneously, and therefore the wide version seems more applicable.    The resulting file will contain averages of averages, and averages of standard deviations.   This is not the same as if we pooled all the data together for one subject and one activity and calculated the mean and standard deviation directly from that.

I have deviated slighly from the instructions becasue I did not like
the format of text file created by write.table
Instead I used the capture.output function to output the print .data.frame to a text file     
By  changing the width and line maximum options we can print out the data in 
a format that is both tidy and visually easy to look at.

Finally, because beyond three digits the data is very likely meaningless I have limited the printout to three significant digits and made the output space delimited to improve readability.  By changing the number of significant digits in the print line at the end of the script, any number of significant digits may be printed.

##Running the Script##

The script is designed assuming that the working directory is where the data file was unzipped.  It will find the subdirectories described above and extract the relevant data perform the two tasks and output the file tidy.txt into the same directory. One needs only to type run_analysis() and it will execute.

 




