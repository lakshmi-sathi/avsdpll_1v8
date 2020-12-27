# 130nm PLL Clock Multiplier IP
8x PLL Clock Multiplier IP on the Google-Skywater 130nm node.

Tested through spice simulations on skywater <b>130nm tt corner at room termperature</b>

Generates 8x Multiplied Clock

<b> Pre-Layout: </b> <br>

Frequency Obtained for 5Mhz input: &nbsp;&nbsp;&nbsp;40MHz <br>
Frequency Obtained for 12.5Mhz input: &nbsp;&nbsp;&nbsp;100MHz

Duty Cycle obtained: &nbsp;&nbsp;&nbsp;46% at 40MHz and 40.6% at 100MHz

Lock-in starts at ~80us for 100MHz and ~120us for 40Mhz

3rd-Order Loop Filter used [c1, c2, c3, r1, r2, r3]: &nbsp;&nbsp;&nbsp;355fF, 350fF, 345fF, 490, 490, 490.

<b> Post-Layout: </b> <br>

Frequency Obtained for 5Mhz input: &nbsp;&nbsp;&nbsp;40MHz <br>
Frequency Obtained for 12.5Mhz input: &nbsp;&nbsp;&nbsp;100MHz

Duty Cycle obtained: &nbsp;&nbsp;&nbsp;52.7% at 40MHz and 50% at 100MHz

Lock-in starts at ~22us for 100MHz and ~37us for 40Mhz

3rd-Order Loop Filter used [c1, c2, c3, r1, r2, r3]: &nbsp;&nbsp;&nbsp;295fF, 300fF, 305fF, 490, 490, 490.

<h2> Contents: </h2>

