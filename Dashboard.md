---
created: {{date}}
updated: {{date}}
type: dashboard
---

# 🏠 Dashboard - Главная панель

## 🎯 Активные проекты

```dataview
TABLE 
  status as "Статус",
  deadline as "Дедлайн",
  progress as "Прогресс"
FROM "Projects"
WHERE status != "Завершен" AND status != "Архив"
SORT deadline ASC
```

## 📊 Области ответственности

```dataview
TABLE 
  priority as "Приоритет",
  last_review as "Последний обзор"
FROM "Areas"
SORT priority DESC
```

## ✅ Задачи на сегодня

```dataview
TASK
FROM "Projects" OR "Areas" OR "Daily"
WHERE !completed AND contains(text, date(today))
```

## 📅 Недавние заметки

```dataview
TABLE 
  file.ctime as "Создано",
  file.mtime as "Изменено"
FROM ""
WHERE file.name != "Dashboard"
SORT file.mtime DESC
LIMIT 10
```

## 📈 Статистика

```dataview
TABLE WITHOUT ID
  length(rows) as "Количество"
GROUP BY type
WHERE type
SORT length(rows) DESC
```

## 🔗 Быстрые ссылки

- [[Projects/Projects Dashboard|📁 Все проекты]]
- [[Areas/Areas Dashboard|🎯 Все области]]
- [[Resources/Resources Dashboard|📚 Все ресурсы]]
- [[Archives/Archives Dashboard|📦 Архив]]
- [[Daily/{{date:YYYY-MM-DD}}|📝 Сегодняшняя заметка]]

---

*Последнее обновление: {{date:YYYY-MM-DD HH:mm}}*
