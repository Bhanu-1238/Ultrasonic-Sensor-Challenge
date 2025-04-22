# ULTRASONIC SENSOR CHALLENGE

## 🎯 Project Objective
The project's primary goal is to interface an ultrasonic sensor (such as the HC-SR04) with an STM32 microcontroller to measure distances accurately. This involves generating a precise trigger pulse, capturing the echo response, calculating the distance based on the time interval, and displaying the results using debugging tools.

## 🛠️ Hardware Components
- **Microcontroller**: STM32F407G-DISC1
- **Ultrasonic Sensor**: HC-SR04

### Connections:
- **TRIG Pin**: Connected to PE9 (TIM1_CH1)
- **ECHO Pin**: Connected to PE11 (TIM1_CH2)
- **Power Supply**: 
  - VCC to 5V
  - GND to GND

## 🧑‍💻 Software Configuration
- **Development Environment**: STM32CubeIDE

### Timer Configuration:
- **TIM1_CH1 (PE9)**: Configured in PWM mode to generate a 10µs trigger pulse.
- **TIM1_CH2 (PE11)**: Configured in Input Capture mode to measure the duration of the echo pulse.
- **Interrupts**: Enabled for TIM1 to handle capture events.

### Distance Calculation:
- **Formula**: 
  - `Distance (cm) = Echo Pulse Width (µs) / 58.0`
- **Variables**:
  - `echo_PW`: Stores the duration of the echo pulse in microseconds.
  - `distance`: Stores the calculated distance in centimeters.

## 🧪 Testing and Debugging
### Live Expressions:
Utilized STM32CubeIDE's Live Expressions feature to monitor `echo_PW` and `distance` in real-time without halting the program execution.

### Debugging Steps:
1. Launch the debugger in STM32CubeIDE.
2. Resume program execution.
3. Open the Expressions view.
4. Add the variables `echo_PW` and `distance` to monitor their values live.

## 📈 Results
The system successfully measures distances by sending a 10µs trigger pulse and capturing the duration of the echo pulse. The calculated distances are displayed in real-time using the Live Expressions feature, allowing for effective debugging and validation of the sensor's performance.

## 📄 Conclusion
This project demonstrates the integration of an ultrasonic sensor with an STM32 microcontroller, highlighting the use of timers, interrupts, and debugging tools to measure distances accurately. The implementation serves as a foundational exercise in embedded systems programming and sensor interfacing.
