# Digital Lock Design Without Microcontroller

![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/a2ccab23-f77c-4843-88b7-b0987883d762)

The Digital Lock Circuit project is a simple yet effective security system that uses an EEPROM to store passwords and control access to a device or area. The circuit is implemented without using a microcontroller, making it a cost-effective and reliable solution.

There are two types of passwords in this system. The first password is for regular users and is formed from 4 digits. The second password is for the administrator and is formed from 6 digits. If a user enters the wrong password twice, the system requires the administrator to enter their password to open the lock.

The circuit has six LEDs that indicate the number of digits entered by the user. There is also an LED that indicates whether the system is open or closed. Another LED indicates which attempt the user is on. If the LED is off, the user is on their first attempt. If the LED is on, it means the user is on their second attempt. There is also an LED that indicates whether the user is entering the administrator password or not.

If the administrator enters the wrong password, the system stops completely and needs to be reset.

This Digital Lock Circuit project is ideal for securing devices such as safes, lockers, or even homes. The use of an EEPROM allows for easy password programming and storage, and the LED indicators provide a clear indication of the system's status.

Overall, the Digital Lock Circuit project is a great way to implement a secure access control system without using a microcontroller, making it a perfect choice for hobbyists and DIY enthusiasts who want to build their own security system.

## Project Sections
The project is composed of four key elements:
1. numerical keypad
2. memory unit
3. notification panel 
4. clock circuit

Together, these components form a functional system for a specific purpose, although the exact nature of that purpose is not specified. The numerical keypad is used to input data, which is then stored in the memory unit. The notification panel provides feedback to the user, indicating the status of the system or the input provided. The clock circuit helps to keep track of time or other relevant metrics, depending on the specific application of the system.

### Numerical Keypad
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/1a483672-79fc-4a83-b95f-5763c9167f74)

A numerical keypad is a device that allows users to input numerical data into a digital system. Typically, the keypad consists of a set of buttons, each labeled with a numerical digit, as well as special buttons for OK and Clear functions.

To interface with a digital circuit, the numerical keypad uses encoder ICs such as the 74HC148. These ICs convert the decimal input from the keypad into a binary output that can be easily interpreted by the digital circuitry. In this case, two 74HC148 ICs are used - one for numbers 0-9, and another for the OK and Clear buttons.

When a user presses a button on the numerical keypad, the corresponding decimal value is sent to the appropriate 74HC148 encoder IC. The IC then converts this value into a binary code that is sent to the digital circuit for processing. Each digit is encoded into four binary numbers: K3, K2, K1, and K0. These numbers represent the value of the button pressed in binary format. For example, if the user presses the button labeled "5", the corresponding binary output would be 0101.

By using two 74HC148 encoder ICs, the keypad is able to convert all possible inputs into binary output that can be easily interpreted by the digital circuitry. This allows the system to recognize the input and perform the appropriate action, such as verifying a password or performing a specific operation. Overall, the use of a numerical keypad with encoder ICs provides a simple and efficient way to input numerical data into a digital system.

