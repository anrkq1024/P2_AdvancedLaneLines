
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
![test2](https://user-images.githubusercontent.com/35591154/40277822-53d1f296-5c60-11e8-99bc-7e9d366cd873.jpg)
![test5](https://user-images.githubusercontent.com/35591154/40277823-5528ac20-5c60-11e8-9fc6-fb1812d2c90f.jpg)

#### calibrated image
![calibrated_test2](https://user-images.githubusercontent.com/35591154/40277801-0a4c57f6-5c60-11e8-9981-f8fe6007063a.png)
![calibrated_test5](https://user-images.githubusercontent.com/35591154/40277802-0ce3b3d8-5c60-11e8-95fe-c4d76295a7ef.png)
