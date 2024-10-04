#### Occupation:: Psychologist, Author
#### About:: #nobel winning #behavioral-economics and #psychology professor who has written books like [[Thinking Fast and Slow]]. Most famous of his theories are that of the brain and separating thinking into #system1 and #system2
#### Works:: [[Thinking Fast and Slow]]
#### Domain:: #psychology #behavioral-economics 
#### Tags:: #psychology #behavioral-economics #nobel #system1 #system2

---
#### Dataview Query
### Books By Author

```dataview
TABLE WITHOUT ID
file.link AS "Title", author, year-published, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
WHERE contains(author, [[Daniel Kahneman]])
```