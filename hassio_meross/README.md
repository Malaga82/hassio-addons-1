# Forked Hassio Meross integration from Carlo Satta

## About
The purpose of **hassio-meross** is to provide an integration in **Home Assistant** for **Meross** devices. It’s works connecting to **Meross** API system and not directly to the devices.


## Devices
For now the addons was tested with this devices:
 - [MSS425F - Smart Wi-Fi Surge Protector (EU/FR/US/JP)](http://www.meross.com/products/home_automation/smart_wi_fi_surge_protect/36.html)
 - [MSS310 - Smart Wi-Fi Plug with Energy Monitor (UK/EU/US/AU/FR/IT)](http://www.meross.com/products/home_automation/smart_wi_fi_plug/22.html)

Probably  it's work with other devices.

## Instruction
All the devices have to be  configured via the Meross app.

The addons was created to work out of the box with [MQTT Discovery](https://www.home-assistant.io/docs/mqtt/discovery/), so I suggest to add in your *`configuration.yaml`* the following configurations:

 ```
Example configuration.yaml entry
mqtt:
  broker: IP_SERVER_MQTT
  port: 1883
  username: youruser
  password: yourpassword
  discovery: true
  discovery_prefix: homeassistant
```


Edit the Configuration on addon side:
### mqtt
&nbsp;&nbsp;&nbsp;&nbsp;**host:** your mqtt host (required)

&nbsp;&nbsp;&nbsp;&nbsp;**port:** the mqtt port (Default: 1883, required)

&nbsp;&nbsp;&nbsp;&nbsp;**protocol:** the protocol (mqtt|mqtts|ws|wss) (Default: mqtt, required)

&nbsp;&nbsp;&nbsp;&nbsp;**username:** the mqtt username, leave empty if not used (Default: null)

&nbsp;&nbsp;&nbsp;&nbsp;**password:** the mqtt password, leave empty if not used (Default: null)

&nbsp;&nbsp;&nbsp;&nbsp;**rejectUnauthorized:** If you are using a **self-signed certificate** (Default: false)
### topic
&nbsp;&nbsp;&nbsp;&nbsp;**discovery_prefix:** the topic prefix. To use Discovery mqtt functionality have to be the same value of *discovery_prefix* set in home assistant configuration. (Default: homeassistant, required)
### meross
&nbsp;&nbsp;&nbsp;&nbsp;**email:** the email used in the meross application (required)

&nbsp;&nbsp;&nbsp;&nbsp;**password:** the password used in the meross application, MUST BE UP TO 10 CHARS (required)
### devices
&nbsp;&nbsp;&nbsp;&nbsp;**refresh:** the number of millisecond to refresh plugs statistics (Default: 30000 (30 sec.), required) Leave it to 30000 for preventing ban from meross cloud if you have many plugs


