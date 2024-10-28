# BigFix BES Property Search Example

This example query looks through BES properties for a given string. In this case, it searches for properties where the definition contains `"descendants of"` in lowercase.

---

## Query

```bigfix
table of (
concatenation of concatenations of trs of (
td of item 0 of it 
& td of item 1 of it
& td of item 2 of it
& td of item 3 of it
)

of
(
( "Bes Property",
   name of it,
  (if (exist source analysis of it) then (name of source analysis of it) else ("no-val")),
  (if (exist source analysis of it) then (name of site of source analysis of it) else ("no-val"))
 ) 
 of bes properties whose (exist definition of it and definition of it as lowercase contains "descendants of")
)
)
```

---

## Example Results

| Bes Property             | Property Name                     | Source Analysis                     | Site                            |
|--------------------------|-----------------------------------|--------------------------------------|---------------------------------|
| Bes Property             | Upload Manager Bufferdir temp size used | Upload Manager BufferDir Measurement | no-val                         |
| Bes Property             | Upload Manager Bufferdir size used      | Upload Manager BufferDir Measurement | no-val                         |
| Bes Property             | Upload Manager Bufferdir Sha1 size used | Upload Manager BufferDir Measurement | no-val                         |

