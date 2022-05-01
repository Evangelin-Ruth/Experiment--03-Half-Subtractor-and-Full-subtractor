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
1.Use module projname(input,output) to start the Verilog programmming.
2.Assign inputs and outputs using the word input and output respectively.
3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4.Use each output to represnt onre for differnce and the other for borrow.
5.End the verilog program using keyword endmodule.


## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Evangelin.S 
RegisterNumber:  212221230025
*/
```
HALF SUBTRACTOR

module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

FULL SUBTRACTOR

module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```

## Output:
## Half Subtractor:
### Logic Symbol
![image](https://user-images.githubusercontent.com/94219798/166142615-d4ce33cc-826d-4a9e-8159-a06e5c38380a.png)

## Truthtable

![image](https://user-images.githubusercontent.com/94219798/166142669-a98d262e-cdc2-4a7f-b64c-d96c3ab350c6.png)


##  RTL realization
![image](https://user-images.githubusercontent.com/94219798/166142677-2435a97c-dc0c-4635-a72c-03a5329b7e14.png)


## Timing diagram 
![image](https://user-images.githubusercontent.com/94219798/166142686-cd06c600-59e4-462a-9789-672b93329a3b.png)

## Full Suubtractor:
### Logic Symbol
![image](https://user-images.githubusercontent.com/94219798/166142821-d02cb156-0df7-4ad6-bdc5-73042415ccaf.png)

## Truthtable
![image](https://user-images.githubusercontent.com/94219798/166142832-68652e15-1fd1-4783-a1b3-69cd74c70b2a.png)

## RTL realization
![image](https://user-images.githubusercontent.com/94219798/166142845-9672fbb8-496d-4f1d-a959-dcca467a62d8.png)

## Timing diagram
![image](https://user-images.githubusercontent.com/94219798/166142858-1b0f3a29-ee79-4c6f-9c5a-7aa3bb6d3b83.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
