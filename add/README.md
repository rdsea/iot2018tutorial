# Adding resources and artefacts for interoperability

Resources and artefacts for interoperability are developed separately and  they can be made available for use. This requires two steps:

* the development of resources (and their providers) and of artefacts
* the definition of metadata about resources and artefacts

The development is not in our work and after having the metadata one can add resources or artefacts into rsiHub.

## Make resources available

Resources can be made available as long as the Adaptor interfaces to the Resource Provider work. In this case, resources metadata will be available from [rsiHubGlobal]() See [Resource Provider setup](../setup/providers) for further information.

## Make an artefact available

Artefact metadata will be made available through [rsiHubSAS](https://github.com/SINCConcept/HINC/tree/master/software-artefact-service)

### Using pizza

```
pizza artefact create <software-artefact> <execution-environment> <metadata-file> <name>

```
See examples from (https://github.com/rdsea/IoTCloudSamples/tree/master/IoTCloudUnits/node_red_dataflows)

### Using REST APIs

The REST APIs are available at [rsiHubSAS document](https://github.com/SINCConcept/HINC/tree/master/software-artefact-service)
