<template>
  <section class="services" id="services">
    <div class="container">
      <div class="services-header">
        <h2 class="section-title">บริการของเรา</h2>
        <p class="section-description">
          เราให้บริการพัฒนาซอฟต์แวร์ครบวงจร ด้วยทีมงานมืออาชีพและเทคโนโลยีทันสมัย
        </p>
      </div>
      
      <div class="services-grid">
        <div class="service-card" v-for="(service, index) in services" :key="index">
          <div class="service-icon">
            <div class="icon-container" v-html="service.icon"></div>
          </div>
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-description">{{ service.description }}</p>
          <div class="service-features">
            <ul>
              <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    title: 'Web Application',
    description: 'พัฒนาเว็บแอปพลิเคชันที่ทันสมัย รองรับการใช้งานบนทุกอุปกรณ์',
    icon: `
      <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="4" y="8" width="56" height="40" rx="4" fill="#10b981" opacity="0.2"/>
        <rect x="4" y="8" width="56" height="8" rx="4" fill="#065f46"/>
        <circle cx="12" cy="12" r="2" fill="#10b981"/>
        <circle cx="20" cy="12" r="2" fill="#10b981"/>
        <circle cx="28" cy="12" r="2" fill="#10b981"/>
        <rect x="8" y="20" width="48" height="4" rx="2" fill="#10b981" opacity="0.6"/>
        <rect x="8" y="28" width="32" height="4" rx="2" fill="#10b981" opacity="0.4"/>
        <rect x="8" y="36" width="40" height="4" rx="2" fill="#10b981" opacity="0.3"/>
        <rect x="44" y="52" width="16" height="8" rx="2" fill="#065f46"/>
      </svg>
    `,
    features: [
      'Responsive Design',
      'Modern UI/UX',
      'Fast Performance',
      'SEO Optimized'
    ]
  },
  {
    title: 'Mobile Application',
    description: 'สร้างแอปพลิเคชันมือถือที่ใช้งานง่าย และมีประสิทธิภาพสูง',
    icon: `
      <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="18" y="4" width="28" height="56" rx="6" fill="#065f46"/>
        <rect x="22" y="12" width="20" height="36" rx="2" fill="#10b981" opacity="0.3"/>
        <rect x="24" y="16" width="16" height="3" rx="1.5" fill="#10b981"/>
        <rect x="24" y="22" width="12" height="3" rx="1.5" fill="#10b981" opacity="0.7"/>
        <rect x="24" y="28" width="14" height="3" rx="1.5" fill="#10b981" opacity="0.5"/>
        <rect x="24" y="34" width="10" height="3" rx="1.5" fill="#10b981" opacity="0.6"/>
        <circle cx="32" cy="52" r="3" fill="#10b981"/>
        <rect x="28" y="8" width="8" height="2" rx="1" fill="#10b981" opacity="0.8"/>
      </svg>
    `,
    features: [
      'iOS & Android',
      'Native Performance',
      'Push Notifications',
      'Offline Support'
    ]
  },
  {
    title: 'Custom Software',
    description: 'พัฒนาซอฟต์แวร์เฉพาะทาง ตามความต้องการของธุรกิจ',
    icon: `
      <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="8" y="8" width="48" height="32" rx="4" fill="#065f46"/>
        <rect x="12" y="12" width="40" height="24" rx="2" fill="#000" opacity="0.8"/>
        <text x="16" y="20" fill="#10b981" font-family="monospace" font-size="4">&lt;/&gt;</text>
        <text x="16" y="26" fill="#10b981" font-family="monospace" font-size="4">code</text>
        <text x="16" y="32" fill="#10b981" font-family="monospace" font-size="4">{ }</text>
        <rect x="4" y="44" width="56" height="4" rx="2" fill="#10b981" opacity="0.3"/>
        <rect x="12" y="52" width="40" height="4" rx="2" fill="#065f46"/>
        <circle cx="20" cy="54" r="1" fill="#10b981"/>
        <circle cx="26" cy="54" r="1" fill="#10b981"/>
        <circle cx="32" cy="54" r="1" fill="#10b981"/>
      </svg>
    `,
    features: [
      'Custom Solutions',
      'Scalable Architecture',
      'API Integration',
      'Database Design'
    ]
  }
]
</script>

<style scoped>
.services {
  padding: 6rem 0;
  background: linear-gradient(135deg, #f9fafb 0%, #f3f4f6 100%);
  position: relative;
}

.services::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(16, 185, 129, 0.3), transparent);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.services-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #065f46;
  margin-bottom: 1rem;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, #10b981, #065f46);
  border-radius: 2px;
}

.section-description {
  font-size: 1.2rem;
  color: #6b7280;
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.service-card {
  background: white;
  padding: 2.5rem;
  border-radius: 20px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  border: 1px solid rgba(16, 185, 129, 0.1);
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #10b981, #065f46);
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 40px rgba(16, 185, 129, 0.15);
}

.service-icon {
  margin-bottom: 1.5rem;
}

.icon-container {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.1), rgba(6, 95, 70, 0.05));
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  transition: all 0.3s ease;
}

.service-card:hover .icon-container {
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.2), rgba(6, 95, 70, 0.1));
  transform: scale(1.1);
}

.icon-container svg {
  width: 48px;
  height: 48px;
}

.service-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 1rem;
  text-align: center;
}

.service-description {
  color: #6b7280;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  text-align: center;
}

.service-features ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.service-features li {
  padding: 0.5rem 0;
  color: #374151;
  position: relative;
  padding-left: 1.5rem;
}

.service-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #10b981;
  font-weight: bold;
}

@media (max-width: 768px) {
  .services {
    padding: 4rem 0;
  }

  .container {
    padding: 0 1rem;
  }

  .section-title {
    font-size: 2rem;
  }

  .section-description {
    font-size: 1.1rem;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .service-card {
    padding: 2rem;
  }

  .icon-container {
    width: 70px;
    height: 70px;
  }

  .icon-container svg {
    width: 40px;
    height: 40px;
  }

  .service-title {
    font-size: 1.3rem;
  }
}

@media (max-width: 480px) {
  .services {
    padding: 3rem 0;
  }

  .section-title {
    font-size: 1.8rem;
  }

  .service-card {
    padding: 1.5rem;
  }

  .icon-container {
    width: 60px;
    height: 60px;
  }

  .icon-container svg {
    width: 36px;
    height: 36px;
  }
}
</style>
