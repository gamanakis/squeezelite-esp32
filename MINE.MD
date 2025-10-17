it is necessary to compile with esp-idf-4.4 (for esp32-s3) and the following packages:
- protoc 29.2 (choco install protoc --version 29.2 --allow-downgrade)
- protobuf 5.29.2 (pip install protobuf==5.29.2)
- grpcio-tools 1.68.1 (pip install grpcio-tools==1.68.1)

Then copy the file for the esp32 from build-scripts/ to sdkconfig.defaults.
Change the target line "... = esp32" to "esp32s3" (NOTE: running idf.py set-target esp32s3 doesnt work as expected)
run idf.py menuconfig and: disable bluetooth, enable octal PSRAM as outlined here: https://github.com/jochen-rath/rfidLmsSteuerung
