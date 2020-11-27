A 2D-Histogram filter implemented in C++, to help a robot move through a colored cyclical grid. 

#localizer.cpp
Contains the functions `initialize_beliefs`, `sense` and `move`. 
**initialize_beliefs**

The function `initialize_beliefs` initializes a grid of beliefs to a uniform distribution, by taking in a 2D grid map representing the world in terms of color, and returning a normalized 2D grid. 

**move**

The function `move` implements robot motion by updating the beliefs based on the changes in x and y of the robot. It takes in the normalized beliefs as the input and returns an updated 2D grid of beliefs. 

**sense**

The function `sense` implements robot sensing by updating beliefs based on the color of the sensor measurement. As inputs, it takes in the current map represented by color, the robot's beliefs before the measurement, the relative probability (p_hit) that the measurement is correct and the relative probability that the measurement is incorrect(p_miss). It returns the updated beliefs of the robot after the measurement.

#helpers.cpp
Contains helper functions for localizer.cpp
**normalize**
 
The `normalize` functions normalizes a grid of numbers. It takes in a 2D grid of numbers representing the probabilities for each cell and returns a 2D grid where the sum of all the probabilities is one. 

 **blur**
 
The `blur` function spreads the probablity of each over a 3x3 gride of cells, assuming that the world is cyclic (meaning the probability "spills over" from the right edge to the left and from the bottom to the top). Takes in a 2D grid of unnormalized probability and a blurring factor (a number between 0 and 1). Returns a new normalized 2D grid of probabilities.
