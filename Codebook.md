The overall project was obtained at the following link:
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The subset of data that was used for this project is located on the following link:
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Accessed plyr pasckage, using require()

Used paste() to convert the below files (via as.character) to character strings, and concatenates them, including the sep "", meaning space delimited.
 features.txt
 activity_labels.txt
 X_train.txt
 y_train.txt
 subject_train.txt
 X_test.txt
 y_test.txt
 subject_test.txt

Used read.table() to read the above Features, Activity, Training, Testing and Subject files

Data transformation
The raw data was processed with run_analisys.R, to create a tidy data set

Merge the training and the test sets to create one data set
Used rbind() and cbind() to merge below data frames.
 *Training data x_train, subject_train, y_train
 *Test data x_test, subject_test, y_test
 *Subject IDs  training_sensor_data, test_sensor_data

Extract the measurements on mean and standard deviation
From the merged data set, used grepl() to extract mean and standard deviations.

Use descriptive names to rename the activities in the data set 
Using join() and names(), the activity names were changed to more descriptive names and also to conform the R Standards.

Create second tidy data set with the average of each variable for each activity.
From the merged data, used numcolwise(mean)) and write.table() to create tidy data set with averages.

Tidy data set
10299 obs. of 81 variables:

Activity labels: 
. WALKING
.	WALKING_UPSTAIRS
.	WALKING_DOWNSTAIRS
.	SITTING
.	STANDING
.	LAYING

Variables Names:
 [1] "Subject"                                                               
 [2] "Activity"                                                              
 [3] "TimeDomain.BodyAcceleration.Mean.X"                                    
 [4] "TimeDomain.BodyAcceleration.Mean.Y"                                    
 [5] "TimeDomain.BodyAcceleration.Mean.Z"                                    
 [6] "TimeDomain.BodyAcceleration.StandardDeviation.X"                       
 [7] "TimeDomain.BodyAcceleration.StandardDeviation.Y"                       
 [8] "TimeDomain.BodyAcceleration.StandardDeviation.Z"                       
 [9] "TimeDomain.GravityAcceleration.Mean.X"                                 
