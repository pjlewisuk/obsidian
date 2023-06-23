<%* 
let CompanyName = await tp.system.prompt("Company Name", "Acme Corp")
let isCustomer = await tp.system.suggester(["Yes", "No"], ["true", "false"], false, "Is this company a customer?", "Yes")
titleName = CompanyName
let tagName = await CompanyName.toLowerCase()
await tp.file.rename(titleName); 
await tp.file.move("Cards/Companies/" + titleName); 
-%>
---
id: <% await titleName %>
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
type: company
tags: company, <% tp.file.creation_date('YYYY-MM') %>, <% await tagName %>,
customer: <% await isCustomer %>
<%*
if ( isCustomer == "true" ) { -%>
currently_active: true
<%* } -%>
summary: Information and notes about <% await CompanyName %>
aliases: <% titleName.toLowerCase() %>
---

# <% await titleName %>

<%*
if ( isCustomer == "true" ) { -%>
> *Quick overview of the customer, and what I'm working with them on.*
<%* } -%>

## 📝 Notes

- 

## 🔗 Links

- 

<%*
if ( isCustomer == "true" ) { -%>
## 🆘 Support Cases

- 

## 🚩 Important Opportunities & Milestones

- Opp
	- Milestone
<%* } -%>

## Tasks

> [!warning]+ Tasks Due Soon
>```tasks
>not done
>due this week
>tags include <% await tagName %>
>```

> [!danger]+ Overdue Tasks
>```tasks
>not done
>due before today
>tags include <% await tagName %>
>```

> [!info]+ Completed Tasks
>```tasks
> done
>tags include <% await tagName %>
>```

## 👥 People Working Here

```dataview
TABLE job_title AS "Job Title", team AS "Team"
FROM #people
WHERE contains(company, "<% await CompanyName %>")
```

## Related Notes

```dataview
TABLE 
  type as "Type", 
  summary AS "Summary"
FROM #note OR #interview OR #meeting OR #1-1-meeting OR #all-hands OR #stand-up OR #training
WHERE contains(company, "<% await CompanyName %>")
SORT file.mtime desc
LIMIT 25
```
