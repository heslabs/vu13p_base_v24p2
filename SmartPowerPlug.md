---
### Smart power Plug

* The smart WiFi plug is used to reset HAPS-ZYNQ after HAPS-FPGA programmed
   * Tapo P105 | Mini Smart Wi-Fi Plug [[Tapo]](https://www.tapo.com/en/product/smart-plug/tapo-p105/)
   * Tapo API Client for TP-Link Tapo smart devices: [[Github]](https://github.com/mihai-dinculescu/tapo)
     
<img src="https://github.com/user-attachments/assets/8188a214-84a8-4690-a463-b4a203c61510" width=120>
<img src="https://github.com/user-attachments/assets/f86ed397-0a8d-4069-b3f5-4957a68ec6c8" width=120>


---
### Setup Python Environment

```
python3 -m venv venv
source venv/bin/activate
pip install aiohttp requests tapo
pip install numpy matplotlib scipy pyqt5
## Test Python installation
python ./zynq/scipy-pylab.py
```

---
### Control Python scripts

```
source ./venv/bin/activate
python ./scrtips/zynq-reset.py
```

```
## zynq-reset.py
## tp-link P100 and P105 Example

import asyncio
import os

from tapo import ApiClient

async def main():
tapo_username = os.getenv("TAPO_USERNAME")
tapo_password = os.getenv("TAPO_PASSWORD")
#ip_address = "192.168.1.8"
ip_address = os.getenv("TAPO_IPADD_VU13P")

client = ApiClient(tapo_username, tapo_password)
device = await client.p100(ip_address)

print("Turning device off...")
await device.off()

print("Waiting 2 seconds...")
await asyncio.sleep(2)

print("Turning device on...")
await device.on()

print("Waiting 2 seconds...")
await asyncio.sleep(2)

device_info = await device.get_device_info()
print(f"Device info: {device_info.to_dict()}")

device_usage = await device.get_device_usage()
print(f"Device usage: {device_usage.to_dict()}")

if __name__ == "__main__":
```
 
