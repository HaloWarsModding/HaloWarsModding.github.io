---
title: Guides
description: "Browse step-by-step guides for modding Halo Wars: Definitive Edition."
permalink: /guides/
layout: default
nav_order: 2
nav_exclude: false
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: false
---

# Guides

Explore the available guides below.

{% assign items = site.guides | where_exp: "item", "item.url != page.url" | sort: "nav_order" %}
{% for item in items %}
- [{{ item.title }}]({{ item.url }})
{% endfor %}
