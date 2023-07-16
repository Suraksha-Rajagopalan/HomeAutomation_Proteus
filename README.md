# HomeAutomation_Proteus


## Abstract:
Due to their capacity to improve residential surroundings' levels of comfort, security, and energy efficiency, home automation systems have seen a substantial increase in popularity in recent years. The LPC2148 microcontroller is used in this project to demonstrate an integrated home automation system developed with Keil and Proteus. A temperature-controlled DC fan, an automatic fire alarm sensor with GSM, and a password-protected door lock system are the three main components of the system. By automatically altering the fan speed in response to the ambient temperature, the temperature-controlled DC fan guarantees the highest level of thermal comfort. In addition to ensuring effective cooling, this feature also conserves electricity by stopping unneeded fan running. An automated fire alarm sensor with GSM capabilities is built into the system to ensure maximum safety. The sensor detects the presence of smoke or heat during a fire and sets off an alarm. Additionally, it uses GSM to deliver an immediate SMS message to the user's mobile phone, enabling quick alerts and swift action to reduce potential fire threats. To further increase security, the system includes a password-protected door lock mechanism. Users can only enter the right password on a keypad to get entrance to their residences. With the help of this system, unauthorized access is guaranteed to be stopped, giving you security and protection from invaders. This home automation system gives homeowners convenience, security, and safety by fusing these elements. A dependable and effective platform for controlling and monitoring various home automation features is provided by the implementation on the LPC2148 microcontroller and the use of Keil and Proteus.


## Keywords: 
Keil, lpc2148, Proteus, DC fan, GSM (Global System for Mobile Communications).

## Introduction:
Welcome to the world of home automation, where convenience and safety meet technological innovation. In this project, we have implemented a sophisticated home automation system using Keil and Proteus, powered by the LPC2148 microcontroller. Our system incorporates several key features that enhance the comfort, security, and efficiency of your living space. One of the standout features of our home automation system is the temperature-controlled DC fan. This smart fan adjusts its speed based on the ambient temperature, ensuring optimal airflow and creating a pleasant environment while saving energy. Say goodbye to manually adjusting fan speed and hello to automated comfort. Safety is paramount in any home, which is why our system includes an automated fire alarm sensor with GSM capabilities. In the event of a fire, this sensor detects the presence of smoke or heat and immediately sends a notification to your mobile device via GSM technology. Early detection is crucial, and our fire alarm system ensures swift action can be taken to minimize damage and protect your loved ones. For an added layer of security, we have integrated a password-protected door lock system. With this feature, you can conveniently control access to your home, granting entry only to authorized individuals. The door lock system offers peace of mind, knowing that your home is protected against unauthorized access. By combining these advanced features in a unified home automation system, we aim to enhance your daily life with comfort, convenience, and safety. Our implementation using the LPC2148 microcontroller, along with the support of Keil and Proteus, guarantees a seamless and efficient operation of the entire system. Get ready to experience the future of home automation, where technology works in harmony to simplify your life and create a secure haven for you and your family. 


## LPC2148:
The LPC2148 is a popular microcontroller based on the ARM7TDMI-S core. It is a member of the LPC2000 series, which is manufactured by NXP Semiconductors (formerly Philips Semiconductor). The LPC2148 offers a range of features and peripherals that make it suitable for various embedded system applications.

 ![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/724ba99d-4830-4a25-a8b9-03dc39286d3c)


