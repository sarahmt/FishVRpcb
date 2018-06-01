This directory contains files for editing the FishVR PCB’s in KiCad 4.0.6

Contact contributors: 

Sarah Thompson, smt2175@columbia.edu
- working on FishVR Spring 2018



For more FishVR files and info: 
https://drive.google.com/open?id=1Ii8UJhQ7dzW9s3ATLErmy2Fkt1ruH-P6



HEAT SEAL BOARD
_______________________

The heat seal board is designed to be connected to the mux board via header pins. This allows heat seal boards to be reused and fatigued separately from the mux board. The heat seal footprint was designed to match the electrode array pattern saved in this drive under FishVR/96-channel_array_Draftsight. The pitch of the interconnect pads in the footprint is 1mm. 

_______________________

MUX BOARD
_______________________

This board accommodates 11 inputs and 99 outputs. 

Inputs:

8 inputs should come from a microcontroller used to address the electrode array (see LabVIEW+Arduino Code). 

The remaining 3 inputs are V+, GND, and Vsig. V+ has been successfully tested at 5V, but datasheets for the mux IC’s in this design are contained under FishVR/Electronics_Documentation. Vsig should be connected to the current source, or whichever signal is reserved for the selected electrode. 

Outputs:

96 electrodes are accessed by these 8 inputs. The remaining 3 ouputs access electrodes 97-99 in case it becomes useful to bias these manually. 

Overall Function:

Only one electrode may be selected at a time. 4 inputs from the microncontroller are used to select 1 of 6 electrode sectors, and the other 4 inputs from the microcontroller are used to select 1/16 electrodes within the sector. All 6 muxes controlling all 6 sectors receive identical address bits, but Vsig is only routed to one mux; therefore, the unselected sector muxes output GND on all channels. A truth table is included under FishVR/Electronics_Documentation, along with a block diagram. A full schematic is contained with all the PCB files. 
