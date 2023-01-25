## run command

```console
docker run \
	-p 9090:9090 \
	-v /containers/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
	--restart=always -d \
	prom/prometheus
```

## config example (prometheus.yml)

```plaintext
global:
  scrape_interval: 10s
  scrape_timeout: 5s

rule_files:
#  - alerts.yml

scrape_configs:
  - job_name: services
    metrics_path: /metrics
    static_configs:
      - targets: ["localhost:9090"]

```
