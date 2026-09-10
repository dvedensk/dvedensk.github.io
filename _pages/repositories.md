---
layout: page
permalink: /repositories/
title: Repositories
description: Selected public code and research projects
nav: true
nav_order: 4
---

{% if site.data.repositories.github_repos %}
<div class="row repositories-list">
  {% for repo in site.data.repositories.github_repos %}
    <div class="col-md-6 mb-4">
      <a href="{{ repo.url }}" class="repository-card d-flex flex-column h-100 p-3" target="_blank" rel="noopener noreferrer">
        <div class="d-flex justify-content-between align-items-start mb-2">
          <span class="repository-card-title">
            <i class="fa-brands fa-github mr-2" aria-hidden="true"></i>{{ repo.name }}
          </span>
          <i class="fa-solid fa-arrow-up-right-from-square repository-card-link-icon" aria-hidden="true"></i>
        </div>
        <p class="repository-card-description">{{ repo.description }}</p>
        {% if repo.language %}
          <div class="repository-card-meta mt-auto">
            <span class="repository-language-dot" style="background-color: {{ repo.language_color }}"></span>
            {{ repo.language }}
          </div>
        {% endif %}
      </a>
    </div>
  {% endfor %}
</div>
{% endif %}

{% if site.data.repositories.github_username %}
## GitHub contributions

<div class="repository-contributions text-center">
  <a href="https://github.com/{{ site.data.repositories.github_username }}" target="_blank" rel="noopener noreferrer">
    <img
      src="https://ghchart.rshah.org/{{ site.data.repositories.github_username }}"
      alt="{{ site.data.repositories.github_username }}'s GitHub contribution chart"
      loading="lazy"
    >
  </a>
</div>
{% endif %}
