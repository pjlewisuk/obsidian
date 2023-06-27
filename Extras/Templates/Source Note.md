<%* 
let sourceName = await tp.system.prompt("What is the name of this source?")
let sourceType = await tp.system.suggester(["Book", "Video", "Podcast", "Article", "Other (please define)"], ["book", "video", "podcast", "article", "other"], false, "What type of source is this?")
let sourceTypeUpper = sourceType.split(" ")[0].charAt(0).toUpperCase() + sourceType.split(" ")[0].slice(1)
let sourceSummary = await tp.system.prompt("Do you want to provide a summary of this source?")
let sourceAuthor = await tp.system.prompt("Would you like to include an author?")
let sourceLink = await tp.system.prompt("Would you like to include a link for this source?")
titleName = sourceName
await tp.file.rename(titleName); 
await tp.file.move("Cards/Sources/" + titleName);
-%>
---
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
type: <% await sourceType %>
tags: source-note <% tp.file.creation_date("YYYY-MM") %>
<%*
if ( sourceType == "book" ) { -%>
planned_read_month: 
read_start_date: 
read_finish_date: 
<%* } -%>
summary: <% await sourceSummary %>
---

# <% await titleName %>

- **Title:** <% await sourceName %>
- **Source Type:** [[<% await sourceTypeUpper %>]]
- **Author:** [[<% await sourceAuthor %>]]
- **Domain(s):** 
- **Note Type:** [[Source Notes]]
- **Link:** [<% await sourceLink %>](<% await sourceLink %>)
- **Status:** <%* if ( ( sourceType == "book" ) || ( sourceType == "article" ) ) { %> #toRead <%* } else if ( sourceType == "video" ) { %> #toWatch <%* } else if ( sourceType == "podcast" ) { -%> #toListen <%* } %>
<%*
if ( sourceType == "book" ) { -%>
- **Publication Date:** 
- **Edition:** 
- **Pages:** 
- **Owned:** yes/no
- **Format:** [[Paperback]], [[eBook]], [[Audiobook]], [[Hardback]] (delete as appropriate)
<%* } -%>
- **Recommendation:** *Did someone recommend this to me?*
- **Motive:** *How did I come across this source? Why do I want to record it? Can I link this source to other sources, notes, or thoughts in my vault?*
- **Rediscovery:** *When might I like to rediscover this source? What topics might it be relevant to? Can I link this source to other notes in my vault?*
- **Date Created:** [[<% tp.file.creation_date("YYYY-MM-DD-dddd") %>]]

## 📝 Notes

- 

## ❓ Questions

- [ ] 

## 🔗 Related Links

- 
