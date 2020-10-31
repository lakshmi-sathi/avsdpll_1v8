# 130nm PLL Clock Multiplier IP
8x PLL Clock Multiplier IP on the Google-Skywater 130nm node.

Tested through spice simulations on skywater 130nm tt corner at room termperature

Generates 8x Multiplied clock having 33% duty cycle

Output frequency obtained for input 5Mhz: 37MHz  (Required: 40Mhz)
Output frequency obtained for input 12.5Mhz: 95Mhz   (Required: 100Mhz)

PLL Output (tt, 27degree Celcius):

![](Images/PLL1.jpg)

Output Wave (33% Duty Cycle):

![](Images/DutyCycle.png)

Custom selection of Phase Detector and Frequency Divider circuits were made to improve stability and area/power consumption:
* Phase Detector

* Frequency Divider


Instructions for simulation:
* The required sky130nm primitives are present inside the 'Sky130_Primitives' folder and already included inside PLL.cir
* Install ngspice if not already installed: 
    On Ubuntu systems - "sudo apt-get install ngspice"
* Clone the repo:
    "git clone https://github.com/lakshmi-sathi/PLL_Clock_Multiplier_IP.git"
* Move to the cloned repo directory.
* Run the simulation: 
    "ngspice PLL.cir"


Acknowledgments:
* I thank Mr. Kunal Ghosh co-founder VSD, for providing me the opportunity to  work on this wonderful project
* I also thank Paras Gidd, who's work has been greatly helpful in helping me shape mine.
