<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Ready to begin your journey?</h2>
      <p class="section-subtitle">Fill out the form below and our admissions team will get in touch with you</p>
      
      <div class="contact-content">
        <form @submit.prevent="handleSubmit" class="contact-form">
          <div class="form-row">
            <div class="form-group">
              <label for="name">Full Name <span class="required">*</span></label>
              <input 
                id="name"
                type="text" 
                v-model="formData.name" 
                required 
                placeholder="John Doe"
              />
            </div>
            
            <div class="form-group">
              <label for="email">Email Address <span class="required">*</span></label>
              <input 
                id="email"
                type="email" 
                v-model="formData.email" 
                required 
                placeholder="john.doe@example.com"
              />
            </div>
          </div>
          
          <div class="form-row">
            <div class="form-group">
              <label for="phone">Phone Number <span class="required">*</span></label>
              <input 
                id="phone"
                type="tel" 
                v-model="formData.phone" 
                required 
                placeholder="+256 700 000 000"
              />
            </div>
            
            <div class="form-group">
              <label for="country">Country <span class="required">*</span></label>
              <select id="country" v-model="formData.country" required>
                <option value="">Select your country</option>
                <option v-for="country in countries" :key="country" :value="country">
                  {{ country }}
                </option>
              </select>
            </div>
          </div>
          
          <div class="form-group">
            <label for="program">Program of Interest <span class="required">*</span></label>
            <select id="program" v-model="formData.program" required>
              <option value="">Select a program</option>
              <option value="foundation">Foundation Program</option>
              <option value="undergraduate">Undergraduate Pathway</option>
              <option value="postgraduate">Postgraduate Pathway</option>
              <option value="english">English Language Course</option>
            </select>
          </div>
          
          <div class="form-group">
            <label for="message">Tell us about your goals</label>
            <textarea 
              id="message"
              v-model="formData.message" 
              rows="5"
              placeholder="Share your educational background, career aspirations, or any questions you have..."
            ></textarea>
          </div>
          
          <button type="submit" class="btn btn-primary">
            <span>Submit Application</span>
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4.167 10h11.666M10 4.167L15.833 10 10 15.833" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </form>
        
        <div class="image-section">
          <div class="image-container">
            <img src="/David_Kiwalabye_Male-rbg.png" alt="Owek. David Kyewalabye Male" class="leader-image" />
          </div>
          <div class="caption">
            <p class="quote">"We at GES (Gombe Education Service) are committed to providing solutions to contemporary challenges. We seek to open new frontiers for our East African learners in America and Europe. We are glad to be here because we know TOMORROW STARTS TODAY…."</p>
            <p class="author"><strong>Owek. David Kyewalabye Male</strong></p>
            <p class="title">Managing Director, Gombe Education Service</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

interface FormData {
  name: string
  email: string
  phone: string
  country: string
  program: string
  message: string
}

const formData = reactive<FormData>({
  name: '',
  email: '',
  phone: '',
  country: '',
  program: '',
  message: ''
})

const countries = [
  'Afghanistan', 'Albania', 'Algeria', 'Andorra', 'Angola', 'Argentina', 'Armenia', 'Australia', 'Austria', 'Azerbaijan',
  'Bahamas', 'Bahrain', 'Bangladesh', 'Barbados', 'Belarus', 'Belgium', 'Belize', 'Benin', 'Bhutan', 'Bolivia',
  'Bosnia and Herzegovina', 'Botswana', 'Brazil', 'Brunei', 'Bulgaria', 'Burkina Faso', 'Burundi',
  'Cambodia', 'Cameroon', 'Canada', 'Cape Verde', 'Central African Republic', 'Chad', 'Chile', 'China', 'Colombia',
  'Comoros', 'Congo', 'Costa Rica', 'Croatia', 'Cuba', 'Cyprus', 'Czech Republic',
  'Denmark', 'Djibouti', 'Dominica', 'Dominican Republic',
  'Ecuador', 'Egypt', 'El Salvador', 'Equatorial Guinea', 'Eritrea', 'Estonia', 'Eswatini', 'Ethiopia',
  'Fiji', 'Finland', 'France',
  'Gabon', 'Gambia', 'Georgia', 'Germany', 'Ghana', 'Greece', 'Grenada', 'Guatemala', 'Guinea', 'Guinea-Bissau', 'Guyana',
  'Haiti', 'Honduras', 'Hungary',
  'Iceland', 'India', 'Indonesia', 'Iran', 'Iraq', 'Ireland', 'Israel', 'Italy',
  'Jamaica', 'Japan', 'Jordan',
  'Kazakhstan', 'Kenya', 'Kiribati', 'Kosovo', 'Kuwait', 'Kyrgyzstan',
  'Laos', 'Latvia', 'Lebanon', 'Lesotho', 'Liberia', 'Libya', 'Liechtenstein', 'Lithuania', 'Luxembourg',
  'Madagascar', 'Malawi', 'Malaysia', 'Maldives', 'Mali', 'Malta', 'Marshall Islands', 'Mauritania', 'Mauritius',
  'Mexico', 'Micronesia', 'Moldova', 'Monaco', 'Mongolia', 'Montenegro', 'Morocco', 'Mozambique', 'Myanmar',
  'Namibia', 'Nauru', 'Nepal', 'Netherlands', 'New Zealand', 'Nicaragua', 'Niger', 'Nigeria', 'North Korea',
  'North Macedonia', 'Norway',
  'Oman',
  'Pakistan', 'Palau', 'Palestine', 'Panama', 'Papua New Guinea', 'Paraguay', 'Peru', 'Philippines', 'Poland', 'Portugal',
  'Qatar',
  'Romania', 'Russia', 'Rwanda',
  'Saint Kitts and Nevis', 'Saint Lucia', 'Saint Vincent and the Grenadines', 'Samoa', 'San Marino',
  'Sao Tome and Principe', 'Saudi Arabia', 'Senegal', 'Serbia', 'Seychelles', 'Sierra Leone', 'Singapore',
  'Slovakia', 'Slovenia', 'Solomon Islands', 'Somalia', 'South Africa', 'South Korea', 'South Sudan', 'Spain',
  'Sri Lanka', 'Sudan', 'Suriname', 'Sweden', 'Switzerland', 'Syria',
  'Taiwan', 'Tajikistan', 'Tanzania', 'Thailand', 'Timor-Leste', 'Togo', 'Tonga', 'Trinidad and Tobago',
  'Tunisia', 'Turkey', 'Turkmenistan', 'Tuvalu',
  'Uganda', 'Ukraine', 'United Arab Emirates', 'United Kingdom', 'United States', 'Uruguay', 'Uzbekistan',
  'Vanuatu', 'Vatican City', 'Venezuela', 'Vietnam',
  'Yemen',
  'Zambia', 'Zimbabwe'
]

