# Maze game

- Left, Right, Up, down states
- Flat position as a state
	- Start and end positions
	- When the ball is removed from the maze and goes to flat state
	- Unknown states
- NN output from Directions  to Pitch and roll angles
- Current angles (-2.5<inclination<2.5)

## 1. Motor Control functioning
- Current position(800) and desired position(1000)
- use the ramp(ex.- 200ms) to move from current position to desired position 
- 800 to 1000 position in 200ms 
- So the output from H7 = Direction and Ramp value(in ms) 

## 2. Another motor control approach
- Current position(800) and desired position(1000)
- difference error =  1000- 800 = 200 positions to move
- New difference = diff error * K
- Move the motors to update new difference with ramp value
- K = Proportional constant
- K determines the movement speed from one position to another
- Using lower number of 'K' for lower speed
- So the output from H7 = Direction and K and Ramp value(in ms)



# 2023-06-27
- [STM32MP1 Developer Package - stm32mpu](https://wiki.st.com/stm32mpu/wiki/STM32MP1_Developer_Package)
- honeybee3mm31
