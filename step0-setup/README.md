# Setup the testbed for tutorial

In this example, we show the setup of rsiHub for 1 rsiHub GlobalManagementService,  rsiHub LocalManagementService, rsiHub Software Artifact Management Service, and rsiHub for Interoperability Service

## External software requirements
###  MongoDB
These services need MongoDB, you can get free MongoDB instances from [mlab](https://mlab.com/) or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).

All services for tutorials can use the same MongoDB instance or different MongoDB instances

## Setup RabbitMQ

We need an instance of RabbitMQ for exchanging messages with rsiHub. You can get a free instance from [CloudAMQP](http://www.cloudamqp.com) or setup an instance of RabbitMQ.

## rsiHub GlobalManagementService

Obtain the docker image and prepare the configuration file for running the image:

```
$docker pull rdsea/rsihubglobal
$docker run -d -v /var/rsihubglobal/config:/rsihubglobal/config -p 8080:8080 rdsea/rsihubglobal
```
/var/rsihubglobal/config is the directory in the host that contains the application.properties file for rsihubglobal. For the tutorial, this application.properties file is available from the organizer.

Further information can be found in [the installation](https://github.com/SINCConcept/HINC/tree/master/global-management-service)

## rsiHub LocalManagement Service

```
$docker pull rdsea/rsihublocal
$docker run -v /var/rsihublocal/config:/rsihublocal/config  rdsea/rsihublocal
```
/var/rsihublocal/config is the directory in the host that contains the application.properties file for rsihublocal. For the tutorial, this application.properties file is available from the organizer.


For further information [see the installation](https://github.com/SINCConcept/HINC/tree/master/local-management-service)

## rsiHub SAS

[see the installation](). We also prepare a docker where you can download and use it
```
$docker pull rdsea/rsihubsas
$docker run -d -p 8082:8082 rdsea/rsihubsas
```

## Setup Interoperability Service

In order to setup the rsiHub Interoperability Service (rsihubintop), pull the docker file from docker hub and provide a configuration file:

```
$docker pull rdsea/rsihubintop
$nano /var/temp/rsihubintop/config/production.json
$docker run -d -v /var/temp/rsihubintop/config:/rsihubintop/config/ -e "NODE_ENV=production" -p 8081:8081 rdsea/rsihubintop
```

/var/temp/rsihubintop/config can be changed. For an example of production.json, pls. see the source directory or obtain it during the tutorial.

##Set up rsiHub Client

Download [the code of pizza](https://github.com/SINCConcept/HINC/tree/master/slice-management-client)  and follow [the installation instruction](https://github.com/SINCConcept/HINC/tree/master/slice-management-client)
