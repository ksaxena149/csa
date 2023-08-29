# Combinational Circuits
### Full Adder
![[Drawing 2023-08-11 09.06.14.excalidraw]]
Truth table
![[Drawing 2023-08-07 11.06.37.excalidraw 1]]
s = x xor y xor z
c = xy+yz+xz
c = x(y+z)+yz
![[Drawing 2023-08-11 09.13.14.excalidraw]]
#### Sir method
c = xy + x'yz + xy'z
xy+z(x'y+y'x)
xy+z(x (**xor**) y)
### S
![[Drawing 2023-08-11 09.29.25.excalidraw]]
### C 
![[Drawing 2023-08-11 09.24.36.excalidraw]]

![[Half Adder]]
### 4 Bit half adder
![[4-bit_HAdder]]
### Questions
1) Design a 4 bit binary adder using full adder
![[4bit-FAdder]] A = 1101
B = 0101
Addition: $A+B$
Subtraction: 
$A-B$
$A+(-B)$
$A+\text{2's comp} (B)$
$A + B' + 1$
#### HW
2) Draw a 4 bit subtractor circuit using full adder
![[4bit-Subtractor]]

3) Design a 4 bit binary decrementer
$A - 1$
$A_3A_2A_1A_0 + 1110 + 1$
$A_3A_2A_1A_0 + 1111$
![[Drawing 2023-08-16 11.31.05.excalidraw]]
Ex - 1101
![[Drawing 2023-08-16 11.31.05.excalidraw]]
4) Design a circuit that can add and subtract two 4 bit binary numbers. Circuit uses a control signal C as per the following table:
![[Drawing 2023-08-16 11.48.13.excalidraw]]
__ans__
![[Drawing 2023-08-16 11.50.05.excalidraw]]
_If we want to flip bit when input is 1 and not flip when input is 0 we will use XOR_

---
# Multiplexer
Multiple inputs and single output
![[Multiplexer]]
### How will input be selected?
Through select lines
#### 2 Variables
| S1  | S2  | Y   |
| --- | --- | --- |
| 0   | 0   | $I_0$  |
| 0   | 1   | $I_1$  |
| 1   | 0   | $I_2$  |
| 1   | 1   | $I_3$    |
#### 3 Variables
| S1  | S2  | S3  | Y   |
| --- | --- | --- | --- |
| 0   | 0   | 0   | $I_0$  |
| 0   | 0   | 1   | $I_1$  |
| 0   | 1   | 0   | $I_2$  |
| 0   | 1   | 1   | $I_3$  |
| 1   | 0   | 0   | $I_4$  |
| 1   | 0    | 1    | $I_5$    |
| 1   |  1   |  0   |  $I_6$   |
| 1    |   1  |  1   |  $I_7$   |

#### Logic Diagram
![[Drawing 2023-08-21 11.40.18.excalidraw]]
#### Design a 4 bit arithmetic circuit that can perform various arithmetic operations like Addition, Subtraction, Add with carry, Increment, Decrement
![[Drawing 2023-08-22 14.05.23.excalidraw]]

| Operation | Equation |
| --------- | -------- |
| Add       | A+B      |
| Subtract  | A+B'+1   |
| Increment | A+1      |
| Decrement | A-1         |

| $S_1$ | $S_0$ | $C_{in}$ | Equation | Operation            |
| --- | --- | ---- | -------- | -------------------- |
| 0   | 0   | 0    | A+B      | Addition             |
| 0   | 0   | 1    | A+B+1    | Addition with carry  |
| 0   | 1   | 0    | A+B'     | Subtract with borrow |
| 0   | 1   | 1    | A+B'+1   | Subtract             |
| 1   | 0   | 0    | A        | Transfer             |
| 1   | 0   | 1    | A+1      | Increment            |
| 1   | 1   | 0    | A-1      | Decrement            |
| 1   | 1   | 1    | A        | Transfer                     |

---
# Flip Flop
__Flip Flops__ are cells that can store data
## SR (Set Reset)
![[Drawing 2023-08-22 14.47.01.excalidraw]]
### Characteristic Table

| Set | Reset |    Q(t+1)     |
|:--: |:-----:|:-------------:|
| 0   |   0   |     Q(t)      |
| 0   |   1   |       0       |
| 1   |   0   |       1       |
| 1   |   1   | Indeterminate |
Output will change only when clock changes from 0 to 1, they are _Positive edge triggered_ 
_Negative edge triggered_ output changes when clock changes from 1 to 0
## D Flip Flip
D stands for data
![[Drawing 2023-08-23 11.21.11.excalidraw]]

