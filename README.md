# Телеграм-бот для пополнения баланса пользователя.

- Телеграмм бот API - aiogram;
- База данных - MySQL;
- ORM система - peewee;
- Логирование - logger.

### Настройка и запуск бота:

- Клонировать репозиторий:
````shell
$ git clone https://github.com/SpeshialS/Diplom_EDS
````
- Из корневой папки проекта установить зависимости:
````shell
$ pip install -r requirements.txt
````
- Переименовать файл `.env.template` в `.env` и добавить в него соответствующие параметры.

- Получить ключ API бота:

Переходим в Telegram и пишем тут BotFather’у команду /newbot. Вводим имя нового бота. Важно, чтобы оно заканчивалось словом Bot.

Получаем ключ и записываем его `.env`.

Бот настроен на тестовую демонстрация взаимодействия со встроенной платёжной системой Telegram `PayMaster`.

- Подключение PayMasterTest к боту:

Возвращаемся к BotFather’у, даем команду /mybots и выбираем из списка своего бота.

В открывшемся меню кликаем на кнопку «Payments». Из предоставленного списка выбираем нужный платежный шлюз. В качестве теста используем PayMaster. Выбираем «PayMaster Test».

Следуем простым инструкциям бота платежной системы и получаем тестовый токен PayMaster. Его сразу же можно сохранить в `.env`.

- Запуск бота осуществляется запуском скрипта `main.py` из корня проекта:
```shell
$ python main.py
```

### Работа бота:

После запуска бота, доступно две команды:

- /admin - взаимодействие с админ панелью.
Админу доступно выгружать логи приложения, список пользователей, а также изменять баланс и блокировать пользователей.

- /start - тестовое пополнение баланса. Доступно любому не заблокированному пользователю.