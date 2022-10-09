# tcpdump
This Helm chart to collect tcpdump from linux nodes and save it storage account


# Install Chart

```bash
wget https://github.com/amjadaljunaidi/tcpdump/blob/main/tcpdump-0.1.0.tgz
gunzip tcpdump-0.1.0.tgz 
tar -xf tcpdump-0.1.0.tar 
helm install tcpdump --values  tcpdump/values.yaml --generate-name 
```
# Values
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
