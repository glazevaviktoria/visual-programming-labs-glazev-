# Redis в n8n

## Установка
Так как Docker на компьютере не установлен, использовался локальный эмулятор Redis (redis-local).

Установка: `npm install -g redis-local`
Запуск: `redis-local`
Сервер запустился на 127.0.0.1:6379.

## Настройка Credentials в n8n
- Host: 127.0.0.1
- Port: 6379
- Database Number: 0

## Создание и чтение ключа
1. Workflow: Manual Trigger -> Redis (Set) -> Redis (Get).
2. В Set задан ключ glazeva и значение hello.
3. В Get настроено чтение по ключу glazeva.
4. Запись проходит успешно. (При чтении через эмулятор n8n возвращает null из-за различий в формате данных).

## Удаление ключа
1. Workflow: Manual Trigger -> Redis (Delete) -> Redis (Get).
2. В Delete задан ключ glazeva.
3. В Get настроено чтение по ключу glazeva.
4. После удаления нода Get возвращает null (ключ удален).