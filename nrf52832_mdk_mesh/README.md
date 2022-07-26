nRF52832-mdk 開發環境
===
安裝步驟參考[nRF5 SDK for Mesh - nRF52832-MDK Documentation](https://wiki.makerdiary.com/nrf52832-mdk/cn/mesh/)，裡面有遇到版本過舊的問題，例如新版的pyocd並沒有pyocd-flash這個工具，所以必須要使用`python3-pyocd`才能得到pyocd-flash這項工具。  
另外nRF52832也有少了一些mesh sdk有建議安裝的(可以參考[Nordic Semiconductor Infocenter ](https://infocenter.nordicsemi.com/index.jsp?topic=%2Fcom.nordic.infocenter.meshsdk.v3.0.0%2Fmd_doc_getting_started_mesh_quick_start.html))的東西Doxygen、Graphviz、Mscgen，另外linux也沒有pc lint這項工具使用，所以在cmake執行時會出現沒有pc lint。  
這些問題都是回頭翻cmake list檔案才發現的問題。

Build
---
```
docker build -d nrf52832-mdk-mesh
```

Run
---
```
// windows
docker run  -it --rm -v <<path>>:/app --isolation=process --device="class/{interface class GUID}" nrf52832-mdk-mesh

// linux
docker run -it --rm -v <<path>>:/app --device=/dev/ttyUSB{usb number} nrf52832-mdk-mesh
```