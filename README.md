# A* Searching Algorithm

This project implements the A* searching algorithm in C++ using multithreading with the pthread library. The A* algorithm is used to find the shortest path from a source to a destination on a grid. The grid is represented by a 2D array where each cell can either be blocked (impassable) or unblocked (passable).

## Table of Contents
- [Project Structure](#project-structure)
- [Features](#features)
- [Algorithm Overview](#algorithm-overview)
- [Grid Representation](#grid-representation)
- [Multithreading](#multithreading)
- [How to Run](#how-to-run)

## Project Structure

- **main.cpp**: Contains the implementation of the A* algorithm.

## Features

- **A* Algorithm**: The algorithm efficiently finds the shortest path in a grid.
- **Multithreading**: Eight threads are used to explore the possible movements in the grid, speeding up the search process.
- **Customizable Grid**: The grid size and the position of the source and destination can be modified.

## Algorithm Overview

The A* algorithm is a pathfinding algorithm that uses a heuristic to estimate the cost from the current node to the destination. The algorithm explores the node with the lowest cost first. It combines the benefits of both Dijkstra's algorithm and Greedy Best-First Search.

### Heuristic Function
The heuristic function `h(x)` used in this implementation is the Euclidean distance between the current cell and the destination.

### Cost Function
The total cost function `f(x)` is calculated as:

f(X)= g(x) + h(x)

where:
- `g(x)`: The cost of the path from the start node to the current node.
- `h(x)`: The heuristic estimated cost from the current node to the destination.

## Grid Representation

The grid is represented as a 2D array where:
- `1`: Represents a passable (unblocked) cell.
- `0`: Represents an impassable (blocked) cell.
- `S`: The source/start position.
- `D`: The destination/end position.

### Example Grid
1 1 1 1 1 1 1 1 1 1

1 0 0 0 0 0 0 0 1 1

1 0 1 1 1 1 1 0 0 1

0 0 1 0 0 0 0 0 1 1

1 1 1 1 1 0 1 0 0 1

1 0 1 1 1 0 1 1 0 1

1 0 0 0 0 0 0 0 0 1

1 1 1 1 1 1 1 1 1 1

1 1 1 0 0 0 1 0 0 1

## Multithreading

Eight threads are created to handle the movement in eight possible directions:
1. North
2. South
3. East
4. West
5. North-East
6. North-West
7. South-East
8. South-West

Each thread evaluates a possible move and updates the open list with the new cost if the move is valid.

## How to Run

1. Clone the repository to your local machine.
2. Compile the project using a C++ compiler that supports POSIX threads (e.g., g++).
3. Run the compiled program.
