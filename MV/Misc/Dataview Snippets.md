
### This shows all incomplete tasks

```dataview
TASK
FROM ""
WHERE !completed
```



### This shows all uncreated files

### This shows all uncreated files with their origins


```dataview
TABLE without id 
out AS "Uncreated files"
FLATTEN file.outlinks as out
WHERE !(out.file) AND !contains(meta(out).path, "/")
GROUP by out
SORT out ASC
```


```dataview
TABLE without id 
out AS "Uncreated files", file.link as "Origin"
FLATTEN file.outlinks as out
WHERE !(out.file) AND !contains(meta(out).path, "/")
SORT out ASC
```

### For Books by Author
```dataview
TABLE WITHOUT ID
file.link AS "Title", author, read, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
WHERE contains(author, [[James Clear]])
```
### For Movies by Director
```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
WHERE contains(director, [[Quentin Tarantino]])
```

### For Movies Starring Actor
```dataview
TABLE WITHOUT ID
file.link AS "Film", director, starring, rating, summary, tags
FROM "Knowledge Base/Media/Movies"
WHERE contains(starring, [[Cillian Murphy]])
```
### For TV Show Starring Actor
```dataview
TABLE WITHOUT ID
file.link AS "Name", created-by, starring, seasons, episodes, status, rating, summary, tags
FROM "Knowledge Base/Media/TV Shows"
WHERE contains(starring, [[Sarah Snook]])
```
### For TV Show by Creator
```dataview
TABLE WITHOUT ID
file.link AS "Name", created-by, starring, seasons, episodes, status, rating, summary, tags
FROM "Knowledge Base/Media/TV Shows"
WHERE contains(created-by, [[Abbi Jacobson]])
```
### For Anime By Studio
### For Games by Studio
```dataview
TABLE WITHOUT ID
file.link as "Game", studio, series, rating, length, complete, tags
FROM "Knowledge Base/Media/Games"
WHERE contains(studio, [[Atlus]])
```
### For Game by System
```dataview
TABLE WITHOUT ID
file.link as "Game", studio, series, rating, length, complete, tags
FROM "Knowledge Base/Media/Games"
WHERE contains(tags, "#ps4")
```
### For Article by Author/Blogger
### This shows how to split a bullet along a separator, in this case pipe |
```dataview
TABLE WITHOUT ID
	split(sub.text, "\|")[0] as "Quote",
	split(sub.text, "\|")[1] as "Author",
	split(sub.text, "\|")[2] as "Source"
FROM "Knowledge Base/💬 Quotes"
FLATTEN file.lists as sub
WHERE meta(sub.section).subpath = "Quotes"
SORT file.link desc
```