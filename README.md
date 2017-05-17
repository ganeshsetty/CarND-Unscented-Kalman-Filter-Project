# Unscented Kalman Filter Project Solution

Self-Driving Car Engineer Nanodegree Program

This project is second project under Sensor Fusion topic of Term2. The objective of this project is designing Unscented Kalman Filter to estimate the position px, py and velocity vx,vy of the object(bicycle) being tracked by fusing the noisy sensor measurements from LIDAR and RADAR.The implementation is in C++ and uses the starter code provided by udacity(forked).

---

## Repository files structure

* **src**: This folder has source code of the project
     - main.cpp : Modified to extend the list of parameters to be outputted to output file like NIS_radar, NIS_laser,yaw_ang_gt and  yaw_rate_gt.
     - tools.cpp : Implements the function for RMSE calculations.
     - UKF.cpp: Implements the predict function and updation functions(LIDAR standard KF and RADAR Extended KF)
     
* **data**: Has input data obj_pose-laser-radar-synthetic-input.txt
* **results**: Has UKF output file obj_pose-laser-radar-UKF-output.txt, logs and plots.
     


## Dependencies

* cmake >= v3.5
* make >= v4.1
* gcc/g++ >= v5.4

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./UnscentedKF path/to/input.txt path/to/output.txt`. You can find
   some sample inputs in 'data/'.
    - eg. `./UnscentedKF ../data/obj_pose-laser-radar-synthetic-input.txt`

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)

## Code Style

Please stick to [Google's C++ style guide](https://google.github.io/styleguide/cppguide.html) as much as possible.

## Generating Additional Data

This is optional!

If you'd like to generate your own radar and lidar data, see the
[utilities repo](https://github.com/udacity/CarND-Mercedes-SF-Utilities) for
Matlab scripts that can generate additional data.

## Project Instructions and Rubric

This information is only accessible by people who are already enrolled in Term 2
of CarND. If you are enrolled, see [the project page](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/c3eb3583-17b2-4d83-abf7-d852ae1b9fff/concepts/f437b8b0-f2d8-43b0-9662-72ac4e4029c1)
for instructions and the project rubric.
