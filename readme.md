# VK Data Fetcher with Neo4j Integration

Программа для сбора данных о пользователях ВКонтакте, их подписчиках и подписках с сохранением в графовую базу данных **Neo4j**.

---

## **Функционал**
- Сбор данных о пользователе, его подписчиках и подписках на указанную глубину.
- Запись данных в Neo4j:
  - Узлы: **User** (пользователи) и **Group** (группы).
  - Связи: **Follow** (подписчики) и **Subscribe** (подписки на группы).
- Выполнение предопределённых запросов на выборку данных.

---

## **Установка**

1. **Склонируйте этот репозиторий**:
   ```bash
   git clone https://github.com/your-repo/vk-neo4j-fetcher.git
   cd vk-neo4j-fetcher
   ```
2. Установите зависимости:
```
pip install -r requirements.txt
```
3. Настройте переменные окружения: Создайте файл .env в директории проекта со следующим содержимым:

```
SERV_VK_TOKEN=ваш_токен_доступа
VK_API_VERSION=
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=ваш_пароль
```

**Использование**

Соберите данные о пользователе и его подписках/подписчиках на определённую глубину:

```bash
python app.py --user_id <ID пользователя VK> --depth <глубина>
```
--user_id: ID пользователя VK (обязательный аргумент).
--depth: Глубина сбора данных (по умолчанию 2).