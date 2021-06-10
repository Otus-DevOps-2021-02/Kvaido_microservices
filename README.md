# Kvaido_microservices
Kvaido microservices repository
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
