<%"---"%>
tags: daily_journal
creation date: <% tp.file.creation_date() %> 
modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
<%"---"%>

<%* 
let title = tp.file.title 
title = tp.date.now("YYYYMMDD") + "-Daily-Journal-Start"
await tp.file.move("/Daily/" +  title) 
-%>

<% tp.web.daily_quote() %>

# My intentions are...
-
-
-

# I am grateful for / today I get to...
-
-
-

# What would make today great?
-
-
-

# Daily Affirmations. I am...
-
-
-

