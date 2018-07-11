# Automatic-Hot-Drinks
# Control of industrial process using PROSIM –process simulator
## What is PROSIM?
PROSIM is an industrial process simulator for technical training.

![PLC](/images/PLC.jpg)

## Functional description:

After inserting a coin (button S5 is active), first a beverage, and then the ingredients are selected using the S1, S2, S3 and S4 buttons. Selections are signaled by lamps: P1, P2, P3 and P4. The filling process is complete when sensor B1 is activated. At this point the selection disappears from the automatic panel. The glass is symbolically removed by activating the S0 button and a new command can be retrieved.

![ProcessMask](/images/mask.png)

## How i built the project:

* I open the Totally Integrated Automation program and select the Create New Project option. In the new fields I write the name of the project and the author, and a brief description of the project. In the Path section, select the file where the project is saved. Then select Create.
* Configure the project components, the PLC and the analog and digital input / output blocks: From the new window, select the Configure a device -> Add new device option. I select CPU unit 1214C, 6ES7 214-1AE30-0XB0 -> Add.
From the window on the right I select Hardware catalog and add the digital and analog input / output modules: first select DI / DO -> DI8 / DO8 x 24VDC -. 6ES7 223-1BH30-0XB0 and add to the project; for example, I select an analogue input / output module, AI / AO -> AI4 x 14 bits -> 6ES7 234-4HE30-0XB0.
I select the PLC and from the configuration window select Properties -> General -> Project Information -> Name and enter: AP S7-1214C.
Selecting PROFINET Interface -> Ethernet address -> Add new subnet. At IP addresses enter 192.168.0.10, and at Subnet mask 255.255.255.0. From General -> System and clock memory set to Enable the use of system memory byte and Enable the use of clock memory byte.
To configure the DI / DO module, select the module, specify the author, and then from General -> DI8 / DO8 -> IO addresses / HW identifier specify the start address for the input and output signals: Input addresses -> Start address -> 2, Output addresses -> Start addresses -> 2. Analogue is done for the AI ​​/ AO module, with the difference that the start address is 3.
Project-> Save.

* We further write the program using the ladder diagrams (vertical lines represent the power source and the horizontal control lines). We go into Project tree and select the name of the PLC configured. From the Bit logic section, we use the necessary instructions to make the process description functional. The drafting of the project is done through Networks.
