Prepare your database
```
$ docker  run --rm \
--network simple-kong_default \
-e "KONG_DATABASE=cassandra" \
-e "KONG_CASSANDRA_CONTACT_POINTS=kong-database" \
kong:2.4-alpine kong migrations bootstrap
```