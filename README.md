# Kvaido_microservices
Kvaido microservices repository
------------------------
## Homework#15
1. Была создана ВМ на Yandex.Cloud с необходимыми параметрами.

2. Был создан docker-compose

3. Были созданы каталоги /srv/gitlab/config, /srv/gitlab/data, /srv/gitlab/logs и
   прописаны в docker-compose.

4. Был настроен Gitlab CI и создан pipeline.

5. В процессе изучения Gitlab CI был доработан и расщирен pipeline.

------------------------
## Homework#14

1. Были изучены сети docker: none, host, bridge.

2. Былз создан и описан docker-compose.

3. Был создан env файл.

4. Был создан docker-compose.override.yml и запускает команду puma с параметрами  --debug -w 2

------------------------
## Homework#13

1. Был установлен linter - hadolint.

2. Был скачен архив прилодения и созданы Dockerfile в каждом каталоге.

3. Были собраны образы и запущены контейнеры
   ```
   docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest
   docker run -d --network=reddit --network-alias=post kvaido/post:1.0
   docker run -d --network=reddit --network-alias=comment kvaido/comment:1.0
   docker run -d --network=reddit -p 9292:9292 kvaido/ui:1.0
   ```

4. Было выполнено задание со звездочкой. Запущены контейнеры с другими сетевыми алиасами.
   ```
   docker run -d --network=reddit --network-alias=my_post_db --network-alias=new_comment_db mongo:latest
   docker run -d --network=reddit --network-alias=post --env POST_DATABASE_HOST=new_post_db kvaido/post:1.0
   docker run -d --network=reddit --network-alias=comment --env COMMENT_DATABASE_HOST=new_comment_db kvaido/comment:1.0
   docker run -d --network=reddit -p 9292:9292 kvaido/ui:1.0
   ```

5. Было выполенено задание со звездочкой. Созданы облегченные образа на основе alpine linux.

6. Были запущены контейнеры с подключенным volume.
   ```
   docker volume create reddit_db
   ```

------------------------
## Homework#12

1. Был создан совой образ на базе ubuntu18.04.

2. С помощью docker-machine была запущена ВМ на Yandex.Cloud.

3. Был описан Dockerfile и на его основе создан docker образ.

4. Образ был залит на Docker Hub.

5. Новый docker обрал был развернут на Yandex.Cloud и локально.
