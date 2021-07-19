# yuhesien_aiot

專案架構：
# for PC
-- init_express (express server for PC) 
        1. Turn on terminal and cd to init_express/
        2. enter "npm start" (on/off server on terminal)
        
-- LiveStream-Flask-API (Flask server for PC that YOLO Image detect)
        1. Turn on terminal and cd to LiveStream-Flask-API/
        2. pip3 install -r requirements.txt
        2. enter "python3 yolov4_realtime.py" on terminal


# for RasberryPi
-- mjpg-streamer (LiveStreaming for RasberryPi that send the real-time image to the PC-Flask-server)
        // 基本影像支援安裝：
            sudo apt-get install libjpeg8-dev 
            sudo apt-get install imagemagick   
            sudo apt-get install libv4l-de
            make clean all
            sudo make install
            
        // 啟用樹莓派專用鏡頭
            ./mjpg_streamer -i "./input_raspicam.so" -o "./output_http.so -w ./www"
        // 啟用USB攝像頭
            ./mjpg_streamer -i "./input_uvc.so" -o "./output_http.so -w ./www"
            # or
            ./mjpg_streamer -i "./input_uvc.so -f 10 -r 640x320" -o "./output_http.so -w ./www"
        
