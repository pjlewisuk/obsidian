---
up: [[🏡 Home]]
created_date: 2023-06-23
updated_date: 2023-06-23
type: customers
tags: customers,
summary: A map of customers I've worked with
aliases: 
---

# 👥 Customers

```dataview
LIST
FROM #company
WHERE contains(type, "company")
AND contains(customer, true)
AND contains(currently_active, true)
SORT file.name asc
```

## Past Customers

```dataview
LIST
FROM #company
WHERE contains(type, "company")
	AND contains(customer, true)
	AND contains(currently_active, false)
SORT file.name asc
```
