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

/* write all the steps invloved */
1. Increment count on each positive edge of the clock
2. Reset count to zero when it reaches 15
3. Generate clock signal(clk)
4. Instantinate functional testing by displaying the count at each clock cycle for 16 cycles
5. Conduct functional testing by displaying the count at each clock cycle for 16 cycles.

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
```
module ripple (
input clk, 
input reset, 
output [3:0] q 
);
reg [3:0] q_int;
assign q = q_int;
always @(posedge clk or posedge reset) begin
if (reset)
q_int[0] <= 1'b0; 
else
q_int[0] <= ~q_int[0]; 
end
genvar i;
generate
for (i = 1; i < 4; i = i + 1) begin : ripple
always @(posedge q_int[i-1] or posedge reset) begin
if (reset)
q_int[i] <= 1'b0; 
else
q_int[i] <= ~q_int[i]; 
end
end
endgenerate
endmodule
```
Developed by: INDUJA R RegisterNumber: 25001726
*/

**RTL LOGIC FOR 4 Bit Ripple Counter

<img width="763" height="484" alt="Screenshot 2025-10-21 111632" src="https://github.com/user-attachments/assets/471c7c5f-9040-423e-9906-7647c61d3f20" />


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

<img width="1919" height="1017" alt="Screenshot 2025-10-21 113348" src="https://github.com/user-attachments/assets/9c3826a3-d677-43f2-b89b-b25534e17a7f" />

**RESULTS**

 Thus, the Bit Ripple Counter is designed and its functionality is validated using the truth table and timing diagrams.
