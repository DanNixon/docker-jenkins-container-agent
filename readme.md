# Jenkins container agent

[![Docker Pulls](https://img.shields.io/docker/pulls/dannixon/jenkins-container-agent)](https://hub.docker.com/r/dannixon/jenkins-container-agent)
[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/dannixon/jenkins-container-agent)](https://hub.docker.com/r/dannixon/jenkins-container-agent/builds)

Jenkins agent running in a Docker container with access to the Docker daemon for starting containers within the build script.
Not the best way to do this but was deemed good enough for a bodge.

## Usage

```
docker run \
  --rm \
  --env JENKINS_URL="http://myinstance:8080" \
  --env JENKINS_SECRET=aaaaa \
  --env JENKINS_AGENT_NAME=aaaaa \
  --env PUID=1000 \
  --env PGID=1000 \
  --env HOST_DOCKER_GID=999 \
  --volume /var/run/docker.sock:/var/run/docker.sock \
  dannixon/docker-jenkins-slave-jnlp-docker
```
