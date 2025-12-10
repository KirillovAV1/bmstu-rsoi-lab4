# Лабораторная работа #4

## Deploy to Cloud

### Формулировка

На базе [Лабораторной работы #3](https://github.com/KirillovAV1/bmstu-rsoi-lab3) выполнен деплой приложения в managed
кластер k8s.

### Требования

1. Скопирован исходный код из ЛР #3 в проект.
2. Развернут Managed Kubernetes Cluster (Yandex Cloud), настроен Ingress Controller (для входящего трафика используется только Ingress).
3. Собраны и опубликованы образы docker в [Docker Registry](https://hub.docker.com/).
4. Описаны манифесты для деплоя в виде helm charts (универсальны для всех сервисов и отличаются лишь набором параметров запуска).
5. В кластере k8s используется один физический instance базы, но каждый сервис работает только со своей виртуальной базой данных. 
6. Для сборки используется Github Actions.
7. В [classroom.yml](.github/workflows/classroom.yml) дописаны шаги на:
    1. сборку приложения;
    2. сборку и публикацию образа docker (`docker compose build`, `docker compose push`);
    3. деплой каждого сервиса в кластер k8s.
