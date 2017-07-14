# What it is?

Container to collect some metrics. Telegraf as an entrypoint to metrics.
Influxdb as a persistent DB. Grafana as a web interface to build graphs 

# How to run container

Create dir for influxdb and grafana:
```
mkdir -p /var/lib/grafana
mkdir -p /var/lib/influxdb
```

Run container:
```
docker run -d --name telegraf-influx-grafana -p 127.0.0.1:3003:3003 -p 127.0.0.1:8125:8125 -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/grafana:/var/lib/grafana -v /var/lib/influxdb:/var/lib/influxdb  telegraf-influx-grafana
```


Ports:
```
8125 - Telegraf port for input metrics in statsd format
3003 - Grafana port (password in grafana config)
```