Here are some key features and specifications of the LPC2148 microcontroller:
1. Architecture: The LPC2148 is based on a 32-bit ARM7TDMI-S processor core, which provides a powerful and efficient processing platform for embedded applications.
2. Clock Speed: It operates at a maximum CPU clock frequency of 60 MHz, allowing for high-speed data processing.
3. Memory: The LPC2148 has 512 KB of on-chip Flash memory for program storage, and 32 KB of on-chip SRAM for data storage. Additionally, it supports in-system programming (ISP) and in-application programming (IAP), which enables the Flash memory to be reprogrammed while the microcontroller is in operation.
4. Peripherals: The LPC2148 offers a wide range of peripherals to facilitate connectivity and functionality. These include UARTs (Universal Asynchronous Receiver-Transmitters), SPI (Serial Peripheral Interface), I2C (Inter-Integrated Circuit), PWM (Pulse Width Modulation), ADC (Analog-to-Digital Converter), timers/counters, and more. These peripherals enable the microcontroller to interface with various devices and sensors, making it versatile for different applications.
5. Communication Interfaces: The microcontroller features multiple communication interfaces such as UART, SPI, and I2C, which enable seamless integration with other devices and systems.
6. Power Management: The LPC2148 includes power-saving modes, such as Idle and Power-down modes, which help to conserve energy and extend battery life in low-power applications.
7. Development Tools: The LPC2148 is supported by a range of development tools and software, including Keil MDK (Microcontroller Development Kit) and Proteus simulation software, which aid in the development and debugging of applications.
8. Package Options: The LPC2148 is available in various package options, including LQFP (Low Profile Quad Flat Package) and TQFP (Thin Quad Flat Package), offering flexibility in terms of board design and space requirements.

Overall, the LPC2148 microcontroller provides a robust and feature-rich platform for developing embedded systems. Its powerful processing capabilities, extensive peripheral set, and support from development tools make it a popular choice for a wide range of applications, including industrial automation, consumer electronics, IoT devices, and more.


## LCD:
An LCD is a flat-panel display technology that uses liquid crystals to produce visual output. It is commonly found in devices like calculators, watches, digital clocks, computer monitors, and more. LCDs offer several advantages, such as low power consumption, thin form factor, and the ability to display alphanumeric characters, symbols, and graphics.

LCD Pin Diagram:
•	VSS (Ground): Connect this pin to the ground or 0V reference of your power supply.
•	VDD (Power): This pin is connected to the power supply voltage, typically +5V or +3.3V.
•	V0 (Contrast): It controls the contrast of the display. Connect it to a variable resistor (potentiometer) to adjust the contrast.
•	RS (Register Select): This pin is used to select between data and command registers. When RS is high, data is interpreted as display data. When RS is low, data is treated as a command.
•	R/W (Read/Write): It determines the direction of data transfer. When R/W is high, data can be read from the LCD. When R/W is low, data can be written to the LCD.
•	E (Enable): The Enable pin enables the LCD to latch data present on its data lines. A falling edge (high to low transition) of the E pin is used to trigger the LCD to read the data lines.
•	D0-D7 (Data Lines): These pins are bi-directional data lines used for transferring commands and data between the microcontroller (or any controlling device) and the LCD. The number of data lines can vary depending on the LCD module, ranging from 4-bit to 8-bit data communication.
•	A (Anode): Connect this pin to the anode (positive terminal) of the backlight, if applicable.
•	K (Cathode): Connect this pin to the cathode (negative terminal) of the backlight, if applicable.
 
![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/ba9c3794-9403-45a9-809c-f5635c1fc5d7)


