# Develop Interoperability Solutions - Protocol Interoperability with Sensor Data

We show one example of protocol interoperability with camera data

## Sensor-as-a-Service

We assume that there is a sensor as a service provider. If we call the provider, the provider will start some sensors which send data to a broker.

## Situation 1

For on-demand, we would like the provider sends the data to an MQTT provided by the user. The user can obtain data in csv.

To test this, you can use our [prebuilt sensor](https://github.com/rdsea/IoTCloudSamples/tree/master/IoTCloudUnits/simplesensor), such as:

```
$docker pull rdsea/simplesensor
$docker run
```


You can discover existing software artifacts for MQTT brokers. In our example,
we have an [MQTT Provider](https://github.com/rdsea/IoTCloudSamples/tree/master/IoTProviders/mosquitt-mqtt-provider) that you can request an instance.

```
$curl -X GET http://IP:3002/mosquittobroker
$
```

## Situation 2

The provider makes assumption that the sensor will send data to a specific queue and the user has to obtain the data from the designated MQTT queue.

However, the user wants to receive the data through AMQP. In this case, the user searches and requests MQTT-to-AMQP bridge.

## Situation 3

Want to obtain data in JSON but the provider can only offer csv data. Thus the user:

* Search for a possibility to do on-line transformation
* Push the data to the broker owned by the user

```
$docker pull rdsea/csvjson-bridge
$docker run
```
Such a bridge can be deployed by existing providers and used by the user.
