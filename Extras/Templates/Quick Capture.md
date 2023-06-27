<%* 
let noteName = await tp.system.prompt("What do you want to call this note?")
let noteSummary = await tp.system.prompt("Do you want to provide a summary of the note?")
titleName = noteName
await tp.file.rename(titleName);
-%>
---
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
company: 
type: note
tags: note, <% tp.file.creation_date("YYYY-MM") %>,
summary: <% await noteSummary %>
aliases: 
---

# <% await titleName %>
