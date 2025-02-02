В этом репозитории находится пример приложения с тестами:

- [e2e тесты](e2e/example.spec.ts)
- [unit тесты](src/example.test.tsx)

Для запуска примеров необходимо установить [NodeJS](https://nodejs.org/en/download/) 16 или выше.

Как запустить:

```sh
# установить зависимости
npm ci

# запустить приложение
npm start
```

Как запустить e2e тесты:

```sh
# скачать браузеры
npx playwright install

# запустить тесты
npm run e2e
```

Как запустить модульные тесты:

```sh
npm test
```
## Задание по теме "Инфраструтура":
### 1. Настройте линтер для соответствия сообщений о коммитах формату conventional commits :heavy_check_mark:
* можете использовать любой готовый инструмент, например commitlint :heavy_check_mark:
### 2. Настройте автоматический запуск проверок в CI для пулл реквестов :heavy_check_mark:
* обязательно должны запускаться автотесты + опционально можете подключить линтер для кода :heavy_check_mark:
* проверки должны запускаться автоматом на каждый коммит в PR :heavy_check_mark:
* результат должен быть виден на странице PR в интерфейсе GitHub :heavy_check_mark:
* нужно настроить ограничение на мерж изменений, если проверки не прошли :heavy_check_mark:
### 3. Настройте релизный процесс
* релиз должен запускаться автоматически при появлении в git нового релизного тега. Считаем тег релизным, если он соответствует маске v<число> (например, v12) :heavy_check_mark:
* версия релиза должна соответствовать релизному тегу :heavy_check_mark:
* должен формироваться changelog по истории коммитов от предыдущего релизного тэга :heavy_check_mark:
* должна создаваться запись в реестре релизов — считаем, что это issue на GitHub с пометкой RELEASE.<br>
Там должна сохраняться вся важная информация: автор и дата релиза (можно взять из тэга), номер версии, changelog :heavy_check_mark:
* предусмотрите корректную работу скрипта при многократном запуске с тем же тэгом (должна обновляться информация в существующей записи реестра релизов, а не создаваться новая)
* должны запускаться проверки, аналогичные PR, а ссылка на результат должна добавляться в реестр релизов :heavy_check_mark:
* если проверки прошли, приложение должно выкладываться на gh-pages (можете использовать готовый инструмент, например, gh-pages), а запись об этом должна добавляться в реестр релизов :heavy_check_mark:
* после этого релизный issue можно автоматом закрывать
### 4. Автоматизацию можно настроить через GitHub Actions или другой бесплатный аналог :heavy_check_mark:
* секреты должны храниться защищенно :heavy_check_mark:

### Примечание
Отключил запрет мержа при пул-реквесте, т.к. неудобно было делать пуш тегов в ветку мастер. Если нужно проверяющему, я включу