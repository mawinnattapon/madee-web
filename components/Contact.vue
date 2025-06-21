<template>
  <section class="contact" id="contact">
    <div class="container">
      <div class="contact-header">
        <h2 class="section-title">ติดต่อเรา</h2>
        <p class="section-description">
          พร้อมให้คำปรึกษาและรับฟังความต้องการของคุณ เริ่มต้นโปรเจกต์ใหม่กับเราวันนี้
        </p>
      </div>
      
      <div class="contact-content">
        <div class="contact-info">
          <div class="info-item">
            <div class="info-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
            </div>
            <div class="info-content">
              <h4>ที่อยู่</h4>
              <p>898/301 โครงการเดอะมิราเคิล ซอยประชาอุทิศ 90 <br>ต. คลองสวน อ.พระสมุทรเจดีย์ จ.สมุทรปราการ 10290</p>
            </div>
          </div>
          
          <div class="info-item">
            <div class="info-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
              </svg>
            </div>
            <div class="info-content">
              <h4>โทรศัพท์</h4>
              <p>0970949815</p>
            </div>
          </div>
          
          <div class="info-item">
            <div class="info-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                <polyline points="22,6 12,13 2,6"/>
              </svg>
            </div>
            <div class="info-content">
              <h4>อีเมล</h4>
              <p>mawinnattapon@gmail.com</p>
            </div>
          </div>
          
          <div class="info-item">
            <div class="info-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <polyline points="12,6 12,12 16,14"/>
              </svg>
            </div>
            <div class="info-content">
              <h4>เวลาทำการ</h4>
              <p>จันทร์ - ศุกร์: 9:00 - 18:00</p>
            </div>
          </div>
        </div>
        
        <div class="contact-form">
          <form @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">ชื่อ - นามสกุล *</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name" 
                required
                placeholder="กรุณากรอกชื่อของคุณ"
              >
            </div>
            
            <div class="form-row">
              <div class="form-group">
                <label for="email">อีเมล *</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="form.email" 
                  required
                  placeholder="your@email.com"
                >
              </div>
              
              <div class="form-group">
                <label for="phone">เบอร์โทรศัพท์</label>
                <input 
                  type="tel" 
                  id="phone" 
                  v-model="form.phone"
                  placeholder="08X-XXX-XXXX"
                >
              </div>
            </div>
            
            <div class="form-group">
              <label for="company">บริษัท/องค์กร</label>
              <input 
                type="text" 
                id="company" 
                v-model="form.company"
                placeholder="ชื่อบริษัทหรือองค์กรของคุณ"
              >
            </div>
            
            <div class="form-group">
              <label for="service">ประเภทบริการที่สนใจ</label>
              <select id="service" v-model="form.service">
                <option value="">เลือกบริการ</option>
                <option value="web">เว็บแอปพลิเคชัน</option>
                <option value="mobile">แอปมือถือ</option>
                <option value="custom">ซอฟต์แวร์เฉพาะทาง</option>
                <option value="consultation">ปรึกษาโปรเจกต์</option>
              </select>
            </div>
            
            <div class="form-group">
              <label for="budget">งบประมาณโดยประมาณ</label>
              <select id="budget" v-model="form.budget">
                <option value="">เลือกช่วงงบประมาณ</option>
                <option value="50k-100k">50,000 - 100,000 บาท</option>
                <option value="100k-300k">100,000 - 300,000 บาท</option>
                <option value="300k-500k">300,000 - 500,000 บาท</option>
                <option value="500k+">มากกว่า 500,000 บาท</option>
              </select>
            </div>
            
            <div class="form-group">
              <label for="message">รายละเอียดโปรเจกต์ *</label>
              <textarea 
                id="message" 
                v-model="form.message" 
                required
                rows="5"
                placeholder="บอกเราเกี่ยวกับโปรเจกต์ของคุณ ความต้องการ และเป้าหมายที่ต้องการบรรลุ"
              ></textarea>
            </div>
            
            <button type="submit" class="btn btn-primary" :disabled="isSubmitting">
              <span v-if="!isSubmitting">ส่งข้อความ</span>
              <span v-else>กำลังส่ง...</span>
              <svg v-if="!isSubmitting" class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
                <path d="M10.894 2.553a1 1 0 00-1.788 0l-7 14a1 1 0 001.169 1.409l5-1.429A1 1 0 009 15.571V11a1 1 0 112 0v4.571a1 1 0 00.725.962l5 1.428a1 1 0 001.17-1.408l-7-14z"/>
              </svg>
            </button>
          </form>
        </div>
      </div>
      
      <div class="contact-map">
        <div class="map-placeholder">
          <div class="map-content">
            <div class="map-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                <circle cx="12" cy="10" r="3"/>
              </svg>
            </div>
            <p>แผนที่ตำแหน่งสำนักงาน</p>
            <span>123 ถนนเทคโนโลยี แขวงนวัตกรรม เขตดิจิทัล กรุงเทพฯ</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

