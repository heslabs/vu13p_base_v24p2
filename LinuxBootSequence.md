
---
### Linux Booting Sequence

* Xilinx Zynq MP First Stage Boot Loader .....
  * Release 2022.2  
* U-Boot 2022.01 .....
  * CPU: ZynqMP | Board: Xilinx ZynqMP | DRAM: 2- GiB
  * PMUFW: v1.1 | EL Level: EL2 | Chip ID: zu4
  * MMC: mmc@ff160000:0, mmc@ff170000:1
* Found U-Boot script /boot.scr
  * Trying to load boot imagess from mmc1
  * Load kernel from FIT Image at 10000000 ....
  * Loading Device Tree to 0000007bbee000, end 000000007bbfab31 ... OK
* Starting Kernel .....
  * Booting Linux on physical CPU 0x0000000000 [0x410fd034]
  * Linux version 5.15.36-xilinx-v2022.2 (aarch64-xilinx-linux-gcc (GCC) 1.2.0
  * Machine model: xlnx, zynqmp
  * earlycon: cdns0 at MMIO 0x00000000ff000000 (options '115200n81)
  * printk: bootconsole [cdns0] enabled
* Welcome to PynqLinux, based pn Ubuntu 22.04
  * PYNQ Linux, based pn Ubuntu 22.04 pynq ttyPS0
  * pynq login: xilinx | Password: xilinx


---

```
xilinx@pynq:~/haps$ uname -a
Linux pynq 5.15.36-xilinx-v2022.2 #1 SMP Mon Oct 3 07:50:07 UTC 2022 aarch64 aarch64 aarch64 GNU/Linux
xilinx@pynq:~/haps$ lsmem
RANGE                                 SIZE  STATE REMOVABLE   BLOCK
0x0000000000000000-0x000000007fffffff   2G online        no    0-15
0x0000000800000000-0x000000087fffffff   2G online        no 256-271
0x0000001000000000-0x00000013ffffffff  16G online        no 512-639

Memory block size:       128M
Total online memory:      20G
Total offline memory:      0B
```

```
xilinx@pynq:~/haps$ cpuinfo
Python Version: 3.10.4.final.0 (64 bit)
Cpuinfo Version: 9.0.0
Vendor ID Raw: ARM
Hardware Raw: 
Brand Raw: Cortex-A53
Hz Advertised Friendly: 1.2000 GHz
Hz Actual Friendly: 1.2000 GHz
Hz Advertised: (1200000000, 0)
Hz Actual: (1200000000, 0)
Arch: ARM_8
Bits: 64
Count: 4
Arch String Raw: aarch64
L1 Data Cache Size: 
L1 Instruction Cache Size: 
L2 Cache Size: 
L2 Cache Line Size: 
L2 Cache Associativity: 
L3 Cache Size: 
Stepping: 
Model: 4
Family: 
Processor Type: 
Flags: aes, asimd, cpuid, crc32, fp, pmull, sha1, sha2
```




---
### Linux Booting Sequence

<img src="https://github.com/user-attachments/assets/c76460cd-42cf-4f14-992e-79d86fff2f95" width=850>

<img src="https://github.com/user-attachments/assets/69b9ae66-a137-4cc2-a8f2-631b6c87a10c" width=850>

<img src="https://github.com/user-attachments/assets/3b8430a0-c8a6-4e2b-97e8-6cf18ebceda4" width=850>

<img src="https://github.com/user-attachments/assets/c216c711-6ae6-420d-9743-da68f540104f" width=850>

 
