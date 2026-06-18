## Week 1 
### May 28
Implemented a simple g-h filter in Python. Key insight: gyroscope used for prediction (dx), accelerometer used for measurement correction (z). 
High g follows noise, low g lags behind real motion. Kalman filter computes optimal g automatically.

### May 29
ESP32 and MPU6050 working. Basic complementary filter running. WHO_AM_I address for the IMU was 0x70 not 0x68. Learned how to bypass ID checks and directly pull accelerometer and gyro data from IMU today.

### May 31
- Wrote readMPU() and setup() from scratch
- Understood I2C register reads: beginTransmission sets device 
  address, write sets register pointer, requestFrom pulls bytes
- Understood bit shifting: "<< 8 |" combines two 8-bit bytes 
  into one 16-bit value
- Understood gyro calibration: 1000 samples averaged to find 
  bias offset, subtracted from every future reading
- Starting chapter 3 (Gaussians) before chapter 4 (Kalman) in Kalman_and_Bayesian_Filters_in_Python
- 
## Week 2 
### June 5
- Read chapter 3 (Gaussians and probability distributions)
- Most of chapter 3 familiar from AP Stats - mean, variance, 
  standard deviation, probability distributions
- Key connection made: Kalman filter tracks two numbers 
  simultaneously - mean (best estimate) and variance 
  (confidence in that estimate)
--- 
From now on, I will stop denoting each log with a Week, and instead just log the date in standard format (DD/MM/YYYY).
--- 

