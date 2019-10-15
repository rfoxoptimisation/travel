---
layout: post
title: Three days in Arequipa
hero_image: lighthouse.jpg
country: peru
continent: "south america"
category: places
---

<!-- description -->

## Categories

{% for category in site.categories %}
{{ category[0] }}
{% endfor %}

## Tags

{% for tag in site.tags %}
{{ tag[0] }}
{% endfor %}

----------

## Display a list of all continents

{% assign allposts = site.posts | group_by: 'continent' %}
{% for continent in allposts %}
{% if continent.name != empty %}

This is one: {{ continent.name | upcase }}

{% endif %}
{% endfor %}

----------

## Display a list of all countries

{% assign allposts = site.posts | group_by: 'country' %}
{% for country in allposts  %}
{% if country.name != empty %}

This is one:
{{ country.name | capitalize }}

{% endif %}
{% endfor %}

----------

## Articles by category

{% assign allposts = site.posts | group_by: 'category' %}
{% for category in allposts  %}

### {{ category.name | capitalize }}

{% assign items = category.items %}
{% for item in items %}

* <a href="{{ item.url | prepend: site.baseurl }}">{{ item.title }}

{% endfor %}
{% endfor %}

----------

{% assign allposts = site.posts | group_by: 'category' %}
{% for category in allposts  %}
### {{ category.name | capitalize }}
{% assign items = category.items %}
{% for item in items %}

* <a href="{{ item.url | prepend: site.baseurl }}">{{ item.title }}</a>

{% endfor %}
{% endfor %}

----------

## Articles by continent

{% assign allposts = site.posts | group_by: 'continent' %}

{% for continent in allposts %}
{% if continent.name != empty %}

Continent: {{ continent.name | capitalize }}

{% endif %}
{% endfor %}

----------

{% assign allposts = site.posts | group_by: 'continent' %}

{% for continent in allposts %}
{% if continent.name != empty %}

Continent: {{ continent.name | capitalize }}

{% endif %}
{% endfor %}
