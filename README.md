# Applying Actor-Critic Reinforcement Learning for Optimizing Capacitated Vehicle Routing Problems
This repository contains the implementation of the Actor-Critic reinforcement learning framework applied to the Capacitated Vehicle Routing Problem (CVRP). The project leverages neural networks and attention mechanisms to optimize vehicle routing under capacity constraints.

# Project Structure
The project is organized into the following directories:

  exp: Contains experiment scripts and configurations.
  .ipynb_checkpoints: Jupyter Notebook checkpoints for version control.
  pytorch_models: Contains the PyTorch models used in the project.
  results: Directory for storing the results of the experiments.
  ReinforceAttempt_V1.ipynb: Main Jupyter Notebook containing the implementation and training process.

# Methodology

The methodology involves creating a synthetic dataset, defining the Actor-Critic model architecture, and training the model to optimize vehicle routes. Key components include:

# Dataset
Synthetic CVRP instances with 10 customers and 1 depot.
Randomly generated customer locations and demands.
Vehicles with a capacity of 2 units.

# Model Architecture

This architecture leverages the actor-critic framework, where the actor-network is responsible for making decisions (actions) and the critic network evaluates these decisions to provide feedback. The attention mechanisms embedded in the actor model enhance the ability to focus on relevant parts of the input, improving decision-making accuracy. This integrated approach aims to optimize vehicle routes effectively by learning from interactions with the environment, demonstrating the potential of reinforcement learning in solving complex combinatorial optimization problems like CVRP.
Actor-Critic Model: Embedding layer, RNN layers with attention mechanisms, Softmax layers for action probabilities
Critic Model: Embedding layer, Dense layers for state-action value estimation

![actor-critic](https://github.com/melikecolak/Actor-critic-algorithm-for-CVRP/assets/73293751/56151528-a5ef-4ed0-8da9-a007e69f57cd)


# Training Process
Environment name: "CVRP"
Seed: 0
Start timesteps: 10
Evaluation frequency: 5 timesteps
Max timesteps: 1000
Batch size: 64
Discount factor (gamma): 0.99
Target network update rate (tau): 0.001
Training time: Approximately 9 hours and 17 minutes
# Results
The model achieved a mean distance of 6.421 during evaluation, demonstrating its effectiveness in optimizing vehicle routes. The training process, despite its computational intensity, shows a significant improvement in travel distance reduction compared to traditional methods. 
Above, Figure shows the fluctuation of the average distance traveled by vehicles during different evaluation steps of the training process. Initially, there are significant fluctuations, indicating the model's exploration phase. As training progresses, the average distance stabilizes somewhat, reflecting the model's convergence toward an optimal policy. Despite some variability, the overall trend shows a reduction in average distance, highlighting the effectiveness of the Actor-Critic model in optimizing vehicle routes. The final evaluation reveals a mean distance of 6.421, demonstrating the model's success in minimizing travel distances within the CVRP framework.
![avg](https://github.com/melikecolak/Actor-critic-algorithm-for-CVRP/assets/73293751/42d2af19-b3cf-40d0-b690-c9a2a6bd0c44)

Here, Routes Visualization was shown.
![routes](https://github.com/melikecolak/Actor-critic-algorithm-for-CVRP/assets/73293751/d99323b4-4564-42e0-b6f9-94009c1017f3)

Route 1 (Blue): Connects points in the order [0, 3, 5, 9, 6, 7, 0]. This route forms a loop starting and ending at the depot (point 0), with distances between consecutive points annotated on the lines.
Route 2 (Orange): Connects points in the order [0, 1, 10, 8, 2, 0]. Similarly, it forms a loop starting and ending at the depot, with distances annotated.
Route 3 (Green): Connects points in the order [0, 4, 0]. This is a shorter route visiting just one additional point and returning to the depot.

# Future Work
Minimize model architecture and reduce training time.
Employ hyperparameter optimization techniques.
Test with different customer counts.
Add average path visualizations.
Compare with other actor-critic methods in the literature.
