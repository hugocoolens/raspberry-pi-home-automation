##############################
Additional tips and references
##############################

These are some additional tips and references to interesting projects not mentioned in the book `Control Your Home with Raspberry Pi: Secure, Modular, Open-Source and Self-sufficient <https://koen.vervloesem.eu/books/control-your-home-with-raspberry-pi/>`_:

***************************
Integrating other protocols
***************************

The book dives into a specific set of home automation protocols, but the architecture is general and modular enough to use it with other protocols. I found the following projects that look interesting if you want to use another protocol (note that I didn't test them):

KNX
  `knx-mqtt-bridge <https://github.com/pakerfeldt/knx-mqtt-bridge>`_ bridges your KNX devices with MQTT. It doesn't have a Docker image on Docker Hub, but it supplies a Dockerfile to build your own Docker image.
Loxone
  `PyLoxone <https://github.com/JoDehli/PyLoxone>`_ is Home Assistant's binding for Loxone. If you use Home Assistant's Loxone integration and enable `MQTT Statestream <https://www.home-assistant.io/integrations/mqtt_statestream/>`_, state changes of your Loxone devices will also be published as MQTT messages. Another option is using `LoxBerry <https://www.loxwiki.eu/pages/viewpage.action?pageId=27100273>`_ with its MQTT integration.

*****************************************************
Chapter 4: MQTT (Message Queuing Telemetry Transport)
*****************************************************

* `system_sensors <https://github.com/Sennevds/system_sensors>`_: A Python script that sends system data such as CPU temperature, CPU, disk and memory usage, Wi-Fi signal strength and the number of pending updates over MQTT. Originally created for the Raspberry Pi, but now also works on other Linux systems. If you have MQTT discovery enabled in Home Assistant (see page 221 of the book), you don't need to configure anything in Home Assistant to see the data.

********************************
Chapter 10: Automating your home
********************************

* `RuuviTag Demo <https://github.com/koenvervloesem/ruuvitag-demo>`_: In this demo Telegraf collects MQTT messages with RuuviTag sensor measurements from bt-mqtt-gateway, sends the values to InfluxDB where they are stored in a time-series database, and then shows them in a Grafana dashboard. I haven't covered Grafana in the book, but you should definitely check it out when you want some more powerful dashboard functionality.

*************************
Chapter 12: Voice control
*************************

* `Automatically save the volume of your ReSpeaker 2-Mics Pi HAT <https://koen.vervloesem.eu/blog/automatically-save-the-volume-of-your-respeaker-2-mics-pi-hat/>`_: A solution I found to the (sometimes not so) minor annoyance that the playback volume of the ReSpeaker 2-Mics Pi HAT is reset to its maximal value after each reboot.
