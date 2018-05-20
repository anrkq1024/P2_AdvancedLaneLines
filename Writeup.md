
# Udacity SDCND Project_2 
# Advanced Lane Lines Detecting
----
### Camera Calibration
- cv2.findChessboardCorners() : Find the chessboard corners
- cv2.calibrateCamera() : Calculates distortion coefficients and restoration matrix
- cv2.undistort() : Undistort the distorted image

#### distorted image
![screenshot from 2018-05-20 18-31-45](https://user-images.githubusercontent.com/35591154/40277631-20ae0f74-5c5d-11e8-96ad-835d358abc98.png)
![screenshot from 2018-05-20 18-32-12](https://user-images.githubusercontent.com/35591154/40277634-29636268-5c5d-11e8-9a08-3102f85e37d7.png)

#### calibrated image
![calibrated_calibration1](https://user-images.githubusercontent.com/35591154/40277773-a184053e-5c5f-11e8-8381-62dbcc560b42.png)
![calibrated_calibration2](https://user-images.githubusercontent.com/35591154/40277776-a9c2c53c-5c5f-11e8-8539-a8537bd955ad.png)

### I apply this method to test images

#### distorted image
![screenshot from 2018-05-20 18-57-53](https://user-images.githubusercontent.com/35591154/40277844-034c649a-5c61-11e8-9ab4-23d0faf6c53c.png)
![screenshot from 2018-05-20 18-58-23](https://user-images.githubusercontent.com/35591154/40277845-079a4936-5c61-11e8-9b14-6016e7af5c8a.png)


#### calibrated image
![calibrated_test2](https://user-images.githubusercontent.com/35591154/40277801-0a4c57f6-5c60-11e8-9981-f8fe6007063a.png)
![calibrated_test5](https://user-images.githubusercontent.com/35591154/40277802-0ce3b3d8-5c60-11e8-95fe-c4d76295a7ef.png)

----
### Detect lane lines
- abs_sobel_thresh() : Use cv2.Sobel in the picture to extract only the pixels with the rate of change between the boundary                                                                   values in the x or y direction
- mag_thresh() : After calculating the magnitude with sobelx and sobely, find the pixel whose magnitude is between the boundary values
- dir_threshold() : Considering the direction of the lane, we find a pixel with that direction.
- hls_select() : S channel is the color channel that distinguishes the lane most accurately even when the lane is covered by the shadow. Therefore, the lane is searched using the s channel.

#### original image                             
![test5](https://user-images.githubusercontent.com/35591154/40278765-16cc5b2c-5c72-11e8-9c46-5e5d8f5f2d85.jpg)

#### gradient x image          
![gradient_x](https://user-images.githubusercontent.com/35591154/40278828-5aa34652-5c73-11e8-931a-45d168429019.png)
#### gradient y image   
![gradient_y](https://user-images.githubusercontent.com/35591154/40278827-5624f10c-5c73-11e8-9570-d23f88843b93.png)






