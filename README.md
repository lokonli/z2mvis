# z2mvis
Zigbee2MQTT Network Visualizer

![z2mvis](https://user-images.githubusercontent.com/22852111/70855310-37b3a000-1ec9-11ea-93bd-45ebd6afcecc.JPG)


Copy the file index.html and z2mvis.css to a webserver folder.

If you are using Domoticz and Mosquitto you can install as follows:

Clone the repository:

```
cd ~/domoticz/www
git clone https://github.com/lokonli/z2mvis.git
cd z2mvis
```

The Zigbee Visualizer needs to communicate with your MQTT server via a websocket.
You have to enable the websocket interface in your MQTT server configuration.
The folder mqttconfig contains a configuration file.

```
sudo cp mqttconfig/ws.conf /etc/mosquitto/conf.d/
```


Restart mosquitto:

```
sudo service mosquitto stop
sudo service mosquitto start
```

Copy the default configuration:

```
cp config_default.js config.js
```

Edit config.js with the IP address of the MQTT server, including the port of the websocket connection.

After that use your browser to go to:

```
http://IP-adres:port/z2mvis/
```

(Use the IP adress:port of your Domoticz server)

Wait approximately 10 seconds, and then your zigbee network should become visible.
It refreshes automatically every 10 seconds.

### Notes

* z2mvis doesn't work when loaded over https. You must use http.

### Update

If you have installed z2mvis with ```git clone```, you can update z2mvis by executing the following command in the z2mvis folder:

```
git pull
```


## Settings

You can set default parameters via the config.js file:

```
var z2mvisConfig = {
    mqttserver : '192.168.178.18:9001',
    renderer: 'dot'
}
```

As alternative renderer 'circo'can be used.

You can also set the parameters via the url. Example:

```
http://192.168.178.18:8080/z2mvis/?renderer=dot&mqttserver=192.168.178.18:9001
```
