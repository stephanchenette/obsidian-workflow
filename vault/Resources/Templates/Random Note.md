---
date: ""
type: note
company: 
summary: ""
tags:
  - inbox
people:
---
<%* 
let title = tp.file.title 
if (title.startsWith("Untitled")) { 
	prompt = await tp.system.prompt("Title"); 
} 

title = tp.date.now("YYYYMMDD") + "-Note-" + prompt
await tp.file.move("/Daily/" +  title) 
-%>
## <% prompt %>

##  Notes


## Next Actions
- [ ]