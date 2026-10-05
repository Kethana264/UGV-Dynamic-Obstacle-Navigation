# UGV-Dynamic-Obstacle-Navigation
UGV navigation in a dynamic obstacle environment using replanning.
In this study, dynamic obstacles are simulated by means of replanning for navigation in UGVs.

## Objective

The goal of this project is to design and build an Unmanned Ground Vehicle (UGV) to travel from an arbitrarily specified start point to a specified goal point in an environment where the obstacles are not totally known in advance and may be dynamic.

In contrast to static obstacle problem, the UGV is able to find new obstacles as it navigates and re-plans its path as needed.

## Problem Setup

- Grid size: 70 × 70 km
- Start position: (0, 0)
- Goal position: (69, 69)
Initial barriers: These are known from the outset
Dynamic obstacles: Hidden at the start, found as part of the walking process
- Detection range is 2 grid cells.

## Navigation Approach

A replanning based A* approach is adopted.

The UGV can be said to execute the following activities:

The UGV is given a partial map of the environment.
2. A* search finds a path from the current position to the goal.
3. The UGV follows the calculated trajectory.
The UGV is able to detect new or unknown obstacles.
5. When an unseen object is detected in the way, the UGV will update its map.
The UGV will repeat the sequence starting from where it currently is.
This process is repeated until the UGV has reached the goal or there is no possible path.

## A* Evaluation Function

The A* algorithm can be used for:

f(n) = g(n) + h(n)

where:

The actual cost from the start to the node at level n is `g(n)`.The cost from the start to the node at level n is `g(n)`.
- h(n) = estimated cost from the node n to the goal
- f(n) = total estimated path cost.

Euclidean distance is used as the heuristic.

## Dynamic Obstacles

The dynamically generated obstacles are generated independently of the initially known obstacles.

The UGV has only partial knowledge of the full dynamic obstacle map. Obstacles are shown if they are in the UGV's detection range.

This scenario is a realistic one, as the environment may change as the vehicle is moving.

## Replanning

If a new obstacle is detected when the robot is at a certain location, the UGV replans from that location.

This gives UGV the ability to change its route rather than take on a path that is unsafe.

## Measures of Effectiveness

The following measures are noted:

Total Distance: The total distance that has been covered by the UGV.
The 2nd command is the number of replans that the UGV will perform.
3. Nodes Expanded – Number of nodes visited in path planning.
Execution Time: the time needed to perform a computation for navigation.
5. Success – UGV's ability to arrive at the goal.

## Technologies Used

- Python
- Google Colab
- NumPy
- Matplotlib
- Heap-based Priority Queue
- A* Search


## Conclusion

The project illustrates the ability of the UGV to move in a space with moving and initially unknown obstacles.

The UGV does not follow a fixed trajectory, but learns the environment and replans its trajectory as necessary when new obstacles are encountered.

This way, the UGV is capable of navigating adaptively and can still move toward the goal even if the environment changes while the UGV is moving.
