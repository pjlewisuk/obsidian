<%* 
let noteName = await tp.system.prompt("What do you want to call this note?")
let noteCompany = await tp.system.prompt("Is this note related to a particular company?", "Acme Corp")
let noteSummary = await tp.system.prompt("Do you want to provide a summary of the note?")
let noteProject = await tp.system.suggester(["Sample Work Project"], ["sample-work-project"], false, "Which project does this note belong to?")
titleName = noteName
await tp.file.rename(titleName); 
await tp.file.move("Projects/" + noteProject + "/" + titleName);
-%>
---
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
company: <% await noteCompany %>
type: note
tags: note, <% tp.file.creation_date("YYYY-MM") %>, <% await noteProject %>,
summary: <% await noteSummary %>
aliases: 
---

# <% await titleName %>

## Notes

- [ ] 

## Thoughts / Questions 

- [ ] 

## Useful Resources

- 

## Related Notes

```dataview
LIST
FROM #note AND #<% await noteProject %>
SORT file.ctime asc
```
