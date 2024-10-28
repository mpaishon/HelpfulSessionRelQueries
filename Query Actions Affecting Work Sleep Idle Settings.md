# BigFix Actions Affecting Work / Sleep Idle Settings

**Description**: This query retrieves BigFix actions that impact Work and Sleep Idle settings for the BES Client. It provides details such as the action name, issuer, script, state, and link.

---

## Query

```bigfix
table "border=1" of 
(
tr of 
(
   td of b of "Action Name"
 & td of b of "Action Issuer"
 & td of b of "Action Script"
 & td of b of "State"
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
& td of ((item 4 of it))
)
of
(
(
 name of it, 
(if (exist issuer of it) then (name of issuer of it) else "no-val"),
(if (exist action script of it) then (action script of it) else "no-val"),
(if (exist state of it) then (state of it) else "no-val"),
link of it
)
of bes actions whose (exist action script whose (
  it contains "_BESClient_Resource_SleepIdle" 
  OR it contains "_BESClient_Resource_WorkIdle"
  OR it contains "_BESClient_Resource_WorkNormal"
  OR it contains "_BESClient_Resource_SleepNormal" 
 ) of it)
)
)
)
```

---

## Example Results

| Action Name                                                            | Action Issuer | Action Script                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | State   | Link                                                                                                                                                                      |
|------------------------------------------------------------------------|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (OPEN POLICY ACTION NO END DATE) Deploy CPU idle settings allocation adjustment for multi-core physical machines | bfservice     | //If the number of cores are greater than 10, then set the value to 100, else calculate the value as ((# of cores) * 10) parameter "worksetting" = "{if ((sum of cores of cpupackage as floating point) > 10) then "100" else (((sum of cores of cpupackage as floating point) * 10) as integer as string)}" setting "_BESClient_Resource_WorkIdle"="{parameter "worksetting"}" on "{parameter "action issue date" of action}" for client // Enter your action script here setting "_BESClient_Resource_SleepIdle"="480" on "{parameter "action issue date" of action}" for client //drop breadcrumb for when the action was last run setting "_TEST_CPU_MultiCore_Adjustment"="{now}" on "{parameter "action issue date" of action}" for client | Stopped | (OPEN POLICY ACTION NO END DATE) Deploy CPU idle settings allocation adjustment for multi-core physical machines |
| Deploy CPU idle settings allocation adjustment for multi-core physical machines                               | bfservice     | //If the number of cores are greater than 10, then set the value to 100, else calculate the value as ((# of cores) * 10) parameter "worksetting" = "{if ((sum of cores of cpupackage as floating point) > 10) then "100" else (((sum of cores of cpupackage as floating point) * 10) as integer as string)}" setting "_BESClient_Resource_WorkIdle"="{parameter "worksetting"}" on "{parameter "action issue date" of action}" for client // Enter your action script here setting "_BESClient_Resource_SleepIdle"="480" on "{parameter "action issue date" of action}" for client //drop breadcrumb for when the action was last run setting "_TEST_CPU_MultiCore_Adjustment"="{now}" on "{parameter "action issue date" of action}" for client | Expired | Deploy CPU idle settings allocation adjustment for multi-core physical machines                         |

---


