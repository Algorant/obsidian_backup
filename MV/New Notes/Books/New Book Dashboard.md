





```dataview
TABLE ("![|100](" + cover + ")") as cover, author, year-published as "published", pages, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
WHERE year-read = "2024"
SORT file.link asc
```

