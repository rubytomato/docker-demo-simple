# docker demo simple

## docker image

### app1

[ubuntu](https://hub.docker.com/_/ubuntu/)

### app2

[centos](https://hub.docker.com/_/centos/)

## dcoker-compose command

### build

```text
docker-compose build
```

```text
docker-compose build --no-cache
```

### up

```text
docker-compose up -d
```

### ps

```text
docker-compose ps
```

### down

```text
docker-compose down
```

### exec

**app1**

```text
docker-compose exec app1 bash --login
```

**app2**

```text
docker-compose exec app2 bash --login
```
