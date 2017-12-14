[//]: # (Image References)
[image_0]: ./misc/rover_image.jpg

# Search and Sample Return Project

This is the first project for Udacity's Robotics Engineer Nanodegree.

This project is a work-in-progress. The rover can map at least 40% of the terrain above 60% fidelity and locate at least one rock sample. However, I still need to adjust the ability of the rover to crawl along the terrain walls without drastically reducing the fidelity. Also, I would like to eventually implement A* algorithm to the mapping ability of the rover.

The project was run on the mac version of the Unity simulator at a resolution of 1152 x 700, with the graphics setting at 'good'.

![alt text][image_0]

This project contains a watered-down solution for the the [NASA sample return challenge](https://www.nasa.gov/directorates/spacetech/centennial_challenges/sample_return_robot/index.html).


## Recording Data
The test_dataset folder contains the images and CSV file from a training run in the simulator. The output video is, appropriately enough, located in the 'output' folder (I couldn't render the video within the notebook on Github).

## Data Analysis
The`Rover_Project_Test_Notebook.ipynb` contains the sample data from the simulator, which is found in the test_dataset folder.


## Navigating Autonomously
The 'perception.py' file contains the adjustments to filter each video image from the Rover to separate the RGB vaules. The threshold for each pixel (approximately 160 for each RGB channel) separates the obstacles (value of '0') from the navigable terrain (value of '1'). Each binary image is then adjusted to the rover point-of-view (rover_coords). Then the radial distances and angles are calculated in the to_polar_coords function:

        the distance of each pixel: np.sqrt(x_pixel**2 + y_pixel**2) 
        
        the angle of each pixel: np.arctan2(y_pixel, x_pixel)


Then the pics are manipulated to display as a worldmap through the rotate_pix (to convert Rover yaw to radians), translate_pix and pix_to_world functions (displayed in `Rover_Project_Test_Notebook.ipynb` in the code folder).

The perspect_transform method takes in each image and "performs the perspective matrix transformation of vectors" https://stackoverflow.com/questions/45817325/opencv-python-cv2-perspectivetransform.




I did not make adjustments to the `drive_rover.py` since limiting the steer range ultimately caused the rover to keep slamming into the walls and lowering the fidelity. I did try to set limits for the yaw and roll, but that caused the rover to just stop moving. I limited the speed of the rover to 1 meter/second and added functionality for the rover to pick up a rock sample if the rover detects that it is near a sample.

My next step is to switch the Rover.steer from nav.angles to the rock

I incorporated the basic solution from the [Project Walkthrough Video](https://www.youtube.com/watch?v=oJA6QHDPdQw).


