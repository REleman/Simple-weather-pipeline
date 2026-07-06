# Simple Weather ETL Pipeline 

ETL пайплайн для сбора данных о погоде из OpenWeatherMap API, трансформации и загрузки в PostgreSQL.
Проект выполнен в рамках портфолио.

## Архитектура
OpenWeatherMap API → Extract → Raw(json формат) → Transformation → Silver(parquet формат) → Load → Gold(PostgreSQL)

## Технологии
- Язык - python 3.9+
- Сбор данных - requests
- Работа с файлами и трансформация данных - pandas
- Хранение - JSON → Parquet 
- База данных - PostgreSQL + SQLAlchemy
- Логирование - Telegram и файловые логи

## Установка и запуск 
**Важно** Для работы нужен python версии 3.9 или выше 
1. Клонируйте репозиторий
```
git clone https://github.com/REleman/Simple-weather-pipeline.git
```
2. Установите зависимости
```
pip install -r requirements.txt
```
3. Создайте secrets.env файл в папке config/
- API_KEY=ваш_ключ_от_OpenWeatherMap
- TG_TOKEN=токен_Telegram_бота
- TG_CHAT_ID=ID_чата
- DB_NAME=weather_db
- DB_USER=postgres
- DB_HOST=localhost
- DB_PORT=5432
4. Запустите пайплайн
```
python ETL/Execute/execute.py
```
```
python ETL/Transform/transform.py
```
```
python ETL/Load/load.py
```

## Логирование 
Все события пишутся в файлы py_log_*.txt, а так же дублируются в Telegram

## Планы по развитию
**Реализовано:**
- Сбор данных из OpenWeatherMap API
- Трансформаця и нормализация 
- Загрузка в PostgreSQL

**Планируется:**
- Оркестрация через Apache Airflow
- Контейнеризация через Docker

**В перспективе:**
- Хранение сырых данных в S3 совместимом хранилище 
- Настройка и переработка мониторинга и алертинга через Telegram
- Добавление юнит тестов для модулей трансформации

## Автор 
[REleman](https://github.com/REleman)


