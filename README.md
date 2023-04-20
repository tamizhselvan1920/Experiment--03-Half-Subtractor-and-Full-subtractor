# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
STEP 1: Use module projname(input,output) to start the Verilog programmming.

STEP 2: Assign inputs and outputs using the word input and output respectively.

STEP 3: Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

STEP 4: Use each output to represnt onre for differnce and the other for borrow.

STEP 5: End the verilog program using keyword endmodule.




 

## Program:
```
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Tamizhselvan R
RegisterNumber: 212222230158
*/
HALF SUBRACTOR:
module subractor(A,b,diff,borrow);
input A,b;
output diff,borrow;
wire X;
xor(diff,A,b);
not(X,A);
and(borrow,X,b);
endmodule

FULL SUBTRACTOR:
module fullsub(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```



## Output:
##HALF SUBTRACTOR:

 
## Truthtable:

![230771064-4f02454c-bf80-4cf2-929e-0dc21506bffc](https://user-images.githubusercontent.com/121148386/233366930-02b747ea-0eab-434d-b1c1-723cb3ad41f3.png)

##LOGIC SYMBOL:
![230771153-9f852790-306e-47d7-b964-acefaaf248cb](https://user-images.githubusercontent.com/121148386/233366998-d818a026-0857-49e1-b42d-98dee7e24063.png)



##  RTL realization

![230771156-75435f12-3b6a-4df7-a28b-d63cb741cfe7](https://user-images.githubusercontent.com/121148386/233367069-c9df9011-d26b-434c-a859-bb619f6038e3.png)


## Timing diagram 

![230771165-a117a588-d83b-4d4e-9f87-eaa5f3f5b87e](https://user-images.githubusercontent.com/121148386/233367115-d423faf4-d825-4a81-b603-e58bd1779983.png)

#FULL SUBTRACTOR:

TRUTH TABLE:
![230771220-66c05ba6-028b-4b64-a4e0-3e57c978b148](https://user-images.githubusercontent.com/121148386/233367243-a99687d2-40be-4aff-a6ba-e001516e73fd.png)

LOGIC SYMBOL:
![230771242-ddac95bd-1a72-41d6-9f68-c9b9ce1beeaf](https://user-images.githubusercontent.com/121148386/233367371-9e968f8e-e6bc-458e-91b6-f38da1f0004d.png)
##RTL REALIZATION:

![230771268-afb60885-cd82-4ab9-bd83-00931e0f46cc](https://user-images.githubusercontent.com/121148386/233367492-4cc501e4-9888-427f-8b19-3299d2c7115f.png)

TIMING DIAGRAM:
![230771313-69d435b1-7308-42cd-93bb-217667842646](https://user-images.githubusercontent.com/121148386/233367577-0fee7d8d-d727-4bac-b608-7f9fcda67021.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