| D   | Q(t+1) |
| :-: | :----: |
| 0   | 0      |
| 1   | 1       |
## JK Flip Flop
![[Drawing 2023-08-23 11.29.50.excalidraw]]

| J   | K   | Q(t+1) |
| --- | --- | ------ |
| 0   | 0   | Q(t)   |
| 0   | 1   | 0      |
| 1   | 0   | 1      |
| 1   | 1   | Q'(t)       |
## T (Toggle)
![[Drawing 2023-08-23 11.32.56.excalidraw]]

| T   | Q(t+1) |
| --- | ------ |
| 0   | Q(t)   |
| 1   | Q'(t)       |

### Exitation Table
Input is given and we have to derive output
#### SR
| Q(t) | Q(t+1) | S   | R      |
| ---- | ------ | --- | ------ |
| 0    | 0      | 0   | 0/1(x) |
| 0    | 1      | 1   | 0      |
| 1    | 0      | 0   | 1      |
| 1    | 1      | 0/1(x)   | 0      |
#### D
| Q(t) | Q(t+1) | D   |
| :--: | :----: | :-: |
| 0    | 0      | 0    |
| 0    | 1      | 1    |
| 1    | 0      |  0   |
| 1    | 1      |  1   |
#### JK
| Q(t) | Q(t+1) | J      | K      |
| ---- | ------ | ------ | ------ |
| 0    | 0      | 0      | 0/1(x) |
| 0    | 1      | 1      | 0/1(x) |
| 1    | 0      | 0/1(x) | 1      |
| 1    | 1      | 0/1(x) | 0       |
#### T

| Q(t) | Q(t+1) | T   |
| ---- | ------ | --- |
| 0    | 0      | 0    |
| 0    | 1      | 1    |
| 1    | 0      | 1    |
| 1    | 1      | 0    |

# Sequential Circuits
Combination of combinational circuit and one or more flip flop
![[Drawing 2023-08-25 09.28.01.excalidraw]]

#### Example Sequential Circuit
![[Screenshot 2023-08-25 093821.png]]
$D_{A}= A \cdot x + B \cdot x$
$D_{B} = A' \cdot x$
$y = A \cdot x' + B \cdot x'$

#### HW (State table)
| Present State |     | Input | Next State |     | Output |
| ------------- | --- | ----- | ---------- | --- | ------ |
| A             | B   | x     | A          | B   | y      |
| 0             | 0   | 0     | 0          | 0   | 0      |
| 0             | 0   | 1     | 0          | 1   | 0      |
| 0             | 1   | 0     | 0          | 0   | 1      |
| 0             | 1   | 1     | 1          | 1   | 0      |
| 1             | 0   | 0     | 0          | 0   | 1      |
| 1             | 0   | 1     | 1          | 0   | 0      |
| 1             | 1   | 0     | 0          | 0   | 1      |
| 1             | 1   | 1     | 1          | 0   | 0       |

#### State Diagram (from the table)
![[Combinational Circuits 2023-08-28 11.14.30.excalidraw]]

_State diagram -> State table -> logic circuit_

# Incrementor (From previous state)
![[Combinational Circuits 2023-08-28 11.27.38.excalidraw]]

| Previous State |     | Input | Next State |     | Flip flop inputs |       |       |     |
| -------------- | --- | ----- | ---------- | --- | ---------------- | ----- | ----- | --- |
| A              | B   | x     | A          | B   | $J_A$            | $K_A$ | $J_B$ | $K_B$ |
| 0              | 0   | 0     | 0          | 0   | 0                | x     | 0     | x   |
| 0              | 0   | 1     | 0          | 1   | 0                | x     | 1     | x   |
| 0              | 1   | 0     | 0          | 1   | 0                | x     | x     | 0   |
| 0              | 1   | 1     | 1          | 0   | 1                | x     | x     | 1   |
| 1              | 0   | 0     | 1          | 0   | x                | 0     | 0     | x   |
| 1              | 0   | 1     | 1          | 1   | x                | 0     | 1     | x   |
| 1              | 1   | 0     | 1          | 1   | x                | 0     | x     | 0   |
| 1              | 1   | 1     | 0          | 0   | x                | 1     | x     | 1   |

### KMAP
$J_A$
![[Combinational Circuits 2023-08-28 11.54.47.excalidraw]]
$J_{A}= B \cdot x$
$K_A$
![[Combinational Circuits 2023-08-28 11.57.05.excalidraw]]
$J_B$
![[Combinational Circuits 2023-08-29 09.09.33.excalidraw]]
$K_B$

