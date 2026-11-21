Дз 3
Счетчик на питоне в докер Сначала сделал с sqlite, потом Redis
Запуск
cp .env.example .env
docker compse up -d --build
В .env можно поменять порт и приветствие
Проверка
curl localhost:8080/
curl -X POST localhost:8080/increment
curl localhost:8080/healthz
curl localhost:8080/readyz
Redis работает отдельно от приложения. Данные сохраняются в volume redis_data, поэтому после удаления
и повторного запуска контейнеровсчетчик не сбрасывается. Без редис счетчик становится недоступен

