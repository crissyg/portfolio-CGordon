---
layout: default
title: Home
---

# Hi, I'm Christina Gordon

## Software Engineer

Welcome to my portfolio! I'm a passionate software engineer with expertise that specializes in building scalable, efficient applications using Python, JavaScript, Java, Cloud technologies and cutting-edge frameworks.

---

## 🚀 What I Do

- **Backend Development**: Python (Flask, FastAPI), REST APIs, Java
- **Frontend Development**: Node.js,  JavaScript, responsive design
- **DevOps & Automation**: Jenkins, CI/CD pipelines, Docker, GitHub Actions, JIRA integration, infrastructure automation
- **Mobile Development**: Android, iOS, Cross-platform solutions

---

## 🎯 Quick Links

- **[About Me](about.md)** - Learn about my background and journey
- **[Skills](skills.md)** - Detailed technical expertise breakdown  
- **[All Projects](projects.md)** - Explore my development work
- **[Experience](experience.md)** - Professional background and achievements
- **[Contact](contact.md)** - Let's connect and discuss opportunities

---

## 🌟 Featured Projects

{% assign featured_projects = site.projects | where: "featured", true | sort: "order" %}
{% for project in featured_projects limit:3 %}

### {{ project.title }}
{{ project.description }}

**Technologies**: {{ project.technologies | join: ', ' }}  
**Category**: {{ project.category }}

{% if project.demo and project.live_demo %}
[ Live Demo]({{ project.demo }}){:target="_blank" rel="noopener"} | [ GitHub]({{ project.github }}){:target="_blank" rel="noopener"}
{% else %}
[ GitHub]({{ project.github }}){:target="_blank" rel="noopener"} | Demo Coming Soon
{% endif %}
{% endfor %}

---

## 👩🏽‍💻 Open to Opportunities

I'm actively seeking **Software Engineer** positions where I can leverage my expertise in:

- **Python, JavaScript, Kotlin, Java** ecosystem and best practices
- **DevOps** with Jenkins automation tools and Docker
- **JIRA** and agile development workflows

**Remote-friendly** | **Full-time** | **Contract** opportunities welcome

## 📞 Let's Connect

Ready to discuss your next project or opportunity? 

- **[Get In Touch!](contact.md)**

---

*Last updated: {{ site.time | date: "%B %Y" }}*
