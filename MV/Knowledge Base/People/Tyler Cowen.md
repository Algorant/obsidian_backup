#### Occupation:: Author, Podcaster, Academic
#### About:: One of the most interesting people in the world. Basically a polyglot with multiple domain expertise's. Works for the #mercatus center.
#### Works::  [[Talent]], [[Conversations With Tyler]], [[Marginal Revolution]]
#### Domain:: #economics #travel #food
#### Tags:: #multidisciplinarian #polyglot #genius #prolific

---
#### Dataview
### Podcast

```dataview
TABLE WITHOUT ID
file.link AS "Podcast", hosted-by, link, summary, tags
FROM "Knowledge Base/Media/Podcasts"
WHERE contains(hosted-by, [[Tyler Cowen]])
```
### Books By Author

```dataview
TABLE WITHOUT ID
file.link AS "Title", author, year-published, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
WHERE contains(author, [[]])
```
