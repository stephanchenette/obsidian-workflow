<%* 
let title = tp.file.title 
title = tp.date.now("YYYYMMDD") + "-Daily-Journal-End"
await tp.file.move("/Daily/" +  title) 
-%>

<%"---"%>
tags: daily_journal
creation date: <% tp.file.creation_date() %> 
modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %> 
<%"---"%>

<% tp.web.daily_quote() %>

# Three amazing things that happened today...
-
-
-

# How could I have made today better?
-
-
-

