# z2mvis
Zigbee2MQTT Network Visualizer

Copy the file index.html to a webserver folder.

If you are using Domoticz and Mosquitto you can install as follows:

Clone the repository:

```
    cd ~/domoticz/www
    git clone https://github.com/lokonli/z2mvis.git
    cd z2mvis.git
```

The Zigbee Visualizer needs to communicate with your MQTT server via a websocket.
You have to enable the websocket interface in your MQTT server configuration.
The folder mqttconfig contains a configuration file.

```
cp mqttconfig/ws.conf /etc/mosquitto/conf.d/
```


Restart mosquitto:

```
sudo service mosquitto restart
```


On line 10 of index.html fill in the IP adress of your Mosquitto server.

After that use your browser to go to:

http://IP-adres:port/z2mvis/

(Use the IP adress:port of your Domoticz server)

Wait approximately 10 seconds, and then your zigbee network should become visible.
It refreshes automatically every 10 seconds.