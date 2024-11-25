# Exp-No:6 - Traffic light Controller-Synthesize the Gate Level Netlist and tabulate Area ,Power and timing reports.(Using Genus in Cadence)

**Aim:** <br>
<br>
&emsp;&emsp;Synthesize Traffic Light Controller design using Constraints and analyse area and Power reports.<br>
<br> 
**Tool Required:** <br>
<br>
&emsp;&emsp;Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

&emsp;&emsp;Synthesis: Genus<br>
<br>
**Step 1: Getting Started** <br>
<br>
&emsp;&emsp;Synthesis requires three files as follows,

&emsp;&emsp;&emsp;&emsp;◦ Liberty Files (.lib)

&emsp;&emsp;&emsp;&emsp;◦ Verilog/VHDL Files (.v or .vhdl or .vhd)<br>
<br>

**Step 2 : Creating an SDC File** <br>
<br>
&emsp;&emsp;•	In your terminal type “gedit input_constraints.sdc” to create an SDC File if you do not have one.

&emsp;&emsp;• The SDC File must contain the following commands;

&emsp;&emsp;&emsp;&emsp;create_clock -name clk -period 2 -waveform {0 1} [get_ports "clk"]

&emsp;&emsp;&emsp;&emsp;set_clock_transition -rise 0.1 [get_clocks "clk"]

&emsp;&emsp;&emsp;&emsp;set_clock_transition -fall 0.1 [get_clocks "clk"]

&emsp;&emsp;&emsp;&emsp;set_clock_uncertainty 0.01 [get_ports "clk"]

&emsp;&emsp;&emsp;&emsp;set_input_delay -max 0.8 [get_ports "rst"] -clock [get_clocks "clk"]

&emsp;&emsp;&emsp;&emsp;set_output_delay -max 0.8 [get_ports "count"] -clock [get_clocks "clk"]

&emsp;&emsp;&emsp;&emsp;i→ Creates a Clock named “clk” with Time Period 2ns and On Time from t=0 to t=1.

&emsp;&emsp;&emsp;&emsp;ii, iii → Sets Clock Rise and Fall time to 100ps.

&emsp;&emsp;&emsp;&emsp;iv → Sets Clock Uncertainty to 10ps.

&emsp;&emsp;&emsp;&emsp;v, vi → Sets the maximum limit for I/O port delay to 1ps.<br>
<br>

**Step 3 : Performing Synthesis** <br>
<br>
&emsp;&emsp;The Liberty files are present in the library path,

&emsp;&emsp;&emsp;&emsp;• The Available technology nodes are 180nm ,90nm and 45nm.

&emsp;&emsp;&emsp;&emsp;• In the terminal, initialise the tools with the following commands if a new terminal is being used.

&emsp;&emsp;&emsp;&emsp;◦ csh

&emsp;&emsp;&emsp;&emsp;◦ source /cadence/install/cshrc

&emsp;&emsp;&emsp;&emsp;• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

&emsp;&emsp;&emsp;&emsp;• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.<br>
<br>

**Synthesis RTL Schematic :** <br>
<br>
![Screenshot 2024-11-13 144942](https://github.com/user-attachments/assets/aa552359-c5f1-4ef2-82e5-f72d1b6244eb)

<br>

**Area report:** <br>
<br>
![Screenshot 2024-11-16 163430](https://github.com/user-attachments/assets/9ade2121-5ade-42c5-8320-b785d15b57fb)

<br>
<br>
<br>
<br>
<br>
<br>

**Power Report:** <br>
<br>
![Screenshot 2024-11-16 163536](https://github.com/user-attachments/assets/9eff52de-a7cc-4488-bb21-2bf0b30dc2f9)

<br> 

**Timing Report:** <br>
<br>
![Screenshot (1)](https://github.com/user-attachments/assets/d82190a5-7965-4c56-89d0-47f978a6722a)

<br>

**Result:** <br>
<br>
&emsp;&emsp;The generic netlist of Traffic Light Controller has been created, and area, power and timing reports have been tabulated and generated using Genus.
