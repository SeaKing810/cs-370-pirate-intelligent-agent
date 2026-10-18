# CS 370 Portfolio: Pirate Intelligent Agent

**Sean McKenna | Current/Emerging Trends in Computer Science**

This project applies reinforcement learning and neural networks to a treasure-hunt game. The pirate learns to navigate an 8 × 8 maze by interacting with its environment, receiving rewards, and updating its estimates of the value of each action.

## Project Files

- [Project Two Jupyter Notebook](McKenna_Sean_ProjectTwo.ipynb): completed training algorithm, saved results, evaluation, and visualizations.
- [TreasureMaze.py](TreasureMaze.py): supplied maze environment, movement rules, rewards, and game status.
- [GameExperience.py](GameExperience.py): supplied experience replay memory and learning-target calculations.
- [requirements.txt](requirements.txt): dependencies for opening and running the notebook.

## What work did I complete, and what code was provided?

The starter code provided the maze environment, experience replay class, neural network architecture, and helper functions for displaying the maze, playing a game, checking completion, and applying a training update. These pieces established the environment and learning framework. I retained the supplied `TreasureMaze.py` and `GameExperience.py` modules and the network architecture.

My main contribution was completing the `qtrain()` training loop. It selects random starting positions, balances exploration and exploitation with an epsilon-greedy policy, stores transitions, trains on sampled experiences, and periodically synchronizes a target network. I also added an inference adapter for replay, training-progress tracking, evaluation assertions, and route visualizations. Working on these pieces helped me understand how the environment, rewards, replay memory, and neural network work together rather than treating the network as an isolated component.

The saved run met the training success criteria at epoch 482 and reached the treasure from all 50 nonterminal free starting cells during greedy evaluation. The route from the top-left corner took 24 steps, matching a breadth-first-search reference used only after training. These results demonstrate performance on the supplied maze; they do not establish performance on unfamiliar layouts.

## What do computer scientists do, and why does it matter?

Computer scientists turn problems into models, algorithms, and systems that can be tested and improved. Their work includes deciding how to represent information, selecting an appropriate approach, measuring results, and explaining tradeoffs. In this project, representing the maze as states, actions, and rewards allowed an agent to learn a useful behavior through experience. This work matters because computing systems influence how people access information, make decisions, and complete everyday tasks. A solution needs to be reliable and useful to the people who depend on it, as well as technically correct.

## How do I approach a problem as a computer scientist?

I start by defining the goal, constraints, and evidence that would demonstrate success. Then I break the problem into smaller parts, inspect the existing code, and test each part before evaluating the complete system. For the pirate agent, that meant understanding the movement rules and reward structure before implementing the learning loop. I learned to separate training progress from final evaluation: a strong recent win rate is encouraging, but checking every valid starting position provides stronger evidence. I also use simple reference methods when they help assess a more complex solution, such as comparing the learned route with breadth-first search. This approach encourages me to investigate failures, revise assumptions, and support conclusions with results.

## What are my ethical responsibilities to the end user and the organization?

My responsibility to end users is to build systems that are dependable, protect their information, and avoid preventable harm. That includes considering accessibility, checking for unfair outcomes, and communicating limitations clearly. My responsibility to the organization includes protecting data, respecting intellectual property, documenting decisions, and reporting results honestly so others can maintain the system and make informed decisions. The pirate project reinforced that a system follows the incentives and information it receives, so reward design and evaluation choices deserve careful attention. I should not claim that success in one maze proves broader reliability. In a real application, I would also evaluate likely failure cases, monitor behavior after deployment, and provide appropriate human oversight.

## Running the Notebook

Use Python 3.12 in a virtual environment. Install the dependencies with `python -m pip install -r requirements.txt`, then launch JupyterLab with `jupyter lab`. Keep the notebook and both Python modules in the same folder, open the notebook, and select **Restart Kernel and Run All Cells**.

The notebook includes saved outputs for review without rerunning training. A fresh run can finish at a different epoch depending on the environment; the final assertions check whether the trained agent meets the success criteria.
