# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**


 1.Declare a Verilog module named EXP11 with input ports clk, rst, sin, and an output port q.

2.Declare input ports: clk for the clock signal, rst for the reset signal, and sin for the input signal. Also, declare the output port q as a 4-bit vector representing the state of flip-flops.

3.Declare an internal register q as a 4-bit vector to store the state of the flip-flops.

4.Create an always block that triggers on the positive edge of both the clock (clk) and the reset signal (rst), containing the following steps:

5.If the reset signal is asserted (rst), assign q to 4'b0000 to reset all flip-flops to 0.

6.If the reset signal is not asserted, assign the value of sin to the first flip-flop (q[0]) and shift the values of q to the right.

**PROGRAM**
```
module shift_register_3bit (
    input  wire clk,     // clock input
    input  wire rst,     // synchronous reset
    input  wire serial_in, // serial data input
    output reg  [2:0] q   // 3-bit register output
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;          // reset all bits
    else
        q <= {q[1:0], serial_in}; // shift left
end

endmodule
```
Program for flipflops and verify its truth table in quartus using Verilog programming.
<img width="750" height="357" alt="image" src="https://github.com/user-attachments/assets/e525e284-be95-4845-8e1c-6438aa535123" />

Developed by: PERARASU K RegisterNumber: 25004665



**RTL LOGIC FOR SISO Shift Register**
<img width="1013" height="551" alt="image" src="https://github.com/user-attachments/assets/307c3269-4153-4fc8-8fe9-da6650fc12e7" />

**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1322" height="170" alt="image" src="https://github.com/user-attachments/assets/a927b14f-425e-444c-8dd7-e744da109d9b" />

**RESULTS**
Thus SISO Shift Register using verilog and validating their functionality using their functional tables has successful execution of the program.
