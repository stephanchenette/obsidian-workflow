---
date: <% tp.date.now("YYYY-MM-DD") %>
type: meeting
company: 
summary: ""
tags:
  - inbox
attendees:
---
<%* 
let title = tp.file.title 
if (title.startsWith("Untitled")) { 
	prompt = await tp.system.prompt("Title"); 
} 

title = tp.date.now("YYYYMMDD") + "-Meeting-" + prompt
await tp.file.move("/Daily/" +  title) 
-%>
## <% prompt %>

##  Pre-Meeting Notes

##  Notes


## Next Actions
- [ ]