# serverproject

## 1. Clone Repo:

The project uses Git Submodules, make sure you clone the repo using:
`git clone https://github.com/Lightnerr/serverproject.git /opt/serverproject`

## 2. Setup services:
### 2.1 Install Docker & Docker Compose:

See here for Docker: https://www.docker.com/get-started
For Docker-compose: https://docs.docker.com/compose/install/

### 2.2 Install Plex & other applications mentioned

**NOTE:** Before running this, you should configure env files
Docker compose files are located in the `dockerfiles/server` directory, and have comments explaining various variables etc.

```
# Copy compose files into /opt
cp -rp /opt/serverproject/dockerfiles/server/* /opt/

# Stand up each container... (go grab a coffee, this will take a while)
find /opt/ -maxdepth 1 -name "docker*" -type d \( ! -wholename /opt/ \) -exec bash -c "cd '{}' && docker-compose up -d" \;
 
