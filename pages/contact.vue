<template>
  <div class="bg-white">
    <!-- Hero Section -->
    <section class="relative bg-gradient-to-br from-indigo-50 to-blue-50 overflow-hidden">
      <!-- Animated background elements -->
      <div class="absolute top-0 left-0 w-full h-full overflow-hidden opacity-20">
        <div class="absolute top-20 left-10 w-64 h-64 bg-indigo-200 rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-blob"></div>
        <div class="absolute top-40 right-20 w-64 h-64 bg-blue-200 rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-blob animation-delay-2000"></div>
        <div class="absolute bottom-20 left-1/2 w-64 h-64 bg-purple-200 rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-blob animation-delay-4000"></div>
      </div>

      <div class="relative max-w-7xl mx-auto px-4 py-24 sm:px-6 lg:px-8 lg:py-32">
        <div class="text-center">
          <h1 class="text-4xl font-extrabold tracking-tight text-gray-900 sm:text-5xl lg:text-6xl">
            <span class="block">Let's Get Started</span>
            <span class="block text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 to-purple-600">Contact Welkesa</span>
          </h1>
          <p class="mt-6 max-w-lg mx-auto text-xl text-gray-600">
            Reach out to learn how our physician-led virtual scribes can transform your practice.
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Form Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-2 lg:gap-16">
          <!-- Contact Form -->
          <div class="mb-16 lg:mb-0">
            <div class="bg-white p-8 rounded-xl shadow-xl border border-gray-100">
              <h2 class="text-2xl font-bold text-gray-900 mb-6">Send us a message</h2>
              <form class="space-y-6">
                <div class="grid grid-cols-1 gap-6 sm:grid-cols-2">
                  <div>
                    <label for="first-name" class="block text-sm font-medium text-gray-700">First name</label>
                    <input 
                      type="text" 
                      id="first-name" 
                      class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 py-3 px-4 border"
                    >
                  </div>
                  <div>
                    <label for="last-name" class="block text-sm font-medium text-gray-700">Last name</label>
                    <input 
                      type="text" 
                      id="last-name" 
                      class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 py-3 px-4 border"
                    >
                  </div>
                </div>
                
                <div>
                  <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
                  <input 
                    type="email" 
                    id="email" 
                    class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 py-3 px-4 border"
                  >
                </div>
                
                <div>
                  <label for="practice-type" class="block text-sm font-medium text-gray-700">Practice Type</label>
                  <select 
                    id="practice-type" 
                    class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 py-3 px-4 border"
                  >
                    <option>Select your specialty</option>
                    <option>Primary Care</option>
                    <option>Internal Medicine</option>
                    <option>Family Medicine</option>
                    <option>Pediatrics</option>
                    <option>Cardiology</option>
                    <option>Other Specialty</option>
                  </select>
                </div>
                
                <div>
                  <label for="message" class="block text-sm font-medium text-gray-700">Message</label>
                  <textarea 
                    id="message" 
                    rows="4" 
                    class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 py-3 px-4 border"
                  ></textarea>
                </div>
                
                <div class="flex items-center">
                  <input 
                    id="privacy-policy" 
                    type="checkbox" 
                    class="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500"
                  >
                  <label for="privacy-policy" class="ml-2 block text-sm text-gray-700">
                    I agree to the <a href="#" class="text-indigo-600 hover:text-indigo-500">Privacy Policy</a>
                  </label>
                </div>
                
                <div>
                  <button 
                    type="submit" 
                    class="w-full flex justify-center py-3 px-6 border border-transparent rounded-md shadow-sm text-lg font-medium text-white bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 transition-all duration-300 transform hover:-translate-y-1"
                  >
                    Send Message
                  </button>
                </div>
              </form>
            </div>
          </div>
          
          <!-- Contact Info -->
          <div class="space-y-8">
            <div class="bg-white p-8 rounded-xl shadow-xl border border-gray-100">
              <h2 class="text-2xl font-bold text-gray-900 mb-6">Schedule a demo</h2>
              <p class="text-gray-600 mb-6">
                See Welkesa in action with a personalized 30-minute demo. We'll show you how our physician-led virtual scribes can save you hours each week.
              </p>
              <a 
                href="https://calendly.com/welkesa/demo" 
                target="_blank"
                class="inline-flex items-center justify-center w-full px-6 py-3 border border-transparent text-lg font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 shadow-lg hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
              >
                Book a Demo
                <ArrowRightIcon class="ml-2 -mr-1 w-5 h-5" />
              </a>
            </div>
            
            <div class="bg-white p-8 rounded-xl shadow-xl border border-gray-100">
              <h2 class="text-2xl font-bold text-gray-900 mb-6">Contact information</h2>
              <div class="space-y-4">
                <div class="flex items-start">
                  <div class="flex-shrink-0 bg-indigo-100 p-3 rounded-full">
                    <PhoneIcon class="h-6 w-6 text-indigo-600" aria-hidden="true" />
                  </div>
                  <div class="ml-4">
                    <h3 class="text-lg font-medium text-gray-900">Phone</h3>
                    <p class="text-gray-600">(555) 123-4567</p>
                  </div>
                </div>
                
                <div class="flex items-start">
                  <div class="flex-shrink-0 bg-indigo-100 p-3 rounded-full">
                    <EnvelopeIcon class="h-6 w-6 text-indigo-600" aria-hidden="true" />
                  </div>
                  <div class="ml-4">
                    <h3 class="text-lg font-medium text-gray-900">Email</h3>
                    <p class="text-gray-600">hello@welkesa.com</p>
                  </div>
                </div>
                
                <div class="flex items-start">
                  <div class="flex-shrink-0 bg-indigo-100 p-3 rounded-full">
                    <MapPinIcon class="h-6 w-6 text-indigo-600" aria-hidden="true" />
                  </div>
                  <div class="ml-4">
                    <h3 class="text-lg font-medium text-gray-900">Headquarters</h3>
                    <p class="text-gray-600">123 Medical Drive<br>Boston, MA 02115</p>
                  </div>
                </div>
              </div>
              
              <div class="mt-8">
                <h3 class="text-lg font-medium text-gray-900 mb-4">Follow us</h3>
                <div class="flex space-x-4">
                  <a href="#" class="text-gray-400 hover:text-indigo-600">
                    <span class="sr-only">LinkedIn</span>
                    <LinkedInIcon class="h-6 w-6" />
                  </a>
                  <a href="#" class="text-gray-400 hover:text-indigo-600">
                    <span class="sr-only">Twitter</span>
                    <TwitterIcon class="h-6 w-6" />
                  </a>
                  <a href="#" class="text-gray-400 hover:text-indigo-600">
                    <span class="sr-only">Facebook</span>
                    <FacebookIcon class="h-6 w-6" />
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Frequently asked questions
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Everything you need to know about Welkesa
          </p>
        </div>

        <div class="max-w-3xl mx-auto">
          <div class="space-y-6">
            <div 
              v-for="(faq, index) in faqs" 
              :key="index" 
              class="bg-white p-6 rounded-xl shadow-lg border border-gray-100"
            >
              <button 
                @click="toggleFaq(index)"
                class="flex justify-between items-center w-full text-left"
              >
                <h3 class="text-lg font-medium text-gray-900">{{ faq.question }}</h3>
                <ChevronDownIcon 
                  class="h-5 w-5 text-indigo-600 transition-transform duration-300" 
                  :class="{ 'transform rotate-180': faq.open }" 
                />
              </button>
              <div 
                v-show="faq.open" 
                class="mt-4 text-gray-600"
                v-html="faq.answer"
              ></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="bg-gradient-to-r from-indigo-600 to-purple-600">
      <div class="max-w-7xl mx-auto px-4 py-16 sm:px-6 lg:px-8 lg:py-24">
        <div class="text-center">
          <h2 class="text-3xl font-extrabold tracking-tight text-white sm:text-4xl">
            Ready to reclaim your clinical day?
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-indigo-100">
            Join hundreds of physicians who trust Welkesa with their documentation.
          </p>
          <div class="mt-10 flex justify-center gap-4">
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-full text-indigo-600 bg-white hover:bg-gray-100 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              Start Free Trial
            </button>
            <button 
              @click="navigateTo('/demo')" 
              class="px-8 py-3 border border-white text-base font-medium rounded-full text-white hover:bg-indigo-700 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              Schedule a Demo
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { 
  PhoneIcon,
  EnvelopeIcon,
  MapPinIcon,
  ChevronDownIcon,
  ArrowRightIcon
} from '@heroicons/vue/24/outline';

