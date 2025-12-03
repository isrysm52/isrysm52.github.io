---
title: Code
tags:
- tag1
- tag2
---

## Overview

This is the code of the updated schematic for the motor system. This shows how the microcontroller is programed to take in information from other microchips and use it to open, close, and stop a door. 

Here is the code: 

```
 /*
 * MAIN Generated Driver File
 * 
 * @file main.c
 * 
 * @defgroup main MAIN
 * 
 * @brief This is the generated driver implementation file for the MAIN driver.
 *
 * @version MAIN Driver Version 1.0.2
 *
 * @version Package Version: 3.1.2
*/

/*
© [2025] Microchip Technology Inc. and its subsidiaries.

    Subject to your compliance with these terms, you may use Microchip 
    software and any derivatives exclusively with Microchip products. 
    You are responsible for complying with 3rd party license terms  
    applicable to your use of 3rd party software (including open source  
    software) that may accompany Microchip software. SOFTWARE IS ?AS IS.? 
    NO WARRANTIES, WHETHER EXPRESS, IMPLIED OR STATUTORY, APPLY TO THIS 
    SOFTWARE, INCLUDING ANY IMPLIED WARRANTIES OF NON-INFRINGEMENT,  
    MERCHANTABILITY, OR FITNESS FOR A PARTICULAR PURPOSE. IN NO EVENT 
    WILL MICROCHIP BE LIABLE FOR ANY INDIRECT, SPECIAL, PUNITIVE, 
    INCIDENTAL OR CONSEQUENTIAL LOSS, DAMAGE, COST OR EXPENSE OF ANY 
    KIND WHATSOEVER RELATED TO THE SOFTWARE, HOWEVER CAUSED, EVEN IF 
    MICROCHIP HAS BEEN ADVISED OF THE POSSIBILITY OR THE DAMAGES ARE 
    FORESEEABLE. TO THE FULLEST EXTENT ALLOWED BY LAW, MICROCHIP?S 
    TOTAL LIABILITY ON ALL CLAIMS RELATED TO THE SOFTWARE WILL NOT 
    EXCEED AMOUNT OF FEES, IF ANY, YOU PAID DIRECTLY TO MICROCHIP FOR 
    THIS SOFTWARE.
*/
#include "mcc_generated_files/system/system.h"
#include <xc.h>
#include "stdio.h"

/*
    Main application
  
 
 
*/

void motor_stop(void)
{
        IO_RC4_SetLow();
        IO_RC6_SetLow();
}
//
void motor_cw(void)
{
        IO_RC4_SetLow();
        IO_RC6_SetHigh(); 
}
//
void motor_ccw(void)
{
        IO_RC4_SetHigh();
        IO_RC6_SetLow();    
}

void motor_on(void)
{
    IO_RD5_SetHigh();
    IO_RF7_SetHigh();
    IO_RF4_SetHigh();
    
        IO_RD0_SetHigh();
        IO_RD1_SetLow();
        //LED Red Off, Green On
}
void motor_off(void)
{
    IO_RD5_SetLow();
    IO_RF7_SetLow();
    IO_RF4_SetLow();
    
        IO_RD0_SetLow();
        IO_RD1_SetHigh();
        //LED Red On, Green Off
}

void motor_problem(void)
{
    IO_RD5_SetLow();
    IO_RF7_SetLow();
    IO_RF4_SetLow();
    
        IO_RD1_SetHigh();
        IO_RD0_SetHigh();
        //LED Red On, Green On
}

void motor_search(void)
{
        uint16_t Fds = PORTDbits.RD6; 
            IO_RD6_GetValue();
    //Rear distance sensor
        uint16_t Rds = PORTDbits.RD7; 
            IO_RD7_GetValue();
    //Flex sensor
        uint16_t Fs = PORTBbits.RB5; 
            IO_RB5_GetValue();
    //Rotary sensor
        uint16_t Rs = PORTFbits.RF5;    
            IO_RF5_GetValue();
}



int main(void)
{
    SYSTEM_Initialize();
    // If using interrupts in PIC18 High/Low Priority Mode you need to enable the Global High and Low Interrupts 
    // If using interrupts in PIC Mid-Range Compatibility Mode you need to enable the Global Interrupts 
    // Use the following macros to: 

//    PWM1_16BIT_Enable();
//    PWM2_16BIT_Enable();
//    PWM3_16BIT_Enable();
    ADC_Initialize();
    ADC_Enable();
    
    ADC_ChannelSelect(ADC_CHANNEL_ANA0);
    // Enable the Global Interrupts 
    //INTERRUPT_GlobalInterruptEnable(); 
    
    
    //Motor Speed
        uint16_t Speed = 200;
    //Motor power
        uint16_t Motor_Power = 0;
    //Front distance sensor
        uint16_t Fds = PORTDbits.RD6; 
    //Rear distance sensor
        uint16_t Rds = PORTDbits.RD7; 
    //Flex sensor
        uint16_t Fs = PORTBbits.RB5; 
    //Rotary sensor
        uint16_t Rs = PORTFbits.RF5; 
    //Grabbing motor movement
        //ANSELCbits.ANSELC6 = 1;
        //ANSELDbits.ANSELD4 = 1;
                
        
        
        
        
    // Disable the Global Interrupts 
    //INTERRUPT_GlobalInterruptDisable(); 

        Rds = 1;
        Rs = 0;
        Fds = 0;
        Fs = 0;
        
                PORTDbits.RD6 == 0; 
                PORTDbits.RD7 == 0;
                PORTBbits.RB5 == 0;
                PORTFbits.RF6 == 0;
                PORTFbits.RF5 == 0;
                
        //IO_RD1_SetHigh();
        //IO_RF3_SetLow();

    while(1)
    {
        // Read ADC (0?1023)
            //Speed = ADC_ConversionResultGet(IO_RA0);
       // IO_RD0_SetLow();
       // IO_RD1_SetHigh();
        //LED Red On, Green Off
        //motor_search();

        
        // Code to test the motor to rotate from one side to the next to show bidirectional movement. 
//                    if(Rds == 0 && Fds == 0 && Fs == 0 && IO_RF2_GetValue() == 0)
//            {
//               motor_stop();
//               motor_off();
//               IO_RF2_GetValue();
//        
//            }
//                    if(Rds == 1 && Fds == 0 && Fs == 0 && IO_RF2_GetValue() == 1)
//            {
//               motor_ccw();
//               motor_on();
//            IO_RF2_GetValue();
//        
//            }
//                    if(Rds == 1 && Fds == 0 && Fs == 0 && IO_RF2_GetValue() == 0)
//            {
//               motor_cw();
//               motor_on();
//            IO_RF2_GetValue();
//        
//            }
//                    if(Rds == 1 && Fds == 1 && Fs == 0 && Rs == 0)
//            {
//               motor_stop();
//               motor_problem();
//            IO_RF2_GetValue();
//        
//            }                    
                    
                    
                    
           // if(PORTDbits.RD6 == 0 && PORTDbits.RD7 == 0 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 0 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetLow();
               //IO_RC6_SetLow();
               //Motor is opening
              // motor_stop();
               //motor_off();
               //motor_search();
        
            }
             if(PORTDbits.RD6 == 1 && PORTDbits.RD7 == 0 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 0 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetHigh();
               //IO_RC6_SetLow();
                motor_cw();
               motor_on();
               //motor_search();
               
            }
            else if(PORTDbits.RD6 == 1 && PORTDbits.RD7 == 0 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 1 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetLow();
               //IO_RC6_SetHigh();
                motor_ccw();
               motor_on();
               //motor_search();
               
              
            }
            else if(PORTDbits.RD6 == 0 && PORTDbits.RD7 == 1 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 0 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetHigh();
               //IO_RC6_SetLow();
                motor_cw();
               motor_on();
               motor_search();
                              
            }
            else if(PORTDbits.RD6 == 0 && PORTDbits.RD7 == 1 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 1 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetLow();
               //IO_RC6_SetHigh();
                motor_ccw();
               motor_on();
               //motor_search();
                
            }
            else if(PORTDbits.RD6 == 0 && PORTDbits.RD7 == 0 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 1 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetLow();
               //IO_RC6_SetHigh();
                motor_ccw(); 
               motor_on();
               //motor_search();
                              
            }
            else if(PORTDbits.RD6 == 0 && PORTDbits.RD7 == 0 && PORTBbits.RB5 == 0 && PORTFbits.RF6 == 0 && PORTFbits.RF5 == 1)
            {
               //IO_RD4_SetHigh();
               //IO_RC6_SetLow();
                motor_cw(); 
               motor_on();
               //motor_search();
                              
            }
            else if(PORTDbits.RD6 == 0 && PORTDbits.RD7 == 0 && PORTBbits.RB5 == 1 && PORTFbits.RF6 == 0 && PORTFbits.RF5 == 0)
            {
               //IO_RD4_SetHigh();
               //IO_RC6_SetLow();
                motor_ccw(); 
               //motor_on();
                IO_RC7_SetLow();
                IO_RD0_SetLow();
               //motor_search();
                              
            }
            else
            {
               //IO_RD4_SetLow();
               //IO_RC6_SetLow();
               motor_stop();
               motor_problem();
               //motor_search();
           
            }

        //motor_search();
        
    }    
}




////            PWM1_16BIT_SetSlice1Output1DutyCycleRegister(Speed);
////            PWM1_16BIT_LoadBufferRegisters();
////            PWM2_16BIT_SetSlice1Output1DutyCycleRegister(Speed);
////            PWM2_16BIT_LoadBufferRegisters();
////            PWM3_16BIT_SetSlice1Output1DutyCycleRegister(Speed);
////            PWM3_16BIT_LoadBufferRegisters();
////            PWM1_16BIT_SetSlice1Output2DutyCycleRegister(Speed);
////            PWM1_16BIT_LoadBufferRegisters();
////            PWM2_16BIT_SetSlice1Output2DutyCycleRegister(Speed);
////            PWM2_16BIT_LoadBufferRegisters();
////            PWM3_16BIT_SetSlice1Output2DutyCycleRegister(Speed);
////            PWM3_16BIT_LoadBufferRegisters();


//    //analogWrite(ANSELCbits.ANSELC6, Speed);

////    uint16_t forward = 0;
////    uint16_t backward = 1; 
////            PWM1_16BIT_SetSlice1Output1DutyCycleRegister(Speed);
////            PWM1_16BIT_LoadBufferRegisters();
////            PWM2_16BIT_SetSlice1Output1DutyCycleRegister(Speed);
////            PWM2_16BIT_LoadBufferRegisters();
////            PWM3_16BIT_SetSlice1Output1DutyCycleRegister(Speed);
////            PWM3_16BIT_LoadBufferRegisters();
////            PWM1_16BIT_SetSlice1Output2DutyCycleRegister(Speed);
////            PWM1_16BIT_LoadBufferRegisters();
////            PWM2_16BIT_SetSlice1Output2DutyCycleRegister(Speed);
////            PWM2_16BIT_LoadBufferRegisters();
////            PWM3_16BIT_SetSlice1Output2DutyCycleRegister(Speed);
////            PWM3_16BIT_LoadBufferRegisters();
////
```


Here is a zip folder for the program [here](). 



