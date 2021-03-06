# Постоянно и автоматически проверяйте наличие уязвимых зависимостей

### Объяснение в один абзац

Из-за простоты и скорости разработки большинство приложений Node.js в значительной степени зависят от большого количества сторонних модулей из npm или Yarn, обоих популярных реестров пакетов. Однако недостатком этого преимущества являются риски безопасности, связанные с включением неизвестных уязвимостей в ваше приложение, что является риском, признанным по его месту в списке важнейших угроз безопасности веб-приложения OWASP.

Существует ряд инструментов, помогающих идентифицировать сторонние пакеты в приложениях Node.js, которые были определены сообществом как уязвимые, чтобы снизить риск их внедрения в ваш проект. Они могут периодически использоваться из инструментов CLI или включаться как часть процесса сборки вашего приложения.

### Оглавление

- [NPM audit](#npm-audit)
- [Snyk](#snyk)
- [Greenkeeper](#greenkeeper)
- [Дополнительные ресурсы](#дополнительные-ресурсы)

### NPM audit

`npm audit` - это новый инструмент CLI, представленный в NPM@6.

Запуск `npm audit` выдаст отчет об уязвимостях безопасности с указанием имени уязвимого пакета, серьезности и описания уязвимости, пути и другой информации, а также, если доступно, команд для применения исправлений для устранения уязвимостей.

![npm audit example](../../assets/images/npm-audit.png)

🔗 [Читайте еще: NPM blog](https://docs.npmjs.com/getting-started/running-a-security-audit)

### Snyk

Snyk предлагает многофункциональный интерфейс командной строки, а также интеграцию с GitHub. Snyk идет дальше с этим и в дополнение к уведомлению об уязвимостях также автоматически создает новые запросы извлечения, исправляющие уязвимости, по мере выпуска исправлений для известных уязвимостей.

Многофункциональный веб-сайт Snyk также позволяет проводить специальную оценку зависимостей, когда предоставляется GitHub-репозиторий или URL-адрес модуля npm. Вы также можете искать пакеты npm, которые имеют уязвимости напрямую.

Пример вывода интеграции Synk GitHub с автоматически созданным пул-запросом:
![synk GitHub example](../../assets/images/snyk.png)

🔗 [Читайте еще: Snyk website](https://snyk.io/)

🔗 [Читайте еще: Synk online tool to check npm packages and GitHub modules](https://snyk.io/test)

### Greenkeeper

Greenkeeper - это сервис, который предлагает обновления зависимостей в режиме реального времени, которые обеспечивают безопасность приложения, всегда используя самые последние обновления и исправленные версии зависимостей.

Greenkeeper следит за зависимостями npm, указанными в файле `package.json` репозитория, и автоматически создает рабочую ветку с каждым обновлением зависимостей. Затем запускается пакет CI репозитория, чтобы выявить любые критические изменения для обновленной версии зависимости в приложении. Если CI завершается неудачно из-за обновления зависимостей, в хранилище, которое будет выставлено на аукцион, создается ясная и краткая проблема, в которой указаны текущие и обновленные версии пакета, а также информация и история изменений обновленной версии.

Пример вывода интеграции Greenkeeper GitHub с автоматически созданным запросом на извлечение:

![synk github example](../../assets/images/greenkeeper.png)
🔗 [Читайте еще: Greenkeeper website](https://greenkeeper.io/)

### Дополнительные ресурсы

🔗 [Rising Stack Blog: Node.js dependency risks](https://blog.risingstack.com/controlling-node-js-security-risk-npm-dependencies/)

🔗 [NodeSource Blog: Improving npm security](https://nodesource.com/blog/how-to-reduce-risk-and-improve-security-around-npm)
