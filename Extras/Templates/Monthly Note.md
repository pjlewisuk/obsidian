<%* 
creationDate = tp.file.creation_date("YYYY-MM-DD")
creationTime = tp.file.creation_date("HHmm")
creationDay = tp.file.creation_date("dddd")
creationDateFolder = tp.file.creation_date("YYYY/")
creationWeek = tp.file.creation_date("WW")
titleName = tp.file.creation_date("YYYY-MM-MMMM")
await tp.file.rename(titleName); 
await tp.file.move("Calendar/" + creationDateFolder + "Monthly Notes/" + titleName);
-%>
---
id: <% tp.file.title.split(" ")[0] %>
up: [[<% tp.date.now("YYYY[ Year Plan]", " ", tp.file.title, "YYYY-MM-MMMM") %>]]
next: [[<% tp.date.now("YYYY-MM-MMMM", "P1M", tp.file.title, "YYYY-MM-MMMM") %>]]
prev: [[<% tp.date.now("YYYY-MM-MMMM", "P-1M", tp.file.title, "YYYY-MM-MMMM") %>]]
created_date: <% tp.file.creation_date('DD/MM/YYYY') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY') %>
type: monthly-note
tags: monthly-note, <% tp.file.creation_date("YYYY-MM") %>,
---

# 📅 {{date:MMMM}} [[{{date:YYYY[ Year Plan]}}|{{date:YYYY}}]]

## Links

- 

## Thoughts

- 

## People I Met This Month

```dataview
TABLE job_title as "Job Title", dateformat(date_met, "d LLL yyyy") as "Date Met"
FROM #people AND #{{date:YYYY-MM}} AND -"Extras/Templates"
WHERE date(date_met).month = this.file.cday.month
SORT date(date_met) ASC
```