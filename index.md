---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---
<h2>{{ site.data.page_list.docs_list_title }}</h2>

<ul>
  {% for pg in site.pages %}
    {% if pg.tag == "doc" %}
      <li><a href="{{ pg.permalink }}" alt="{{ pg.title }}">{{ pg.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>
