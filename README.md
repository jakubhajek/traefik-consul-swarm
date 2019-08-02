# traefik-consul-swarm
Example code how to deploy Traefik with Consul as the provider

These stack files have been presented during the online meetup organized by Containous - a company behind Traefik. The presentation is entitled:

## Container Orchestration with Traefik based on Docker Swarm

The link to the presentation is available here.

<https://www.slideshare.net/jakubhajekcometari/container-orchestration-with-traefk-on-docker-swarm>

### Deployment order

The stack files have to be deployed in following order

1.  Consul
```docker stack deploy -c stack-consul.yml consul --with-registry-auth```

2. Traefik stack
```docker stack deploy -c stack-traefik.yml  traefik --with-registry-auth```

3. Application Stack
```docker stack deploy -c stack-app.yml app --with-registry-auth```