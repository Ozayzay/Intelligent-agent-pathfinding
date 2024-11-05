# Intelligent Vacuum Cleaner Navigation - CMPT 310, Assignment #1

**Course:** CMPT 310, Winter 2024  
**Assignment:** #1 - Search Algorithms for Intelligent Agents

## Project Overview

This project demonstrates the design and implementation of fundamental search algorithms used in Artificial Intelligence (AI) for autonomous navigation within structured environments. The assignment simulates a 2D grid environment with randomly placed dirt and blocked rooms, where an intelligent vacuum agent must navigate to clean efficiently.

The primary objective is to equip the agent with different search strategies to optimize its cleaning path, thus minimizing the steps taken and maximizing its performance. The project provides hands-on experience in implementing classic search algorithms, a critical skill for AI and robotics applications.

## Table of Contents

1. [Environment and Problem Setup](#environment-and-problem-setup)
2. [Implemented Search Algorithms](#implemented-search-algorithms)
3. [Features and Functionalities](#features-and-functionalities)
4. [Turn Cost Implementation](#turn-cost-implementation)
5. [Analysis and Evaluation](#analysis-and-evaluation)
6. [Execution Instructions](#execution-instructions)
7. [Conclusion](#conclusion)

---

## Environment and Problem Setup

The environment consists of:

- **2D Grid**: Represents rooms as a grid layout.
- **Random Dirty Rooms**: Five rooms are randomly designated as “dirty.”
- **Blocked Rooms**: Rooms that are inaccessible to the agent.
- **Agent**: A vacuum starting in the center of the grid, programmed to clean all dirty rooms using various search strategies.

The agent uses search algorithms to determine the optimal path for cleaning, adjusting for potential obstacles and costs associated with movements and turns.

## Implemented Search Algorithms

The project includes implementations of the following search algorithms, each enhancing the agent’s efficiency:

1. **Breadth-First Graph Search (BF Graph)**:
   - Explores the grid level-by-level, ensuring the shortest path to the first dirty room.
2. **Depth-First Graph Search (DF Graph)**:
   - Explores deeply in each branch before backtracking, potentially finding a sub-optimal path but with lower memory requirements.
3. **Uniform Cost Search (UC)**:
   - Selects the lowest-cost path at each step, accounting for movement costs, making it suitable for environments with varied path costs.
4. **Greedy Search**:
   - Uses a heuristic to prioritize rooms closest to the agent, potentially reducing path length but may not guarantee the optimal solution.
5. **A\* Search**:
   - Combines the strengths of Uniform Cost and Greedy searches, leveraging both path cost and heuristics, ensuring optimality in pathfinding while balancing efficiency.

Each algorithm computes the path to the next dirty room and highlights explored areas in **pink** and the path in **orange**.

## Features and Functionalities

- **User-Interactive Interface**:
  - A menu allows the selection of search algorithms.
  - Options to advance the agent manually (step-by-step) or automatically with a 1-second delay per step.
- **Real-Time Updates**:
  - Tracks and displays the total steps taken (green) and overall cost (blue) for each algorithm.
- **Sequential Room Cleaning**:
  - After reaching and cleaning each dirty room, the agent proceeds to the next dirty room using the selected search algorithm until all rooms are clean.

## Turn Cost Implementation

An additional feature, **TurnCost**, introduces a penalty for each 90-degree turn:

- **Cost Calculation**: Each turn incurs a cost equivalent to 50% of a straight move, which is 5 units (based on the 10-unit move cost provided in lectures).
- **Impact on Path Selection**: Enabling **TurnCost** encourages the agent to prioritize paths with fewer turns, impacting the performance across different algorithms and leading to unique exploration patterns.

## Analysis and Evaluation

### Turn-Cost Impact

1. **Impact on Path and Explored Area**:

   - The TurnCost feature alters the agent’s navigation, reducing unnecessary turns and optimizing paths, especially for algorithms like A\* and Uniform Cost.
   - Higher turn penalties encourage straighter, more direct routes, which reduce total steps and costs, making the agent’s behavior more predictable and efficient.

2. **Vertical Movement Penalty**:
   - Hypothetical adjustment to increase vertical movement costs to twice that of horizontal moves:
     - **Implementation**: Update cost functions within the search algorithms to assign higher weights for vertical steps.
     - **Approach Variations**:
       - Modify cost calculations directly within each algorithm, specifically where movement costs are calculated.
       - Use a heuristic function to adjust for directional preferences.
     - **Benefits**: Enhances control over agent behavior in uneven environments.
     - **Drawbacks**: May reduce algorithmic efficiency due to additional calculations.

## Execution Instructions

1. **Setup**: Clone the repository and ensure Python is installed.
2. **Run the Interface**:

   ```bash
   python vacuum_agent.py

   ```

3. **Select Algorithm**: Choose a search algorithm from the menu.
4. **Control Execution**: Use the **‘next’** button to proceed step-by-step or **‘run’** to automate movement.
5. **Enable TurnCost**: Toggle the **TurnCost** button to apply turn penalties.
6. **Observe Output**: Note the real-time feedback on steps, path costs, and explored areas.

## Conclusion

This project demonstrates proficiency in designing and implementing core AI algorithms to solve real-world pathfinding problems. The codebase showcases thoughtful algorithmic selection, efficient pathfinding, and insightful adjustments for cost factors, proving both technical competency and practical problem-solving skills.
