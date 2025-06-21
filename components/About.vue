<template>
  <section class="about" id="about">
    <div class="container">
      <div class="about-content">
        <div class="about-text">
          <h2 class="section-title">เกี่ยวกับเรา</h2>
          <div class="about-description">
            <p class="lead-text">
              Madee House Software เป็นบริษัทพัฒนาซอฟต์แวร์ที่มุ่งมั่นสร้างสรรค์โซลูชันทางเทคโนโลยี
              ที่ตอบโจทย์ความต้องการของธุรกิจในยุคดิจิทัล
            </p>
            <p>
              ด้วยประสบการณ์กว่า 5 ปีในการพัฒนาซอฟต์แวร์และเว็บแอปพลิเคชัน 
              เราได้ให้บริการลูกค้าหลากหลายประเภทธุรกิจ ตั้งแต่สตาร์ทอัพไปจนถึงองค์กรขนาดใหญ่
            </p>
            <p>
              ทีมงานของเราประกอบด้วยนักพัฒนาซอฟต์แวร์มืออาชีพ นักออกแบบ UX/UI 
              และที่ปรึกษาด้านเทคโนโลยีที่มีความเชี่ยวชาญในเทคโนโลยีล่าสุด
            </p>
          </div>
          
          <div class="stats-grid">
            <div class="stat-item">
              <div class="stat-number">50+</div>
              <div class="stat-label">โปรเจกต์สำเร็จ</div>
            </div>
            <div class="stat-item">
              <div class="stat-number">30+</div>
              <div class="stat-label">ลูกค้าพึงพอใจ</div>
            </div>
            <div class="stat-item">
              <div class="stat-number">5+</div>
              <div class="stat-label">ปีประสบการณ์</div>
            </div>
            <div class="stat-item">
              <div class="stat-number">24/7</div>
              <div class="stat-label">การสนับสนุน</div>
            </div>
          </div>
        </div>
        
        <div class="about-visual">
          <div class="team-illustration">
            <div class="team-member member-1">
              <div class="avatar"></div>
              <div class="member-info">
                <div class="name">Developer</div>
                <div class="role">Full Stack</div>
              </div>
            </div>
            <div class="team-member member-2">
              <div class="avatar"></div>
              <div class="member-info">
                <div class="name">Designer</div>
                <div class="role">UI/UX</div>
              </div>
            </div>
            <div class="team-member member-3">
              <div class="avatar"></div>
              <div class="member-info">
                <div class="name">Manager</div>
                <div class="role">Project</div>
              </div>
            </div>
            
            <!-- Connection lines -->
            <svg class="connection-lines" viewBox="0 0 300 200">
              <defs>
                <linearGradient id="lineGradient" x1="0%" y1="0%" x2="100%" y2="0%">
                  <stop offset="0%" style="stop-color:#10b981;stop-opacity:0.6" />
                  <stop offset="100%" style="stop-color:#065f46;stop-opacity:0.3" />
                </linearGradient>
              </defs>
              <path d="M50,50 Q150,25 250,50" stroke="url(#lineGradient)" stroke-width="2" fill="none"/>
              <path d="M50,150 Q150,125 250,150" stroke="url(#lineGradient)" stroke-width="2" fill="none"/>
              <path d="M150,50 L150,150" stroke="url(#lineGradient)" stroke-width="2" fill="none"/>
            </svg>
          </div>
        </div>
      </div>
      
      <div class="values-section">
        <h3 class="values-title">ค่านิยมของเรา</h3>
        <div class="values-grid">
          <div class="value-item">
            <div class="value-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M9 12l2 2 4-4"/>
                <path d="M21 12c-1 0-3-1-3-3s2-3 3-3 3 1 3 3-2 3-3 3"/>
                <path d="M3 12c1 0 3-1 3-3s-2-3-3-3-3 1-3 3 2 3 3 3"/>
                <path d="M3 12c0 5.5 4.5 10 10 10s10-4.5 10-10"/>
              </svg>
            </div>
            <h4>คุณภาพ</h4>
            <p>มุ่งมั่นส่งมอบผลงานที่มีคุณภาพสูงสุด</p>
          </div>
          <div class="value-item">
            <div class="value-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>
              </svg>
            </div>
            <h4>นวัตกรรม</h4>
            <p>ใช้เทคโนโลยีล่าสุดในการพัฒนา</p>
          </div>
          <div class="value-item">
            <div class="value-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/>
                <circle cx="9" cy="7" r="4"/>
                <path d="M23 21v-2a4 4 0 0 0-3-3.87"/>
                <path d="M16 3.13a4 4 0 0 1 0 7.75"/>
              </svg>
            </div>
            <h4>ความร่วมมือ</h4>
            <p>ทำงานร่วมกับลูกค้าอย่างใกล้ชิด</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 6rem 0;
  background: white;
  position: relative;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #065f46;
  margin-bottom: 2rem;
  position: relative;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, #10b981, #065f46);
  border-radius: 2px;
}

