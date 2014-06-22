Getting-and-Cleaning-Data-Project
=================================
The run_Analysis.R works by first reading the test an train files, merging them in a single file with the name "x" or "y" ################################################################################
################################################################################
## Course Project
## Download file

fileURL1 <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip" 
if(!file.exists("./data")) {dir.create("data")}
download.file(fileURL1, "./data/HARS.zip")

## Unzip content
unzip(zipfile = "data/HARS.zip")

## Read and bind x sets
x_test <- read.table("UCI HAR Dataset/test/X_test.txt", header = F, nrow= 2947)
x_train <- read.table("UCI HAR Dataset/train/X_train.txt", header = F)

x <- rbind(x_test, x_train)

## The features.txt file contains the features for the 561 long vetors in x_test

features <- read.table("UCI HAR Dataset/features.txt")
features.name <- make.names(features$V2)


## Give features to test data

colnames(x) <- features.name

## Read and bind labels
y_test <- read.table("UCI HAR Dataset/test/y_test.txt", nrows = 2947)
y_train <- read.table("UCI HAR Dataset/train/y_train.txt")

y <- rbind(y_test, y_train)

## Read and bind Subject ID's

ID_test <- read.table("UCI HAR Dataset/test/subject_test.txt", nrows = 2947)
ID_train <- read.table("UCI HAR Dataset/train/subject_train.txt")

ID <- rbind(ID_test, ID_train)

x[,562] <- as.factor(ID$V1)

colnames(x)[562] <- "ID"


## Append the y_test to the x_test as a factor with lables obtained from 
## activity_labels.txt

activity_labels <- read.table("UCI HAR Dataset/activity_labels.txt",
                              stringsAsFactors = F)

y_labels <- factor(x = y$V1, labels = activity_labels$V2)

x[563] <- y_labels

colnames(x)[563] <- "Activity"

## Only std() and mean() features

mean_features <- grep(pattern = "(?:mean)",x = features$V2)
std_features <- grep(pattern = "(?:std)",x = features$V2)
x_ms <- x[, c(sort(append(std_features,mean_features)), 562, 563)]

## Calculate the mean by ID and Activity and store in a new "tidy" data frame which will be stored in a tidy.txt file 

tidy <- aggregate(x = x_ms, by = list(x$Activity, x$ID), FUN = mean)
tidy <- tidy[, 1:81]
write.table(x = tidy, file = "tidy.txt", sep = "\t", row.names = T)


