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
- Bucket Aggregations: create buckets of documents, where each bucket is associated with a vriterion

### ES DSL
- `Search` object
