# Why this repo?

This repository should demonstrate a behaviour change between docker-compose v1 and docker-compose v2.

# Steps to repeat

1. Execute `docker-compose -f docker-compose.yml -f subpath/docker-compose.yml --profile=foo up -d`
2. Let everything start
3. Execute `docker-compose -f docker-compose.yml -f subpath/docker-compose.yml down`

# Actual behaviour:
* with `docker-compose v2`: Only the service(s) without a specified profile get stopped and removed
* with `docker-compose v1`: All services get stopped

# Expected behaviour:
`docker-compose v2` should either behave the same as `docker-compose v1` or this behaviour change should at least documented somewhere (at least I haven't found anything regarding this).
