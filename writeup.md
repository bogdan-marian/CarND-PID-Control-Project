## Writeup: PID Controller

### Reflection
[image1]: ./output_images/01_camera_calibration.png "Undistorted"

#### Describe the effect each of the P, I, D components had in your implementation

In the PID clas the related PID control class members are
- Kp is the proportional gain. Kp produces an output value that is proportional to the current error value. The higher the absolute value of this term is the staring angles become more violent directly proportional to the error of the center.
- Ki is the integral gain. Ki is in fact related to the fact of an system error that accumulates over time. On our simulator wee can safely assume that the Ki is all the time zero.
- Kd is the derivative gain. The higher the value this term is the system is in practice it files like is delaying applying the correction and it and it also you can observe that the car sears back in to the opposite direction before it reaches the middle of the road.

#### Describe how the final hyperparameters were chosen.
Just by experimenting and making sure that I reduce the intensity between the care angle and the steering angle I managed to settle on 3 different parameters sets
- set1: (kp -0.2, ki 0.0, kd -3.5) -> relatively violent correction. This set corrects very violently the searing but it feels that it is not a very smooth ride for most of the time.
- set2: (kp -0.2, ki 0.0, kd -1.5) -> smooth correction. Comparing to the previous set the car feels much more stable and there is less chance to get a headache while monitoring this car.
- set3: (-0.1, 0.0, -1.5 ) -> The car feels really nice. During a full lap on the tight corners the care touches one the edge of the road but due to the fact that it stabilities quite fast and for the most part of the ride it almost resembles that an actual person steers the car I decided to use this setting for the final project submission
