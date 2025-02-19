The idea is to predict the amount of tilt to be made to the board to move the ball efficiently to the precise location.

- Future Predict n=5 positions (only the inference * 5 times)
	1. Predict ball at x, y position
	2. Get action
	3. Based on the action shift x or y
	4. For example if action=right
	5. Predict ball at {x,y1;x,y2;x,y3;x,y4}
	6. shift and predict until there is a change in the action
	7. once there is a change: calculate the 'n' predictions made with same action.
- For: 1<n<5
- Tilt at: 15degree<Tilt Angle< 35degree