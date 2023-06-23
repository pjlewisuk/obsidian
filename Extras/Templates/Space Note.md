<%* 
let noteName = await tp.system.prompt("What do you want to call this note?")
let noteCompany = await tp.system.prompt("Is this note related to a particular company?", "Acme Corp")
let noteSummary = await tp.system.prompt("Do you want to provide a summary of the note?")
let noteSpace = await tp.system.suggester(["My Demo Space"], ["my-demo-space"], false, "Which space does this note belong to?")
titleName = noteName
await tp.file.rename(titleName); 
await tp.file.move("Spaces/" + noteSpace + "/" + titleName);
-%>
---
id: <% await titleName %>
up: [[<% await noteSpace %>]]
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
company: <% await noteCompany %>
type: note
tags: note, <% tp.file.creation_date("YYYY-MM") %>, <% await noteSpace %>
summary: <% await noteSummary %>
aliases: 
---

# <% await titleName %>

## Notes

-  

## Thoughts / Questions 

- [ ] 

## Useful Resources

- 
