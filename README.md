# GraphQL Users API

## Описание

Это приложение представляет собой сервер GraphQL, разработанный с использованием Node.js, Express и библиотеки express-graphql. Оно позволяет выполнять запросы к API для получения данных о пользователях и компаниях. В качестве источника данных используется json-server, который предоставляет данные в формате JSON.

### Структура проекта

- **server.js**: Основной файл сервера, который настраивает Express и маршрутизацию GraphQL.
- **schema.js**: Файл схемы GraphQL, где определены типы данных и корневые запросы.

### Модули и зависимости

В проекте используются следующие модули:

- **axios**: Для выполнения HTTP-запросов.
- **express**: Для создания веб-сервера.
- **express-graphql**: Middleware для интеграции GraphQL с Express.
- **graphql**: Основная библиотека GraphQL для определения схем и типов данных.
- **json-server**: Для создания фальшивого REST API, который используется как источник данных.
- **nodemon**: Инструмент для автоматической перезагрузки сервера при изменении файлов.

## Установка и запуск

### Шаг 1: Клонируйте репозиторий

```bash
git clone <URL вашего репозитория>
cd <название директории репозитория>
```

### Шаг 2: Установите зависимости

```bash
npm install
```

### Шаг 3: Запустите json-server

Создайте файл `db.json` с необходимыми данными и запустите json-server:

```bash
npm run json:server
```

### Шаг 4: Запустите сервер разработки

В отдельном терминале запустите сервер разработки:

```bash
npm run dev
```

### Шаг 5: Используйте GraphiQL

Перейдите в браузере по адресу [http://localhost:4000/graphql](http://localhost:4000/graphql), чтобы открыть GraphiQL и начать выполнять запросы к вашему GraphQL API.

Пример запроса для получения данных о пользователе:

```graphql
{
  user(id: "1") {
    id
    firstName
    age
    company {
      id
      name
      description
    }
  }
}
```