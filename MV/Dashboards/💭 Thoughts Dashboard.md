
# Capture all Thoughts from Daily Notes

```dataview
TABLE bullet.text as "Thoughts"
FROM "Daily Notes"
FLATTEN file.lists as bullet
WHERE meta(bullet.section).subpath = "Thoughts"
SORT file.link desc
```





# Version 2 that Separates along pipe |

```dataview
TABLE WITHOUT ID
	file.link as "Date",
	split(sub.text, "\|")[0] as "Thought",
	split(sub.text, "\|")[1] as "Tags"
FROM "Daily Notes"
FLATTEN file.lists as sub
WHERE meta(sub.section).subpath = "Thoughts"
SORT file.link desc
```
