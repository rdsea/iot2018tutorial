# Search for Interoperability Solutions

Another important step in IoT Interoperability is to find suitable resources and software artefacts for building IoT Interoperability solution. With our tools and services, resources and Software artefacts for interoperability can be searched from rsiHub using pizza command line.

## General commands

$pizza query-intop
$pizza artefact

## Search for REST pull-push Google Storage  

```
$pizza artefact list

 5bab72c046e0fb00011901b8 │ docker                │ datastorageArtefact

$pizza artefact get 5bab72c046e0fb00011901b8

```

We can also search using metadata, such as

```
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{"metadata.inputs.protocol.protocol_name": "mqtt"}' 'http://[HOST]:8082/softwareartefacts/search'

```

## Stories for tutorial

### Search artefacts for pull and push video data

In an emergency context, it is  required the seaport authority to push video data to certain storage for sharing video. Typically the IoTVideoProvider allows the seaport authority to PULL video only through REST API.

Given the situation, the seaport authority searches for

* a bridge that can pull data from URL and push the data to a storage, e.g., Google Storage.


The following search would find suitable artefacts

```
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{"executionEnvironment": "docker", \
 "metadata.inputs.protocol.protocol_name": "http" \
 }' 'http://[HOST]:8082/softwareartefacts/search'

 ```
Then search for docker provider:

Given the result from the search. The seaport authority can start to create a slice.   
