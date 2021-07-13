# Differential Dynamics With Respect To Kinematic Parameters

A recursive algorithm for differential dynamics with respect to both joint twists and joint states, e.g., for design optimization and unified model identification, implemented in MATLAB. Further, the exact inertial parameters computed from a (water-tight) triangle mesh ("MeshToInertia.m") is also presented. The example code ("example_computation_time.m") mainly demonstrates how to use each functions (dynamics, differential dynamics, mesh inertia, and differential mesh inertia) and measures their computation times. We've validated the derivatives by the fmincon option ['CheckGradients'](https://www.mathworks.com/help/optim/ug/checking-validity-of-gradients-or-jacobians.html#br80a0q).

## Dynamics

The Lie group formulation of Newton-Euler recursive inverse dynamics is implemented in "solveRecursiveDynamics_single.m" and its differential version is in "solveDifferentialDynamics_single.m". It computes body velocities, accelerations and force wrenches (and their derivaties w.r.t. joint twists) of each link.

## Mesh Inertia

"MeshToInertia.m" computes from a triangle mesh the 10-dimensional inertial parameters and its derivatives with respect the vertices that are changed by a design model during the design optimization. "translateInertia.m" differentiates the coordinate transformation (for any rigid body motion) of inertia, which is particularly useful when a link is translated by deformations of its preceeding (parent) links.

## Related Publications:

Jaewoon Kwon, Seunghyun Kim, and Frank C. Park, "A Fast and Reliable Co-Optimization of Robot Design and Motion" (in-progress).

Jaewoon Kwon, Keunjun Choi, and Frank C. Park. "Kinodynamic Model Identification: A Unified Geometric Approach." IEEE Transactions on Robotics (2021).
