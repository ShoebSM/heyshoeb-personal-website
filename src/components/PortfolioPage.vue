<script setup lang="ts">
import { ref } from 'vue'

const projects = ref([
  {
    id: 1,
    title: 'E-Commerce Platform',
    description: 'A full-featured e-commerce platform with payment integration and real-time inventory management.',
    tags: ['Vue.js', 'Node.js', 'MongoDB', 'Stripe'],
    image: '🛒',
  },
  {
    id: 2,
    title: 'Task Management App',
    description: 'A collaborative task management application with real-time updates and team collaboration features.',
    tags: ['React', 'Firebase', 'Tailwind CSS'],
    image: '✅',
  },
  {
    id: 3,
    title: 'Analytics Dashboard',
    description: 'Interactive data visualization dashboard with real-time analytics and custom reporting.',
    tags: ['Vue.js', 'D3.js', 'Express', 'PostgreSQL'],
    image: '📊',
  },
  {
    id: 4,
    title: 'Social Media App',
    description: 'A social networking platform with messaging, notifications, and user profiles.',
    tags: ['React Native', 'Node.js', 'MongoDB'],
    image: '👥',
  },
  {
    id: 5,
    title: 'AI Content Generator',
    description: 'Tool for generating content using AI with customizable templates and export options.',
    tags: ['Next.js', 'OpenAI', 'TypeScript'],
    image: '🤖',
  },
  {
    id: 6,
    title: 'Weather Application',
    description: 'Beautiful weather app with location-based forecasts and detailed weather information.',
    tags: ['Vue.js', 'REST API', 'Geolocation'],
    image: '🌤️',
  },
])
</script>

<template>
  <div class="portfolio-page">
    <div class="portfolio-header">
      <h1>Portfolio</h1>
      <p class="intro">Showcase of my recent projects and work</p>
    </div>

    <div class="portfolio-content">
      <div class="projects-grid">
        <div v-for="project in projects" :key="project.id" class="project-card">
          <div class="project-image">{{ project.image }}</div>
          <h3>{{ project.title }}</h3>
          <p class="project-description">{{ project.description }}</p>
          <div class="project-tags">
            <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
          <button class="view-btn">View Project</button>
        </div>
      </div>
    </div>

    <div class="cta-section">
      <h2>Interested in working together?</h2>
      <p>Let's discuss your project and how I can help bring your ideas to life.</p>
      <button class="cta-btn">Get In Touch</button>
    </div>
  </div>
</template>

<style scoped>
.portfolio-page {
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

.portfolio-header {
  text-align: center;
  margin-bottom: 4rem;
  padding: 3rem 2rem;
  border-radius: 12px;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.05) 0%, rgba(123, 97, 255, 0.05) 100%);
  border: 1px solid rgba(0, 212, 255, 0.2);
}

.portfolio-header h1 {
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

.portfolio-content {
  margin-bottom: 5rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}

.project-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 2rem;
  border-radius: 12px;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  background: rgba(0, 212, 255, 0.1);
  border-color: rgba(0, 212, 255, 0.5);
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(0, 212, 255, 0.2);
}

.project-image {
  font-size: 3rem;
  margin-bottom: 1rem;
  text-align: center;
}

.project-card h3 {
  font-size: 1.4rem;
  color: #00d4ff;
  margin-bottom: 0.8rem;
}

.project-description {
  color: #b0b0b0;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  flex-grow: 1;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tag {
  background: rgba(0, 212, 255, 0.15);
  color: #00d4ff;
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  font-size: 0.8rem;
  border: 1px solid rgba(0, 212, 255, 0.3);
}

.view-btn {
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  color: #000;
  border: none;
  padding: 0.8rem 1.5rem;
  border-radius: 6px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  width: 100%;
}

.view-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 212, 255, 0.3);
}

.cta-section {
  text-align: center;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.05) 0%, rgba(123, 97, 255, 0.05) 100%);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 3rem 2rem;
  border-radius: 12px;
}

.cta-section h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.cta-section p {
  color: #b0b0b0;
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

.cta-btn {
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  color: #000;
  border: none;
  padding: 1rem 2.5rem;
  border-radius: 8px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.cta-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.3);
}

@media (max-width: 768px) {
  .portfolio-header h1 {
    font-size: 2rem;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .cta-section h2 {
    font-size: 1.5rem;
  }
}
</style>
