---
date: {{date}}
type: daily
tags:
  - daily
---

{{date}}


## Prep for Today


##  Notes 


##  Noted Tasks 
- [ ]

## Prep for Tomorrow


## ## [[Tasks Dashboard |Tasks]]

[!past due]- More than 30 days past due (on or past {{thirty_days_past_date}})
```tasks
not done
is not recurring
due on or BEFORE {{thirty_days_past_date}} 
sort by priority
```

[!past due]- Less than 30 days past due ({{thirty_days_past_date}} - {{date}})
```tasks
not done
is not recurring
due after {{thirty_days_past_date}} 
due before {{date}} 
sort by priority
```

[!today]- Due today {{date}}
```tasks
not done
is not recurring
due {{date}}
```

[!tomorrow]- Due tomorrow {{date_plus_one}}
```tasks
not done
is not recurring
due {{date_plus_one}}
```

[!coming-soon]- Due in the next two weeks ({{date}} - {{fourteen_days_from_date}})
```tasks
not done  
is not recurring
due AFTER {{date}}
due BEFORE {{fourteen_days_from_date}}
sort by due
```

[!completed]- Completed today {{date}}

```tasks
done on {{date}}
is not recurring
sort by due
```