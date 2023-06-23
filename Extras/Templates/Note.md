<%* 
let noteName = await tp.system.prompt("What do you want to call this note?")
let noteCompany = await tp.system.prompt("Is this note related to a particular company?", "Acme Corp")
let noteSummary = await tp.system.prompt("Do you want to provide a summary of the note?")
titleName = noteName
await tp.file.rename(titleName); 
await tp.file.move("Cards/Everything Else/" + titleName);
-%>
---
id: <% await titleName %>
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
company: <% await noteCompany %>
type: note
tags: note, <% tp.file.creation_date("YYYY-MM") %>,
summary: <% await noteSummary %>
aliases: 
---

# <% await titleName %>
