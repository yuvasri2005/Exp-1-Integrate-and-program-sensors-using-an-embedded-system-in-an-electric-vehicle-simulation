# Exp-1-Integrate-and-program-sensors-using-an-embedded-system-in-an-electric-vehicle-simulation

## AIM
To integrate and program temperature and accelerometer sensors in an embedded system for an electric vehicle (EV) simulation. The system monitors battery temperature and vehicle acceleration in real-time.
 
## APPARATUS REQUIRED
•	MATLAB Software
•	Embedded System (ESP32, Arduino, or Simulated Data in MATLAB)
•	Temperature Sensor (e.g., LM35, DHT11)
•	Accelerometer Sensor (e.g., MPU6050, ADXL345)
•	Serial Communication (for real sensors)
 
## THEORY
1. Temperature Monitoring in EVs
•	The battery temperature is crucial for safety and efficiency.
•	Excess heat can degrade battery performance and reduce lifespan.
•	A temperature sensor (e.g., LM35) provides real-time temperature monitoring.
2. Accelerometer for Motion Analysis
•	The accelerometer tracks vehicle movement and stability.
•	It measures acceleration in X, Y, and Z axes.
•	This data helps in suspension tuning, crash detection, and navigation.
3. Embedded System Integration
•	Data from sensors is acquired and processed using an embedded system.
•	The system can send alerts if temperature exceeds safe limits.
•	It can also detect sudden acceleration or braking for safety applications.
 
## PROCEDURE
🔹 Step 1: Sensor Simulation in MATLAB
•	Simulate temperature variations using a sinusoidal function.
•	Generate accelerometer readings in X, Y, and Z directions.
🔹 Step 2: Plot Sensor Data
•	Plot temperature variations over time.
•	Plot acceleration data in X, Y, and Z axes.
🔹 Step 3: Display Key Sensor Readings
•	Print the final temperature and acceleration values.
 
## MATLAB CODE 

clear; clc; close all;

%% Simulation Parameters

time = linspace(0, 10, 100); % Simulate for 10 seconds with 100 samples

battery_temp = 25 + 5*sin(0.5*time); % Simulated temperature variation (25°C avg)

accX = 0.5*sin(2*time);     % Simulated acceleration in X-axis

accY = 0.3*cos(2*time);     % Simulated acceleration in Y-axis

accZ = 9.81 + 0.1*sin(time); % Simulated gravity effect on Z-axis


%% Plot Temperature Sensor Data

figure;

subplot(2,1,1);

plot(time, battery_temp, 'r', 'LineWidth', 2);

title('Battery Temperature Monitoring');

xlabel('Time (s)');

ylabel('Temperature (°C)');

grid on;

%% Plot Accelerometer Data

subplot(2,1,2);

plot(time, accX, 'b', time, accY, 'g', time, accZ, 'm', 'LineWidth', 2);

title('Vehicle Motion Tracking (Accelerometer)');

xlabel('Time (s)');

ylabel('Acceleration (m/s²)');

legend('X-axis', 'Y-axis', 'Z-axis');

grid on;

%% Display Key Data in Console

fprintf('Simulated Data at Final Time (t=10s):\n');

fprintf('Battery Temperature: %.2f °C\n', battery_temp(end));

fprintf('Acceleration (X, Y, Z): %.2f, %.2f, %.2f m/s²\n', accX(end), accY(end), accZ(end));


## OUTPUT

<img width="1600" height="833" alt="image" src="https://github.com/user-attachments/assets/1ca02c65-d3dc-45a1-a635-f118e5583edb" />


 
## RESULT

<img width="1089" height="181" alt="image" src="https://github.com/user-attachments/assets/0aed9d50-a4f5-4b26-80c5-281870c8fb5a" />

•	The battery temperature and vehicle acceleration were successfully simulated.
•	The system monitored and displayed sensor data in MATLAB.
•	The output provides insights into EV motion and battery performance.
 
## CONCLUSION
This experiment demonstrated how temperature and motion sensors can be integrated into an embedded system for an electric vehicle simulation. This system can be extended to real sensors for live monitoring and safety applications.

