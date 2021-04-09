# Проверка качества проектов 1С

## Структура каталогов
* В каталоге `projects` размещаются проверяемые проекты
* Исходные коды проекта следует размещать в каталоге `projects/<project_name>/src`
* Для каждого проекта в каталоге `projects/<project_name>/` размещается файл `scan.bat` для запуска сканера, а также файл `sonar-project.properties` с настройками сканирования проекта

## Подготовка
1. Перед запуском контейнеров необходимо в каталог `sonarqube/extensions/downloads` положить следующие плагины:
* [SonarQube 1C (BSL) Community Plugin](https://github.com/1c-syntax/sonar-bsl-plugin-community)
* [SonarQube Russian Language Pack](https://github.com/1c-syntax/sonar-l10n-ru) `опционально`
2. В каталог `sonar-scanner` распаковать дистрибутив [сканера](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/)

## Запуск:
* Контейнеры запускаются командой
```bash
docker-compose up -d
```
* После успешного запуска SonarQube должен стать доступен по адресу [http://localhost:9000](http://localhost:9000)
* В веб-интерфейсе следует сформировать [токен](https://docs.sonarqube.org/latest/user-guide/user-token/) и прописать его в файл `scan.bat`  для каждого проекта
* Заключительным шагом запускаем команду
```bash
scan.bat
```
