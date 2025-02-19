
# Maze game 3.0
1. Develop the motor control system to stabilize ball in position before Q2.
2. Develop a new application which enables to detect dynamic walls and re-route the gameplay before the end of Q2.
3. Development of multi-step inference for smooth gameplay and to overcome the latency delay problem before the end of Q3.
4. Perform a feasibility analysis to understand the gameplay without walls before the end of Q3.

# Door Knock Application
1. Collect, clean and annotate a wide variety of door knock data from up to at least 10 different doors by Q3.
2. Prepare a documentation/report which explains the dataset collection by Q3.
3. Develop a Neural Network for ISPU with more classes to detect pattens in door knock by the end of Q4.
4. Prepare a detailed report which documents the architecture and preprocessing methods used in (3) by the end of Q4.

# Technical Research on AI
1. Prepare reports and presentations for two patent proposals on the objective "Door knock application" by Q3.
2. Write a paper to be published in a conference/journal by Q3.
3. Prepare a report about the research and evaluation of the possibility to use N6 acceleration NPU to perform data preprocessing by Q4.
4. Review papers on generative AI topic to gain in-depth knowledge and make a report by the end of Q4.

# Bold Leadership - Communicating with Conviction
1. Complete A1 Italian Course before Q4 with a certification from the GoFluent or any other platform.
2. Prepare a technical presentation on the Maze game/Door Knock (or both) application in Italian

# Smart Thinking - Developing Expertise
1. Complete two technical courses from online platforms like LinkedIn learn, Coursera, etc. One before June and one before December.
2. Read and summarize three books or articles related to my area of expertise one each Quarter year.


# Maze game
- [x]  Motor Control to stabilize the ball at a given position
- [x]  Gameplay without walls
    - [x]  To play the game without any walls by moving the balls to an instructed position on a flat plane.
- [x]  Move the ball to a path position after dropping it randomly.
    - [x]  Add the feature to move the ball to the nearest path position in the maze when randomly dropped into the playable area
- [x]  Initialize the ROI with the corners as reference.
    - [x]  Display the reference corners in the LCD panel only during the initialization.
- [x]  X-linux-AI
    - To do the inference directly on the MPU which is supported by the X-linux-AI.
    - Should import the project to do the inference with the tflite wrapper
- [x]  Multistep Inference and reduce latency
    - To do multiple inference at a time to n positions until a change in direction is observed
    - To reduce the latency of the gameplay by optimizing the game with the incorporation of the Multistep inference
- [x]  Dynamic Walls
    - Interface the LCD panel with the MPU board to display the maze layout.
    - To create an application which helps to change the maze layout by adding random walls or user defined walls at given 5 positions.
    - Test the dynamic rerouting of the ball in the maze game.

# Door Knock Application
- Collect the hardware to setup
    - [ ]  2 ISPU in a single I2C bus (discuss on wednesday)
    - [ ]  SPI more than 2 devices
    - [ ]  2 STwin.Box
    - [ ]  2 SDCard
    - Check the Thesis
        - ODR 75Hz
        - Resync time every 1sec
        - Loss high when ODR is 100Hz and When n devices > 2
        - Data Transmitted: IMU (accelerometer, gyroscope, magnetometer), pressure, humidity and temperature sensors
    - [x]  Check the PhD thesis from Davide Aliprandi
    - [x]  BLE/Radio Clock sync
    - [x]  Check for BLE STM32 clock sync in internet
-  [Distributed learning](https://www.notion.so/Distributed-learning-b8265a608df44f12a9b42c755d09022e?pvs=21)
- Data Parallelism: Distributed Learning
    - **Each worker node contains a copy of the model, and each one trains the model using a different subset of the data.**
- Trilateration Algorithm
- [Find X location using 3 known (X,Y) location using trilateration](https://math.stackexchange.com/questions/884807/find-x-location-using-3-known-x-y-location-using-trilateration#:~:text=Use%20the%20distance%20equation.%20If%20your%20unknown%20point%20is%20$(x,y)$,)
- [Trilateration with 3 acceleromters](https://forum.arduino.cc/t/trilateration-with-3-acceleromters/152762/4)
- [ ]  Study the sensors and placement
    - To understand the number of sensors to be placed and the interface between them
    - Position of the sensors and arrangement
    - Do initial test on a single door to understand the data
- [ ]  New Dataset
    - Collect a new dataset of knock performed on 10 different doors.
    - The knocks must be a pattern of knock on the door.
        - Like a passcode by positioning the knocks on different parts of the door
- [ ]  Demo setup at F13
    - To setup the existing Vespucci demo permanently in F13, Agrate.
- [ ]  Documentation for Dataset
    - To create a detailed documentation of the data collected and the configuration of sensors which helps to reproduce the same with ease.
- [ ]  Pattern detection algorithm
    - Create a preprocessing algorithm to smartly process larger windows of data to recognize the pattern within the limitations of ISPU.
    - To develop an algorithm which is able to detect patterns from the knock.
    - Optimize the network and the algorithm to run on the ISPU.
- [ ]  Report on the work
    - Write a detailed report on the work done as a paper or for a journal publication.
- [ ]  Fine tuning/ on-device learning
    - Study about the fine tuning of the model on-device which helps in personalizing the passcode for each user without retraining from scratch.
   
# Technical Research and AI
- [ ]  Patent
    - [x]  Prepare a ppt for the first patent submission
    - [ ]  Prepare a report and draft PPT for submission
- [ ]  Study the federated learning and create a report or document which summarizes the study
- [ ]  Research on the topic of Transformers and LLM at edge
# Smart Thinking
- [x]  Solid works/ Coursera Online course
- [x]  Another Online course
- [x]  Article/Book 1 for Q2
- [ ]  Article/Book 2 for Q3
- [ ]  Article/Book 3 for Q4
# Bold leadership and Communication
- [ ]  Complete A1 in Italian
- [ ]  Prepare a presentation in Italian