# motion

## Deployment

The service is prepared to be reverse-proxied with **Traefik**, and accessible at `motion.${TRAEFIK_DOMAIN}` domain. How to run **Traefik** is not described here, check its [official site](https://traefik.io) and [my own Traefik deployment project](https://gitlab.com/pedroetb-projects/traefik).

The proxy needs a little help from **Caddy**, because Docker Swarm is not compatible with devices configuration (required to use video capabilities) and Traefik cannot work with Docker containers and Docker Swarm services at once.

Both, Docker container and service, can be running on different hosts, because they are able to communicate through a Docker network. Run `motion` Docker container on host which has the camera, so you can watch video.

Don't forget to edit `TRAEFIK_DOMAIN` environment variable before deploying.
