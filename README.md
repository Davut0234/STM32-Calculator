# STM32-Calculator

Project Overview
This project is a simple calculator that runs on an STM32 microcontroller. The user can perform basic arithmetic operations such as addition, subtraction, multiplication, division, and modulo. The input is entered using physical pushbuttons and displayed on an LCD screen using I2C communication. The results are also transmitted via UART to a connected computer.

Features:
Performs basic arithmetic operations (addition, subtraction, multiplication, division, and modulo).
Input using physical buttons (0-9, operations).
Results displayed on an LCD (16x2) via I2C.
Transmits results over UART to a connected computer.
LCD and UART interface for user interaction.
Components Used
Microcontroller: STM32 (specifically STM32F401RE).
LCD: 16x2 I2C Display.
Button Inputs: Physical buttons for numbers (0-9) and operations.
UART: For communication with the PC to transmit results.
Timer: Used for generating random values.
Installation
Prerequisites
STM32CubeIDE: For programming and debugging the STM32 microcontroller.
STM32F401RE Microcontroller: This project is designed for this MCU but can be adapted to others with similar specifications.
Setting up the Project
Open STM32CubeIDE and create a new project.
Add the necessary peripheral libraries for I2C, UART, and GPIO as well as timers for random number generation.
Copy the main.c code into the project’s src folder.
Make sure the I2C1, USART2, and TIM2 peripherals are initialized correctly in the STM32CubeMX settings.
Wiring
LCD (16x2) connected to the I2C pins of the STM32.
Buttons: Connect to GPIO pins configured as inputs (each connected to a specific pin for each number and operation).
UART: Connect the TX and RX pins to the corresponding UART ports.
Code Explanation
Main Function
The main function handles the initialization of the MCU peripherals (GPIO, I2C, UART, Timer) and contains the main infinite loop for the program. It listens for button presses and performs the selected arithmetic operation, displays results on the LCD, and sends the result to the PC via UART.

Button Input Handling
The calculator waits for button presses (0-9, operations, result recall, random number).
When a button is pressed, it updates the input string num1 and displays the digit or operation symbol on the LCD.
When the operation is selected, it performs the corresponding mathematical operation and displays the result.
LCD Output
The LCD is used to display the current input and result. It also displays the selected operation symbol.

UART Communication
Every time a calculation is completed, the result is transmitted via UART to a connected computer for logging or further use.

Interrupts and Timers
The timer is used to generate random numbers for the random button functionality.
External interrupts are used to capture button presses from GPIO pins.
How to Use
Power the board.
Press the buttons to input numbers (0-9) and select operations (+, -, *, /, %).
After completing the calculation, the result will be displayed on the LCD.
The result is also sent via UART to the connected PC for viewing.
Project Presentation
This project is a simple arithmetic calculator that demonstrates the use of basic hardware and software techniques for embedded systems. It integrates input handling through GPIO interrupts, real-time display on an LCD via I2C, and communication with a PC over UART. The program handles basic arithmetic operations and also includes a random number generator feature, offering a practical and interactive way to perform simple calculations on an embedded system.

Applications
Embedded system development practice.
Understanding peripheral integration on STM32.
Basic user interface design with I2C and UART communication.
