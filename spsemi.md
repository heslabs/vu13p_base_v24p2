# spsemi

---
### Install HAPS E-CoreFlow
```
scp spsemi@59.124.169.195:./vu13p/E-CoreFlow.v805.tgz .
scp spsemi@59.124.169.195:./vu13p/vu13p_base_v24p2.v505.tgz .
```

---
### Login WiFi router and find the IP address of Zynq module

```
https://192.168.72.1
Login: demo
Password: rpi5demo
```

---
### Connecting HAPS-PC via AnyDesk: 1577246064

```
ssh xilinx@192.168.72.3 -X (Password: xilinx)
cd ~/haps
make bus
make yolov8n-pos
make yolov8n-seg
```

---
### Connecting Zynq via SSH and Install Yolov8

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
### Install Utilities

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

