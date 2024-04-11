[![Actions Status](https://github.com/ishchts/devops-for-programmers-project-74/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/ishchts/devops-for-programmers-project-74/actions) &nbsp; [![Actions Status](https://github.com/ishchts/devops-for-programmers-project-74/actions/workflows/push.yml/badge.svg)](https://github.com/ishchts/devops-for-programmers-project-74/actions)

# Упаковка в Docker Compose

Автоматизация развертывания и обновления локального окружения с помощью Docker Compose, Github Actions (CI), Makefile

## Требования

Для запуска этого приложения необходимы следующие компоненты:

- Docker Engine (версия 18.06.0 или выше)
- Docker Compose (версия 1.22.0 или выше)

## Инструкции

### Установка зависимостей

Для установки зависимостей выполните следующие шаги:

1. Установите Docker Engine и Docker Compose, если они еще не установлены. Инструкции можно найти на [официальном сайте Docker](https://docs.docker.com/get-docker/).

2. Если для запуска приложения требуются дополнительные зависимости, установите их с помощью инструкций, предоставленных разработчиком.

### Настройка приложения

Перед запуском приложения убедитесь, что вы выполнили все необходимые настройки. Это может включать в себя:

- Создание файлов конфигурации
- Установку переменных окружения
- Изменение параметров в файле конфигурации Docker Compose

### Запуск приложения

Для запуска приложения выполните следующие шаги:

1. Откройте терминал или командную строку.

2. Перейдите в корневую директорию проекта.

3. Выполните следующую команду для запуска приложения с использованием Docker Compose:

   ```
   make compose-start
   ```

   Или выполните следующие команды вручную:

   ```
   docker-compose up
   ```

4. Откройте браузер и перейдите по адресу [http://localhost:PORT](http://localhost:PORT), где PORT - порт, на котором запущено ваше приложение.

---

## Тестирование

Опишите здесь инструкции для тестирования приложения.

1. **Запуск тестов**:
   ```
   # Команда для запуска тестов в контейнере
   make compose-test
   ```

## Docker Образ

Если вы хостите ваш образ на Docker Hub или другом реестре, укажите ссылку или имя образа.

```
docker pull ishchts/devops-for-programmers-project-74
```

## Makefile

```
compose-start:
	docker-compose up

compose-test:
	docker-compose -f docker-compose.yml up --abort-on-container-exit --exit-code-from app

compose-build:
	docker-compose -f docker-compose.yml build app

compose-push:
	docker-compose -f docker-compose.yml push app
```



