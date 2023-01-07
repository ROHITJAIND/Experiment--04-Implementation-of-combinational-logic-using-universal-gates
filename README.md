Developed by : ROHIT JAIN D  
Reference No : 22005894  

## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.  

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate  
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate  
## Equipments Required:  
- Hardware  
  - PCs
  - Cyclone II 
  - USB flasher
- Software
  - Quartus prime
## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate.  
So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one.   
By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR.   
So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed.  
This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression.   
Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'  

## Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate.  
So its output is complement of the output of an OR gate.This gate can have minimum two inputs, output is always one.  
By using only NOR gates, we can realize all logic functions:AND, OR, NOT, Ex-OR, Ex-NOR, NAND.   
So this gate is also called universal gate.Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem.  
The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.  

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Procedure  
- Create a project with required entities.
- Create a module along with respective file name.
- Run the respective programs for the given boolean equations.
- Run the module and get the respective RTL outputs.
- Create university program(VWF) for getting timing diagram.
- Give the respective inputs for timing diagram and obtain the results.
## Program:
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.  
- ## COMBINATION 1 USING NAND GATE
```
module combone(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P=(~(~C & B & A));
assign Q=(~(~D & C & A));
assign R=(~(C & ~B & A));
assign F=~(P & Q & R);
endmodule
```  

- ## COMBINATION 2 USING NOR GATE
```
module combtwo(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = (C & ~B & A);
assign Q = (D & ~C & A);
assign R = (C & ~B & A);
assign S = (~(P | Q | R));
assign F = (~s);
endmodule
```
## Output:
## COMBINATION 1:
- ## RTL realization:
![Screenshot_20230107_074607](https://user-images.githubusercontent.com/118707073/211157437-16b088b7-accf-468e-8a80-7868d16912db.png)

- ## Timing Diagram:  
![Screenshot_20230107_080738](https://user-images.githubusercontent.com/118707073/211157446-ad7b8560-55c1-45b6-a6b2-735efc7f1a60.png)

- ## Truth Table:  
![Screenshot_20230107_104520](https://user-images.githubusercontent.com/118707073/211162655-b33052f6-b805-4520-b784-18d258b54e96.png)


## COMBINATION 2:

- ## RTL realization:
![Screenshot_20230107_093811](https://user-images.githubusercontent.com/118707073/211160189-75cc6000-ae61-4f72-a32b-04d20ba3bb6a.png)

- ## Timing Diagram: 
![Screenshot_20230107_104759](https://user-images.githubusercontent.com/118707073/211162693-56338373-fcce-4cc3-814e-ca88e74b8ffd.png)

- ## Truth Table:
![Screenshot_20230107_104317](https://user-images.githubusercontent.com/118707073/211162664-5f406fba-3204-441a-a687-6ce3244fafc6.png)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
