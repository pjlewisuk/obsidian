# obsidian
Collection of Obsidian templates and other useful resources

This repository includes the "bare bones" of my day-to-day working Obsidian vault. You may want to use it as the basis for your own vault, or selectively pick some templates or other elements of the vault.

If you find any problems, or have any questions about the vault, please [raise an issue](https://github.com/pjlewisuk/obsidian/issues/new) on GitHub.

## Plugins

At a minimum, you will need to use the following plugins for this vault to work correctly. I tend to use many more than this, but wanted to keep the list of "required" plugins as small as possible

- **Calendar**
  - This gives a nice visual calendar to help create new daily and weekly notes, as well as navigate back to previous daily/weekly notes
  - I tend to keep this docked at the bottom of the life sidebar for quick access
  - You will need to ensure that *Show week number* is toggled on, so you can quickly view/create weekly notes from the sidebar
- **Dataview**
  - Probably the most important plugin in this list, the Dataview plugin generates all the "dynamic" views across notes in the vault, such as surfacing all actions from a given day, or finding videos to watch
  - None of my notes use `Dataviewjs`, so you can keep *Javascript Queries* and *Inline Javascript Queries* disabled
- **Periodic Notes**
  - This plugin is used to quickly create *Daily* and *Weekly* notes from a specified template
  - You will need to disable the core *Daily notes* plugin so that it doesn't conflict with this plugin
  - The plugin configuration I used is included with this vault, a summary of the configuration is [included below](#periodic-notes)
  - At this point, I mainly use Daily and Weekly notes, and only use Monthly notes occasionally. I'm also thinking about how I might want to use Quarterly and/or Yearly notes going forwards
- **QuickAdd**
  - I use this plugin to quickly create new notes based off templates, and to make sure notes are created in the right folder with the right filename format. After that, Templater takes care of processing the template
  - The configuration for this plugin is included with this vault, and a summary is [included below](#quickadd)
- **Tasks**
  - This plugin is useful for capturing and tracking to-dos across your vault; combined with Dataview you can easily surface tasks whenever you need, based on time, location, or context
  - I used a **Global Task Filter** of `#task` so that Tasks isn't looking through **all** my checklist items, which means I can also use them for non-task purposes
  - I have a **Global Query** set up to exlude my Templates folder, just so tasks from my templates don't show up: `path does not include Extras/Templates`
- **Templater**
  - This plugin is really useful for creating note templates, and having information automatically substituted in (such as the date and time), or prompting for information when you create the note
  - The configuration for this plugin is included with this vault, and a summary is [included below](#templater)

## Using The Vault

In my day-to-day use, I tend to keep a couple of notes open most of the time:

- 🏡 Home - this note provides a handy shortcut to many notes I access or refer to during the day, including my Daily and Weekly notes, as well as customers, projects, and spaces I'm currently working on
- Today's *Daily note* - this is where I note down what's happening during the day, and also where any meetings I attend will be recorded, and actions will bubble up to

Before you start to use the vault, I suggest you take a look through the [[🧠 Vault Overview]], as this runs through the different templates available, how to use them, and how to create notes using them.

## Plugin Configuration

This section simply highlights any configuration parameters I change as part of configuring my vault; if I don't mention a particular configuration parameter, just assume I'm using the default (or customise it to your taste).

### Periodic Notes

- Daily Notes
  - **Format**: YYYY/MM-MMMM/[Daily Notes]/YYYY-MM-DD-dddd
  - **Daily Note Template**: Extras/Templates/Daily Note.md
  - **Note Folder**: Calendar
- Weekly Notes
  - **Format**: YYYY/[Weekly Notes]/gggg-[W]ww
  - **Weekly Note Template**: Extras/Templates/Weekly Note.md
  - **Note Folder**: Calendar
- Monthly Notes
  - **Format**: YYYY/[Monthly Notes]/YYYY-MM-MMMM
  - **Monthly Note Template**: Extras/Templates/Monthly Note.md
  - **Note Folder**: Calendar

### QuickAdd

- Create new 1-1 Meeting
  - **Template Path**: Extras/Templates/1-1 Meeting.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new All Hands Meeting
  - **Template Path**: Extras/Templates/All Hands.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Company
  - **Template Path**: Extras/Templates/Company.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Definition
  - **Template Path**: Extras/Templates/Definition.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Meeting
  - **Template Path**: Extras/Templates/Meeting.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Monthly Note
  - **Template Path**: Extras/Templates/Monthly Note.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Note
  - **Template Path**: Extras/Templates/Note.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Note in Project
  - **Template Path**: Extras/Templates/Project Note.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Note in Space
  - **Template Path**: Extras/Templates/Space Note.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Person
  - **Template Path**: Extras/Templates/Person.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Project
  - **Template Path**: Extras/Templates/Project.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Quote
  - **Template Path**: Extras/Templates/Quote.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Source
  - **Template Path**: Extras/Templates/Source Note.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true
- Create new Space
  - **Template Path**: Extras/Templates/Space.md
  - **File Name Format**: true
  - **File Name**: {{date:YYYY-MM-DD-HHmmss}}
  - **Create in folder**: true
  - **Folder path**: + Encounters
  - **Open**: true
  - **Focus new pane**: true

### Templater

- **Template folder location**: Extras/Templates
- **Automatic jump to cursor**: true
- **Trigger Templater on new file creation**: true
- **Enable Folder Templates**:
  - **Folder**: + Encounters
    - **Template**: Extras/Templates/Quick Capture.md
