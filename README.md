# pmacct-lab
**pmacct-lab** is a docker-compose project with  [Pmacct] collector, [Kafka] broker, and [Victoria Metrics] db as a backend.\
Project also includes [Traefik] reverse proxy, [Grafana] and Web-UI for Kafka.
### Runnig the project

Copy `.env.example`  to '.env' and set all variables in according to your environment.\
When just do:
```
docker-compose up -d
```
In [Grafana] go to `Configuration->Data Source` and click `Add data source`.\
Choose Prometheus, set URL `to http://victoria:8428`, and click `Save & Test`.\
Now you can quickly find data under `Explore` menu. Just query metric `bytes{}`.\



[//]:#

[pmacct]: <http://www.pmacct.net/>
[victoria metrics]: <https://victoriametrics.github.io/> 
[kafka]: <https://kafka.apache.org/>
[grafana]: <https://grafana.com/>
[traefik]: <https://docs.traefik.io/>

