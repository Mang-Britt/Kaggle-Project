# Predict Student Performance from Game Play
  This repository holds an attempt to predict whether a future user will answer questions correctly.
  
  https://www.kaggle.com/competitions/predict-student-performance-from-game-play

# Overview
  When given data about the state of the game, along with if the correct answers were given over multiple sessions, the goal was
  to see if it would be possible to predict if the next user would be likely to answer correctly based on the previous sessions data.
  The approach used a gradient boosted trees model testing the correct answers with the different variables given in the dataset. The final result gave
  an accuracy score of 75% and an F1 score of .67

## Data
  Test.csv - information about the state that the game was in. Some of the columns were not used as they were nebulous, such as whether the game was in.

  This had a size of 26296946 rows by 20 columns. The data was edited to categorize the rows into the level groups that they corresponded with(1-4, 5-12, 13-22). The mean and standard deviations were also grabbed from the numerical data was given. 
  
  
  Train_Labels.csv - whether the question was answered correctly or incorrectly. This data was altered so that each session could be seen if which answers were answered correctly or incorrectly.

  ### Training

  This used a Gradient Boosted Tree Model as it seemed best for prediction type functions.
  Searches led to using TensorFlow to work with the model but later on came to find that one of the tools needed was no longer supported so SciKit was also used.

# Import
  NumPy
  TensorFlow
  SciKit
  
