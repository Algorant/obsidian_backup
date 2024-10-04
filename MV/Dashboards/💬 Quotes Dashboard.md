

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










