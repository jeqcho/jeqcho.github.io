---
title: Projects
layout: single
permalink: /
---

<link rel="stylesheet" href="/assets/projects.css">

<div class="project-container">
{% assign sorted_projects = site.projects | sort: 'date' | reverse %}
    {% for project in sorted_projects %}
    <div class="project">
        <img src="{{ project.image }}" alt="{{ project.title }}" class="project-image">
        <div class="project-content">
            <h2 class="project-title">{{ project.title }}</h2>
            <p class="project-description">{{ project.description }}</p>
            <a href="{{ project.project_link }}" class="project-link" target="_blank">Project</a>
            {% if project.code_link %}
            <a href="{{ project.code_link }}" class="project-code-link" target="_blank">Code</a>
            {% endif %}
        </div>
    </div>
    {% endfor %}
</div>
