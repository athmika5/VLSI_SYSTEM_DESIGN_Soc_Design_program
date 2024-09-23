![Screenshot 2024-09-22 235708](https://github.com/user-attachments/assets/9e78d731-ce26-4c95-b4a4-274db36ac33c)# Session 1: Inception of open source EDA, OpenLANE and Sky130 PDK

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
[Session2_Theory.docx](https://github.com/user-attachments/files/17085508/Session2_Theory.docx)

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

# Session 3: Design Library Cell using Magic Layout and ngspice characterization

# Implimentation
## Task 3

### 1. Clone custom inverter standard cell design from github repository: Standard cell design and characterization using OpenLANE flow
### 2. Load the custom inverter layout in the magic and explore.
### 3. Spice extraction of inverter in the magic.
### 4. Editing the spice model file for analysis through simulation.
### 5. Post-layout ngspice simulation.
### 6. Find problem in the DRC section of the old magic tech file for the skywater process and fix them

### 1. Clone custom inverter standard cell design from github repository: Standard cell design and characterization using OpenLANE flow

#### Change directory to openlane
###### cd Desktop/work/tools/openlane_working_dir/openlane

#### Clone the github repository with custom inverter design
###### git clone https://github.com/nickson-jose/vsdstdcelldesign

#### Change into the repository direction
###### cd vsdstdcelldesign

#### Copy magic tech file to the repository direction, for the easy access
###### cp sky130A.tech /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign

#### Check conents to view the tech file
###### ls -ltr

#### Command to open custom inverter layout in magic
###### magic -T sky130A.tech sky_130_inv.mag &

### Screenshot of these commands
![Screenshot 2024-09-22 151340](https://github.com/user-attachments/assets/33998846-9237-4f75-b493-31384c44f37f)

![Screenshot 2024-09-22 151924](https://github.com/user-attachments/assets/418d91f7-dae1-44a4-89ef-f5c5f6b202df)

![Screenshot 2024-09-22 152236](https://github.com/user-attachments/assets/fb087e47-cbfc-4545-878c-1c835a1b7d98)

### 2. Load the custom inverter layout in the magic and explore.

#### Screenshot of custom inverter layout in magic
![Screenshot 2024-09-22 152409](https://github.com/user-attachments/assets/dbedc16b-b340-4f06-a8f7-fbd9df2fa339)

#### NMOS and PMOS identified 
![Screenshot 2024-09-22 202533](https://github.com/user-attachments/assets/83b89a70-4b45-43fb-8545-f92709dace6d)

#### By double clicking on the box, we can view where it is connected.
#### Screenshot of Nmos source connecting to Ground

![Screenshot 2024-09-22 203034](https://github.com/user-attachments/assets/ba4d0765-8e52-482f-91dc-21304b085184)

### 3. Spice extraction of inverter in the magic.

#### Commands for spice extraction of the custom inverter layout in tkcon window of magic

#### Check the current directory
###### pwd

#### Extraction command to extract to .ext format
###### extract all

#### Before converting ext to spice this command enables the parasitic extraction also
###### ext2spice cthresh 0 rthresh 0

#### Converting to .ext to .spice
###### ext2spice

### Screenshot of tkcon window after running above commands
![Screenshot 2024-09-22 215712](https://github.com/user-attachments/assets/0d4fe0ed-ff5f-4b11-9fc4-c80a690a0ddf)

![Screenshot 2024-09-22 233604](https://github.com/user-attachments/assets/3e67d650-19fc-44a5-acfe-e72c532c8562)

#### Screenshot of created spice file
![Screenshot 2024-09-22 220251](https://github.com/user-attachments/assets/2ad1ed2e-3d28-4bab-873b-32c3b97c5d67)

### 4. Editing the spice model file for analysis through simulation.

#### Final edited spice file ready for ngspice simulation

![Screenshot 2024-09-22 235935](https://github.com/user-attachments/assets/acd5567c-8978-4d15-8003-d2fcd9da6f77)

### 5. Post-layout ngspice simulation.

#### Commands for ngspice simulation

#### Command to directly load spice file ngspice sky130_inv.spice
###### ngspice sky130_inv.spice

#### Load the plot
###### plot y vs time a

### Screenshots of ngspice run
![Screenshot 2024-09-22 221835](https://github.com/user-attachments/assets/5cc60ef1-23a2-4fe3-87cd-5407b2da58fc)

![Screenshot 2024-09-22 235708](https://github.com/user-attachments/assets/33dce9db-174e-4ef0-ac53-710a53b9709b)

### Generated plot
![Screenshot 2024-09-23 000029](https://github.com/user-attachments/assets/4a375332-19d4-47ac-a22b-aed33a496c86)

### Rise transition calculation

###### Rise transition time = Time taken for the output to rise to 80% - time taken for output to rise to 20%
###### 20% of output = 660mV
###### 80% of output = 2.64V

### Screenshot of 20% screenshot
![Screenshot 2024-09-23 002048](https://github.com/user-attachments/assets/2d2e0a22-812d-4d01-88fe-8a9d3346abd1)

### Screenshot of 80% screenshot
![Screenshot 2024-09-23 003214](https://github.com/user-attachments/assets/0b018410-d51c-4893-ad16-619e820d1efe)

###### Rise transition time = 2.24647 - 2.1824 = 0.06407

### fall transition calculation
