# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
1.create mocule projectname(input,output)to start the verilog programming.
2.create a ih loop condition to increase the counter in counter _up function.
3.similarly,create another loop for the down counter.
4.End the verilog program using keyword endmodule.
5.Get the timing diagram and RTL realization diagram for respective counters.



### PROGRAM 
~~~
module uc(input CLK, input reset,output[0:3]counter);
reg[0:3]counter_up;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_up <=4'd0;
else
counter_up <=counter_up+4'd1;
end
assign counter = counter_up;
endmodule

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
~~~
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: panimalar.p
RegisterNumber:  22009107
/*

### RTL LOGIC UP COUNTER AND DOWN COUNTER  


![Screenshot (133)](https://user-images.githubusercontent.com/121490826/214215154-3da966ec-bc87-484e-a414-4dba7c50bcb1.png)

![Screenshot (137)](https://user-images.githubusercontent.com/121490826/214218624-59f0d75a-8353-4f95-92ad-8941125f08e6.png)

### TIMING DIGRAMS FOR COUNTER  

![Screenshot (134)](https://user-images.githubusercontent.com/121490826/214215263-4277b221-6d3f-430a-bebf-bdec973d7877.png)

![Screenshot (138)](https://user-images.githubusercontent.com/121490826/214218783-86f9f28c-0fa0-4b74-97a2-d4986bf79110.png)



### TRUTH TABLE 

![Screenshot (140)](https://user-images.githubusercontent.com/121490826/214222987-8418934a-8f58-4447-9c3e-c5ab5182dd4a.png)
![Screenshot (141)](https://user-images.githubusercontent.com/121490826/214223350-0eb04b92-4103-40a1-9f8e-76a49652fb4f.png)


### RESULTS 
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different
logic gates are verified.
