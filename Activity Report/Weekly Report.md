	
- ## Week 5

- ## Week 6
- Familiarized myself with STM32CubeIDE and STM32CubeMX tools for further development.
- Familiarized with PyTorch framework
- setup and configuration of ST corporate proxies to access Conda, pip and other package managers to create environments
- worked on paper reviews and comments for the TinyML submission to submit before deadline
- ## Week 7
- Received Maze solving based on Reinforcement Learning code which Stefano Colella worked on
- studied the codebase for better understanding
- Researched on conversion of PyTorch model to ONNX and tried to solve a problem with PyTorch layers which are not supported by existing ONNX conversion methods
- Uploaded and validated RL maze TfLite model into STM32H747-disco for on device validation.
- Gained access to HMI server to run training session on Maze solving network
- 1 DAY OFF
- ## Week 8
- Worked on the slides to present at TinyML symposium for the paper submitted.
- Validated the RL Maze model with custom inputs and outputs on device with an STM32H747 discovery board.
- Understanding the "STM32_Image Processing Library" from FP-AI-VISION package for future use of this library in the maze demo.
- Meeting
	- The art of science storytelling: how to capture hearts and minds
	- AIST alignment meeting
	- IP awareness : how to protect internal and external innovations

- ## Week 9
- Worked on TinyML symposium presentation final version
- Redesigning of the dummy Maze model to replicate the camera vision, This helps in testing the maze with the machine learning model without compromising the original setup
- Received the maze image capture and positioning code for the discovery board
- Added code block to capture images and save it external storage(microSD) 
- Training: 
	- Data privacy Training
	- InfoSec Awareness course
	- St Code Of Conduct
- Meeting
	- Talk from Bruno Murari and Giuseppe about latest tech in semiconductors and innovations
	- Meeting with Yijun Deng Shenzhen

- ## Week 10 
- Maze Game
	- Solved problem with importing the AI model to the maze code base
	- Solved the problem with reading and casting the Input output of the model in the target.
	- Debugging the response of the model for different position of ball in the maze
	- Added code to show directional arrows next to the ball in the LCD by inferencing with the AI model.
- Italian language class 1hr/day
- Meeting
	- Demo presentation to Rajita D’SOUZA and SRA
	- International Women's Day Webcast - Session 1

- ## Week 11
- Worked on a journal publication to MDPI
- Research on Image transformation of the maze to map the maze to a matrix.
- Getting familiar with OpenCV's perspective transformation function to implement in C

- Training
- Fresher's training for 2 days (16 Hrs)

- ## Week 12
- Development of code to detect the four corners of the maze to use them in performing a normalization (perspective transformation) of the tilted maze image.
- Tested the perspective transformation on images from camera - found high processing and memory load and performed at 0.25 frame/sec, which is extremely low. 
- Development under work for implementation of perspective transformation only on the ball position to make faster inference and other optimizations.
- Meeting & Training
	- Paper Presentation : Track - IV : AI/ML, Embedded and IT
	- DTIT Services Notification >>Session 2-Make sure your data is backed-up on OneDrive!-Save the date!

- ## Week 13
- Sketch a new maze for fabrication to incorporate precise mapping of the maze. This is to solve the problems with maze walls not geometrically matching the maze matrix. Which causes the state of ball to be present in two states. 
- Started developing reinforcement learning model for the new maze size, which has been increased from 15x19 to 27x38.
- Resolving problems with the usage of existing framework and policy, which only supports lower dimensions of inputs.
- Training 
	- Security Basics - EN-OL
	- Quality at ST Awareness - EN-OL
	- Trade Compliance awareness -EN-OL
- Webinar 
	- How to boost your data labeling productivity with ChatGPT & Large Language Models?


- ## Week 14
- Training of the new model which takes a high resolution input is complete. 
- [Solved] problems with the PyTorch code as it stopped learning the game after few episodes of training.
- This new model was converted into TfLite model and tested on device for the inference speed if its tolerable. 
- The inference time was 195ms for a single inference which struggles to track ball when moving fast.
- A new maze size of 13x19 has been sketched to avoid this slow inference and also to avoid the uncertainty of the ball position caused by the incoherent ball diameter size and wall width when viewed from top.
- A new network was trained with the new maze input of 13x19 and being evaluated for inference measurements. 
- Further quantization of the model is under development to improve the inference time.

- ## Week 15
- Trained RL-based models with different topology for the 13x19 maze
- Analyzed the performance measurements and made a comparison table
- Chose the best models and made a Quantization aware training of PyTorch model to compare with the unquantized models. 
- The accuracy of the quantized models are 20 to 25% below the unquantized model.
- Wrote code to support the new best unquantized model to run on the device to perform the inference.
- This new model performs inference at 31 to 33 Frames per second (30 to 33ms inference time).
- Italian Language class - 2hr
- Meetings
	- AIST alignment call
	- SRA communication meeting
	- AI models and techniques for sound anomaly detection in industrial scenarios
	- Goal setting for the year 2023

