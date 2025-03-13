
## Инструкция по запуску

### **1. Клонирование репозитория**
Сначала необходимо клонировать репозиторий на ваш локальный компьютер:
```sh
git clone https://github.com/Bustle101/pract_3.git
cd pract_3
```
### **2. Установка зависимостей**
Перед запуском установите все необходимые зависимости:
```sh
npm install
```

### **3. Запуск серверов**
Проект включает два сервера, которые необходимо запустить в **отдельных терминалах**:

#### Запуск сервера каталога (порт 3000)
```sh
node catalog-server/server.js
```

#### Запуск панели администратора (порт 8080)
```sh
node admin-server/server.js
```

### **4. Открытие в браузере**
После запуска серверов:
- Каталог товаров доступен по адресу: [http://localhost:3000](http://localhost:3000)
- Панель администратора (API) работает на: [http://localhost:8080](http://localhost:8080)

## Возможности (API-запросы) (при запуске 2х серверов)

### 🔹 1. Добавление товара 
```javascript
fetch('http://localhost:8080/desserts', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        name: "пончик",
        price: 200,
        description: "с посыпкой",
        categories: ["Десерты"]
    })
})
.then(res => res.json())
.then(data => console.log(data));

```

---
### 🔹 2. Изменение товара 
```javascript
fetch('http://localhost:8080/desserts/1', {
    method: 'PUT',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        price: 300,
        description: "с посыпкой и глазурью"
    })
})
.then(res => res.json())
.then(data => console.log(data));

```

---
### 🔹 3. Удаление товара 
```javascript
fetch('http://localhost:8080/desserts/1', {
    method: 'DELETE'
})
.then(res => res.json())
.then(data => console.log(data));

```
