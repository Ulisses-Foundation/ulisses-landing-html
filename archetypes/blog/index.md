---
title: "{{ replace .Name "-" " " | title }}"
author: Christiane Hepp
description: "Blog post description" # relevant for meta tag
date: {{ .Date }}
draft: true
slug: "{{ .Name }}"
hero: ./delete-me.jpg
hero_alt: "delete-me"
tags:
- tag 1
- tag 2
categories:
- category 1
related_articles: [] # leave empty for hugo to guess related articles based on date, tags and categories
---

Link to another page:

## Short code examples

More can be found [here](https://gohugo.io/content-management/shortcodes/)

### Tweet

{{< tweet 877500564405444608 >}}

### YouTube

{{< youtube w7Ft2ymGmfc >}}

### Instagram

{{< instagram BWNjjyYFxVx hidecaption >}}


### Regular image

![Delete me](./delete-me.jpg)

### Full width image

{{< mdimage src="./delete-me.jpg" alt="Delete me" >}}

### Button

{{< btn-success href="https://forest8.ch" title="Visit forest8" >}}