## Integrated Circuit (L293D):
The L293D is a popular integrated circuit (IC) commonly used to drive small DC motors or stepper motors in various electronic projects. It is specifically designed to provide bidirectional control (forward and reverse) of motors with high current and voltage requirements. 
•	Motor Driver: The L293D has two H-bridge circuits that can drive two DC motors independently or control a single stepper motor. Each H-bridge consists of four output transistors (two per motor coil) that can switch the direction of current flow to the motor.
•	Voltage and Current: The L293D is capable of handling voltages up to 36V and currents of up to 600mA (per channel). It provides sufficient power for small to medium-sized motors commonly used in robotics, hobby projects, and other applications.
•	Logic Compatibility: The IC is compatible with both TTL (Transistor-Transistor Logic) and CMOS (Complementary Metal-Oxide-Semiconductor) logic levels, making it compatible with a wide range of microcontrollers, such as Arduino, Raspberry Pi, and other digital systems.
•	Enable Pins: The L293D has enable pins (EN1 and EN2) that can be used to control the motor outputs. When these enable pins are high, the outputs are enabled, and when they are low, the outputs are disabled.
•	Protection Features: The L293D incorporates various protection features to ensure the safety and reliability of the motor and the IC itself. These include built-in clamp diodes for suppressing voltage spikes (back EMF) generated by the motor coils during switching and thermal shutdown protection to prevent overheating.
•	Package Options: The L293D is available in different package options, such as a 16-pin DIP (Dual Inline Package) or a surface-mount SOIC (Small Outline Integrated Circuit) package, allowing for flexibility in circuit board design and assembly.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/04483bdb-4d9b-4625-bb3e-16207d2fe251)

 
In Proteus, the L293D IC has the following pin configuration and functionality:
•	Pin 1 (1A): This is the input pin for controlling the direction of current flow for Motor 1.
•	Pin 2 (2A): This is another input pin for controlling the direction of current flow for Motor 1.
•	 Pin 3 (1Y): This is an output pin connected to the motor coil of Motor 1. It provides the current required to drive the motor in the specified direction.
•	Pin 4 (2Y): This is an output pin connected to the motor coil of Motor 1. It controls the direction of Motor 1.
•	Pin 5 (1Z): This is an output pin connected to the motor coil of Motor 2. It provides the current required to drive the motor in the specified direction.
•	Pin 6 (2Z): This is an output pin connected to the motor coil of Motor 2. It controls the direction of Motor 2.
•	Pin 7 (GND): This is the ground reference pin. Connect this pin to the ground of the circuit.
•	Pin 8 (1,2EN): This is the enable pin for both motors. When this pin is high (typically connected to Vcc1), the motor outputs (1Y, 2Y, 1Z, and 2Z) are enabled. When it is low (typically connected to GND), the motor outputs are disabled.
•	Pin 9 (3Z): This is an output pin connected to the motor coil of Motor 3. It provides the current required to drive the motor in the specified direction.
•	Pin 10 (4Z): This is an output pin connected to the motor coil of Motor 3. It controls the direction of Motor 3.
•	Pin 11 (3A): This is an input pin for controlling the direction of current flow for Motor 3.
•	Pin 12 (4A): This is another input pin for controlling the direction of current flow for Motor 3.
•	Pin 13 (NC): This pin is not connected internally and is usually left unconnected in the circuit.
•	Pin 14 (NC): This pin is not connected internally and is usually left unconnected in the circuit.
•	Pin 15 (Vcc1): This is the power supply pin for the logic section. Connect this pin to the logic power supply (5V or 3.3V).
•	Pin 16 (Vcc2): This is the power supply pin for the motor section. Connect this pin to the power supply providing the required voltage for the motors.

## Keypad Phone:
A keypad phone, also known as a feature phone or a basic phone, is a mobile phone that primarily focuses on voice calls and text messaging. It typically has a numeric keypad as the primary input method, consisting of buttons labeled with digits from 0 to 9 and additional keys for call-related functions like making and ending calls. Components needed:
•	Matrix Keypad: This is a grid of buttons arranged in rows and columns. Each button represents a digit or a character.
•	Microcontroller: You can use a microcontroller, such as Arduino or PIC, to interface with the keypad and process the button presses.
•	Display: A display, such as an LCD or LED display, can be used to show the entered digits or characters.

## DC Fan:
A DC fan, also known as a direct current fan, is a type of electric fan that operates on DC power. It is commonly used in electronic devices, cooling systems, and various applications where airflow is required. The basic principle of operation for a DC fan involves the conversion of electrical energy into mechanical energy to generate airflow. Here's a simplified explanation of how it works:
•	Power Source: A DC fan requires a direct current (DC) power source to operate. This power can be provided by a battery, a DC power supply, or by converting an alternating current (AC) power source into DC using a rectifier.
•	Motor: The heart of a DC fan is an electric motor, typically a brushless DC (BLDC) motor. BLDC motors are widely used in DC fans due to their efficiency, reliability, and precise control.
•	Stator: The motor's stator consists of a stationary set of coils that generate a magnetic field when current flows through them. The number and arrangement of the stator coils depend on the motor design.
•	Rotor: The rotor is a rotating part of the motor and is typically composed of permanent magnets or electromagnets. The rotor is placed inside the stator and is free to rotate.
•	Commutation: In a brushless DC motor, electronic commutation is used to control the motor's rotation. This is achieved through the use of Hall effect sensors or position sensors that detect the rotor's position and provide feedback to the motor controller.
•	Motor Controller: The motor controller is an electronic circuit that regulates the power supplied to the motor based on the feedback from the sensors. It controls the speed and direction of the fan by adjusting the voltage and current supplied to the motor.
•	Blades: The DC fan has blades or impellers attached to the motor's rotor. As the motor spins, the blades rotate, creating airflow.
•	Airflow: The rotation of the blades generates a pressure difference that causes air to move. This airflow can be used for cooling electronic components, ventilating spaces, or other applications depending on the fan's design and purpose.

