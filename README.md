# Unity Autonomous Navigation with A* Pathfinding

A Unity 3D autonomous vehicle simulation using the A* informed search algorithm to plan and execute efficient routes across a waypoint-based environment.

The agent starts from a base location, travels through multiple navigation nodes, reaches a sequence of goal destinations, and returns as part of delivery-style journey scenarios. The calculated route is visualized in the scene, while blocked paths and route changes are handled dynamically.

## Demo

[Watch Demo Video](https://www.linkedin.com/feed/update/urn:li:activity:7448423871994630144/)

## Screenshot

![Autonomous Vehicle Pathfinding Demo](autonomous-vehicle-demo.png)

## Project Overview

This project was developed for an Intelligent Agents module and demonstrates how an autonomous agent can navigate a simulated environment using graph-based pathfinding.

The waypoint map contains more than 35 nodes. The vehicle performs multiple journeys between start and goal locations, using A* to calculate the shortest available path. The algorithm considers both the travelled cost and a heuristic estimate based on straight-line Euclidean distance.

When the route becomes blocked, the agent does not immediately reroute. Instead, it waits briefly to check whether the path becomes available again. If the blockage remains, the vehicle recalculates a new valid route and continues the journey.

The simulation also includes pedestrian-style obstacle detection. When a pedestrian or moving obstacle is detected in front of the vehicle, the agent stops safely before continuing.

## Features

- Autonomous vehicle navigation in Unity 3D
- A* shortest-path planning
- Waypoint graph with 35+ navigation nodes
- Multiple journey scenarios between start and goal locations
- Delivery-style route execution
- Dynamic route recalculation when roads are blocked
- Temporary waiting behavior before rerouting
- Blocked-path detection and visual feedback
- Pedestrian-style obstacle detection
- Collision handling and adaptive navigation
- Green path visualization for the calculated route
- Red path highlighting for blocked/unavailable routes

## How A* Works in This Project

A* is an informed search algorithm that finds the shortest path between two nodes in a graph.

In this simulation, each waypoint acts as a graph node, and the paths between waypoints act as graph edges. The vehicle uses A* to choose the route with the lowest estimated total cost.

The algorithm combines:

- **G cost** — the travelled cost from the start node to the current node
- **H cost** — the heuristic estimate from the current node to the goal, calculated using straight-line Euclidean distance
- **F cost** — the total estimated cost

```text
F = G + H
```

This allows the vehicle to select efficient routes while still adapting when certain paths become unavailable.

## Dynamic Replanning

The vehicle continuously monitors the route ahead. If a road or path segment becomes blocked, the affected connection is marked as unavailable and highlighted in red.

The agent then waits briefly before recalculating. This delay allows the vehicle to continue on the same route if the blockage clears quickly. If the route remains blocked, the agent excludes that path from the graph and calculates a new route to the goal.

This behavior makes the simulation more realistic because the vehicle does not instantly reroute for temporary obstacles.

## Pedestrian and Obstacle Detection

The simulation includes obstacle detection for pedestrian-style objects. When the vehicle detects an obstacle in front of it, it stops to avoid collision. Once the obstacle is no longer blocking the path, the vehicle continues its journey.

This demonstrates basic autonomous agent behavior, including perception, decision-making, and safe navigation.

## Technologies Used

- Unity 3D
- C#
- A* Pathfinding Algorithm
- Graph Search
- Waypoint Navigation
- Intelligent Agents
- Collision Detection
- Obstacle Detection

## Use Cases

A* pathfinding is commonly used in:

- Autonomous vehicles
- Robotics
- Game AI
- Delivery route planning
- Logistics optimization
- Navigation systems
- Simulation environments

## Key Learning Outcomes

This project demonstrates:

- How graph-based search can be applied to autonomous navigation
- How A* uses cost and heuristic estimates to find efficient routes
- How agents can react to blocked paths
- How route recalculation improves adaptive behavior
- How obstacle detection can support safer navigation
- How Unity can be used to simulate intelligent agent behavior

## Author

Cristian-Marian Pascu

## Demo Link

[LinkedIn Demo Video](https://www.linkedin.com/feed/update/urn:li:activity:7448423871994630144/)
