---
title: Sve stranice
is_wiki_page: false
---

<div class="git-wiki-page-list">

    <span class="page-list-title">Popis dostupnih stranica</span>
    <ul class="page-list">
        {% assign numPages=0 %}
        {% assign items = site.html_pages | sort_natural %}
        {% for page in items %}
        {% if page.is_wiki_page != false and page.sitemap != false %}
        <li class="page-list-item">
            {% assign title = page.title | default: page.name %}
            <a href="{{ page.url | relative_url }}">{{title | escape}}</a>
        </li>
        {% assign numPages = numPages | plus: 1 %}
        {% endif %}

        {% endfor %}
    </ul>

</div>
