---
created_date: 2023-06-23
updated_date: 2023-06-23
type: home-page
tags: home
summary: Home page for my vault
---

Read the [[🧠 Vault Overview]] to understand how to make best use of this vault!

# 🏡 Home

- Open today's `="[[" + dateformat(date(today), "yyyy-MM-dd-cccc") + "|Daily Note ]]"`.  
- Open this week's `="[[" + dateformat(date(today), "yyyy-'w'WW") + "|Weekly Note ]]"`.  
- Open this month's `="[[" + dateformat(date(today), "yyyy-MM-MMMM") + "|Monthly Note ]]"`.  
- Open this quarter's Quarterly Note.  
- Open this year's Year Plan.  
- Open this year's [[IN-PROGRESS 2022-2023 Tax Return|Tax Return Note]].

## Inbox

Check the [[📬 Inbox]] to review and triage recent notes.

## Useful Lists

- A list of [[👥 Customers]] I'm currently working with
- Check the [[📝 Tasks]] list to keep on top of your tasks!
- Check the [[📰 Articles to read]] list for something to read when you have some free time. 
- Check the [[🎞️ Videos to watch]] list for something to watch.

## Spaces

Here are some areas of high importance in my life:

```dataview
LIST
FROM #space
SORT file.name asc
```

## Projects

Here are my active projects:

```dataview
LIST
FROM #project
SORT file.name asc
```

## Quick Links

- *Include links to notes you need to quickly reference here*

## Reading List

Here are the books I would like to read this month:

```dataview
TABLE read_start_date as "Start Date", read_finish_date as "Finish Date", summary as "Summary"
FROM #source-note
WHERE planned_read_month.month = date(now).month
SORT asc
```

Here's my [[📚 Reading List]].
