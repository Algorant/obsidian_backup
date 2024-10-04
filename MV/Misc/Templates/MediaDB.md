---
director: "{{ producer }}"
year: "{{ year }}"
url: "{{ url }}"
image: "{{ image }}"
length: "{{ duration }}"
genres: 
starring: 
onlinerating: "{{ onlineRating }}"
rating: 
summary: 
tags: 
delete_below_here: ---
type: "{{ type }}"
id: "{{ id }}"
title: 
duration:
---

---
#### Cover
- `="![Cover|400](" + this.image + ")"`
