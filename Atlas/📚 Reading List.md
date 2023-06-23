---
id: 📚-Reading-List
up: [[🏡 Home]]
created_date: 23/06/2023
updated_date: 23/06/2023
type: reading-list
tags: reading-list,
summary: A list of books to read and previously read
aliases: 
---

# 📚 Reading List

```dataview
TABLE WITHOUT ID
	file.link as "Book Title", 
	dateformat(planned_read_month, "MMMM yyyy") as "Planned Read Month"
FROM #source-note AND #toRead
WHERE contains(type, "book")
SORT default(planned_read_month, "") ASC, file.name ASC
```

## Books Previously Read

```dataview
TABLE WITHOUT ID
	file.link as "Book Title", 
	dateformat(read_finish_date, "MMMM yyyy") as "Finished Reading Month"
FROM #source-note AND #complete
WHERE contains(type, "book")
SORT default(read_finish_date, "") ASC, file.name ASC
```
