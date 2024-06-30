
## With Due Dates:
```dataview 
task from "Daily" 
where !completed and due and text != ""
group by due sort due asc
```
## With No Due Date:
```dataview 
task from "Daily" 
where !completed and !due and text != ""
group by due sort due asc
```
