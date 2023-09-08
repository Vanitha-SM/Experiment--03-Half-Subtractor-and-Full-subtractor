```
Developed by: Vanitha S
RegisterNumber: 212222100057
```
# Experiment 03 Half Subtractor and Full subtractor

## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Components Required:
 Hardware – PCs, Cyclone II , USB flasher
 Software – Quartus prime
 Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Theory:
#### Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

#### Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin


## Procedure:-
1. Create a New Project:
   - Open Quartus and create a new project by selecting "File" > "New Project Wizard."
   - Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).

2. Create a New Design File:
   - Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
   - Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.

3. Write the Combinational Logic Code:
   - Open the newly created Verilog or VHDL file and write the code for your combinational logic.
     
4. Compile the Project:
   - To compile the project, click on "Processing" > "Start Compilation" in the menu.
   - Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.

5. Analyze and Fix Errors:*
   - If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
   - Review and fix any issues in your code if necessary.
   - View the RTL diagram.

6.*Verification:
   - Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
   - Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
   - Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.


## Program:
 
#### half subtractor
```
module halfsub(a,b,Diff,Borrow);
input a,b;
output Diff,Borrow;
assign Diff = (a^b);
assign Borrow = (~a&b);
endmodule
```
#### full subtractor
```
module fullsub(A,B,Bin,diff,borrow);
input A,B,Bin;
output diff,borrow;
assign diff=(A^B^Bin);
assign borrow=((~A&B)|(~(A^B)&Bin));
endmodule
```
##  RTL diagram:
#### Half subtractor
![Screenshot 2023-09-08 092339](https://github.com/Vanitha-SM/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119557985/8c89e61a-762b-418e-b969-c1f360a92139)
#### Full subtractor
![Screenshot 2023-09-08 093750](https://github.com/Vanitha-SM/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119557985/a18af67d-e0ae-4a8d-875f-3dbaaaacf202)


## Truthtable:
#### Half subtractor:
![image](https://github.com/Vanitha-SM/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119557985/18842840-0e38-4ac4-b8aa-cce5428e72ee)
#### Full subtractor:
![image](https://github.com/Vanitha-SM/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119557985/f85b9a6d-e135-43a5-b9c8-4c65da2d3f19)

## Output Waveform:
#### Half subtractor
![Screenshot 2023-09-08 092353](https://github.com/Vanitha-SM/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119557985/0b48855a-6f42-4a43-9a7d-f24f9125b195)

#### Full subtractor
![Screenshot 2023-09-08 093736](https://github.com/Vanitha-SM/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119557985/f1e84e64-0dcc-4a4c-a097-b4d6d9d8e086)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
