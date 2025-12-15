<template>
  <section id="hero" class="hero">
    <!-- Animated Background -->
    <div class="hero-bg">
      <div class="gradient-orb orb-1"></div>
      <div class="gradient-orb orb-2"></div>
      <div class="grid-overlay"></div>
    </div>

    <div class="container hero-content">
      <div class="hero-text">
        <div class="badge animate-fade-in-up">
          <span class="badge-dot"></span>
          Available for opportunities
        </div>
        
        <h1 class="hero-title animate-fade-in-up animate-delay-1">
          Hi, I'm <span class="gradient-text">Luthfi Sangaji Pramono</span>
        </h1>
        
        <div class="typing-container animate-fade-in-up animate-delay-2">
          <span class="typing-text">{{ currentText }}</span>
          <span class="cursor">|</span>
        </div>
        
        <p class="hero-description animate-fade-in-up animate-delay-3">
          Passionate about building scalable APIs, robust database architectures, 
          and clean server-side solutions. 2+ years of crafting efficient backend 
          systems with <strong>Python</strong> and <strong>PHP/Laravel</strong>.
        </p>
        
        <div class="hero-actions animate-fade-in-up animate-delay-4">
          <a href="#projects" class="btn btn-primary">
            <span>View Projects</span>
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
          <a href="#contact" class="btn btn-secondary">
            <span>Get In Touch</span>
          </a>
        </div>
        
        <div class="hero-stats animate-fade-in-up animate-delay-5">
          <div class="stat">
            <span class="stat-number">2+</span>
            <span class="stat-label">Years Experience</span>
          </div>
          <div class="stat">
            <span class="stat-number">10+</span>
            <span class="stat-label">Projects Completed</span>
          </div>
          <div class="stat">
            <span class="stat-number">5+</span>
            <span class="stat-label">Happy Clients</span>
          </div>
        </div>
      </div>
      
      <div class="hero-visual animate-fade-in-up animate-delay-3">
        <div class="code-window">
          <div class="window-header">
            <div class="window-dots">
              <span class="dot red"></span>
              <span class="dot yellow"></span>
              <span class="dot green"></span>
            </div>
            <span class="window-title">backend_engineer.py</span>
          </div>
          <pre class="code-content"><code><span class="keyword">class</span> <span class="class-name">BackendEngineer</span>:
    <span class="keyword">def</span> <span class="function">__init__</span>(<span class="param">self</span>):
        <span class="param">self</span>.name = <span class="string">"Luthfi Sangaji Pramono"</span>
        <span class="param">self</span>.role = <span class="string">"Backend Engineer @ Aluesa"</span>
        <span class="param">self</span>.skills = [
            <span class="string">"Python"</span>, <span class="string">"Laravel"</span>,
            <span class="string">"REST APIs"</span>, <span class="string">"MySQL"</span>
        ]
    
    <span class="keyword">def</span> <span class="function">build</span>(<span class="param">self</span>, project):
        <span class="keyword">return</span> <span class="string">f"Scalable solution ✨"</span></code></pre>
        </div>
      </div>
    </div>
    
    <div class="scroll-indicator">
      <div class="mouse">
        <div class="wheel"></div>
      </div>
      <span>Scroll Down</span>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const words = ['Building RESTful APIs', 'Designing Databases', 'Writing Clean Code', 'Optimizing Performance']
const currentText = ref('')
let wordIndex = 0
let charIndex = 0
let isDeleting = false
let typeInterval = null

const type = () => {
  const currentWord = words[wordIndex]
  
  if (isDeleting) {
    currentText.value = currentWord.substring(0, charIndex - 1)
    charIndex--
  } else {
    currentText.value = currentWord.substring(0, charIndex + 1)
    charIndex++
  }
  
  if (!isDeleting && charIndex === currentWord.length) {
    setTimeout(() => { isDeleting = true }, 1500)
  } else if (isDeleting && charIndex === 0) {
    isDeleting = false
    wordIndex = (wordIndex + 1) % words.length
  }
}

onMounted(() => {
  typeInterval = setInterval(type, isDeleting ? 50 : 100)
})

onUnmounted(() => {
  if (typeInterval) clearInterval(typeInterval)
})
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 80px;
}

.hero-bg {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.gradient-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.4;
}

