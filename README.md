# Docker Swarm Infrastructure

Startup PostgreSQL, Kafka, Redis, TimescaleDB
### Start
```
docker stack deploy -c docker-compose.yaml infra --with-registry-auth
```
### How to use with other swarms:
```
like Spring env:
SPRING_DATASOURCE_URL=jdbc:postgresql://infra_postgres_container_authtest:5432/homerep_userservice
# add swarm prefix of service 


# use additional global network in service

networks:
  your-default-network:
    driver: overlay
    attachable: true
# network used in infrastructure swarm
  homerep-global-network:
    external: true

```
