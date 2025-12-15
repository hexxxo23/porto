<template>
  <section id="projects" class="projects section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Portfolio</span>
        <h2>Featured <span class="gradient-text">Projects</span></h2>
        <p class="section-description">
          A selection of projects I've worked on
        </p>
      </div>
      
      <div class="timeline">
        <div class="timeline-item" v-for="(project, index) in projects" :key="index">
          <div class="timeline-marker">
            <div class="marker-dot"></div>
            <div class="marker-line" v-if="index < projects.length - 1"></div>
          </div>
          
          <div class="timeline-content">
            <div class="project-header">
              <div class="project-company">
                <div class="company-logo" :style="{ background: project.color }">
                  {{ project.logo }}
                </div>
                <div>
                  <h3>{{ project.title }}</h3>
                  <p class="company-name">{{ project.company }}</p>
                </div>
              </div>
              <div class="project-meta">
                <span class="project-date">{{ project.period }}</span>
                <span class="project-type" :class="project.type.replace(/\s+/g, '-')">{{ project.type }}</span>
              </div>
            </div>
            
            <p class="project-description">{{ project.description }}</p>
            
            <ul class="project-achievements">
              <li v-for="(achievement, i) in project.achievements" :key="i">
                <span class="achievement-icon">✓</span>
                {{ achievement }}
              </li>
            </ul>
            
            <div class="project-stack">
              <span class="stack-tag" v-for="tech in project.stack" :key="tech">{{ tech }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const projects = ref([
  {
    title: 'FastAPI Backend System',
    company: 'Aluesa Global Digitek',
    period: 'Nov 2023 - Present',
    type: 'Backend API',
    logo: 'F',
    color: 'linear-gradient(135deg, #6366f1, #8b5cf6)',
    description: 'High-performance backend system built with FastAPI Python for enterprise software products, delivering scalable and efficient API solutions.',
    achievements: [
      'Developed RESTful APIs with FastAPI achieving high throughput and low latency',
      'Implemented async/await patterns for optimal performance',
      'Integrated with PostgreSQL and MSSQL databases for data persistence',
      'Deployed using Docker containers with Nginx as reverse proxy',
    ],
    stack: ['FastAPI', 'Python', 'PostgreSQL', 'MSSQL', 'Docker', 'Nginx'],
  },
  {
    title: 'Odoo ERP Backend Applications',
    company: 'Aluesa Global Digitek',
    period: 'Nov 2023 - Present',
    type: 'ERP System',
    logo: 'O',
    color: 'linear-gradient(135deg, #8b5cf6, #a855f7)',
    description: 'Backend web applications using Odoo framework and Python, integrated with Docker and Nginx for robust enterprise resource planning.',
    achievements: [
      'Created and maintained custom Odoo modules for business processes',
      'Integrated Odoo backend with external systems via REST APIs',
      'Configured Docker containers for development and production environments',
      'Implemented Nginx configuration for load balancing and security',
    ],
    stack: ['Odoo', 'Python', 'Docker', 'Nginx', 'PostgreSQL'],
  },
  {
    title: 'Vendor Management System',
    company: 'Aluesa Global Digitek',
    period: 'Nov 2023 - Present',
    type: 'Full Stack',
    logo: 'V',
    color: 'linear-gradient(135deg, #10b981, #059669)',
    description: 'Comprehensive vendor management application using Laravel PHP for streamlined supplier operations and procurement processes.',
    achievements: [
      'Developing VMS application with Laravel PHP framework',
      'Implementing vendor registration, approval workflows, and contract management',
      'Building database schema with MySQL for vendor data management',
      'Creating REST APIs for vendor data integration with other systems',
    ],
    stack: ['Laravel', 'PHP', 'MySQL', 'REST API'],
  },
  {
    title: 'System Monitoring Infrastructure',
    company: 'Aluesa Global Digitek',
    period: 'Nov 2023 - Present',
    type: 'DevOps',
    logo: 'Z',
    color: 'linear-gradient(135deg, #f59e0b, #d97706)',
    description: 'Comprehensive monitoring solution using Zabbix for system-wide observability and automated alerting mechanisms.',
    achievements: [
      'Configured Zabbix server and deployed agents across infrastructure',
      'Implemented automated error detection systems for service monitoring',
      'Created staff alert mechanisms for service level monitoring',
      'Designed dashboards for real-time system health visualization',
    ],
    stack: ['Zabbix', 'Linux', 'Monitoring', 'Alerting'],
  },
  {
    title: 'Push Voucher Website',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'Full Stack',
    logo: 'P',
    color: 'linear-gradient(135deg, #3b82f6, #1d4ed8)',
    description: 'Full-stack web application for managing voucher distribution with CodeIgniter frontend and Flask-RESTful backend.',
    achievements: [
      'Developed frontend features using CodeIgniter PHP framework',
      'Built RESTful backend services using Python with Flask-RESTful',
      'Integrated frontend and backend for seamless voucher management',
      'Implemented database operations with PostgreSQL',
    ],
    stack: ['CodeIgniter', 'Python', 'Flask-RESTful', 'PostgreSQL'],
  },
  {
    title: 'Order Tracking System',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'Full Stack',
    logo: 'T',
    color: 'linear-gradient(135deg, #ec4899, #be185d)',
    description: 'Customer order tracking application with detailed view features and push API integration for real-time updates.',
    achievements: [
      'Created detailed customer view features using CodeIgniter on frontend',
      'Developed backend code and push APIs using Python with Flask-RESTful',
      'Implemented real-time order status updates and notifications',
      'Designed customer-facing interfaces for order tracking',
    ],
    stack: ['CodeIgniter', 'Python', 'Flask-RESTful', 'Push API'],
  },
  {
    title: 'Alfa Customer Service Website',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'Full Stack',
    logo: 'A',
    color: 'linear-gradient(135deg, #14b8a6, #0d9488)',
    description: 'Customer service platform with enhanced features for customer support and data processing capabilities.',
    achievements: [
      'Enhanced frontend features using CodeIgniter framework',
      'Developed data processing pipelines on the backend using Python',
      'Implemented Flask-RESTful backend for API endpoints',
      'Managed databases using PostgreSQL and MongoDB',
    ],
    stack: ['CodeIgniter', 'Python', 'Flask-RESTful', 'PostgreSQL', 'MongoDB'],
  },
  {
    title: 'GoCorp Website UI Design',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'UI Design',
    logo: 'G',
    color: 'linear-gradient(135deg, #a855f7, #7c3aed)',
    description: 'Complete user interface design for the GoCorp corporate website at PT GLI, focusing on user experience and visual consistency.',
    achievements: [
      'Designed comprehensive UI for GoCorp website',
      'Created wireframes and interactive prototypes',
      'Collaborated with developers for accurate implementation',
      'Ensured visual consistency across all pages',
    ],
    stack: ['UI Design', 'Figma', 'Wireframing', 'Prototyping'],
  },
])
</script>

<style scoped>
.projects {
  background: var(--bg-primary);
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-tag {
  display: inline-block;
  font-family: var(--font-mono);
  font-size: 0.875rem;
  color: var(--accent-primary);
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin-bottom: 1rem;
}

.section-description {
  max-width: 500px;
  margin: 1rem auto 0;
  color: var(--text-tertiary);
}

.timeline {
  max-width: 800px;
  margin: 0 auto;
}

.timeline-item {
  display: flex;
  gap: 2rem;
}

.timeline-marker {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-shrink: 0;
}

.marker-dot {
  width: 16px;
  height: 16px;
  background: var(--accent-gradient);
  border-radius: 50%;
  box-shadow: 0 0 20px rgba(99, 102, 241, 0.4);
  position: relative;
  z-index: 1;
}

.marker-line {
  width: 2px;
  flex: 1;
  background: linear-gradient(to bottom, var(--accent-primary), transparent);
  margin-top: 0.5rem;
}

.timeline-content {
  flex: 1;
  padding-bottom: 3rem;
}

.project-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 1rem;
}

.project-company {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.company-logo {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  font-weight: 700;
  font-size: 1.25rem;
  color: white;
}

.project-company h3 {
  font-size: 1.25rem;
  margin-bottom: 0.25rem;
}

.company-name {
  color: var(--text-secondary);
  font-size: 0.95rem;
}

.project-meta {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 0.5rem;
}

.project-date {
  font-family: var(--font-mono);
  font-size: 0.875rem;
  color: var(--text-tertiary);
}

.project-type {
  padding: 0.25rem 0.75rem;
  border-radius: 100px;
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: capitalize;
}

.project-type.Backend-API {
  background: rgba(99, 102, 241, 0.1);
  color: var(--accent-primary);
  border: 1px solid var(--accent-primary);
}

.project-type.Full-Stack {
  background: rgba(16, 185, 129, 0.1);
  color: #10b981;
  border: 1px solid #10b981;
}

.project-type.ERP-System {
  background: rgba(139, 92, 246, 0.1);
  color: #8b5cf6;
  border: 1px solid #8b5cf6;
}

.project-type.DevOps {
  background: rgba(245, 158, 11, 0.1);
  color: #f59e0b;
  border: 1px solid #f59e0b;
}

.project-type.UI-Design {
  background: rgba(168, 85, 247, 0.1);
  color: #a855f7;
  border: 1px solid #a855f7;
}

.project-description {
  margin-bottom: 1.25rem;
  line-height: 1.7;
}

.project-achievements {
  list-style: none;
  margin-bottom: 1.5rem;
}

.project-achievements li {
  display: flex;
  gap: 0.75rem;
  margin-bottom: 0.5rem;
  font-size: 0.95rem;
  color: var(--text-secondary);
}

.achievement-icon {
  color: #10b981;
  font-weight: 700;
  flex-shrink: 0;
}

.project-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.stack-tag {
  padding: 0.375rem 0.875rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 8px;
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--text-secondary);
}

@media (max-width: 768px) {
  .project-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .project-meta {
    align-items: flex-start;
    flex-direction: row;
    gap: 1rem;
  }
  
  .timeline-item {
    gap: 1rem;
  }
}
</style>