// Custom social icons since some aren't available in outline package
const LinkedinIcon = {
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
      <path d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"/>
    </svg>
  `
};

const TwitterIcon = {
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
      <path d="M22.46 6c-.77.35-1.6.58-2.46.69.88-.53 1.56-1.37 1.88-2.38-.83.5-1.75.85-2.72 1.05C18.37 4.5 17.26 4 16 4c-2.35 0-4.27 1.92-4.27 4.29 0 .34.04.67.11.98C8.28 9.09 5.11 7.38 3 4.79c-.37.63-.58 1.37-.58 2.15 0 1.49.75 2.81 1.91 3.56-.71 0-1.37-.2-1.95-.5v.03c0 2.08 1.48 3.82 3.44 4.21a4.22 4.22 0 0 1-1.93.07 4.28 4.28 0 0 0 4 2.98 8.521 8.521 0 0 1-5.33 1.84c-.34 0-.68-.02-1.02-.06C3.44 20.29 5.7 21 8.12 21 16 21 20.33 14.46 20.33 8.79c0-.19 0-.37-.01-.56.84-.6 1.56-1.36 2.14-2.23z"/>
    </svg>
  `
};

const FacebookIcon = {
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
      <path fill-rule="evenodd" d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z" clip-rule="evenodd" />
    </svg>
  `
};

const faqs = ref([
  {
    question: "How quickly can I get started with Welkesa?",
    answer: "Most practices can onboard within 24-48 hours. We'll need to connect with your EMR and understand your workflow preferences to match you with the perfect MD scribe.",
    open: false
  },
  {
    question: "Is Welkesa HIPAA compliant?",
    answer: "Absolutely. We use enterprise-grade security measures including end-to-end encryption, strict access controls, and regular audits to ensure complete HIPAA compliance.",
    open: false
  },
  {
    question: "What EMR systems do you work with?",
    answer: "We're compatible with all major EMRs including Epic, Cerner, Athenahealth, eClinicalWorks, and more. Our team will work with your specific system.",
    open: false
  },
  {
    question: "How does the pricing work?",
    answer: "We offer flexible pricing based on your practice size and needs. Most clients save significantly compared to in-house scribes while getting higher quality documentation.",
    open: false
  },
  {
    question: "Can I try before committing?",
    answer: "Yes! We offer a 7-day free trial so you can experience the Welkesa difference with no obligation.",
    open: false
  }
]);

const toggleFaq = (index) => {
  faqs.value[index].open = !faqs.value[index].open;
};

// Navigation function (replace with your router if needed)
const navigateTo = (path) => {
  if (process.client) {
    window.location.href = path;
  }
};
</script>

<style>
@keyframes blob {
  0% {
    transform: translate(0px, 0px) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
  100% {
    transform: translate(0px, 0px) scale(1);
  }
}

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2s;
}

.animation-delay-4000 {
  animation-delay: 4s;
}
</style>