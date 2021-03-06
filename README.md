# Unscented Kalman Filter Project Solution

Self-Driving Car Engineer Nanodegree Program

This project is second project under Sensor Fusion topic of Term2. The objective of this project is designing Unscented Kalman Filter to estimate the position px, py and velocity vx,vy of the object(bicycle) being tracked by fusing the noisy sensor measurements from LIDAR and RADAR.The implementation is in C++ and uses the starter code provided by udacity(forked).

---

## Repository files structure

* **src**: This folder has source code of the project
     - main.cpp : Modified to extend the list of parameters to be outputted to output file like NIS_radar, NIS_laser,yaw_ang_gt and  yaw_rate_gt.
     - tools.cpp : Implements the function for RMSE calculations.
     - UKF.cpp: Implements the predict function and updation functions for Unscented Kalman Filter fusing the LIDAR and RADAR noisy sensors measurements.
     
* **data**: Has input data obj_pose-laser-radar-synthetic-input.txt
* **results**: Has UKF output file obj_pose-laser-radar-ukf-output.txt, logs and plots.
     
## Results with plots


![](./results/UKF_Meas_GT.png)


To differentiate clearly UKF-estimate line and Ground Truth line plots towards the curve, zoomed and plotted as below:

![](./results/UKF_Meas_GT_Zoom.png)

The Yaw angle and yaw rate estimates are plotted below showing the accuracy in estimation eventhough they are not measured by sensors.

![](./results/UKF_yaw_angle_est.png)

![](./results/UKF_yaw_rate_est.png)

The NIS laser and NIS radar plots are shown below

![](./results/UKF_NIS_laser.png)

![](./results/UKF_NIS_radar.png)


The plots are obtained using Sensor Utilities https://github.com/udacity/CarND-Mercedes-SF-Utilities

The RMSE accuracy obtained as :[px,py,vx,vy] --> [0.0672495, 0.0807008, 0.343781,  0.162614] against the thresholded (mentioned as rubric)[.09, .10, .40, .30]

## Running the code
1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make` 
   * On windows, you may need to run: `cmake .. -G "MinGW Makefiles" && mingw32-make`
4. Run it: `./UnscentedKF ../data/obj_pose-laser-radar-synthetic-input.txt obj_pose-laser-radar-ukf-output.txt > logs.log

## Summary

For the new dataset obj_pose-laser-radar-synthetic-input.txt as input,tuned the process noise parameters std_a_ and std_yawdd_ to improve RMSE accuracy. Further the RMSE is optimized by tuning the initialization of P state covariance matrix and parallely ensuring conditions for NIS for radar and laser.

By using only laser measurements, the RMSE is [0.0949654, 0.0959804, 0.394245,  0.209651]
By using only radar measurements, the RMSE is [0.145199, 0.212919, 0.361528, 0.218052]
The Px,Py estimations are better using LIDAR than only using RADAR as LIDAR is better in position measurement.
The Vx, Vy estimations are better using RADAR than only using LIDAR as RADAR is better in velocity measurement

Compared with EKF using CV results RMSE [px,py,vx,vy]  --> [0.0935411, 0.0848205, 0.310778, 0.423821], the UKF performs better with CTRV motion model.

 













