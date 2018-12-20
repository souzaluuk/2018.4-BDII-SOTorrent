### Número de dados da amostra analisada
#### Java: Count Posts.png
```SQL
SELECT
  COUNT(*)
FROM
  [sotorrent-org:2018_12_09.Posts] AS Posts
JOIN
  [sotorrent-org:2018_12_09.PostReferenceGH] AS PostsGH
ON
  (Posts.Id = PostsGH.PostId)
WHERE
  Posts.Tags LIKE "%<java>%"
```
### Query que seleciona os dados analisados (Java)
```SQL
SELECT
  Posts.Id, Posts.Tags, PostsGH.SOUrl, PostsGH.GHUrl, Rand() AS RANDOM
FROM
  [sotorrent-org:2018_12_09.Posts] AS Posts
JOIN
  [sotorrent-org:2018_12_09.PostReferenceGH] AS PostsGH
ON
  (Posts.Id = PostsGH.PostId)
WHERE
  Posts.Tags LIKE "%<java>%"
ORDER BY
  RANDOM
LIMIT 383
```

Base manipulada: [SOTorrent](https://bigquery.cloud.google.com/table/sotorrent-org:2018_12_09.Posts)
