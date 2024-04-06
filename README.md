# VLSI-LAB-EXPERIMENTS
# AIM: 

To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

# APPARATUS REQUIRED: 

vivado 2023.2

# PROCEDURE: 

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.



Logic Diagram :



Logic Gates:




![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



# VERILOG CODE:

# LOGIC GATES:

module logic_gates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

# HALF ADDER:

module exp1HA(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule

# FULL ADDER:

module full_adder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3,w4;

xor (w1,a,b); 

xor (sum,w1,c);

and (w2,a,b);

and (w3,b,c);

and (w4,c,a);

or (carry,w2,w3,w4);

endmodule

# HALF SUBTRACTOR:

module half_sub(a,b,borrow,diff);

input a,b;

output borrow,diff;

wire w1;

xor (diff,a,b);

not (w1,a);

and (borrow,w1,b);

endmodule

# FULL SUBTRACTOR:

module full_sub(a,b,c,diff,borrow);

input a,b,c;

output borrow,diff;

wire w1,w2,w3;

xor g1(w1,a,c);

and g2(w2,~a,b);

xor g3(diff,w1,c);

or g4(borrow,w2,w3);

and g5(w3,~w1,c);

endmodule

# 8 BIT RIPPLE CARRY ADDER:

module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,a,b);

xor g3(sum,w1,c);

and g4(w3,w1,c);

or g5(carry,w2,w3);

endmodule

module rca(a,b,c,sum,carry);

input [7:0]a,b;

input c;

output [7:0]sum;

output carry;

wire w1,w2,w3,w4,w5,w6,w7;

fa fa1(a[0],b[0],c,sum[0],w1);

fa fa2(a[1],b[1],w1,sum[1],w2);

fa fa3(a[2],b[2],w2,sum[2],w3);

fa fa4(a[3],b[3],w3,sum[3],w4);

fa fa5(a[4],b[4],w4,sum[4],w5);

fa fa6(a[5],b[5],w5,sum[5],w6);

fa fa7(a[6],b[6],w6,sum[6],w7);

fa fa8(a[7],b[7],w7,sum[7],carry);

endmodule

# OUTPUT:

# LOGIC GATES:


![logic gates](https://github.com/U3gueh/VLSI-LAB-EXP-1/assets/115100663/cb994891-20eb-4e99-814f-b74e3ef98eb2)



# HALF ADDER:


![half add](https://github.com/U3gueh/VLSI-LAB-EXP-1/assets/115100663/adeee95b-3c5d-4b54-a3c0-2de74f2fd8ad)



# FULL ADDER:


![full adder](https://github.com/U3gueh/VLSI-LAB-EXP-1/assets/115100663/ba92bbc2-a27e-4f15-8e69-01682fd7ea67)



# HALF SUBTRACTOR:


![half sub](https://github.com/U3gueh/VLSI-LAB-EXP-1/assets/115100663/f0e8d3b5-f9b3-47a0-b15f-df96cfc87c80)



# FULL SUBTRACTOR:


![full sub](https://github.com/U3gueh/VLSI-LAB-EXP-1/assets/115100663/7ae6d33c-95b4-4b13-a880-79f440b44dbb)


# 8 BIT RIPPLE CARRY ADDER:


![8bit rca](https://github.com/U3gueh/VLSI-LAB-EXP-1/assets/115100663/e5c20d1e-c282-4094-9ea1-1b5217ca124c)



# RESULT:

         Thus the  simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .
