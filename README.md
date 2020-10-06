# pmacct-lab
**pmacct-lab** is a docker-compose project with  [Pmacct] collector, [Kafka] broker, and [Victoria Metrics], [Clickhouse] and [Elasticsearch]  as a backends.\
Project also includes [Traefik] reverse proxy, [Grafana] and Web-UI for Kafka.
### Runnig the project

Copy `.env.example`  to '.env' and set all variables in according to your environment.\
Set vm.max_map_count = 262144:
```
sudo sysctl -w vm.max_map_count=262144
```
Don't forget to persist this value by adding `vm.max_map_count=262144` to /etc/sysctl.conf

Then just run:
```
docker-compose up -d
```
In [Grafana] go to `Configuration->Data Source` and click `Add data source`.\
Choose Prometheus, set URL to `http://victoria:8428`, and click `Save & Test`.\
Now you can quickly find data under `Explore` menu. Just query metric `bytes{}`.\

To get data from [Clickhouse] add datasource "ClickHouse" to [Grafana], vertamedia-clickhouse-datasource plugin is already installed.\
Set URL to `http://clickhouse:8123`, turn on "Basic Auth" and fill in login and password from you environment.

To discover and visualize data from [Elasticssearch] you can add Elasticsearch datasource in [Grafana] with URL `http://elastic:9200`.\
Or you can discover data with Kibana, deployed in docker-compose.



[//]:#

[pmacct]: <http://www.pmacct.net/>
[victoria metrics]: <https://victoriametrics.github.io/> 
[clickhouse]: <https://clickhouse.tech/> 
[Elasticsearch]: <https://www.elastic.co/> 
[kafka]: <https://kafka.apache.org/>
[grafana]: <https://grafana.com/>
[traefik]: <https://docs.traefik.io/>

