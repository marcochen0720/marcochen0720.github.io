---
layout: page
title: Projects
permalink: /projects/
---

<style>
.project-card {
  display: inline-block;
  width: 320px;
  vertical-align: top;
  margin: 10px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  border-radius: 10px;
  background: #fff;
  overflow: hidden;
  padding: 0;
}
.project-card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}
.project-card-content {
  padding: 15px;
}
.project-card-title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
}
.project-card-summary {
  color: #555;
  margin-bottom: 8px;
}
.project-card-link {
  display: inline-block;
  color: #0076d1;
  text-decoration: none;
}
</style>

<h2>My Projects</h2>

<div>
  {% for project in site.projects %}
    <div class="project-card">
      {% if project.image %}
        <img src="{{ project.image }}" alt="{{ project.title }}">
      {% endif %}
      <div class="project-card-content">
        <div class="project-card-title">{{ project.title }}</div>
        <div class="project-card-summary">{{ project.summary }}</div>
        <a class="project-card-link" href="{{ project.link }}" target="_blank">View Details &rarr;</a>
      </div>
    </div>
  {% endfor %}
</div>