- ## Week 16
- Working with ISPU examples to understand the workflow
- Research on feature extraction for the new Door knock project based on ISPU
- Analyzing  different statistical feature extraction methods with the help of AlgoBuilder for faster code generation and analyzing them with Unicleo GUI
- Git workshop for version control with Eclipse (STM32Cube IDE)

- ## Week 17
- Development of simple Neural Networks with different topologies and parameters to work with accelerometer data.
- Testing few feature extraction methods with python on Human Activity Recognition dataset (since the door knock dataset has to be collected with the actual setup)
- Italian Language practice: read "Italian with Elisa" book

- 1 DAY OFF

- ## Week 18
- Research and understanding the documentation of "FP-AI-MONITOR2" package for use in ISPU
- Understanding the usage of "NanoEdge AI Studio" tool
- More research on preprocessing and the pipeline for Door knock application. Looking for existing work on similar topics. 
- Italian Language practice: read "Italian with Elisa" book

- 1 DAY OFF

- ## Week 19
- [x] Created a python project which allows to gather different features that can be collected from the sensor data.
- [x] Analyze the features with plots and graphs to obtain good features.
- [x] These different approaches are gathered from the different research papers.
- [x] Configuration and setup of the ISPU with STWINBox for further development.

- [x] goFluent: Italian  1hr


- ## Week 20
- [x] Understanding the ISPUAI toolchain which enables to generate machine learning models for the ISPU. 
- [x] Developed and ran few tiny models to check the support of ISPUAI in translating those models.
- [x] Quantized dense layers are not supported yet.
- [x] Need additional understanding and documentation related to ISPU's AI capability and memory usage.
- [x] Webinar In-sensor monitoring with intelligent MEMS sensors.
- [x] POW - How to for new comers. 
- [x] goFluent: Italian - 4hr 

- ## Week 21
- [x] Experimenting with keras 1D conv models on HAR datasets with multiple classes to help understand the memory usage for different window sizes and inputs. 
- [x] Study on  AutoKeras and StructuredDataClassifier of Autokeras for this specific use case. Since there is no studies in relation to the door knock application.

- [x] Meeting with Lorenzo Gualneira about the ISPUAI toolchain.
- [x] goFluent: Italian - 4hr 
- [x] AIST alignment call 

- ## Week 22
- [x] Setup the environment for ISPU development in the Linux server 
- [x] Created a simple math operation ISPU project using the template provided by X-CUBE-ISPU package
- [x] Generated a simple Neural network code for ISPU using the ISPUAI 2.1.1 toolchain


- [x] Registrazione dei contratti di locazione e di affitto
- [x] AIST alignment call
- [x] goFluent: Italian - 3hr

- ## Week 23
- [x] Mounted the new 3D printed maze layout to the maze game
- [x] Preliminary tests were made with the painted balls in detection and tracking
- [x] Made changes to the code to train the ball's color. Tracking was successful in most illumination conditions (shadows and highlights) 

- [x] goFluent: Italian - 2 hr
- [x] STRED-ISPU based Sensors - TRAINING (2022)

- ## Week 24
- [x] Fixed the PyTorch model (TfLite converted) output of Maze game in H7 board
- [x] Fine tuned the corner detection and perspective transformation code with new colors for corner markers
- [x] Meeting with Giuseppe Caruso for the motor control part of the maze game
- [x] Initial game play with manual movement of the board were passed
- [x] Working on preliminary test with the auto play game mode to understand the motor control and action time required. ✅ 2023-10-19
	- [x] To be Fixed: facing problems with the communication from master to slave. ✅ 2023-10-19

- [x] goFluent: Italian - 2 hr

- ## Week 25
```tasks
filename includes work
done in 2023-W25
```

- ## Week 26
```tasks
filename includes work
done in 2023-W26
```

- ## Week 27
```tasks
filename includes work
done in 2023-W27
```

- ## Week 28
```tasks
filename includes work
done in 2023-W28
```

- ## Week 29
```tasks
filename includes work
done in 2023-W29
```

- ## Week 30
```tasks
filename includes work
done in 2023-W30
```
- ## Week 31
```tasks
filename includes work
done in 2023-W31
```
- ## Week 32
```tasks
filename includes work
done in 2023-W32
```
- ## Week 33
```tasks
filename includes work
done in 2023-W33
```
- ## Week 34
```tasks
filename includes work
done in 2023-W34
```
- ## Week 35
```tasks
filename includes work
done in 2023-W35
```
- ## Week 36
```tasks
filename includes work
done in 2023-W36
```
- ## Week 37
```tasks
filename includes work
done in 2023-W37
```

%%```dataviewjs
dv.taskList(dv.pages('-"Templates"').file.tasks
.where(t => t.completed && !t.text.includes("@frank") &&
!t.text.includes("#task")
))
```%%

