# fast_api

Подсказка по Fast Api
http://localhost:8000/docs

### Lesson 1-3
- методы get, post (передача парамс, боди, пути)
- pydantic

### Lesson 4
- Инит alembic и его настройка
```
alembic init migrations # инициировать алембик
```
[alembic.ini](Lesson%204%2Falembic.ini) (строка 64) 
`sqlalchemy.url = postgresql://%(DB_USER)s:%(DB_PASS)s@%(DB_HOST)s:%(DB_PORT)s/%(DB_NAME)s`

[migrations/env.py](Lesson%204%2Fmigrations%2Fenv.py) (строки 12+):
```
section = config.config_ini_section
config.set_section_option(section, "DB_HOST", DB_HOST)
config.set_section_option(section, "DB_PORT", DB_PORT)
config.set_section_option(section, "DB_USER", DB_USER)
config.set_section_option(section, "DB_NAME", DB_NAME)
config.set_section_option(section, "DB_PASS", DB_PASS)
```
[migrations/env.py](Lesson%204%2Fmigrations%2Fenv.py) (строка 32):
```
target_metadata = metadata
```
- Применение миграций
```
# Ревизия алембика:
alembic revision --autogenerate -m "Database creation"

# Применить миграцию
alembic upgrade ID_REVISION
```
