---
layout: home
---

<!-- Wrapper for the portfolio section, displaying a list of projects -->
<div class="portfolio">
  {% if site.data.projects %}
    {% for project in site.data.projects %}
      <div class="project">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <a href="{{ project.link }}">View Project</a>
      </div>
    {% endfor %}
  {% else %}
    <p>No projects available at the moment.</p>
  {% endif %}
</div>