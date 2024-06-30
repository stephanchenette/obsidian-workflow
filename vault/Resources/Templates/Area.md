---
date: <% tp.date.now("YYYY-MM-DD") %>
type: area
tags:
---
<%* 
let title = tp.file.title 
if (title.startsWith("Untitled")) { 
	prompt = await tp.system.prompt("Title"); 
} 

title = prompt
await tp.file.move("/Areas/" +  title) 
-%>
## <% prompt %>

# Main
- **Goal:**
- **Strategy to learn:**
- **Stake:**
- **Current state:**
- **Next big test/milestone to put into practice:**

##  Notes


## References


## Mentions
```dataview 
table WITHOUT ID
file.inlinks as "Reference(s)", 
file.inlinks.type as "Type",
file.inlinks.file.cday as Created, file.inlinks.summary AS "Summary" 
where file.name = this.file.name
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