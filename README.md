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
# step1:
1.Create a new project in QuartusII software.
# step2:
2.Name the project as uc for upcounter and dc for down counter.
# step3:
3.Create a new verilog hdl file in the project file.
#  step4:
4.Name the module as dc and uc for down counter and up counter.
#  step5:
5.Within the module declare input and output variables.
# step6:
6.Create a loop using if-else with condition parameter as reset value.
# step7:
7.End the loop.
# step8:
8.End the module.



### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.

Developed by: JEEVITHA E

RegisterNumber:  212222230054
```
# DOWN COUNTER:
```
module counters(clk,A);
input clk;
output reg [0:3]A;
always@(posedge clk)
begin
	A[0]=(((~A[2])&(~A[3])&(~A[1]))^A[0]);
	A[1]=(((~A[2])&(~A[3]))^A[1]);
	A[2]=(~A[3])^A[2];
	A[3]=1^A[3];
end
endmodule
```
# UP COUNTER:
```
module counters(clk,A);
input clk;
output reg [0:3]A;
always @(posedge clk)
begin
	A[0]=(((A[2])&(A[3])&(A[1]))^A[0]);
	A[1]=(((A[2])&(A[3]))^A[1]);
	A[2]=(A[3])^A[2];
	A[3]=1^A[3];
end
endmodule

```

### RTL LOGIC UP COUNTER AND DOWN COUNTER  
# DOWN COUNTER:

![242487237-c6938290-59bd-4ccd-88ba-95aa8854df29](https://github.com/Jeevithaelumalai/Exp-7-Synchornous-counters-/assets/118708245/3e548083-8a69-43df-acf9-e24fe9f6905c)


# UP COUNTER:
![242490286-a7453958-564c-4ef5-940c-347e19ddc645](https://github.com/Jeevithaelumalai/Exp-7-Synchornous-counters-/assets/118708245/86115917-4ce2-4733-894e-18d00ddff8b8)




### TIMING DIGRAMS FOR COUNTER  
# UP COUNTER:

![image](https://github.com/Jeevithaelumalai/Exp-7-Synchornous-counters-/assets/118708245/9b08fd0c-25df-4c50-a9b4-f846795419a3)



# DOWN COUNTER
![244275891-a20707c6-c5ef-44e3-a1d6-e03f062363d7](https://github.com/Jeevithaelumalai/Exp-7-Synchornous-counters-/assets/118708245/8ee8953d-d3a0-4aaa-932c-9571f6d5b487)


### TRUTH TABLE 

# UP COUNTER:
![image](https://github.com/Jeevithaelumalai/Exp-7-Synchornous-counters-/assets/118708245/6016fcae-4a33-4c64-b806-673572d79b25)

# DOWN COUNTER:
![image](https://github.com/Jeevithaelumalai/Exp-7-Synchornous-counters-/assets/118708245/8a184fc8-2781-451f-82a5-84d983451911)


### RESULTS :
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified
