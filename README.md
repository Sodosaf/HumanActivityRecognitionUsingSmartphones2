## HumanActivityRecognitionUsingSmartphones
Repo for the course project of Coursera's "Getting and Cleaning Data" course

###Project description

The script `run_analysis.R` will work on the "Human Activity Recognition Using Smartphones Data Set" that can be found here:
[data overview](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones#)

If you have not done yet, please download the data and unzip the file:
[download file](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

This ReadMe file will give you an overview over of the data and the functions performed by `run_analysis.R`.

###The raw data and study design

The data comes in 26 seperate *.txt files and some additional information like a `features_info.txt`. The two sub-folders "Inertial Signals" (one for "train" and one for "test") contain raw measured data and will be ignored here. Reason: We have all needed information in the remaining 8 files that are listed below. They contain calculated data based on the "Inertial Signals" and meta-data.

The files that we are using here are:

* "train" folder:
  * subject_train
  * X_train
  * y_train

* "test" folder: 
  * subject_test
  * X_test
  * y_test

* Main folder:
  * activity_labels
  * features

For this study 30 test persons carried a waist-mounted smartphone with embedded inertial sensors. The persons were numbered with 1-30, then randomly divided into two groups, the "train" group and the "test" group (cp. `subject_train.txt` and `subject_test.txt`):

|  test persons "train" |  test persons "test" |
| :-------------------- |:---------------------|
| 1     3     5     6     7     | 2   4   9  10  12    |
| 8   11  14  15  16    | 13  18  20  24       |   
| 17  19  21  22  23    |                      |   
| 25  26  27  28  29    |                      |   
| 30                    |                      |  


The waist-mounted smartphone was used to measure different movement data, usually for each direction in space, while the persons performed different activities. The 6 types of activities are (cp. `activity_labels.txt`):

|  index |  activity           |
| :----- |:--------------------|
| 1      | Walking             |
| 2      | Walking upstairs    |   
| 3      | Walking downstairs  |   
| 4      | Sitting             |   
| 5      | Standing            |  
| 6      | Laying              |

The two files `X_train.txt` and `X_test.test` contain the main data that we are interested in. Each has 561 variables (=columns) with measured and calculated data. See `features_info.txt` for more information about what those variables mean.

`X_train.txt` contains 7352 observations (= rows), `X_test.txt` contains 2947 observations (remember: we have fewer persons in this group).

`y_train.txt` and `y_test.txt` are two seperate files with only one column and 7352 respectively 2947 rows that contains numbers between 1 and 6. Those numbers represent the executed activity for each of the observations according to the table shown above. 

