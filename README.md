# Form-Engine (ESP32-Compatible)

## About:

This application was made to make the ESP32 turn on a PC over the internet.

The ESP32 will short the `Power SW` pins on the motherboard, simulating a power button click, which will turn on the PC.

This is a solution for those who have a router that flushes the ARP table and don't have means to manually add a static record to keep Wake-on-LAN (WoL) working.

## Adjusting settings via Form-Engine:

I included an [**Form-Engine**](https://github.com/AbdullahAlKhafajiDev/Form-Engine/tree/main/form_engine) which will use the base HTML template to generate an HTML file that has the inputs you desire.

All you need to do is edit the config.json file and run the Python script. It will create a single HTML file ready to use!

## Considerations:

- The webpage expects the response from the server to be in the following format: `{"message":"messageBody"}`, the webpage will output the `messageBody` to the little console window.
- Make sure the ESP32 will have a static IP in the router settings.
- To ensure the application is accessible from WAN, enable port-forwarding in the router to the ESP32 webserver on port `80`.

## Application:

The application is hosted on an ESP32 server connected to a relay.  
When the server recieves an ON/OFF message from the user, the server switches ON/OFF the relay.

<p align="center">
  <img src="https://github.com/AbdullahAlKhafajiDev/remote-ESP32-communication/blob/main/appImage.png?raw=true" />
</p>

## Testing the application:

I included a basic Python server, **example_server.py** that hosts a basic API that the client application can interact with. Again, the client expects a json response from the server in the following format: `{"message":"messageBody"}`.

## ESP32 code:

Heres's the ESP32 code I used in my project: https://github.com/AbdullahAlKhafajiDev/ESP32-CNC-API-generator/blob/main/esp32_sketch.ino
