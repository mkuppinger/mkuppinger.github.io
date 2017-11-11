{% assign links = site.data.navbar.content %}

<nav id="navbar" class="collapse navbar-collapse">
  <ul class="nav navbar-nav">

    {% for link in links %}
      {% if link.sublinks %}
        <li class="dropdown">
          <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Dropdown <span class="caret"></span></a>

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
          <button class="btn btn-default" type="button">
            <a href="{{ site.baseurl }}{{ link.url }}">{{ link.title }}</a>
          </button>
        </li>
      {% endif %}

    {% endfor %}
  </ul>
</nav>
