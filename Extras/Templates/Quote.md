<%* 
creationDate = tp.file.creation_date("YYYY-MM-DD")
let quoteName = await tp.system.prompt("What do you want to call this note?")
let quoteAuthor = await tp.system.prompt("Who is the original author or speaker?")
let quoteCompany = await tp.system.prompt("Is this note related to a particular company?", "Acme Corp")
let quoteSummary = await tp.system.prompt("Do you want to provide a summary of the note?")
titleName = await quoteName
authorName = await quoteAuthor
await tp.file.rename(titleName); 
await tp.file.move("Cards/Quotes/" + titleName);
-%>
---
id: <% await titleName %>
created_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
updated_date: <% tp.file.creation_date('DD/MM/YYYY HH:mm') %>
company: <% await quoteCompany %>
type: quote
tags: quote, <% tp.file.creation_date("YYYY-MM") %>,
author: <% await authorName %>
summary: <% await quoteSummary %>
aliases: 
---

# <% await titleName %>

> <% tp.file.cursor() %>
> 

\- *[[<% await authorName %>]]*