1. [Google-SkyWater 130nm PDK](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Google-SkyWater-130nm-PDK-)
2. [Specifications](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Specifications-)
3. [Pre-Layout Simulations](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Pre-Layout-Simulations-)
4. [Layout](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Layout-)
5. [Post-Layout Simulations](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Post-Layout-Simulations-)
6. [Instructions](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Instructions-)
7. [EDA tools used](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-EDA-Tools-Used-)
8. [Preparing your IP for Tapeout](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Preparing-your-IP-for-Tapeout-)
9. [References](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-References-)
10. [Future Scope](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Future-Scope-)
11. [Acknowlegements](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Acknowledgements-)
12. [Contact](https://github.com/lakshmi-sathi/avsdpll_1v8/blob/main/README.md#-Contact-)

<h3> Google-SkyWater 130nm PDK: </h3>

>This PLL circuit is built on the [Google-Skywater 130nm](https://github.com/google/skywater-pdk) node. It is a mature 180nm-130nm hybrid technology originally developed internally by Cypress Semiconductor. The SkyWater Open Source PDK is a collaboration between Google and SkyWater Technology Foundry to provide a fully open source Process Design Kit and related resources, which can be used to create manufacturable designs at SkyWater’s facility. 

<h3> Specifications </h3>

| Parameter | Description | min | typ | max | Unit | Conditions |
| --- | --- | --- | --- | --- | --- | --- |
| VDD | Digital Supply | - | 1.8 | - | V | T = 27C |
| F<sub>CLKREF</sub> | Reference | 5 | - | 12.5 | MHz | T = 27C |
| F<sub>CLKOUT</sub> | Output Clock | 40 | - | 100 | MHz | PLL Mode, T = 27C |
| F<sub>CLKOUT</sub> | Output Clock | - | - | - | MHz | VCO Mode, T = 27C |
| J<sub>RMS</sub> | Jitter (rms) | - | - | - | ps | PLL_Mode |
| DC | Duty Cycle | 52.7 | - | 50 | % | T = 27C | 
| T<sub>SET</sub> | Settling Time | ~37 | - | ~22 | us | T = 27C |
| C<sub>L</sub> | Load Capacitance | - | - | - | fF | T = 27C |
| IDD | Supply Current | - | - | - | fF | T = 27C |


<h3> Pre-Layout Simulations </h3>

<h4> PLL Output (tt, 27degree Celcius): </h4>

<b> Red: </b> Reference Clock  <br> 
<b> Blue: </b> Output Clock Divided by 8  <br>
<b> Yellow: </b> Down Signal <br>
<b> Brown: </b> Up Signal <br>
<b> Pink (at top): </b> ChargePump output <br>

<h4> 40Mhz Output: </h4>
    
<h4>-Close-up </h4>

![](PreLayout/Simulation_Results/40Mhzzoomin.jpg)
    
<h4>-Steady State <br></h4>

![](PreLayout/Simulation_Results/5MhzInputSteadyState.png)
<b> Blue constantly overlapping Red indicating locked state </b>

<h4>-Trend <br> </h4>

![](PreLayout/Simulation_Results/5MhzInputFullPicture.jpg)

<b>100Mhz Output: </b><br>

<h4>-Close-up </h4>

![](PreLayout/Simulation_Results/100Mhzzoomin.jpg)

<h4>-Steady State <br></h4>

![](PreLayout/Simulation_Results/12.5MhzInputSteadyState.jpg)
<b> Blue constantly overlapping Red indicating lock </b>

<h4>-Trend <br></h4>

![](PreLayout/Simulation_Results/12.5MhzInputFullPicture.jpg)

<b>Output Specs:</b> <br>
-Exact 40 Mhz
![](PreLayout/Specs/Exact40Mhz.jpg)

-Exact 100Mhz
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

<b>40Mhz Output: </b> <br>

<h4>-Close-up </h4>

![](PostLayout/Simulation_Results/PostLay40Mhzzoomin.jpg)
<h4>-Steady State </h4>

![](PostLayout/Simulation_Results/postlay40mhz295fF.jpg)
<b> Blue constantly overlapping Red indicating locked state </b> <br>

<h4>-Trend <br></h4>

![](PostLayout/Simulation_Results/postlay40mhz295fFfullpicture.jpg)

<b>100Mhz Output:</b> <br> 
<h4>-Close-up <br></h4>

![](PostLayout/Simulation_Results/Postlay100Mhzzoomin.jpg)

<h4>-Steady State <br></h4>

![](PostLayout/Simulation_Results/postlay100mhz295fF.jpg)
<b> Blue constantly overlapping Red indicating locked state </b> <br> 
<h4>-Trend</h4>

![](PostLayout/Simulation_Results/postlay100mhz295fFfullpicture.jpg)




<b>Output Specs:</b> <br>
-40 Mhz
![](PostLayout/Specs/PostLay40Mhz.jpg)

-Exact 100Mhz
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
    
<h3> EDA Tools Used </h3>

* [kicad](https://kicad.org/) (schematic capture) <br>
* [ngspice](http://ngspice.sourceforge.net/download.html) (simulation) <br>
* [magic](http://opencircuitdesign.com/magic/) (layout design) 

<h3> Preparing your IP for Tapeout </h3>

For any design to be tapeout ready there are more requirements than just having a finished and tested IP Layout.<br>
For Example, a proper GPIO (cells that enable the IP to be interfaced with external world) is needed for connecting the IP pins to the package (the final DIP or Surface Mount case in which the IC comes in from the Fab) <br>

To meet these requirements either we need to take care of them individually by ourself (which may get complicated and time consuming) or, <br>
we can choose a vehicle for enabling our IP to meet the requirements to go through the fabrication process. <br>
Here we will be using [Efabless Caravel SoC template](https://github.com/efabless/caravel) as the Vehicle. <br>

Before we start, this is the [datasheet](https://github.com/efabless/caravel/blob/master/doc/caravel_datasheet.pdf) of the Caravel SoC from [Efabless](https://efabless.com/), <br>
and these are the parts involved in it: <br>

![](Images/CaravelSoCTemplate.jpg)
The Mega Project Area (MPRJ) or 'user_project_wrapper' or in other words 'the container' is where we will place and route our IP.

<h4> Basic Steps Overview: </h4>

* Initial setup.
* Place and Route the IP inside the container (keep in mind to not have any DRCs).
* Verify Connectivity.
* Integrate the container onto the Caravel SoC.
* Check if everything is as expected including DRC (Precheck).

Getting it ready is as direct as this. We will see in detail the steps involved in context of Caravel SoC and Google-Skywater OpenShuttle.

<h4> Steps in Detail: </h4>

<h5> 1) Initial Setup </h5> 

Steps:
* Fork and clone Caravel
* Uncompress files
* Install PDK

-> Fork and 'git clone' the Caravel SoC. <br> <br>
Select the 'Fork' option on the top right of the [Caravel Github](https://github.com/efabless/caravel) repo. <br>
Specify a name for your fork and then clone it (somewhere on your system where you want to integrate the design onto the Caravel SoC):
> git clone \<url of your fork\>

![](Images/caravel_repo_root.jpg)
<br>
Here we can see the content of the Caravel Repo. Each type of file is placed in it's respective folder. <br>
Our main focus is the 'gds' folder which contains all the Layout GDS files. <br> <br>

We can see that several files have '.gz' extension. All these files are compressed files. This compression is in place to meet the Github size limit on individual files. <br>
They need to be uncompressed for working on them. <br>
-> This can be done the right way by moving to the root folder (the folder which is the local clone of the forked caravel repo) and giving:
> make uncompress

Now we need to setup the [Google-Skywater PDK](https://github.com/google/skywater-pdk) on the machine on which this integration is to be performed. <br>
-> The entire PDK installation is provided as a two step process: <br>
> export PDK_ROOT=\<location where you want to install it\> 

&nbsp;You would want to install it outside the local clone of the caravel repo since finally it has to be pushed back to Github. <br>
-> Move to the root folder and give:
> make pdk

This downloads and installs the pdks in the location specified earlier (It takes a significant amount of time).
    
<h5> 2) Place and Route </h5>

There are two ways to place and route:
* Automatically (Openlane) - commonly used in large digital designs.
* Manually - good for designs that aren't having too many pins to interface.

Here in context of the PLL IP, we will be proceeding along the Manual method of placing and routing the IP. <br>
For more information on the automatic method follow this [link](https://github.com/efabless/caravel/blob/master/openlane/README.md).

For placing and routing the IP manually the magic layout tool can be used:
* export the PDK_ROOT variable with the location of the PDK installation.
* cd to the 'mag' folder and open magic layout tool (this is since the .magicrc configuration file is in this folder).

  This is how to open magic with the right configuration for Caravel with the installed PDK:
  ![](Images/opening_magic.jpg)
  
* Select File -> Read GDS and open user_project_wrapper.gds from 'gds' folder (this is the container where we are going to place the IP).
* Select Cell -> Place Instance and select the mag file of the IP you want to insert (this allows you to place your IP inside this container).

![](Images/place_ip.jpg)

![](Images/PLL_in_caravel.jpg)

* After Placing the IP by seeing a location with the right I/O pins, manually route the IP pins to the appropriate pins on the container (refer to the datasheet mentioned earlier). Keep in mind to avoid DRC errors.
* Select File -> Write GDS and write out the GDS file for the modified container (remember that the final container in which the IP is placed should be named user_project_wrapper.gds and it should be inside 'gds' folder, this is required for the integration step using 'make' to work).

<h5> 3) Verify Connectivity </h5>

In context of the a manual connectivity check for it's connectivity to the container pins is performed. You may want to have an automated process if your design has a large number of pins.<br>

The connectivity check can be done through the simple yet effective net tracing feature of the magic layout tool:
* Select any part of the net you wish to trace using the 's' key.

Reference net or Input clock net can be seen selected in this image:
![](Images/selected.jpg)

* Press 's' multiple times to see the net being traced till it's endpoints.

![](Images/net_trace.jpg)

Now the fully highlighted net enables us to see which pin is connected where.<br>
This way we can do the same for all nets interfacing the IP to the container to verify the connectivity.

<h5> 4) Integrating Container to Caravel SoC </h5>

The Caravel Repo uses a simple 'make' based method to integrate the container onto the Caravel SoC. <br>

All that needs to be done, once all the place, route and verification is completed, <br>
is to move to the root folder (the folder which is the local clone of the forked caravel repo) and, <br>
give the 'make' command. This integrates the container onto the Caravel SoC (takes about 10-15mins usually). <br>

We can see that in 'gds' folder a 'caravel.gds' file is generated. <br>
This is the final gds file which is to be used by the Fab for fabricating the IC.

<h5> 5) Precheck </h5>

The precheck is provided as a [separate repo](https://github.com/efabless/open_mpw_precheck) by Efabless.
This was the precheck for Google-Skywater-Efabless open MPW shuttle 2020, on which this guide will be based. It would be different for different tapeout runs and you would need to find the one for the specific tapeout run that you are tagetting.

Efabless Caravel Precheck is designed to run on docker (a container for software, kind of like Virtual Machine). Follow this [link](https://docs.docker.com/engine/install/ubuntu/) to know how to install docker. <br>

Clone the Efabless precheck repo and follow these steps to run the precheck on your finished Caravel:
* Fetch their open_mpw_precheck docker

``` cd dependencies
sh build-docker.sh
docker pull efabless/open_mpw_precheck:latest
```

* Load the precheck docker (assuming the PDK is already installed from the Caravel repo as mentioned earlier in the initial setup step)
```
export PDK_ROOT=< location where the PDK was installed >
export TARGET_PATH=< location where you have the forked and cloned Caravel repo where the completed caravel exists >
docker run -it -v $(pwd):/usr/local/bin -v $TARGET_PATH:$TARGET_PATH -v $PDK_ROOT:$PDK_ROOT -e TARGET_PATH=$TARGET_PATH -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/open_mpw_precheck:latest
```

After docker loads you should see 'bash $' indication on the terminal.

* Run the precheck
```
python3 open_mpw_prechecker.py [-h] --target_path < the target path given earlier > --pdk_root < the pdk location given earlier > --waive_fuzzy_checks
```
This should run the precheck and tell you which of the checks failed, which passed and whether there are any DRC violations.<br>

![](Images/precheck.jpg)

Contact the organisation facilitating the tapeout run you are interested in and enquire what other steps are required to ensure tapeout readiness.<br><br>
And you are done! <br>

<h5> Fun Fact! </h5>
The Google-Skywater openshuttle 2020, was the first of its kind where any individual could have his/her open-source IP design fabricated and delivered for free (costs sponsored by Google), which would otherwise be in many thousands of US dollars. This PLL IP fabrication was enabled through it.

![](Images/open_mpw_shuttle.jpg)

<h3> References </h3>

<b>[1]</b> K.K. Abdul Majeed, Binsu J. Kailath, A Novel Phase Frequency Detector for a High Frequency PLL Design, Procedia Engineering, Volume 64, 2013, Pages 377-384, ISSN 1877-7058,
doi: 10.1016/j.proeng.2013.09.110. <br> <br> 
<b>[2]</b> X. Liu and A. N. Willson, "A pA-leakage CMOS charge pump for low-supply PLLs," 2010 53rd IEEE International Midwest Symposium on Circuits and Systems, Seattle, WA, 2010, pp. 1037-1040, doi: 10.1109/MWSCAS.2010.5548821. <br> <br> 
<b>[3]</b> Suman, Shruti & Sharma, Krishna. (2018). An Improved Performance Ring VCO: Analysis and Design. Ciência e Técnica Vitivinícola. 33. 254-0223. <br> <br> 
<b>[4]</b> Karbalaei Mohammad Ali, M., Hashemipour, O. A simple and high performance charge pump based on the self-cascode transistor. Analog Integr Circ Sig Process 100, 633–638 (2019). doi: 10.1007/s10470-019-01478-y <br> <br> 
<b>[5]</b> Y. -. Choi and D. -. Han, "Gain-Boosting Charge Pump for Current Matching in Phase-Locked Loop," in IEEE Transactions on Circuits and Systems II: Express Briefs, vol. 53, no. 10, pp. 1022-1025, Oct. 2006, doi: 10.1109/TCSII.2006.882122. <br> <br> 
<b>[6]</b> Agrawal, Abhishek and Nikhil Saxena. “Comparative Analysis of High Speed FBB TSPC and E-TSPC Frequency Divider at 32 nm CMOS process,” International Journal of Trend in Research and Development (2017), Volume 4(1), ISSN: 2394-9333.


<h3> Future Scope </h3> 

* Incorporation of Trimmer Codes.
* Incorporation of PVT compensation circuit.

<h3> Acknowledgements </h3>

* I thank Mr. Kunal Ghosh, co-founder [VSD](https://www.vlsisystemdesign.com/), for providing me the opportunity to  work on this wonderful project.
* I thank [Google](https://github.com/google), [Skywater](https://www.skywatertechnology.com/) and [Efabless](https://efabless.com/) for bringing this wonderful [opportunity](https://www.skywatertechnology.com/press-releases/google-partners-with-skywater-and-efabless-to-enable-open-source-manufacturing-of-custom-asics/) to the world and making this project tapeout possible.

<h3> Contact </h3>

* Lakshmi S (Author), MS ECE - lakshmi.sathi96@gmail.com
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com