By controlling the voltage and current supplied to the motor, the speed of the DC fan can be adjusted. Higher voltage and current result in faster rotation and increased airflow, while lower values reduce the speed and airflow. DC fans offer advantages such as energy efficiency, quiet operation, and precise control. They are widely used in electronic devices, computers, servers, automotive cooling systems, and many other applications that require effective cooling or airflow.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/088909ff-8770-426b-8f52-3f7ad55d6550)


## LM35:
The LM35 is a precision analog temperature sensor integrated circuit (IC) commonly used for temperature measurement in various applications. It provides an accurate and linear voltage output that is directly proportional to the temperature being measured. In Proteus, a software simulation tool, you can simulate the LM35 temperature sensor and use it in your virtual circuits. 

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/d2812a39-0bd9-47aa-ab52-20d182afc901)

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/410239d5-5dde-4fb3-bc19-b30f4c7f895c)

OMIH-SH-112L:
The Omron G5LE-1 series (also known as Omih-sh-112l) is a general-purpose power relay manufactured by Omron Corporation. It is commonly used in various applications to switch high-power loads using a low-power control signal. Here are some key features and specifications of the Omron G5LE-1 relay:

•	Coil Voltage: The Omron G5LE-1 relay is available in different coil voltage options, such as 5V DC, 12V DC, 24V DC, etc. The specific part number Omih-sh-112l refers to a 12V DC coil voltage variant.
•	Contact Configuration: The relay has a single-pole, single-throw (SPST) contact configuration. It means that it has one set of normally open (NO) contacts.
•	Contact Rating: The contact rating of the Omron G5LE-1 relay depends on the specific model. Common contact ratings include 10A or 16A at 250V AC, and 10A or 30A at 30V DC. It is important to select the appropriate relay based on the load requirements of your application.
•	Switching Mechanism: The relay utilizes an electromagnetic switching mechanism. When the coil is energized, it generates a magnetic field that attracts the armature, causing the contacts to close and complete the circuit. When the coil is de-energized, the contacts return to their normal state (open).
•	Mounting Style: The Omron G5LE-1 relay is commonly available in through-hole mounting style, which means it can be soldered onto a PCB (Printed Circuit Board) using through-hole soldering techniques.
•	Application Examples: The Omron G5LE-1 relay can be used in various applications, including industrial control systems, home automation, appliances, automotive electronics, power supplies, and more.
When using the Omron G5LE-1 relay in your circuit, ensure that you follow the datasheet and application guidelines provided by Omron to ensure proper operation and reliability.
 
 ![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/4b8bbc6e-e96b-49a3-bb3b-95409e2e42b0)

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/28e1fbba-96ed-4fda-a371-907e70370be3)

## Experiment and Results:

## 1. Password Protected Door Lock System:

## Circuit Diagram
 ![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/ac9ba53a-0c48-4184-b911-803d31f4b9ce)

## Components Used:
-	LCD Display
-	LPC2148
-	Integrated Circuit (IC L293D)
-	Keypad Phone
-	Keypad Calculator
-	Motor

