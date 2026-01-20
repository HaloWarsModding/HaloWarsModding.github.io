---
title: Guides
description: "Browse step-by-step guides for modding Halo Wars: Definitive Edition."
permalink: /guides/
layout: default
nav_order: 3
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: false
---

# Guides

Explore the available guides below.

{% assign items = site.guides | sort: "nav_order" %}
{% for item in items %}
## [{{ item.title }}]({{ item.url }}) <span class="label {{ item.status_class }}">{{ item.status_label }}</span>
{% endfor %}
