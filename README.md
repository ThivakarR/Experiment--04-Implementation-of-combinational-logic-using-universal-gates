# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram

## Procedure

1. Create a project with required entities.

2. Create a module along with respective file name.

3. Run the respective programs for the given boolean equations. 

4. Run the module and get the respective RTL outputs. 

5. Create university program(VWF) for getting timing diagram. 

6. Give the respective inputs for timing diagram and obtain the results. 
## Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: 
RegisterNumber:  
```
Using NAND Operation
```
module expfour(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(~c & b & a);
assign q=(~d & c & ~a);
assign r=(c & ~b & a);
assign f=(~(~p & ~q & ~r));
endmodule
```
Using NOR operation
```
module expfourone(a,b,c,d,f);
input a,b,c,d;
output f;
wire x,y,z;
assign x=( c & ~b & a);
assign y=( d & ~c & a);
assign z=( c & ~b & a);
assign f=(~(~( x | y | z)));
endmodule
```
## NAND Operation:

### RTL:
![image](https://user-images.githubusercontent.com/118348224/211159814-4549e0c9-5b54-429d-b758-49bde1096cf6.png)

### Timing Diagram:

![image](https://user-images.githubusercontent.com/118348224/211160402-c4a2efc3-aa2b-4cb2-a655-acb51d72ae0d.png)


### Truth table:

![image](https://user-images.githubusercontent.com/118348224/211159994-5ea3e9da-6a89-49ea-85e5-8ffe0cf89c4a.png)

## NOR Operation:

### RTL:
![image](https://user-images.githubusercontent.com/118348224/211160055-6642dfd4-4840-4dff-ab81-645d99211ab2.png)

### Timing Diagram:

![image](https://user-images.githubusercontent.com/118348224/211160133-06ae4353-28d5-482d-a121-1e9d79287569.png)

### Truth table:

![image](https://user-images.githubusercontent.com/118348224/212308861-bf2e1090-26bc-436d-8fd6-c1a348619833.png)
## Result:
Thus, the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