## Code:
``` c
#include <lpc214x.h>
#include <string.h>
#include "timedelay.h"
#include "lcd.h"
#include "keypad.h"
#define bit(x) (1 << x)
char flag = 0;
char pwd[] = "3333";
void lock(void);
int main(void)
{
    char key[5];
    int con = 0;
    lcd_init();
    lcd_cmd(0x01);
    lcd_string("press 1 to cha-");
    lcd_cmd(0x01);
    lcd_string("nge password");
    flag = get_key();
    if (flag == '1')
    {
        lcd_cmd(0x01);
        lcd_string("New pwd : ");
        for (con = 0; con < 4; con++)
        {
            pwd[con] = get_key();
            lcd_string("*");
        }
        pwd[con] = 0;
    }
    while (1)
    {
        lcd_cmd(0x01);
        lcd_string("password:");
        // lcd_cmd(0xc0);
        for (con = 0; con < 4; con++)
        {
            key[con] = get_key();
            lcd_string("*");
        }
        key[con] = 0;
        if (strcmp(key, pwd) != 0)
        {
            lcd_cmd(0x20);
            lcd_cmd(0x01);
            lcd_string("Wrong password");
        }
        else
        {
            lock();
        }
    }
}
void lock(void)
{
    IO0DIR |= bit(19) | bit(20);
    lcd_cmd(0x01);
    lcd_string("lock is opening");
    IO0SET |= bit(19);
    timemdel(50);
    IO0CLR |= bit(19);
    timemdel(100);
    lcd_cmd(0x01);
    lcd_string("lock is closing");
    IO0SET |= bit(20);
    timemdel(50);
    IO0CLR |= bit(20);
}
```

## Output:
Step1: 
 

A new password is first put on the LCD, allowing the user to change the password for our home security system. The password can be established, and it mainly comprises of a four-digit pattern made up of either numbers ranging from 0 to 9 or the special characters * and #. The user of the Keypad phone will enter this sequence.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/70ba2fe7-ee9a-436e-89ac-7efb36abdfec)

Step2: 
 
The user is prompted to input the password after the new password has been set. This makes sure that the person entering is actually the user.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/23e0225d-c7a2-4209-b953-54ff7bbef364)

Step3: 
 
When the user enter the wrong password, the LCD displays that it is a “Wrong Password”.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/f33d8eaf-6830-427a-b1da-4c4a099dc499)

Step4: 
 
If the entered password is right the lock is opened which is mentioned in the LCD Display. This lock is automatically closed after some time.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/dac17156-d84e-46f1-b178-9db5383d466e)


## 2. Temperature Controlled DC Fan: 
## Circuit Diagram:

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/2c42ddf4-a975-4a42-8515-9d81e78b4f9a)

## Components Used:
•	Button
•	Cell
•	DC Fan
•	LM016L
•	LM35
•	LPC2138
•	OMIH-SH-112L

## Code:

