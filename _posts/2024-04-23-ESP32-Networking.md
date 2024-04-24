# ESP32 Networking Methods: SoftAP, Smartconfig, and AirKiss

ESP32 modules, in practical use, may need to connect to different networks. Fixing the wireless SSID and password in advance can be quite limiting. Therefore, we can use "over-the-air configuration technologies" such as Smartconfig, Airkiss, and Bluetooth-assisted networking. Below, I will detail the networking methods for the ESP32.

<div style="text-align: center;">
    <img src="/images/screen_shot_2016-04-27_at_1.30.27_pm_0.png" alt="1"/>
</div>


## 1. SoftAP Networking:
The ESP32 creates a WiFi hotspot (AP mode). Users connect their smartphones to this hotspot and send the WiFi information they wish to connect to the ESP32, including the SSID and password.  

__Advantages:__ This method is very reliable, with a success rate that generally reaches 100%, and the device-side code is simple.   

__Disadvantages:__ It requires manually switching the smartphone WiFi connection to the ESP32's AP network. Once configuration is complete, the connection must be switched back to the regular WiFi network. This process can be somewhat complex and may trouble users.  

## 2. Smartconfig Networking:
The ESP32 operates in promiscuous mode, listening to all packets in the network. The smartphone app encodes the currently connected SSID and password into a UDP packet, which is then sent via broadcast or multicast. The ESP32 receives the UDP packet, decodes it, and uses the SSID and password to connect to the network.  

__Advantages:__ This method is straightforward and easy for users to operate, but the success rate of networking is highly influenced by the environment.  

__Official Support:__ There are demos and a smart_config example provided. [SmartConfig](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/network/esp_smartconfig.html)  

## 3. AirKiss Networking:
AirKiss is a quick network configuration technology for Wi-Fi devices provided by the WeChat hardware platform. To configure devices for network access using the WeChat client, the device must support AirKiss technology.
The principle of AirKiss is very similar to Smartconfig. The device operates in promiscuous mode, and the WeChat client sends a broadcast packet containing the SSID and password. The device receives the broadcast packet and decodes it to obtain the SSID and password.  

__Advantages:__ This method is straightforward and easy for users to operate, but the success rate of networking is greatly influenced by the environment.  

__Official Support:__ Demos and smart_config examples are provided.  [SmartConfig](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/network/esp_smartconfig.html)  
