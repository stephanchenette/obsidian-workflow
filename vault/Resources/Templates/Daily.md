<%"---"%>
date: <% tp.date.now("YYYY-MM-DD") %>
type: daily
tags:
  - daily
<%"---"%>

<%* 
let title = tp.file.title 
title = tp.date.now("YYYYMMDD") + "-Daily"
await tp.file.move("/Daily/" +  title) 
-%>
<% tp.date.now("YYYY-MM-DD") %>


## Prep for Today


##  Notes 


##  Noted Tasks 
- [ ]

## Prep for Tomorrow


## ## [[Tasks Dashboard |Tasks]]

[!past due]- More than 30 days past due (on or past <% tp.date.now("YYYY-MM-DD", -30) %>)
<%"```tasks"%>
not done
is not recurring
due ON OR BEFORE <% tp.date.now("YYYY-MM-DD", -30) %> 
sort by priority
<%"```"%>

[!past due]- Less than 30 days past due (<% tp.date.now("YYYY-MM-DD", -30) %> - <% tp.date.now("YYYY-MM-DD", 0) %>)
<%"```tasks"%>
not done
is not recurring
due after <% tp.date.now("YYYY-MM-DD", -30) %> 
due before <% tp.date.now("YYYY-MM-DD", 0) %> 
sort by priority
<%"```"%>

[!today]- Due today <% tp.date.now("YYYY-MM-DD", 0) %>
<%"```tasks"%>
not done
is not recurring
due <% tp.date.now("YYYY-MM-DD", 0) %>
<%"```"%>

[!tomorrow]- Due tomorrow <% tp.date.now("YYYY-MM-DD", 1) %>
<%"```tasks"%>
not done
is not recurring
due <% tp.date.now("YYYY-MM-DD", 1) %>
<%"```"%>

[!coming-soon]- Due in the next two weeks (<% tp.date.now("YYYY-MM-DD", 0) %> - <% tp.date.now("YYYY-MM-DD", 14) %>)
<%"```tasks"%>
not done  
is not recurring
due AFTER <% tp.date.now("YYYY-MM-DD", 0) %>
due BEFORE <% tp.date.now("YYYY-MM-DD", 14) %>
sort by due
<%"```"%>

[!completed]- Completed today <% tp.date.now("YYYY-MM-DD", 0) %>

<%"```tasks"%>
done on <% tp.date.now("YYYY-MM-DD", 0) %>
is not recurring
sort by due
<%"```"%>