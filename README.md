# tmdb_api
Упражнение на чтение кода. Фильмы с TMDB

## tmdb_helpers.py

Вспомогательный скрипт, отвечающий за взаимодействие с Web API сервиса TMDB.

*Не запускается непосредственно пользователем, вызывается другими скриптами*

- Отправляет запросы на themoviedb.org
- Получает уникальный ключ для использования API
- Загружает JSON-ответы от сервисов

## search_in_db.py

Ищет информацию о фильме по ключевому слову из файла, заранее выгруженного на ПК. Возвращает все фильмы, в названиях которых встречается слово.

### Использование
```console
user@user:/mnt/tmdb_api$ python3 search_ond_db.py
Enter path to DataBase: ./MyFilmDB.json
Enter film to search for: Fight Club
```

## make_own_db.py

Выгружает на ПК файл под названием `MyFimDB.json`. В файле хранится бибилиотка с информацией о 1000 фильмов с сервиса.

### Использование

```console
user@user:/mnt/tmdb_api$ python3 make_own_db.py
Enter your api key v3: 
0.0 percent complete
...
100.0 percent complete
```

## own_db_helpers.py
Вспомогательный скрипт. Выгружает информацию о фильмах из указанного пути. Используется `search_in_db.py` и `find_similar.py`, чтобы выгружать из заранее скачанного файла информацию по фильмам.

*Не запускается напрямую пользователем*

## hello_api_TMDB.py
Отладочный скрипт. Проверяет работу `tmdb_helpers.py`, скачивая информацию о фильме под номером 215.
Нужен для ручной проверки правильности ключа доступа к сервису и работы скриптов.

*Не используется напрямую пользователем*

## find_similar.py

Ищет фильмы, похожие на запрошенный. Отбор происходит по схожести:
- Бюджета
- Жанра
- Языка оригинала
- Коллекции

Выводит лучшие 8 совпадений.

### Использование
```console
user@user:/mnt/tmdb_api$ python3 find_similar.py
Enter path to DataBase: ./MyFilmDB.json
Enter film to search for: Fight Club
```
