<%* 
creationDate = tp.file.creation_date("YYYY-MM-DD")
creationTime = tp.file.creation_date("HHmm")
creationDay = tp.file.creation_date("dddd")
creationDateFolder = tp.file.creation_date("YYYY/MM-MMMM/")
let personName = await tp.system.prompt("Who is the 1-1 meeting with?")
firstName = personName.split(" ")[0].charAt(0).toUpperCase() + personName.split(" ")[0].slice(1)
lastName = personName.split(" ")[1].charAt(0).toUpperCase() + personName.split(" ")[1].slice(1)
personNameCapitalized = firstName + " " + lastName
let CompanyName = await tp.system.prompt("Company Name", "")
CompanyNameCapitalized = CompanyName.charAt(0).toUpperCase() + CompanyName.slice(1)
titleName = creationDate +"-" + creationTime + " 1-1 with " + personNameCapitalized
await tp.file.rename(titleName); 
await tp.file.move("Calendar/" + creationDateFolder + "/Meetings/" + titleName);
-%>
---
up: [[<% CompanyNameCapitalized %>]]
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
type: 1-1 meeting
tags: 1-1-meeting, <% tp.file.creation_date("YYYY-MM") %>,
company: <% CompanyNameCapitalized %>
summary: 
---

**Date:** [[<% tp.file.creation_date("YYYY-MM-DD-dddd") %>]]

# <% await "1-1 with " + personNameCapitalized %>

## 👥 Attendees

- [[<% await personNameCapitalized %>]]
- _You!_

## 📋 Agenda/Questions

- 

## 🗨️Topics to Discuss with <% firstName %>

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

## 📝 Notes

- 

## ✅ Actions

- [ ] 

^actions