<template>
  <header class="header">
    <div class="container">
      <!-- Logo -->
      <div class="logo">
        <div class="logo-icon">
          <svg viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="4" y="4" width="32" height="32" rx="8" fill="#065f46"/>
            <rect x="8" y="8" width="8" height="8" rx="2" fill="#10b981"/>
            <rect x="20" y="8" width="8" height="8" rx="2" fill="#10b981"/>
            <rect x="8" y="20" width="20" height="8" rx="2" fill="#10b981"/>
          </svg>
        </div>
        <span class="logo-text">Madee House</span>
      </div>

      <!-- Mobile menu button -->
      <button class="mobile-menu-btn" @click="toggleMobileMenu" :class="{ active: isMobileMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <!-- Navigation -->
      <nav class="nav" :class="{ 'nav-open': isMobileMenuOpen }">
        <ul class="nav-list">
          <li><a href="#home" @click="closeMobileMenu">หน้าแรก</a></li>
          <li><a href="#services" @click="closeMobileMenu">บริการ</a></li>
          <li><a href="#about" @click="closeMobileMenu">เกี่ยวกับเรา</a></li>
          <li><a href="#portfolio" @click="closeMobileMenu">ผลงาน</a></li>
          <li><a href="#contact" @click="closeMobileMenu">ติดต่อเรา</a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(16, 185, 129, 0.1);
  transition: all 0.3s ease;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 80px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  text-decoration: none;
  color: #065f46;
}

.logo-icon {
  width: 40px;
  height: 40px;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
  color: #065f46;
}

.mobile-menu-btn {
  display: none;
  flex-direction: column;
  gap: 4px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 8px;
  z-index: 1001;
}

.mobile-menu-btn span {
  width: 25px;
  height: 3px;
  background: #065f46;
  transition: all 0.3s ease;
  border-radius: 2px;
}

.mobile-menu-btn.active span:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.mobile-menu-btn.active span:nth-child(2) {
  opacity: 0;
}

.mobile-menu-btn.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

.nav-list {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 2rem;
}

.nav-list a {
  text-decoration: none;
  color: #065f46;
  font-weight: 500;
  font-size: 1rem;
  transition: all 0.3s ease;
  padding: 0.5rem 1rem;
  border-radius: 8px;
  position: relative;
}

.nav-list a:hover {
  color: #10b981;
  background: rgba(16, 185, 129, 0.1);
}

.nav-list a::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 50%;
  width: 0;
  height: 2px;
  background: #10b981;
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-list a:hover::after {
  width: 80%;
}

@media (max-width: 768px) {
  .container {
    padding: 0 1rem;
  }

  .mobile-menu-btn {
    display: flex;
  }

  .nav {
    position: fixed;
    top: 80px;
    left: 0;
    right: 0;
    background: rgba(255, 255, 255, 0.98);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(16, 185, 129, 0.1);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
  }

  .nav-open {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }

  .nav-list {
    flex-direction: column;
    padding: 2rem;
    gap: 0;
  }

  .nav-list a {
    padding: 1rem;
    border-bottom: 1px solid rgba(16, 185, 129, 0.1);
    border-radius: 0;
  }

  .nav-list a:last-child {
    border-bottom: none;
  }

  .logo-text {
    font-size: 1.25rem;
  }
}

@media (max-width: 480px) {
  .container {
    height: 70px;
  }

  .nav {
    top: 70px;
  }

  .logo-text {
    font-size: 1.1rem;
  }

  .logo-icon {
    width: 35px;
    height: 35px;
  }
}
</style>
