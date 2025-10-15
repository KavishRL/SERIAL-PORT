
# Serial Transfer of Single Byte / Character using 8051 (Keil)
## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.
## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  
## PROGRAM
### (i) Serial Port Transfer a Single Character
```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
WAIT:JNB TI, WAIT
CLR TI 
END
```
### (ii) Serial Port to Transfer a Message
```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="KAVISH";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<17;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}
```
### OUTPUT:
<img width="1675" height="1060" alt="image" src="https://github.com/user-attachments/assets/4098e103-f655-47c1-ad9c-6992dba525e7" />


<img width="1022" height="920" alt="image" src="https://github.com/user-attachments/assets/2bafb2d7-22f6-4079-a0cf-584982d8be46" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
