<%* 
creationDate = tp.file.creation_date("YYYY-MM-DD")
creationTime = tp.file.creation_date("HHmm")
creationDay = tp.file.creation_date("dddd")
creationDateFolder = tp.file.creation_date("YYYY/MM-MMMM/")
let MeetingName = await tp.system.prompt("Meeting Name")
let CompanyName = await tp.system.prompt("Company Name", "Acme Corp")
CompanyNameCapitalized = CompanyName.charAt(0).toUpperCase() + CompanyName.slice(1)
titleName = creationDate + "-" + creationTime + " " + MeetingName
await tp.file.rename(titleName);
await tp.file.move("Calendar/" + creationDateFolder + "/Meetings/" + titleName);
-%>
---
id: <% titleName %>
up: [[<% await CompanyNameCapitalized %>]]
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
type: meeting
tags: meeting, <% tp.file.creation_date("YYYY-MM") %>,
company: <% CompanyNameCapitalized %>
summary: 
---

**Date:** [[<% tp.file.creation_date("YYYY-MM-DD-dddd") %>]]

# <% await MeetingName %>

## Attendees

- 
- *You!*

## Agenda

- 

## Questions

- 

## Notes

- 

## Actions

- [ ] 

^actions