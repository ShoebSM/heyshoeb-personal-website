<script setup lang="ts">
import { ref } from 'vue'
import HomePage from './components/HomePage.vue'
import AboutPage from './components/AboutPage.vue'
import PortfolioPage from './components/PortfolioPage.vue'
import ContactPage from './components/ContactPage.vue'

const activeTab = ref('home')

const tabs = [
  { id: 'home', label: 'Home', icon: '🏠' },
  { id: 'about', label: 'About', icon: '👤' },
  { id: 'portfolio', label: 'Portfolio', icon: '💼' },
  { id: 'contact', label: 'Contact', icon: '✉️' },
]

const navigateTo = (tabId: string) => {
  activeTab.value = tabId
}
</script>

<template>
  <div class="container">
    <!-- Navigation -->
    <nav class="navbar">
      <div class="navbar-content">
        <h1 class="logo">Shoeb</h1>
        <div class="nav-tabs">
          <button
            v-for="tab in tabs"
            :key="tab.id"
            :class="['nav-tab', { active: activeTab === tab.id }]"
            @click="navigateTo(tab.id)"
          >
            <span class="tab-icon">{{ tab.icon }}</span>
            <span class="tab-label">{{ tab.label }}</span>
          </button>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="main-content">
      <HomePage v-if="activeTab === 'home'" />
      <AboutPage v-else-if="activeTab === 'about'" />
      <PortfolioPage v-else-if="activeTab === 'portfolio'" />
      <ContactPage v-else-if="activeTab === 'contact'" />
    </main>

    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2025 Shoeb. All rights reserved.</p>
      <div class="social-links">
        <a href="#" class="social-link">GitHub</a>
        <a href="#" class="social-link">LinkedIn</a>
        <a href="#" class="social-link">Twitter</a>
      </div>
    </footer>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: linear-gradient(135deg, #1a1a2e 0%, #0f0f1e 100%);
  color: #e0e0e0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Navigation Bar */
.navbar {
  background: rgba(20, 20, 35, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 100;
}

.navbar-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.8rem;
  font-weight: 700;
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav-tabs {
  display: flex;
  gap: 1rem;
}

.nav-tab {
  background: none;
  border: none;
  color: #a0a0a0;
  cursor: pointer;
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition: all 0.3s ease;
  font-size: 1rem;
  font-weight: 500;
}

.nav-tab:hover {
  color: #e0e0e0;
  background: rgba(255, 255, 255, 0.05);
}

.nav-tab.active {
  color: #00d4ff;
  background: rgba(0, 212, 255, 0.1);
  border: 1px solid rgba(0, 212, 255, 0.3);
}

.tab-icon {
  font-size: 1.2rem;
}

.tab-label {
  white-space: nowrap;
}

/* Main Content */
.main-content {
  flex: 1;
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
  padding: 4rem 2rem;
}

/* Footer */
.footer {
  background: rgba(20, 20, 35, 0.95);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 2rem;
  text-align: center;
  margin-top: auto;
}

.footer p {
  margin-bottom: 1rem;
  color: #808080;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 2rem;
}

.social-link {
  color: #00d4ff;
  text-decoration: none;
  transition: color 0.3s ease;
}

.social-link:hover {
  color: #7b61ff;
}

/* Responsive Design */
@media (max-width: 768px) {
  .navbar-content {
    flex-direction: column;
    gap: 1rem;
  }

  .nav-tabs {
    width: 100%;
    justify-content: space-around;
  }

  .nav-tab {
    padding: 0.5rem 1rem;
    font-size: 0.9rem;
  }

  .tab-label {
    display: none;
  }

  .main-content {
    padding: 2rem 1rem;
  }

  .logo {
    font-size: 1.4rem;
  }
}
</style>