[10] "TimeDomain.GravityAcceleration.Mean.Y"                                 
[11] "TimeDomain.GravityAcceleration.Mean.Z"                                 
[12] "TimeDomain.GravityAcceleration.StandardDeviation.X"                    
[13] "TimeDomain.GravityAcceleration.StandardDeviation.Y"                    
[14] "TimeDomain.GravityAcceleration.StandardDeviation.Z"                    
[15] "TimeDomain.BodyAccelerationJerk.Mean.X"                                
[16] "TimeDomain.BodyAccelerationJerk.Mean.Y"                                
[17] "TimeDomain.BodyAccelerationJerk.Mean.Z"                                
[18] "TimeDomain.BodyAccelerationJerk.StandardDeviation.X"                   
[19] "TimeDomain.BodyAccelerationJerk.StandardDeviation.Y"                   
[20] "TimeDomain.BodyAccelerationJerk.StandardDeviation.Z"                   
[21] "TimeDomain.BodyAngularSpeed.Mean.X"                                    
[22] "TimeDomain.BodyAngularSpeed.Mean.Y"                                    
[23] "TimeDomain.BodyAngularSpeed.Mean.Z"                                    
[24] "TimeDomain.BodyAngularSpeed.StandardDeviation.X"                       
[25] "TimeDomain.BodyAngularSpeed.StandardDeviation.Y"                       
[26] "TimeDomain.BodyAngularSpeed.StandardDeviation.Z"                       
[27] "TimeDomain.BodyAngularAcceleration.Mean.X"                             
[28] "TimeDomain.BodyAngularAcceleration.Mean.Y"                             
[29] "TimeDomain.BodyAngularAcceleration.Mean.Z"                             
[30] "TimeDomain.BodyAngularAcceleration.StandardDeviation.X"                
[31] "TimeDomain.BodyAngularAcceleration.StandardDeviation.Y"                
[32] "TimeDomain.BodyAngularAcceleration.StandardDeviation.Z"                
[33] "TimeDomain.BodyAccelerationMagnitude.Mean"                             
[34] "TimeDomain.BodyAccelerationMagnitude.StandardDeviation"                
[35] "TimeDomain.GravityAccelerationMagnitude.Mean"                          
[36] "TimeDomain.GravityAccelerationMagnitude.StandardDeviation"             
[37] "TimeDomain.BodyAccelerationJerkMagnitude.Mean"                         
[38] "TimeDomain.BodyAccelerationJerkMagnitude.StandardDeviation"            
[39] "TimeDomain.BodyAngularSpeedMagnitude.Mean"                             
[40] "TimeDomain.BodyAngularSpeedMagnitude.StandardDeviation"                
[41] "TimeDomain.BodyAngularAccelerationMagnitude.Mean"                      
[42] "TimeDomain.BodyAngularAccelerationMagnitude.StandardDeviation"         
[43] "FrequencyDomain.BodyAcceleration.Mean.X"                               
[44] "FrequencyDomain.BodyAcceleration.Mean.Y"                               
[45] "FrequencyDomain.BodyAcceleration.Mean.Z"                               
[46] "FrequencyDomain.BodyAcceleration.StandardDeviation.X"                  
[47] "FrequencyDomain.BodyAcceleration.StandardDeviation.Y"                  
[48] "FrequencyDomain.BodyAcceleration.StandardDeviation.Z"                  
[49] "FrequencyDomain.BodyAcceleration.MeanFrequency.X"                      
[50] "FrequencyDomain.BodyAcceleration.MeanFrequency.Y"                      
[51] "FrequencyDomain.BodyAcceleration.MeanFrequency.Z"                      
[52] "FrequencyDomain.BodyAccelerationJerk.Mean.X"                           
[53] "FrequencyDomain.BodyAccelerationJerk.Mean.Y"                           
[54] "FrequencyDomain.BodyAccelerationJerk.Mean.Z"                           
[55] "FrequencyDomain.BodyAccelerationJerk.StandardDeviation.X"              
[56] "FrequencyDomain.BodyAccelerationJerk.StandardDeviation.Y"              
[57] "FrequencyDomain.BodyAccelerationJerk.StandardDeviation.Z"              
[58] "FrequencyDomain.BodyAccelerationJerk.MeanFrequency.X"                  
[59] "FrequencyDomain.BodyAccelerationJerk.MeanFrequency.Y"                  
[60] "FrequencyDomain.BodyAccelerationJerk.MeanFrequency.Z"                  
[61] "FrequencyDomain.BodyAngularSpeed.Mean.X"                               
[62] "FrequencyDomain.BodyAngularSpeed.Mean.Y"                               
[63] "FrequencyDomain.BodyAngularSpeed.Mean.Z"                               
[64] "FrequencyDomain.BodyAngularSpeed.StandardDeviation.X"                  
[65] "FrequencyDomain.BodyAngularSpeed.StandardDeviation.Y"                  
[66] "FrequencyDomain.BodyAngularSpeed.StandardDeviation.Z"                  
[67] "FrequencyDomain.BodyAngularSpeed.MeanFrequency.X"                      
[68] "FrequencyDomain.BodyAngularSpeed.MeanFrequency.Y"                      
[69] "FrequencyDomain.BodyAngularSpeed.MeanFrequency.Z"                      
[70] "FrequencyDomain.BodyAccelerationMagnitude.Mean"                        
[71] "FrequencyDomain.BodyAccelerationMagnitude.StandardDeviation"           
[72] "FrequencyDomain.BodyAccelerationMagnitude.MeanFrequency"               
[73] "FrequencyDomain.BodyBodyAccelerationJerkMagnitude.Mean"                
[74] "FrequencyDomain.BodyBodyAccelerationJerkMagnitude.StandardDeviation"   
[75] "FrequencyDomain.BodyBodyAccelerationJerkMagnitude.MeanFrequency"       
[76] "FrequencyDomain.BodyBodyAngularSpeedMagnitude.Mean"                    
[77] "FrequencyDomain.BodyBodyAngularSpeedMagnitude.StandardDeviation"       
[78] "FrequencyDomain.BodyBodyAngularSpeedMagnitude.MeanFrequency"           
[79] "FrequencyDomain.BodyBodyAngularAccelerationMagnitude.Mean"             
[80] "FrequencyDomain.BodyBodyAngularAccelerationMagnitude.StandardDeviation"
[81] "FrequencyDomain.BodyBodyAngularAccelerationMagnitude.MeanFrequency"    
> 