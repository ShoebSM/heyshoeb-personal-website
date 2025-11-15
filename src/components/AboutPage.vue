<script setup lang="ts">
</script>

<template>
  <div class="about-page">
    <div class="about-header">
      <h1>About Me</h1>
      <p class="intro">Get to know me a bit better</p>
    </div>

    <div class="about-content">
      <div class="about-text">
        <h2>Who I Am</h2>
        <p>
          I'm a passionate full-stack developer with a love for creating elegant solutions to complex
          problems. With years of experience in web development, I've honed my skills across the entire
          stack, from front-end UI design to back-end architecture.
        </p>

        <h2>My Journey</h2>
        <p>
          My journey into tech started with a curiosity about how things work. From building my first
          website to architecting scalable applications, I've grown tremendously. I believe in continuous
          learning and staying updated with the latest technologies and best practices.
        </p>

        <h2>What I Do</h2>
        <p>
          I specialize in building modern, responsive web applications that provide excellent user
          experiences. Whether it's crafting beautiful interfaces or designing robust backend systems,
          I'm committed to delivering high-quality solutions that make a difference.
        </p>

        <h2>Beyond Code</h2>
        <p>
          When I'm not coding, you can find me exploring new technologies, contributing to open-source
          projects, or enjoying the great outdoors. I'm always eager to collaborate and learn from
          others in the tech community.
        </p>
      </div>

      <div class="about-stats">
        <div class="stat-box">
          <div class="stat-number">5+</div>
          <div class="stat-label">Years of Experience</div>
        </div>
        <div class="stat-box">
          <div class="stat-number">20+</div>
          <div class="stat-label">Projects Completed</div>
        </div>
        <div class="stat-box">
          <div class="stat-number">10+</div>
          <div class="stat-label">Technologies Mastered</div>
        </div>
        <div class="stat-box">
          <div class="stat-number">100%</div>
          <div class="stat-label">Dedication</div>
        </div>
      </div>
    </div>

    <div class="values-section">
      <h2>My Values</h2>
      <div class="values-grid">
        <div class="value-card">
          <div class="value-icon">💡</div>
          <h3>Innovation</h3>
          <p>Always seeking better solutions and new approaches</p>
        </div>
        <div class="value-card">
          <div class="value-icon">🤝</div>
          <h3>Collaboration</h3>
          <p>Strong believer in teamwork and open communication</p>
        </div>
        <div class="value-card">
          <div class="value-icon">📚</div>
          <h3>Continuous Learning</h3>
          <p>Passionate about growing and staying current</p>
        </div>
        <div class="value-card">
          <div class="value-icon">✨</div>
          <h3>Quality</h3>
          <p>Committed to excellence in everything I do</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-page {
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

.about-header {
  text-align: center;
  margin-bottom: 4rem;
  padding: 3rem 2rem;
  border-radius: 12px;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.05) 0%, rgba(123, 97, 255, 0.05) 100%);
  border: 1px solid rgba(0, 212, 255, 0.2);
}

.about-header h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.intro {
  font-size: 1.3rem;
  color: #a0a0a0;
}

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 3rem;
  margin-bottom: 5rem;
}

.about-text h2 {
  font-size: 1.8rem;
  color: #00d4ff;
  margin-top: 2rem;
  margin-bottom: 1rem;
}

.about-text p {
  color: #b0b0b0;
  line-height: 1.8;
  margin-bottom: 1rem;
  font-size: 1.05rem;
}

.about-stats {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}

.stat-box {
  background: rgba(0, 212, 255, 0.1);
  border: 1px solid rgba(0, 212, 255, 0.3);
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
  transition: all 0.3s ease;
}

.stat-box:hover {
  background: rgba(0, 212, 255, 0.15);
  transform: translateY(-5px);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 0.5rem;
}

.stat-label {
  color: #a0a0a0;
  font-size: 0.95rem;
}

.values-section {
  text-align: center;
}

.values-section h2 {
  font-size: 2.5rem;
  margin-bottom: 3rem;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
}

.value-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 2rem;
  border-radius: 12px;
  transition: all 0.3s ease;
}

.value-card:hover {
  background: rgba(0, 212, 255, 0.1);
  border-color: rgba(0, 212, 255, 0.5);
  transform: translateY(-5px);
}

.value-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.value-card h3 {
  font-size: 1.2rem;
  color: #00d4ff;
  margin-bottom: 0.5rem;
}

.value-card p {
  color: #a0a0a0;
  font-size: 0.95rem;
}

@media (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
  }

  .about-header h1 {
    font-size: 2rem;
  }

  .about-text h2 {
    font-size: 1.4rem;
  }

  .values-grid {
    grid-template-columns: 1fr;
  }
}
</style>
