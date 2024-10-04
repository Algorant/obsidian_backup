

```dataview
TABLE author, year-published, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
SORT year-published DESC
```




## Unread Books

```dataview
TABLE author, year-published, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
WHERE contains(tags, "#unread")
SORT rating DESC
```