.orb-1 {
  width: 600px;
  height: 600px;
  background: var(--accent-primary);
  top: -200px;
  right: -200px;
  animation: float 8s ease-in-out infinite;
}

.orb-2 {
  width: 400px;
  height: 400px;
  background: var(--accent-secondary);
  bottom: -100px;
  left: -100px;
  animation: float 6s ease-in-out infinite reverse;
}

.grid-overlay {
  position: absolute;
  inset: 0;
  background-image: 
    linear-gradient(rgba(99, 102, 241, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(99, 102, 241, 0.03) 1px, transparent 1px);
  background-size: 60px 60px;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 1;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 100px;
  font-size: 0.875rem;
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
}

.badge-dot {
  width: 8px;
  height: 8px;
  background: #10b981;
  border-radius: 50%;
  animation: pulse-glow 2s infinite;
}

.hero-title {
  margin-bottom: 1rem;
}

.typing-container {
  font-family: var(--font-mono);
  font-size: 1.25rem;
  color: var(--accent-primary);
  margin-bottom: 1.5rem;
  min-height: 2rem;
}

.cursor {
  animation: blink 1s infinite;
}

.hero-description {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-bottom: 2rem;
  max-width: 540px;
}

.hero-description strong {
  color: var(--text-primary);
}

.hero-actions {
  display: flex;
  gap: 1rem;
  margin-bottom: 3rem;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.875rem 1.75rem;
  border-radius: 12px;
  font-weight: 600;
  font-size: 0.95rem;
  text-decoration: none;
  transition: all var(--transition-normal);
  cursor: pointer;
  border: none;
}

.btn-primary {
  background: var(--accent-gradient);
  color: white;
  box-shadow: 0 4px 20px rgba(99, 102, 241, 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(99, 102, 241, 0.4);
}

.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-color);
}

.btn-secondary:hover {
  background: var(--bg-glass);
  border-color: var(--accent-primary);
}

.hero-stats {
  display: flex;
  gap: 3rem;
}

.stat {
  display: flex;
  flex-direction: column;
}

.stat-number {
  font-size: 2rem;
  font-weight: 800;
  background: var(--accent-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-label {
  font-size: 0.875rem;
  color: var(--text-tertiary);
}

/* Code Window */
.hero-visual {
  display: flex;
  justify-content: center;
}

.code-window {
  background: var(--bg-secondary);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  overflow: hidden;
  width: 100%;
  max-width: 480px;
  box-shadow: var(--shadow-lg), var(--shadow-glow);
  animation: float 6s ease-in-out infinite;
}

.window-header {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.875rem 1rem;
  background: var(--bg-tertiary);
  border-bottom: 1px solid var(--border-color);
}

.window-dots {
  display: flex;
  gap: 6px;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.dot.red { background: #ff5f56; }
.dot.yellow { background: #ffbd2e; }
.dot.green { background: #27ca3f; }

.window-title {
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--text-tertiary);
}

.code-content {
  padding: 1.5rem;
  font-family: var(--font-mono);
  font-size: 0.85rem;
  line-height: 1.7;
  overflow-x: auto;
}

.code-content code {
  display: block;
}

.keyword { color: #c678dd; }
.class-name { color: #e5c07b; }
.function { color: #61afef; }
.param { color: #e06c75; }
.string { color: #98c379; }

/* Scroll Indicator */
.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  color: var(--text-tertiary);
  font-size: 0.8rem;
}

.mouse {
  width: 24px;
  height: 38px;
  border: 2px solid var(--text-tertiary);
  border-radius: 12px;
  display: flex;
  justify-content: center;
  padding-top: 8px;
}

.wheel {
  width: 4px;
  height: 8px;
  background: var(--accent-primary);
  border-radius: 2px;
  animation: float 1.5s infinite;
}

@media (max-width: 992px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .hero-description {
    margin-left: auto;
    margin-right: auto;
  }
  
  .hero-actions {
    justify-content: center;
  }
  
  .hero-stats {
    justify-content: center;
  }
  
  .hero-visual {
    order: -1;
  }
  
  .code-window {
    max-width: 400px;
  }
}

@media (max-width: 576px) {
  .hero-stats {
    flex-direction: column;
    gap: 1.5rem;
  }
  
  .hero-actions {
    flex-direction: column;
  }
  
  .btn {
    width: 100%;
    justify-content: center;
  }
}
</style>
