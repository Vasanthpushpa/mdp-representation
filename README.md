# MDP REPRESENTATION

## AIM:

To create a MDP (Markov Decision Process) for the undertaken problem statement

## PROBLEM STATEMENT:

### Problem Description

The problem involves detecting road blockages in a city. The goal is to identify the optimal path for vehicles to take when a road blockage occurs. The environment is modeled as a Markov Decision Process, where states represent road conditions, actions represent possible routes or decisions, and rewards are based on reaching a destination efficiently.

### State Space

The state space consists of all possible road conditions at a given time. Each state represents a specific configuration of roads, including whether they are blocked or clear.

### Sample State

A sample state could be: S = {Road_1: Clear, Road_2: Blocked, Road_3: Clear}

### Action Space

The action space consists of the set of possible actions that a vehicle can take when encountering a blocked road. These actions involve choosing an alternative route or proceeding along the current path.

### Sample Action

A sample action could be: A = {Take Alternate Route}

### Reward Function

The reward function assigns rewards based on the effectiveness of the chosen action in reaching the destination without delay. A higher reward is given for efficient routes, while a penalty is assigned for blocked roads or unnecessary detours.

### Graphical Representation

![WhatsApp Image 2024-09-03 at 19 35 09_f88dc6b0](https://github.com/user-attachments/assets/b4acc3a5-a9f3-4869-b316-064ac800881e)

## PYTHON REPRESENTATION:
![image](https://github.com/user-attachments/assets/4d72ae22-61b2-4b43-af2d-9ea2de93dd3b)


## OUTPUT:
![WhatsApp Image 2024-09-03 at 16 29 12_d8d9045c](https://github.com/user-attachments/assets/d74a89ce-7478-4887-b534-b1610f41021d)


## RESULT:
The MDP simulation successfully detects road blockages and determines optimal actions for avoiding blocked roads. The rewards indicate the efficiency of the chosen routes, helping vehicles reach their destinations while minimizing delays due to road blockages.

