---
up: [[🏡 Home]]
created_date: 2023-06-23
updated_date: 2023-06-23
type: videos
tags: videos,
summary: List of videos to watch when you have some free time
aliases: 
---

# 🎞️ Videos to watch

```dataview
TASK
FROM #toWatch 
WHERE 
	!completed
AND
	!contains(text, "#discussWith")
AND
	!contains(text, "#promisedTo")
AND
	!contains(text, "#waitingFor")
AND
	!contains(text, "#toRead")
AND
	!contains(text, "#task")
AND 
	text != ""
FLATTEN tags
GROUP BY tags
SORT tag ASC
```
