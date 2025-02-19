1. Control the motor to stay in a precise position
2. Ask, friend of Davide for the ball balancing project using motor control system
3. Replace the motor controller with an NN which keeps the ball in a static position by controlling the motors current
	1. A uniform linear movement of Ball as Claudio suggested
		1. Like a sinusoid wave, when the signal goes high the ball is accelerated to a direction indicated by the network.
		2. When the signal goes down the ball is stopped and made to stay in a position
	2. Like Marco BIANCHESSI suggested by capturing the ball position with camera
		1. error correction of the motor control is made by moving the ball to a known position with a vector of distance and direction
		2. correlate the vector from actual position of the ball to the previous state with the expected vector
		3. Correct the motor control with the difference
		4. Repeat this until the motor control system constructs a lookup table of its own.
		5. (1 - 4) could be done without a neural network
			1. PID
			2. Kalman filter
			3. etc
		6. This can also be made to learn with a Neural network.
4. Playing the game in a very slow rate by setting the max slope of the maze to a small value.
	- Step 1: By playing the game slow, the camera even with slow framerate is able to capture the ball position at any giving state of movement.
	- Step 2: Develop the motor control system to play the game without touching the wall
	- Step 3: Slowly increase the speed of the game play by setting a higher value for max slope.
	- Step 4: Keep increasing until we face a bottleneck
	- Step 5: Replace the maze and walls with a  Maze diagram.
	- Step 6: Further replace the maze diagram with an LCD display which displays the Maze.