Data Set Information
 The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

 The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. 

Process
 The script run_analysis.R performs the following process to clean up the data and create tiny data sets:

    Merge the training and test sets to create one data set.

    Reads features.txt and uses only the measurements on the mean and standard deviation for each measurement.

    Reads activity_labels.txt and applies human readable activity names to name the activities in the data set.

    Labels the data set with descriptive names. 

    Merges the features with activity labels and subject IDs.

    The average of each measurement for each activity and each subject is merged to a second data set. The result is saved as tidyData2.txt.
    
Variables
    testData - table contents of test/X_test.txt
    trainData - table contents of train/X_train.txt
    X - Measurement data. Combined data set of the two above variables
    testSub - table contents of test/subject_test.txt
    trainSub - table contents of test/subject_train.txt
    S - Subjects. Combined data set of the two above variables
    testLabel - table contents of test/y_test.txt
    trainLabel - table contents of train/y_train.txt
    Y - Data Labels. Combined data set of the two above variables.
    featuresList - table contents of features.txt
    features - Names of for data columns derived from featuresList
    keepColumns - logical vector of which features to use in tidy data set
    activities - table contents of activity_labels.txt. Human readable
    tidyData - subsetted, human-readable data ready for output according to project description.
    uS - unique subjects from S
    nS - number of unique subjects
    nA - number of activities
    nC - number of columns in tidyData
    td - second tiny data set with average of each variable for each activity and subject


Output
 tidyData2.txt
 tidyData2.txt is a 180x68 data frame.
    The first column contains subject IDs.
    The second column contains activity names.
    The averages for each of the 66 attributes are in columns 3-68.

