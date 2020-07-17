# Elasticsearch

- Started off as scalable Lucene(?)
- Horizonally scalable seach engine
- Each "shard" is an inverted index of documents(?)

- Server that can handle JSON requests and process and return JSON

- **Kibana**
    - Web UI for searching and visualizing
    - Complex aggregations, graphs, charts
    - Often used for log analysis

- **Logstash/Beats**
    - Ways to feed data into Elasticsearch
    - FileBeat can monitor log files, parse them, aand import into Elasticsearch in near-real-time
    - Logstash also pushes data into Elasticsearch from many machines
    - Not just log files

- **X-Pack** (Paid)
    - Security
    - Alerting
    - Monitoring
    - Reporting
    - Machine Learning
    - Graph Exploration

## Concepts of Elasticsearch
- **Cluster** - Like a DB
- **Documents**- Things you're searching for (Like a DB row)
- **Indices**- Like a DB table

## TF/IDF (Term Frequency, Inverse Document Frequency)
<img src = 'Screen Shot 2020-07-17 at 12.57.42 PM.png'>

- Term Frequency is how often a term appears in a *given document*
- Document Frequency is how often a term appears in *all documents*
- TF-IDF means Term Frequency*Inverse Document Frequency
- Term Frequency/Document Frequency measures the relevance of a term in a document.

***Space***- low document frequency<br>
***The***- high document frequency<br>

Therefore,<br>
***Space*** will rank highly<br>
***the*** will not

## How Elasticsearch scales
<img src="Screen Shot 2020-07-17 at 1.11.56 PM.png">

<img src="Screen Shot 2020-07-17 at 1.17.25 PM.png">

<img src="Screen Shot 2020-07-17 at 1.18.50 PM.png">
Total 6 shards 👆🏻 (1 replica for each of 3)

Quiz:
- [x] The schema for your documents are defined by? The index
- [x] What purpose do Inverted Indices serve? They quickly map search terms to documents
- [x] An index configured for 5 Primary Shards and 3 Replicas would have how many shards in total? 20. Because 5*3=15 replicas + 5 Primary
- [x] Elasticsearch is built only for full-text search of documents? False. It can be used for any sort of data.