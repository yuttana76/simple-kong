Clone project
```
$ git clone https://gitlab.com/supawit/simple-kong.git
$ cd simple-kong
```
Create .env file with content
```
TOKEN_SECRET=<randomstring>
```

Deploy kong, cassandra, konga stack
```
$ docker-compose up -d
```

Prepare database for kong
```
$ docker  run --rm \
--network simple-kong_default \
-e "KONG_DATABASE=cassandra" \
-e "KONG_CASSANDRA_CONTACT_POINTS=kong-database" \
kong:2.4-alpine kong migrations bootstrap
```

Manage kong
```
http://<server-ip>:1337
```