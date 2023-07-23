<div align="center">
<h1><strong>Home Automation Using Protetus</strong></h1>
</div>


## Abstract:
Due to their capacity to improve residential surroundings' levels of comfort, security, and energy efficiency, home automation systems have seen a substantial increase in popularity in recent years. The LPC2148 microcontroller is used in this project to demonstrate an integrated home automation system developed with Keil and Proteus. A temperature-controlled DC fan, an automatic fire alarm sensor with GSM, and a password-protected door lock system are the three main components of the system. By automatically altering the fan speed in response to the ambient temperature, the temperature-controlled DC fan guarantees the highest level of thermal comfort. In addition to ensuring effective cooling, this feature also conserves electricity by stopping unneeded fan running. An automated fire alarm sensor with GSM capabilities is built into the system to ensure maximum safety. The sensor detects the presence of smoke or heat during a fire and sets off an alarm. Additionally, it uses GSM to deliver an immediate SMS message to the user's mobile phone, enabling quick alerts and swift action to reduce potential fire threats. To further increase security, the system includes a password-protected door lock mechanism. Users can only enter the right password on a keypad to get entrance to their residences. With the help of this system, unauthorized access is guaranteed to be stopped, giving you security and protection from invaders. This home automation system gives homeowners convenience, security, and safety by fusing these elements. A dependable and effective platform for controlling and monitoring various home automation features is provided by the implementation on the LPC2148 microcontroller and the use of Keil and Proteus.


## Keywords: 
Keil, lpc2148, Proteus, DC fan, GSM (Global System for Mobile Communications).

## Introduction:
Welcome to the world of home automation, where convenience and safety meet technological innovation. In this project, we have implemented a sophisticated home automation system using Keil and Proteus, powered by the LPC2148 microcontroller. Our system incorporates several key features that enhance the comfort, security, and efficiency of your living space. One of the standout features of our home automation system is the temperature-controlled DC fan. This smart fan adjusts its speed based on the ambient temperature, ensuring optimal airflow and creating a pleasant environment while saving energy. Say goodbye to manually adjusting fan speed and hello to automated comfort. Safety is paramount in any home, which is why our system includes an automated fire alarm sensor with GSM capabilities. In the event of a fire, this sensor detects the presence of smoke or heat and immediately sends a notification to your mobile device via GSM technology. Early detection is crucial, and our fire alarm system ensures swift action can be taken to minimize damage and protect your loved ones. For an added layer of security, we have integrated a password-protected door lock system. With this feature, you can conveniently control access to your home, granting entry only to authorized individuals. The door lock system offers peace of mind, knowing that your home is protected against unauthorized access. By combining these advanced features in a unified home automation system, we aim to enhance your daily life with comfort, convenience, and safety. Our implementation using the LPC2148 microcontroller, along with the support of Keil and Proteus, guarantees a seamless and efficient operation of the entire system. Get ready to experience the future of home automation, where technology works in harmony to simplify your life and create a secure haven for you and your family. 




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

- Button
- Cell
- DC Fan
- LM016L
- LM35
- LPC2138
- OMIH-SH-112L

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
