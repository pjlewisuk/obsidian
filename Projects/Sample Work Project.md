---
id: Sample Work Project
created_date: 23/06/2023 17:15
updated_date: 23/06/2023 17:15
company: Acme Corp
type: project
tags: project, 2023-06, sample-work-project,
summary: A sample project for the demo vault
aliases: 
---

# Sample Work Project

***Don't forget to add your new project to the [[Project Note]] template***!

## Ideas To Explore

- [ ] 

## Questions

- [ ] 

### Questions from Notes in Project

```dataview
TASK
FROM #sample-work-project AND #question AND -#task
WHERE 
	!completed
AND 
	text != ""
SORT file.name ASC
```

## To-Dos

- [ ] 

### To-Dos from Notes in this Project

```tasks
not done
tag includes #sample-work-project 
path includes sample-work-project
sort by due asc
```

### To-Dos from Notes Outside this Project

```tasks
not done
tag includes #sample-work-project
path does not include sample-work-project
sort by due asc
group by filename
```

## Related Notes

```dataview
TABLE 
  summary as "Summary"
FROM #note AND #sample-work-project AND -"Extras/Templates"
SORT file.ctime desc
LIMIT 20
```
