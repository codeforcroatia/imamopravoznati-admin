<strong>Table of pages</strong>

{% assign items = site.html_pages %}
{% for page in items %}
{% assign url = page.url | relative_url %}
{% assign urls = urls | append: url | append: "," %}
{% endfor %}
