# From Simhub Discord:
Edited for github markdown, clarity and [Alert syntax](https://docs.github.com/es/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts)  
By **@supafly6789** at 09/10/2025. [Original](https://discord.com/channels/299259397060689920/306850631271055362/1425613572960030830)
   
  
**MQTT INFO:**  

I noticed a number of MQTT questions that have gone mostly unanswered across the forum and Discord, so I wanted to chip in my 2c to help anyone looking to get started.  
MQTT is a fantastic way to bring race telemetry into platforms like Home Assistant for automations and displays.  
Compiling a DLL can feel a bit intimidating if you haven’t done it before and might be a bit of a barrier-to-entry for a few users that are otherwise comfortable tinkering around with MQTT in platforms like HA.  
  
I use MQTT from SimHub to control various LEDs in my home and rig, and to feed telemetry into displays.  
Some examples from my setup:  
  
- Room lights automatically turn off when a race starts.  
- Tuya WiFi “underglow” LEDs on the rig that dim during a session. (SimHub has a Govee integration but I wanted to do this on the cheap!)  
- A rear LED segment of above underglow turns red under braking and whole strip flashes purple for a fastest lap.  
- A wall-mounted tablet shows the current car, race info, and lap times (I sync my Assetto Corsa car images to a folder in HA for this).  
  
**Because the MQTT Publisher project on GitHub is source-only, you’ll need to build it once yourself.**  
- Download and extract the repo:  https://github.com/SHWotever/SimHub-MQTT-Publisher  
- Extract it directly into your SimHub directory (C:\Program Files (x86)\SimHub).   
- Install Visual Studio Community 2022 with the .NET Framework 4.8 SDK workload.  
- Open SimHub.MQTTPublisher.sln from your SimHub folder in Visual Studio.  
If prompted for prerequisites, allow them to install.  
- In the menu: Build → Configuration Manager → Release.  
- Build (or press Ctrl + B).  
- When complete, copy:  
  - *SimHub.MQTTPublisher.dll *   
  - *MQTTnet.dll*  
from *C:\Program Files (x86)\SimHub\bin\Release\ *back into your main SimHub directory.  
- Launch SimHub and accept the prompt to load the new plugin. Also enable the toggle so it appears in the left-hand nav.  


> [!IMPORTANT]
> Note that if SimHub has any major updates, there is a chance that the plugin may need to be recompiled and imported, in which case do the above process again and overwrite the 2x DLL's in SimHub directory. 

HA Specific:
Configure the MQTT plugin in SimHub using your MQTT server hostname and some valid user credentials (homeassistant users using Mosquito Broker, this must be a valid User that has been set up in HA. I suggest creating a new one for SimHub)  
Change your topic if you feel the desire to, I have set mine to racing/sim (for example below)  
Over in HA, set up your sensors in configuration.yaml (or mqtt.yaml if you have one set up specific for mqtt already), I am using a format similar to the below:  

```yaml
mqtt:
  sensor:
    
name: "Sim Speed"
    state_topic: "racing/sim"
    value_template: "{{ value_json.carState.SpeedKmh | float(0) }}"
    unit_of_measurement: "km/h"
    icon: mdi:speedometer
```
Continue defining sensors for the remaining items, the default JSON payload in the project file is as below :
```json
{ 
"time": 1759898617695, 
"userId": "xxxx-xxxx-xxxx-xxxx-xxxx", 
"carState": { 
  "SpeedKmh": 0, 
  "Rpms": 4000, 
  "Brake": 100, 
  "Throttle": 0, 
  "Clutch": 100, 
  "Gear": "N",
   "CarCoordinates": [ 614.1373291015625, 5.2156219482421875, 5.778396129608154 ], 
  "CurrentLapTime": 105708, 
  "CarModel": "F1 2023 Red Bull RB19",
   "CarClass": null, 
  "EngineIgnitionOn": true, 
  "EngineStarted": true
   } 
}
```
If you want to extend the MQTT payload information, you can obtain a list of available properties from within SimHub (Under the Available Properties tab of course) and then edit the Payload files that are in the Payload folder of the MQTT Publisher project.

You will of course need to recompile the DLL's if you make changes here. 
<img width="1613" height="790" alt="image" src="https://github.com/user-attachments/assets/dfe14c5d-bfe6-4b13-a557-180a0885aef5" />