``` c
#include <LPC214X.H>
#include <stdio.h> // for sprintf function
#include <stdlib.h> // for atoi function

#define LCD (0xFFFF00FF)
#define RS (1<<4)
#define RW (1<<5)
#define EN (1<<6)

void ADC_INIT(void);		 // Initial setup of ADC
int ADC(void);		   		 // Returns ADC Value
//int UART(void);				 // UART interface
void LCD_INIT(void);   		 // Initial setup of LCD
void LCD_CMD(char command);	 // Instruction to LCD
void LCD_STRING (char* msg); // String to LCD
void delay_ms(int count);	 // 1 milli second delay

int main (void)
  {		
	int ADC_val, prev = 0 , check = 0, temp_c, TEMP_LIMIT = 30,voltage ;
	char val[10];								 

	PINSEL0 = 0x00000000;
	IODIR0 |= 0X00100000;  // P0.20 as output for Relay
	IODIR0 &= 0XFFFEFFFF;  // P0.16 as input from switch

	ADC_INIT();  
	LCD_INIT(); 
	while (1)
	{
		ADC_val = ADC(); // Returns ADC Value
		voltage = (ADC_val * 3.3) / 10;  // Convert to voltage (assuming Vref = 3.3V)
    temp_c = (int)(voltage);
		if (prev != temp_c || check == 1)
		{
			voltage = (ADC_val * 3.3) / 10;  // Convert to voltage (assuming Vref = 3.3V)
			temp_c = (int)(voltage);
			sprintf(val," %dC",temp_c);// int into string
				 
			LCD_CMD(0x01);  // Display clear 
			LCD_STRING(val);
			LCD_CMD(0xC0);	// next line in display		 
				
			if (temp_c >= TEMP_LIMIT)
			{
				IOSET0 |= 0x00100000; // sets P0.20 for relay
				LCD_STRING(" Hot");
			}
			else
			{
				IOCLR0 |= 0x00100000; // clears P0.16 for relay
				LCD_STRING(" Normal");
			}
			prev = temp_c;
		}
		check = 0;
	}
  }
  
void ADC_INIT(void)
  {
	PINSEL1 &= 0xFF7FFFFF; // (PINSEL1<23rd bit> = 0)
	PINSEL1 |= 0x00400000; // (PINSEL1<22nd bit> = 1)
	//P0.27 is Configured as ADC Pin AD0.0
	PCONP |= (1<<12); // Enable Power/Clock to ADC0
  }

int ADC(void)
  {
  	unsigned int ADC_data;
	AD0CR = 0x00200700; // CLKDIV =(PCLK)/8, BURST=0, CLKS=11clks/10bits, PDN=1
	AD0CR|= 0x01;       // Enabling A/D Channel 0
	AD0CR |= (1<<24);   // Activate ADC Module (new conversion)
	//Wait for conversion to get over by monitoring 31th bit of A/D register
	while(!(AD0GDR & 0x80000000));  
	//Read 10 bit ADC Data ie RESULT = 10 Bit Data (15:6)
	ADC_data = (AD0GDR >> 6) & 0x3FF; 
	//Deactivate ADC Module ie START = 000 (Bits 26,25,24) (stop conversion)
	AD0CR &= 0xF8FFFFFF; 

	return ADC_data;
  }

	/*
int UART(void)
  {
  	unsigned int i=0 ,val;
	char data = 0, str[4];
	PINSEL0 |= 0x00000005; // Enable RxD0 and TxD0
	U0LCR = 0x83;   // 8 bits, no parity , 1 stop bits, DLAB = 1
	U0DLL = 97;     // 9600 Baud Rate @ 15MHZ VPB Clock 				   
	U0LCR = 0x03;   // DLAB = 0 
	while(data != 44) // if data received is not comma
      {
	  	// Wait until reception is over and UART0 is ready with data
		while(!(U0LSR & 0x01)); 
		data = U0RBR;  //Receive character
		// Wait until UART0 ready to send character
		while(!(U0LSR & 0x20)); 
		U0THR = data;  //Send character
		str[i] = data;
		i++;
	  }
	val = atoi(str); //converts string into integer
	return val;
  }
*/

void LCD_INIT(void)
{
	//P0.12 to P0.15 as output for LCD Data
	//P0.4,5,6 as output for RS, RW and EN 
	IO0DIR |= 0x0000F070; 
	delay_ms(20);	
	LCD_CMD(0x02);  // Initialize cursor to home position
	LCD_CMD(0x28);  // 4 - bit interface, 2 line, 5x8 dots 
	LCD_CMD(0x06);  // Auto increment cursor 
	LCD_CMD(0x0C);  // Display on cursor off 
	LCD_CMD(0x01);  // Display clear 
	LCD_CMD(0x80);  // First line first position 
}

void LCD_CMD(char command)
{
	IO0PIN = ( (IO0PIN & LCD) | ((command & 0xF0)<<8) ); //Upper nibble 
	IO0SET = EN; // EN = 1 
	IO0CLR = (RS|RW); // RS = 0, RW = 0 
	delay_ms(5); // 5 milli sec
	IO0CLR = EN; // EN = 0, RS and RW unchanged(RS = RW = 0)	 
	delay_ms(5);
	IO0PIN = ( (IO0PIN & LCD) | ((command & 0x0F)<<12) ); //Lower nibble 
	IO0SET = EN; // EN = 1 
	IO0CLR = (RS|RW); // RS = 0, RW = 0 
	delay_ms(5);
	IO0CLR = EN; // EN = 0, RS and RW unchanged(RS = RW = 0)	 
	delay_ms(5);	
}

void LCD_STRING (char* msg)
{
	unsigned int i=0;
	while(msg[i]!=0)
	{
		IO0PIN = ( (IO0PIN & LCD) | ((msg[i] & 0xF0)<<8) ); //Upper nibble
		IO0SET = (RS|EN); // RS = 1, EN = 1 
		IO0CLR = RW; // RW = 0 
		delay_ms(2); // 2 milli sec
		IO0CLR = EN; // EN = 0, RS and RW unchanged(RS = 1, RW = 0) 
		delay_ms(5);
		IO0PIN = ( (IO0PIN & LCD) | ((msg[i] & 0x0F)<<12) ); //lower nibble
		IO0SET = (RS|EN); // RS = 1, EN = 1 
		IO0CLR =  RW; // RW = 0 
		delay_ms(2);
		IO0CLR = EN; // EN = 0, RS and RW unchanged(RS = 1, RW = 0) 
		delay_ms(5);
		i++;
	}
}

void delay_ms(int count)
{
  int j=0,i=0;
  for(j=0;j<count;j++)
  { 
    for(i=0;i<1000;i++);
  }
}
```

