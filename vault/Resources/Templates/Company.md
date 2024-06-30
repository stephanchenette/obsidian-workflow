---
location: 
website: 
aliases:
---
<%* 
let title = tp.file.title 
if (title.startsWith("Untitled")) { 
	prompt = await tp.system.prompt("Title"); 
} 

title = prompt
await tp.file.move("/Resources/Companies/" +  title) 
-%>
## Notes


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