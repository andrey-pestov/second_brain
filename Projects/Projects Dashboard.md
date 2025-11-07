---
created:
  "{ date }":
type: dashboard
---

# 📁 Проекты - Projects

> Проект - это серия задач с конкретной целью и дедлайном.

## 🎯 Активные проекты

```dataview
TABLE 
  status as "Статус",
  deadline as "Дедлайн",
  progress as "Прогресс (%)",
  priority as "Приоритет"
FROM "Projects"
WHERE status = "В работе"
SORT priority DESC, deadline ASC
```

## 🔜 Запланированные проекты

```dataview
TABLE 
  start_date as "Старт",
  deadline as "Дедлайн",
  priority as "Приоритет"
FROM "Projects"
WHERE status = "Запланирован"
SORT start_date ASC
```

## ✅ Недавно завершенные

```dataview
TABLE 
  completed_date as "Завершен",
  duration as "Длительность"
FROM "Projects"
WHERE status = "Завершен"
SORT completed_date DESC
LIMIT 5
```

## 📊 Статистика проектов

```dataview
TABLE WITHOUT ID
  status as "Статус",
  length(rows) as "Количество"
FROM "Projects"
GROUP BY status
```

## 🆕 Создать новый проект

[[Templates/Project Template|Использовать шаблон проекта]]

---

[← Назад к Dashboard](../Dashboard.md)
