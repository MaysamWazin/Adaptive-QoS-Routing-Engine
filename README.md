# Adaptive-QoS-Routing-Engine


A desktop-based simulation tool for solving the multi-constraint QoS routing problem using different optimization algorithms.

The application allows you to load a network topology from CSV files, select routing parameters, and compute optimal paths based on delay, reliability, and bandwidth constraints.

# Overview

In real networks, routing decisions are not based on a single metric. This project focuses on finding paths that balance:

Delay (latency)
Reliability
Bandwidth (resource cost)

The system computes a combined cost function and searches for efficient paths under these competing constraints.

# Features
Multi-objective QoS routing (delay, reliability, bandwidth)
Multiple algorithm support:
Genetic Algorithm (GA)
Ant Colony Optimization (ACO)
Q-Learning (Reinforcement Learning)
Demand-aware routing (bandwidth constraints)
Interactive desktop UI (PyQt5)
Real-time graph visualization
Scenario-based routing using CSV datasets
# How it works
Graph Model
Nodes and edges are loaded from CSV files
Each edge includes:
delay
bandwidth
reliability
Each node includes:
processing delay
reliability
# Cost Function

Routing decisions are based on a weighted cost:

Delay (edge + node processing)
Reliability (log-based penalty)
Resource cost (inverse bandwidth)

Weights can be adjusted dynamically from the UI.

# Algorithms
Genetic Algorithm (GA)
Population-based search using crossover and mutation
Uses random-walk path generation (no shortest path bias)
Includes fitness sharing to reduce duplicates
Ant Colony Optimization (ACO)
Probabilistic path construction based on pheromone + heuristic
Uses cost-based heuristic (1 / edge cost)
Includes evaporation and elitist updates
Q-Learning
Reinforcement learning approach
Learns optimal routing policy through episodes
Uses epsilon-greedy exploration
# User Interface

The application provides a GUI where you can:

Select source (S) and destination (D)
Choose routing algorithm
Adjust weight parameters
Set bandwidth demand manually or via scenario
Run the algorithm and visualize the path

The resulting path is highlighted on the network graph.
Input Files

# The system expects three CSV files:

NodeData.csv → node properties
EdgeData.csv → link properties
DemandData.csv → traffic scenarios

All files should use ; as separator.

# Running the Project

Clone the repository:

git clone https://github.com/your-username/adaptive-qos-routing-engine.git
cd adaptive-qos-routing-engine

Install dependencies:

pip install -r requirements.txt

Run the application:

python main.py
Dependencies
Python 3.9+
PyQt5
NetworkX
NumPy
Pandas
Matplotlib
Notes
This is a simulation tool, not a production routing system
No classical shortest-path algorithms (like Dijkstra) are used
Focus is on heuristic and learning-based routing approaches
Project Context

Developed as a Computer Networks course project, with emphasis on:

algorithm design
system integration
interactive visualization
License

MIT License
