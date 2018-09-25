
# IBM Digital Experience - Portal Server

![IIB Logo](https://ot4i.github.com/iib-helm/ibm-integration-bus-dev/IBM_Integration_Bus_Icon.svg)

IBM WebSphere Portal provides enterprise portals that help companies deliver highly-personalized, social experiences for their customers either on premise or in private or public clouds. Deliver faster response to the demands for digital experience solutions by giving users a single point of access to the applications, services, information and social connections they need. Provide pre-installed, pre-configured images and expert deployment patterns for automated provisioning, aiding in the creation of an optimized user experience. Help increase visitor response and reduce web operations cost.

# Introduction

This chart deploys a single WebSphere Portal node, containing a single portal server into an IBM Cloud Private or other Kubernetes environment.

## Installing the Chart

To install the chart with the release name `rel1`:

```bash
helm install --name rel1 portal9 --set license=accept
```

This command accepts the [IBM Portal Server v9 license](LICENSE) and deploys an IBM Portal server on the Kubernetes cluster. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: See all the resources deployed by the chart using `kubectl get all -l release=rel1`

## Uninstalling the Chart

To uninstall/delete the `rel1` release:

```bash
helm delete rel1
```

The command removes all the Kubernetes components associated with the chart.

## Configuration
The following table lists the configurable parameters of the `ibm-integration-bus-dev` chart and their default values.

| Parameter                        | Description                                     | Default                                                    |
| -------------------------------- | ----------------------------------------------- | ---------------------------------------------------------- |
| `license`                        | Set this to accept the terms of the IBM license | `Not accepted`                                     |
| `image.repository`               | Image full name including repository            | `ibmcom/portal`                                                |
| `image.tag`                      | Image tag                                       | `v9`                                                        |
| `image.pullPolicy`               | Image pull policy                               | `IfNotPresent`                                             |
| `image.pullSecret`               | Image pull secret, if you are using a private Docker registry | `nil`                                        |
| `service.type`                   | Kubernetes service type for exposing ports       | `NodePort`                                  |
| `resources.limits.cpu`          | Kubernetes CPU limit for the Portal container | `2`                                                   |
| `resources.limits.memory`       | Kubernetes memory limit for the Portal container | `2048Mi`                                              |
| `resources.requests.cpu`        | Kubernetes CPU request for the Portal container | `1`                                                 |
| `resources.requests.memory`     | Kubernetes memory request for the Portal container | `512Mi`                                            |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart.

> **Tip**: You can use the default [values.yaml](values.yaml)

[View the IBM Digital Experience  Dockerfile repository on Github](https://github.com/digexp/)

[View the Portal Image build instructions](https://github.com/digexp/ci.docker.websphere-portal)

[Learn more about IBM Digital Experience](https://www.ibm.com/support/knowledgecenter/en/SSHRKX_9.0.0/welcome/wp9_welcome.html)

_Copyright IBM Corporation 2017. All Rights Reserved._

_The IBM Integration Bus logo is copyright IBM and is provided for use for the purposes of IBM Cloud Private. You will not use the IBM Integration Bus logo in any way that would diminish the IBM or IBM Integration Bus image. IBM reserves the right to end your privilege to use the logo at any time in the future at our sole discretion. Any use of the IBM Integration Bus logo affirms that you agree to adhere to these conditions._
