[//]: # (Image References)
[image_0]: ./misc/rover_image.jpg

# Search and Sample Return Project

This is the first project for Udacity's Robotics Engineer Nanodegree.

This project is a work-in-progress. The rover can map at least 40% of the terrain above 60% fidelity and locate at least one rock sample. However, I still need to adjust the ability of the rover to crawl along the terrain walls without drastically reducing the fidelity. Also, I would like to eventually implement A* algorithm to the mapping ability of the rover.

The project was run on the mac version of the Unity simulator at a resolution of 1152 x 700, with the graphics setting at 'good'.

![alt text][image_0]

This project contains a watered-down solution for the the [NASA sample return challenge](https://www.nasa.gov/directorates/spacetech/centennial_challenges/sample_return_robot/index.html).

## The Simulator
The first step is to download the simulator build that's appropriate for your operating system.  Here are the links for [Linux](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Linux_Roversim.zip), [Mac](	https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Mac_Roversim.zip), or [Windows](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Windows_Roversim.zip).



## Recording Data
The test_dataset folder contains the images and CSV file from a training run in the simulator. The output video is, appropriately enough, located in the 'output' folder (I couldn't render the video within the notebook on Github).

## Data Analysis
The`Rover_Project_Test_Notebook.ipynb` contains the sample data from


The last two cells in the notebook are for running the analysis on a folder of test images to create a map of the simulator environment and write the output to a video.  These cells should run as-is and save a video called `test_mapping.mp4` to the `output` folder.  This should give you an idea of how to go about modifying the `process_image()` function to perform mapping on your data.

## Navigating Autonomously
The file called `drive_rover.py` is what you will use to navigate the environment in autonomous mode.  This script calls functions from within `perception.py` and `decision.py`.  The functions defined in the IPython notebook are all included in`perception.py` and it's your job to fill in the function called `perception_step()` with the appropriate processing steps and update the rover map. `decision.py` includes another function called `decision_step()`, which includes an example of a conditional statement you could use to navigate autonomously.  Here you should implement other conditionals to make driving decisions based on the rover's state and the results of the `perception_step()` analysis.

`drive_rover.py` should work as is if you have all the required Python packages installed. Call it at the command line like this:

```sh
python drive_rover.py
```

Then launch the simulator and choose "Autonomous Mode".  The rover should drive itself now!  It doesn't drive that well yet, but it's your job to make it better!

**Note: running the simulator with different choices of resolution and graphics quality may produce different results!  Make a note of your simulator settings in your writeup when you submit the project.**

### Project Walkthrough
If you're struggling to get started on this project, or just want some help getting your code up to the minimum standards for a passing submission, we've recorded a walkthrough of the basic implementation for you but **spoiler alert: this [Project Walkthrough Video](https://www.youtube.com/watch?v=oJA6QHDPdQw) contains a basic solution to the project!**.


