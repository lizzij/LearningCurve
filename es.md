# elasticsearch
[reference 6.2](https://www.elastic.co/guide/en/elasticsearch/reference/6.2/index.html)

### basic concepts
- es: full-text search
  - near realtime = searchable after indexed
  - document = a JSON basic unit of information that can be indexed
  - index = a collection of documents with similar characteristics (lowercase name used for indexing, search, update and delete operations against the document in it)
  - node = a single server that stores data and contribute to indexing and searching (default name `UUID`)
  - cluster = collection of nodes, holds the entire data (default name `elasticsearch`)
  - shards & replicas = store a large amount of data, subdivide index into multiple shards, copies of index's shards into replicas to provide high availability in case a shard/node fails and allow searches in parallel.
    - Each index can be split into multiple shards, an index can also be replicated 0 or more times (primary/original shards + replica shards).
    - Number of shards and replicas defined per index at the time index is created (best practice), can also change dynamically using `_shrink` and `split` APIs
    - by default, each index is allocated 5 primary shards and 1 replica

### The Search API
- Through the REST request URI
```
GET /bank/_search?q=*&sort=account_number:asc&pretty
```
- Through the REST request body (in Query DSL)
```
GET /bank/_search
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ]
}
```

### Aggregations
- Metrics aggregations: compute metrics basd on values extracted from documents aggregated
  - Top hits aggregation:
- Bucket Aggregations: create buckets of documents, where each bucket is associated with a criterion

### ES DSL
- `Search` object

# Elasticsearch: The Definitive Guide
### 1O1
- Apache Lucene (a full-text search-engine library) + Elasticserch (in Java) RESTful API: every fielde is indexed adn serachable
- Java API (node/transport client) or RESTful API (port 9200) with JSON over HTTP

- relational DB vs Elasticsearch
  - relational = flatten the object to fit thte table schema vs document oriented, indexed
  ```
  Relational DB  ⇒ Databases ⇒ Tables ⇒ Rows      ⇒ Columns
  Elasticsearch  ⇒ Indices   ⇒ Types  ⇒ Documents ⇒ Fields
  ```

- basic demo
  - indexing (put) [what is megacorp :question: (or index in general)]
  - retrieving (get)
  - search lite (search)
    - query-string search
    - query DSL
      - match query
      - filter
      - full-text search (with relevance score) `match`
      - phrase search `match_phrase`
      - highlight
    - analytics

- distributed nature

### cluster

### data
- document: root object serialized into JSON and stored under a unique ID
- three required metadata
  - `_index` where the document lives (like a database in a relational db)
  - `_type` the class of object that the document represents
  - `_id` the unique identifier for the documnent
- indexing a documnent
  - `PUT` or `POST` (autogenerate ID)
- retriving a document
  -  `GET` (whole document) or specify `_source` parameter (part of the document)
- check if a document exists
  -  `HEAD`
- update a whole document
  - `PUT`
- creating a new document
  - `POST` or `PUT` with `op_type=create`/`_create`
- deleting a document
  - `DELETE`
