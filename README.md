# docker demo simple

simple demonstration of docker with 2 containers

**references**

* [Compose file version 3 reference](https://docs.docker.com/compose/compose-file/)

## docker image

### app1

[ubuntu](https://hub.docker.com/_/ubuntu/)

OS Version

```bash
$ cat /etc/os-release
NAME="Ubuntu"
VERSION="18.04.1 LTS (Bionic Beaver)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 18.04.1 LTS"
VERSION_ID="18.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=bionic
UBUNTU_CODENAME=bionic
```

install package

* curl
* nodejs
* git

### app2

[centos](https://hub.docker.com/_/centos/)

OS Version

```bash
$ cat /etc/os-release
NAME="CentOS Linux"
VERSION="7 (Core)"
ID="centos"
ID_LIKE="rhel fedora"
VERSION_ID="7"
PRETTY_NAME="CentOS Linux 7 (Core)"
ANSI_COLOR="0;31"
CPE_NAME="cpe:/o:centos:centos:7"
HOME_URL="https://www.centos.org/"
BUG_REPORT_URL="https://bugs.centos.org/"

CENTOS_MANTISBT_PROJECT="CentOS-7"
CENTOS_MANTISBT_PROJECT_VERSION="7"
REDHAT_SUPPORT_PRODUCT="centos"
REDHAT_SUPPORT_PRODUCT_VERSION="7"
```

install package

* curl
* nodejs
* git

## docker-compose command

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

```text
docker-compose up -d app1
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
