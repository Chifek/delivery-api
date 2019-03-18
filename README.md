

# Парсинг курс валют

Данные (курсы валют) взяты с ресурса: https://www.cbr.ru
и с ресурса: http://www.ecb.europa.eu/

### Как пользоваться

Для парсинга курс валют с ресурса: https://www.cbr.ru вам необходимо написать в консоле в корне проекта:

```
php bin/console app:get-info-cbr
```

После чего, обновленные данные будут записаны в БД.
Внимание! Предыдущие данные будут удалены.

Для конвертации курс валют вам необходимо отправить запрос на адрес /cbr/exchange в след.виде:

```
{
        "from": "KGS", // Эквивалент валюты
        "from_nominal": 1000, // Сумма выбранной валюты
        "to": "KZT" // Необходимая конвертируемая валюта
}
```

После чего, нажмите отправить и вам придет необходимая конвертируемая валюта.

Для парсинга курс валют с ресурса: http://www.ecb.europa.eu/ вам необходимо написать в консоле в корне проекта:

```
php bin/console app:get-info-eurofx
```

После чего, обновленные данные будут записаны в БД.
Внимание! Предыдущие данные будут удалены.

Для конвертации курс валют вам необходимо отправить запрос на адрес /cbr/exchange в след.виде:

```
{
        "from": "KGS", // Эквивалент валюты
        "from_nominal": 1000, // Сумма выбранной валюты
        "to": "KZT" // Необходимая конвертируемая валюта
}
```

После чего, нажмите отправить и вам придет необходимая конвертируемая валюта.

### Установка

Для установки проекта вам потребуется:

* Symfony 4.2
* PostgreSQL
* Composer
* Git

## Запуск тестов


### Юнит тесты

Для запуска Unit тестов запустите команду:

```
phpunit
```

## Настройка cron

Также вы можете настроить автоматическое обновление курса валют каждые 12 часов 

### Crontab

Для этого в терминале запустите след.команду:

```
crontab -e
```
И впешите следующие 2 строки в файл и сохраните:
```
0 */12 * * * /path/to/php7.0 /path/to/project/root/bin/console app:get-info-cbr
0 */12 * * * /path/to/php7.0 /path/to/project/root/bin/console app:get-info-eurofx
```

## Автор

 **Исмаилов Руслан** - *web developer* - [Chifek](https://github.com/Chifek)

