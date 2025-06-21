<template>
  <section class="portfolio" id="portfolio">
    <div class="container">
      <div class="portfolio-header">
        <h2 class="section-title">ผลงานของเรา</h2>
        <p class="section-description">
          ชมผลงานที่เราภูมิใจ จากโปรเจกต์ที่หลากหลายและประสบความสำเร็จ
        </p>
      </div>
      
      <div class="portfolio-filters">
        <button 
          v-for="filter in filters" 
          :key="filter.id"
          @click="activeFilter = filter.id"
          :class="['filter-btn', { active: activeFilter === filter.id }]"
        >
          {{ filter.name }}
        </button>
      </div>
      
      <div class="portfolio-grid">
        <div 
          v-for="project in filteredProjects" 
          :key="project.id"
          class="project-card"
          @click="openProject(project)"
        >
          <!-- <div class="project-image">
            <div class="image-placeholder" :style="{ background: project.color }">
              <div class="project-icon" v-html="project.icon"></div>
            </div>
          </div> -->
          <div class="project-content">
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="project-tags">
              <span v-for="tag in project.tags" :key="tag" class="project-tag">
                {{ tag }}
              </span>
            </div>
            <!-- <div class="project-tech">
              <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
                {{ tech }}
              </span>
            </div> -->
          </div>
          <div class="project-overlay">
            <div class="overlay-content">
              <h4>{{ project.title }}</h4>
              <p>{{ project.description }}</p>
              <!-- <div class="project-tech">
                <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
                  {{ tech }}
                </span>
              </div> -->
            </div>
          </div>
        </div>
      </div>
      
      <div class="portfolio-cta">
        <p>มีโปรเจกต์ที่น่าสนใจ?</p>
        <button class="btn btn-primary">
          <span>ปรึกษาโปรเจกต์</span>
          <svg class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

const activeFilter = ref('all')

const filters = [
  { id: 'all', name: 'ทั้งหมด' },
  // { id: 'web', name: 'เว็บแอป' },
  // { id: 'mobile', name: 'แอปมือถือ' },
  // { id: 'custom', name: 'ซอฟต์แวร์เฉพาะ' }
]

const projects = ref([
  {
    id: 1,
    title: 'ระบบบริหารจัดการทรัพยากรบุคคล',
    description: 'ระบบบริหารจัดการพนักงานครบวงจร ตั้งแต่การสมัครงาน การจัดการข้อมูลพนักงาน ระบบลาออนไลน์ และการประเมินผลงาน',
    category: 'web',
    tags: ['การจัดการ', 'พนักงาน', 'ระบบองค์กร', 'ประเมินผลงาน', 'ประวัติบุคลากร'],
    technologies: ['Vue.js', 'Node.js', 'MySQL', 'Express'],
    image: '/api/placeholder/400/250'
  },
  {
    id: 2,
    title: 'แพลตฟอร์มจัดหางาน AI Job Matching',
    description: 'ระบบจัดหางาน AI Job Matching สำหรับอำนวยความสะดวกในการทำธุรกรรม ประหยัดเวลา และรองรับการใช้งานจำนวนมาก',
    category: 'web',
    tags: ['จัดหางาน', 'AI Job Matching', 'สร้าง resume', 'ประกาศงาน'],
    technologies: ['React', 'Python', 'PostgreSQL', 'AI/ML'],
    image: '/api/placeholder/400/250'
  },
  {
    id: 3,
    title: 'ระบบจัดการทรัพย์สิน',
    description: 'ระบบบริหารจัดการทรัพย์สิน ทะเบียนครุภัณฑ์ การตรวจสอบสภาพ และการบำรุงรักษาอุปกรณ์ขององค์กร',
    category: 'web',
    tags: ['ข้อมูลทรัพย์สิน', 'การตรวจสอบครุภัณฑ์', 'ประวัติการซ่อม'],
    technologies: ['Laravel', 'Vue.js', 'MySQL', 'Bootstrap'],
    image: '/api/placeholder/400/250'
  },
  {
    id: 4,
    title: 'ระบบบริหารจัดการบุคลากร',
    description: 'ระบบบริหารบุคลากรสำหรับมหาวิทยาลัย รองรับการจัดการข้อมูลอาจารย์ เจ้าหน้าที่ และการประเมินผลการปฏิบัติงาน',
    category: 'web',
    tags: ['ข้อมูลบุคลากร', 'โครงสร้างองค์กร', 'การประเมินผลการปฏิบัติงาน', 'สวัสดิการ'],
    technologies: ['PHP', 'JavaScript', 'MySQL', 'CSS'],
    image: '/api/placeholder/400/250'
  },
  {
    id: 5,
    title: 'ระบบเงินเดือน',
    description: 'ระบบจัดการเงินเดือนสำหรับมหาวิทยาลัย รองรับการจัดการข้อมูลเงินเดือน ค่าจ้าง และการคำนวนเงินเดือน',
    category: 'web',
    tags: ['ข้อมูลเงินเดือน', 'ค่าจ้าง', 'การคำนวนเงินเดือน', 'ภาษี'],
    technologies: ['PHP', 'JavaScript', 'MySQL', 'CSS'],
    image: '/api/placeholder/400/250'
  },
  {
    id: 6,
    title: 'ระบบออกใบอนุญาตและแจ้งนำเข้า - ส่งออกระหว่างประเทศ',
    description: 'ระบบออกใบอนุญาตและแจ้งนำเข้า - ส่งออกระหว่างประเทศ',
    category: 'web',
    tags: ['ใบอนุญาต', 'แจ้งนำเข้า - ส่งออก', 'รับ - ส่งข้อมูลกับกรมศุลกากร', 'รายงานการนำเข้า - ส่งออก'],
    technologies: ['Vue.js', 'Laravel', 'MySQL', 'Redis'],
    image: '/api/placeholder/400/250'
  }
])

