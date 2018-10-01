## Hooking up ScyllaDB and Spark - Writing to Scylla

### Launching Spark and Scylla

To set up your local Spark environment, run the following command:
```shell
docker-compose up -d
```

You can then launch the Spark shell as described in the blog post:
```shell
docker-compose exec spark-master spark-shell \
  --conf spark.driver.host=spark-master \
  --conf spark.cassandra.connection.host=scylla \
  --packages datastax:spark-cassandra-connector:2.3.0-s_2.11,commons-configuration:commons-configuration:1.10
```

### Shutting everything down

To stop everything:
```shell
docker-compose down
```
