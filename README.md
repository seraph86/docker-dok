# Docker

Usage:

```bash
docker [OPTIONS] COMMAND
```

## Commands:

### version

Show version

```bash
docker version [OPTIONS]
```

### ps

List containers (default shows running)

```bash
docker ps [OPTIONS]
```

| options        | type / default | descripitons                                                      |
| -------------- | :------------: | ----------------------------------------------------------------- |
| `-a, --all`    |                | Show all containers (default shows just running)                  |
| `-f, --filter` |    _filter_    | Filter output based on conditions provided                        |
| `--format`     |    _string_    | Pretty-print containers using a Go template                       |
| `-n, --last`   |  _int_ / `-1`  | Show n last created containers (includes all states) (default -1) |
| `-l, --latest` |                | Show the latest created container (includes all states)           |
| `--no-trunc`   |                | Don't truncate output                                             |
| `-q, --quiet`  |                | Only display container IDs                                        |
| `-s, --size`   |                | Display total file sizes                                          |

### images

List images

```bash
docker images [OPTIONS] [REPOSITORY[:TAG]]
```

| options         | descripitons                                        |
| --------------- | --------------------------------------------------- |
| `--all , -a`    | Show all images (default hides intermediate images) |
| `--digests`     | Show digests                                        |
| `--filter , -f` | Filter output based on conditions provided          |
| `--format`      | Pretty-print images using a Go template             |
| `--no-trunc`    | Don't truncate output                               |
| `--quiet , -q`  | Only show image IDs                                 |

### pull

Скачать образ локально:

```bash
docker pull IMAGE 
```

### run

Создать и запустить контейнер из образа:

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

| options             |        type / default        | descripitons                                         |
| ------------------- | :--------------------------: | ---------------------------------------------------- |
| `-it [-i -t]`       |                              | interactive terminal не завершать процесс контейнера |
| `-d`                |                              | в фоновом режиме                                     |
| `--name`            |           _string_           | свое имя контейнера                                  |
| `-p`                |           _8080:80_          | проброс портов 8080 — внешний, 80 — внутренний       |
| `-v`                | ${PWD}:/usr/share/nginx/html | проброс томов                                        |
| `--rm`              |                              | удалять остановленный контейнер                      |
| `CONTAINER COMMAND` |                              | команда или файл который надо запустить в контейнере |

### rm

Уделить контейнер

```bash
docker rm CONTAINER
```

### rmi

Удалить образ

```bash
docker rmi IMAGE
```

### container prune

Удалить все остановленые контейнеры

```bash
docker container prune
```

### container inspect

Детали контейнера

```bash
docker container inspect CONTAINER | grap IpAddress (фильтровать вывод)
```

### stop

Stop one or more running containers

```bash
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

### kill

Kill one or more running containers

```bash
docker kill [OPTIONS] CONTAINER [CONTAINER...]
```

### exec

Run a command in a running container

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

| options             | type \| default | descripitons                                        |
| ------------------- | --------------- | --------------------------------------------------- |
| `-d, --detach`      |                 | Detached mode: run command in the background        |
| `--detach-keys`     | _string_        | Override the key sequence for detaching a container |
| `-e, --env`         | _list_          | Set environment variables                           |
| `--env-file`        | _list_          | Read in a file of environment variables             |
| `-i, --interactive` |                 | Keep STDIN open even if not attached                |
| `--privileged`      |                 | Give extended privileges to the command             |
| `-t, --tty`         |                 | Allocate a pseudo-TTY                               |
| `-u, --user`        | _string_        | Username or UID (format: \<name                     |
| `-w, --workdir`     | _string_        | Working directory inside the container              |

_добавить процесс в запущенный контейнер_

```bash
docker exec -it CONTAINER bash 
```

### logs

Вывести логи контейнера

```bash
docker logs CONTAINER
```

### diff

Измененные файлы

```bash
docker diff CONTAINER
```

### commit

Создать образ из контейнера

```bash
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

### push

Отправить образ в свой реестр

```bash
docker push IMAGE
```

### history

docker history

```bash
docker history IMAGE
```

> / — в конце каждой строки, многострочная команда
