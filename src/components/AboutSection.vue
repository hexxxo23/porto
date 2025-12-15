<template>
  <section id="about" class="about section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">About Me</span>
        <h2>Passionate Backend <span class="gradient-text">Developer</span></h2>
      </div>
      
      <div class="about-content">
        <div class="about-text">
          <p class="about-intro">
            I'm a dedicated Backend Engineer with <strong>2+ years of experience</strong> 
            building robust and scalable server-side applications. My expertise lies in 
            crafting efficient APIs, optimizing database performance, and implementing 
            clean architecture patterns.
          </p>
          
          <div class="about-highlights">
            <div class="highlight-item">
              <div class="highlight-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M12 2L2 7l10 5 10-5-10-5z"/>
                  <path d="M2 17l10 5 10-5"/>
                  <path d="M2 12l10 5 10-5"/>
                </svg>
              </div>
              <div>
                <h4>API Development</h4>
                <p>RESTful APIs with clean architecture and proper documentation</p>
              </div>
            </div>
            
            <div class="highlight-item">
              <div class="highlight-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <ellipse cx="12" cy="5" rx="9" ry="3"/>
                  <path d="M21 12c0 1.66-4 3-9 3s-9-1.34-9-3"/>
                  <path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5"/>
                </svg>
              </div>
              <div>
                <h4>Database Design</h4>
                <p>Optimized database schemas with MySQL and PostgreSQL</p>
              </div>
            </div>
            
            <div class="highlight-item">
              <div class="highlight-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
                </svg>
              </div>
              <div>
                <h4>Security First</h4>
                <p>Authentication systems and secure coding practices</p>
              </div>
            </div>
          </div>
        </div>
        
        <div class="about-card">
          <div class="card-content">
            <div class="card-header">
              <div class="avatar">
                <span>👨‍💻</span>
              </div>
              <div>
                <h3>Backend Engineer</h3>
                <p>Python & Laravel Specialist</p>
              </div>
            </div>
            
            <div class="card-stats">
              <div class="card-stat">
                <span class="stat-icon">🐍</span>
                <span>Python</span>
              </div>
              <div class="card-stat">
                <span class="stat-icon">🔴</span>
                <span>Laravel</span>
              </div>
              <div class="card-stat">
                <span class="stat-icon">🐘</span>
                <span>PHP</span>
              </div>
              <div class="card-stat">
                <span class="stat-icon">🗃️</span>
                <span>MySQL</span>
              </div>
            </div>
            
            <div class="card-divider"></div>
            
            <div class="card-info">
              <div class="info-row">
                <span class="info-label">Experience</span>
                <span class="info-value">2+ Years</span>
              </div>
              <div class="info-row">
                <span class="info-label">Location</span>
                <span class="info-value">Remote Ready</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
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

.about-content {
  display: grid;
  grid-template-columns: 1fr 400px;
  gap: 4rem;
  align-items: start;
}

.about-intro {
  font-size: 1.15rem;
  line-height: 1.9;
  margin-bottom: 2.5rem;
}

.about-intro strong {
  color: var(--text-primary);
}

.about-highlights {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.highlight-item {
  display: flex;
  gap: 1rem;
  padding: 1.25rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  transition: all var(--transition-normal);
}

.highlight-item:hover {
  border-color: var(--accent-primary);
  transform: translateX(8px);
}

.highlight-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent-gradient);
  border-radius: 12px;
  flex-shrink: 0;
}

.highlight-icon svg {
  color: white;
}

.highlight-item h4 {
  font-size: 1rem;
  margin-bottom: 0.25rem;
  color: var(--text-primary);
}

.highlight-item p {
  font-size: 0.875rem;
  color: var(--text-tertiary);
}

/* About Card */
.about-card {
  position: sticky;
  top: 100px;
}

.card-content {
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 24px;
  padding: 2rem;
  box-shadow: var(--shadow-lg);
}

.card-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.avatar {
  width: 64px;
  height: 64px;
  background: var(--accent-gradient);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
}

.card-header h3 {
  font-size: 1.25rem;
  margin-bottom: 0.25rem;
}

.card-header p {
  font-size: 0.9rem;
  color: var(--text-tertiary);
}

.card-stats {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.75rem;
}

.card-stat {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 10px;
  font-size: 0.875rem;
  font-weight: 500;
  transition: all var(--transition-fast);
}

.card-stat:hover {
  border-color: var(--accent-primary);
}

.stat-icon {
  font-size: 1.25rem;
}

.card-divider {
  height: 1px;
  background: var(--border-color);
  margin: 1.5rem 0;
}

.card-info {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.info-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.info-label {
  font-size: 0.875rem;
  color: var(--text-tertiary);
}

.info-value {
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--text-primary);
}

.status-available {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #10b981;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #10b981;
  border-radius: 50%;
  animation: pulse-glow 2s infinite;
}

@media (max-width: 992px) {
  .about-content {
    grid-template-columns: 1fr;
  }
  
  .about-card {
    position: static;
    max-width: 400px;
    margin: 0 auto;
  }
}
</style>
