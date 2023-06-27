<%* 
creationWeek = tp.file.creation_date("YYYY-[W]WW")
creationMonth = tp.file.creation_date("YYYY-MM-MMMM")
creationDateFolder = tp.file.creation_date("YYYY/")
titleName = creationWeek
-%>
---
up: [[<% await creationMonth %>]]
next: [[<% moment(creationWeek,'YYYY-[W]WW').add(7,'days').format("YYYY-[W]WW") %>]]
prev: [[<% moment(creationWeek,'YYYY-[W]WW').add(-7,'days').format("YYYY-[W]WW") %>]]
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
type: weekly-note
tags:  weekly-note, <% tp.file.creation_date("YYYY-MM") %>,
summary: Weekly note for <% moment(tp.file.title, 'YYYY-[W]ww').format("[Week] ww, MMMM YYYY") %>
---

# {{date:[Week] ww}} 🪴 [[<% await creationMonth %>|{{date:MMM gggg}}]]

M [[{{monday:YYYY-MM-DD-dddd}}|{{monday:DD}}]] · T [[{{tuesday:YYYY-MM-DD-dddd}}|{{tuesday:DD}}]] · W [[{{wednesday:YYYY-MM-DD-dddd}}|{{wednesday:DD}}]] · T [[{{thursday:YYYY-MM-DD-dddd}}|{{thursday:DD}}]] · F [[{{friday:YYYY-MM-DD-dddd}}|{{friday:DD}}]] · S [[{{saturday:YYYY-MM-DD-dddd}}|{{saturday:DD}}]] · S [[{{sunday:YYYY-MM-DD-dddd}}|{{sunday:DD}}]] ^w{{date:ww}}

## This Week's Intentions

- What do you want to focus on this week?

^w{{date:ww}}i

## This Week's Tasks

- [ ] #task Add tasks that you need to repeat weekly to this list; *they will automatically bubble-up into your Daily notes too!* 🛫 {{monday:YYYY-MM-DD}} 📅 {{monday:YYYY-MM-DD}}
- [x] #task Another task that you've already completed :) ✅ {{monday:YYYY-MM-DD}}

^w{{date:ww}}twt

### Due This Week

> [!warning]+ Tasks Due This Week
> ```tasks
> not done
> due in this week
> sort by priority 
> hide due date
> hide backlink
> limit 10
> ```

^w{{date:ww}}tdtw

### Starting This Week

> [!notice]+ Tasks Starting This Week
> ```tasks
>not done
>sort by priority
>sort by due date
>tag does not include #someday 
>group by tags
>starts in this week
>limit 20
>```

^w{{date:ww}}tstw

### Completed This Week

> [!success]+ Tasks Completed This Week
> ```tasks 
> done in this week
> hide due date
> hide backlink
> ```

## Things To Read This Week

- [ ] 

^w{{date:ww}}tr

# 🗓️ Weekly Review

## [[{{monday:YYYY-MM-DD-dddd}}|{{monday:ddd Do MMM}}]]

### Tasks
![[{{monday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{monday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

## [[{{tuesday:YYYY-MM-DD-dddd}}|{{tuesday:ddd Do MMM}}]]

### Tasks
![[{{tuesday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{tuesday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

## [[{{wednesday:YYYY-MM-DD-dddd}}|{{wednesday:ddd Do MMM}}]]

### Tasks
![[{{wednesday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{wednesday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

## [[{{thursday:YYYY-MM-DD-dddd}}|{{thursday:ddd Do MMM}}]]

### Tasks
![[{{thursday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{thursday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

## [[{{friday:YYYY-MM-DD-dddd}}|{{friday:ddd Do MMM}}]]

### Tasks
![[{{friday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{friday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

## [[{{saturday:YYYY-MM-DD-dddd}}|{{saturday:ddd Do MMM}}]]

### Tasks
![[{{saturday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{saturday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

## [[{{sunday:YYYY-MM-DD-dddd}}|{{sunday:ddd Do MMM}}]]

### Tasks
![[{{sunday:YYYY-MM-DD-dddd}}#^w{{date:ww}}t]]

### Meetings
![[{{sunday:YYYY-MM-DD-dddd}}#^w{{date:ww}}m]]

