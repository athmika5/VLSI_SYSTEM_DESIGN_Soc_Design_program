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

#### Fed the required packages for the proper functionality of the OpenLANE flow
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
###### percentage of flop ratio = 0.1084296 * 100 = 10.84296

### Synthesis result file view 
![Screenshot 2024-09-20 145351](https://github.com/user-attachments/assets/8dc3eca7-b648-410b-b75e-834c8ae46409)
