# mouse_biometrics
User identification based on mouse activity fingerprint (mouse dynamics)

Mouse dynamics algorithms interpret the data gathered from a mouse or pointer to build a unique user profile. Mouse dynamics in authentication is essentially being able to validate someone’s identity by the way they use their mouse.

In this project we will analyze mouse event data with the aim to identify the user. 

<h4> Datasets:</h4>

• Train_Mouse.csv: In this dataset, the mouse events data from 20 users are collected.<br>
The mouse events are collected during user interaction with a demo banking application. Each user is asked to do 6 sessions and for each session, the data of mouse events are collected. Each row of the dataset represents a single mouse event and consists of uid (unique identifier for each mouse event), session_id (session identifier), user_id, timestamp, event_type (mouse movement type), screen_x and screen_y (coordinates of the mouse event).<br>
Every row of the mouse event data has an event_type column that shows what kind of mouse event the row represents. However, every row by itself does not represent the entire event, the event if oftentimes represented by multiple events in a row. <br>For example, a drag event is a event_type 4 (drag) followed by an indeterminate amount of event_type’s 2 (move) and ends with a event_type 1 (release).<br><br>
The different event_type’s recorded are: 
- 1 = release
- 2 = move 
- 3 = wheel 
- 4 = drag
- 5 = click

And the different events that can occur are:
- click – one click event_type (5) followed by one release event_type (1)
- move – indeterminate amount of cursor move event_type’s (2)
- drag – one drag event_type (4) followed by indeterminate amount of move event_type’s (2) ending with one release event_type (1) 
- wheel – indeterminate amount of wheel event_type’s (3)

• Test_Mouse.csv: This dataset has the same structure as the Train dataset except that the user_id is not included.
<h4> Objective:</h4>

Determine UserID for each session_id in “Test_Mouse.csv” dataset based on collected mouse events data.

<h4> Content of the notebook:</h4>

We will go through 4 major parts:
- EDA that covers real simulation of the mouse, showing the exact path it took on the screen (space), plus temporal analysis for the user's session time. 
- Feature engineering part during which I derived insights from the X-Y-T and converted them into indicative features like slope, tightness, centers, frequencies, etc.
- Model training, which shows the transformations of the dataset and running the multilayer perceptron classifier (Neural network).
- Evaluation of the model using F1 score and confusion matrix, and introducing cross validation to reduce the over-fitting.
- Generating the users IDs for the Test_mouse.csv file.
- Conclusion and perspectives.

We used <b>Spark</b> for this implementation.