#### The final circuit diagram will be
![[Screenshot 2023-08-29 091202.png]]

# Integrated Circuits
Complex package of multiple digital components
![[Combinational Circuits 2023-08-29 09.19.30.excalidraw]]
Efficiency increases if we can include more components in less space
#### __TTL(Transistor-Transistor Logic)__ 
The transistor-transistor logic family was an evolution of a previous technology that used diodes and transistors for the basic NAND gate. This technology was called DTL, for "diode-transistor logic." Later the diodes were replaced by transistors to improve the circuit operation and the name of the
logic family was changed to "transistor-transistor logic."

#### __ECL__ (Emitter-coupled logic)
Provides the highest speed digital circuits in integrated form
#### __MOS__ 
The metal-oxide semiconductor (MOS) is a unipolar transistor that CMOS
depends on the flow of only one type of carrier, which may be electrons
(n-channel) or holes (p-channel).
#### __CMOS__
The complementary MOS (CMOS) technology uses PMOS and NMOS transistors connected in a complementary fashion in all circuits. The most important advantages of CMOS over bipolar are the high packing density of circuits, a simpler processing technique during fabrication, and a more economical operation because of low power consumption.

__SSI__ - 0-20 components
__MSI__ - 20-800 components
__LSI__ - 200-1000 components
__VLSI__ - 1000+ Components

# Decoder
A decoder is a combinational circuit that converts binary information from the n coded inputs to a __maximum__ of $2^n$ unique outputs
![[Combinational Circuits 2023-08-29 09.28.36.excalidraw]]

| $A_1$ | $A_0$ | D_0 | D_1 | D_2 | D_3 |
| ----- | ----- | --- | --- | --- | --- |
| 0     | 0     | 1   | 0   | 0   | 0   |
| 0     | 1     | 0   | 1   | 0   | 0   |
| 1     | 0     | 0   | 0   | 1   | 0   |
| 1     | 1     | 0   | 0   | 0   | 1    |
Using AND gate
![[Combinational Circuits 2023-08-29 09.34.42.excalidraw]]
Using NAND Gate
![[Screenshot 2023-08-29 094902.png]]

3x8 decoder
![[Combinational Circuits 2023-08-29 09.41.31.excalidraw]]

| $A_2$ | $A_1$ | $A_0$ | D_0 | D_1 | D_2 | D_3 | D_4 | D_5 | D_6 | D_7 |
| ----- | ----- | ----- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0     | 0     | 0     | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |
| 0     | 0     | 1     | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   |
| 0     | 1     | 0     | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   |
| 0     | 1     | 1     | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   |
| 1     | 0     | 0     | 0   | 0   | 0   | 0   | 1   | 0   | 0   | 0   |
| 1     | 0     | 1     | 0   | 0   | 0   | 0   | 0   | 1   | 0   | 0   |
| 1     | 1     | 0     | 0   | 0   | 0   | 0   | 0   | 0   | 1   | 0   |
| 1     | 1     | 1     | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 1    |

![[Screenshot 2023-08-29 094631.png]]

#### This decoder can be expanded
![[Screenshot 2023-08-29 095147.png]]

| A2  | A1  | A0  | D0  | D1  | D2  | D3  | D4  | D5  | D6  | D7  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |
| 0   | 0   | 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   |
| 0   | 1   | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   | 0   |
| 0   | 1   | 1   | 0   | 0   | 0   | 1   | 0   | 0   | 0   | 0   |
| 1   | 0   | 0   | 0   | 0   | 0   | 0   | 1   | 0   | 0   | 0   |
| 1   | 0   | 1   | 0   | 0   | 0   | 0   | 0   | 1   | 0   | 0   |
| 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 1   | 0   |
| 1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 1    |
# Encoder
![[Combinational Circuits 2023-08-29 14.25.25.excalidraw]]

$A_0 = D_1+D_3$
$A_1 = D_2+D_3$
![[Combinational Circuits 2023-08-29 14.27.43.excalidraw]]
8x3
![[Combinational Circuits 2023-08-29 14.32.26.excalidraw]]
![[Screenshot 2023-08-29 142420.png]]
$A_{0}= D_{1}+D_{3}+D_{5}+D_{7}$
$A_{1}= D_{2}+D_{3}+D_{6}+D_{7}$
$A_{2}= D_{4}+D_{5}+D_{6}+D_{7}$
![[Combinational Circuits 2023-08-29 14.34.13.excalidraw]]

