# Exp-6-Synchornous-counters---up-counter-and-down-counter

# AIM: To implement 4 bit up and down counters and validate functionality.

# HARDWARE REQUIRED: – PC, Cyclone II , USB flasher

# SOFTWARE REQUIRED: Quartus prime

# THEORY

# UP COUNTER

The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down).

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle. The Counter will be set to Zero when “reset” input is at logic high. The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down. The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output. The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence. Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1: Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

![Screenshot (115)](https://user-images.githubusercontent.com/119476322/215180323-4a88c8ae-886d-4ee5-a12f-6696c5154cf7.png)

# DOWN COUNTER

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.

![Screenshot (116)](https://user-images.githubusercontent.com/119476322/215180432-12ef6986-c5fc-41a7-96fa-36d9455bfac0.png)
4-bit Count Down Counter 

# Procedure
```
1.Using if statement construct a 4bit UP Counter.

2.Repeat the same for 4bit DOWN Counter.

3.Find RTL and Timing Diagram for both the counters.

4.End the program.
```

# PROGRAM

Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: Sivaramakrishnan B

RegisterNumber: 22006798

```
module uc(input clk,input reset,output[0:3]counter);
reg[0:3] counter_up;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_up<=4'd0;
else
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule

DOWN COUNTER:-

module dc(input clk,input reset,output[0:3]counter);
reg[0:3] counter_down;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_down<=4'd0;
else
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule
```

# RTL LOGIC UP COUNTER AND DOWN COUNTER

![Screenshot (117)](https://user-images.githubusercontent.com/119476322/215180663-8d50dc71-e495-4a81-b06b-28469b4c4ec7.png)

# TIMING DIGRAMS FOR COUNTER

![Screenshot (118)](https://user-images.githubusercontent.com/119476322/215180734-47b211bf-da57-4841-b800-33912e7dc7ac.png)

# TRUTH TABLE

# UP COUNTER:

![Screenshot (119)](https://user-images.githubusercontent.com/119476322/215181024-c5330d77-6b82-4353-b66b-a9d1dac9e668.png)

# DOWN COUNTER:

![Screenshot (120)](https://user-images.githubusercontent.com/119476322/215180887-abaeed89-1bb6-46fb-9b25-99592ad094b4.png)

# RESULTS
Thus,design of up counter and down counter and to verify its truth table in Quartus using Verilog programming is executed successfully
