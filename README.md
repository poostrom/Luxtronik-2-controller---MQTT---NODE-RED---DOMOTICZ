# Luxtronik-2-controller---MQTT---NODE-RED---DOMOTICZ
Manual to get info from a Luxtronik 2 controller (heatpump) to Domoticz via NODE-RED &amp; MQTT

First of all, install MQTT on your Raspberry Pi, Google is your friend, but ok:
```
sudo apt-get install mosquitto
```

If you want the clients as well (not needed for this, but handy):
```
sudo apt-get install mosquitto-clients
```
Follow this guide to install and setup Node-Red on your Raspberry:
https://nodered.org/docs/getting-started/raspberrypi

You will need to add hardware in your Domoticz to be able to talk to MQTT. This is called "MQTT client gateway with LAN interface", standard hardware in Domoticz.

In Node-Red you need to install this node: (you can install it from the GUI or CLI)
https://flows.nodered.org/node/node-red-contrib-luxtronik2

And this node: (this is just date/time formatting for the alarms coming from the Luxtronik):
https://flows.nodered.org/node/node-red-contrib-moment

I've created 1 flow that covers all. This is work in progress. Not all of the information coming from the heatpump is used, so feel free to add more.
You will need to change all the sensor ID's in the function node corresponding with your Domoticz ID's.
Also you will need to change the MQTT server IP to your own MQTT IP.

Virtual sensors to create in Domoticz:
- 7 Temp sensors
- 1 Selector Switch with values: 0:Off 10:Verwarming 20:Heet water 30:Koeling
- 1 alarm sensor

This is working for the Luxtronik 2.0 controller with firmware 1.86
