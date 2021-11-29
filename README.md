

#### Project Title

# Go with the Flow (July 2020)
Modeling the flow of fluids in the subsurface is a challenging but essential task for geoscientists. Oil and gas are generated from deeply buried source rocks and then migrate up through the subsurface. Many factors can affect the migration paths of hydrocarbon molecules, such as the characteristics of the rocks (lithology), rock quality, and more.

### Problem Statement
Generate an agent-based model that mimics fluid movement in the subsurface

More details can be find [here](https://xeek.ai/challenges/go-with-the-flow/overview)


## Project structure
├── data\
│   ├── sample_submission.csv\
│   ├── test.csv\
│   └── train.csv\
├── main.ipynb\
├── images\
├── submissions\
└── requirements.txt

### Prerequisites

```bash
pip install -r requirements.txt
```

### Rules for Agents
- To best match the behavior of hydrocarbon molecules, agents must follow these rules:
- Agents move up and sideways in a 3D environment (Figure 1). Agents can move up, sideways, and diagonally. Agents can not move down or diagonally down. The environment contains different values in different arrangements that mimic real world geology.
- Each turn, each agent moves one space. The agent decides which space to move to by adding its move preference array (Figure 2) to the value array of the surrounding environment. The agent then selects the highest value from these summed arrays and moves.
- 10% of the time the agent moves randomly to an adjacent space. See Figure 3 for the move probability matrix.
- Only one agent can exist in a space at any point in time.
- Each turn in the simulation 100 agents are born. 75 agents are born randomly in the bottom layer of the environment (maximum value in the z direction). 25 agents are born in a uniform random distribution throughout the environment.
- Agents die when they reach the top of the environment (minimum value in the z direction). Agents also die if they can’t move during a turn. Dead agents occupy their final space.
- The output for this competition is a CSV file with the x, y, z location of all the agents (alive and dead) at the end of 2,000 turns.


### Overview
- The dataset for this competition was provided in the .npy format.
- This simulation will be run on large volumes so run time efficiency is critical.
- The path of an agent is just as important as its final location. Along with each simulation, a separate NumPy file will be generated that records the location of each agent every turn.

![03_probabilities](images/03_probabilities.png)

### Summary
 
- SIMULATION
- GEOSCIENCE
- AGENT-BASED MODEL
- ipyvolume for 3D visualization
- ipywidgets
