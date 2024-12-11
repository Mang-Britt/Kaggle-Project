# Predict Student Performance from Game Play
  This repository holds an attempt to predict whether a future user will answer questions correctly

# Overview
  When given data about the state of the game, along with if the correct answers were given over multiple sessions, the goal was
  to see if it would be possible to predict if the next user would be likely to answer correctly based on the previous sessions data.
  There were 18 questions total divided into 3 groups

# Data
  Test.csv - information about the state that the game was in. Some of the columns were not used as they were nebulous, such as whether the game was in
  fullscreen, high quality or if the music was on or off.
    Columns
    
    session_id - the ID of the session the event took place in
    index - the index of the event for the session
    elapsed_time - how much time has passed (in milliseconds) between the start of the session and when the event was recorded
    event_name - the name of the event type
    name - the event name (e.g. identifies whether a notebook_click is is opening or closing the notebook)
    level - what level of the game the event occurred in (0 to 22)
    page - the page number of the event (only for notebook-related events)
    room_coor_x - the coordinates of the click in reference to the in-game room (only for click events)
    room_coor_y - the coordinates of the click in reference to the in-game room (only for click events)
    screen_coor_x - the coordinates of the click in reference to the player’s screen (only for click events)
    screen_coor_y - the coordinates of the click in reference to the player’s screen (only for click events)
    hover_duration - how long (in milliseconds) the hover happened for (only for hover events)
    text - the text the player sees during this event
    fqid - the fully qualified ID of the event
    room_fqid - the fully qualified ID of the room the event took place in
    text_fqid - the fully qualified ID of the
    fullscreen - whether the player is in fullscreen mode
    hq - whether the game is in high-quality
    music - whether the game music is on or off
    level_group - which group of levels - and group of questions - this row belongs to (0-4, 5-12, 13-22)

  Train_Labels.csv - whether the question was answered correctly or incorrectly. This data was altered in the notebook so session and question were split so the data could be more easily read through.

  # Training

  This used a Gradient Boosted Tree Model as it seemed best for prediction type functions.
  Searches led to using TensorFlow to work with the model but later on came to find that one of the tools needed was no longer supported so SciKit was also used.
