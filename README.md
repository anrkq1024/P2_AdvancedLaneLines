
# Udacity SDCND Project_2 
# Advanced Lane Lines Detecting

#### This project's goal is to recognize not only straight lanes but also curved lanes then calculate the curvature of the left and right lanes. And assume that the camera is attached to the center of the car, I calculate how far away the car is from the center of the lane to which direction.
----
## Process
- ### Camera Calibration

The camera accepts light through the lens. The light is refracted by the lens and the picture is distorted. Therefore, the distorted picture should be converted to the original picture without refraction. Use openCV to resolve this.

- ### Detect lane lines 

There are obstacles to distinguishing lanes in general situations. First, the color of the lane can be white or yellow. And because of the shadow, the lane can become dark. Even in this situation, the lane must be distinguished from the photograph. To do this, apply the canny edge to the photo, then set the boundary value for the size and orientation of the pixel. That is, it finds the pixel that is the lane. And in the shadows we use the S channel that best finds the lane and finds the pixel that is the line and matches the previous results.

- ### Perspective transform

In the photograph, the lane gradually becomes smaller and gathered by the perspective. So we have to transform perspective to look at the lane efficiently. Converts the area in which the lane is located, as seen from the top down, called the bird's view. The area is defined by a square shape consisting of four points. Later in this section we find the lane and fill the area with color. When you convert it back to its original point of view, the area corresponding to the lane is displayed on the picture.

- ### Calculate lane lines

In the lane picture obtained through the perspective transform, use the histogram to find the starting point of the lane in the x-axis. And displays the area around the line with a rectangle along the lane.

- ### Calculate curvature & vehicle position

Calculate the curvature expressed as a function of y. 

![screenshot from 2018-05-20 16-40-42](https://user-images.githubusercontent.com/35591154/40276770-915bd2e8-5c4d-11e8-9cee-20eedc7defb4.png)


![screenshot from 2018-05-20 16-40-33](https://user-images.githubusercontent.com/35591154/40276792-0300a1ee-5c4e-11e8-8f68-f46a5bd6738b.png)


This allows you to see how much of the current left and right lanes are bent. Then, the middle point of the lane is compared with the midpoint of the entire photograph. Thus the current vehicle position is calculated.


- ### Apply to video

Apply the above procedure to the camera. In other words, the lane, the curvature, and the current position of the vehicle are displayed every moment.


![screenshot from 2018-05-20 16-48-15](https://user-images.githubusercontent.com/35591154/40276819-a8758068-5c4e-11e8-842f-5cd2c23fe2a8.png)

----
## Configuration 
- ### images_for_calibration

Contains photographs to calculate the distortion of the camera lens and convert the image to an undistorted image.

- ### output_images

  - calibrated_images

  Contains a photograph of a calibrated test image.

  - processed_images

  There are output images for each stage in the whole process

- ### output_video

There is an output video where all processes are applied

- ### test_images 

There are test pictures provided to do the project.

- ### *Writeup.md*

The entire process is explained and described in detail.






