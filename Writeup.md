
# Udacity SDCND Project_2 
# Advanced Lane Lines Detecting
----
## Camera Calibration
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
## Detect lane lines
- abs_sobel_thresh() : Use cv2.Sobel in the picture to extract only the pixels with the rate of change between the boundary                                                                   values in the x or y direction
- mag_thresh() : After calculating the magnitude with sobelx and sobely, find the pixel whose magnitude is between the boundary values
- dir_threshold() : Considering the direction of the lane, we find a pixel with that direction.
- hls_select() : S channel is the color channel that distinguishes the lane most accurately even when the lane is covered by the shadow. Therefore, the lane is searched using the s channel. It can be done by using cv2.COLOR_RGB2HLS to convert RGB color space into HLS color space

### I show the results of each steps.

#### original image                          
![screenshot from 2018-05-20 21-15-12](https://user-images.githubusercontent.com/35591154/40278861-e732c822-5c73-11e8-999b-9cf32286c8dd.png)
#### gradient_x of the image          
![gradient_x](https://user-images.githubusercontent.com/35591154/40278828-5aa34652-5c73-11e8-931a-45d168429019.png)
#### gradient_y of the image   
![gradient_y](https://user-images.githubusercontent.com/35591154/40278827-5624f10c-5c73-11e8-9570-d23f88843b93.png)
#### magnitude of the image
![magnitude](https://user-images.githubusercontent.com/35591154/40278941-8199824c-5c75-11e8-883d-7c70386ccaa6.png)
#### direction of the image
![direction](https://user-images.githubusercontent.com/35591154/40278946-9a8a146a-5c75-11e8-9073-9fe8cc3becdd.png)
#### S_channel of the image
![s_channel](https://user-images.githubusercontent.com/35591154/40279020-9a605714-5c76-11e8-8891-65db255f89ad.png)
#### gradient_x and magnitude of the image combined with the S_channel 
#### (which are more efficient and accurate results in lane detection)
#### Apply this to test_images
![gradx_mag_color_combined1](https://user-images.githubusercontent.com/35591154/40278953-af56954e-5c75-11e8-97f3-7a5fa9489143.png)
![gradx_mag_color_combined2](https://user-images.githubusercontent.com/35591154/40278954-b04eb3c8-5c75-11e8-9ccd-99eefaf28ccf.png)
![gradx_mag_color_combined3](https://user-images.githubusercontent.com/35591154/40278957-bd15e590-5c75-11e8-8927-371a60a84003.png)
![gradx_mag_color_combined4](https://user-images.githubusercontent.com/35591154/40278958-c0462892-5c75-11e8-9cf4-9ca84029c590.png)
![gradx_mag_color_combined5](https://user-images.githubusercontent.com/35591154/40278959-c18c5d8e-5c75-11e8-8696-3953ddee31e4.png)
![gradx_mag_color_combined6](https://user-images.githubusercontent.com/35591154/40278961-c6afb9e6-5c75-11e8-937f-aef259ad276d.png)

## Perspective transform
- cv2.getPerspectiveTransform(src, dst) : Returns a matrix for transforming the perspective from source to destination.
- cv2.getPerspectiveTransform(dst ,src) : Returns the inverse transformation matrix for painting the lane in the bird's view and then applying it back to the original photograph.
- cv2.warpPerspective() : Using the obtained matrix, get an image whose point of view is actually changed.

#### source point
![markedarea](https://user-images.githubusercontent.com/35591154/40279046-f3bed3c6-5c76-11e8-89c6-52b1ebe103b1.png)

### Apply this to test_images

![warped1](https://user-images.githubusercontent.com/35591154/40279106-e9d15888-5c77-11e8-962a-9bae5870347e.png)
![warped2](https://user-images.githubusercontent.com/35591154/40279107-e9dadc8c-5c77-11e8-8907-a38acba58aa2.png)
![warped3](https://user-images.githubusercontent.com/35591154/40279108-ea37e99a-5c77-11e8-8cf6-82e17b6ba324.png)
![warped4](https://user-images.githubusercontent.com/35591154/40279109-eb45c71c-5c77-11e8-81c9-9f8ed6b285f6.png)
![warped5](https://user-images.githubusercontent.com/35591154/40279110-ec6677f4-5c77-11e8-8bb5-dc48639650c9.png)
![warped6](https://user-images.githubusercontent.com/35591154/40279111-f3672288-5c77-11e8-94a3-e5bd01371378.png)



