---
company: 
location: 
title: 
email: 
cell phone: 
website: 
address: 
aliases: 
birthdate: 
date: <% tp.date.now("YYYY-MM-DD") %>
type: person
tags:
  - inbox
---
<%* 
let title = tp.file.title 
if (title.startsWith("Untitled")) { 
	prompt = await tp.system.prompt("Title"); 
} 

title = prompt
await tp.file.move("/Resources/People/" +  title) 
-%>
## <% prompt %>

## [OGAS Framework](https://notes.nicolevanderhoeven.com/OGAS%20framework)
- Occupation: 
- Goal: 
- Attitude:
- Stake: 

##  Notes

**When and how we met:**
**Nature of relationship to you (at the time of meeting):**
**Age:**
**Family members (w/ age):**
	**Wife/Husband:**
**Topics of importance to them:**
**Current or past jobs/roles:**
**Where they live:**

**Recommendations for the growth of personal relationship**:


## Repeated Reminders
* [ ] 🔁 

## Mentions
```dataviewjs
const currentPage = dv.current();

const pages = dv.pages()
	.filter(page => page.file.outlinks && page.file.outlinks.some(link => link.path === currentPage.file.path));

dv.table(["Mentions", "Created", "Summary"], 
    pages.map(page => [
        dv.fileLink(page.file.path),
        page.file.cday,
        page.summary
    ])
);
```
## Meetings
```dataviewjs
const currentPage = dv.current();

const pages = dv.pages()
    .where(page => page.type === "meeting")
	.filter(page => page.file.outlinks && page.file.outlinks.some(link => link.path === currentPage.file.path));

dv.table(["Meeting", "Created", "Summary"], 
    pages.map(page => [
        dv.fileLink(page.file.path),
        page.file.cday,
        page.summary
    ])
);
```