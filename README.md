# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Consider two peers (two boxes in the same unit) which can only accept two similar values (for example 1 and 9).
One of these boxes should take value of 1 and the other value of 9, so none of their other peers (in the same unit)
can have those values.

In other words when two peers can only accept two values, they impose a constraint on all other peers (in the same unit)
not to hold those two values.

The naked twins strategy is particularly useful as it takes advantage of a disadvantageous setup. We have
no clue on how to choose a value for any of the twins, but we know those two values should be eliminated from all other
boxes in the unit. Most of the times elimination of those two values from other boxes in the unit helps us to solve
other units which might in turn help us to come up with the values for the naked twins themselves.

For implementing the naked twins strategy, we go through units and detect twins in each unit. Then
apply the constraint (not having same value as possible twin values) to the boxes in intersection of the twin-boxes
peers.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: The diagonal sudoku adds two more units to the normal sudoku, forcing thatno box on the major diagonals of the sudoku
board should have same number assigned. For example, if A1 has value 1 assigned B2, C3, D4, ... can not have value 1.

In other words, the diagonal sudoku adds the board diagonals as two new units to which the main game constraints needs
to hold - no box with the same value is allowed in a unit.

For implementing the naked twins strategy, we keep everything the same except for adding the major diagonals to the
units list. All the previous constraints now gets applied to diagonals as well.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.