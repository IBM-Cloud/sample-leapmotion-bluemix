Sample to connect Leap Motion with Bluemix
================================================================================

The [sample-leapmotion-bluemix](https://github.com/IBM-Bluemix/sample-leapmotion-bluemix) project contains sample code that shows how to send MQTT commands to [IBM Bluemix](https://bluemix.net) when gestures are recognized via [Leap Motion](https://www.leapmotion.com/).

Right now four gestures can be recognized: swipe left, swipe right, screen tap and circle. These gestures can be used, for example, to steer [Anki Overdrive](https://github.com/IBM-Bluemix/node-mqtt-for-anki-overdrive) cars.

The best way to explain the functionality are pictures. Check out the pictures in the [screenshots](https://github.com/IBM-Bluemix/sample-leapmotion-bluemix/tree/master/screenshots) directory.

![alt text](https://raw.githubusercontent.com/IBM-Bluemix/sample-leapmotion-bluemix/master/screenshots/swipeleft.jpg "Leap Motion")

![alt text](https://raw.githubusercontent.com/IBM-Bluemix/sample-leapmotion-bluemix/master/screenshots/swiperight.jpg "Node-RED flow")

The project has been implemented via the [Leap Motion JavaScript SDK](https://developer.leapmotion.com/documentation/javascript/index.html). MQTT messages are sent via [Paho](https://www.eclipse.org/paho/clients/js/) to [IBM Bluemix](https://bluemix.net/) and the [Internet of Things](https://console.ng.bluemix.net/catalog/internet-of-things/) foundation. 

Via the Internet of Things foundation the commands can be sent to devices like the Anki Overdrive cars. The cars can be connected to the foundation via the separate project [Node.js Controller and MQTT API for Anki Overdrive](https://github.com/IBM-Bluemix/node-mqtt-for-anki-overdrive).

Author: Niklas Heidloff [@nheidloff](http://twitter.com/nheidloff)


Setup
================================================================================

In order to run this sample you need the [Leap Motion](https://www.leapmotion.com/product/desktop) device and you need to set up the [software](https://www.leapmotion.com/setup).

The sample is just a single HTML file with JavaScript code that can be run locally in web browsers. Via the API it connects to a local web socket server to receive data.

Invoke the following command to download the project.

> git clone https://github.com/IBM-Bluemix/sample-leapmotion-bluemix.git

You will need to create an instance of the [IBM IoT Foundation](https://console.ng.bluemix.net/catalog/services/internet-of-things-foundation/) service in Bluemix. Within the IoT Foundation dashboard your need to register a new device with the type "leapmotion". After this copy and paste the following data in bluemix.html.

1. mqttConfig.deviceId
2. mqttConfig.apiToken
3. mqttConfig.orgId

In order to steer the [Anki Overdrive](https://github.com/IBM-Bluemix/node-mqtt-for-anki-overdrive) cars you can import a [flow](https://github.com/IBM-Bluemix/node-mqtt-for-anki-overdrive/blob/master/node-red-speech-kinect-leap.json) in Node-RED.