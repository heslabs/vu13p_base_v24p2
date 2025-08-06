# HAPS VU13P Quick Start Guide

### FPGA Prototyping Platform - Lab setup 

<img src="https://github.com/user-attachments/assets/713f953a-b265-42f8-8df8-45b70c512401" width=850>
 
---
### Hardware configuration 

| Device | IP Address | Description | Smart WiFi Plug |
|:-|:-|:-|:-|
| HAPS-VU13P | 192.168.50.13 | HAPS VU13P | N/A |
| HAPS-ZYNQ | 192.168.50.14 | HAPS SMF ZynqMPSoC/CA53 module | 192.168.50.95 |
| HAPS-PC | 192.168.50.5 | Linux PC | N/A |

---
### ESP-VU13P

| Product Name | EPS-VU13P | Serial Number | EC231115 |
|:-|:-|:-|:-|
| MAC Adderess | 00:0a:35:10:0e:b9 | IP Adderess | 192.168.50.13 |
| Firmware Version | FW-1.0.0 | Hardware Version | FW-1.0.3 |

---
### Remote access to HAPS and ZYNQ module

#### Step-1: Configure and program FPGA

* Launch FPGA tool "Confpro-SX" in Linux shell
* Openthe Confpro project file (PASS.bmprj) with the FPGA bitstream (PASS.bit)
* Select the HAPS system in the scanned list
* Configure the system and wait few seconds
* Check the successful message.  ```Operation successful!```

```
./E-CoreFlow-Gui-Run.sh &
```

#### Step-2: Connect HAPS-PC from remote

* Connect HAPS-ZYNQ via Ethernet

```
<Remote> $ sshpass -p <password> ssh vu13p@59.124.169.195 -X
```

#### Step-3: Connect HAPS-ZYNQ via serial console from HAPS-PC  

* Monitoring the HAPS-ZYNQ Boot Process
* Connect a serial cable to the HAPS-ZYNQ and HAPS-PC. Use a terminal program like PuTTY to establish a connection.
* The boot messages will be displayed in the console, including the IP address assignment
  
```
$ ls /dev/ttyUB*
$ sudo chmod 666 /dev/ttyUSB0
$ putty -serial -sercfg 115200,8,n,1,N /dev/ttyUSB0 -fn "client:Ubuntu Mono 16" &
```

* Enter username and password (xilinx:xilinx)
  
```
login: xilinx
password: xilinx
```

* Note
   * A serial console typically does not display graphics; it's a text-based interface designed for basic system diagnostics and troubleshooting, especially when graphical output is unavailable or the operating system is in a non-bootable state.



#### Step-4: Connect HAPS-ZYNQ via Ethernet from HAPS-PC  

* To connect HAPS-ZYNQ from HAPS-PC via ssh:  

```
<HAPS-PC> $ sshpass -p xilinx ssh xilinx@192.169.50.14 -X
```

#### Step-5:

* Check the 16GB DDR og HAPS system is in the Linux memory map

```
xilinx@pynq:~/haps$ lsmem
RANGE                                 SIZE  STATE REMOVABLE   BLOCK
0x0000000000000000-0x000000007fffffff   2G online        no    0-15
0x0000000800000000-0x000000087fffffff   2G online        no 256-271
0x0000001000000000-0x00000013ffffffff  16G online        no 512-639

Memory block size:       128M
Total online memory:      20G
Total offline memory:      0B
```
