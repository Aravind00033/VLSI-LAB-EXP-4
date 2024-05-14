**SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS**

**AIM:**

 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Vivado 2023.3.

**APPARATUS REQUIRED:**

Vivado 2023.3
  
**PROCEDURE:**

STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.



**SR FLIPFLOP:**

**LOGIC DIAGRAM:**


![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

**VERILOG CODE:**


```
module srff(s,r,clk,rst,q);
input s,r,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({s,r})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=1'bX;
endcase
end
end
endmodule
```

**OUTPUT:**


![316233145-0f6d3c8a-68ed-42c1-950f-97b055ceaf98](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/b266b12a-4287-4021-80ac-997c6c1ba24a)


**JK FLIPFLOP:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

**VERILOG CODE:**

```
module jkff(j,k,clk,rst,q);
input j,k,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({j,k})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=~q;
endcase
end
end
endmodule
```

**OUTPUT:**
![316233162-f10f8a81-e7aa-44f7-a5ee-70f276eeb4ba](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/468be26b-46a5-409f-bd38-c7bc526f4209)

**T FLIPFLOP:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)

**VERILOG CODE:**

```
module tff(clk,rst,t,q);
input clk,rst,t;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else if (t==0)
q=q;
else
q=~q;
end
endmodule
```

**OUTPUT:**

![316233164-111a7a8f-4e01-4ac4-90c1-4a1a45d13115](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/d6207a0e-c644-465e-a4ef-0946c3de5e39)


**D FLIPFLOP:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)

**VERILOG CODE:**

```
module dff(d,clk,rst,q);
input d,clk,rst;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else
q=d;
end
endmodule
```

**OUTPUT:**

![316233181-03c4477f-c15a-4898-9e11-df5f1ff4850a](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/9b5810a9-c9ca-4a8c-9eaa-c3e20fba5a88)


**COUNTER:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

**UPDOWN COUNTER:**

**LOGIC DIAGRAM:**

![320875970-dd12585a-157f-4b6f-a0c3-b421bb52434c](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/0c01a674-4af5-4711-ab8b-3fdbced62995)



**VERILOG CODE:**

```
module udc(clk,rst,updown,out);
input clk,rst,updown;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1)
out=4'b0000;
else if(updown==1)
out=out+1;
else
out=out-1;
end
endmodule
```

**OUTPUT:**

![320868824-c37fe928-351f-4e40-bf5a-49491aab4bfc](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/16551402-317f-4cec-98a3-5b755f857c4b)

**MOD-10 COUNTER:**

**LOGIC DIAGRAM:**

![320876746-3a4a4da2-7488-411d-8ea5-2e57c4fd942f](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/1df46053-6857-4ee2-867d-0680c77623c7)

**VERILOG CODE:**

```
module mod10(clk,rst,out);
input clk,rst;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1 | out==4'b1001)
out=4'b0000;
else
out=out+1;
end
endmodule
```

**OUTPUT:**

![320869850-c6465024-ee28-4781-ba9a-9bec97dd2c1a](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/8f8e90e7-7a43-4d0b-9b95-f565ed3ed632)


**RIPPLE CARRY COUNTER:**

**LOGIC DIAGRAM:**

![320877668-129b1a22-407f-4f38-adff-b4dbf3595eb7](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/d76987a3-19ee-431f-8d8f-13945d8b08be)



![320877790-fecad9d3-7f49-4c98-91f4-443803a60e37](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/34d4748b-b57b-49da-86d0-cf454f35672a)




**VERILOG CODE:**

```
module tff(q,clk,rst);
input clk,rst;
output q;
wire d;
dff df1(q,d,clk,rst);
not n1(d,q);
endmodule

module dff(q,d,clk,rst);
input d,clk,rst;
output q;
reg q;
always @(posedge clk or posedge rst)
begin
if (rst)
q=1'b0;
else 
q=d;
end
endmodule

module rcc(clk,rst,q);
input clk,rst;
output [3:0]q;
tff tf1(q[0],clk,rst);
tff tf2(q[1],q[0],rst);
tff tf3(q[2],q[1],rst);
tff tf4(q[3],q[2],rst);
endmodule
```

**OUTPUT:**

![320874442-4a1a2d79-9e4d-4b0a-bda9-64bb19952f67](https://github.com/Aravind00033/VLSI-LAB-EXP-4/assets/160571380/c57173e9-2e27-4a81-ac1c-e87acf2ab5b9)


**RESULT:**

 Hence SR, JK, T, D - FLIPFLOP, COUNTER DESIGN are simulated and synthesised using Vivado 2023.2


