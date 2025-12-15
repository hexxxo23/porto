<template>
  <section id="skills" class="skills section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Tech Stack</span>
        <h2>Skills & <span class="gradient-text">Technologies</span></h2>
        <p class="section-description">
          Technologies I use to bring products to life
        </p>
      </div>
      
      <div class="skills-grid">
        <!-- Languages & Frameworks -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">💻</span>
            Languages & Frameworks
          </h3>
          <div class="skill-list">
            <div class="skill-item" v-for="skill in languages" :key="skill.name">
              <div class="skill-icon" :style="{ background: skill.color }">
                <span>{{ skill.icon }}</span>
              </div>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <div class="skill-bar">
                  <div class="skill-progress" :style="{ width: skill.level + '%', background: skill.color }"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Databases -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">🗃️</span>
            Databases
          </h3>
          <div class="skill-list">
            <div class="skill-item" v-for="skill in databases" :key="skill.name">
              <div class="skill-icon" :style="{ background: skill.color }">
                <span>{{ skill.icon }}</span>
              </div>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <div class="skill-bar">
                  <div class="skill-progress" :style="{ width: skill.level + '%', background: skill.color }"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Tools & DevOps -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">🛠️</span>
            Tools & DevOps
          </h3>
          <div class="skill-list">
            <div class="skill-item" v-for="skill in tools" :key="skill.name">
              <div class="skill-icon" :style="{ background: skill.color }">
                <span>{{ skill.icon }}</span>
              </div>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <div class="skill-bar">
                  <div class="skill-progress" :style="{ width: skill.level + '%', background: skill.color }"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Concepts -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">🧠</span>
            Concepts & Practices
          </h3>
          <div class="concept-tags">
            <span class="concept-tag" v-for="concept in concepts" :key="concept">
              {{ concept }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const languages = ref([
  { name: 'Python', icon: '🐍', level: 90, color: '#3776ab' },
  { name: 'FastAPI', icon: '⚡', level: 88, color: '#009688' },
  { name: 'PHP', icon: '🐘', level: 85, color: '#777bb4' },
  { name: 'Laravel', icon: '🔺', level: 85, color: '#ff2d20' },
  { name: 'Flask-RESTful', icon: '🌶️', level: 82, color: '#000000' },
  { name: 'Odoo', icon: '🔧', level: 80, color: '#875a7b' },
  { name: 'CodeIgniter', icon: '🔥', level: 78, color: '#ee4323' },
  { name: 'Vue.js', icon: '💚', level: 75, color: '#4fc08d' },
])

const databases = ref([
  { name: 'PostgreSQL', icon: '🐘', level: 88, color: '#336791' },
  { name: 'MySQL', icon: '🐬', level: 88, color: '#4479a1' },
  { name: 'MSSQL', icon: '📊', level: 80, color: '#cc2927' },
  { name: 'MongoDB', icon: '🍃', level: 78, color: '#47a248' },
])

const tools = ref([
  { name: 'Docker', icon: '🐳', level: 88, color: '#2496ed' },
  { name: 'Nginx', icon: '🌐', level: 85, color: '#009639' },
  { name: 'Git', icon: '📦', level: 90, color: '#f05032' },
  { name: 'Zabbix', icon: '📡', level: 82, color: '#d40000' },
  { name: 'Linux', icon: '🐧', level: 85, color: '#fcc624' },
  { name: 'Figma', icon: '🎨', level: 75, color: '#f24e1e' },
])

const concepts = ref([
  'REST APIs',
  'Error Detection & Monitoring',
  'Service Level Monitoring',
  'System Administration',
  'ERP Systems',
  'Vendor Management',
  'Database Management',
  'Data Processing',
  'Push API Integration',
  'UI/UX Design',
  'Containerization',
  'Web Server Configuration',
])
</script>

<style scoped>
.skills {
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

.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
}

.skill-category {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 20px;
  padding: 1.75rem;
  transition: all var(--transition-normal);
}

.skill-category:hover {
  border-color: var(--accent-primary);
  box-shadow: var(--shadow-glow);
}

.category-title {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 1.1rem;
  margin-bottom: 1.5rem;
  color: var(--text-primary);
}

.category-icon {
  font-size: 1.5rem;
}

.skill-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.skill-item {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.skill-icon {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  font-size: 1.25rem;
  flex-shrink: 0;
}

.skill-info {
  flex: 1;
}

.skill-name {
  font-size: 0.9rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  display: block;
}

.skill-bar {
  height: 6px;
  background: var(--bg-tertiary);
  border-radius: 3px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  border-radius: 3px;
  transition: width 1s ease;
}

.concept-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.concept-tag {
  padding: 0.5rem 1rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 100px;
  font-size: 0.85rem;
  color: var(--text-secondary);
  transition: all var(--transition-fast);
}

.concept-tag:hover {
  border-color: var(--accent-primary);
  color: var(--accent-primary);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
