#### Occupation:: Actor
#### Best Roles:: [[Pride and Prejudice]], [[Atonement]], [[Pirates of the Carribean]]
#### Tags:: #actor #actress 

---
#### Dataview Query

```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
WHERE contains(starring, [[Keira Knightley]])
```
