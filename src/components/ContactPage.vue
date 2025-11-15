<script setup lang="ts">
import { ref } from 'vue'

const formData = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const submitted = ref(false)

const handleSubmit = () => {
  // In a real application, you would send this data to a backend
  console.log('Form submitted:', formData.value)
  submitted.value = true

  // Reset form after 2 seconds
  setTimeout(() => {
    formData.value = { name: '', email: '', subject: '', message: '' }
    submitted.value = false
  }, 2000)
}

const contactMethods = [
  {
    icon: '📧',
    label: 'Email',
    value: 'shoeb@example.com',
    link: 'mailto:shoeb@example.com',
  },
  {
    icon: '💼',
    label: 'LinkedIn',
    value: 'linkedin.com/in/shoeb',
    link: 'https://linkedin.com/in/shoeb',
  },
  {
    icon: '🐙',
    label: 'GitHub',
    value: 'github.com/shoeb',
    link: 'https://github.com/shoeb',
  },
  {
    icon: '🐦',
    label: 'Twitter',
    value: '@shoeb_dev',
    link: 'https://twitter.com/shoeb_dev',
  },
]
</script>

<template>
  <div class="contact-page">
    <div class="contact-header">
      <h1>Get In Touch</h1>
      <p class="intro">I'd love to hear from you. Let's connect!</p>
    </div>

    <div class="contact-content">
      <!-- Contact Form -->
      <div class="form-section">
        <h2>Send Me a Message</h2>
        <form @submit.prevent="handleSubmit" class="contact-form">
          <div class="form-group">
            <label for="name">Name</label>
            <input
              v-model="formData.name"
              type="text"
              id="name"
              placeholder="Your name"
              required
            />
          </div>

          <div class="form-group">
            <label for="email">Email</label>
            <input
              v-model="formData.email"
              type="email"
              id="email"
              placeholder="your@email.com"
              required
            />
          </div>

          <div class="form-group">
            <label for="subject">Subject</label>
            <input
              v-model="formData.subject"
              type="text"
              id="subject"
              placeholder="What is this about?"
              required
            />
          </div>

          <div class="form-group">
            <label for="message">Message</label>
            <textarea
              v-model="formData.message"
              id="message"
              placeholder="Your message here..."
              rows="6"
              required
            ></textarea>
          </div>

          <button type="submit" class="submit-btn" :disabled="submitted">
            {{ submitted ? '✓ Message Sent!' : 'Send Message' }}
          </button>
        </form>
      </div>

      <!-- Contact Methods -->
      <div class="contact-methods">
        <h2>Other Ways to Connect</h2>
        <div class="methods-grid">
          <a
            v-for="method in contactMethods"
            :key="method.label"
            :href="method.link"
            target="_blank"
            rel="noopener"
            class="method-card"
          >
            <div class="method-icon">{{ method.icon }}</div>
            <div class="method-label">{{ method.label }}</div>
            <div class="method-value">{{ method.value }}</div>
          </a>
        </div>
      </div>
    </div>

    <!-- Response Time -->
    <div class="response-time">
      <h3>Response Time</h3>
      <p>I typically respond to messages within 24-48 hours. Looking forward to hearing from you!</p>
    </div>
  </div>
</template>

<style scoped>
.contact-page {
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

.contact-header {
  text-align: center;
  margin-bottom: 4rem;
  padding: 3rem 2rem;
  border-radius: 12px;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.05) 0%, rgba(123, 97, 255, 0.05) 100%);
  border: 1px solid rgba(0, 212, 255, 0.2);
}

.contact-header h1 {
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

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  margin-bottom: 4rem;
}

.form-section h2,
.contact-methods h2 {
  font-size: 1.8rem;
  color: #00d4ff;
  margin-bottom: 2rem;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-group label {
  color: #b0b0b0;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.form-group input,
.form-group textarea {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(0, 212, 255, 0.2);
  color: #e0e0e0;
  padding: 0.8rem 1rem;
  border-radius: 6px;
  font-size: 1rem;
  font-family: inherit;
  transition: all 0.3s ease;
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: #606060;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  background: rgba(0, 212, 255, 0.1);
  border-color: rgba(0, 212, 255, 0.5);
  box-shadow: 0 0 0 3px rgba(0, 212, 255, 0.1);
}

.submit-btn {
  background: linear-gradient(135deg, #00d4ff 0%, #7b61ff 100%);
  color: #000;
  border: none;
  padding: 1rem;
  border-radius: 6px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 1rem;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 212, 255, 0.3);
}

.submit-btn:disabled {
  opacity: 0.8;
}

.methods-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

.method-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 1.5rem;
  border-radius: 8px;
  text-decoration: none;
  color: inherit;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.method-card:hover {
  background: rgba(0, 212, 255, 0.1);
  border-color: rgba(0, 212, 255, 0.5);
  transform: translateX(5px);
}

.method-icon {
  font-size: 2rem;
  min-width: 50px;
  text-align: center;
}

.method-label {
  color: #00d4ff;
  font-weight: 600;
  flex: 1;
}

.method-value {
  color: #a0a0a0;
  font-size: 0.9rem;
}

.response-time {
  text-align: center;
  background: rgba(0, 212, 255, 0.1);
  border: 1px solid rgba(0, 212, 255, 0.3);
  padding: 2rem;
  border-radius: 12px;
}

.response-time h3 {
  color: #00d4ff;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
}

.response-time p {
  color: #b0b0b0;
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
  }

  .contact-header h1 {
    font-size: 2rem;
  }

  .methods-grid {
    grid-template-columns: 1fr;
  }
}
</style>
