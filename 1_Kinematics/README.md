# Kinematics AKA Manipulation

Conventions:
- Use matrices to solve motion problems instead of solving x's, y's and thetas in equations
- Think of motion in terms of transformations from one frame of reference to the other

# Rotations
The end effector position and orientiation is determined by:
1) Defining frames for each joint (where Z axis of frame = axis of rotation of joint)
2) Computing homogenous transformation matrices (rotation and displacement) from one frame to next
  i) Case 1: To find transformation from the frame of reference of previous frame, multiply matrix to the right
  ii) Case 2: To find transformatino from the global original frame of reference, multiply matrix to the left

Example of code:
```
import numpy.cos as cos
import numpy.sin as sin
import numpy.pi as pi

# degrees
t1 = 0  # theta1
t2 = 0  # theta2

# radians
t1 = float(t1)*pi/180 
t2 = float(t2)*pi/180

# Rotation about the Z-axis
H0_1 = [[cos(t1), -sin(t1), 0],
        [sin(t1),  cos(t1), 0],
        [  0,       0,      1]]
        
# Rotation about the Y-axis
H1_2 = [[cos(t2), -sin(t2), 0],
        [sin(t2),  cos(t2), 0],
        [  0,       0,      1]]
```
