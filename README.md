\# Thermal Power Management ECU with Fault Management, Diagnostics and Automated Validation using STM32



\## Project Overview



This project focuses on the development and validation of an embedded Thermal Power Management ECU built around the STM32F446RE microcontroller.



The system is designed to acquire temperature-related inputs, evaluate their plausibility, control a cooling actuator, detect abnormal operating conditions, manage faults, and provide diagnostic information to an external test system.



The project is developed first as a breadboard prototype using the NUCLEO-F446RE development board. A custom PCB may be designed in a later stage after the hardware and firmware architecture have been validated.



A major goal of the project is not only to implement the embedded control functionality, but also to build an automated validation environment using Python, PySerial and PyTest.



\---



\## Project Goals



The project is intended to demonstrate practical knowledge in:



\- Embedded C development on STM32

\- Hardware-software integration

\- GPIO, ADC, I2C, UART and PWM

\- Sensor acquisition and plausibility checking

\- State-machine-based embedded control

\- Fault detection and fault management

\- Safe-state handling

\- Watchdog supervision

\- UART diagnostics

\- Automated hardware validation using Python

\- Test automation using PyTest

\- Hardware debugging using a logic analyzer and multimeter



\---



\## General System Architecture



The current prototype architecture consists of an STM32-based ECU connected to real and simulated inputs, status outputs, a cooling actuator and an external validation environment.



!\[General System Architecture](docs/architecture/arhitectura\_generala.drawio.png)



The STM32F446RE acts as the main ECU controller.



The main input sources are:



\- A digital temperature sensor connected through I2C for real temperature acquisition

\- A potentiometer connected to the internal STM32 ADC for simulated analog input and fault injection

\- Push buttons used for fault injection and fault clearing



The main outputs are:



\- Cooling fan control

\- Status LEDs

\- UART diagnostic messages



An external PC communicates with the ECU through UART and runs automated validation software written in Python.



\---



\## Hardware Architecture



\### Main Controller



The project currently uses the \*\*NUCLEO-F446RE\*\* development board based on the \*\*STM32F446RET6\*\* microcontroller.



The STM32 is responsible for:



\- Sensor acquisition

\- ADC conversion

\- I2C communication

\- State management

\- Fault detection

\- Cooling control

\- Diagnostic communication

\- Watchdog supervision



\### Temperature Sensor



A digital temperature sensor is connected through the I2C bus.



The sensor provides the real environmental temperature used by the thermal control algorithm.







