# Simulation Of Digital Lock Design Without Microcontroller Using Proteus 8.13

![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/a2ccab23-f77c-4843-88b7-b0987883d762)

The Digital Lock Circuit project is a simple yet effective security system that uses an EEPROM to store passwords and control access to a device or area. The circuit is implemented without using a microcontroller, making it a cost-effective and reliable solution.

There are two types of passwords in this system. The first password is for regular users and is formed from 4 digits. The second password is for the administrator and is formed from 6 digits. If a user enters the wrong password twice, the system requires the administrator to enter their password to open the lock.

The circuit has six LEDs that indicate the number of digits entered by the user. There is also an LED that indicates whether the system is open or closed. Another LED indicates which attempt the user is on. If the LED is off, the user is on their first attempt. If the LED is on, it means the user is on their second attempt. There is also an LED that indicates whether the user is entering the administrator password or not.

If the administrator enters the wrong password, the system stops completely and needs to be reset.

This Digital Lock Circuit project is ideal for securing devices such as safes, lockers, or even homes. The use of an EEPROM allows for easy password programming and storage, and the LED indicators provide a clear indication of the system's status.

Overall, the Digital Lock Circuit project is a great way to implement a secure access control system without using a microcontroller, making it a perfect choice for hobbyists and DIY enthusiasts who want to build their own security system.

## Project Sections
The project is composed of four key elements:
* numerical keypad
* memory section
* notification panel 
* clock circuit

Together, these components form a functional system for a specific purpose, although the exact nature of that purpose is not specified. The numerical keypad is used to input data, which is then stored in the memory unit. The notification panel provides feedback to the user, indicating the status of the system or the input provided. The clock circuit helps to keep track of time or other relevant metrics, depending on the specific application of the system.

## Project Symbol 
| Symbol | Meaning                                                        |
|--------|----------------------------------------------------------------|
| L.O    | Is System Opened?                                               |
| I2 I1 I0 | The 3 binary digit for six LEDs that indicate the number of digits entered by the user |
| IP     | Is system In the Adminstrator password                           |
| T      | Number of trial LED                                             |
| A      | For alarm                                                       |

***
### 1. Numerical Keypad
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/1a483672-79fc-4a83-b95f-5763c9167f74)

A numerical keypad is a device that allows users to input numerical data into a digital system. Typically, the keypad consists of a set of buttons, each labeled with a numerical digit, as well as special buttons for OK and Clear functions.

To interface with a digital circuit, the numerical keypad uses encoder ICs such as the 74HC148. These ICs convert the decimal input from the keypad into a binary output that can be easily interpreted by the digital circuitry. In this case, two 74HC148 ICs are used - one for numbers 0-9, and another for the OK and Clear buttons.

When a user presses a button on the numerical keypad, the corresponding decimal value is sent to the appropriate 74HC148 encoder IC. The IC then converts this value into a binary code that is sent to the digital circuit for processing. Each digit is encoded into four binary numbers: K3, K2, K1, and K0. These numbers represent the value of the button pressed in binary format. For example, if the user presses the button labeled "5", the corresponding binary output would be 0101.

By using two 74HC148 encoder ICs, the keypad is able to convert all possible inputs into binary output that can be easily interpreted by the digital circuitry. This allows the system to recognize the input and perform the appropriate action, such as verifying a password or performing a specific operation. Overall, the use of a numerical keypad with encoder ICs provides a simple and efficient way to input numerical data into a digital system.
***
## 2. Memory Section

![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/aa290f67-9d99-436b-b2e3-1cb44506e396)

#### Using Memory IC 2732 to Store Program State and Output Data

The 2732 is an electrically erasable programmable read-only memory (EEPROM) IC that can store up to 4 kilobytes of data. In digital logic circuits, it is commonly used to store the program state and output data.

##### Program State

Program state refers to the current status or state of the circuit. In the context of a digital lock circuit, program state could include information such as the current password entered by the user, the number of times the user has entered an incorrect password, and whether or not the system is currently locked or unlocked.

The 2732 can be used to store this program state by connecting its data input pins to the outputs of logic gates that generate the state information. These gates could be implemented using other ICs or discrete logic components. The state information is then written to the EEPROM using a programmer device.

