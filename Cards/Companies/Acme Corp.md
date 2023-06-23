---
id: Acme Corp
created_date: 23/06/2023 17:27
updated_date: 23/06/2023 17:27
type: company
tags: company, 2023-06, acme corp,
customer: false
summary: Information and notes about Acme Corp
aliases: acme corp
---

# Acme Corp


## 📝 Notes

- 

## 🔗 Links

- 


## Tasks

> [!warning]+ Tasks Due Soon
>```tasks
>not done
>due this week
>tags include acme corp
>```

> [!danger]+ Overdue Tasks
>```tasks
>not done
>due before today
>tags include acme corp
>```

> [!info]+ Completed Tasks
>```tasks
> done
>tags include acme corp
>```

## 👥 People Working Here

```dataview
TABLE job_title AS "Job Title", team AS "Team"
FROM #people
WHERE contains(company, "Acme Corp")
```

## Related Notes

```dataview
TABLE 
  type as "Type", 
  summary AS "Summary"
FROM #note OR #interview OR #meeting OR #1-1-meeting OR #all-hands OR #stand-up OR #training
WHERE contains(company, "Acme Corp")
SORT file.mtime desc
LIMIT 25
```
