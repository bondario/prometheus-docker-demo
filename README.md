# prometheus-docker-demo

It's a demo kit for Docker Swarm monitoring with [Prometheus](https://prometheus.io/), [Grafana](http://grafana.org/), [cAdvisor](https://github.com/google/cadvisor), [Node Exporter](https://github.com/prometheus/node_exporter)

## Install

Clone this repository and run the monitoring stack:

```bash
$ git clone https://github.com/bondario/prometheus-docker-demo.git
$ cd prometheus-docker-demo
$ docker stack deploy -c docker-compose.yml mon
```

If you don't have docker:

```bash
$ sudo apt-get update
$ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
$ docker swarm init
```

Services:

* prometheus (metrics database) `http://<swarm-ip>:9090`
* grafana (visualize metrics) `http://<swarm-ip>:3000`
* node-exporter (host metrics collector)
* cadvisor (containers metrics collector)
