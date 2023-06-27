---
up: [[🏡 Home]]
created_date: 2023-06-23
updated_date: 2023-06-23
type: vault-overview
tags: vault-overview,
summary: An overview of how this vault is organised and how to use it
aliases: 
---

# 🧠 Vault Overview

## Organisation 

The vault has six top-level folders and a single top-level note:

- [[🏡 Home]] - the main homepage of the vault, with links to useful and commonly accessed notes
- **+ Encounters** - the landing zone for any new notes created that cannot be sorted immediately
- **Atlas** - some high-level notes that are useful for navigating the vault, e.g. finding videos to watch, articles or books to read, finding overdue or missed tasks, any new notes that need processing, customers I'm working with, etc.
- **Calendar** - all time-based notes live here, including daily, weekly, and monthly notes, as well as notes for meetings, 1:1 meetings, All Hands, and other encounters that occur at a specific time on a specific day
- **Cards** - all archived notes live in the **Cards/Everything Else** folder, while special types of notes live within their own sub-folders, including notes about companies or customers I interact with, definitions of things, people I meet, quotes I want to keep, and source materials I want to keep, such as books, articles, and videos
- **Extras** - attachments, images, and templates live in here, in their own respective sub-folders
- **Projects** - projects are on-going collections of tasks that I'm working on. They are similar to Spaces but are normally time-bound, and as such have a finite completion date
- **Spaces** - spaces are areas of my life that are generally long-running, and so may collect a lot of notes and resources over time

## How To Use The Vault

The vault makes use of the *Templater* community plugin to define a number of reusable templates to speed up everyday events, such as creating a [[Daily Note]]. These templates live in the **Extras/Templates** folder.

### Recurring Notes

The *Periodic Notes* and *Templater* plugins work together to quickly provide daily, weekly, monthly, quarterly, and yearly notes.

The daily notes and weekly notes can be created from the calendar view provided by the *Calendar* plugin. These notes are used to plan out my weeks and my days, and also to capture notes, information, resources, and tasks during my days. 

Other recurring notes can be created using macros that are configured using the *QuickAdd* plugin. By typing *Ctrl + P* and then *monthly*, I can create the relevant monthly note for the month I am currently in.

### Other Types of Notes

There are a number of other types of notes with associated templates, including: various types of meetings, companies/customers, definitions, general notes, people, quotes, source notes (books/videos/articles), spaces, and notes in spaces. These all have associated *QuickAdd* macros and can be used to create new notes by typing *Ctrl + P* followed by *quick* and the type of template you want to use (e.g. *meeting*, *1:1 meeting*, *company*, *person*, *definition*, *quote*, etc.)

## Projects

Projects are collections of tasks that share a common theme or goal (such as customer work, a demo, or a home improvement project) and have a finite completion date. As such, projects should be transient, and when they're complete, they should be archived. I tend to archive my completed projects in `Cards/Project Archives/`.

As with Spaces (see below), projects are created using the *QuickAdd* macro and the [[Project]] template (*Ctrl + P* followed by *quick project*), which will prompt for a few pieces of information, such as the Project name, a summary of the project, and a tag to use for other notes related to the project.

Once the Project has been created, you need to update the [[Project Note]] template to include the new Project and its associated tag, so that these are available in the drop-down list when you create notes in that space.

To create a note in a project, use the *QuickAdd* macro and the [[Project Note]] template (*Ctrl + P* follow by *quick note project*), which will prompt for further information.

## Spaces

Spaces are areas of my life that are important, and often long-running, so do not fit nearly into projects (which can always be finished). Spaces are created using the *QuickAdd* macro and the [[Space]] template (*Ctrl + P* followed by *quick space*), which will prompt for a few pieces of information, such as the Space name, a summary of what the Space is for, and a tag to use for other notes related to the Space.

Once the Space has been created, you need to update the [[Space Note]] template to include the new Space and associated tag, so that these are available in the drop-down lists when you create notes in that space.

To create a note in a space, use the *QuickAdd* macro and the [[Space Note]] template (*Ctrl +P* followed by *quick note space*), which will prompt for a few pieces of information, including the name of the note, a summary of the note, and the Space the note is related to.

## Meetings

There are a number of templates for specific types of meetings, including:

- [[Meeting|Meetings]] (*Ctrl + P*, *quick meeting*) - general purpose meetings, asks for information such as the name of the meeting, whether it was related to a particular company, and includes sections for the meeting attendees, agenda, questions, notes, and actions
- [[1-1 Meeting|1:1 Meetings]] (*Ctrl + P*, *quick 1 meeting*) - meetings with one other person, asks for the name of the person and whether the meeting is related to a paricular company, and includes sections to surface topics to #discussWith that person, you #promisedTo do for that person, or are #waitingFor that person to do for you
- [[All Hands]] (*Ctrl + P*, *quick all hands*) - meetings where there are a small number of presenters and a large number of attendees, asks for the name of the meeting, and includes sections for the presenters, agenda and questions, notes, and resources

## People and Companies

When I start working with a new customer, or encounter a company that I want to keep track of, I create a new *Company* note, using *Ctrl + P, quick company* shortcut, and then filling out the details that the template prompts for. 

When I meet new people I may create a new *Person* note to track some things about them, such as when and where we met, what they do, who they work for, etc. I create the note using *Ctrl + P, quick person*, and then filling filling out the details as prompted. The template attempts to capitalise first and last names, so you can type this in lowercase, but currently it doesn't work well with people with more than two names. In this case, create the note using the person's first and last name, and then add any additional information (titles, middle names, etc.) to the note afterwards.

In addition to keeping track of details about companies and people, these notes can be a useful way of finding other notes relating to those customers or people, as when you open the note you can quickly see all other notes that are *back-linked* to it.