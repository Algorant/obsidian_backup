
# Create watched, unwatched, and partially watched

```dataview
TABLE WITHOUT ID
file.link AS "Name", created-by, starring, original-release as "release year", seasons, episodes, status, rating, summary, tags
FROM "Knowledge Base/Media/TV Shows"
SORT rating DESC
```




