# Elasticsearch on Docker
This docker-compose file will run up elasticsearch and kibana locally. It is intended for dev usage.
## Getting Started
### Prerequisites
[Docker](https://www.docker.com/) should be [installed](https://docs.docker.com/engine/installation/)
### Usage
To start:
```shell
docker-compose up -d
```
This will run up two docker machines:
1. Elasticsearch. Accessible at http://localhost:9200
2. Kibana. Accessible at http://localhost:5601. Data visualizer for the Elasticsearch database. Also has some dev tools to make life a bit easier.
It can take a couple of minutes to start Elasticsearch and Kibana. If following along with the logs:
```shell
docker-compose logs -f
```
it starts with a lot of elasticsearch lines, then after a while a lot of kibana lines at which point it should all be running.

The database will persist between restarts. It can be deleted by using:
```shell
docker-compose down -v
```
## Testing
Once running test that the elasticsearch database is running:
```shell
curl -XGET 'localhost:9200/_cluster/health?pretty'
```
To test Kibana, go to http://localhost:5601
On the 'Dev Tools' tab, and run:
```Shell
GET _cluster/health
```
## References
[Install Elasticsearch with Docker](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)
