Install
```
docker-compose up -d --build
```
Reset password and set in ENV variables for elastic user
```
docker-compose exec elastic bin/elasticsearch-reset-password -b -s -f -u elastic
```
Reset password and set in ENV variables for kibana_system user
```
docker-compose exec elastic bin/elasticsearch-reset-password -b -s -f -u kibana_system
```

Needed ENV variables:
```
ELASTIC_USERNAME=elastic
# Password for the 'elastic' user (at least 6 characters)
ELASTIC_PASSWORD=

KIBANA_USERNAME=kibana_system
# Password for the 'kibana_system' user (at least 6 characters)
KIBANA_PASSWORD=

KEYSTORE_PASSWORD=

# Version of Elastic products
STACK_VERSION=8.5.0

# Set the cluster name
CLUSTER_NAME=docker-cluster

#/usr/share/elasticsearch/bin/elasticsearch-reset-password -b -s -u elastic > pass

# Set to 'basic' or 'trial' to automatically start the 30-day trial
LICENSE=basic
#LICENSE=trial

# Port to expose Elasticsearch HTTP API to the host
ELASTIC_PORT=9200
#ELASTIC_PORT=127.0.0.1:9200

# Port to expose Kibana to the host
KIBANA_PORT=5601
#KIBANA_PORT=80

# encryption at least 32 characters
ENCRYPTION_KEY=

```