
# AIoT_codeRecognition
guide line of code recognition

適用於 Espressif 晶片組的 TensorFlow Lite Micro


安裝 ESP IDF
------------
依照 ESP-IDF 入門指南的說明設定工具鏈和 ESP-IDF 本身。接下來的步驟假設此安裝成功且 IDF 環境變數已設定。具體來說，
設定 IDF_PATH 環境變數
```
./install.sh
. .export.sh
```

使用組件
------------

在 ESP-IDF 專案中執行以下命令來安裝此元件：
```
cd esp-WHO/examples/code_recognition
```

相依套件
------------

在console中執行以下命令來安裝此元件：
```
pip install esptool
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
