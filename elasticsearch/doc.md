1.查看集群状态

```
GET /_cat/health?v
http://127.0.0.1:9200/_cat/health?v
```

> ```sh
> curl -X<VERB> '<PROTOCOL>://<HOST>:<PORT>/<PATH>?<QUERY_STRING>' -d '<BODY>'
> ```

2.索引一些数据

```
curl -X PUT "localhost:9200/customer/_doc/1?pretty" -H 'Content-Type: application/json' -d'{"name": "John Doe"}'
```

3.查询数据

```
curl -X GET "localhost:9200/customer/_doc/1?pretty"
```

4.批量插入数据

```
curl -H "Content-Type: application/json" -XPOST "localhost:9200/bank/_bulk?pretty&refresh" --data-binary "@accounts.json"
```

5.查询数据

```
curl -X GET "localhost:9200/bank/_search?pretty" -H 'Content-Type: application/json' -d'
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ]
}'
```

```
{
    "query": {
        "match": {
            "balance": 46170
        }
    },
    "sort": [
        {
            "account_number": "asc"
        }
    ],
    "from": 0,
    "size": 10
}
```

分词查询 match addresses contain `mill` or `lane`:

```
{
    "query": {
        "match": {
            "address": "mill lane"
        }
    },
    "sort": [
        {
            "account_number": "asc"
        }
    ],
    "from": 0,
    "size": 10
}
```
match_phrase
```
{
    "query": {
        "match_phrase": {
            "address": "mill lane"
        }
    },
    "sort": [
        {
            "account_number": "asc"
        }
    ],
    "from": 0,
    "size": 10
}
```

```
curl -X GET "localhost:9200/bank/_search?pretty" -H 'Content-Type: application/json' -d'
{
  "query": {
    "bool": {
      "must": [
        { "match": { "age": "40" } }
      ],
      "must_not": [
        { "match": { "state": "ID" } }
      ]
    }
  }
}
'
```

```
curl -X GET "localhost:9200/bank/_search?pretty" -H 'Content-Type: application/json' -d'
{
  "size": 0,
  "aggs": {
    "group_by_state": {
      "terms": {
        "field": "state.keyword"
      },
      "aggs": {
        "average_balance": {
          "avg": {
            "field": "balance"
          }
        }
      }
    }
  }
}
'

```

加密

```
curl -X POST "localhost:9200/_nodes/reload_secure_settings?pretty" -H 'Content-Type: application/json' -d'
{
  "secure_settings_password": "password" 
}
'

```

