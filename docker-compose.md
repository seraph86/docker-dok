---
description: docker-compose.yml
---

# Docker-compose

```yaml
version: "3"

services:
  app: 
    build: ./app
  mongo:
    image: mongo
```

### up

```bash
docker-compose up
```

| options   | description            |
| --------- | ---------------------- |
| `-d`      | в фоновом режиме       |
| `--build` | пересоздать все образы |

### down

остановить и удалить все контейнеры

```bash
docker-compose down
```