.lead-text {
  font-size: 1.25rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.about-description p {
  color: #6b7280;
  line-height: 1.7;
  margin-bottom: 1.5rem;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  margin-top: 2rem;
}

.stat-item {
  text-align: center;
  padding: 1.5rem;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.05), rgba(6, 95, 70, 0.02));
  border-radius: 12px;
  border: 1px solid rgba(16, 185, 129, 0.1);
}

.stat-number {
  font-size: 2rem;
  font-weight: 800;
  color: #10b981;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  color: #6b7280;
  font-weight: 500;
}

.about-visual {
  position: relative;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.team-illustration {
  position: relative;
  width: 300px;
  height: 200px;
}

.team-member {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.member-1 {
  top: 0;
  left: 50%;
  transform: translateX(-50%);
}

.member-2 {
  bottom: 0;
  left: 0;
}

.member-3 {
  bottom: 0;
  right: 0;
}

.avatar {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: linear-gradient(135deg, #10b981, #065f46);
  position: relative;
  animation: pulse 3s ease-in-out infinite;
}

.avatar::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 40px;
  height: 40px;
  background: white;
  border-radius: 50%;
}

.member-info {
  text-align: center;
}

.name {
  font-weight: 600;
  color: #065f46;
  font-size: 0.9rem;
}

.role {
  font-size: 0.8rem;
  color: #6b7280;
}

.connection-lines {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.values-section {
  text-align: center;
}

.values-title {
  font-size: 2rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 3rem;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.value-item {
  padding: 2rem;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.05), rgba(6, 95, 70, 0.02));
  border-radius: 16px;
  border: 1px solid rgba(16, 185, 129, 0.1);
  transition: all 0.3s ease;
}

.value-item:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 25px rgba(16, 185, 129, 0.1);
}

.value-icon {
  width: 60px;
  height: 60px;
  margin: 0 auto 1rem;
  background: linear-gradient(135deg, #10b981, #065f46);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}

.value-icon svg {
  width: 28px;
  height: 28px;
}

.value-item h4 {
  font-size: 1.25rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 0.75rem;
}

.value-item p {
  color: #6b7280;
  line-height: 1.6;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

@media (max-width: 1024px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: center;
  }
  
  .section-title::after {
    left: 50%;
    transform: translateX(-50%);
  }
}

@media (max-width: 768px) {
  .about {
    padding: 4rem 0;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .stats-grid {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .values-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .team-illustration {
    width: 250px;
    height: 150px;
  }
  
  .avatar {
    width: 50px;
    height: 50px;
  }
  
  .avatar::before {
    width: 32px;
    height: 32px;
  }
}

@media (max-width: 480px) {
  .about {
    padding: 3rem 0;
  }
  
  .section-title {
    font-size: 1.8rem;
  }
  
  .values-title {
    font-size: 1.6rem;
  }
  
  .value-item {
    padding: 1.5rem;
  }
}
</style>
