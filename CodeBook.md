# Code Book

## Raw data collection
Raw data were obtained from UCI Machine Learning repository. Human Activity Recognition Using Smartphones Data Set was used in particular. The data set was built from experiments carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (walking, walking upstairs, walking downstairs, sitting, standing, laying) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, 3-axial linear acceleration and 3-axial angular velocity were captured. The obtained data set has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.
## Data transformation
The raw data sets are processed with run_analisys.R script to create a tidy data set. The proces of data transformation is described within the R script.

### Merge training and test sets
Test and training data (X_train.txt, X_test.txt), subject ids (subject_train.txt, subject_test.txt) and activity ids (y_train.txt, y_test.txt) are merged to obtain a single data set. Variables are labelled with the names assigned by original collectors (features.txt).

### Extract mean and standard deviation variables
From the merged data set is extracted and intermediate data set with only the values of estimated mean (variables with labels that contain "mean") and standard deviation (variables with labels that contain "std").

### Use descriptive activity names
A new column is added to intermediate data set with the activity description. Activity id column is used to look up descriptions in activity_labels.txt.

### Label variables appropriately
Labels given from the original collectors were changed: to obtain valid R names without parentheses, dashes and commas to obtain more descriptive labels.

### Create a tidy data set
From the intermediate data set is created a final tidy data set where numeric variables are averaged for each activity and each subject.
The tidy data set contains 10299 observations with 81 variables.

## References

1. Human Activity Recognition Using Smartphones Data Set, source: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
2. Activity recognition, source: http://en.wikipedia.org/wiki/Activity_recognition