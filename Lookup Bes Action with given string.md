# BigFix Action Search Example

This example retrieves actions that have a specific signature within the relevance or action script. Here, the query looks for actions that contain `"notify client ForceRefresh"` within the action script. You can adapt this to look for any type of action script signature you choose.

---

## Query:

```bigfix
table "border=1" of 
(
tr of 
(
   td of b of "Action name"
 & td of b of "Action issuer"
 & td of b of "Action script"
 & td of b of "State"
 & td of b of "Relevance"
 & td of b of "Link"
)
& 
(
  concatenation of trs of 
(
td of ((item 0 of it) as string)
& td of ((item 1 of it) as string)
& td of ((item 2 of it) as string)
& td of ((item 3 of it) as string)
& td of ((item 4 of it) as string)
& td of ((item 5 of it))
)
of
(
(
 name of it, 
(if (exist issuer of it) then (name of issuer of it) else "no-val"),
(if (exist action script of it) then (action script of it) else "no-val"),
(if (exist applicability relevance of it) then (applicability relevance of it) else "no-val"),
(if (exist state of it) then (state of it) else "no-val"),
link of it
)
of bes actions whose ( 
 (exist action script whose (
  it contains "Throttle"
  OR it contains "notify client ForceRefresh"
 ) of it)
)
)
)
)
```

---

## Example Results

| Action name             | Action issuer | Action script             | State    | Relevance | Link                   |
|-------------------------|---------------|---------------------------|----------|-----------|------------------------|
| Custom Action - test    | bfservice     | notify client ForceRefresh | true     | Stopped   | Custom Action - test   |
| Boom_goes_the_dynamite  | bfservice     | notify client ForceRefresh | true     | Expired   | Not a Great Idea       |
| Boom_goes_the_dynamite  | bfservice     | notify client ForceRefresh | true     | Expired   | Boom_goes_the_dynamite |
| Boom_goes_the_dynamite  | bfservice     | notify client ForceRefresh | true     | Expired   | This is a test         |