When the circuit is powered on or reset, the program state is read from the EEPROM and used to initialize the system to its previous state.

##### Output Data

Output data refers to the information generated by the circuit and displayed to the user. In the context of a digital lock circuit, output data could include the number of digits entered by the user, whether or not the system is currently locked or unlocked, and whether or not the user has entered the correct password.

The 2732 can be used to store this output data by connecting its data output pins to the inputs of display devices such as LEDs or 7-segment displays. The output data is then written to the EEPROM by the logic gates that generate the output information.

When the circuit is powered on or reset, the output data is read from the EEPROM and used to initialize the display devices to their previous state.

##### Using Tow ICs of 2732 EPROM
The 2732 is a memory IC that can store up to 4K bits of data. It is commonly used in digital circuits to store program code or other data that needs to be accessed quickly. However, one limitation of the 2732 is that it only has 8 output pins, which can be a problem in circuits that require more than 8 output signals.

To get more than 8 output pins from a memory IC like the 2732, one solution is to use two of them in parallel. By connecting the address inputs and control pins of the two ICs together, they can be treated as a single larger memory IC with twice the capacity and twice the number of output pins.

### Input Pins Table
| Pin | Usage                         |
| --- | -----------------------------|
| A0  | K0 from keypad                      |
| A1  | K1 from keypad                      |
| A2  | K2 from keypad                      |
| A3  | K3 from keypad                      |
| A4  | D3 from EPROM0 output as next state |
| A5  | D4 from EPROM0 output as next state |
| A6  | D5 from EPROM0 output as next state |
| A7  | D6 from EPROM0 output as next state |
| A8  | D7 from EPROM0 output as next state |

### Output Pins Table
#### For EPROM0
| Pin | Usage            |
| --- | ----------------|
| D0  | I1 output        |
| D1  | I2 output        |
| D2  | L.O output       |
| D3  | Q0 for next state|
| D4  | Q1 for next state|
| D5  | Q2 for next state|
| D6  | Q3 for next state|
| D7  | Q4 for next state|

#### For EEPROM1
| Pin | Usage            |
|-----|-----------------|
| D0  | A output         |
| D1  | T output         |
| D2  | IP output        |
| D3  | I0 output        |



### Using 74HC374 IC as Delay for Memory
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/fac16c47-9c6a-46bd-9d76-718eaea64faf)


The 74HC374 is an octal D-type flip-flop IC that can be used as a delay element in digital circuits. In the context of a circuit that uses a memory IC like the 2732, the 74HC374 can be used to delay the output data from the memory and ensure that it is stable before being sent to other parts of the circuit.

##### Delaying Output Data

When output data is read from a memory IC like the 2732, it can take a short amount of time for the data to stabilize and become valid. If this data is sent to other parts of the circuit before it has stabilized, it could cause errors or other issues.

The 74HC374 can be used to delay the output data from the memory by connecting its data input pins to the outputs of the memory IC and its data output pins to the inputs of other parts of the circuit. The flip-flops in the 74HC374 provide a delay that allows the output data to stabilize before being sent to the next part of the circuit.

##### Implementation

To use the 74HC374 as a delay for memory, the data output pins of the memory IC are connected to the data input pins of the 74HC374. The data output pins of the 74HC374 are then connected to the inputs of other parts of the circuit.

The delay time provided by the 74HC374 can be adjusted by changing the clock frequency applied to the clock input pins of the IC. By increasing the clock frequency, the delay time is reduced, and by decreasing the clock frequency, the delay time is increased.
***
## 3. Notification Panel
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/45ed6081-d6e7-4581-9e02-9b1ee167b7a1)

### The six LEDs that indicate the number of digits
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/a90d5e93-4abf-4943-9f76-ae7d2f5352ce)

To explain the process of converting a binary number to decimal using a Decoder 74HC137 and connecting its output pins to 6 LEDs that indicate the entered number, we first need to understand what a Decoder is.

