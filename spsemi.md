# spsemi

---
### Download and Install HAPS E-CoreFlow

```
scp spsemi@59.124.169.195:./vu13p/E-CoreFlow.v805.tgz .
```

---
### Download VU13P HAPS base design

```
scp spsemi@59.124.169.195:./vu13p/vu13p_base_v24p2.v505.tgz .
```

---
### Connecting WiFi router and find the IP address of ZYNQ module

```
https://192.168.72.1
Login: demo
Password: rpi5demo
```

---
### Connecting HAPS-PC via AnyDesk: 

```
AnyDesk ID: 1577246064
```


---
### Connecting ZYNQ via Serial 

```
sudo chmod 777 /dev/ttyUSB*
putty -serial -sercfg 115200,8,n,1,N /dev/ttyUSB1 -fn "client:Ubuntu Mono 18" &
```

---
### Connecting ZYNQ via SSH
```
ssh xilinx@192.168.72.3 -X (Password: xilinx)
```

---
### Runing Yolov8 - Image

```
cd ~/haps
make bus
```

---
### Runing Yolov8 - USBcam

```
cd ~/haps
make yolov8n-pos
make yolov8n-seg
```

---
### Connecting ZYNQ via SSH and Install Yolov8 (Optional)

```
ssh xilinx@192.168.72.3 -X (Password: xilinx)
sudo apt install feh
pip install numpy cv2
pip install ultralytics
scp spsemi@59.124.169.195:./zynq/zynq-yolov8.v806a.tgz .
tar zxvf zynq-yolov8.v806a.tgz
cd zynq-yolov8
make bus
```

---
### Install Utilities (Optional)

```
sudo apt install nomacs feh
sudo v4l2-ctl --list-devices
pip install v4l2-ctl
pip install opencs-contrib-python
pip install tensorflow
pip install matplotlib
pip install pyscreenshot
pip install mediapipe
pip install ultralytics
pip install numpy
pip install cv2
```

