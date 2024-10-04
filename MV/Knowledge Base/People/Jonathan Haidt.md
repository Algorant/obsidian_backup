#### Occupation:: Psychologist, Academic, Author
#### About:: Famous public intellectual. Known for his work on psychology and how it relates to our everyday lives in #politics, #religion, and #social-media.
#### Works:: [[The Righteous Mind]], [[The Coddling of the American Mind]]
#### Domain:: #development #psychology #behavioral-economics
#### Tags:: #judgment #academic #philosophy

---
#### Dataview Query
### Books By Author

```dataview
TABLE WITHOUT ID
file.link AS "Title", author, year-published, year-read, series, rating, tags, summary
FROM "Knowledge Base/Media/Books"
WHERE contains(author, [[Jonathan Haidt]])
```