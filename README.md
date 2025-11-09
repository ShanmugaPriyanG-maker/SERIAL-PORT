
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
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
 WAIT:JNB TI, WAIT
 CLR TI 
 END


```

### (ii) Serial Port to Transfer a Message

```
ORG 00H 
MOV DPTR, #4500H
MOV TMOD, #20H 
MOV TH1, #0FDH 
MOV SCON, #40H 
SETB TR1 
AGAIN: MOVX A,@DPTR
MOV SBUF, A
 WAIT:JNB TI, WAIT
 CLR TI 
 INC DPTR
 SJMP AGAIN
 END


```

### OUTPUT:

### (i) Serial Port Transfer a Single Character

<img width="886" height="362" alt="MPMC SERIAL " src="https://github.com/user-attachments/assets/d9b0a5b5-c2f7-4fbb-9c5c-49a950bb749e" />

### (ii) Serial Port to Transfer a Message

<img width="886" height="362" alt="MPMC serial port" src="https://github.com/user-attachments/assets/8c607832-376a-4ade-b604-a2e0d1e98cc7" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
