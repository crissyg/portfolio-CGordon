---
layout: default
title: Projects
---

# Projects Portfolio

Explore my work across **Frontend**, **Backend**, **Mobile**, and **Cloud** technologies. Each project demonstrates practical application of modern development practices with live demos and comprehensive documentation.

---

## 🔍 Filter by Category

<div class="filter-buttons" style="margin: 20px 0; text-align: center;">
  <button onclick="filterProjects('All')" class="filter-btn active" id="filter-all">🎯 All Projects</button>
  <button onclick="filterProjects('Frontend')" class="filter-btn" id="filter-frontend">🎨 Frontend</button>
  <button onclick="filterProjects('Backend')" class="filter-btn" id="filter-backend">⚙️ Backend</button>
  <button onclick="filterProjects('Mobile')" class="filter-btn" id="filter-mobile"> 📱 🤖 Mobile</button>
  <button onclick="filterProjects('Miscellaneous')" class="filter-btn" id="filter-misc"> 🔧 Miscellaneous</button>
</div>

<div id="project-count" style="text-align: center; margin: 10px 0; color: #666;"></div>

---

<div id="projects-list">
{% assign sorted_projects = site.projects | sort: "order" %}
{% for project in sorted_projects %}
  <div class="project-card" data-category="{{ project.category }}" style="border: 1px solid #e1e4e8; border-radius: 8px; padding: 20px; margin: 20px 0; background: #fff;">
    
    <!-- Project Header -->
    <div class="project-header" style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 15px;">
      <div>
        <h3 style="margin: 0 0 10px 0; color: #0366d6;">
          <a href="{{ project.url }}" style="text-decoration: none; color: inherit;">{{ project.title }}</a>
        </h3>
        <div class="project-meta" style="display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 10px;">
          <span class="category-badge" style="background: #f1f8ff; color: #0366d6; padding: 4px 8px; border-radius: 4px; font-size: 12px; font-weight: bold;">
            {{ project.category }}
          </span>
          {% if project.status %}
          <span class="status-badge status-{{ project.status | downcase | replace: ' ', '-' }}" style="padding: 4px 8px; border-radius: 4px; font-size: 12px; font-weight: bold;
          {% if project.status == 'Live' %}background: #28a745; color: white;
          {% elsif project.status == 'In Development' %}background: #ffc107; color: #212529;
          {% elsif project.status == 'Complete' %}background: #17a2b8; color: white;
          {% else %}background: #6c757d; color: white;{% endif %}">
            {{ project.status }}
          </span>
          {% endif %}
          {% if project.featured %}
          <span class="featured-badge" style="background: #ff6b6b; color: white; padding: 4px 8px; border-radius: 4px; font-size: 12px; font-weight: bold;">
            Featured
          </span>
          {% endif %}
        </div>
      </div>
    </div>

    <!-- Project Description -->
    <p style="color: #586069; line-height: 1.5; margin-bottom: 15px;">{{ project.description }}</p>

    <!-- Technologies -->
    {% if project.technologies %}
    <div class="tech-stack" style="margin-bottom: 15px;">
      <strong style="color: #24292e;">Technologies:</strong>
      {% for tech in project.technologies %}
        <span class="tech-tag" style="background: #f6f8fa; color: #586069; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin: 0 4px 4px 0; display: inline-block;">{{ tech }}</span>
      {% endfor %}
    </div>
    {% endif %}

    <!-- Deployment Info -->
    {% if project.deployment_platform %}
    <div class="deployment-info" style="margin-bottom: 15px; font-size: 14px; color: #586069;">
      <strong>Hosted on:</strong> {{ project.deployment_platform }}
    </div>
    {% endif %}

    <!-- Action Buttons -->
    <div class="project-actions" style="display: flex; gap: 10px; flex-wrap: wrap;">
      {% if project.demo and project.live_demo %}
        <a href="{{ project.demo }}" target="_blank" rel="noopener noreferrer" class="demo-btn" style="background: #28a745; color: white; padding: 8px 16px; border-radius: 6px; text-decoration: none; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          🚀 Live Demo
        </a>
      {% elsif project.demo %}
        <a href="{{ project.demo }}" target="_blank" rel="noopener noreferrer" class="demo-btn" style="background: #17a2b8; color: white; padding: 8px 16px; border-radius: 6px; text-decoration: none; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          🚀 Demo
        </a>
      {% else %}
        <span class="demo-planned" style="background: #6c757d; color: white; padding: 8px 16px; border-radius: 6px; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          🚀 Demo Planned
        </span>
      {% endif %}

      {% if project.github %}
        <a href="{{ project.github }}" target="_blank" rel="noopener noreferrer" class="github-btn" style="background: #24292e; color: white; padding: 8px 16px; border-radius: 6px; text-decoration: none; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
           🖥️ GitHub
        </a>
      {% endif %}

      {% if project.url and project.url != project.github %}
        <a href="{{ project.url }}" class="details-btn" style="background: #0366d6; color: white; padding: 8px 16px; border-radius: 6px; text-decoration: none; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          📄 Details
        </a>
      {% endif %}
    </div>

  </div>
{% endfor %}
</div>

<div id="no-projects" style="display: none; text-align: center; padding: 40px; color: #586069;">
  <h3>No projects found</h3>
  <p>Try selecting a different category filter.</p>
</div>

---

<style>
.filter-btn {
  background: #f6f8fa;
  border: 1px solid #d1d5da;
  border-radius: 6px;
  color: #24292e;
  cursor: pointer;
  font-size: 14px;
  font-weight: 500;
  margin: 0 5px 10px 0;
  padding: 8px 16px;
  transition: all 0.2s ease;
}

.filter-btn:hover {
  background: #e1e4e8;
  border-color: #c6cbd1;
}

.filter-btn.active {
  background: #0366d6;
  border-color: #0366d6;
  color: white;
}

.project-card {
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.project-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

@media (max-width: 768px) {
  .filter-buttons {
    text-align: left;
  }
  
  .project-actions {
    flex-direction: column;
  }
  
  .project-actions a,
  .project-actions span {
    text-align: center;
  }
}
</style>

<script>
// Project filtering functionality
function filterProjects(category) {
  const cards = document.querySelectorAll('.project-card');
  const noProjectsMsg = document.getElementById('no-projects');
  const countDisplay = document.getElementById('project-count');
  let visibleCount = 0;

  // Update active filter button
  document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
  document.getElementById('filter-' + category.toLowerCase()).classList.add('active');

  // Filter project cards
  cards.forEach(card => {
    const cardCategory = card.dataset.category;
    if (category === 'All' || cardCategory === category) {
      card.style.display = '';
      visibleCount++;
    } else {
      card.style.display = 'none';
    }
  });

  // Update count and show/hide no results message
  if (visibleCount === 0) {
    noProjectsMsg.style.display = 'block';
    countDisplay.textContent = '';
  } else {
    noProjectsMsg.style.display = 'none';
    const totalProjects = cards.length;
    const countText = category === 'All' 
      ? `Showing all ${totalProjects} projects`
      : `Showing ${visibleCount} of ${totalProjects} projects`;
    countDisplay.textContent = countText;
  }
}

// Initialize page with all projects visible
document.addEventListener('DOMContentLoaded', function() {
  filterProjects('All');
});

// Smooth scrolling for anchor links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      target.scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      });
    }
  });
});
</script>

<!-- Navigation footer -->
<div class="page-footer">
  <a href="/index.html" class="btn btn-outline">← Back to Home</a>
</div>