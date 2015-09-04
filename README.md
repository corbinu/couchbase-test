Couchbase Test
======================
This Docker container is setup to run Couchbase and create a single node cluster for use in testing.

## Running

It can be run on its own simply via:

```
CB_ID=$(docker run -d -p 8091:8091 corbinu/couchbase-test:$CB_VERSION)

docker exec -it $CB_ID couchbase-bootstrap bootstrap
```

Couchbase Dashboard will be on port mapped to 8091