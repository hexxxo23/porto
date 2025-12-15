<template>
  <section id="experience" class="experience section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Career Path</span>
        <h2>Work <span class="gradient-text">Experience</span></h2>
      </div>
      
      <div class="timeline">
        <div class="timeline-item" v-for="(exp, index) in experiences" :key="index">
          <div class="timeline-marker">
            <div class="marker-dot"></div>
            <div class="marker-line" v-if="index < experiences.length - 1"></div>
          </div>
          
          <div class="timeline-content">
            <div class="exp-header">
              <div class="exp-company">
                <div class="company-logo" :style="{ background: exp.color }">
                  {{ exp.logo }}
                </div>
                <div>
                  <h3>{{ exp.role }}</h3>
                  <p class="company-name">{{ exp.company }}</p>
                </div>
              </div>
              <div class="exp-meta">
                <span class="exp-date">{{ exp.period }}</span>
                <span class="exp-type" :class="exp.type">{{ exp.type }}</span>
              </div>
            </div>
            
            <p class="exp-description">{{ exp.description }}</p>
            
            <ul class="exp-achievements">
              <li v-for="(achievement, i) in exp.achievements" :key="i">
                <span class="achievement-icon">✓</span>
                {{ achievement }}
              </li>
            </ul>
            
            <div class="exp-stack">
              <span class="stack-tag" v-for="tech in exp.stack" :key="tech">{{ tech }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const experiences = ref([
  {
    role: 'Back End Engineer',
    company: 'Aluesa Global Digitek',
    period: 'Nov 2023 - Present',
    type: 'Full-time',
    logo: 'A',
    color: 'linear-gradient(135deg, #6366f1, #8b5cf6)',
    description: 'Spearheading backend development for enterprise software products, building scalable applications and implementing robust monitoring solutions in Bandung, West Java.',
    achievements: [
      'Spearheaded backend development using FastAPI (Python) for high-performance software products',
      'Architected and maintained backend web applications using Odoo and Python, integrated with Docker and Nginx',
      'Implemented comprehensive error detection systems and automated staff alert mechanisms for service-level monitoring',
      'Configured and managed Zabbix monitoring infrastructure including agent deployment for system-wide observability',
      'Developing vendor management system application using Laravel PHP for streamlined supplier operations',
      'Designed and maintained database management systems using PostgreSQL, MSSQL, and MySQL to support diverse application requirements',
    ],
    stack: ['FastAPI', 'Python', 'Odoo', 'Laravel', 'PHP', 'Docker', 'Nginx', 'Zabbix', 'PostgreSQL', 'MSSQL', 'MySQL'],
  },
  {
    role: 'Application Developer Intern',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'Internship',
    logo: 'G',
    color: 'linear-gradient(135deg, #10b981, #059669)',
    description: 'Contributed to multiple full-stack projects developing customer-facing applications and internal tools for one of Indonesia\'s largest retail loyalty programs.',
    achievements: [
      'Developed and enhanced features for the Push Voucher website project, implementing frontend components using CodeIgniter',
      'Built RESTful backend services using Python with Flask-RESTful framework for the Push Voucher platform',
      'Created detailed customer view features for the Order Tracking project using CodeIgniter on the frontend',
      'Developed backend code and push APIs using Python with Flask-RESTful for the Order Tracking website',
      'Enhanced the Alfa Customer Service website with new features on the frontend using CodeIgniter',
      'Implemented data processing pipelines on the backend using Python with Flask-RESTful framework',
      'Managed and optimized databases using PostgreSQL and MongoDB for various project requirements',
    ],
    stack: ['Python', 'Flask-RESTful', 'CodeIgniter', 'Vue.js', 'PostgreSQL', 'MongoDB'],
  },
  {
    role: 'Quality Assurance Intern',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'Internship',
    logo: 'G',
    color: 'linear-gradient(135deg, #f59e0b, #d97706)',
    description: 'Ensured software quality through systematic testing methodologies while gaining hands-on experience in the QA lifecycle.',
    achievements: [
      'Executed comprehensive test cases to identify and document software defects',
      'Collaborated with development teams to ensure high-quality product releases',
      'Participated in quality assurance processes and testing best practices',
    ],
    stack: ['Manual Testing', 'Test Documentation', 'Bug Tracking'],
  },
  {
    role: 'UI Designer',
    company: 'Alfagift - Global Loyalty Indonesia',
    period: 'Mar 2022 - Mar 2023',
    type: 'Internship',
    logo: 'G',
    color: 'linear-gradient(135deg, #ec4899, #be185d)',
    description: 'Created user interface designs for corporate web applications, focusing on user experience and visual consistency.',
    achievements: [
      'Designed the complete UI for the GoCorp website at PT GLI, ensuring intuitive user experience',
      'Created wireframes and mockups following modern UI/UX design principles',
      'Collaborated with developers to ensure accurate implementation of design specifications',
    ],
    stack: ['UI Design', 'Figma', 'Wireframing', 'Prototyping'],
  },
])
</script>

<style scoped>
.experience {
  background: var(--bg-secondary);
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

.exp-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 1rem;
}

.exp-company {
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

.exp-company h3 {
  font-size: 1.25rem;
  margin-bottom: 0.25rem;
}

.company-name {
  color: var(--text-secondary);
  font-size: 0.95rem;
}

.exp-meta {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 0.5rem;
}

.exp-date {
  font-family: var(--font-mono);
  font-size: 0.875rem;
  color: var(--text-tertiary);
}

.exp-type {
  padding: 0.25rem 0.75rem;
  border-radius: 100px;
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: capitalize;
}

.exp-type.Full-time {
  background: rgba(99, 102, 241, 0.1);
  color: var(--accent-primary);
  border: 1px solid var(--accent-primary);
}

.exp-type.Internship {
  background: rgba(16, 185, 129, 0.1);
  color: #10b981;
  border: 1px solid #10b981;
}

.exp-description {
  margin-bottom: 1.25rem;
  line-height: 1.7;
}

.exp-achievements {
  list-style: none;
  margin-bottom: 1.5rem;
}

.exp-achievements li {
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

.exp-stack {
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
  .exp-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .exp-meta {
    align-items: flex-start;
    flex-direction: row;
    gap: 1rem;
  }
  
  .timeline-item {
    gap: 1rem;
  }
}
</style>
