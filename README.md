## Запуск

1. `docker-compose up`


## Адреса

1. Нестабильный сервис: http://localhost:6200
1. Нестабильный сервис через Envoy: http://localhost:8000/unstable_service/
1. Админ-панель Envoy: http://localhost:8001

## Пример команды для тестирования

```
siege -v -d 0.1 -c 1 -r 100 "http://localhost:8000/unstable_service/?response_time_bucket=0.1:70.0&response_time_bucket=0.2:29.0&response_time_bucket=5:1.0&response_code_bucket=200:99.0&response_code_bucket=500:1.0"
```

### Время ответа

1. 70%: 0.1 сек
2. 29%: 0.2 сек
4. 1%: 5 сек

### Коды ответа

1. 99%: 200
2. 1%: 500
