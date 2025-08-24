# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
```
CMC
LDA 4200H
MOV B, A
LDA 4201H
ADD B
STA 4300H
HLT
```

### Output:
<img width="1900" height="781" alt="ADDITION" src="https://github.com/user-attachments/assets/b3cde32c-f7c2-44b5-aef9-b46ebbddc548" />

<img width="1879" height="747" alt="ADDITION 1" src="https://github.com/user-attachments/assets/d7a2f800-cb39-4f28-819e-30edabbf85a6" />

![ADDITION EXPLANATION](https://github.com/user-attachments/assets/a4deed1b-7b2c-45be-a139-9ec9ab4d60b3)


### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
CMP C
MOV B, A
MOV A, C
SWAP:
SUB B
STA 4300H
HLT
```

### Output:
<img width="1808" height="733" alt="SUBTRACTION" src="https://github.com/user-attachments/assets/bae8585f-49b2-4cee-a8e4-b6e340572ec2" />

<img width="1810" height="729" alt="SUBTRACTION1" src="https://github.com/user-attachments/assets/19a24eeb-8db2-4368-9d96-bff5636efdb1" />

![SUBTRACTION EXPLANTION](https://github.com/user-attachments/assets/2b1729ae-f858-4729-a3ae-88e5123871ac)



### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
```
LDA 4200H
MOV C, A
LDA 4201H
MOV B, A
MVI A, 00H
LOOP: ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
```

### Output:
<img width="1812" height="724" alt="MULTIPLICATION" src="https://github.com/user-attachments/assets/01d35af8-d0d9-494a-8f8c-faf9a36cd0f5" />

<img width="1815" height="734" alt="MULTIPLICATION 1" src="https://github.com/user-attachments/assets/855578d5-7eea-409b-a6a5-b452376e0236" />

![MULTIPLICTION EXPLANATION1](https://github.com/user-attachments/assets/4d0584fd-7412-4451-ac4c-9d28c898559d)

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
```
LDA 4200H
MOV C,A
LDA 4201H
MOV B,A
MVI A,00H
LOOP: MOV A,C
CMP B
JC END
SUB B
MOV C,A
INR D
JMP LOOP
END: MOV A,D
STA 4300H
MOV A,C
STA 4301H
HLT
```

### Output:
<img width="1810" height="739" alt="DIVISION" src="https://github.com/user-attachments/assets/bb693a5f-5ead-4f33-8349-6e3aa13a46ef" />

<img width="1806" height="737" alt="DIVISION1" src="https://github.com/user-attachments/assets/f5c76d6a-62ea-4bbd-9147-31f153026997" />

![DIVISION EXPLANATION](https://github.com/user-attachments/assets/e61ee93b-ee4c-4c37-a62b-5dbbf4e1f81d)




## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

