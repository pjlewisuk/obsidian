---
up: [[🏡 Home]]
created_date: 2023-06-23
updated_date: 2023-06-23
type: articles
tags: articles 
summary: List of articles to read when you have free time
aliases: 
---

# 📰 Articles to read

```dataview
TASK
FROM #toRead  
WHERE 
	!completed
AND
	!contains(text, "#discussWith")
AND
	!contains(text, "#promisedTo")
AND
	!contains(text, "#waitingFor")
AND
	!contains(text, "#toWatch")
AND
	!contains(text, "#task")
AND 
	text != ""
FLATTEN tags
GROUP BY tags
SORT tag ASC
```
