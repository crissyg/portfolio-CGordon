---
layout: default
title: Projects
---

# Projects Portfolio

Explore my work across **Frontend**, **Backend**, **Mobile**, and **Cloud** technologies. Each project demonstrates practical application of modern development practices with live demos and comprehensive documentation.

---

## 🔍 Filter by Category

<div class="filter-buttons" style="margin: 20px 0; text-align: center;">
  <button onclick="filterProjects('All')" class="filter-btn active" data-filter="All">🎯 All Projects</button>
  <button onclick="filterProjects('Frontend')" class="filter-btn" data-filter="Frontend">🎨 Frontend</button>
  <button onclick="filterProjects('Backend')" class="filter-btn" data-filter="Backend">⚙️ Backend</button>
  <button onclick="filterProjects('Mobile')" class="filter-btn" data-filter="Mobile">📱 Mobile</button>
  <button onclick="filterProjects('Miscellaneous')" class="filter-btn" data-filter="Miscellaneous">🔧 Miscellaneous</button>
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
          {% if project.url %}
          <a href="{{ project.url }}" style="text-decoration: none; color: inherit;">{{ project.title }}</a>
          {% else %}
          {{ project.title }}
          {% endif %}
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
            ⭐ Featured
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
      {% if project.demo and project.demo != "" %}
        <a href="{{ project.demo }}" target="_blank" rel="noopener noreferrer" class="demo-btn" style="background: #28a745; color: white; padding: 8px 16px; border-radius: 6px; text-decoration: none; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          🚀 Live Demo
        </a>
      {% else %}
        <span class="demo-planned" style="background: #6c757d; color: white; padding: 8px 16px; border-radius: 6px; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          ⏳ Demo Planned
        </span>
      {% endif %}

      {% if project.github and project.github != "" %}
        <a href="{{ project.github }}" target="_blank" rel="noopener noreferrer" class="github-btn" style="background: #24292e; color: white; padding: 8px 16px; border-radius: 6px; text-decoration: none; font-weight: 500; display: inline-flex; align-items: center; gap: 5px;">
          🐙 GitHub
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
  <button onclick="filterProjects('All')" style="background: #0366d6; color: white; border: none; padding: 8px 16px; border-radius: 6px; cursor: pointer;">Show All Projects</button>
</div>

---

## 🎯 Recommended Future Projects

Based on current market demands for **Python + AWS + Jira** expertise, here are strategic projects I'm planning:

<div class="recommended-projects" style="display: grid; gap: 20px; margin: 30px 0;">
  <div style="border: 1px solid #e1e4e8; border-radius: 8px; padding: 20px; background: #f8f9fa;">
    <h4 style="color: #0366d6; margin-top: 0;">🔧 AWS Resource Manager CLI</h4>
    <p>Command-line tool for automating AWS resource provisioning, cost monitoring, and infrastructure management using Boto3 and Terraform.</p>
    <div style="margin-top: 10px;">
      <span style="background: #f1f8ff; color: #0366d6; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin-right: 5px;">Python</span>
      <span style="background: #f1f8ff; color: #0366d6; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin-right: 5px;">AWS</span>
      <span style="background: #f1f8ff; color: #0366d6; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin-right: 5px;">Boto3</span>
    </div>
  </div>
  
  <div style="border: 1px solid #e1e4e8; border-radius: 8px; padding: 20px; background: #f8f9fa;">
    <h4 style="color: #0366d6; margin-top: 0;">📊 JIRA Sprint Insights Dashboard</h4>
    <p>Interactive dashboard for visualizing sprint metrics, identifying bottlenecks, and generating automated reports from JIRA boards using Python and Plotly.</p>
    <div style="margin-top: 10px;">
      <span style="background: #f1f8ff; color: #0366d6; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin-right: 5px;">Python</span>
      <span style="background: #f1f8ff; color: #0366d6; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin-right: 5px;">JIRA API</span>
      <span style="background: #f1f8ff; color: #0366d6; padding: 2px 6px; border-radius: 3px; font-size: 12px; margin-right: 5px;">Plotly</span>
    </div>
  </div>
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
  transform: translateY(-1px);
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
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
}

.project-actions a:hover,
.project-actions span:hover {
  transform: translateY(-1px);
  box-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

@media (max-width: 768px) {
  .filter-buttons {
    text-align: left;
  }
  
  .filter-btn {
    margin: 0 5px 5px 0;
    padding: 6px 12px;
    font-size: 13px;
  }
  
  .project-actions {
    flex-direction: column;
  }
  
  .project-actions a,
  .project-actions span {
    text-align: center;
    justify-content: center;
  }
  
  .recommended-projects {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .project-card {
    padding: 15px;
    margin: 15px 0;
  }
  
  .project-header {
    flex-direction: column;
  }
  
  .project-meta {
    margin-top: 10px;
  }
}
</style>

<script>
// Project filtering functionality with improved error handling
function filterProjects(category) {
  const cards = document.querySelectorAll('.project-card');
  const noProjectsMsg = document.getElementById('no-projects');
  const countDisplay = document.getElementById('project-count');
  let visibleCount = 0;

  // Update active filter button
  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.classList.remove('active');
    if (btn.getAttribute('data-filter') === category) {
      btn.classList.add('active');
    }
  });

  // Filter project cards with case-insensitive matching
  cards.forEach(card => {
    const cardCategory = card.getAttribute('data-category');
    const shouldShow = category === 'All' || 
                      cardCategory === category || 
                      cardCategory.toLowerCase() === category.toLowerCase();
    
    if (shouldShow) {
      card.style.display = '';
      card.style.opacity = '1';
      visibleCount++;
    } else {
      card.style.display = 'none';
      card.style.opacity = '0';
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
      : `Showing ${visibleCount} of ${totalProjects} projects in ${category}`;
    countDisplay.textContent = countText;
  }

  // Smooth scroll to projects list after filtering
  setTimeout(() => {
    document.getElementById('projects-list').scrollIntoView({ 
      behavior: 'smooth', 
      block: 'start' 
    });
  }, 100);
}

// Initialize page with all projects visible
document.addEventListener('DOMContentLoaded', function() {
  filterProjects('All');
  
  // Add keyboard navigation for filter buttons
  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.addEventListener('keydown', function(e) {
      if (e.key === 'Enter' || e.key === ' ') {
        e.preventDefault();
        this.click();
      }
    });
  });
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

// Performance optimization: debounce rapid filter clicks
let filterTimeout;
function debouncedFilter(category) {
  clearTimeout(filterTimeout);
  filterTimeout = setTimeout(() => filterProjects(category), 100);
}
</script>

<div style="text-align: center; margin: 40px 0; padding: 20px; border-top: 1px solid #e1e4e8;">
  <a href="{{ site.baseurl }}/" style="background: #0366d6; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: 500;">
    ← Back to Home
  </a>
</div>
