---
up: [[🏡 Home]]
created_date: 2023-06-23
updated_date: 2023-06-23
type: inbox
tags: inbox
summary: Inbox note to help process recent and stagnating notes
aliases: 
---

# 📬 Inbox

``` dataview
TABLE WITHOUT ID
  file.link as "Encounters and new notes",
  (date(today) - file.cday).day as "Days alive",
  file.tags as "Tags",
  file.summary as "Summary"

FROM "+ Encounters" and -#on/readme 

SORT file.cday asc

LIMIT 20
```

## Notes without Summaries

```dataview
TABLE WITHOUT ID 
  file.link as "Note without summary",
  file.folder as "Location", 
  file.tags as "Tags", 
  type as "Type of Note", 
  created_date as "Created", 
  updated_date as "Last Updated"
FROM -"Extras/Templates"
WHERE (!summary OR summary = "") 
  AND (file.name != "! Quick Capture") 
  AND !contains(tags, "people")
  AND !contains(tags, "recipe")
SORT file.ctime asc
LIMIT 20
```
