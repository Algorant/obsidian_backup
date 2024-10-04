#### Occupation:: Actor, Singer
#### About:: Well known pop singer. Has had some acting roles, which is essentially my main exposure to him.
#### Best Roles::
#### Tags:: #acting #singing #actor #pop 

---
#### Dataview Query for movies
```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
WHERE contains(starring, [[Harry Styles]])
```