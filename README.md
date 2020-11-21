The following R script was written to analyze the data from UCI HAR Dataset as part of the final project in the "Getting and Cleaning Data course" by Johns Hopkins University.



The included R script called run_analysis.R that does the following.

- Merges the training and the test sets to create one data set.
- Extracts only the measurements on the mean and standard deviation for each measurement.
- Uses descriptive activity names to name the activities in the data set
- Appropriately labels the data set with descriptive variable names.
- From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.



The R script was developerd in the following stages:

- Downloads to R ids and descriptions for features being measured in experiment from file features.txt.

- Independently loads complete data for train and test sets.
a. Loads the values from X_train.txt as a dataframe
b. In this dataframe, the column names are updated using features description loaded previously.
c. Activity labels and subjects for measurements are also loaded from files train/y_train.txt and train/subject_train.txt and added to data frame as a separated columns.

- Similar steps are made for test dataset and finally 2 rows of 2 data frames are merged together to form are data frame with complete data

- To extract values required, grep() function was implemented, which finds column names that includes mean and standard deviation. A new data frame with only the necessary columns is created.

- To provide descriptive values for activity labels a new variable "activitylabel" is added to dataset, that is a factor variable with levels mentioned in file activity_labels.txt

- Creates a melted data frame using the activity label and subject tags as IDs, mean values for all variables are calculated and grouped by activity and subject using dcast() function and tidy data frame is created.
