---
title: Models of mobile robots
date: 2019-12-31 16:51:01
tags:
mathjax: true
---
This post includes kinematic and dynamic models of mobile robots.
<!-- more -->
#### Coordinate Transformation
Inertial frame is fixed and usually relative to earth. Body frame is attached to vehicle, origin at the center of gravity or center of rotation. The location of a point $P$ in Body frame.

$$P_E = C_{BE}(\theta)P_B + O_{BE}$$

where $C_{BE}$ refers to the rotation from inertial frame to the body frame.

#### Nonholonomic constrain
It is a a constraint on the rate of change of degree of freedom. Vehicle velocity always tangent to current path, i.e.:
$$\frac{dy}{dx} = tan(\theta) = \frac{sin\theta}{cos\theta}$$
Thus, we derive the nonholonomic constrain:
$$\dot{y}cos\theta = \dot{x}sin\theta$$

#### Two wheeled robot kinematic model
<!-- ![two wheeled robot pic 1](tw_1.png) -->
Kinematic constraint:

$$v_i = rw_i$$

<figure float="center">
<img src="tw_1.png" alt="two wheeled robot pic 1" title="[title]">
<img src="tw_2.png" alt="two wheeled robot pic 2" title="[title]">
</figure>

The velocity is the average of two wheel velocities. ICR refers to instantaneous center of rotation:

$$v = \frac{v_1+ v_2}{2} = \frac{rw_1+rw_2}{2}$$
$$w = \frac{-v_2}{p} = -\frac{v_2-v_1}{2l} =-\frac{rw_2-rw_1}{2l}  $$

Kinematic model in continuous time form:
$$ 
\dot{x} = \frac{rw_1+rw_2}{2} cos\theta\\
\dot{y} = \frac{rw_1+rw_2}{2} sin\theta\\
\dot{\theta} = \frac{rw_1-rw_2}{2l}
$$

Kinematic model in discrete time form:
$$
x_{k+1} = x_{k} + [\frac{rw_{1,k}+rw_{2,k}}{2}cos\theta_k] \Delta t\\
y_{k+1} = y_{k} + [\frac{rw_{1,k}+rw_{2,k}}{2}cos\theta_k] \Delta t\\
\theta_{k+1} = \theta_k + (\frac{rw_{1,k}-rw_{2,k}}{2l})\Delta t
$$