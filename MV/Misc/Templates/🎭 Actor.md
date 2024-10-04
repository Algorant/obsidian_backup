#### Occupation:: Actor
#### Best Roles::
#### Tags::
---

### Dataview
### Movies 
```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
WHERE contains(starring, [[]])
```