A Decoder is a combinational logic circuit that converts a binary input signal into an output signal representing a single, specific value. In the case of the 74HC137 Decoder, it has 3 binary input signals (I0, I1, and I2) and 8 output signals (Y0-Y7). The output signal that is active (i.e., has a logical high state) is determined by the binary input signal.

To convert a binary number to decimal using a Decoder 74HC137, we connect the binary input signal to the I0, I1, and I2 pins of the Decoder and connect the output pins Y0-Y7 to the corresponding LEDs.

For example, if we have a binary number 101 (which represents decimal number 5), we would connect I0 to logic 1, I1 to logic 0, and I2 to logic 1. The Decoder would then activate output pin Y5, which is connected to the 5th LED, indicating that the entered number is 5.

By connecting the output pins Y0-Y7 to the corresponding LEDs, we can display the entered number in decimal form, making it easier for the user to understand and interact with the system.

### L.O LED 
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/64d422ea-29c2-42ac-8df2-bb3f521e0430)

The L.O LED is a visual indicator that shows whether the system is currently in an opened state or not. If the user enters the correct password, the system will transition to an opened state and the L.O LED will turn on. This can help the user to confirm that they have successfully entered the correct password and that they are now able to access the system. 

### T LED 
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/bb915468-f193-4348-b27b-b42435f1b3bc)
The T LED is used to indicate the number of trial attempts that the user has made to enter the password. It can be used to give the user feedback on their progress.

For example, if the T LED is off, it means that the user is on their first trial attempt. If the T LED is on, it means that the user is on their second trial attempt. This can continue up to a maximum number of trial attempts, after which the system might lock the user out or take other security measures.

Overall, the T LED is an important component of the system's security features and helps to keep the user informed about their progress in entering the correct password.

### IP LED
![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/cf36b5bb-5d65-45a3-9ef3-f5155bfb415b)

The IP LED stands for "In the Administrator Password." When the user enters the wrong password twice in a row, it means that there may be a security issue or an attempted breach. In such cases, the system may require the administrator to enter a special password to verify that they have the authority to access the system.

The purpose of the IP LED is to indicate to the user that the system has entered a special mode that requires the administrator password. When the LED is lit, the user knows that they cannot proceed without entering the correct password, and that they must seek assistance from the administrator.

The use of the IP LED in this way helps to ensure the security of the system by requiring a higher level of authentication before allowing access.
***
## 4. Clock Circuit Using 555
![0c1be4ea-aa49-454c-98c6-e872d5d8a56d](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/81f166ed-2893-49ad-a6f2-6a48abfd88be) ![image](https://github.com/amdhazm/DigitalLockDesign/assets/133523862/dbb8dd2d-f599-41b3-b972-7814e36b1c87)

The 555 timer IC can be used as a digital clock generator circuit. The 555 timer is a versatile and widely used IC that can operate in various modes. The digital clock circuit using the 555 timer IC can generate accurate and stable clock pulses with a high degree of precision.

The 555 timer IC can be configured to operate in astable mode, which means that it can generate a continuous stream of pulses. The frequency of the pulses can be set using external components such as resistors and capacitors. By adjusting the values of these components, the frequency of the clock pulses can be precisely controlled.

The digital clock circuit using the 555 timer IC typically consists of the following components:

- 555 timer IC: This is the main component of the circuit, which generates the clock pulses.
- Resistors: These are used to set the frequency of the clock pulses.
- Capacitors: These are also used to set the frequency of the clock pulses.
- LEDs: These are used to indicate the output of the clock pulses.
- Power supply: The circuit requires a power supply to operate.

The digital clock circuit using the 555 timer IC works by charging and discharging the capacitor connected to the 555 timer IC. When the capacitor is charged, the output of the 555 timer IC goes high, and when the capacitor is discharged, the output goes low. This process continues, generating a continuous stream of clock pulses.

The frequency of the clock pulses can be calculated using the following formula:

f = 1.44 / ((R1 + 2 * R2) * C)

Where f is the frequency of the clock pulses, R1 and R2 are the resistors used in the circuit, and C is the capacitance of the capacitor used in the circuit.

Overall, the digital clock circuit using the 555 timer IC is a simple yet effective way to generate accurate and stable clock pulses.

