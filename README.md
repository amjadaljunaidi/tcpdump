# tcpdump
This Helm chart to collect tcpdump from linux nodes and save it storage account


# Install Chart

Download the helm chart 
```bash
wget https://github.com/amjadaljunaidi/tcpdump/blob/main/tcpdump-0.1.0.tgz?raw=true
gunzip tcpdump-0.1.0.tgz 
tar -xf tcpdump-0.1.0.tar 
helm install tcpdump --values  tcpdump/values.yaml --generate-name 
```
# Values
tcp
