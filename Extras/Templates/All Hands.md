<%* 
creationDate = tp.file.creation_date("YYYY-MM-DD")
creationTime = tp.file.creation_date("HHmm")
creationDay = tp.file.creation_date("dddd")
creationDateFolder = tp.file.creation_date("YYYY/MM-MMMM/")
let MeetingName = await tp.system.prompt("Meeting Name")
let CompanyName = await tp.system.prompt("Company Name", "Acme Corp")
CompanyNameCapitalized = CompanyName.charAt(0).toUpperCase() + CompanyName.slice(1)
titleName = creationDate +"-" + creationTime + " " + MeetingName
await tp.file.rename(titleName);
await tp.file.move("Calendar/" + creationDateFolder + "/Meetings/" + titleName);
-%>
---
up: [[<% CompanyNameCapitalized %>]]
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
type: all-hands
tags: all-hands, <% tp.file.creation_date("YYYY-MM") %>,
company: <% CompanyNameCapitalized %>
summary: 
---

**Date:** [[<% tp.file.creation_date("YYYY-MM-DD-dddd") %>]]

# <% await MeetingName %>

## Presenters

- 

## Agenda/Questions

- 

## Notes

- 

## Resources

- 
