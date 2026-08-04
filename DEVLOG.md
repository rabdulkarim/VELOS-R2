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

## 21/07/2026
### TVC Mount Rings Finalised

Motor Mount (Inner Ring), Center Ring, and Outer Ring bases finalised with exact screw, bearing, and servo dimensions. Will move onto building supports for the FC + battery + ESC.

---
## 30/07/2026
### Exported Thrust stand file and sliced in Cura

Thrust stand dimensions checked once more in FreeCAD, exported as a .3mf file (Cura is having problems with .stl files), sliced as a .gcode file and placed on 16GB SD card, ready for printing tomorrow.

---
## 31/07/2026
###  Thrust Stand Printed!!

Thrust Stand successfuly printed at school's Ender 3 Pro, dimensions checked with caliper. Finalising and commiting .3mf file to Github.

---
## 02/08/2026
### Exported Center Ring and Motor Mount in Cura slicer

Center Ring and Motor Mount are now ready for printing, exported as .gcode file for printing on school's Ender 3 Pro. Will commit .3mf files when Outer Ring is ready for printing and also exported.

---
## 03/08/2026
### Moved Motor Mount servo from Outer Ring to Center Ring

Realised that push rods connecting servos to mounts will experience bending (as well as servo horns).

Root cause:
- Both servos are placed on the same ring.
- No ball-jointed pushrods available.
- Servo mounts dont match caliper readings.

Solution:
- Placed MotorMount Servo on the Center Ring.
- Re-desinged servo mounts to match real-life caliper measurements.

Result: Outer Ring is ready for flight computer mount and battery mount bracket fitting.

---
## 04/08/2026
### HX711 Sample Rate Investigation

Initially observed inconsistent sample rates.

Root cause:
- Incorrect wiring.
- HX711 RATE pin left in 10 SPS configuration.

Modification:
- Connected RATE pin to VCC.

Result:
- Measured sample rate ≈ 89.6 Hz.
