# Predict Student Performance from Game Play
  This repository holds an attempt to predict whether a future user will answer questions correctly.
  
  https://www.kaggle.com/competitions/predict-student-performance-from-game-play

## Overview
  When given data about the state of the game, along with if the correct answers were given over multiple sessions, the goal was
  to see if it would be possible to predict if the next user would be likely to answer correctly based on the previous sessions data.
  The approach used a gradient boosted trees model testing the correct answers with the different variables given in the dataset. The final result gave
  an average accuracy score of 75% and an F1 score of .67

## Data
  Test.csv - information about the state that the game was in. Some of the columns were not used as they were nebulous, such as whether the game was in. Three categories were also ignored, these being 'fullscreen', 'music' and 'hq'

  This had a size of 26296946 rows by 20 columns. The data was edited to categorize the rows into the level groups that they corresponded with(1-4, 5-12, 13-22). The mean and standard deviations were also grabbed from the numerical data was given. The test data was broken up into 56547 for training and 14139 examples for testing
  
  ![](https://github.com/Mang-Britt/Kaggle-Project/blob/main/files/Screen%20Coord.JPG)
    
  <sub>Comparing all of the standard deviations with the range indices, the greatest differences between groups came from where the mouse was in terms of the size of the room</sub>
  
  Train_Labels.csv - whether the question was answered correctly or incorrectly. This data was altered so that each session could be seen if which answers were answered correctly or incorrectly.
  

## Problem Formulation
  For the dataset there were a total of 13 inputs with the goal output to be to see if how accurately we could predict a new player answering the questions.

  A Gradient Boosted Trees Model was used to test for accuracy, with it being able to use from previous trees to help the current iteration. This was used due to the questions being answered were correct or incorrect would be compared to the rest of the data.

## Training
  Training was done entirely through TensorFlow. Each question went over 5 epochs taking about 15 seconds per question. There was no difficulty testing and the results were used afterwards.

## Performance
  The key metric was accuracy, seeing how accurately the model would be able to predict each question and seeing an average accuracy in the end. The average accuracy was about 75% total, meaning that this model would be able to predict a person about 75% of the time.
  
  ![](https://github.com/Mang-Britt/Kaggle-Project/blob/main/files/Accuracy.JPG)

  Certain questions were given a higher accuracy than others due to certain questions being answered incorrectly at least half the time.

  An importance score was also obtained from the variables, with the Room's ID being given the highest score of a 9 and the std of the y-coordinate being given a 1.

## Conclusions
  The Gradient Boosting Trees model seemed to work in this situation, allowing use to see what a user is more likely to select when it comes to the questions.

### Future Work
  It would be interesting to see if a model similar to this could be used to education, seeing if an optimal testing environment or condition could be found. Another interesting use for this would be to see if this could answer for a similar experience in the game applied to the real world, where after a person works through levels, if it would be possible to predict their answers based of where they were. 
  
# Reproducing results

  You will need to install the following librarys
    1. sklearn
    2. tensorflow and tensorflow_decisions_forest

  Afterwards, download this notebook along with the train.csv and train_labels.csv from the kaggle page [here](https://www.kaggle.com/competitions/predict-student-performance-from-game-play).

  After this is done, all that is needed is to open the notebook and run the cells.
    
  
