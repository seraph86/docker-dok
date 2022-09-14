# Dockerfile

### example

```docker
FROM python:alpine (alpine минимальная версия)
MAINTAINER USER-NAME <info@mail.com> (информация об авторе)
WORKDIR /app (рабочая директория внутри образа)
RUN pip install pymongo (выполнить команду внутри образа)
COPY . . (копирует содержимое текущей папки в WORKDIR)
CMD ["python", "main.py"] (команда которая будет запущена после создания контейнера)
ENTRYPOINT ["cowsay"] (файл выполнить при запуске контейнера)
```

### build&#x20;

создать образ из текущей директории

```bash
docker build . 
```

| options | type/default   | description                                                         |
| ------- | -------------- | ------------------------------------------------------------------- |
| `-f`    | my-dockerfile  | если докерфайл назван по другому                                    |
| `-t`    | my-image:0.0.7 | задать свое имя и тег для образа. _**latest**_ (если тег не указан) |

Если повторить команду образ перезапишется