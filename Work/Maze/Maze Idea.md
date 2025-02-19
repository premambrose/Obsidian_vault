#maze #idea #brainstorm #ST #work

- ## Matrix formation 
	![[Maze structure]]
- ##### Take avg/max of square from pixel to pixel (diagonal) 
	- For Example: (0,0) to (1,1)
	- if num > avg, or max 
	- set label
	- Create a matrix like below with labels
- ### Matrix as input
	[0, 1, 0, 0, 0, 0]
	[0, 1, 0, 1, 1, 0]
	[0, B, 0, 0, 1, 1]
	[0, 1, 1, 0, 0, 0]
	[0, 1, 0, 0, 1, 0]

- ### Labels
	- 0.5 - Rat/Ball
	- 1.0 - Wall
	- 0.0 - Path
	- 0.25 - Exit/Target
- Start_pos = (0,0) in matrix
- End position = (matrix.shape[0], matrix.shape[1])
- Actions 
	- 0 = Left
	- 1 = Up
	- 2 = Right
	- 3 = Down

- use STM32_Image_Processing_Library's (STM32IPL) Edge detector to detect edges and pass to [Hough Transforms]([OpenCV: Hough Line Transform](https://docs.opencv.org/3.4/d9/db0/tutorial_hough_lines.html)) to detect edges and draw lines.Hough is also available in STM32_IPL.
- Hough transform uses a threshold value to detect straight lines.
	- Better threshold value = better detection of straight lines
- #### Image from OpenCV hough transform
	![[Pasted image 20230224133621.png]]
 
- Binary funciton in STM32IPL (request example from Claudio) (Binarize)
- Binarize -> Hough transformation ->then matrix conversion
- Code to capture images from demonstration
- Alignment call on monday with Claudio


- Image size: 320x240
- 320/19 = **16.84** pixels per block in matrix (**x**)
- 240/15 = **16** pixels per block in matrix (**y**)

![[Maze Transformation pipeline.canvas]]




