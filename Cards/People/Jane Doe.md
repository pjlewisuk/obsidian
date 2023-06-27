---
created_date: 2023-06-23 17:32
updated_date: 2023-06-23 17:32
type: people
tags: people, 2023-06,
birthday: 
anniversary: 
company: Acme Corp
job_title: CEO
team: C-suite
location: 
home_location: 
date_met: 2023-06-23
summary: 
aliases: Jane, jane
---

# Jane Doe

[ ](#anki-card)

## 👤 About

**How did we meet**? 
**When did we meet**? 2023-06-23

### 👨‍👩‍👦 Related People

- [[John Doe]]

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

## 🗨️Topics to Discuss with Jane

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
> 	contains(text, "[[Jane Doe")
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
> 	contains(text, "[[Jane Doe")
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
> 	contains(text, "[[Jane Doe")
> GROUP BY file.link
> SORT file.name ASC
> ```

## 👥 Meetings with Jane

```dataview
TABLE type as "Meeting Type", file.cday as "Meeting Date", summary AS "Summary"
FROM #note OR #interview OR #meeting OR #1-1-meeting OR #all-hands OR #stand-up OR #training
WHERE contains(file.outlinks, [[Jane Doe]])
SORT file.cday DESC
```
