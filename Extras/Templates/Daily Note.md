<%* 
fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd');
let prevDay = moment(fileDate).subtract(1, 'd').format('YYYY-MM-DD-dddd');
let nextDay = moment(fileDate).add(1, 'd').format('YYYY-MM-DD-dddd');
let yearLink = fileDate.format('YYYY');
let quarterLink = fileDate.format('YYYY-[Q]Q');
let monthLink = fileDate.format('YYYY-MM-MMMM');
let weekLink = fileDate.format('gggg-[W]WW');
let fileTitle = fileDate.format('YYYY-MM-DD-dddd');
let creationDate = fileDate.format('YYYY-MM-DD');
let friendlyDate = fileDate.format('dddd Do MMMM, YYYY');
let dateFolder = fileDate.format("YYYY/MM-MMMM/");
let dayOfWeek = fileDate.format("dd");
titleName = fileTitle;
await tp.file.rename(titleName); 
await tp.file.move("Calendar/" + dateFolder + "Daily Notes/" + titleName);
-%>
---
id: <% await creationDate %>
up: [[<% await weekLink %>]]
next: [[<% await nextDay %>]]
prev: [[<% await prevDay %>]]
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
type: daily-note
tags: daily-note, <% await monthLink %>, <% await creationDate %>,
summary: Daily note for <% await friendlyDate %>
---

# <% await friendlyDate %>

[[<% await prevDay %>|<< <% moment(prevDay, 'YYYY-MM-DD-dddd').format('ddd Do MMM') %>]] | `<% await friendlyDate %>` | [[<% await nextDay %>|<% moment(nextDay, 'YYYY-MM-DD-dddd').format('ddd Do MMM') %> >>]]
[[<% await weekLink %>| W<% moment(weekLink,'gggg-[W]WW').format('WW') %> weekly note]] | [[<% await monthLink %>| <% moment(monthLink, 'YYYY-MM-MMMM').format('MMM YY') %> monthly note]] | [[<% await quarterLink %>| <% moment(quarterLink, 'YYYY-[Q]Q').format('[Q]Q') %> quarterly note]] 

## Birthdays & Anniversaries

```dataview
LIST FROM #people
WHERE (date(birthday).month = this.file.day.month AND date(birthday).day = this.file.day.day) OR (date(anniversary).month = this.file.day.month AND date(anniversary).day = this.file.day.day)
SORT file.ctime DESC
```

## This Week's Intentions

![[<% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('YYYY-[W]WW') + moment(tp.file.title, 'YYYY-MM-DD-dddd').format('[#^w]WW[i]') %>]]

## Tasks

### Today

> [!warning]+ Tasks Due Today
> ```tasks
> not done
> due <% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('YYYY-MM-DD') %>
> sort by priority 
> path does not include Extras/Templates
> hide due date
> hide backlink
> limit 5
> ```

> [!success]+ Tasks Done Today
> ```tasks 
> done <% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('YYYY-MM-DD') %>
> path does not include Extras/Templates
> hide due date
> hide backlink
> ```

> [!notice]+ Tasks Starting Today
> ```tasks
> not done
> has start date
> path does not include Extras/Templates
> starts <% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('YYYY-MM-DD') %>
> limit 5
> ```

### This Week

> [!warning]+ Tasks Due This Week
> ```tasks
> not done
> (due after <% moment(tp.file.title, 'YYYY-MM-DD-dddd').startOf('week').format('YYYY-MM-DD') %>) AND (due before <% moment(tp.file.title, 'YYYY-MM-DD-dddd').endOf('week').format('YYYY-MM-DD') %>) AND NOT (due today)
> sort by priority 
> path does not include Extras/Templates
> hide backlink
> limit 5
> ```

> [!notice]+ Tasks Starting This Week
> ```tasks
> not done
> sort by priority
> sort by due date
> path does not include Extras/Templates
> (starts after <% moment(tp.file.title, 'YYYY-MM-DD-dddd').startOf('week').format('YYYY-MM-DD') %>) AND (starts before <% moment(tp.file.title, 'YYYY-MM-DD-dddd').endOf('week').format('YYYY-MM-DD') %>) AND NOT (due today)
> limit 10
>```

### This Week's Tasks

> [!info]+ This Week's Tasks
> ```tasks
> not done
> sort by due date
> group by due
> path includes <% await weekLink %>
> ```

## Links

- 

## Notes

- <% tp.file.cursor() %>

## Tasks

- [ ] 

^w<% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('WW') %>t

## Meetings / Calls

```dataview
LIST
FROM (#meeting OR #1-1-meeting OR #all-hands OR #team-meeting OR #stand-up OR #training) AND -"Extras/Templates"
WHERE file.cday = this.file.day
SORT file.name ASC
```
^w<% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('WW') %>m

## Today's Actions From Meetings

```dataview
TASK
FROM #interview OR #meeting OR #1-1-meeting OR #all-hands OR #stand-up OR #training
WHERE file.cday = this.file.day AND !completed AND text != ""
SORT file.ctime DESC
```

## Today's Activities

```dataview
TABLE type as "Note Type", summary as "Summary"
FROM -"Extras/Templates"
WHERE file.cday = this.file.day
SORT file.cday DESC
```
^w<% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('WW') %>a

### Notes Updated Today

```dataview
TABLE type as "Note Type", summary as "Summary"
WHERE file.mday = this.file.day
SORT file.mtime asc

```
^w<% moment(tp.file.title, 'YYYY-MM-DD-dddd').format('WW') %>u
