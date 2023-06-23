---
id: John-Doe
created_date: 23/06/2023 17:25
updated_date: 23/06/2023 17:25
type: people
tags: people, 2023-06,
birthday: 
anniversary: 
company: Acme Corp
job_title: CFO
team: C-suite
location: 
home_location: 
date_met: 2023-06-23
summary: 
aliases: John, john
---

# John Doe

[ ](#anki-card)

## 👤 About

**How did we meet**? 
**When did we meet**? 23/06/2023

### 👨‍👩‍👦 Related People

- [[Jane Doe]]

## ☎️ Contact Information

- **Email**: 
- **Phone**: 
- **Twitter**: 
- **LinkedIn**: 
- **Other**: 

## 📝 Notes

- Known for?
	- 

## 🔗 Links

- 

## 🗨️Topics to Discuss with John

> [!info]+ Discuss With...
> ```dataview
> TASK
> FROM #discussWith
> WHERE 
> 	!completed
> AND
> 	!contains(text, "#promisedTo")
> AND
> 	!contains(text, "#waitingFor")
> AND
> 	!contains(text, "#task")
> AND 
> 	text != ""
> AND
> 	contains(text, "[[John Doe")
> GROUP BY file.link
>SORT file.name ASC
> ```

> [!warning]+ Promised To...
> ```dataview
> TASK
> FROM #promisedTo
> WHERE
> 	!completed
> AND
> 	!contains(text, "#discussWith")
> AND
> 	!contains(text, "#waitingFor")
> AND
> 	!contains(text, "#task")
> AND 
> 	text != ""
> AND
> 	contains(text, "[[John Doe")
> GROUP BY file.link
> SORT file.name ASC
> ```

> [!notice]+ Waiting For...
> ```dataview
> TASK
> FROM #waitingFor
> WHERE 
> 	!completed
> AND
> 	!contains(text, "#discussWith")
> AND
> 	!contains(text, "#promisedTo")
> AND
> 	!contains(text, "#task")
> AND 
> 	contains(text, "[[John Doe")
> GROUP BY file.link
> SORT file.name ASC
> ```

## 👥 Meetings with John

```dataview
TABLE type as "Meeting Type", file.cday as "Meeting Date", summary AS "Summary"
FROM #note OR #interview OR #meeting OR #1-1-meeting OR #all-hands OR #stand-up OR #training
WHERE contains(file.outlinks, [[John Doe]])
SORT file.cday DESC
```
