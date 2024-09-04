### MDP Reoresentation

## Problem Statement:
A robot needs to navigate through a warehouse to reach a specific storage location while avoiding obstacles and minimizing time.

## Problem Description:
The warehouse is represented by a grid, with each cell being a state. The robot can move in four directions (up, down, left, right). The goal is to find the optimal path from the robot's starting position to the target storage location.

## MDP Representation:
1. States (S)
Each state represents a specific cell in the warehouse grid. For example, in a 3x3 grid:

S1: (1,1) - Top-left corner
S2: (1,2) - Top-middle
S3: (1,3) - Top-right corner
S4: (2,1) - Middle-left
S5: (2,2) - Middle-center
S6: (2,3) - Middle-right
S7: (3,1) - Bottom-left corner
S8: (3,2) - Bottom-middle
S9: (3,3) - Bottom-right corner (Target storage location)
2. Actions (A)
There are 4 possible actions the robot can take:

A1: Move Up
A2: Move Down
A3: Move Left
A4: Move Right
3. Transition Probabilities (P)
The transition probabilities represent the likelihood of the robot successfully moving to the intended state. There may be obstacles that affect these probabilities.

P(S1, A3, S1) = 1: If the robot tries to move left from the top-left corner, it stays in place since it's at the boundary.
P(S2, A4, S3) = 0.9: The robot successfully moves right with 90% probability; 10% chance of staying in place due to obstacles.
4. Rewards (R)
Rewards encourage reaching the target location quickly while avoiding obstacles.

R(Target State, Any Action) = +10: Reaching the target storage location.
R(Any Other State, Move) = -1: Penalty for each move to encourage the shortest path.
R(Obstacle Collision) = -5: Penalty for hitting an obstacle.
5. Policy (π)
The policy will determine the best action at each state to maximize the robot's reward. The goal is to find the optimal path to the target storage location with the least time and avoiding obstacles.

## Example Transitions:
P(S1, A2, S4) = 1: Moving down from (1,1) leads to (2,1).
P(S4, A4, S5) = 1: Moving right from (2,1) leads to (2,2).
P(S8, A1, S5) = 1: Moving up from (3,2) leads to (2,2).
P(S9, A1, S6) = 1: Moving up from (3,3) leads to (2,3), but this is the target state, so the policy should avoid this action.

## Graphical Representation
![image](https://github.com/user-attachments/assets/cfa80fbc-599c-4de4-8698-8f596b587131)


## PYTHON REPRESENTATION:
import matplotlib.pyplot as plt
import networkx as nx

# Create a directed graph
G = nx.DiGraph()

# Define the states
states = ['S1', 'S2', 'S3', 'S4']

# Add nodes to the graph
G.add_nodes_from(states)

# Define the transitions with probabilities
transitions = [
    ('S1', 'S2', 0.5),  # Entrance to Reception
    ('S2', 'S3', 0.6),  # Reception to Security Room
    ('S3', 'S4', 0.3)   # Security Room to Storage Room
]

# Add edges to the graph with labels as probabilities
for (start, end, prob) in transitions:
    G.add_edge(start, end, weight=prob)

# Define positions for each node (for visualization)
pos = {
    'S1': (0, 1),  # Entrance
    'S2': (1, 1),  # Reception
    'S3': (1, 0),  # Security Room
    'S4': (0, 0)   # Storage Room
}

# Draw the graph
plt.figure(figsize=(8, 6))
nx.draw(G, pos, with_labels=True, node_size=3000, node_color='lightblue', font_size=10, font_weight='bold', arrowsize=20)

# Draw edge labels (probabilities)
edge_labels = {(start, end): f'{prob}' for (start, end, prob) in transitions}
nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_labels, font_size=10)

# Show the plot
plt.title("MDP Representation Based on Provided Diagram")
plt.show()


OUTPUT:
![image](https://github.com/user-attachments/assets/ba6f6e63-a878-4e9a-ba74-f44e519f53c2)


RESULT:
THe project for programming MDP executed Successfully.
