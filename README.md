# tcpdump
This Helm chart to collect tcpdump from linux nodes and save it storage account as Daemonset and it will keep running


## Install Chart

```bash
helm repo add tcpdump https://amjadaljunaidi.github.io/tcpdump/
helm install tcpdump tcpdump/tcpdump
```



## Uninstall Chart
make sure to keep the pvc before deleting the chart
```bash
kubectl patch pv <pvc_name>  -p "{\"spec\":{\"persistentVolumeReclaimPolicy\":\"Retain\"}}"
helm uninstall tcpdump
```

## Values
| Key | Type | Default |
|-----|------|---------|
| tcpReplica   |   int   |   15      |
| src   |  int    |  empty means all sources, example x.x.x.x or FQDN     |
| dst   |   int   |  empty means destinations, example x.x.x.x or FQDN    | 
| nodeSelector  |   object   |   {"kubernetes.io/os":"linux"}      |
| resources.limits.cpu    |   string   |     "100m"    | 
| resources.limits.memory    |  string    |    "90Mi"     |
| resources.requests.cpu    |    string  |      "100m"   | 
| resources.requests.memory    |  string    |    "90Mi"     |
