<%* 
let spaceName = await tp.system.prompt("What do you want to call this space?")
let spaceCompany = await tp.system.prompt("Is this space related to a particular company?", "Acme Corp")
let spaceSummary = await tp.system.prompt("Do you want to provide a summary of the space?")
let spaceTag = await tp.system.prompt("Would you like to create a tag for this space?")
titleName = spaceName
await tp.file.rename(titleName); 
await tp.file.move("Spaces/" + titleName);
await this.app.vault.createFolder("Spaces/" + spaceTag)
-%>
---
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
company: <% await spaceCompany %>
type: space
tags: space, <% tp.file.creation_date("YYYY-MM") %>, <% await spaceTag %>,
summary: <% await spaceSummary %>
aliases: 
---

# <% await titleName %>

***Don't forget to add your new space to the [[Space Note]] template***!

## Ideas To Explore

- [ ] 

## Questions

- [ ] 

### Questions from Notes in this Space

```dataview
TASK
FROM #<% await spaceTag %> AND #question 
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

### To-Dos from Notes in this Space

```tasks
not done
tag includes #<% await spaceTag %> 
path includes <% await spaceTag %>
sort by due asc
```

### To-Dos from Notes Outside this Space

```tasks
not done
tag includes #<% await spaceTag %>
path does not include <% await spaceTag %>
sort by due asc
group by filename
```

## Related Notes

```dataview
TABLE 
  summary as "Summary"
FROM #note AND #<% await spaceTag %> AND -"Extras/Templates"
SORT file.ctime desc
LIMIT 20
```
