# My-Project
This is a repository wihich is about my final B.E Project
Introduction
Im Abdul Jabbar from Muffakham Jah College of Engineering and Technology in the field of Electronics and Communication Engineering. My Skills are Verilog, Iverilog, Gtkwave, yosys and Android App Development.

In this project I'm going to explain how to use Iverilog and Gtkwave for verification and simulation of verilog modules using VScode as IDE. As we know Iverilog and gtkwave are opensource EDA tools it only runs on command prompt to make it simpler i am using vscode which provide a compact view for dealing with this kind of Opensource tools.
We require some softwares to perform these applications
Links for Installation
1.icarus verilog (for windows download link:https://bleyer.org/icarus/ ).

2.vscode download link-https://code.visualstudio.com/download (also extentions i.Verilog-HDL/SystemVerilog/Bluespec SystemVerilog and ii.Graphviz Preview).

# Let the journey begin
# Step 1
Create a special folder and write the verilog code in the Visual Studio and save it as .v file
![1](https://user-images.githubusercontent.com/94279161/143183091-14d3ba1c-6283-4ea1-85e5-fe291559a370.jpg)
# Step 2
Now create and write the test bench file for the verilog code written before.
![2](https://user-images.githubusercontent.com/94279161/143183416-a60adc57-7064-4cd1-abd8-8d88e63e1f2f.jpg)
# Step 3
Now open a new terminal and write the code as iverilog .\ha.v .\ha_t.v  In your case replace the names of verilog and test bench files.
![3](https://user-images.githubusercontent.com/94279161/143183681-7a4710b1-3cbf-4948-8a49-03bd02e9dd8d.jpg)
# Step 4
After this we get and a.out file. Now in terminal type vvp .\a.out
![4](https://user-images.githubusercontent.com/94279161/143184084-0e1519b6-37bd-47fa-8a9d-ecf61a212d76.jpg)![5](https://user-images.githubusercontent.com/94279161/143184137-7d3ad010-9f75-4cb0-8323-49c339895932.jpg)
# Step 5
Now for generating wave forms we are using gtkwave as EDA Tool for waveform representation. To get waveform use coomand gtkwave .\half_adder.vcd
We get the waveform as
![6](https://user-images.githubusercontent.com/94279161/143184547-67315828-b607-43c4-a0c6-002852015ac1.jpg)
# Now coming to synthesis process we use a tool called yosys link:http://www.clifford.at/yosys/download.html )
# Step 1
Type yosys in terminal. Now we entered into yosys
![7](https://user-images.githubusercontent.com/94279161/143184869-7c37a4c5-f3b0-41b6-af3b-20a6bd038887.jpg)
# Step 2
The next command Type: read_liberty -lib sky130_fd_sc_hd__tt_025C_1v80.lib
![10](https://user-images.githubusercontent.com/94279161/143185273-c925ed41-4f69-4ba1-8125-2977a7823120.jpg)
![9](https://user-images.githubusercontent.com/94279161/143185146-d98a1b39-6a98-4878-a21f-7abb8ec3cc3c.jpg)
# Step 3
for downloading netlist file type : show
![12](https://user-images.githubusercontent.com/94279161/143185535-39faa547-e31e-45ea-a8fd-e97d05271061.jpg)
![13](https://user-images.githubusercontent.com/94279161/143185631-6f401465-000c-4406-868e-caf89978f931.jpg)
# Step 4
Now use following command : tee -o report.txt stat -liberty sky130_fd_sc_hd__tt_025C_1v80.lib
![14](https://user-images.githubusercontent.com/94279161/143185711-43101786-a564-407e-bf34-37dd8ccb799d.jpg)
# Step 5
After synthesys now we need to download or write the synthesys file into some sort of file mainly in verilog formate for this use : write_verilog -noattr netlist.v
![15](https://user-images.githubusercontent.com/94279161/143185824-43092d96-7955-4d92-8dee-56461ae028e7.jpg)
# Step 6
Now exit from yosys from typing exit.
![16](https://user-images.githubusercontent.com/94279161/143186021-59dd7632-55b4-4211-a665-457a6c7c71b6.jpg)
# Step 7
report.txt file shows the statistical data of the design made![18](https://user-images.githubusercontent.com/94279161/143186440-16cf3ddd-cadf-4770-b555-e95fd9a71a15.jpg)
# Step 8
netlist.v file shows the all the detailed information which requred to make a intigrated Circuit.This file is provided to the foundry for physical copy of circuit.
![17](https://user-images.githubusercontent.com/94279161/143186635-5e847b76-1fc7-4844-b54e-1cf6f697954d.jpg)
