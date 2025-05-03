---
layout: home
title: Welcome to MatthewN.ca
---
<h1>A central repository for all things me</h1>
<div class="portfolio">
  {% for project in site.data.projects %}
    <div class="project">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
      <a href="{{ project.link }}">View Project</a>
    </div>
  {% endfor %}
</div>