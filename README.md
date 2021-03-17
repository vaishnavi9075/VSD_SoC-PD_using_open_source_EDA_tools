# VSD_SoC-PD_using_open_source_EDA_tools
This repository is to give brief idea about the VSD's 'Beginner Soc/Physical Design using open source EDA tools' Workshop. The workshop has given me a hands on experience with the EDA tools used in Physical Design.

* Here are some sources used in this workshop:

1.YOSYS : Synthesis.

2.Graywolf :Placement.

3.Qrouter : Routing.

4.Qflow : RTL2GDS integration.

5.MAGIC : VLSI Layout tool.

6.Netgen : LVS.

7.OpenSTA & Opentimer : Prelayout & postlayout Static Timing Analysis.




## DAY1 : Study of components of RISC-V based picoSoC


* Theory :
1. Introduction to QFN-48 packages, Chips, Pads, Core, Die & IP's.
2. Introduction to RISC-V, PiCoRV32 & PicoSoc.
3. RavenSoC & Raven full chip Design overview.
4. Introduction to IC design component & Open Source EDA Tools.
5. Test open source EDA tools using sample design (spi-slave) & VSD flow.


![D1_SK1_1](https://user-images.githubusercontent.com/80053265/110242838-d10f1c00-7f7d-11eb-866f-f64b1e3c6cfa.PNG)
![D1_SK1_2](https://user-images.githubusercontent.com/80053265/110243062-cef98d00-7f7e-11eb-8072-c78c160c459c.PNG)
![D1_SK2_1](https://user-images.githubusercontent.com/80053265/110243082-e3d62080-7f7e-11eb-8f53-471fcfac86e7.PNG)



## Labs1


  -> type a command “yosys” to open ‘yosys open synthesis tool’.
  
![d1_l1](https://user-images.githubusercontent.com/80053265/110243135-1e3fbd80-7f7f-11eb-989e-796940441018.PNG)


  -> Type "which sta" to see the ‘sta tool’s’ directory.
  
  -> git clone https://github.com/kunalg123/vsdflow.git.
  
  -> command to clone the vsdflow.
  
![lab2 (2)](https://user-images.githubusercontent.com/80053265/110243265-a3c36d80-7f7f-11eb-941b-a1b8a84391b0.PNG)


  -> cd vsdflow
  
  -> ./vsdflow spi_slave_design_details.csv
  
  -> ls -ltr outdir_spi_slave/
  
  -> ls -ltr outdir_spi_slave | wc
   and here can see the total created files
   
![lab4](https://user-images.githubusercontent.com/80053265/110243311-c3f32c80-7f7f-11eb-8fe5-3a1b8bccc012.PNG)


  -> cd outdir_spi_slave
  
  -> qflow display spi_slave
  
   It will open 2 windows "layout1" and "tkcon" On "tkcon" window, type "box". And we can see dimensions of the box we selected.
   
![d1_l2](https://user-images.githubusercontent.com/80053265/110247391-189fa300-7f92-11eb-82d1-4af1e0d33c03.PNG)


  -> cd
  
  -> cd vsdflow
  
  -> mkdir my_picorv32
  
  -> cd my_picorv32
  
  -> mkdir source synthesis layout
  
  -> cp ~/vsdflow/verilog/picorv32.v source/.
  
  -> qflow gui &
  
   it will open qflow for synthesis and the settings below makes our picoRV32 module to be synthesized.
  -> Technology = osu018
  -> Verilog source file : picorv32.v
  -> Verilog module : picorv32
  
![lab5](https://user-images.githubusercontent.com/80053265/110243316-c8b7e080-7f7f-11eb-9f5e-5a4e4cc1504a.PNG)
![lab6](https://user-images.githubusercontent.com/80053265/110247942-a9777e00-7f94-11eb-9ca3-3db223af1a69.PNG)







## DAY2 : Chip planning and introduction to foundry library cells.



* Theory :
1. Concepts of Utilization Factor & Aspect Ratio. 
2. Concept of Preplaced Cells, Decoupling Capacitors, AND Power Planning.
3. Pin placement & logical cell placement blockage.
4. Netlist Binding & initial place design.
5. Placement Optimization using estimated wire-length & capacitance.
6. Need for libraries And Logic Design Flow.
7. Cell Design Flow.
8. Circuit Design.
9. Layout Design And Characterization Flow. 
10. Timing Chracterization and Propagation Delay.


![D2SK3_1](https://user-images.githubusercontent.com/80053265/110245026-8eead800-7f87-11eb-915b-ffa707ba1e8f.PNG)
![D2SS8](https://user-images.githubusercontent.com/80053265/110245028-97dba980-7f87-11eb-8d10-a7167610f473.PNG)



## Labs2
  
  -> cd vsdflow/my_picorv32
  
  -> qflow display picorv32 &
  
   This will open layout and tkcon window In the layout window, select whole chip using below steps Take cursor to bottom left. Left mouse click. Take cursor to top right. Right mouse click. Press Shift+i. This will select the whole layout Now in tkcon window, type below command
   
  -> box.  And we can see dimensions of the box we selected.
![d1_l2](https://user-images.githubusercontent.com/80053265/110247391-189fa300-7f92-11eb-82d1-4af1e0d33c03.PNG)


   Here are the outputs shown when we go further for synthesis and placement process.
   
![D2_L1](https://user-images.githubusercontent.com/80053265/110245052-b772d200-7f87-11eb-87f4-df8e554d187b.PNG)
![D2_L3](https://user-images.githubusercontent.com/80053265/110245062-bb9eef80-7f87-11eb-8a76-b3e5c2470e1a.PNG)
![D2_L6](https://user-images.githubusercontent.com/80053265/110245069-c8bbde80-7f87-11eb-8200-101bce51a8a1.PNG)





## DAY3 : SPICE Simulation and CMOS fabrication Process.



* Theory :
1. SPICE Deck creation for CMOS inverter.
2. SPICE Simulation for CMOS inverter.
3. Static & Dyanmic Simulation of CMOS.
4. Layout using Euler's Path and Stick Diagram.
5. Script to create layout in MAGIC.
6. Final layout & input/output labelling.
7.  Post layout ngspice.
8. 16-MASK CMOS Process.


![D3_SK3_1](https://user-images.githubusercontent.com/80053265/110245208-3ec04580-7f88-11eb-8290-0337573e104e.PNG)
![D3_SK3_2](https://user-images.githubusercontent.com/80053265/110245214-4253cc80-7f88-11eb-955e-b221645c22aa.PNG)
![D3_SK4_1](https://user-images.githubusercontent.com/80053265/110245223-467fea00-7f88-11eb-84e8-c48362d8bb21.PNG)



## Labs3


  -> cd
  
  -> git clone https://github.com/kunalg123/ngspice_labs.git
  
   This command will clone ngspice labs
   
  -> cd ngspice_labs
  
  -> cat inv.spice
  
   it gives us model description
   
![D3_L1](https://user-images.githubusercontent.com/80053265/110245384-d6be2f00-7f88-11eb-9c8c-a4e5d9365a21.PNG)

 
  -> cd ngspice_labs
  
  -> ngspice inv.spice
  
   There will be terminal like. ngspice 1 ->. On the ngspice terminal, type below commands
   
  -> run
  
  -> setplot dc1
  
  -> plot out in
  
   This will open a plot with CMOS VTC and Blue 45 degree line. Click on the intersection of Blue line and CMOS VTC. And we get the ‘Switching Threshold- Vm’.
   
![d3_l3](https://user-images.githubusercontent.com/80053265/110245387-da51b600-7f88-11eb-8142-a48f4da54a17.PNG)


   Type below commands for transient simulations
   
  -> ngspice inv_tran.spice
  
  -> ngspice 1 -> run
  
  -> ngspice 1 -> setplot tran1
  
  -> ngspice 1 -> plot out in
  
![d3_l4](https://user-images.githubusercontent.com/80053265/110245389-dde53d00-7f88-11eb-9d63-7888b3dbb4a7.PNG)


   Open file called "inv_tran.spice" using below command
   
  -> leafpad inv_tran.spice
  
   Change PMOS width to 0.75u, Save and Close and doing the same process as above will give us transient simulations and find the difference
   
![d3_l5](https://user-images.githubusercontent.com/80053265/110245403-f0f80d00-7f88-11eb-8728-3c60d3f17b5b.PNG)


  -> cd
  
  -> cd ngspice_labs
  
  -> magic -T min2.tech
  
   This will open magic layout window and tkcon window. Go to tkcon window and type below command
   
  -> source draw_fn.tcl
 
![d3_l6](https://user-images.githubusercontent.com/80053265/110245407-f7868480-7f88-11eb-9ddb-6f402cfc152d.PNG)


  -> cd
  
  -> cd ngspice_labs
  
  -> magic -T min2.tech fn_postlayout.mag &
  
  These command will create post layout in Magic.
  
![d3_l7](https://user-images.githubusercontent.com/80053265/110245411-fbb2a200-7f88-11eb-9b1e-b0ece2120b88.PNG)
![d3_l8](https://user-images.githubusercontent.com/80053265/110245412-ffdebf80-7f88-11eb-9a4c-79464f5d8104.PNG)
![d3_l9](https://user-images.githubusercontent.com/80053265/110245415-040add00-7f89-11eb-827d-6e3eaf2676f3.PNG)






## DAY4 : Timing Analysis and Clock Tree Synthesis


* Theory :
1. Introduction to Delay Tables.
2. SETUP Timing Analysis.
3. Introduction to clock jitter & uncertainty.
4. Clock Tree Routing & Buffering using H-tree Algorithm.
5. Clock net shielding.
6. HOLD Timing Analysis using real clocks.


![D4_SK3_2](https://user-images.githubusercontent.com/80053265/110245652-23eed080-7f8a-11eb-80bc-fedb9d8da1a7.PNG)
![D4_SK3_3](https://user-images.githubusercontent.com/80053265/110245653-26e9c100-7f8a-11eb-839e-face47761f99.PNG)



## Labs4


  -> cd
  
  -> git clone https://github.com/kunalg123/ngspice_labs
  
  -> cd ngspice_labs
  
  -> cat inv_tran.spice
  
   here we will compute rise and fall delay.
   
  -> ngspice inv_tran.spice
  
   output delay and rise delay has been computed here.
   
![d4_l1](https://user-images.githubusercontent.com/80053265/110245707-62848b00-7f8a-11eb-9b18-1161f0a4683d.PNG)
![d4_sk1_l1](https://user-images.githubusercontent.com/80053265/110245722-729c6a80-7f8a-11eb-8d4f-a9345e7a8d52.PNG)


  -> /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib
  
   The files in the given directory has been opened by “vim/leafpad/less” commands
   
![d4_l3](https://user-images.githubusercontent.com/80053265/110245743-7f20c300-7f8a-11eb-983b-f66d5c5b2a67.PNG)
![d4_l6](https://user-images.githubusercontent.com/80053265/110245765-98297400-7f8a-11eb-998e-b9b2a8bf5a57.PNG)
![d4_l7](https://user-images.githubusercontent.com/80053265/110245770-9b246480-7f8a-11eb-9caa-c9a4dea0aa9d.PNG)
![d4_l8](https://user-images.githubusercontent.com/80053265/110245772-9eb7eb80-7f8a-11eb-9e6b-715b089960bd.PNG)
![d4_l9](https://user-images.githubusercontent.com/80053265/110245774-a1b2dc00-7f8a-11eb-952f-536e719cdc25.PNG)





## DAY5 : RTL2GDS Tutorial.


* Theory :
1. Introduction to MAZE Routing- lee's algorithm.
2. DRCs (Design Rule Check).
3. Introduction to IEEE 1481- 1999 SPEF Format.
4. SPEF file for NET.
5. Few tips on pin placement & floorplanning.
6. Placement & Pre-layout STA.
7. Routing & Post-layout STA.


![D5_SK1](https://user-images.githubusercontent.com/80053265/110245809-c9a23f80-7f8a-11eb-8ef0-4b0dd8497d53.PNG)
![D5_SK1_2](https://user-images.githubusercontent.com/80053265/110245814-cd35c680-7f8a-11eb-8bb1-1ef1c339ae0a.PNG)



## Labs5


  -> cd
  
  -> cd vsdflow/my_picorv32
  
  -> qflow route picorv32
  
![d5_l1](https://user-images.githubusercontent.com/80053265/110245817-d030b700-7f8a-11eb-9bd1-35b52569d33f.PNG)


  -> qflow sta picorv32
  
  -> qflow backanno picorv32
  
  -> leafpad log/sta.log
  
![d5_l3](https://user-images.githubusercontent.com/80053265/110245823-d757c500-7f8a-11eb-890f-3754f1d2c88d.PNG)


  -> log/post_sta.log
  
![d5_l4](https://user-images.githubusercontent.com/80053265/110245828-d9ba1f00-7f8a-11eb-819a-ff61be7c12a4.PNG)




##### Acknowledgements:
  * Kunal Ghosh, Co-founder(VSD Corp. Pvt.Ltd)
