### All Movies
```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, release-year, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
SORT rating DESC
```


#### Unwatched Movies

```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
WHERE contains(tags, "#unwatched")
SORT rating DESC
```
