
# AIoT_codeRecognition_Group 6
Member: 112368029 陳沅昊/ 112368040 劉宇紘/ 112368098 謝嘉元

guide line of code recognition

適用於 Espressif 晶片組的 TensorFlow Lite Micro

AWS SageMaker雲端上操作流程


安裝 ESP IDF
------------
依照 ESP-IDF 入門指南的說明設定工具鏈和 ESP-IDF 本身。接下來的步驟假設此安裝成功且 IDF 環境變數已設定。具體來說，
設定 IDF_PATH 環境變數
```
cd esp/esp-idf
./install.sh
. .export.sh
```

使用組件
------------

在 ESP-IDF 專案中執行以下命令來安裝此元件：
```
cd esp-WHO/examples/code_recognition
```

建構範例  : code_recognition
------------
```
idf.py set-target esp32s3
```
```
idf.py fullclean
idf.py build
```

Download .bin to local file 
------------
```
partition-table.bin
esp-code-recognition.bin
bootloader.bin
```

PC本地端操作
------------

在console中執行以下命令來安裝此元件：
```
pip install esptool
```
#### 燒錄韌體
```
esptool.py --chip esp32 -p /dev/tty(YourUSBPort) write_flash -z 0x1000 ./bootloader.bin 0x8000 ./partition-table.bin  0x10000 ./esp-code-recognition.bin
```
#### How to find YourUSBPort
```
ls /dev/tty*
```
![image](https://github.com/joejojo789456/AIoT_codeRecognition/assets/166804089/18f19d0f-66f7-4463-84af-a0ae7ba0e7db)

#### 使用 Minicom 来查看ESP32的输出
* 安装 Minicom
```
sudo apt-get install minicom
sudo minicom -s
```
在配置介面中，選擇 "Serial port setup" 來設定串列埠參數。
Serial Device：修改為設備串列埠，例如 /dev/ttyUSB0。
Bps/Par/Bits：設定傳輸速率（例如 115200）及其他通訊參數（通常為 8N1）。
Exit：退出配置介面。
使用 Minicom 查看輸出。
  
* ![image](https://github.com/joejojo789456/AIoT_codeRecognition/assets/166804089/cf630cf3-0903-4970-bf56-eeaa89158f4d)


Espressif 晶片組上操作按鈕
------------
## QR-Code sample
![image](https://github.com/joejojo789456/AIoT_codeRecognition/assets/166804089/f10c0d56-5621-497c-af99-da5508591535)

## camera recognition
![image](https://github.com/joejojo789456/AIoT_codeRecognition/assets/166804089/e4090c53-6dfd-4f83-82d8-9034c5ec0c85)

## esp recognize and PC show the QR-Code numbers
![image](https://github.com/joejojo789456/AIoT_codeRecognition/assets/166804089/cf630cf3-0903-4970-bf56-eeaa89158f4d)
