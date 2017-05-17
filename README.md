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
     
## Results with plots


![](./results/UKF_Meas_GT_plot.png)


To differentiate clearly UKF-estimate line and Ground Truth line plots, only those are plotted as below:

![](./results/UKF_GT_plot.png)

The plots are obtained using Sensor Utilities https://github.com/udacity/CarND-Mercedes-SF-Utilities

The RMSE accuracy obtained as :[px,py,vx,vy] --> [0.0672495, 0.0807008, 0.343781,  0.162614] against the thresholded (mentioned as rubric)[.09, .10, .40, .30]

## Running the code
1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make` 
   * On windows, you may need to run: `cmake .. -G "MinGW Makefiles" && migw32-make`
4. Run it: `./UnscentedKF ../data/obj_pose-laser-radar-synthetic-input.txt obj_pose-laser-radar-ukf-output.txt > logs.log

## Summary

For the new dataset obj_pose-laser-radar-synthetic-input.txt as input, the RMSE is optimized by tuning the initialization of P state covariance matrix and parallely ensuring conditions NIS for radar and laser.













