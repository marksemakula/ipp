<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Ready to begin your journey?</h2>
      
      <div class="contact-content">
        <form @submit.prevent="handleSubmit" class="contact-form">
          <div class="form-row">
            <div class="form-group">
              <input 
                type="text" 
                v-model="formData.name" 
                required 
                placeholder="Your Name"
              />
            </div>
            
            <div class="form-group">
              <input 
                type="email" 
                v-model="formData.email" 
                required 
                placeholder="Your Email"
              />
            </div>
          </div>
          
          <div class="form-group">
            <select v-model="formData.program" required>
              <option value="">Select Program</option>
              <option value="foundation">Foundation</option>
              <option value="undergraduate">Undergraduate</option>
              <option value="postgraduate">Postgraduate</option>
              <option value="english">English Language</option>
            </select>
          </div>
          
          <div class="form-group">
            <textarea 
              v-model="formData.message" 
              rows="5"
              placeholder="Tell us about your goals..."
            ></textarea>
          </div>
          
          <button type="submit" class="btn btn-primary">Submit Application</button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

interface FormData {
  name: string
  email: string
  program: string
  message: string
}

const formData = reactive<FormData>({
  name: '',
  email: '',
  program: '',
  message: ''
})

const handleSubmit = () => {
  console.log('Form submitted:', formData)
  alert('Thank you for your application! We will contact you soon.')
  Object.assign(formData, { name: '', email: '', program: '', message: '' })
}
</script>

<style scoped>
.contact {
  padding: 6rem 0;
  background: #fafafa;
}

.container {
  max-width: 700px;
  margin: 0 auto;
}

.section-title {
  text-align: center;
  font-family: 'Ubuntu', sans-serif;
  color: var(--text-dark);
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 3rem;
  line-height: 1.3;
}

.contact-content {
  display: flex;
  justify-content: center;
}

.contact-form {
  width: 100%;
  background: var(--white);
  padding: 3rem;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(139, 21, 56, 0.1);
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.25rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.contact-form input,
.contact-form select,
.contact-form textarea {
  width: 100%;
  padding: 1.125rem 1.25rem;
  background: var(--white);
  border: 2px solid #d1d5db;
  border-radius: 10px;
  font-size: 1.05rem;
  font-family: 'Ubuntu', sans-serif;
  font-weight: 400;
  color: var(--text-dark);
  transition: all 0.3s ease;
  outline: none;
}

.contact-form input::placeholder,
.contact-form textarea::placeholder {
  color: #9ca3af;
  font-family: 'Ubuntu', sans-serif;
}

.contact-form select {
  cursor: pointer;
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 16 16'%3E%3Cpath fill='%236b7280' d='M4.427 6.427l3.396 3.396a.25.25 0 00.354 0l3.396-3.396A.25.25 0 0011.396 6H4.604a.25.25 0 00-.177.427z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 1rem center;
  background-size: 16px;
  padding-right: 3rem;
}

.contact-form select option {
  font-family: 'Ubuntu', sans-serif;
  padding: 0.5rem;
}

.contact-form input:hover,
.contact-form select:hover,
.contact-form textarea:hover {
  border-color: #9ca3af;
}

.contact-form input:focus,
.contact-form select:focus,
.contact-form textarea:focus {
  border-color: var(--primary-color);
  box-shadow: 0 0 0 4px rgba(139, 21, 56, 0.08);
}

.contact-form textarea {
  resize: vertical;
  min-height: 140px;
  line-height: 1.6;
}

.contact-form button {
  width: 100%;
  padding: 1.25rem;
  font-size: 1.125rem;
  font-family: 'Ubuntu', sans-serif;
  font-weight: 600;
  border-radius: 10px;
  margin-top: 0.5rem;
  transition: all 0.3s ease;
}

.contact-form button:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(139, 21, 56, 0.25);
}

@media (max-width: 768px) {
  .contact {
    padding: 4rem 0;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .contact-form {
    padding: 2rem 1.5rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
  }
  
  .contact-form input,
  .contact-form select,
  .contact-form textarea {
    font-size: 1rem;
    padding: 1rem;
  }
}
</style>
