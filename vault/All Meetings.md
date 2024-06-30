
```dataview 
TABLE WITHOUT ID
link(file.name) as "Meeting",
date as "Date", 
topics as "Topics", 
summary as "Summary" 
from "Daily" where contains(type,"meeting") 
sort date desc
```







