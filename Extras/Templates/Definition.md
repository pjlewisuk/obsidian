<%* 
let definitionName = await tp.system.prompt("What is the term you want to define?")
let definitionAliases = await tp.system.prompt("Are there are aliases for this term?")
titleName = definitionName
aliases = definitionAliases
await tp.file.rename(titleName);
await tp.file.move("Cards/Definitions/" + titleName);
await tp.frontmatter.type
-%>
---
created_date: <% tp.file.creation_date('YYYY-MM-DD') %>
updated_date: <% tp.file.creation_date('YYYY-MM-DD HH:mm') %>
company: Acme Corp
type: definition
tags: definition, <% tp.file.creation_date("YYYY-MM") %>,
summary: Definition of <% await titleName %>
aliases: <% await aliases %>
---

# <% await titleName %>

## Definition

> <% tp.file.cursor() %>

## Synonyms

- <% await aliases %>
