# Session 1: Inception of open source EDA, OpenLANE and Sky130 PDK

# Theory:
[DIGITAL VLSI SOC DESIGN AND PLANNING_theory.docx](https://github.com/user-attachments/files/17077752/DIGITAL.VLSI.SOC.DESIGN.AND.PLANNING_theory.docx)

# Implimentation:
## Task 1:
### 1. Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.
### 2. Calulate the flop ratio with reference to number of dflipflop and number of cells
###### flop ratio = No of D flip flop / No of cells
###### percentage of flop ratio = flop ratio * 100

### 1. Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.
#### Invoke the OpenLANE flow and perform synthesis
#### => commands used :

#### Open the directory where the OpenLANE exists
###### cd Desktop/work/tools/openlane_working_dir/openlane

#### Invoke the OpenLANE flow docker sub-system by running below command
###### docker

#### Invoke the OpenLANE flow in the interactive mode using the below command
###### ./flow.tcl -interactive

#### Feed the required packages for the proper functionality of the OpenLANE flow
###### package require openlane 0.9

#### OpenLANE flow is ready to run any design and have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
###### prep -design picorv32a

#### Design is prepped and ready, run the synthesis using the command below
###### run_synthesis

#### Exit from OpenLANE flow
###### exit

#### Exit from docker sub-system
###### exit

### Screenshots of running these commands:

![Screenshot 2024-09-20 142436](https://github.com/user-attachments/assets/6e22a783-0779-4658-88a0-d250d878e198)

![Screenshot 2024-09-20 142336](https://github.com/user-attachments/assets/42b86b5d-f65a-4e59-9e26-06c437f64520)

![Screenshot 2024-09-20 143755](https://github.com/user-attachments/assets/6a49391e-a8f4-407e-adb0-322a99693e2a)

### 2.Calulate the flop ratio with reference to number of dflipflop and number of cells 

### Chip Area for the module - 'picorv32a'

![Screenshot 2024-09-20 144231](https://github.com/user-attachments/assets/b19ac39c-9538-4b78-949d-cc2a1dfa2c10)

### Number of D flip-flop

![Screenshot 2024-09-20 144527](https://github.com/user-attachments/assets/854fd101-9300-4d04-b8af-325b344c8b32)

### Number of cells 

![Screenshot 2024-09-20 144645](https://github.com/user-attachments/assets/40f79759-b810-4056-9ec7-0c7618894cd2)

### flop ratio and Percentage of flop ratio

###### flop ratio = 1613 / 14876 = 0.1084296
###### percentage of flop ratio = 0.1084296 * 100 = 10.84296 %

### Synthesis result file view 
![Screenshot 2024-09-20 145351](https://github.com/user-attachments/assets/8dc3eca7-b648-410b-b75e-834c8ae46409)

# Session 2: Good Floorplan vs Bad Floorplan and Introduction to Library cells

## Theory:


## Implementation:

### Task 2:
### 1. Run picorv32a design floorplan using OpenLANE flow and generate necessary outputs.
### 2. calculate the die area in microns from the height and width value from floorplan def.
### 3. load generated floorplan def in magic tool and explore the floorplan.
### 4. Run picorv32a design congestion aware placement using OpenLANE flow and generate necessary outputs.
### 5. load generated placement def and view the placement of standard cell in the core area.
###### area of die in micron = die width in microns * die height in microns

### 1. Run picorv32a design floorplan using OpenLANE flow and generate necessary outputs.

#### Commands used to invoke the OpenLANE flow and to run floorplan are:

#### Open the directory where the OpenLANE exists
###### cd Desktop/work/tools/openlane_working_dir/openlane

#### Invoke the OpenLANE flow docker sub-system by running below command
###### docker

#### Invoke the OpenLANE flow in the interactive mode using the below command
###### ./flow.tcl -interactive

#### Feed the required packages for the proper functionality of the OpenLANE flow
###### package require openlane 0.9

#### OpenLANE flow is ready to run any design and have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
###### prep -design picorv32a

#### Design is prepped and ready, run the synthesis using the command below
###### run_synthesis

#### run the floorplan
###### run_floorplan

### Screenshot of Floorplan run
![Screenshot 2024-09-21 154903](https://github.com/user-attachments/assets/d5ee279d-7884-4d90-9fe4-3cbdce97e678)

![Screenshot 2024-09-21 143345](https://github.com/user-attachments/assets/74e95b03-5bf2-4d6d-9bfa-e2150cc073c3)

### Utilization screenshot
![Screenshot 2024-09-21 154142](https://github.com/user-attachments/assets/bc4bdeb6-4a71-41ee-aa10-4f4b33196fa2)

![Screenshot 2024-09-21 154259](https://github.com/user-attachments/assets/c44cfbe0-93b8-45f6-9d58-6a6854c2d8fb)

### Floorplan result def file
![Screenshot 2024-09-21 155226](https://github.com/user-attachments/assets/bf2a65d4-6172-4673-8196-87463bc481a8)

### 2. Calculate the die area in microns from the height and width value from floorplan def.

### Screenshot of floorplan def file which has information of width, height and area of die

![Screenshot 2024-09-21 155358](https://github.com/user-attachments/assets/a7c59006-3bb9-41bd-8861-17470e0f845c)

### Calculation of Area of die in micron

###### 1000 unit/distance = 1 micron
###### width of die in unit/distance = 660685
###### height of die in unit/distance = 671405
###### width of die in microns = 660685/1000 = 660.685
###### height of die in microns = 671405/1000 = 671.405
###### Area of die in microns = 443587.212 square microns

### 3. Load generated floorplan def in magic tool and explore the floorplan.

### Commands used to load floorplan def into magic tool is:

#### Open the directory where the floorplan def exists
###### cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-09_08-45/results/floorplan/

#### Command to load the def file into magic tool
###### magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &

### Screenshot of command
![Screenshot 2024-09-21 161053](https://github.com/user-attachments/assets/04c66067-8a63-4715-87ab-ed038b8fef2e)

### Screenshot of floorplan def in magic tool
![Screenshot 2024-09-21 160352](https://github.com/user-attachments/assets/bd637cd2-ccf8-43b1-99c7-53160d51eb73)

### Screenshot of pins which are placed with equal spacing
![Screenshot 2024-09-21 160818](https://github.com/user-attachments/assets/ee72983b-9159-4a9b-9e1f-2e42309f3c5f)

### Screenshot of port layers - vertical and horizontal
![Screenshot 2024-09-21 162352](https://github.com/user-attachments/assets/4573df92-53d3-47d3-8fc9-9664a4b00355)

### Unplaced standard cells
![Screenshot 2024-09-21 162439](https://github.com/user-attachments/assets/3da6ab76-917e-429c-81dd-f0153cdc5988)

### 4. Run picorv32a design congestion aware placement using OpenLANE flow and generate necessary outputs.

### Command used to run placement is
###### run_placement

### Screenshot of placement run 
![Screenshot 2024-09-21 183125](https://github.com/user-attachments/assets/9c02fa5d-55b6-46b0-b633-05390d5879fe)

### 5. load generated placement def and view the placement of standard cell in the core area.

### Commands used to load placement def in magic tool

#### Open the directory where the placement def file exists
###### cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-09_08-45/results/placement/

#### load the placement def into the magic tool 
###### magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

### Screenshot of placement def in magic tool
![Screenshot 2024-09-21 182704](https://github.com/user-attachments/assets/d37bfc05-68d4-4ad9-9194-2468bfe469c6)

### Screenshot of Standard cell placement in the core area
![Screenshot 2024-09-21 182820](https://github.com/user-attachments/assets/1e4bc3e0-0b04-4c84-8e99-c58dbfc52d41)

