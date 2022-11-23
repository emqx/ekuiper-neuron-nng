# ekuiper-neuron-nng

![Version: 1.0.8](https://img.shields.io/badge/Version-1.0.8-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| ekuiperEnv.enabled | bool | `true` |  |
| ekuiperEnv.keys.fileLog | string | `"KUIPER__BASIC__FILELOG"` |  |
| ekuiperEnv.keys.mqttDefaultServer | string | `"MQTT_SOURCE__DEFAULT__SERVER"` |  |
| ekuiperEnv.keys.premetheusPort | string | `"KUIPER__BASIC__PROMETHEUSPORT"` |  |
| ekuiperEnv.keys.prometheusEnabled | string | `"KUIPER__BASIC__PROMETHEU"` |  |
| ekuiperEnv.values.fileLog | bool | `false` |  |
| ekuiperEnv.values.mqttDefaultServer | string | `"tcp://broker.emqx.io:1883"` |  |
| ekuiperEnv.values.premetheusPort | int | `9081` |  |
| ekuiperEnv.values.prometheusEnabled | bool | `true` |  |
| ekuiperMounts[0].capacity | string | `"100Mi"` |  |
| ekuiperMounts[0].mountPath | string | `"/kuiper/data"` |  |
| ekuiperMounts[0].name | string | `"pvc-ekuiper-data"` |  |
| ekuiperMounts[1].capacity | string | `"100Mi"` |  |
| ekuiperMounts[1].mountPath | string | `"/kuiper/plugins/portable"` |  |
| ekuiperMounts[1].name | string | `"pvc-ekuiper-plugins-portable"` |  |
| images.ekuiper.repository | string | `"lfedge/ekuiper"` |  |
| images.ekuiper.tag | string | `"1.7.1-slim-python"` |  |
| images.neuron.pullPolicy | string | `"IfNotPresent"` |  |
| images.neuron.repository | string | `"emqx/neuron"` |  |
| images.neuron.tag | string | `"2.2.8"` |  |
| images.pullPolicy | string | `"IfNotPresent"` |  |
| neuronEnv.enabled | bool | `true` |  |
| neuronEnv.key.disableAuth | string | `"DISABLE_AUTH"` |  |
| neuronEnv.value.disableAuth | bool | `true` |  |
| neuronMounts[0].capacity | string | `"100Mi"` |  |
| neuronMounts[0].mountPath | string | `"/opt/neuron/persistence"` |  |
| neuronMounts[0].name | string | `"pvc-neuron-data"` |  |
| nodeSelector | object | `{}` |  |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.enabled | bool | `false` |  |
| persistence.storageClass | string | `"huawei-nfs"` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| service.annotations | object | `{"eip.openelb.kubesphere.io/v1alpha2":"eip-pool","lb.kubesphere.io/v1alpha1":"openelb","protocol.openelb.kubesphere.io/v1alpha1":"layer2"}` | Provide any additional annotations which may be required. Evaluated as a template |
| service.nodePorts | object | `{"ekuiper":{"api":null,"push":null},"neuron":{"api":null,"web":null}}` | Specify the nodePort(s) value for the LoadBalancer and NodePort service types. ref: https://kubernetes.io/docs/concepts/services-networking/service/#type-nodeport |
| service.ports | object | `{"ekuiper":{"api":{"name":"ekuiper-api","port":9081},"push":{"name":"ekuiper-push","port":10081}},"neuron":{"api":{"name":"neuron-api","port":7001},"web":{"name":"neuron-web","port":7000}}}` | Service ports |
| service.ports.ekuiper.api.name | string | `"ekuiper-api"` | eKuiper api port name |
| service.ports.ekuiper.api.port | int | `9081` | eKuiper api port |
| service.ports.ekuiper.push.name | string | `"ekuiper-push"` | eKuiper push port name |
| service.ports.ekuiper.push.port | int | `10081` | eKuiper push port |
| service.ports.neuron.api.name | string | `"neuron-api"` | Neuron API port name |
| service.ports.neuron.api.port | int | `7001` | Neuron API port |
| service.ports.neuron.web.name | string | `"neuron-web"` | Neuron Dashboard port name |
| service.ports.neuron.web.port | int | `7000` | Neuron Dashboard port |
| service.type | string | `"ClusterIP"` | service type |
| tolerations[0].effect | string | `"NoExecute"` |  |
| tolerations[0].key | string | `"node.kubernetes.io/not-ready"` |  |
| tolerations[0].operator | string | `"Exists"` |  |
| tolerations[0].tolerationSeconds | int | `30` |  |
| tolerations[1].effect | string | `"NoExecute"` |  |
| tolerations[1].key | string | `"node.kubernetes.io/unreachable"` |  |
| tolerations[1].operator | string | `"Exists"` |  |
| tolerations[1].tolerationSeconds | int | `30` |  |

