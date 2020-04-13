---
layout: default
title: Docker
parent: Documentation
nav_order: 2
---
# Docker

![cli docker](../assets/images/docker.gif)

## Run Echo-Server

List of available [Docker Tags](https://hub.docker.com/r/ealen/echo-server/tags) - Read the [release notes](https://github.com/Ealenn/Echo-Server/releases)

```sh
docker run -d \
    -p 3000:80 \
    ealen/echo-server
```

You can use environments variables with `-e ENV_NAME=VALUE` or CLI arguments after image's name `ealen/echo-server --arg value`

### Example

- **With environments variables:**

```sh
docker run -d \
    -p 3000:80 \
    -e ENABLE__ENVIRONMENT=false 
    -e ELASTIC_APM_SERVICE_NAME=$ELASTIC_APM_SERVICE_NAME
    -e ELASTIC_APM_SECRET_TOKEN=$ELASTIC_APM_SECRET_TOKEN
    -e ELASTIC_APM_SERVER_URL=$ELASTIC_APM_SERVER_URL
    -e ELASTIC_APM_CAPTURE_BODY=$ELASTIC_APM_CAPTURE_BODY
    ealen/echo-server
```

- **With CLI arguments:**

```sh
docker run -d \
    -p 3000:80 \
    ealen/echo-server --enable:environment false
```

{% include_relative includes/section-configuration.md %}

---

{% include_relative includes/section-tests.md %}
