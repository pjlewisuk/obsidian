<%* 
let projectName = await tp.system.prompt("What do you want to call this project?")
let projectCompany = await tp.system.prompt("Is this project related to a particular company?", "Acme Corp")
let projectSummary = await tp.system.prompt("Do you want to provide a summary of the project?")
let projectTag = await tp.system.prompt("Would you like to create a tag for this project?")
titleName = projectName
await tp.file.rename(titleName); 
await tp.file.move("Projects/" + titleName);
await this.app.vault.createFolder("Projects/" + projectTag)
-%>
---
id: <% await titleName %>
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
company: <% await projectCompany %>
type: project
tags: project, <% tp.file.creation_date("YYYY-MM") %>, <% await projectTag %>,
summary: <% await projectSummary %>
aliases: 
---

# <% await titleName %>

***Don't forget to add your new project to the [[Project Note]] template***!

## Ideas To Explore

- [ ] 

## Questions

- [ ] 

### Questions from Notes in Project

```dataview
TASK
FROM #<% await projectTag %> AND #question 
WHERE 
	!completed
AND
    !contains(text, "#task")
AND 
	text != ""
SORT file.name ASC
```

## To-Dos

- [ ] 

### To-Dos from Notes in this Project

```tasks
not done
tag includes #<% await projectTag %> 
path includes <% await projectTag %>
sort by due asc
```

### To-Dos from Notes Outside this Project

```tasks
not done
tag includes #<% await projectTag %>
path does not include <% await projectTag %>
sort by due asc
group by filename
```

## Related Notes

```dataview
TABLE 
  summary as "Summary"
FROM #note AND #<% await projectTag %> AND -"Extras/Templates"
SORT file.ctime desc
LIMIT 20
```
