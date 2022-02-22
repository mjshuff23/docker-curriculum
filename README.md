# Docker-Curriculum

- [Docker-Curriculum](#docker-curriculum)
  - [Commands](#commands)

## Commands

- **NOTE:** The `--help` flag can be added to any docker command for documentation (e.g. `docker run --help`)

1. **pull** - Fetches [images](https://hub.docker.com/_/busybox/) from [Docker Registry](https://hub.docker.com/explore/) and saves it to our system.
   1. You can use the `docker images` command to see a list of all images on your system
2. **run** - Docker client finds image, loads up container, and runs a command in that container
   1. Use the `-it` flags to attach an interactive tty
3. **ps** - Shows all Docker containers currently running
   1. Add the `-a` flag to see a list of all container that have been run