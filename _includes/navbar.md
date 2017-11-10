{% for item in site.data.navbar.content %}
  <ul>
    {% if item.subitems %}
      <li>
        <a href="#">{{ item.title }}</a>
        <ul>
          {% for entry in item.subitems %}
            <li><a href="{{ entry.url }}">{{ entry.title }}</a></li>
          {% endfor %}
        </ul>
      </li>
    {% else %}
      <li>
        <a href="{{ item.url }}">{{ item.title }}</a>
      </li>
    {% endif %}
  </ul>
{% endfor %}
