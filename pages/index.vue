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
            <span class="block">AI-Smart. Clinically Sharp.</span>
            <span class="block text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 to-purple-600">Your Virtual Scribe is an MD.</span>
          </h1>
          <p class="mt-6 max-w-lg mx-auto text-xl text-gray-600">
            Reduce documentation time, improve note quality, and reclaim your clinical day.
          </p>
          <div class="mt-10 flex justify-center gap-4">
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-full text-white bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              Start Free Trial
            </button>
            <button 
              @click="navigateTo('/demo')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-full text-indigo-700 bg-white hover:bg-gray-50 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              Schedule a Demo
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Welkesa Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Why Choose Welkesa?
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            The perfect blend of medical expertise and AI efficiency
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="(feature, index) in features"
            :key="index"
            class="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 border border-gray-100 hover:border-indigo-100"
          >
            <div class="flex items-center mb-4">
              <div class="flex-shrink-0 bg-indigo-100 p-3 rounded-full">
                <component 
                  :is="feature.icon" 
                  class="h-6 w-6 text-indigo-600" 
                  aria-hidden="true"
                />
              </div>
              <h3 class="ml-3 text-lg font-medium text-gray-900">{{ feature.title }}</h3>
            </div>
            <p class="mt-2 text-gray-600">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Our Services
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Comprehensive solutions for your clinical workflow
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div 
            v-for="(service, index) in services"
            :key="index"
            class="group bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-all duration-300 transform hover:-translate-y-2"
          >
            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-100 text-indigo-600 mb-4 group-hover:bg-indigo-600 group-hover:text-white transition-colors duration-300">
              <component :is="service.icon" class="h-6 w-6" aria-hidden="true" />
            </div>
            <h3 class="text-lg font-medium text-gray-900 mb-2">{{ service.title }}</h3>
            <p class="text-gray-600">{{ service.description }}</p>
            <div class="mt-4">
              <ul class="space-y-2">
                <li 
                  v-for="(item, i) in service.items"
                  :key="i"
                  class="flex items-start"
                >
                  <svg class="h-5 w-5 text-indigo-500 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                  </svg>
                  <span class="text-gray-600">{{ item }}</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- How It Works Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            How It Works
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Simple steps to transform your documentation workflow
          </p>
        </div>

        <div class="relative">
          <!-- Timeline bar -->
          <div class="hidden lg:block absolute top-1/2 left-0 right-0 h-1 bg-gray-200 transform -translate-y-1/2"></div>
          
          <div class="grid lg:grid-cols-5 gap-8">
            <div 
              v-for="(step, index) in steps"
              :key="index"
              class="relative group"
            >
              <!-- Timeline dot -->
              <div class="hidden lg:flex absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 h-8 w-8 rounded-full bg-indigo-600 items-center justify-center z-10 group-hover:scale-125 transition-transform duration-300">
                <span class="text-white font-bold">{{ index + 1 }}</span>
              </div>
              
              <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-all duration-300 h-full flex flex-col">
                <div class="flex-shrink-0 flex justify-center mb-4">
                  <div class="h-16 w-16 rounded-full bg-indigo-100 flex items-center justify-center text-indigo-600 group-hover:bg-indigo-600 group-hover:text-white transition-colors duration-300">
                    <component :is="step.icon" class="h-8 w-8" aria-hidden="true" />
                  </div>
                </div>
                <h3 class="text-lg font-medium text-gray-900 text-center mb-2">{{ step.title }}</h3>
                <p class="text-gray-600 text-center">{{ step.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-20 bg-indigo-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            What Our Clients Say
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Trusted by physicians across the country
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <TestimonialCard 
            v-for="(testimonial, index) in testimonials"
            :key="index"
            :testimonial="testimonial"
          />
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
  UserGroupIcon,
  ClockIcon,
  DocumentTextIcon,
  ShieldCheckIcon,
  ChatBubbleLeftRightIcon as ChatAltIcon,
  CogIcon,
  InboxArrowDownIcon as InboxIcon,
  ClipboardDocumentListIcon as ClipboardListIcon,
  PhoneArrowUpRightIcon as PhoneIcon,
  CheckCircleIcon,
  StarIcon
} from '@heroicons/vue/24/outline';
import TestimonialCard from '@/components/TestimonialCard.vue';
import useTestimonials from '@/composables/useTestimonials';

const router = useRouter();
const { testimonials } = useTestimonials();

// Features data
const features = ref([
  {
    title: 'MD-Level Scribes',
    description: 'Our Virtual Clinical Assistants are foreign-trained physicians with medical expertise',
    icon: UserGroupIcon
  },
  {
    title: 'AI Collaboration',
    description: 'They work with AI tools to dramatically speed up your documentation',
    icon: CogIcon
  },
  {
    title: 'Comprehensive Support',
    description: 'We handle labs, messages, chart prep, and note editing - all in one service',
    icon: InboxIcon
  },
  {
    title: 'HIPAA Compliant',
    description: 'Secure, HIPAA-conscious workflow to protect patient data',
    icon: ShieldCheckIcon
  },
  {
    title: 'Dedicated Support',
    description: 'Personalized quality control and continuous improvement',
    icon: ChatAltIcon
  },
  {
    title: 'Time Savings',
    description: 'Reduce documentation time by 50% or more',
    icon: ClockIcon
  }
]);

// Services data
const services = ref([
  {
    title: 'AI-Supported Note Editing',
    description: 'Review and finalize AI-generated progress notes',
    icon: DocumentTextIcon,
    items: [
      'Review AI-generated notes',
      'Ensure clinical accuracy',
      'Add relevant context',
      'Format to your preferences'
    ]
  },
  {
    title: 'Inbox & Lab Tracking',
    description: 'Manage patient messages and results efficiently',
    icon: InboxIcon,
    items: [
      'Patient message triage',
      'Refill requests',
      'Lab result tracking',
      'Priority flagging'
    ]
  },
  {
    title: 'Chart Preparation',
    description: 'Pre-visit summaries and documentation',
    icon: ClipboardListIcon,
    items: [
      'Pre-visit summaries',
      'Referral letters',
      'Insurance documentation',
      'Chart review'
    ]
  },
  {
    title: 'Optional Add-ons',
    description: 'Enhance your workflow with extras',
    icon: StarIcon,
    items: [
      'Audio transcription',
      'Bilingual support',
      'Custom templates',
      'Priority turnaround'
    ]
  }
]);

// Steps data
const steps = ref([
  {
    title: 'Onboard',
    description: 'Share your preferences and EMR setup',
    icon: ClipboardListIcon
  },
  {
    title: 'Assign',
    description: 'We match you with a dedicated MD-level scribe',
    icon: UserGroupIcon
  },
  {
    title: 'Collaborate',
    description: 'Share your notes, audio, or AI drafts',
    icon: ChatAltIcon
  },
  {
    title: 'Finalize',
    description: 'Your scribe returns clean, accurate notes within 12-24 hours',
    icon: CheckCircleIcon
  },
  {
    title: 'Support',
    description: 'Regular check-ins + continuous improvement',
    icon: PhoneIcon
  }
]);

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