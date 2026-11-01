---
layout: page
title: Projects
permalink: /projects/
nav: true
nav_order: 3
_styles: |
  .research-projects {
    display: grid;
    gap: 0;
  }
  .research-project {
    display: grid;
    grid-template-columns: 180px minmax(0, 1fr);
    gap: 1.5rem;
    padding: 1.75rem 0;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .research-project:first-child {
    padding-top: 0;
  }
  .research-project:last-child {
    border-bottom: 0;
  }
  .research-project-content {
    grid-column: 2;
    min-width: 0;
  }
  .research-project-image {
    display: block;
    align-self: start;
    border: 1px solid var(--global-divider-color);
    border-radius: 1rem;
    overflow: hidden;
    background: white;
  }
  .research-project-image img {
    display: block;
    width: 100%;
    height: 150px;
    object-fit: contain;
  }
  .research-project h2 {
    margin: 0 0 0.5rem;
    font-size: 1.3rem;
    line-height: 1.4;
    font-weight: 600;
  }
  .research-project h2 a {
    color: var(--global-text-color);
  }
  .research-project h2 a:hover {
    color: var(--global-theme-color);
  }
  .research-project a:focus-visible {
    outline: 2px solid var(--global-theme-color);
    outline-offset: 4px;
    border-radius: 0.2rem;
  }
  .research-project-meta {
    color: var(--global-text-color-light);
    margin: 0 0 0.5rem;
  }
  .research-project-summary {
    margin: 0;
    line-height: 1.65;
  }
  .research-project-actions {
    display: flex;
    flex-wrap: wrap;
    column-gap: 1.25rem;
    margin-top: 0.5rem;
  }
  .research-project-actions a {
    display: inline-flex;
    align-items: center;
    min-height: 44px;
    font-size: 0.95rem;
    font-weight: 500;
    text-decoration: underline;
    text-underline-offset: 0.2em;
  }
  .research-project-badge {
    display: inline-block;
    margin-top: 0.6rem;
    padding: 0.15rem 0.65rem;
    border-radius: 999px;
    background: var(--global-code-bg-color, #f1f3f3);
    color: var(--global-text-color);
    font-size: 0.9rem;
  }
  .research-project-badge.published {
    background: #dff4e5;
    color: #087b32;
  }
  @media (max-width: 575px) {
    .research-project {
      grid-template-columns: minmax(0, 1fr);
      gap: 1rem;
    }
    .research-project-content {
      grid-column: 1;
    }
    .research-project-image {
      width: 180px;
    }
  }
---

{% assign selected_projects = site.projects | where: "show_on_projects", true | sort: "importance" %}

<div class="research-projects">
  {% for project in selected_projects %}
    {% assign project_href = project.url | relative_url %}
    {% if project.primary_url %}
      {% assign project_href = project.primary_url %}
    {% endif %}
    <article class="research-project{% if project.img and project.img != empty %} has-image{% endif %}">
      {% if project.img and project.img != empty %}
        {% if project.show_details == false and project.primary_url == nil %}
          <div class="research-project-image">
            <img src="{{ project.img | relative_url }}" alt="{{ project.img_alt | default: project.title | escape }}" loading="lazy" width="180" height="150">
          </div>
        {% else %}
        <a class="research-project-image" href="{{ project_href | escape }}" aria-label="{{ project.title | escape }}">
          <img src="{{ project.img | relative_url }}" alt="{{ project.img_alt | default: project.title | escape }}" loading="lazy" width="180" height="150">
        </a>
        {% endif %}
      {% endif %}
      <div class="research-project-content">
        <h2>
          {% if project.show_details == false and project.primary_url == nil %}
            {{ project.title | escape }}
          {% else %}
            <a href="{{ project_href | escape }}">{{ project.title | escape }}</a>
          {% endif %}
        </h2>
        <p class="research-project-meta">{{ project.subtitle | escape }}</p>
        <p class="research-project-summary">{{ project.description | escape }}</p>
        {% if project.badge %}
          <span class="research-project-badge{% if project.badge == 'Published' %} published{% endif %}">{{ project.badge | escape }}</span>
        {% endif %}
        {% if project.details_label or project.resources %}
          <div class="research-project-actions">
            {% if project.details_label and project.show_details != false %}
              <a href="{{ project.url | relative_url }}">{{ project.details_label | escape }}</a>
            {% endif %}
            {% for resource in project.resources %}
              <a href="{{ resource.url | escape }}">{{ resource.label | escape }}</a>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    </article>
  {% endfor %}
</div>