const isSubmitting = ref(false)

const form = reactive({
  name: '',
  email: '',
  phone: '',
  company: '',
  service: '',
  budget: '',
  message: ''
})

const submitForm = async () => {
  isSubmitting.value = true
  
  // Simulate form submission
  try {
    await new Promise(resolve => setTimeout(resolve, 2000))
    
    // In a real app, you would send the form data to your backend
    console.log('Form submitted:', form)
    
    // Reset form
    Object.keys(form).forEach(key => {
      form[key] = ''
    })
    
    alert('ขอบคุณสำหรับข้อความของคุณ เราจะติดต่อกลับโดยเร็วที่สุด!')
    
  } catch (error) {
    console.error('Error submitting form:', error)
    alert('เกิดข้อผิดพลาดในการส่งข้อความ กรุณาลองใหม่อีกครั้ง')
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style scoped>
.contact {
  padding: 6rem 0;
  background: white;
  position: relative;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.contact-header {
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

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-bottom: 4rem;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.info-item {
  display: flex;
  gap: 1rem;
  padding: 1.5rem;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.05), rgba(6, 95, 70, 0.02));
  border-radius: 16px;
  border: 1px solid rgba(16, 185, 129, 0.1);
  transition: all 0.3s ease;
}

.info-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(16, 185, 129, 0.1);
}

.info-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #10b981, #065f46);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.info-icon svg {
  width: 24px;
  height: 24px;
}

.info-content h4 {
  font-size: 1.1rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 0.5rem;
}

.info-content p {
  color: #6b7280;
  line-height: 1.6;
}

.contact-form {
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.05), rgba(6, 95, 70, 0.02));
  padding: 2rem;
  border-radius: 20px;
  border: 1px solid rgba(16, 185, 129, 0.1);
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group label {
  display: block;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 0.5rem;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 0.875rem 1rem;
  border: 2px solid rgba(16, 185, 129, 0.2);
  border-radius: 8px;
  font-size: 1rem;
  transition: all 0.3s ease;
  background: white;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #10b981;
  box-shadow: 0 0 0 3px rgba(16, 185, 129, 0.1);
}

.form-group textarea {
  resize: vertical;
  min-height: 120px;
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
  width: 100%;
  justify-content: center;
}

.btn-primary {
  background: linear-gradient(135deg, #10b981, #065f46);
  color: white;
  box-shadow: 0 4px 15px rgba(16, 185, 129, 0.3);
}

.btn-primary:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(16, 185, 129, 0.4);
}

.btn-primary:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.btn-icon {
  width: 20px;
  height: 20px;
  transition: transform 0.3s ease;
}

.btn-primary:hover:not(:disabled) .btn-icon {
  transform: translateX(4px);
}

.contact-map {
  margin-top: 2rem;
}

.map-placeholder {
  height: 300px;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.1), rgba(6, 95, 70, 0.05));
  border-radius: 20px;
  border: 2px dashed rgba(16, 185, 129, 0.3);
  display: flex;
  align-items: center;
  justify-content: center;
}

.map-content {
  text-align: center;
  color: #6b7280;
}

.map-icon {
  width: 60px;
  height: 60px;
  margin: 0 auto 1rem;
  background: linear-gradient(135deg, #10b981, #065f46);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}

.map-icon svg {
  width: 30px;
  height: 30px;
}

.map-content p {
  font-size: 1.1rem;
  font-weight: 600;
  color: #065f46;
  margin-bottom: 0.5rem;
}

.map-content span {
  font-size: 0.9rem;
  color: #9ca3af;
}

@media (max-width: 1024px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
}

@media (max-width: 768px) {
  .contact {
    padding: 4rem 0;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
  }
  
  .contact-form {
    padding: 1.5rem;
  }
  
  .info-item {
    padding: 1rem;
  }
}

@media (max-width: 480px) {
  .contact {
    padding: 3rem 0;
  }
  
  .section-title {
    font-size: 1.8rem;
  }
  
  .contact-form {
    padding: 1rem;
  }
  
  .map-placeholder {
    height: 200px;
  }
}
</style>
