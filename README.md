SIMULATION AND IMPLEMENTATION OF COMBINATIONAL LOGIC CIRCUITS

AIM: 

To simulate ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using VIVADO 2023.2.

APPARATUS REQUIRED: 

VIVADO 2023.2

PROCEDURE:

STEP:1 Start the Xilinx navigator, Select and Name the New project. 
STEP:2 Select the device family, device, package and speed.
STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 
STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax.
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

ENCODER


LOGIC DIAGRAM

![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/7e77d44e-492d-441b-bd5a-c3485cfb14e9)
 
VERILOG CODE
```
module encoder(a,y);
input [7:0]a;
output[2:0]y;
or(y[2],a[6],a[5],a[4],a[3]);
or(y[1],a[6],a[5],a[2],a[1]);
or(y[0],a[6],a[4],a[2],a[0]);
endmodule
```
OUTPUT WAVEFORM

 ![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/58db2fd1-52c5-4927-98c8-c6199a592d19)

DECODER

LOGIC DIAGRAM

 ![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/809d66a5-d9f3-49bd-a819-68ba602affe3)

VERILOG CODE
```
module decoder1(a,y);
input [2:0]a;
output[7:0]y;
and(y[0],~a[2],~a[1],~a[0]);
and(y[1],~a[2],~a[1],a[0]);
and(y[2],~a[2],a[1],~a[0]);
and(y[3],~a[2],a[1],a[0]);
and(y[4],a[2],~a[1],~a[0]);
and(y[5],a[2],~a[1],a[0]);
and(y[6],a[2],a[1],~a[0]);
and(y[7],a[2],a[1],a[0]);
endmodule
```
OUTPUT WAVEFORM

 ![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/bc30fde5-ba43-4a5f-be0d-fe7366315d92)

MULTIPLEXER

LOGIC DIAGRAM 
 
![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/ceb9b16b-8571-4b2b-8cce-053b8ee5729c)

VERILOG CODE
```
module mux(s,c,a);
input [2:0]s;
input [7:0]a;
wire [7:0]w;
output c;
and(w[0],a[0],~s[2],~s[1],~s[0]);
and(w[1],a[1],~s[2],~s[1],s[0]);
and(w[2],a[2],~s[2],s[1],~s[0]);
and(w[3],a[3],~s[2],s[1],s[0]);
and(w[4],a[4],s[2],~s[1],~s[0]);
and(w[5],a[5],s[2],~s[1],s[0]);
and(w[6],a[6],s[2],s[1],~s[0]);
and(w[7],a[7],s[2],s[1],s[0]);
or (c,w[0],w[1],w[2],w[3],w[4],w[5],w[6],w[7]);
endmodule
```
OYTPUT WAVEFORM

![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/ad8199b4-f549-461e-b1bc-6dc382a13a08)
 
DEMULTIPLEXER

LOGIC DIAGRAM 

![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/7d0fbb3c-bb1f-4b04-a23f-da9d4424abe5)
 
VERILOG CODE
```
module demux_8(s,a,y);
input [2:0]s;
input a;
output [7:0]y;
and(y[0],a,~s[2],~s[1],~s[0]);
and(y[1],a,~s[2],~s[1],s[0]);
and(y[2],a,~s[2],s[1],~s[0]);
and(y[3],a,~s[2],s[1],s[0]);
and(y[4],a,s[2],~s[1],~s[0]);
and(y[5],a,s[2],~s[1],s[0]);
and(y[6],a,s[2],s[1],~s[0]);
and(y[7],a,s[2],s[1],s[0]);
endmodule
```
OYTPUT WAVEFORM

 ![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/5972a670-5ed8-4b36-b4dc-e4a06e790c62)

MAGNITUDE COMPARATOR

LOGIC DIAGRAM 

 ![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/deeb2145-d89b-47d5-ac76-a24a484eecc0)

VERILOG CODE
```
module comparator(a,b,eq,lt,gt);
input [3:0] a,b;
output reg eq,lt,gt;
always @(a,b)
begin
 if (a==b)
 begin
  eq = 1'b1;
  lt = 1'b0;
  gt = 1'b0;
 end
 else if (a>b)
 begin
  eq = 1'b0;
  lt = 1'b0;
  gt = 1'b1;
 end
 else
 begin
  eq = 1'b0;
  lt = 1'b1;
  gt = 1'b0;
 end
end 
endmodule
```
OYTPUT WAVEFORM
 
![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/2f73d88a-01c0-4e21-8f2d-3465464bf7f6)

RESULT

![image](https://github.com/Lokeshmb005/VLSI-LAB-EXP-2/assets/159941167/dee082e1-1762-4166-b4d8-18649f2227c0)


 
 
