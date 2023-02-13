## Run Command

```
docker run -d -p 9100:9100 --name node-exporter prom/node-exporter:latest
```


## Prometheus Config File Sample

```
- job_name: node
  static_configs:
  - targets:
    - host.docker.internal:9100
```
