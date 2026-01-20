---
title: Docs
description: "Browse technical documentation and reference material."
permalink: /docs/
layout: default
nav_order: 4
nav_exclude: false
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: false
---

# Docs

Explore the available documentation below.

{% assign items = site.docs | where_exp: "item", "item.url != page.url" | sort: "nav_order" %}
{% for item in items %}
- [{{ item.title }}]({{ item.url }})
{% endfor %}
