---
layout: page
title: Projects
permalink: /projects/
---
<style>
.projects-section {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px 0;
}
.project-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center; /* 居中对齐 */
  margin: -10px; /* 负边距补偿卡片间距 */
}
.project-card {
  width: 320px;
  margin: 15px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  border-radius: 10px;
  background: #fff;
  overflow: hidden;
  padding: 0;
  display: flex;
  flex-direction: column;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}
.project-card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}
.project-card-content {
  padding: 15px;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}
.project-card-title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
}
.project-card-summary {
  color: #555;
  margin-bottom: 12px;
  flex-grow: 1;
}
.project-card-link {
  display: inline-block;
  color: #0076d1;
  text-decoration: none;
  margin-top: auto;
  font-weight: 500;
}
.section-heading {
  text-align: center;
  margin-bottom: 30px;
  font-size: 28px;
  font-weight: bold;
}
</style>

<div class="projects-section">
  <h2 class="section-heading">My Projects</h2>
  <div class="project-container">
    {% for project in site.projects %}
      <div class="project-card">
        {% if project.img %}
          <img src="{{ project.img | relative_url }}" alt="{{ project.title }}">
        {% endif %}
        <div class="project-card-content">
          <div class="project-card-title">{{ project.title }}</div>
          <div class="project-card-summary">{{ project.description }}</div>
          <a class="project-card-link" href="{{ project.url | relative_url }}">View Details &rarr;</a>
        </div>
      </div>
    {% endfor %}
  </div>
</div>
