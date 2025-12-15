<template>
  <header class="header" :class="{ scrolled: isScrolled }">
    <div class="container header-content">
      <a href="#" class="logo">
        <span class="logo-bracket">&lt;</span>
        <span class="logo-text">Dev</span>
        <span class="logo-bracket">/&gt;</span>
      </a>
      
      <nav class="nav" :class="{ active: mobileMenuOpen }">
        <a href="#about" class="nav-link" @click="closeMenu">About</a>
        <a href="#skills" class="nav-link" @click="closeMenu">Skills</a>
        <a href="#experience" class="nav-link" @click="closeMenu">Experience</a>
        <a href="#projects" class="nav-link" @click="closeMenu">Projects</a>
        <a href="#contact" class="nav-link" @click="closeMenu">Contact</a>
      </nav>

      <button class="mobile-toggle" @click="toggleMenu" aria-label="Toggle menu">
        <span :class="{ active: mobileMenuOpen }"></span>
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const mobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMenu = () => {
  mobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 1rem 0;
  transition: all var(--transition-normal);
}

.header.scrolled {
  background: rgba(10, 10, 15, 0.9);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border-color);
  padding: 0.75rem 0;
}

.header-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-family: var(--font-mono);
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.125rem;
}

.logo-bracket {
  color: var(--accent-primary);
}

.logo-text {
  background: var(--accent-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: var(--text-secondary);
  font-size: 0.9rem;
  font-weight: 500;
  text-decoration: none;
  position: relative;
  transition: color var(--transition-fast);
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--accent-gradient);
  transition: width var(--transition-normal);
}

.nav-link:hover {
  color: var(--text-primary);
}

.nav-link:hover::after {
  width: 100%;
}

.mobile-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  width: 28px;
  height: 24px;
  position: relative;
}

.mobile-toggle span,
.mobile-toggle span::before,
.mobile-toggle span::after {
  display: block;
  width: 100%;
  height: 2px;
  background: var(--text-primary);
  position: absolute;
  transition: all var(--transition-normal);
}

.mobile-toggle span {
  top: 50%;
  transform: translateY(-50%);
}

.mobile-toggle span::before {
  content: '';
  top: -8px;
}

.mobile-toggle span::after {
  content: '';
  top: 8px;
}

.mobile-toggle span.active {
  background: transparent;
}

.mobile-toggle span.active::before {
  top: 0;
  transform: rotate(45deg);
}

.mobile-toggle span.active::after {
  top: 0;
  transform: rotate(-45deg);
}

@media (max-width: 768px) {
  .mobile-toggle {
    display: block;
  }

  .nav {
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
    background: rgba(10, 10, 15, 0.98);
    backdrop-filter: blur(20px);
    flex-direction: column;
    padding: 2rem;
    gap: 1.5rem;
    transform: translateY(-100%);
    opacity: 0;
    pointer-events: none;
    transition: all var(--transition-normal);
  }

  .nav.active {
    transform: translateY(0);
    opacity: 1;
    pointer-events: auto;
  }

  .nav-link {
    font-size: 1.1rem;
  }
}
</style>
