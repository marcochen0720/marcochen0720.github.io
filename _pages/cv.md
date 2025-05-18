---
layout: archive # 使用archive布局
title: "Curriculum Vitae" # 将标题改为更正式的 "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<p>Welcome to my curriculum vitae page. Below you'll find a summary of my academic background, key skills, and professional experiences. For a comprehensive overview with full details, please download the complete PDF version.</p> {# 添加一段介绍性文字 #}

<p class="page__content"> {# 使用一个p标签包裹，并使用主题的content class辅助定位样式 #}
  <a href="https://drive.google.com/file/d/10TXgXLxSadKUjpItiY7A-hNLFdoSMkj8/view?usp=sharing" class="btn btn--primary"> {# 使用主题内置的primary button样式类 #}
    <i class="fas fa-download"></i> Download My Full CV (PDF) {# 添加一个下载图标，需要确保主题支持Font Awesome #}
  </a>
</p>

<hr> {# 使用HTML的hr标签，主题会为其提供默认样式，也可以通过CSS自定义 #}

<h2 id="education">Education</h2> {# 修改 ### 为 ##，并添加一个id方便将来做页面内跳转链接（可选） #}
{# 保持 Education 部分内容不变 #}
### **University of California, Berkeley**
**Visiting Student** | January 2024 – May 2024
- Departments: Industrial Engineering and Operations Research (IEOR) and Haas School of Business.
- Focus: Data analytics, operations research, and business decision-making.

### **Soochow University**
**Bachelor of Science (B.S.) in Applied Psychology** | September 2022 – June 2025
- Relevant coursework: Behavioral Psychology, Statistical Analysis, Cognitive Science.

**Bachelor of Business Administration (B.BA.) in Accounting** | September 2021 – June 2025
- Relevant coursework: Financial Accounting, Managerial Accounting, Auditing, Corporate Finance.
- Honors: Innovation and Entrepreneurship Scholarship (Outstanding Prize,0.5%,2023).

<hr>

<h2 id="work-experience">Work Experience</h2> {# 修改 ### 为 ##，并添加id #}
{# 保持 Work Experience 部分内容不变 #}
### **Bank of China Investment Management Co., Ltd. (BOCIM)**
**Quantitative Research Intern** | Summer 2024
- Developed alpha-seeking strategies using **Genetic Algorithms** and replicated analytical reports for performance insights.
- Constructed predictive models leveraging **statistical methods** and **ML/DL techniques** for financial data analysis.
- Conducted backtesting with an average **RankIC** exceeding 0.1, validating model robustness and predictive power.

### **Deloitte iBond (Shanghai) Co., Ltd.**
**Data Analyst Intern** | Fall 2024
- Developed a **Bond Risk Early Warning Model** integrating **sentiment analysis**, **market data**, and **fundamental indicators** to evaluate stress indices and default risks of bond issuers.
- Employed **Python** for real-time data scraping and processing, dynamically updating risk scores using decay algorithms.
- Designed a **network model** to analyze risk transmission paths and utilized an **SIS model** to capture credit risk contagion among enterprises.
- Assisted in transitioning from legacy systems to advanced risk assessment models.

<hr>

<h2 id="skills">Skills</h2> {# 修改 ### 为 ##，并添加id #}
{# 保持 Skills 部分内容不变 #}
### **Languages**
- English (Fluent)
- Mandarin (Native)

### **Programming**
- **Python** (Most Proficient)
- R, SQL

### **Software Tools**
- **Data Visualization**: Tableau, Power BI
- **Office Productivity**: MS Office, Prezi
- **Creative Tools**: Photoshop, Premiere Pro, Canva

<hr>

<h2 id="publications">Publications</h2> {# 修改 ### 为 ##，并添加id #}
{# 保持 Publications 部分不变 #}
<ul>{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>
