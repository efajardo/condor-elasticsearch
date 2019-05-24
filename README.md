# Overview

Factory Data online (completed data from json and schedd status from xml) is aggregated using aggregator.py

messenger.py calls aggregator.py and appends each json to a list.

When called using monitor.py (set on cron for 5m), messenger.py creates exchange on pika using credentials in Rabbitmq_osg.json pushes the jsons from the list one by one to Elasticsearch.

Data is pulled from GRACC onto Grafana.

Curator on GRACC is set to delete data every 12 months.

### Prerequisites

```
Make sure a java VM is installed. Elasticsearch needs at least java 8.
```
