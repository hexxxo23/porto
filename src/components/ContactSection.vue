<template>
  <section id="contact" class="contact section">
    <div class="container">
      <div class="contact-wrapper">
        <div class="contact-info">
          <span class="section-tag">Get In Touch</span>
          <h2>Let's Work <span class="gradient-text">Together</span></h2>
          <p class="contact-description">
            I'm always open to discussing new projects, creative ideas, 
            or opportunities to be part of your vision. Feel free to reach out!
          </p>
          
          <div class="contact-methods">
            <a href="mailto:luthfisangaji2301@gmail.com" class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                  <polyline points="22,6 12,13 2,6"/>
                </svg>
              </div>
              <div>
                <span class="method-label">Email</span>
                <span class="method-value">luthfisangaji2301@gmail.com</span>
              </div>
            </a>
            
            <a href="https://www.linkedin.com/in/luthfisangaji/" target="_blank" class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/>
                  <rect x="2" y="9" width="4" height="12"/>
                  <circle cx="4" cy="4" r="2"/>
                </svg>
              </div>
              <div>
                <span class="method-label">LinkedIn</span>
                <span class="method-value">Luthfi Sangaji Pramono</span>
              </div>
            </a>
            
            <a href="https://github.com/hexxxo23" target="_blank" class="contact-method">
              <div class="method-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </div>
              <div>
                <span class="method-label">GitHub</span>
                <span class="method-value">@hexxxo23</span>
              </div>
            </a>
          </div>
        </div>
        
        <div class="contact-form-wrapper">
          <form class="contact-form" @submit.prevent="handleSubmit">
            <div class="form-group">
              <label for="name">Your Name</label>
              <input type="text" id="name" v-model="form.name" placeholder="John Doe" required />
            </div>
            
            <div class="form-group">
              <label for="email">Your Email</label>
              <input type="email" id="email" v-model="form.email" placeholder="john@example.com" required />
            </div>
            
            <div class="form-group">
              <label for="subject">Subject</label>
              <input type="text" id="subject" v-model="form.subject" placeholder="Project Discussion" required />
            </div>
            
            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" v-model="form.message" rows="5" placeholder="Tell me about your project..." required></textarea>
            </div>
            
            <button type="submit" class="btn-submit" :class="{ sending: isSending }">
              <span v-if="!isSending">Send Message</span>
              <span v-else>Sending...</span>
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="22" y1="2" x2="11" y2="13"/>
                <polygon points="22 2 15 22 11 13 2 9 22 2"/>
              </svg>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const isSending = ref(false)

const handleSubmit = async () => {
  isSending.value = true
  // Simulate sending
  await new Promise(resolve => setTimeout(resolve, 2000))
  alert('Message sent successfully! (Demo)')
  form.value = { name: '', email: '', subject: '', message: '' }
  isSending.value = false
}
</script>

<style scoped>
.contact {
  background: var(--bg-secondary);
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

.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-description {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-bottom: 2.5rem;
  max-width: 400px;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem 1.25rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 16px;
  text-decoration: none;
  transition: all var(--transition-normal);
}

.contact-method:hover {
  border-color: var(--accent-primary);
  transform: translateX(8px);
}

.method-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--accent-gradient);
  border-radius: 12px;
  color: white;
}

.method-label {
  display: block;
  font-size: 0.8rem;
  color: var(--text-tertiary);
  margin-bottom: 0.25rem;
}

.method-value {
  display: block;
  font-weight: 500;
  color: var(--text-primary);
}

/* Contact Form */
.contact-form-wrapper {
  background: var(--bg-tertiary);
  border: 1px solid var(--border-color);
  border-radius: 24px;
  padding: 2rem;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.form-group label {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--text-secondary);
}

.form-group input,
.form-group textarea {
  padding: 0.875rem 1rem;
  background: var(--bg-glass);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  color: var(--text-primary);
  font-family: inherit;
  font-size: 0.95rem;
  transition: all var(--transition-fast);
  outline: none;
  resize: vertical;
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: var(--text-muted);
}

.form-group input:focus,
.form-group textarea:focus {
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.1);
}

.btn-submit {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  background: var(--accent-gradient);
  color: white;
  border: none;
  border-radius: 12px;
  font-family: inherit;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all var(--transition-normal);
  margin-top: 0.5rem;
}

.btn-submit:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 30px rgba(99, 102, 241, 0.4);
}

.btn-submit.sending {
  opacity: 0.7;
  pointer-events: none;
}

@media (max-width: 992px) {
  .contact-wrapper {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}
</style>