## Output:

 
As the temperature is over 30 then it is detected to be hot and therefore, the DC Fan is turned on.

 ![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/353c461f-9a28-407a-8d0b-648e87148cc9)

When the temperature is detected to be less than 30o C then the temperature is taken as normal temperature and therefore the DC Fan is not turned on.

![image](https://github.com/Suraksha-Rajagopalan/HomeAutomation_Proteus/assets/91787553/6069a591-e0e3-415e-8a3c-472958a00495)

## Results And Conclusion:
The home automation system developed using LPC2148 microcontroller in Proteus successfully incorporates two features: a security lock system and a temperature-controlled DC fan. The system aims to enhance security and provide comfort by automatically managing access and regulating room temperature. In the security lock system, the user is prompted to enter a password during initialization. The entered password is stored, and subsequent attempts to unlock the system require the user to input the password. If the correct password is entered, the lock is opened, granting access to the secured area. On the other hand, if an incorrect password is provided, the lock remains closed, ensuring unauthorized individuals cannot gain entry. The temperature-controlled DC fan feature monitors the temperature using an onboard temperature sensor (such as LM35) connected to the microcontroller. The system continuously reads the temperature and compares it to a predefined threshold, in this case, 30 degrees Celsius. When the temperature exceeds the threshold, indicating a warm environment, the DC fan is automatically turned on to provide cooling. Conversely, when the temperature drops below the threshold, the fan is switched off to conserve energy. By integrating these features into a single system, the home automation solution provides a convenient and secure environment. Users can easily control access to their premises using the security lock system, while the temperature-controlled DC fan ensures optimal comfort and energy efficiency. The system demonstrates the capabilities of the LPC2148 microcontroller in managing multiple tasks and interacting with various peripherals.

In conclusion, the developed home automation system successfully combines security and temperature control functionalities. It offers convenience, efficiency, and peace of mind to homeowners. The system can be further expanded and customized to incorporate additional features such as remote access, motion detection, and integration with other smart home devices. The use of the LPC2148 microcontroller in Proteus enables a simulated testing environment for validation and future development of the home automation solution.

## Future Scope:
•	Enhanced Security Features: The project can be further developed to include advanced security features such as facial recognition, fingerprint scanning, or voice recognition for authentication. These additional security measures can provide even stronger access control and improve the overall security of the system.
•	Integration with IoT: The project can be integrated with an IoT (Internet of Things) platform, allowing users to control and monitor their home automation system remotely through a mobile app or web interface. This would enable homeowners to access and manage their security lock system and temperature-controlled fan from anywhere, providing greater convenience and flexibility.
•	Integration with Smart Home Devices: The home automation system can be integrated with other smart home devices such as smart lights, smart thermostats, or smart appliances. This integration would create a comprehensive smart home ecosystem where different devices can communicate with each other and be controlled centrally, providing a seamless and integrated user experience.
•	Energy Optimization: The project can incorporate energy optimization techniques by integrating energy monitoring sensors and algorithms. This would enable the system to monitor energy consumption patterns and optimize the operation of devices, including the DC fan, based on energy efficiency considerations. This feature can contribute to energy savings and environmental sustainability.
•	Voice Control and AI Integration: Integration of voice control capabilities and artificial intelligence (AI) algorithms can enhance the user experience and automation capabilities of the system. Users can control the security lock system and fan using voice commands, and AI algorithms can learn and adapt to user preferences, automatically adjusting temperature settings and fan speed based on user habits and environmental conditions.
