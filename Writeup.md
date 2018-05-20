
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

### Calibrate images on the road
