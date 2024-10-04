---
director: "{{ producer }}"
release year: "{{ year }}"
url: "{{ url }}"
poster: "{{ poster }}"
length: "{{ duration }}"
genres: []
starring: []
onlinerating: "{{ onlineRating }}"
rating: 
summary: 
tags: []
delete_below_here: ---
type: "{{ type }}"
datasource: "{{ dataSource }}"
id: "{{ id }}"
title: "{{ title }}"
duration: "{{ duration }}"
misc: "{{ type }} {{ dataSource }} {{ id }}"
---

---
## Cover

- `="![Cover|400](" + this.poster + ")"`
