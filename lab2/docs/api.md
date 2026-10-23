# API Node-RED (Лабораторная 2)

## 1. GET /api/text
Возвращает простой текстовый ответ.
- **Пример запроса:** `http://localhost:1880/api/text`
- **Ответ:** `Привет! Это простой текстовый ответ из Node-RED. Студент: Глазева.`

## 2. GET /api/info
Возвращает JSON с данными.
- **Пример запроса:** `http://localhost:1880/api/info`
- **Ответ:** `{"student":"Глазева","lab":2,"status":"OK"}`

## 3. GET /api/items/:id
Возвращает информацию об элементе по ID. Поддерживает query-параметр `limit`.
- **Успешный запрос:** `http://localhost:1880/api/items/42?limit=5`
- **Ответ (200 OK):** `{"status":"success","itemId":42,"limit":5}`
- **Ошибка 400 (неверный ID):** `http://localhost:1880/api/items/abc`
- **Ответ (400 Bad Request):** `{"status":"error","message":"ID must be a number","code":400}`
- **Ошибка 404 (ID больше 100):** `http://localhost:1880/api/items/999`
- **Ответ (404 Not Found):** `{"status":"error","message":"Item not found","code":404}`