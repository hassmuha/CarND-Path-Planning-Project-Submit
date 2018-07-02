# CarND-Path-Planning-Project
Self-Driving Car Engineer Nanodegree Program

---
* Source Code can be found [here](https://github.com/hassmuha/CarND-Path-Planning-Project-Submit/tree/master/src)
* Compilation Result ./path_planning can be found [here](https://github.com/hassmuha/CarND-Path-Planning-Project-Submit/tree/master/build)
* Rubic point are discussed below
---
# Compilation
## The code compiles correctly.

Code has been compiled succesfully and compiled code is also uploaded in the repository

# Valid Trajectories
## The car is able to drive at least 4.32 miles without incident..

- Respect the speed limit of 50MPH

- Collision avoidance
When there is car infront perform two steps
1) Try to start following the front car speed
2) Prepare for lane change if acceptable

- Overall there state for the car has been defined
1) Keep Lane : Follow Lane till there is a car infront within a maximum distanc of 30m
2) Lane Change Left : This has preference over Lane Change Right. Check the relative cars location in the left lane, whether or not other cars in the left lane will be having sufficient distance to the our car to avoid collision
3) Lane Change Right : Check the relative cars location in the right lane, whether or not other cars in the right lane will be having sufficient distance to the our car to avoid collision

- Minimize the jerk by not accelerating or deaccelerating more than 8m/s2

- Use of spline for trajectory generation

## The car drives according to the speed limit.
The portion of code which helps to maintain the speed limit is main.cpp:line393-397

## Max Acceleration and Jerk are not Exceeded.
The portion of code which helps to maintain the speed limit is main.cpp:line361,364,381,396

## Car does not have collisions.
This is achieved by start following the front car speed when the distance is within 30 down to 15. Below 15 deaccelerate maximum of 8m/s2. The portion of code can where this is checked is main.cpp:line309-322 and main.cpp:line355-392
## The car stays in its lane, except for the time between changing lanes.
Simple code logic used for trajectory generation based on the waypoints selected at a distance of 30,60,90m away from car current freenet s-coordinate position and also include the some of previous generated trajectory points. This not only give smoothness but also keep the car in the lane.

## The car is able to change lanes
As explained earlier car is able to change the lanes.
