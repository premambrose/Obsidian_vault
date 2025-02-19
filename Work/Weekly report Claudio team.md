06/25

- The TFLite model has been effectively tested on the MP2 platform using a maze-solving game, achieving an inference speed of 60-70 milliseconds per inference when running on the CPU. 
- Compilation for GPU or NPU execution is currently on hold due to unresolved OpenVX dependencies, and this is deemed acceptable as the current inference speed meets the application's requirements. 
- For the implementation of the new door knock application, an order has been placed for 4 ISPU nodes. 

07/02

- A new thread has been added to handle AI inference concurrently with motor control, allowing for parallel processing. 
- A semaphore-based mechanism is employed to initiate inference as required, and the game now employs a one-shot strategy to solve the maze, storing the successful path in a vector. 
- This dedicated thread can solve the maze in under 90 milliseconds from any position within the maze, operating solely on the CPU. 
- The objective is to integrate a feature that will highlight the path to the goal on the LCD display. 
- Development is underway for an additional thread that will perform homography transformations. 

07/09

- Testing the MP2 kit camera MB1854 with the MP2 
- Faced some issues in interfacing the Camera with v4l2 API 

07/16

- Maze Game: 
- Interfaced the MP1854 Camera with the MP2 using Gstreamer pipeline method.  
- Having some issues with the color space and conversion to process the sample with OpenCV 
- There's a memory leak and the application stop working, which I'm still working to fix. 
- Did some tests with the Logitech white camera: It works at 30fps with 320x240 resolution only with v4l2 API. 

07/23

o   Replaced the self-written homography transformation with the OpenCV module.

o   Removed the homography transformation thread and incorporated it with the camera thread.

o   Developed a fully virtually simulated gameplay within the camera and AI thread.

o   Implemented a feature that creates a green path to the goal upon placing the ball on the board.

07/30

o   Added SDL integration with OpenCV for video capture and rendering in MPUEC/sdl.cpp.

o   Tested the SDL and OpenCV integration in the application, but it was not working. Further debugging is required to identify and resolve the issues.

o   Performed PID tuning as the system had stopped working as expected. Adjustments were made to the PID parameters to restore optimal performance.

o   Upgraded the OpenST Linux distribution to the latest version 5.1.0, which includes several bug fixes and performance improvements.

o   Added OpenCV to GStreamer display of the game.

o   Removed the old GStreamer pipeline for IMX camera, to be added later.

o   The x-linux-ai package received an update with changes in the TFLite wrapper. The maze game application was ported to support the changes made in the wrapper.

08/*
- Fixed the AI inference by correcting the input in the new TFLite wrapper. Adjusted the wrapper to correctly process the input as an image.
- Added letters to be displayed on the dynamic walls of the maze.
- Implemented dynamic wall control in the maze with six different fixed positions. The walls can be opened and closed using pre-allocated keyboard buttons.

09/*
- Fixing the Ethernet port to support dual Ethernet connections. Both ports are operational, but the EtherCAT protocol malfunctions when both Ethernet ports are connected to the board. 
- Developing support for the Sony MB1854B camera using the GStreamer pipeline approach. 
- Combining the display and camera pipelines in GStreamer for integrated functionality. 
- Helping Giuseppe Caruso to replicate the same. 
- In discussion to obtain a discovery kit for the MP2 or the D version of the eval kit since the HDMI is not functioning with the latest distribution in C version.

10/02
- The state machine for the process and camera threads has been refactored for improved efficiency. 
- A new state machine has been introduced to manage the camera thread based on maze status or game mode. 
- The drawing display code has been refactored into modules, allowing for easy calls based on different game modes. 
- The Ethernet issue has been resolved by upgrading to a newer version of the motherboard. 
- The new hardware setup now has motors placed perpendicular to the plane, with one motor dedicated to pitch control and the other to roll control.

10/15
- Added a warp perspective feature using corner points and creating a ROI in any inclination.
- Implemented auto-calibration of plane inclination and perspective transformation using h_matrix acquisition to ensure precise control and alignment.
- Enabled the real-time display of both the warped and virtual matrices to improve monitoring and debugging.
- Created a real-time maze reconstruction by processing the warped frame, allowing for dynamic visualization of the maze layout.
- Added an option to show either the full path or only the next move, providing flexibility in navigation display.

10/22
- The motors have been reconfigured to pull the plane instead of pushing it. This adjustment reduces the strain on the motors and improves the speed and precision of control. 
- The PID settings have been updated to align with the new motor orientation. These settings have been modified and the motors are calibrated. 
- The process of fine-tuning the PID settings is underway to achieve precise control over the ball's movement, allowing it to stop and move to designated coordinates accurately.