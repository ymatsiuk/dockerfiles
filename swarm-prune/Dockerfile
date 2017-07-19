#
# swarm service for `docker system prune`
#
#      version: '3.3'
#      services:
#        docker-system-prune:
#          hostname: docker-system-prune
#          image: ymatsiuk/swarm-prune:latest
#          volumes:
#            - source: /var/run/docker.sock
#              target: /var/run/docker.sock
#              type: bind
#          deploy:
#            restart_policy:
#              delay: 86400s # 1 day
#              max_attempts: 3650 # 10 years
#            mode: global
#
#
#
# docker run --mount type=bind,src=/var/run/docker.sock,dst=/var/run/docker.sock -it ymatsiuk/swarm-prune

FROM docker:edge
CMD ["docker", "system", "prune", "--force", "--all"]
