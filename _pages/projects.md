---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: false
nav_order: 3
horizontal: true
_styles: |
  .projects > .container {
    padding: 0;
  }
  .projects .card {
    overflow: hidden;
    border: 1px solid var(--global-divider-color);
    border-radius: 0.5rem;
  }
  .projects .card > .row {
    display: grid;
    grid-template-columns: minmax(140px, 28%) minmax(0, 1fr);
    min-height: 170px;
    margin: 0;
  }
  .projects .card > .row > div {
    width: 100%;
    max-width: none;
    min-width: 0;
    padding: 0;
  }
  .projects .card .col-md-12 {
    grid-column: 1 / -1;
  }
  .projects .card .col-md-6:first-child {
    position: relative;
  }
  .projects .card figure {
    position: absolute;
    inset: 0;
    margin: 0;
  }
  .projects .card picture {
    display: block;
    height: 100%;
  }
  .projects .card .card-img {
    display: block;
    height: 100%;
    padding: 0;
    object-fit: cover;
    border-radius: 0;
  }
  .projects .card-body {
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-height: 170px;
    padding: 1.5rem;
  }
  .projects .card-title {
    color: var(--global-theme-color);
    font-size: 1.35rem;
  }
  .projects .card-text {
    margin-bottom: 0;
  }
  .projects h2.category {
    color: var(--global-text-color-light);
  }
  @media (max-width: 575px) {
    .projects .card > .row {
      grid-template-columns: 100px minmax(0, 1fr);
      min-height: 145px;
    }
    .projects .card-body {
      min-height: 145px;
      padding: 1rem;
    }
    .projects .card-title {
      font-size: 1.15rem;
    }
  }
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
