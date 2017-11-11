<nav id="navbar" class="collapse navbar-collapse">
  <ul class="nav navbar-nav">
    {% assign links = site.data.navbar.content %}

    {% for link in links %}
      {% assign class = nil %}
      {% if page.url contains link.url %}
        {% assign class = 'active' %}
      {% endif %}

      {% if link.sublinks %}
        <li class="dropdown">
          <button class="btn dropdown-toggle"
                  type="button"
                  data-toggle="dropdown">
            <a href="{{ sublink.url }}">{{ link.title }} <span class="caret"></span></a>
          </button>

          <ul class="dropdown-menu">
            {% for sublink in link.sublinks %}
              <li>
                <a href="{{ site.baseurl }}{{ sublink.url }}">{{ sublink.title }}</a>
              </li>
            {% endfor %}
          </ul>
        </li>
      {% else %}
        <li>
          <button class="btn" type="button">
            <a href="{{ site.baseurl }}{{ link.url }}">{{ link.title }}</a>
          </button>
        </li>
      {% endif %}

    {% endfor %}
  </ul>
</nav>
