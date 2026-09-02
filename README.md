# Backend для приложения с объявлениями в Docker контейнере

## Документация по проекту

Для запуска проекта необходимо:
- Создание контейнера на оснвоании Dockerfile
```bash
docker build -t backend_app .
```
- На основании образа запускаем контейнер в фоновом режиме(-d), пробрасываем порты(-t), называем контейнер backend_app(--name)
```bash
docker run -d -t 8000:8000 --name backend_app backend_app
```
- Переходим в терминал контейнера
```bash
docker exec -it backend_app bash
```
- Создаем нового пользователя
```bash
python manage.py createsuperuser
```
- Переходим на http://localhost:8000/admin и создаем там для нового пользователя токен доступа 

- Заменяем токен в файле [requests-examples.http](requests-examples.http) и делаем запросы
- На странице http://localhost:8000/api/advertisements/ можно увидеть результаты этих запросов 