const handleSubmit = () => {
  console.log('Form submitted:', formData)
  alert('Thank you for your application! We will contact you soon.')
  Object.assign(formData, { name: '', email: '', phone: '', country: '', program: '', message: '' })
}
</script>

<style scoped>
.contact {
  padding: 1.5rem 0 6rem 0;
  background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
  position: relative;
  overflow: hidden;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 1.5rem;
  position: relative;
  z-index: 1;
}

.section-title {
  text-align: center;
  font-family: 'Ubuntu', sans-serif;
  color: var(--text-dark);
  font-size: 2.75rem;
  font-weight: 700;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.section-subtitle {
  text-align: center;
  color: var(--text-light);
  font-size: 1.125rem;
  margin-bottom: 3rem;
  line-height: 1.6;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: end;
  max-width: 1400px;
  margin: 0 auto;
}

.contact-form {
  width: 100%;
  background: var(--white);
  padding: 3rem;
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  border: 1px solid rgba(139, 21, 56, 0.08);
  transition: box-shadow 0.3s ease;
}

.image-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
}

.image-container {
  width: 100%;
  max-width: 400px;
  margin-bottom: 1.5rem;
}

.leader-image {
  width: 100%;
  height: auto;
  object-fit: contain;
  opacity: 0.4;
  filter: grayscale(20%);
}

.caption {
  max-width: 500px;
  padding: 0;
}

.quote {
  font-style: italic;
  color: var(--text-dark);
  margin-bottom: 1rem;
  line-height: 1.7;
  font-size: 0.95rem;
  font-family: 'Times New Roman', Times, serif;
}

.author {
  color: var(--primary-color);
  margin-bottom: 0.25rem;
  font-size: 1rem;
}

.title {
  color: var(--text-dark);
  font-size: 0.9rem;
  margin: 0;
}

.contact-form:hover {
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.12);
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
}

.form-group {
  margin-bottom: 1.75rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 600;
  color: var(--text-dark);
  font-size: 0.95rem;
  font-family: 'Ubuntu', sans-serif;
}

.required {
  color: var(--primary-color);
}

.contact-form input,
.contact-form select,
.contact-form textarea {
  width: 100%;
  padding: 1rem 1.25rem;
  background: #f9fafb;
  border: 2px solid #e5e7eb;
  border-radius: 12px;
  font-size: 1rem;
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
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='20' viewBox='0 0 20 20'%3E%3Cpath fill='%236b7280' d='M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 1rem center;
  background-size: 20px;
  background-color: #f9fafb;
  padding-right: 3rem;
}

.contact-form select option {
  font-family: 'Ubuntu', sans-serif;
  padding: 0.5rem;
}

.contact-form input:hover,
.contact-form select:hover,
.contact-form textarea:hover {
  border-color: #d1d5db;
  background: var(--white);
}

.contact-form input:focus,
.contact-form select:focus,
.contact-form textarea:focus {
  border-color: var(--primary-color);
  background: var(--white);
  box-shadow: 0 0 0 4px rgba(139, 21, 56, 0.1);
}

.contact-form textarea {
  resize: vertical;
  min-height: 140px;
  line-height: 1.6;
}

.contact-form button {
  width: 100%;
  padding: 1.25rem 2rem;
  font-size: 1.125rem;
  font-family: 'Ubuntu', sans-serif;
  font-weight: 600;
  border-radius: 12px;
  margin-top: 0.5rem;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.75rem;
  background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
  border: none;
  color: white;
  cursor: pointer;
}

.contact-form button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(139, 21, 56, 0.3);
}

.contact-form button:active {
  transform: translateY(-1px);
}

.contact-form button svg {
  transition: transform 0.3s ease;
}

.contact-form button:hover svg {
  transform: translateX(4px);
}

@media (max-width: 1200px) {
  .contact-content {
    gap: 2rem;
  }
  
  .caption {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .contact {
    padding: 1rem 0 4rem 0;
  }
  
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .image-section {
    order: -1;
  }
  
  .image-container {
    max-width: 300px;
  }
  
  .leader-image {
    opacity: 0.3;
  }
  
  .quote {
    font-size: 0.875rem;
  }
  
  .section-title {
    font-size: 2rem;
  }
  
  .section-subtitle {
    font-size: 1rem;
    margin-bottom: 2rem;
  }
  
  .contact-form {
    padding: 2rem 1.5rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
    gap: 0;
  }
  
  .form-group {
    margin-bottom: 1.5rem;
  }
  
  .contact-form button {
    font-size: 1rem;
    padding: 1.125rem 1.5rem;
  }
}
</style>
