---
created: {{date}}
type: dashboard
---

# 📦 Архив - Archives

> Архив содержит завершенные проекты и неактуальные материалы.

## 📁 Архивированные проекты

```dataview
TABLE 
  completed_date as "Завершен",
  duration as "Длительность",
  outcome as "Результат"
FROM "Archives/Projects"
SORT completed_date DESC
```

## 📚 Архивированные ресурсы

```dataview
TABLE 
  category as "Категория",
  archived_date as "Архивирован",
  archive_reason as "Причина"
FROM "Archives/Resources"
SORT archived_date DESC
```

## 🎯 Неактивные области

```dataview
TABLE 
  archived_date as "Архивирован",
  archive_reason as "Причина"
FROM "Archives/Areas"
SORT archived_date DESC
```

## 📊 Статистика архива

```dataview
TABLE WITHOUT ID
  type as "Тип",
  length(rows) as "Количество"
FROM "Archives"
WHERE type
GROUP BY type
```

## 🔍 Поиск в архиве

Используйте глобальный поиск Obsidian для поиска по архиву.

---

[← Назад к Dashboard](../Dashboard.md)
