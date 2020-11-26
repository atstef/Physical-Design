# **Physical design using open-source EDA Tools

## Table of Contents
###### Day-1   
- Physical Design Flow and Open source EDA tools prep
- Lab Exercises 
###### Day-2 
- Floorplan
- Placement
- Cell Design Flow
- Lab Exercises



### Day-1
Starting from folder:

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/1.PNG?raw=true)

./flow.tcl -interactive

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/2.PNG?raw=true)


package require openlane 0.9

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/3.PNG?raw=true)

prep -design picorv32a [-tag trial_run1 -overwrite]

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/4.PNG?raw=true)

A runs directory is created


### Day-2

Prepare data for interactive run. Alternatively you can run complete flow:        ./flow.tcl  -design spm

Sky130A_sky130_.....tcl overwrites all config settings

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/21.PNG?raw=true)


Try to modify clock frequency:

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/22.PNG?raw=true)

To set it on-the-fly you need to:

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/23.PNG?raw=true)

#run_synthesis
(yosys and abc)

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/24.PNG?raw=true)

Study the report

Number of flop counts … flop ratio

The results folder will have the synthesized netlist

ABC did the mappings

Yosys.stat.rpt :  gives the stats
See the timing reports

#run_floorplan
(we set the die area, core area, aspect ratio, utilization…, macro placement)
Std_cells are not placed now, but in placement


In:       openlane/configurations

README:

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/25.PNG?raw=true)

.tcl files have the default values

floorplan.tcl


./run_floorplan

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/26.PNG?raw=true)


Analyse results:

Logs/floorplan

.def files has information of orientation and location

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/27.PNG?raw=true)

Press S    (to select all)   and then V (to center in screen)

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/28.PNG?raw=true)

Zoom in  (left mouse click + right mouse click)

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/29.PNG?raw=true)

Press S over a metal 

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/210.PNG?raw=true)

Tapvpwrgnd --> for latchup

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/211.PNG?raw=true)


STD cells are placed temporarily

![alt text](https://github.com/atstef/Physical-Design/blob/main/images/212.PNG?raw=true)
