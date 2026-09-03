# CubeSat Attitude Control and Orbital Dynamics

## Overview
This project models a simplified CubeSat attitude-control system and a two-body Low Earth Orbit using MATLAB and Simulink.

The project has two main parts:
1. Single-axis spacecraft attitude control using a PD controller in Simulink.
2. Numerical propagation of a 500 km circular Low Earth Orbit using MATLAB.

## Attitude Control
The spacecraft begins 30 degrees away from its commanded attitude.

The Simulink model includes:
- Rigid-body rotational dynamics
- Closed-loop PD control
- Actuator torque saturation
- Attitude and angular-rate feedback

Baseline controller gains:
- Kp = 0.0067
- Kd = 0.0107

Actuator torque limit:
- +/- 0.002 N m

Baseline results:
- Final pointing error: 0.0000 deg
- Maximum angular velocity: 12.6173 deg/s
- Maximum control torque: 0.002000 N m
- Settling time within +/- 0.5 deg: 4.016 s

## Controller Tuning
Three proportional-gain values were tested while keeping Kd fixed.

| Kp | Final Error (deg) | Max Angular Velocity (deg/s) | Max Torque (N m) | Settling Time (s) |
|---|---:|---:|---:|---:|
| 0.0030 | 0.0303 | 6.5351 | 0.001571 | 12.533 |
| 0.0067 | 0.0000 | 12.6173 | 0.002000 | 4.016 |
| 0.0120 | 0.0000 | 18.3772 | 0.002000 | 4.890 |

The baseline gain Kp = 0.0067 provided the best settling-time performance of the three tested cases while maintaining stable closed-loop behaviour.

## Orbital Dynamics
A CubeSat was modelled in a 500 km circular Low Earth Orbit.

Analytical results:
- Orbital altitude: 500 km
- Circular orbital velocity: 7.617 km/s
- Orbital period: 94.47 minutes

The orbit was propagated using MATLAB ode45 and the two-body gravitational equation of motion.

Numerical validation:
- Minimum altitude: 500.000 km
- Maximum altitude: 500.000 km
- Altitude variation: 0.000 km to displayed precision

## Tools
- MATLAB
- Simulink
- ode45 numerical integration

## Project Structure
```text
CubeSat_Project/
├── attitude_control/
├── orbital_dynamics/
├── results/
└── README.md