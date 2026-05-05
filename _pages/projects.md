---
layout: default
title: Madison Cheek - Portfolio
permalink: /projects/
---

<div class="gallery-container">
  <div class="project-gallery">
    {% for project in site.projects %}
      {% if project.toc != true %}
        <div class="gallery-item">
          <a href="{{ project.url | relative_url }}">
            {% if project.image %}
              <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
            {% endif %}
            <p>{{ project.title}}</p>
          </a>
        </div>
      {% endif %}
    {% endfor %}
  </div>
</div>