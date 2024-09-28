![Screenshot 2024-09-26 005610](https://github.com/user-attachments/assets/47d5c020-72b7-4771-a75e-765f366aa3aa)# Session 1: Inception of open source EDA, OpenLANE and Sky130 PDK

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
###### Rise transition time = Time taken for the output to fall to 20% - time taken for output to fall to 80%
###### 20% of output = 660mV
###### 80% of output = 2.64V

### Screenshot of 20% of output
![Screenshot 2024-09-23 003326](https://github.com/user-attachments/assets/c489bab8-367e-4360-b0b4-76c8e947d322)

### Screenshot of 80% of output
![Screenshot 2024-09-23 003432](https://github.com/user-attachments/assets/17232d97-cf74-42b8-be0b-8c0ceb99e2b1)

###### fall transition time = 4.094-2.244
![Screenshot 2024-09-23 003514](https://github.com/user-attachments/assets/2bea1d5a-2ca3-418f-a9ef-0638cca0ede9)

### Rise Cell Delay Calculatuion

###### Rise Cell Delay = time taken for a output to rise to 50% - time taken for a input to fall to 50%
###### 50% of 3.3V = 1.65V
### Screenshot of 50% rise output
![Screenshot 2024-09-23 003801](https://github.com/user-attachments/assets/06d62bb6-c1dc-4c36-aaad-71d0afd8470c)
![Screenshot 2024-09-23 003917](https://github.com/user-attachments/assets/ab0cdca6-e2fe-421e-b00a-abde904345af)

###### Rise Cell Delay = 2.21-2.14 = 0.07

### Fall cell delay Calculation

###### Fall cell delay = time taken for a output to fall to 50% - time taken for a input to rise to 50%

### Screenshot of 50% output fall
![Screenshot 2024-09-23 004106](https://github.com/user-attachments/assets/3a52c68c-642a-499a-9992-e40ed13b303d)
![Screenshot 2024-09-23 004143](https://github.com/user-attachments/assets/c5981aee-4b44-4429-b18f-f68e06db96da)

###### Fall cell delay = 4.077-4.05 = 0.027

### 6. Find problem in the DRC section of the old magic tech file for the skywater process and fix them

#### Link to Sky130 Periphery rules:
###### https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html

##### Commands to download and view the corrupted skywater process magic tech files and associated files to perform drc corrections

###### change the home directory
###### cd

###### Command to download the lab files
###### wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz

###### Command to extract drc_tests
###### tar xfz drc_tests.tgz

###### Change directory into the lab folder
###### cd drc_tests

###### List all files and directories present in the current directory
###### ls -al

###### Command to view .magicrc file
###### gvim .magicrc

###### command to open magic tool in better graphics
###### magic -d XR &

###### Screenshot command use
![Screenshot 2024-09-23 013324](https://github.com/user-attachments/assets/93015db5-97d7-4f63-9d14-297e534d890e)
![Screenshot 2024-09-23 013447](https://github.com/user-attachments/assets/4b64ef78-9cf8-4e05-bf51-7af7e4b1d6c1)

#### Screenshot of .magicrc file
![Screenshot 2024-09-23 013524](https://github.com/user-attachments/assets/ea57da71-d200-478f-916b-9c2c14e56937)

#### Loading met3 file to magic and observe rule violation

![Screenshot 2024-09-23 014353](https://github.com/user-attachments/assets/f8b58099-ae1b-49f4-876e-f94484e71b15)

#### Command to Check DRC error in tkcon
###### drc why

#### To check width height of metal in tkcon
###### box
### Screenshot of commands
![Screenshot 2024-09-23 014753](https://github.com/user-attachments/assets/d89d21a5-7bb8-4bd1-a854-b3a4caea3cd6)
![Screenshot 2024-09-23 015310](https://github.com/user-attachments/assets/848eca19-ce1c-4970-9a2d-f4c05cadcb2c)

### Incorrectly implimented poly.9 simple rule correction

#### Load poly file 
![Screenshot 2024-09-23 015445](https://github.com/user-attachments/assets/390aab04-a5b5-48f7-8229-f6c42992b697)

### Incorrectly implimented poly.9 rule no drc violation even though spacing <0.48
![Screenshot 2024-09-23 015500](https://github.com/user-attachments/assets/5e4d99d2-e6b4-406c-9518-73c22818a1d9)

![Screenshot 2024-09-23 015823](https://github.com/user-attachments/assets/9a521ecd-8e95-4387-a438-768f87c33d40)

![Screenshot 2024-09-23 015800](https://github.com/user-attachments/assets/b4ffe69f-d065-4e6b-a44f-39e0abf318d6)

#### New commands inserted in sky130A.tech file to update drc
![Screenshot 2024-09-23 021104](https://github.com/user-attachments/assets/3ac9dcf6-771d-457a-b6bb-86d311311787)

### Commands to run in tkcon window

#### Loading updated tech file
###### tech load sky130.tech

#### Re-Run DRC 
###### drc check

#### selecting region displaying the new erros and getting the error message
###### drc why
![Screenshot 2024-09-23 015800](https://github.com/user-attachments/assets/60c1b9d7-5e23-4556-955c-52e3fea9b04b)

#### Load Metal contact file to magic and check the violations

#### Screenshot
![Screenshot 2024-09-23 022844](https://github.com/user-attachments/assets/dff4ee95-58b9-4326-b78c-5c33f71ea2ae)


# Section 4: Pre-layout timing analysis and importance of good clock tree

## Implementation

## Task: 4
### 1. Fix up small DRC errors and verify the design is ready to be inserted into our flow
### 2. Save the finalized layout with custom name and open it.
### 3. Generate lef from the layout.
### 4. Copy the newly generated lef and associated required lib files to 'picorv32a' design 'src' directory.
### 5. Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.
### 6. Run openlane flow synthesis with newly inserted custom inverter cell.
### 7. Remove/reduce the newly introduced violations with the introduction of custom inverter cell by modifying design parameters.
### 8. Once synthesis has accepted our custom inverter we can now run floorplan and placement and verify the cell is accepted in PnR flow.
### 9. Do Post-Synthesis timing analysis with OpenSTA tool.
### 10. Make timing ECO fixes to remove all violations.
### 11. Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.
### 12. Post-CTS OpenROAD timing analysis.
### 13. Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.

## 1. Fix up small DRC errors and verify the design is ready to be inserted into our flow

### Conditions to be checked in the custom designed cell layout:

#### Condition 1: The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks
#### Condition 2: Width of the standard cell should be odd multiples of the horizontal track pitch.
#### Condition 3: Height of the standard cell should be even multiples of the vertical track pitch.

### Commands to open the custom inverter layout

#### open the vsdstdcelldesign directory
###### cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
#### Open custom inverter layout in magic
###### magic -T sky130A.tech sky130_inv.mag &

### Screenshot of tracks.info of sky130_fd_sc_hd
![Screenshot 2024-09-24 192231](https://github.com/user-attachments/assets/da9075c6-e5c5-44f0-bd2c-edd8fc72fba9)

![Screenshot 2024-09-24 192913](https://github.com/user-attachments/assets/e895cd18-fec7-46ba-8a5c-cfdd95fa80fb)

### Commands for tkcon window to set grid as tracks of locali layer

#### Get syntax for grid command
###### help grid
#### Set grid values accordingly
###### grid 0.46um 0.34um 0.23um 0.17um

#### Screenshot of tkcon commands
![Screenshot 2024-09-24 193424](https://github.com/user-attachments/assets/7045ea7e-44d0-47b1-895e-aadb8b315eb6)

#### Condition 1 verified
![Screenshot 2024-09-24 193709](https://github.com/user-attachments/assets/868b1516-688b-40cc-b0ed-84cb4d9b3d05)

#### Condition 2 verified
![Screenshot 2024-09-24 195840](https://github.com/user-attachments/assets/1b61c6d0-69cd-4aaa-9db6-6f62587487ad)

#### Condition 3 verified
![Screenshot 2024-09-24 193448](https://github.com/user-attachments/assets/cb4a5dbb-3f9c-4a94-bdc6-9b4690ec7ff7)

### 2. Save the finalized layout with custom name and open it.

#### Command to save the layout with custom name in tkcon
###### save sky130_vsdinv.mag
![Screenshot 2024-09-24 201404](https://github.com/user-attachments/assets/478815d0-e39c-4d8f-96b0-3ebe410a1fcc)

#### Command to open custom inverter layout in magic
###### magic -T sky130A.tech sky130_vsdinv.mag &
![Screenshot 2024-09-24 201618](https://github.com/user-attachments/assets/dba83381-40c7-4378-9d94-17d164132119)

#### Screenshot of custom inverter layout
![Screenshot 2024-09-24 201541](https://github.com/user-attachments/assets/82bd4d9d-6f3b-4ea4-8283-954b8dc555e0)

### 3. Generate lef from the layout.

#### Command to write lef in tkcon 
###### left write

#### Screenshot of command
![Screenshot 2024-09-24 201710](https://github.com/user-attachments/assets/4ece704b-e87b-448c-b3a1-c1e5239134a0)

#### Screenshot of newly created lef file
![Screenshot 2024-09-24 201943](https://github.com/user-attachments/assets/f99cafd7-d909-498b-8dcb-c4315b3ed1a1)

### 4. Copy the newly generated lef and associated required lib files to 'picorv32a' design 'src' directory.

#### Copy lef file
###### cp sky130_vsdinv.lef /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

#### Check whether it's copied or not
###### ls /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

#### Copy lib files
###### cp libs/sky130_fd_sc_hd__* /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

#### Check whether it's copied or not
###### ls /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

### Screenshot of command
![Screenshot 2024-09-24 214502](https://github.com/user-attachments/assets/c3166ad3-5e4f-4275-bde6-c0d63df2e6c9)

![Screenshot 2024-09-24 214618](https://github.com/user-attachments/assets/6529cc52-c0dc-437f-b8f2-734bf25bb7ad)

### 5. Edit 'config.tcl' to change lib file and add the new extra lef into the openlane flow.

#### Commands to be added to config.tcl to include our custom cells in the openlane flow

###### set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
###### set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
###### set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
###### set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

###### set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]

### Edited Config.tcl to include the added lef and change library to ones we added in src directory
![Screenshot 2024-09-24 223500](https://github.com/user-attachments/assets/829a6a6e-e33f-40fd-9c24-7a54839ed37c)

### 6. Run openlane flow synthesis with newly inserted custom inverter cell.

### Commands to invoke the OpenLANE flow include new lef and perform synthesis

#### Open the Openlane flow directory
###### cd /Desktop/work/tools/openlane_working_dir/openlane/

#### Invoke the OpenLANE flow docker sub-system 
###### docker

#### Invoke the OpenLANE flow in the Interactive mode using the following command
###### ./flow.tcl -interactive

#### prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
###### prep -design picorv32a

#### Additional commands to include newly added lef to openlane flow
###### set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
###### add_lefs -src $lefs

#### Run Synthesis using following command
###### run_synthesis

![Screenshot 2024-09-24 223434](https://github.com/user-attachments/assets/97a45a6e-d03b-4e2d-b566-c8a222e07a39)

![Screenshot 2024-09-25 115129](https://github.com/user-attachments/assets/28b69bb2-b8dd-42dd-9a39-43d572454f65)

![Screenshot 2024-09-24 223543](https://github.com/user-attachments/assets/0b7b7e2a-c115-49a3-b767-01fde91dddfb)

![Screenshot 2024-09-24 224636](https://github.com/user-attachments/assets/9ebc5f27-7901-4c90-ae7a-16bee9760591)

### 7. Remove/reduce the newly introduced violations with the introduction of custom inverter cell by modifying design parameters.

#### Noting down current design values generated before modifying parameters to improve timing

![Screenshot 2024-09-25 121451](https://github.com/user-attachments/assets/5da004f1-e7c4-45d1-b8b6-b30fa9c744a1)

![Screenshot 2024-09-25 122100](https://github.com/user-attachments/assets/731d59c9-ed98-4e10-8724-4aa596f016fa)

### Commands to view and change parameters to improve timing and run synthesis

#### prep design again to update variables
###### prep -design picorv32a -tag 22-09_06-18 -overwrite

#### Additional commands to include newly added lef to openlane flow merged.lef
###### set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
###### add_lefs -src $lefs

#### Command to display current value of SYNTH_STRATEGY
###### echo $::env(SYNTH_STRATEGY)

#### Command to set new value for SYNTH_STRATEGY
###### set ::env(SYNTH_STRATEGY) "DELAY 3"

#### Command to display current value of SYNTH_BUFFERING to check whether its enabled
###### echo $:: env(SYNTH_BUFFERING)

#### Command to display current value of SYNTH_SIZING
###### echo $::env(SYNTH_SIZING)

#### Command to set a new value to SYNTH_SIZING
###### set ::env(SYNTH_SIZING) 1

#### Command to display currennt value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
###### echo $::env(SYNTH_DRIVING_CELL)

#### Command to Run synthesis
###### run_synthesis

### Screenshot of merged.lef in tmp directory with our custom inverter as macro
![Screenshot 2024-09-25 131939](https://github.com/user-attachments/assets/bbab66e8-1540-4079-96c4-6070470ce4fb)

### Screenshot of Commands
![Screenshot 2024-09-25 130930](https://github.com/user-attachments/assets/518263c0-4f50-40e5-a1b4-c688e636d8c3)

![Screenshot 2024-09-25 131057](https://github.com/user-attachments/assets/ab1d1324-cf9d-43dc-933b-af4de7345a7d)

![Screenshot 2024-09-25 131127](https://github.com/user-attachments/assets/7b22d945-5b96-4b95-bf24-8ddd3b981852)

#### Comaparing the previous run values, area has increased and worst negative slock has become 0

### 8. Once synthesis has accepted our custom inverter we can now run floorplan and placement and verify the cell is accepted in PnR flow.

#### Now Custom inverter is properly accepted in synthesis, next step is to run Floorplan
###### run_floorplan

### Screenshot of run

![Screenshot 2024-09-25 132223](https://github.com/user-attachments/assets/dd181faf-d73c-4cbf-9d4c-b85774b8000e)

#### Since we are facing unexpected unexplainable error while using run_floorplan, we can instead use the following set of commands available based on information from floorplan.tcl and also based on floorplan commands section in OpenLANE_commands.md

#### Following commands are alltogether sourced in "run_floorplan" command
###### init_floorplan
###### place_io
###### tap_decap_or

### Screenshots of commands run
![Screenshot 2024-09-25 132418](https://github.com/user-attachments/assets/e53bfe6d-0a15-4ee4-8e25-d6b006ce6865)

![Screenshot 2024-09-25 132513](https://github.com/user-attachments/assets/fe49056e-a01c-4505-aea9-d1dd3eaa4f68)

### Now floorplan id done, run Placement

###### run_placement

### Screenshot of command
![Screenshot 2024-09-25 132606](https://github.com/user-attachments/assets/bfaaec18-02a6-4b89-ad40-d3a047173f99)

![Screenshot 2024-09-25 132803](https://github.com/user-attachments/assets/f598a562-da17-43bd-9e8f-c1df4b3b16e3)

### Command to load placement def in magic in another terminal

#### Open the directory that has generated placement def file
###### cd /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/22-09_06-18/results/placement/

#### Command to load the placement def into magic tool
###### magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

### Screenshot of Placement def in magic

![Screenshot 2024-09-25 133135](https://github.com/user-attachments/assets/586050a8-57ca-45c5-84e3-9475751a733b)

### Screenshot of Custom inverter inserted in placement def with proper abutment
![Screenshot 2024-09-25 133343](https://github.com/user-attachments/assets/205517c3-357f-4857-b199-5e3df4fe84e2)

#### Command for tkcon window to view internal layers of cells
##### expand
![Screenshot 2024-09-25 133431](https://github.com/user-attachments/assets/3bc7cbd5-633f-4876-8ad0-b7a21363b551)

#### Abutment of power pins with other cell from library clearly visible
![Screenshot 2024-09-25 133516](https://github.com/user-attachments/assets/10f21254-3839-480e-8ab9-e6c7a96037f9)

![Screenshot 2024-09-25 133658](https://github.com/user-attachments/assets/fbae2515-26cc-4fdc-8b0e-123039041153)

### 9. Do Post-Synthesis timing analysis with OpenSTA tool.

#### Since we are having 0 wns after improved timing run we are going to do timing analysis on initial run of synthesis which has lots of violations and no parameters were added to improve timing

### Command to invoke OpenLANE flow include new lef and perform synthesis

#### Open the openlane directory
###### cd /Desktop/work/tools/openlane_working_dir/openlane

#### Invoke the OpenLANE flow docker sub-system 
###### docker

#### Invoke the OpenLANE flow in the Interactive mode using the following command
###### ./flow.tcl -interactive

#### Feed the required packages for the proper functionality of the OpenLANE flow
###### package require openlane 0.9

#### prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
###### prep -design picorv32a

#### Additional commands to include newly added lef to openlane flow
###### set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
###### add_lefs -src $lefs

#### Command to set a new value to SYNTH_SIZING
###### set ::env(SYNTH_SIZING) 1

#### Run Synthesis using following command
###### run_synthesis

### Command run final screenshot 
![Screenshot 2024-09-25 124057](https://github.com/user-attachments/assets/15514250-839b-47f0-bf0b-85c24768303e)

### Newly created pre_sta.conf for STA analysis in openlane directory
![Screenshot 2024-09-25 234923](https://github.com/user-attachments/assets/d4cdc208-21ec-4aa5-bc1c-d946c5ada52d)

### Newly created my_base.sdc for STA analysis in openlane/designs/picorv32a/src directory based on the file openlane/scripts/base.sdc
![Screenshot 2024-09-25 234045](https://github.com/user-attachments/assets/8343bde8-e00c-4a6b-aa98-6823f6c33617)

### Commands to run STA in another terminal

#### Open the openlane directory
###### cd /Desktop/work/tools/openlane_working_dir/openlane

#### Invoke OpenSTA tool with script
#### sta pre_sta.conf

### Screenshot
![Screenshot 2024-09-24 224636](https://github.com/user-attachments/assets/64242b9d-fe83-4763-9ca4-54cbf88b40ff)

#### Since more fanout is causing more delay, to reduce fanout add parameters 

#### prep design again to update variables
###### prep -design picorv32a -tag 22-09_06-18 -overwrite

#### Additional commands to include newly added lef to openlane flow merged.lef
###### set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
###### add_lefs -src $lefs

#### Command to set a new value to SYNTH_SIZING
###### set ::env(SYNTH_SIZING) 1

#### Command to set a new value to SYNTH_MAX_FANOUT
###### set ::env(SYNTH_MAX_FANOUT) 4

#### Command to display currennt value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
###### echo $::env(SYNTH_DRIVING_CELL)

#### Command to Run synthesis
###### run_synthesis

### Screenshot
![Screenshot 2024-09-26 001840](https://github.com/user-attachments/assets/14098429-defa-4fc8-a703-fcdf4148197f)

#### Open the openlane directory
###### cd /Desktop/work/tools/openlane_working_dir/openlane

#### Invoke OpenSTA tool with script
#### sta pre_sta.conf

### Screenshot
![Screenshot 2024-09-26 002052](https://github.com/user-attachments/assets/1149d5f4-470d-49e4-b383-203112e61fce)

![Screenshot 2024-09-26 002124](https://github.com/user-attachments/assets/b221489f-d68f-4c92-99d3-c127eb6efb40)

![Screenshot 2024-09-26 001956](https://github.com/user-attachments/assets/77fa0d05-b7f5-4568-aaa3-e03ea110edcc)

### 10. Make timing ECO fixes to remove all violations.

#### OR gate of drive strength 2 is driving 4 fanouts
![Screenshot 2024-09-26 004640](https://github.com/user-attachments/assets/7c6c72f6-2beb-4ce7-8ae4-efe5063958ab)

### Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4

#### Reports all the connections to a net
###### report_net -connections _11672_

#### Replace cell
###### replace_cell _14510_ sky130_fd_sc_hd__or3_4

#### Generate custom timing report
###### report_checks -fields {net cap slew input_pins} -digits 4

### Result-slack reduction

### Screenshot
![Screenshot 2024-09-26 004856](https://github.com/user-attachments/assets/1530c37f-d1e5-459e-9052-9ef750aa5d3c)

![Screenshot 2024-09-26 004953](https://github.com/user-attachments/assets/742468d2-bf4c-4024-84d8-de9c0b61285e)

![Screenshot 2024-09-26 005116](https://github.com/user-attachments/assets/0549b51a-5e12-4a55-b7e2-35c547497203)

![Screenshot 2024-09-26 005153](https://github.com/user-attachments/assets/b4eedfb2-f38f-4ab5-9e8d-c084fa824f28)

### OR Gate drive strength 2 is driving 4 fanouts
### Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4

#### Reports all the connections to a net
###### report_net -connections _11675_

#### Replace cell
###### replace_cell _14514_ sky130_fd_sc_hd__or3_4

#### Generate custom timing report
###### report_checks -fields {net cap slew input_pins} -digits 4

### Result-slack reduction
![Screenshot 2024-09-26 005610](https://github.com/user-attachments/assets/6653354e-35de-420c-a021-81a87e59bfba)

![Screenshot 2024-09-26 005728](https://github.com/user-attachments/assets/fd26c5b1-1365-4518-a267-89dcc3ba746d)

![Screenshot 2024-09-26 005750](https://github.com/user-attachments/assets/a4df6ec2-d703-4999-b61d-f5a46d20382a)

### OR Gate drive strength 2 is driving OR gate has more delay

### Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4

#### Reports all the connections to a net
###### report_net -connections _11643_

#### Replace cell
###### replace_cell _14481_ sky130_fd_sc_hd__or4_4

#### Generate custom timing report
###### report_checks -fields {net cap slew input_pins} -digits 4

![Screenshot 2024-09-26 010410](https://github.com/user-attachments/assets/9054da52-03c9-41de-8f63-32ee5fe03a1d)

![Screenshot 2024-09-26 010858](https://github.com/user-attachments/assets/afa2a6ca-b18d-444a-b5cb-b325b6240b01)

### OR Gate drive strength 2 is driving OR gate has more delay
![Screenshot 2024-09-26 011307](https://github.com/user-attachments/assets/bed9afb0-366f-4517-9566-a90cfa84dedd)

### Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4

#### Reports all the connections to a net
###### report_net -connections _11668_

#### Replace cell
###### replace_cell _14506_ sky130_fd_sc_hd__or4_4

#### Generate custom timing report
###### report_checks -fields {net cap slew input_pins} -digits 4
![Screenshot 2024-09-26 011607](https://github.com/user-attachments/assets/3caec1c9-426e-4b23-bfb0-4b33225f84ca)

![Screenshot 2024-09-26 011541](https://github.com/user-attachments/assets/334507b5-9648-4996-86b8-482a0a9e3e41)

#### Commands to verify instance _14506_ is replaced with sky130_fd_sc_hd__or4_4

#### Generating custom timing report
###### report_checks -from _29043_ -to _30440_ -through _14506_

### Screenshot
![Screenshot 2024-09-26 011840](https://github.com/user-attachments/assets/161fdf16-c8e5-4379-9e74-2f83e1a806f7)

### Reduced violations from -23.9000 to -22.6173

### 11. Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.

#### Now to insert this updated netlist tp PnR flow, we use write_verilog and overwrite the synthesis netlist.

### Commands

#### check syntax
###### help write_verilog

#### Overwriting current sythesis netlist
###### write_verilog /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/22-09_06-18/results/synthesis/picorv32a.synthesis.v

#### Exit from OpenSTA 
###### exit

![Screenshot 2024-09-26 215305](https://github.com/user-attachments/assets/1ff07ebe-f014-4c95-9ff5-f85f76e9d3fc)

#### Verified that the netlist is overwritten by checking that instance _14506_ is replaced with sky130_fd_sc_hd__or4_4
![Screenshot 2024-09-26 215542](https://github.com/user-attachments/assets/9c59e0c6-0e07-498d-913c-6ecd29a26373)

#### Since we confirmed that netlist is replaced and will be loaded in PnR but since we want to follow up on the earlier 0 violation design we are continuing with the clean design to further stages

### Command :
#### prep design again to update variables
###### prep -design picorv32a -tag 22-09_06-18 -overwrite

#### Additional commands to include newly added lef to openlane flow merged.lef
###### set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
###### add_lefs -src $lefs

#### Command to set new value for SYNTH_STRATEGY
###### set ::env(SYNTH_STRATEGY) "DELAY 3"

#### Command to set a new value to SYNTH_SIZING
###### set ::env(SYNTH_SIZING) 1

#### Command to Run synthesis
###### run_synthesis

#### Following commands are alltogether sourced in "run_floorplan" command
###### init_floorplan
###### place_io
###### tap_decap_or

#### Now floorplan id done, run Placement
###### run_placement

#### Run CTS
###### run_cts

### Screenshots
![Screenshot 2024-09-26 220049](https://github.com/user-attachments/assets/b8e8f9ca-7c42-4996-93c7-f72b50ad716b)

![Screenshot 2024-09-26 220446](https://github.com/user-attachments/assets/f74a14c0-1970-42e3-a740-18568b461f10)

![Screenshot 2024-09-26 220453](https://github.com/user-attachments/assets/0789b4e5-fe9d-438d-86ad-51901b1b4fbe)

![Screenshot 2024-09-26 220529](https://github.com/user-attachments/assets/3f028972-9921-4bce-a6a9-e9dae9a15eb7)

![Screenshot 2024-09-26 220623](https://github.com/user-attachments/assets/55363e29-f5bf-4f0f-b478-24a84072d3a1)

![Screenshot 2024-09-26 220713](https://github.com/user-attachments/assets/89e29738-c022-4dd9-927e-996e0beeca59)

![Screenshot 2024-09-26 220752](https://github.com/user-attachments/assets/02c094a3-72f0-416c-bf55-9a45ce8e226f)

![Screenshot 2024-09-26 220852](https://github.com/user-attachments/assets/ca5c5318-34d6-4375-9536-c1585b2f7d70)

![Screenshot 2024-09-26 221114](https://github.com/user-attachments/assets/2a94960f-3183-4a66-9c17-17c6e2894a25)

![Screenshot 2024-09-26 221328](https://github.com/user-attachments/assets/5938acec-40c8-4a8e-9766-b1c6c433e488)

### 12. Post-CTS OpenROAD timing analysis.
#### Commands to run in openlane flow to OpenROAD timing analysis with integrated OpenSTA in OpenROAD

#### Command to run OpenROAD tool
###### openroad

#### Reading lef file
###### read_lef /openLANE_flow/designs/picorv32a/runs/22-09_06-18/tmp/merged.lef

#### Reading def file
###### read_def /openLANE_flow/designs/picorv32a/runs/22-09_06-18/results/cts/picorv32a.cts.def

#### Creating an openroad daatabase
###### write_db pico_cts.db

#### Loading the created database in OpenROAD
###### read_db pico_cts.db

#### Read netlist post CTS
###### read_verilog /openLANE_flow/designs/picorv32a/runs/22-09_06-18/results/synthesis/picorv32s.synthesis_cts.v

#### Read library for design
###### read_liberty $::env(LIB_SYNTH_COMPLETE)

#### Link design and library
###### link_design picorv32a

#### Read in the custom sdc we created
###### read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

#### setting all clocks as propagated clocks
###### set_propagated_clock [all_clock]

#### Generating custom timing report
###### report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

#### Exit to OpenLANE flow
###### exit

### Screenshots
![Screenshot 2024-09-26 235351](https://github.com/user-attachments/assets/ab860e4f-90aa-4a83-a070-f831833cb212)

![Screenshot 2024-09-26 235434](https://github.com/user-attachments/assets/9114714f-a56c-42db-8be4-46932f49dcf8)

![Screenshot 2024-09-26 235453](https://github.com/user-attachments/assets/b685ed84-e6d6-49ba-923a-5fbcbb87da73)

![Screenshot 2024-09-26 235508](https://github.com/user-attachments/assets/a480c4bf-42fc-42b5-ad13-9a744d800db8)

### 13. Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.

#### Commands to be run in OpenLANE flow to do OpenROAD timing analysis after changing CTS_CLK_BUFFER_LIST

#### Checking current value of 'CTS_CLK_BUFFER_LIST'
###### echo $::env(CTS_CLK_BUFFER_LIST)

#### Removing 'sky130_fd_sc_hd__clkbuf_1' from the list
###### set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0

#### Checking current value of 'CTS_CLK_BUFFER_LIST'
###### echo $::env(CTS_CLK_BUFFER_LIST)

#### Checking current value 'CURRENT_DEF'
###### echo $::env(CURRENT_DEF)

#### setting def as placement def
###### set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/22-09_06-18/results/placement/picorv32a.placement.def

#### Run CTS again
###### run_cts

#### Checking current value of 'CTS_CLK_BUFFER_LIST'
###### echo $::env(CTS_CLK_BUFFER_LIST)

#### Command to run OpenROAD tool
###### openroad

#### Reading lef file
###### read_lef /openLANE_flow/designs/picorv32a/runs/22-09_06-18/tmp/merged.lef

#### Reading def file
###### read_def /openLANE_flow/designs/picorv32a/runs/22-09_06-18/results/cts/picorv32a.cts.def

#### Creating an openroad daatabase
###### write_db pico_cts.db

#### Loading the created database in OpenROAD
###### read_db pico_cts.db

#### Read netlist post CTS
###### read_verilog /openLANE_flow/designs/picorv32a/runs/22-09_06-18/results/synthesis/picorv32s.synthesis_cts.v

#### Read library for design
###### read_liberty $::env(LIB_SYNTH_COMPLETE)

#### Link design and library
###### link_design picorv32a

#### Read in the custom sdc we created
###### read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

#### setting all clocks as propagated clocks
###### set_propagated_clock [all_clock]

#### Generating custom timing report
###### report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

#### Report hold skew
###### report_clock_skew -hold

#### Report setup skew
###### report_clock_skew -setup

#### Checking current value of 'CTS_CLK_BUFFER_LIST'
###### echo $::env(CTS_CLK_BUFFER_LIST)

#### Removing 'sky130_fd_sc_hd__clkbuf_1' from the list
###### set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]

#### Checking current value of 'CTS_CLK_BUFFER_LIST'
###### echo $::env(CTS_CLK_BUFFER_LIST)

### Screenshots
![Screenshot 2024-09-27 002924](https://github.com/user-attachments/assets/9ecc8927-a8f6-4800-b5e8-3a4332ac5f60)

![Screenshot 2024-09-27 005116](https://github.com/user-attachments/assets/7583f1b2-82ef-4526-ac2e-ff8fcff828b0)

![Screenshot 2024-09-27 005136](https://github.com/user-attachments/assets/633bcab0-2bdc-4d90-a839-4bd919f04a24)

![Screenshot 2024-09-27 005156](https://github.com/user-attachments/assets/d0c0539c-e804-43f2-a388-4bbe35d5ff81)

![Screenshot 2024-09-27 005213](https://github.com/user-attachments/assets/937bd1f4-ea00-4811-a390-30d49c860483)

![Screenshot 2024-09-27 005325](https://github.com/user-attachments/assets/a8e00629-2420-4adc-bb8f-97bc165804dd)

![Screenshot 2024-09-27 005643](https://github.com/user-attachments/assets/b00cec88-340e-4ada-9adf-cb3d6c7fe938)

