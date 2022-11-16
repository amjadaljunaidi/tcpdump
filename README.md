# tcpdump
This Helm chart to collect tcpdump from linux node/s and save it throw azure file share, by default will create Daemonset and will keep running, for more option please check the Values.


## Install Chart

```bash
helm repo add tcpdump https://amjadaljunaidi.github.io/tcpdump/
helm repo update
helm install tcpdump tcpdump/tcpdump
```

### Using a custom image
To use your own custom tcpdump image pass `--set customImage.enabled=true --set customImage.image=<your image>` to the helm install command.

## Uninstall Chart
make sure to keep the pvc before deleting the chart
```bash
kubectl patch pv <pv_name>  -p "{\"spec\":{\"persistentVolumeReclaimPolicy\":\"Retain\"}}"
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
| customImage.enabled   | bool | false  |
| customImage.image | string | ubuntu:18.04 |
