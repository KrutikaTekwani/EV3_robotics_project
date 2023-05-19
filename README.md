# EV3 Robot Writing Project

## Overview

This project utilizes an EV3 Robot to perform writing or drawing actions. A pen is attached to the robot, and it moves in a predetermined path to create letters and words on a surface. The Python script defines the robot’s actions, dictating the movement and pen position (up or down).

## Getting Started

## EV3 Installation Resources

The project uses the EV3 Robot by Lego. If you're setting up your EV3 Robot for the first time, or if you're encountering issues with your EV3 Robot, the following resource might be helpful:

- [Python EV3Dev Documentation](https://ev3dev-lang.readthedocs.io/projects/python-ev3dev/en/stable/)

### Prerequisites

- EV3 Robot Set
- Small elastic bands (2.4cm diameter recommended)
- Bullet tip marker pen
- Python development environment 

### Robot Setup

1. Fix the pen on the robot using the elastic bands, ensuring it is carefully centered. The tension from the bands should secure the pen in place.
2. Use the `adjust_cam.py` script to correctly position the cam in the upward position when the drawing script starts.

## Writing with the Robot

The robot writes using a grid-based system. The paths for each letter are defined as a sequence of nodes on a 2x4 grid. Each node in a letter's path is represented by a letter (A-P). Uppercase letters imply the pen should be up while moving to that node, whereas lowercase letters indicate that the pen should be down.

Example: To write the letter 'A', the sequence might be 'GiMbo'. This tells the robot to go to node G with the pen up, then to node I with the pen down, and so forth.

### Running the Program

The Python script `AI.py` operates the writing program. To create letters or words, construct a string with the desired output and assign it to `my_string`. Each letter in your string needs a corresponding sequence in the `sequence` dictionary.

Example: To write the word 'LIKE', 
```python
my_string = 'LIKE'
```
### Calculating Distance and Angles

The program performs distance calculation and movement direction using Pythagoras theorem and Python’s `atan2(y,x)` function respectively. It keeps track of the robot's current heading and the heading it must adopt to move to the next node.

