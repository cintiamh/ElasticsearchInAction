# Elasticsearch In Action

Notes from book

Download ElasticSearch: https://www.elastic.co/downloads/elasticsearch

Install Java:
```
$ brew cask install java
$ brew cask install java8
```

If you get an error about HOMEBREW_CASK_OPTS:
```
$ export HOMEBREW_CASK_OPTS="--appdir=/Applications"
```

Install ElasticSearch:
```
$ brew install elasticsearch
```

Start ElasticSearch:
```
$ elasticsearch
```

* Port 9300 is used for inter-node communication (transport)
* Port 9200 is used for HTTP communication.
* Access the REST API: http://127.0.0.1:9200/
* Shards
  * balanced across available servers in cluster
  * replication
  * easy to add and remove on the fly
