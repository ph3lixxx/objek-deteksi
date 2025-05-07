# Realtime object detection

## Instructions

0. [if using pi headless, `ssh -X user@hostname` to use X11 forwarding
1. `git clone https://github.com/ph3lixxx/objek-deteksi'
2. `cd objek-deteksi`
3. `pip3 install imutils`
4. `python3 real_time_object_detection.py --prototxt MobileNetSSD_deploy.prototxt.txt --model MobileNetSSD_deploy.caffemodel`
5. On the GUI window git `q` to quit
6. `python3 people_counter.py --prototxt MobileNetSSD_deploy.prototxt.txt --model MobileNetSSD_deploy.caffemodel`
