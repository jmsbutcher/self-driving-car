# self-driving-car
A deep-reinforcement-learning agent (car) that learns to drive across a map while avoiding obstacles

March, 2019

#### Technologies used: Python, Pytorch, Numpy, Kivy

This was one of the guided projects in the first Artificial Intelligence course I took for fun:  
Artificial Intelligence A-Z™: Learn How To Build An AI  
by Hadelin de Ponteves and kirill Eremenko  
https://www.udemy.com/course/artificial-intelligence-az/

A deep neural network takes sensor readings from the car and outputs a steering action.  
The agent receives rewards for moving toward the target and receives penalties for moving away and/or hitting obstacles.  
The network learns using batch reinforcement learning: Data points consist of: 1. a state, 2. the next state, 3. The reward, and 4. The action taken.  
The loss is calculated using Temporal Difference Loss.  
The weights are updated via the Adam optimizer.

The architecture demonstrated in the course was good enough to get the car to learn how to navigate this simple road:

<img src="https://github.com/jmsbutcher/self-driving-car/blob/main/self_driving_car_1.PNG">

<br>

The challenge was to get the car to learn to navigate the very windy road below by changing the network architecture, and/or hyperparameters.  
I was able to achieve this by:
- adding a new layer, 
- increasing the Replay Memory capacity from 100,000 to 1,000,000,
- increasing the memory samples from 100 to 1,000,
- increasing the reward window from 1,000 to 10,000, and
- decreasing the time-cost reward as the car travels from -0.2 to -0.01.

<img src="https://github.com/jmsbutcher/self-driving-car/blob/main/self_driving_car_2.PNG">
