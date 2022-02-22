# Docker-Curriculum

- [Docker-Curriculum](#docker-curriculum)
  - [Commands](#commands)
  - [Terminology](#terminology)

## Commands

- **NOTE:** The `--help` flag can be added to any docker command for documentation (e.g. `docker run --help`)

1. **pull** - Fetches [images](https://hub.docker.com/_/busybox/) from [Docker Registry](https://hub.docker.com/explore/) and saves it to our system.
   1. You can use the `docker images` command to see a list of all images on your system
2. **run** - Docker client finds image, loads up container, and runs a command in that container
   1. Use the `-it` flags to attach an interactive tty
   2. You can pass the `--rm` flag to automatically delete a container once it is exited
3. **ps** - Shows all Docker containers currently running
   1. Add the `-a` flag to see a list of all container that have been run
4. **rm** - Remove one or more containers.  Use `docker ps -a` to see a list of containers to clean up.  Use the `CONTAINER ID` to specify which container to remove.  On deletion, you should see the IDs echoed back to you.  
   1. If you have a bunch of container to delete in one go, copy-pasting IDs can be tedious.  In that case, run `docker rm $(docker ps -a -q -f status=exited)`.  This command deletes all containers that have been exited.
      1. `-q` Only returns the numeric IDs
      2. `-f` Filters output based on condition provided
      3. In later versions of Docker, `docker container prune` can be used to achieve the same effect
   2. `-f` - Force (via `SIGKILL`)
   3. `-l` - Remove specified link
   4. `-v` - Remove anonymous volumes associated with container
5. **rmi** - Delete images that are no longer running

## Terminology

- **Images** - The blueprints of our application which form the basis of containers.  Can be downloaded with the `docker pull` command
- **Containers** -  Created from Docker images and run the actual application.  We create a container using `docker run`.  A list of containers can be seen using the `docker ps` command
- **Docker Daemon** - The background service running on the host that manages building, running, and distributing Docker containers.  The daemon is the process that runs in the operating system which the client talks to
- **Docker Client** - The command line tool that allows the user to interact with the daemon.  More generally, there can be other forms of clients too, such as [Kitematic](https://kitematic.com/) which provide a GUI to the users.
- **Docker Hub** - A registry of Docker images.  You can think of the registry as a directory of all avaible Docker images.  If required, one can host their own Docker registries and can use them for pulling images.