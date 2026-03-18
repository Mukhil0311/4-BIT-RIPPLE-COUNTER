# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

Type the program in Quartus software.

Compile and run the program.

Generate the RTL schematic and save the logic diagram.

Create nodes for inputs and outputs to generate the timing diagram.

For different input combinations generate the timing diagram. 

**PROGRAM**

```
Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by: MUKHIL S 
 RegisterNumber: 212225040263


module ripple_counter(clk,rst,t,A,B,C,D); 
input clk,rst,t; 
output A,B,C,D;
reg A,B,C,D;

Tff T0(D,clk,rst,t); 
Tff T1(C,D,rst,t); 
Tff T2(B,C,rst,t); 
Tff T3(A,B,rst,t); 

endmodule 

module Tff(q,clk,rst,t); 
input clk,rst,t; 
output q; 
reg q; 
output q_bar;
always @(posedge clk) 
	
begin 
if(!rst)
q<=0;
else 
begin
q<=(t?~q:q);
end
end
assign q_bar = ~q;

endmodule

```
**RTL LOGIC FOR 4 Bit Ripple Counter**
![image](https://github.com/Mukhil0311/4-BIT-RIPPLE-COUNTER/blob/main/WhatsApp%20Image%202026-03-18%20at%208.32.16%20PM.jpeg)
**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![image](https://github.com/Mukhil0311/4-BIT-RIPPLE-COUNTER/blob/main/WhatsApp%20Image%202026-03-18%20at%208.32.16%20PM%20(1).jpeg)
**RESULTS**
Thus the program has been executed successfully..
