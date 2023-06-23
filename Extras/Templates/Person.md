<%* 
let personName = await tp.system.prompt("Person's Name")
let companyName = await tp.system.prompt("Company Name", "Acme Corp")
firstName = personName.split(" ")[0].charAt(0).toUpperCase() + personName.split(" ")[0].slice(1)
// lastName = personName.split(" ")[1].charAt(0).toUpperCase() + personName.split(" ")[1].slice(1)
// titleName = firstName + " " + lastName
await tp.file.rename(personName); 
await tp.file.move("Cards/People/" + personName); 
-%>
---
id: <% personName.split(" ")[0] %>-<% personName.split(" ")[1] %>
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
type: people
tags: people, <% tp.file.creation_date("YYYY-MM") %>,
birthday: 
anniversary: 
company: <% await companyName %>
job_title: 
team: 
location: 
home_location: 
date_met: <% tp.file.creation_date('YYYY-MM-DD') %>
summary: 
aliases: <% personName.split(" ")[0] %>, <% personName.split(" ")[0].toLowerCase() %>
---

# <% await personName %>

## 👤 About

**How did we meet**? 
**When did we meet**? <% tp.file.creation_date('DD/MM/YYYY') %>

### 👨‍👩‍👦 Related People

- 

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

## 🗨️Topics to Discuss with <% await firstName %>

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
> 	contains(text, "[[<% await personName %>")
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
> 	contains(text, "[[<% await personName %>")
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
> 	contains(text, "[[<% await personName %>")
> GROUP BY file.link
> SORT file.name ASC
> ```

## 👥 Meetings with <% firstName %>

```dataview
TABLE type as "Meeting Type", file.cday as "Meeting Date", summary AS "Summary"
FROM #note OR #interview OR #meeting OR #1-1-meeting OR #all-hands OR #stand-up OR #training
WHERE contains(file.outlinks, [[<% personName %>]])
SORT file.cday DESC
```
