---
title: "{{ title }}"
year: "{{ year }}"
image: "{{ image }}"
type: game
id: "{{ id }}"
dataSource: "{{ datasource }}"
url: "{{ url }}"
personalRating: 0
genres:
  - Action
  - Adventure
  - Fantasy
tags:
  - mediaDB/game
---
---
#### Cover
- `="![Cover|400](" + this.image + ")"`