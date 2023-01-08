AIM:
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

Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

 Logic Diagram
Procedure
 Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

PROGRAM 1:

module expfour(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3;

assign f1 = (~c&~b&~a);

assign f2 = (~d&~c&~a);

assign f3 = (c&~(~b)&~a);

assign f= f1&~f2&~f3;

endmodule

PROGRAM 2:

module expfourtwo(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3,f4;

assign f1 = c&(~b)&a;

assign f2 = d&(~c)&a;

assign f3 = c&(~b)&a;

assign f4 = ~(f1|f2|f3);

not(f,f4);

endmodule


RTL REALIZATION

OUTPUT

PROGRAM 1

![PROGRAM  1](https://user-images.githubusercontent.com/121557017/211178676-9cd659c4-2403-4885-91aa-d8e22263b8bf.png)



PROGRAM 2

![Screenshot (25)](https://user-images.githubusercontent.com/121557017/211178680-261fc6ad-0ede-4ba9-8401-a83a72852456.png)


Developed by: M.ABINAYA
RegisterNumber:22008642  


TRUTH TABLE 

PROGRAM 1

![TRUTH TABLLE 1](https://user-images.githubusercontent.com/121557017/211178788-cf94f7ec-0f19-468c-92e8-52ac04d7edd4.png)


PROGRAM 2

![TRUTH TABLE 2](https://user-images.githubusercontent.com/121557017/211178839-8d6940e3-6f8e-4619-b18e-d2769499823a.png)


TIMING DIAGRAM

PROGRAM 1



![TIMING DIAGRAM 1](https://user-images.githubusercontent.com/121557017/211178903-8bf5f052-13d7-43c0-8559-5b8602127bb8.png)


PROGRAM 2

![TIMING DIAGRAM 2](https://user-images.githubusercontent.com/121557017/211178942-3f9d6ee1-958d-46ba-98dd-940bc493620b.png)



 Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
