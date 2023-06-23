---
id: My Demo Space
created_date: 23/06/2023 16:58
updated_date: 23/06/2023 16:58
company: Acme Corp
type: space
tags: space, my-demo-space,
summary: A sample space for the demo vault
aliases: 
---

# My Demo Space

***Don't forget to add your new space to the [[Space Note]] template***!

## Ideas To Explore

- [ ] 

## Questions

- [ ] 

### Questions from Notes in this Space

```dataview
TASK
FROM #my-demo-space AND #question
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
tag includes #my-demo-space 
path includes my-demo-space
sort by due asc
```

### To-Dos from Notes Outside this Space

```tasks
not done
tag includes #my-demo-space
path does not include my-demo-space
sort by due asc
group by filename
```

## Related Notes

```dataview
TABLE 
  summary as "Summary"
FROM #note AND #my-demo-space AND -"Extras/Templates"
SORT file.ctime desc
LIMIT 20
```
