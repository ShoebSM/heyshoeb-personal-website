<script setup lang="ts">
defineProps<{
  modelValue?: string
}>()
</script>

<template>
  <div class="home-page">
    <div class="hero">
      <div class="avatar">👨‍💻</div>
      <h1 class="hero-title">Hey, I'm Shoeb</h1>
      <p class="hero-subtitle">Full Stack Developer | Creative Problem Solver</p>
      <p class="hero-description">
        I build beautiful, functional web applications that solve real-world problems.
        Welcome to my corner of the internet!
      </p>
      <div class="cta-buttons">
        <button class="btn btn-primary">View My Work</button>
        <button class="btn btn-secondary">Get In Touch</button>
      </div>
    </div>

    <div class="skills-section">
      <h2>Skills & Technologies</h2>
      <div class="skills-grid">
        <div class="skill-card">
          <div class="skill-icon">🎨</div>
          <h3>Frontend</h3>
          <p>Vue.js, React, TypeScript, Tailwind CSS</p>
        </div>
        <div class="skill-card">
          <div class="skill-icon">⚙️</div>
          <h3>Backend</h3>
          <p>Node.js, Express, Python, Databases</p>
        </div>
        <div class="skill-card">
          <div class="skill-icon">📱</div>
          <h3>Mobile</h3>
          <p>Responsive Design, Progressive Web Apps</p>
        </div>
        <div class="skill-card">
          <div class="skill-icon">🛠️</div>
          <h3>Tools</h3>
          <p>Git, Docker, CI/CD, Cloud Deployment</p>
        </div>
      </div>
    </div>

    <div class="featured-section">
      <h2>Featured Work</h2>
      <div class="featured-preview">
        <p>Check out my portfolio to see some of my recent projects.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home-page {
  animation: fadeIn 0.6s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero {
  text-align: center;
  margin-bottom: 6rem;
  padding: 3rem 2rem;
  border-radius: 12px;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.05) 0%, rgba(123, 97, 255, 0.05) 100%);
  border: 1px solid rgba(0, 212, 255, 0.2);
}

.avatar {
  font-size: 5rem;
  margin-bottom: 2rem;
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: 1.5rem;
  color: #00d4ff;
  margin-bottom: 1rem;
  font-weight: 500;
}

.hero-description {
  font-size: 1.1rem;
  color: #b0b0b0;
  max-width: 600px;
  margin: 0 auto 2rem;
  line-height: 1.6;
}

.cta-buttons {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 8px;
  border: none;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-primary {
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  color: #000;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
}

.btn-secondary {
  background: transparent;
  color: #00d4ff;
  border: 2px solid #00d4ff;
}

.btn-secondary:hover {
  background: rgba(0, 212, 255, 0.1);
  transform: translateY(-2px);
}

.skills-section {
  margin-bottom: 6rem;
}

.skills-section h2 {
  font-size: 2.5rem;
  margin-bottom: 3rem;
  text-align: center;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.skill-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 2rem;
  border-radius: 12px;
  text-align: center;
  transition: all 0.3s ease;
  cursor: pointer;
}

.skill-card:hover {
  background: rgba(0, 212, 255, 0.1);
  border-color: rgba(0, 212, 255, 0.5);
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
}

.skill-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.skill-card h3 {
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  color: #00d4ff;
}

.skill-card p {
  color: #a0a0a0;
  font-size: 0.95rem;
}

.featured-section {
  text-align: center;
}

.featured-section h2 {
  font-size: 2.5rem;
  margin-bottom: 2rem;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.featured-preview {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 3rem;
  border-radius: 12px;
  color: #b0b0b0;
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2rem;
  }

  .hero-subtitle {
    font-size: 1.2rem;
  }

  .cta-buttons {
    flex-direction: column;
  }

  .btn {
    width: 100%;
  }
}
</style>
