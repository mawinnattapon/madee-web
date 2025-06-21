<template>
  <div class="background-container">
    <!-- Geometric shapes -->
    <div class="geometric-shape shape-1"></div>
    <div class="geometric-shape shape-2"></div>
    <div class="geometric-shape shape-3"></div>
    
    <!-- Circuit lines -->
    <svg class="circuit-lines" viewBox="0 0 1920 1080" preserveAspectRatio="xMidYMid slice">
      <defs>
        <linearGradient id="circuitGradient" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" style="stop-color:#10b981;stop-opacity:0.1" />
          <stop offset="100%" style="stop-color:#065f46;stop-opacity:0.05" />
        </linearGradient>
      </defs>
      <path d="M0,200 Q400,100 800,200 T1600,200" stroke="url(#circuitGradient)" stroke-width="2" fill="none" opacity="0.3"/>
      <path d="M200,0 Q300,400 600,300 T1200,400" stroke="url(#circuitGradient)" stroke-width="1.5" fill="none" opacity="0.2"/>
      <path d="M1920,800 Q1500,600 1200,800 T400,800" stroke="url(#circuitGradient)" stroke-width="1" fill="none" opacity="0.15"/>
    </svg>
    
    <!-- Floating particles -->
    <div class="particle particle-1"></div>
    <div class="particle particle-2"></div>
    <div class="particle particle-3"></div>
    <div class="particle particle-4"></div>
  </div>
</template>

<style scoped>
.background-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  overflow: hidden;
  background: linear-gradient(135deg, #f0fdf4 0%, #ecfdf5 50%, #f0fdf4 100%);
}

.geometric-shape {
  position: absolute;
  border-radius: 20px;
  background: linear-gradient(45deg, rgba(16, 185, 129, 0.1), rgba(6, 95, 70, 0.05));
  animation: float 6s ease-in-out infinite;
}

.shape-1 {
  width: 200px;
  height: 200px;
  top: 10%;
  right: 10%;
  transform: rotate(45deg);
  animation-delay: 0s;
}

.shape-2 {
  width: 150px;
  height: 150px;
  bottom: 20%;
  left: 5%;
  transform: rotate(-30deg);
  animation-delay: 2s;
}

.shape-3 {
  width: 100px;
  height: 100px;
  top: 60%;
  right: 20%;
  transform: rotate(60deg);
  animation-delay: 4s;
}

.circuit-lines {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.4;
}

.particle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: #10b981;
  border-radius: 50%;
  animation: particle-float 8s linear infinite;
}

.particle-1 {
  top: 20%;
  left: 10%;
  animation-delay: 0s;
}

.particle-2 {
  top: 70%;
  left: 80%;
  animation-delay: 2s;
}

.particle-3 {
  top: 40%;
  left: 60%;
  animation-delay: 4s;
}

.particle-4 {
  top: 80%;
  left: 30%;
  animation-delay: 6s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px) rotate(45deg);
  }
  50% {
    transform: translateY(-20px) rotate(45deg);
  }
}

@keyframes particle-float {
  0% {
    transform: translateY(0px);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    transform: translateY(-100vh);
    opacity: 0;
  }
}

@media (max-width: 768px) {
  .shape-1 {
    width: 120px;
    height: 120px;
  }
  
  .shape-2 {
    width: 100px;
    height: 100px;
  }
  
  .shape-3 {
    width: 80px;
    height: 80px;
  }
}
</style>