const filteredProjects = computed(() => {
  if (activeFilter.value === 'all') {
    return projects.value
  }
  return projects.value.filter(project => project.category === activeFilter.value)
})

const openProject = (project) => {
  // In a real app, this would open a modal or navigate to project details
  console.log('Opening project:', project.title)
}
</script>

<style scoped>
.portfolio {
  padding: 6rem 0;
  background: linear-gradient(135deg, #f9fafb 0%, #f3f4f6 100%);
  position: relative;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.portfolio-header {
  text-align: center;
  margin-bottom: 3rem;
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

.portfolio-filters {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.filter-btn {
  padding: 0.75rem 1.5rem;
  border: 2px solid rgba(16, 185, 129, 0.2);
  background: white;
  color: #6b7280;
  border-radius: 25px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
}

.filter-btn:hover {
  border-color: #10b981;
  color: #10b981;
}

.filter-btn.active {
  background: linear-gradient(135deg, #10b981, #065f46);
  color: white;
  border-color: transparent;
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.project-card {
  position: relative;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.1), rgba(6, 95, 70, 0.05));
  border-radius: 16px;
  overflow: hidden;
  transition: all 0.3s ease;
  cursor: pointer;
  border: 1px solid rgba(16, 185, 129, 0.2);
  padding: 1.5rem;
  height: 300px;
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(16, 185, 129, 0.2);
  border-color: rgba(16, 185, 129, 0.4);
}

.project-image {
  width: 100%;
  height: 120px;
  background: linear-gradient(135deg, #10b981, #065f46);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
  position: relative;
  overflow: hidden;
}

.project-image::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.1'%3E%3Ccircle cx='30' cy='30' r='4'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E") repeat;
  opacity: 0.3;
}

.project-icon {
  width: 60px;
  height: 60px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  z-index: 1;
  position: relative;
}

.project-icon svg {
  width: 32px;
  height: 32px;
}

.project-content {
  flex: 1;
  display: flex;
  flex-direction: column;
}

.project-content h3 {
  font-size: 1.2rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 0.5rem;
  line-height: 1.4;
}

.project-content p {
  color: #6b7280;
  font-size: 0.9rem;
  line-height: 1.5;
  margin-bottom: 1rem;
  flex: 1;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.project-tag {
  background: rgba(16, 185, 129, 0.1);
  color: #065f46;
  padding: 0.25rem 0.5rem;
  border-radius: 6px;
  font-size: 0.75rem;
  font-weight: 500;
  border: 1px solid rgba(16, 185, 129, 0.2);
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.25rem;
}

.tech-tag {
  background: linear-gradient(135deg, #10b981, #065f46);
  color: white;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  font-size: 0.7rem;
  font-weight: 500;
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.95), rgba(6, 95, 70, 0.95));
  color: white;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  opacity: 0;
  transition: all 0.3s ease;
  border-radius: 16px;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.overlay-content h4 {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.overlay-content p {
  font-size: 0.9rem;
  line-height: 1.5;
  margin-bottom: 1rem;
  color: rgba(255, 255, 255, 0.9);
}

.overlay-content .project-tech {
  margin-top: auto;
}

.overlay-content .tech-tag {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.portfolio-cta {
  text-align: center;
  padding: 3rem 0;
  background: white;
  border-radius: 20px;
  border: 1px solid rgba(16, 185, 129, 0.1);
}

.portfolio-cta p {
  font-size: 1.25rem;
  color: #6b7280;
  margin-bottom: 1.5rem;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-weight: 600;
  font-size: 1rem;
  text-decoration: none;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-primary {
  background: linear-gradient(135deg, #10b981, #065f46);
  color: white;
  box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(16, 185, 129, 0.4);
}

.btn-icon {
  width: 20px;
  height: 20px;
  transition: transform 0.3s ease;
}

.btn-primary:hover .btn-icon {
  transform: translateX(4px);
}

@media (max-width: 768px) {
  .portfolio {
    padding: 4rem 0;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .portfolio-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .portfolio-filters {
    gap: 0.5rem;
  }
  
  .filter-btn {
    padding: 0.5rem 1rem;
    font-size: 0.9rem;
  }
}

@media (max-width: 480px) {
  .portfolio {
    padding: 3rem 0;
  }
  
  .section-title {
    font-size: 1.8rem;
  }
  
  .project-content {
    padding: 1rem;
  }
  
  .portfolio-cta {
    padding: 2rem 1rem;
  }
}
</style>
