# 130nm PLL Clock Multiplier IP
8x PLL Clock Multiplier IP on the Google-Skywater 130nm node.

Tested through spice simulations on skywater <b>130nm tt corner at room termperature</b>

Generates 8x Multiplied Clock

<b> Pre-Layout: </b> <br>

Frequency Obtained for 5Mhz input:   40MHz <br>
Frequency Obtained for 12.5Mhz input:   100MHz

Duty Cycle obtained:   46% at 40MHz and 40.6% at 100MHz

Lock-in starts at ~80us for 100MHz and ~120us for 40Mhz

3rd-Order Loop Filter used [c1, c2, c3, r1, r2, r3]:   355fF, 350fF, 345fF, 490, 490, 490.

<b> Post-Layout: </b> <br>

Frequency Obtained for 5Mhz input:   40MHz <br>
Frequency Obtained for 12.5Mhz input:   100MHz

Duty Cycle obtained:   52.7% at 40MHz and 50% at 100MHz

Lock-in starts at ~22us for 100MHz and ~37us for 40Mhz

3rd-Order Loop Filter used [c1, c2, c3, r1, r2, r3]:   295fF, 300fF, 305fF, 490, 490, 490.

<h2> Contents: </h2>

1. [Google-SkyWater 130nm PDK](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md-Google-SkyWater-130nm-PDK-)
2. [Pre-Layout Simulations](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Pre-Layout-Simulations-)
3. [Layout](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Layout-)
4. [Post-Layout Simulations](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Post-Layout-Simulations-)
5. [EDA tools used](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-EDA-Tools-Used-)
6. [Instructions](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Instructions-)
7. [Future Scope](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Future-Scope-)
8. [Acknowledgements](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Acknowledgements-)
9. [Contact](https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP/blob/main/README.md#-Contact-)

<h3> Google-SkyWater 130nm PDK: </h3>

>This PLL circuit is built on the [Google-Skywater 130nm](https://github.com/google/skywater-pdk) node. It is a mature 180nm-130nm hybrid technology originally developed internally by Cypress Semiconductor. The SkyWater Open Source PDK is a collaboration between Google and SkyWater Technology Foundry to provide a fully open source Process Design Kit and related resources, which can be used to create manufacturable designs at SkyWater’s facility. 

<h3> Pre-Layout Simulations </h3>

<h4> PLL Output (tt, 27degree Celcius): </h4>

<b> Red: </b> Reference Clock  <br>
<b> Blue: </b> Output Clock Divided by 8  <br>
<b> Yellow: </b> Down Signal <br>
<b> Brown: </b> Up Signal <br>
<b> Pink (at top): </b> ChargePump output <br>

40Mhz Output: <br>
Trend <br>
![](PreLayout/Simulation_Results/5MhzInputFullPicture.jpg)
Steady State <br>
![](PreLayout/Simulation_Results/5MhzInputSteadyState.png)
<b> Blue constantly overlapping Red indicating locked state </b>

100Mhz Output: <br>
Trend <br>
![](PreLayout/Simulation_Results/12.5MhzInputFullPicture.jpg)
Steady State <br>
![](PreLayout/Simulation_Results/12.5MhzInputSteadyState.jpg)
<b> Blue constantly overlapping Red indicating lock </b>

<b>Output Specs:</b> <br>
Exact 40 Mhz:
![](PreLayout/Specs/Exact40Mhz.jpg)

Exact 100Mhz:
![](PreLayout/Specs/Exact100Mhz.jpg)

<h4> Phase Frequency Detector 'Up' Signal : </h4>

![](PreLayout/Simulation_Results/PD_PreLay_Up.jpg)

<b>Red:</b> Clock 2 <br>
<b>Blue:</b> Clock 1 <br>
<b>Orange:</b> Up Signal <br>
<b>Green:</b> Down Signal

<h4> Phase Frequency Detector 'Down' Signal : </h4>

![](PreLayout/Simulation_Results/PD_PreLay_Down.jpg)

<b>Red:</b> Clock 2 <br>
<b>Blue:</b> Clock 1 <br>
<b>Orange:</b> Up Signal <br>
<b>Green:</b> Down Signal

<h4> Charge Pump response to 'Up' signal: </h4>

![](PreLayout/Simulation_Results/CP_PreLay_Charge.jpg)

<b>Red:</b> Charge Pump Output Voltage <br>

<h4> Charge Pump response to 'Down' signal: </h4>

![](PreLayout/Simulation_Results/CP_PreLay_Discharge.jpg)

<b>Red:</b> Charge Pump Output Voltage<br>

<h4> Charge Pump output rise due to charge leakage: </h4>

![](PreLayout/Simulation_Results/CP_PreLay_Leakage.jpg)

<b>Red:</b> Charge Pump Output Voltage <br>
<b>Leakage:</b> 40uV increase every 1us <br>

<h4> Frequency Divider: </h4>

![](PreLayout/Simulation_Results/FD_PreLay.jpg)

<b>Red:</b> Output Clock <br>
<b>Blue:</b> Input Clock <br>

*These above circuits were custom selected to improve stability and reduce area/power consumption.


<h3> Layout </h3>

<h4> Frequency Divider </h4>

![](Layout/FD_Layout.jpg)

<b> Area: </b> 29.92um square

<h4> Phase Frequency Detector </h4>

![](Layout/PFD_Layout.jpg)

<b> Area: </b> 49.09um square

<h4> Mux </h4>

![](Layout/MUX_Layout.jpg)

<b> Area: </b> 12.12um square

<h4> Charge Pump </h4>

![](Layout/CP_Layout.jpg)

<b> Area: </b> 132.29um square

<h4> Voltage Controlled Oscillator </h4>

![](Layout/VCO_Layout.jpg)

<b> Area: </b> 57.73um square

<h4> Integrated PLL </h4>

![](Layout/PLL_Layout.jpg)

<b> Area: </b> 496.03um square



<h3> Post-Layout Simulations </h3>

<h4> PLL Output (tt, 27degree Celcius): </h4>

<b> Red: </b> Reference Clock  <br>
<b> Blue: </b> Output Clock Divided by 8  <br>
<b> Yellow: </b> Down Signal <br>
<b> Brown: </b> Up Signal <br>
<b> Pink (at top): </b> ChargePump output <br>

40Mhz Output: <br>
Trend <br>
![](PostLayout/Simulation_Results/postlay40mhz295fFfullpicture.jpg)
Steady State <br>
![](PostLayout/Simulation_Results/postlay40mhz295fF.jpg)
<b> Blue constantly overlapping Red indicating locked state </b>

100Mhz Output: <br>
Trend <br>
![](PostLayout/Simulation_Results/postlay100mhz295fFfullpicture.jpg)
Steady State <br>
![](PostLayout/Simulation_Results/postlay100mhz295fF.jpg)
<b> Blue constantly overlapping Red indicating locked state </b>

<b>Output Specs:</b> <br>
40 Mhz:
![](PostLayout/Specs/PostLay40Mhz.jpg)

Exact 100Mhz:
![](PostLayout/Specs/PostLayExact100Mhz.jpg)

<h4> Phase Frequency Detector 'Up' Signal : </h4>

![](PostLayout/Simulation_Results/PFD_PostLay_Up.jpg)

<b>Red:</b> Clock 1 <br>
<b>Blue:</b> Clock 2 <br>
<b>Orange:</b> Up Signal <br>
<b>Green:</b> Down Signal

<h4> Phase Frequency Detector 'Down' Signal : </h4>

![](PostLayout/Simulation_Results/PFD_PostLay_Down.jpg)

<b>Red:</b> Clock1 2 <br>
<b>Blue:</b> Clock 2 <br>
<b>Orange:</b> Up Signal <br>
<b>Green:</b> Down Signal

<h4> Charge Pump response to 'Up' signal: </h4>

![](PostLayout/Simulation_Results/CP_PostLayout_Charge.jpg)

<b>Orange:</b> Charge Pump Output Voltage <br>
<b>Red:</b> Up Signal <br>
<b>Blue:</b> Down Signal

<h4> Charge Pump response to 'Down' signal: </h4>

![](PostLayout/Simulation_Results/CP_PostLayout_Discharge.jpg)

<b>Orange:</b> Charge Pump Output Voltage <br>
<b>Red:</b> Up Signal <br>
<b>Blue:</b> Down Signal

<h4> Charge Pump output rise due to charge leakage: </h4>

![](PostLayout/Simulation_Results/CP_PostLayout_Leakage.jpg)

<b>Orange:</b> Charge Pump Output Voltage <br>
<b>Red:</b> Up Signal <br>
<b>Blue:</b> Down Signal <br>
<b>Leakage:</b> < 0.05V in 100us <br>

<h4> Frequency Divider: </h4>

![](PostLayout/Simulation_Results/FD_PostLay.jpg)

<b>Red:</b> Input Clock <br>
<b>Blue:</b> Output Clock <br>


<h3> EDA Tools Used </h3>

* [kicad](https://kicad.org/) (schematic capture) <br>
* [ngspice](http://ngspice.sourceforge.net/download.html) (simulation) <br>
* [magic](http://opencircuitdesign.com/magic/) (layout design) 

<h3> Instructions </h3>

<h4> For using magic for layout: </h4>

* Get magic v8.3.82 or above from [here](http://opencircuitdesign.com/magic) <br>
* Place the tech file [sky130.tech](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/sky130.tech) in the folder where you'll be using magic <br>
* Open magic using the command:
    ```magic -T sky130```

<h4> For using ngpice for simulations: </h4>

* Get ngspice from [here](http://ngspice.sourceforge.net/) or for ubuntu users, just use this command: ```sudo apt-get install ngspice``` <br>
* Place the [sky130nm.lib](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/sky130nm.lib) file and the Sky130_Primitives folder in the location where you'll be running ngspice <br>
* Run the simulation: 
    ```ngspice circuitname.cir``` 

<h3> Future Scope </h3> 

* Incorporation of Trimmer Codes.
* Incorporation of PVT compensation circuit.

<h3> Acknowledgements </h3>

* I thank Mr. Kunal Ghosh co-founder VSD, for providing me the opportunity to  work on this wonderful project

<h3> Contact </h3>

* Lakshmi S (Author), MS ECE, Georgia Institute of Technology - lakshmi.sathi96@gmail.com
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com

