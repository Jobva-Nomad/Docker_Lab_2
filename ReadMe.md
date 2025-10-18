# Пояему мой образ лучше "наивной сборки":
## 1) Меньше итоговый размер, нежели у "наивного" подхода, так как удаляем временные файлы и инструменты сборки
## 2) Запуск не под root пользователем, что повышает уровень безопасности
## 3) Запуск в режиме Read-Only, что так же увеличивает безопасность
## 4) Использование переменных окружения, что является возможностью изменять поведение приложения без пересборки
## 5) Возможность автоотслеживания приложения
## 6) Умное кэширование: зависимости грузятся один раз, а код можно менять много раз без переустановки.



# Вывод истории

| IMAGE        |        CREATED | CREATED BY                                      | SIZE   |                COMMENT     |
|--------------| ---------------|------------------------------------------------ |--------|----------------------------|
| 89214c09f999 |   27 hours ago |  CMD ["gunicorn" "--bind" "0.0.0.0:8000" "--w…  | 0B     |    buildkit.dockerfile.v0  | 
| <missing>    |   27 hours ago |  USER appuser                                   | 0B     |   buildkit.dockerfile.v0   |  
| <missing>    |   27 hours ago |  LABEL org.lab.login=izverjobva org.lab.token…  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  ARG LAB_TOKEN=5c7845130741aa991f4ff545e356e9…  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  ARG LAB_LOGIN=izverjobva                       | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  HEALTHCHECK &{["CMD-SHELL" "python -c \"impo…  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  ENV ROCKET_SIZE=Small                          | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  ENV PORT=8000                                  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  RUN /bin/sh -c mkdir -p /tmp/app && chown -R…  | 307kB  |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  COPY app.py . # buildkit                       | 12.3kB |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  COPY /usr/local/bin/ /usr/local/bin/ # build…  | 24.6kB |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  COPY /usr/local/lib/python3.9/site-packages/…  | 10.8MB |    buildkit.dockerfile.v0  |  
| <missing>    |   27 hours ago |  RUN /bin/sh -c addgroup -S appuser && adduse…  | 41kB   |    buildkit.dockerfile.v0  |  
| <missing>    |   39 hours ago |  WORKDIR /app                                   | 8.19kB |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  CMD ["python3"]                                | 0B     |    buildkit.dockerfile.v0  |
| <missing>    |   7 days ago   |  RUN /bin/sh -c set -eux;  for src in idle3 p…  | 16.4kB |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  RUN /bin/sh -c set -eux;   apk add --no-cach…  | 48MB   |    buildkit.dockerfile.v0  | 
| <missing>    |   7 days ago   |  ENV PYTHON_SHA256=668391afabd5083faafa454375…  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  ENV PYTHON_VERSION=3.9.24                      | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  ENV GPG_KEY=E3FF2839C048B25C084DEBE9B26995E3…  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  RUN /bin/sh -c set -eux;  apk add --no-cache…  | 3.02MB |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  ENV LANG=C.UTF-8                               | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   7 days ago   |  ENV PATH=/usr/local/bin:/usr/local/sbin:/usr…  | 0B     |    buildkit.dockerfile.v0  |  
| <missing>    |   8 days ago   |  CMD ["/bin/sh"]                                | 0B     |    buildkit.dockerfile.v0  | 
| <missing>    |   8 days ago   |  ADD alpine-minirootfs-3.22.2-x86_64.tar.gz /…  | 8.99MB |    buildkit.dockerfile.v0  |  
