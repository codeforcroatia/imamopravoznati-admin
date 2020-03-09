<div class="git-wiki-page-list">

    <span class="page-list-title">Pages {% if (site.show_wiki_pages_limit >= 1 %} (Latest {{site.show_wiki_pages_limit
        }} updated) {% endif %}:</span>
    <ul class="page-list">
        {% assign numPages=0 %}
        {% assign items = site.html_pages | sort: 'date' %}
        {% for page in items %}
        {% if numPages >= site.show_wiki_pages_limit %}
        {% break %}
        {% endif %}
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
