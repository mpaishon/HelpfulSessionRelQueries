# ActionSite Version for the Communication elements of your BigFix infrastructure. 

---

## Query: Maximum of Unique Values for Actionsite Version

**Query:**
```bigfix
maximum of unique values of ((values of it) as integer) of results of (bes properties whose (name of it = "BES Health Checks::Actionsite Version"))
```

**Example Results:** 
```
336
```

---

## Description: To See All Values Less Than the Latest
 
> **Note**: If everything is on the current version, you won’t see any return here.

**Query:**
```bigfix
(item 1 of it) of 
(
maximum of unique values of ((values of it) as integer) of results of (bes properties whose (name of it = "BES Health Checks::Actionsite Version")),
(value of it,(name of it,last report time of it) of computer of it) of results of (bes properties whose (name of it = "BES Health Checks::Actionsite Version"))
)
whose (((item 0 of item 1 of it) as integer) < (item 0 of it) as integer)
```

**Example Results:**  
```
217, ( VMBEC01, ( Thu, 13 Aug 2024 07:22:57 -0500 ) )
```

---

## Description: To See Everything on the Latest Version

**Query:**
```bigfix
(item 1 of it) of 
(
maximum of unique values of ((values of it) as integer) of results of (bes properties whose (name of it = "BES Health Checks::Actionsite Version")),
(value of it,(name of it,last report time of it) of computer of it) of results of (bes properties whose (name of it = "BES Health Checks::Actionsite Version"))
)
whose (((item 0 of item 1 of it) as integer) = (item 0 of it) as integer)
```

**Example Results:**  
```
336, ( SRV2, ( Mon, 01 Feb 2024 16:43:18 -0500 ) )
336, ( VMBEC02, ( Mon, 01 Feb 2024 16:36:35 -0500 ) )
336, ( VMDC01, ( Mon, 01 Feb 2024 16:38:16 -0500 ) )
```
