<template>
  <div class="page">
    <Background />
    <Header />
    <Hero />
    <Services />
    <About />
    <Portfolio />
    <Contact />
  </div>
</template>

<script setup>
// Import components
import Background from '~/components/Background.vue'
import Header from '~/components/Header.vue'
import Hero from '~/components/Hero.vue'
import Services from '~/components/Services.vue'
import About from '~/components/About.vue'
import Portfolio from '~/components/Portfolio.vue'
import Contact from '~/components/Contact.vue'

// Set page meta
useHead({
  title: 'Madee House Software - พัฒนาซอฟต์แวร์และเว็บแอปพลิเคชัน',
  meta: [
    {
      name: 'description',
      content: 'บริษัทพัฒนาซอฟต์แวร์และเว็บแอปพลิเคชันที่ทันสมัย ด้วยเทคโนโลยีล่าสุด สร้างสรรค์โซลูชันที่ตอบโจทย์ธุรกิจของคุณ'
    },
    {
      name: 'keywords',
      content: 'พัฒนาซอฟต์แวร์, เว็บแอปพลิเคชัน, แอปมือถือ, Madee House Software'
    },
    {
      property: 'og:title',
      content: 'Madee House Software - พัฒนาซอฟต์แวร์และเว็บแอปพลิเคชัน'
    },
    {
      property: 'og:description',
      content: 'บริษัทพัฒนาซอฟต์แวร์และเว็บแอปพลิเคชันที่ทันสมัย ด้วยเทคโนโลยีล่าสุด'
    },
    {
      property: 'og:type',
      content: 'website'
    }
  ]
})
</script>

<style>
/* Global styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: #374151;
  overflow-x: hidden;
}

.page {
  position: relative;
  min-height: 100vh;
}

/* Smooth scrolling for anchor links */
html {
  scroll-padding-top: 80px;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f5f9;
}

::-webkit-scrollbar-thumb {
  background: #10b981;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #065f46;
}

/* Selection color */
::selection {
  background: rgba(16, 185, 129, 0.2);
  color: #065f46;
}

/* Focus styles */
button:focus,
a:focus {
  outline: 2px solid #10b981;
  outline-offset: 2px;
}

/* Utility classes */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
</style>