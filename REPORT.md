Результаты проверок команд
sqlite после docker compose down и повторного запуска счетчик сохранился - 2
Команды сохранение счетчика:
docker compose down
docker compose up -d --wait
curl localhost:8080/
Отключение redis. Получил 200, 503, 503. После восстановления счетчик остался 3,post дал 4
Команды отключение redis:
docker compose stop redis
curl -i localhost:8080/healthz
curl -i localhost:8080/readyz
curl -i -X POST localhost:8080/increment
Redis после пересоздания контейнеров счетчик сохранился - 3
Команды восстановления redis:
docker compose start redis
curl localhost:8080/
curl -X POST localhost:8080/increment
