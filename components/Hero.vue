<template>
  <section class="hero" id="home">
    <div class="container">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">
            <span class="title-main">Madee House Software</span>
            <span class="title-accent">Solutions</span>
          </h1>
          <p class="hero-description">
            พัฒนาซอฟต์แวร์และเว็บแอปพลิเคชันที่ทันสมัย ด้วยเทคโนโลยีล่าสุด
            <br>
            สร้างสรรค์โซลูชันที่ตอบโจทย์ธุรกิจของคุณอย่างแท้จริง
          </p>
          <div class="hero-buttons">
            <button class="btn btn-primary">
              <span>เริ่มต้นโปรเจกต์</span>
              <svg class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
            </button>
            <button class="btn btn-secondary">
              <span>ติดต่อเรา</span>
            </button>
          </div>
        </div>
        
        <div class="hero-visual">
          <div class="visual-container">
            <!-- 3D Geometric shapes -->
            <div class="shape-3d shape-cube">
              <div class="cube-face front"></div>
              <div class="cube-face back"></div>
              <div class="cube-face right"></div>
              <div class="cube-face left"></div>
              <div class="cube-face top"></div>
              <div class="cube-face bottom"></div>
            </div>
            
            <div class="shape-3d shape-pyramid">
              <div class="pyramid-face front"></div>
              <div class="pyramid-face back"></div>
              <div class="pyramid-face right"></div>
              <div class="pyramid-face left"></div>
            </div>
            
            <div class="shape-3d shape-cylinder">
              <div class="cylinder-top"></div>
              <div class="cylinder-side"></div>
              <div class="cylinder-bottom"></div>
            </div>
            
            <!-- Floating elements -->
            <div class="floating-element element-1"></div>
            <div class="floating-element element-2"></div>
            <div class="floating-element element-3"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 80px;
  position: relative;
  overflow: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  width: 100%;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  min-height: 600px;
}

.hero-text {
  z-index: 2;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  color: #065f46;
}

.title-main {
  display: block;
}

.title-accent {
  display: block;
  background: linear-gradient(135deg, #10b981, #065f46);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-description {
  font-size: 1.25rem;
  line-height: 1.6;
  color: #374151;
  margin-bottom: 2.5rem;
  max-width: 500px;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
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
  position: relative;
  overflow: hidden;
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

.btn-secondary {
  background: transparent;
  color: #065f46;
  border: 2px solid #10b981;
}

.btn-secondary:hover {
  background: #10b981;
  color: white;
  transform: translateY(-2px);
}

.btn-icon {
  width: 20px;
  height: 20px;
  transition: transform 0.3s ease;
}

.btn-primary:hover .btn-icon {
  transform: translateX(4px);
}

.hero-visual {
  position: relative;
  height: 500px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.visual-container {
  position: relative;
  width: 400px;
  height: 400px;
  perspective: 1000px;
}

.shape-3d {
  position: absolute;
  transform-style: preserve-3d;
  animation: rotate3d 20s linear infinite;
}

.shape-cube {
  width: 100px;
  height: 100px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotateX(45deg) rotateY(45deg);
}

.cube-face {
  position: absolute;
  width: 100px;
  height: 100px;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.8), rgba(6, 95, 70, 0.6));
  border: 2px solid rgba(16, 185, 129, 0.3);
}

.cube-face.front { transform: rotateY(0deg) translateZ(50px); }
.cube-face.back { transform: rotateY(180deg) translateZ(50px); }
.cube-face.right { transform: rotateY(90deg) translateZ(50px); }
.cube-face.left { transform: rotateY(-90deg) translateZ(50px); }
.cube-face.top { transform: rotateX(90deg) translateZ(50px); }
.cube-face.bottom { transform: rotateX(-90deg) translateZ(50px); }

.shape-pyramid {
  width: 80px;
  height: 80px;
  top: 20%;
  right: 10%;
  animation-delay: -5s;
}

.pyramid-face {
  position: absolute;
  background: linear-gradient(135deg, rgba(16, 185, 129, 0.6), rgba(6, 95, 70, 0.4));
  border: 1px solid rgba(16, 185, 129, 0.3);
}

.pyramid-face.front {
  width: 80px;
  height: 80px;
  transform: rotateX(-30deg) translateZ(40px);
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}

.pyramid-face.back {
  width: 80px;
  height: 80px;
  transform: rotateX(-30deg) rotateY(180deg) translateZ(40px);
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}

.pyramid-face.right {
  width: 80px;
  height: 80px;
  transform: rotateY(90deg) rotateX(-30deg) translateZ(40px);
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}

.pyramid-face.left {
  width: 80px;
  height: 80px;
  transform: rotateY(-90deg) rotateX(-30deg) translateZ(40px);
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}

.shape-cylinder {
  width: 60px;
  height: 120px;
  bottom: 20%;
  left: 15%;
  animation-delay: -10s;
}

.cylinder-top, .cylinder-bottom {
  width: 60px;
  height: 60px;
  background: radial-gradient(ellipse, rgba(16, 185, 129, 0.8), rgba(6, 95, 70, 0.6));
  border: 2px solid rgba(16, 185, 129, 0.3);
  border-radius: 50%;
  position: absolute;
}

.cylinder-top {
  top: 0;
  transform: rotateX(90deg) translateZ(30px);
}

.cylinder-bottom {
  bottom: 0;
  transform: rotateX(90deg) translateZ(-30px);
}

.cylinder-side {
  width: 60px;
  height: 120px;
  background: linear-gradient(90deg, rgba(16, 185, 129, 0.6), rgba(6, 95, 70, 0.4), rgba(16, 185, 129, 0.6));
  border: 2px solid rgba(16, 185, 129, 0.3);
  border-radius: 30px;
}

.floating-element {
  position: absolute;
  background: linear-gradient(135deg, #10b981, #065f46);
  border-radius: 50%;
  animation: float 6s ease-in-out infinite;
}

.element-1 {
  width: 20px;
  height: 20px;
  top: 10%;
  right: 20%;
  animation-delay: 0s;
}

.element-2 {
  width: 15px;
  height: 15px;
  bottom: 30%;
  right: 40%;
  animation-delay: 2s;
}

.element-3 {
  width: 12px;
  height: 12px;
  top: 70%;
  left: 20%;
  animation-delay: 4s;
}

@keyframes rotate3d {
  0% {
    transform: translate(-50%, -50%) rotateX(0deg) rotateY(0deg);
  }
  100% {
    transform: translate(-50%, -50%) rotateX(360deg) rotateY(360deg);
  }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

@media (max-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: center;
  }
  
  .hero-title {
    font-size: 3rem;
  }
  
  .visual-container {
    width: 300px;
    height: 300px;
  }
}

@media (max-width: 768px) {
  .container {
    padding: 0 1rem;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-description {
    font-size: 1.1rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .btn {
    padding: 0.875rem 1.5rem;
    font-size: 0.9rem;
  }
  
  .visual-container {
    width: 250px;
    height: 250px;
  }
  
  .shape-cube {
    width: 80px;
    height: 80px;
  }
  
  .cube-face {
    width: 80px;
    height: 80px;
  }
}

@media (max-width: 480px) {
  .hero {
    padding-top: 70px;
  }
  
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-description {
    font-size: 1rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .btn {
    width: 100%;
    max-width: 280px;
    justify-content: center;
  }
}
</style>
