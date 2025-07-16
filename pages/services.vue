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
            <span class="block">Comprehensive Clinical</span>
            <span class="block text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 to-purple-600">Support Services</span>
          </h1>
          <p class="mt-6 max-w-3xl mx-auto text-xl text-gray-600">
            Our physician-led virtual assistance combines medical expertise with AI efficiency to transform your clinical workflow.
          </p>
          <div class="mt-10 flex justify-center gap-4">
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-full text-white bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              Get Started
            </button>
            <button 
              @click="navigateTo('/demo')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-full text-indigo-700 bg-white hover:bg-gray-50 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              See How It Works
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Grid -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Our Core Services
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Designed by physicians to streamline your practice
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="(service, index) in services"
            :key="index"
            class="group bg-white p-8 rounded-xl shadow-lg hover:shadow-2xl transition-all duration-500 border border-gray-100 hover:border-indigo-100 relative overflow-hidden"
            :style="{ transitionDelay: `${index * 100}ms` }"
            @mouseenter="hoveredService = index"
            @mouseleave="hoveredService = null"
          >
            <!-- Animated background overlay -->
            <div 
              class="absolute inset-0 bg-gradient-to-br from-indigo-50 to-purple-50 opacity-0 group-hover:opacity-100 transition-opacity duration-500"
              :class="{ 'opacity-100': hoveredService === index }"
            ></div>
            
            <!-- Floating icon animation -->
            <div class="relative z-10">
              <div class="flex items-center justify-center w-16 h-16 mx-auto mb-6 rounded-full bg-white shadow-md group-hover:bg-indigo-100 transition-colors duration-300">
                <component 
                  :is="service.icon" 
                  class="h-8 w-8 text-indigo-600 group-hover:text-indigo-700 transition-colors duration-300" 
                />
              </div>
              
              <h3 class="text-xl font-bold text-center text-gray-900 mb-3">{{ service.title }}</h3>
              <p class="text-gray-600 text-center mb-4">{{ service.description }}</p>
              
              <ul class="space-y-2">
                <li 
                  v-for="(feature, i) in service.features"
                  :key="i"
                  class="flex items-start"
                >
                  <CheckCircleIcon class="h-5 w-5 text-indigo-500 mr-2 mt-0.5 flex-shrink-0" />
                  <span class="text-gray-600">{{ feature }}</span>
                </li>
              </ul>
              
              <div class="mt-6 text-center">
                <span class="inline-flex items-center px-3 py-1 rounded-full text-xs font-medium bg-indigo-100 text-indigo-800">
                  {{ service.turnaround }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Feature Spotlight -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-12 lg:gap-16">
          <div class="lg:col-span-6">
            <div class="relative">
              <!-- Floating cards animation -->
              <div class="relative max-w-md mx-auto">
                <div class="absolute -top-8 -left-8 w-full h-full bg-indigo-100 rounded-2xl"></div>
                <div class="relative rounded-2xl bg-white shadow-xl overflow-hidden border border-gray-200">
                  <img 
                    src=".,/assets/images/ai-note-editing.jfif" 
                    alt="AI Note Editing Interface"
                    class="w-full h-auto"
                  >
                </div>
              </div>
              
              <div class="hidden lg:block absolute -bottom-8 -right-8 w-64 h-64">
                <div class="relative w-full h-full">
                  <div 
                    v-for="(card, index) in floatingCards"
                    :key="index"
                    class="absolute bg-white p-4 rounded-lg shadow-md border border-gray-200 transition-all duration-1000 ease-in-out"
                    :class="card.class"
                    :style="{ zIndex: 10 - index }"
                  >
                    <div class="flex items-center">
                      <div class="flex-shrink-0 bg-indigo-100 p-2 rounded-full">
                        <component :is="card.icon" class="h-5 w-5 text-indigo-600" />
                      </div>
                      <div class="ml-3">
                        <p class="text-sm font-medium text-gray-900">{{ card.title }}</p>
                        <p class="text-xs text-gray-500">{{ card.value }}</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <div class="mt-16 lg:mt-0 lg:col-span-6">
            <div class="lg:pl-12">
              <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
                AI-Powered Clinical Documentation
              </h2>
              <p class="mt-4 text-lg text-gray-600">
                Our unique combination of physician expertise and AI technology delivers accurate, contextual medical notes that save you hours each day.
              </p>
              
              <div class="mt-10 space-y-8">
                <div 
                  v-for="(feature, index) in spotlightFeatures"
                  :key="index"
                  class="flex"
                >
                  <div class="flex-shrink-0">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-100 text-indigo-600">
                      <component :is="feature.icon" class="h-6 w-6" />
                    </div>
                  </div>
                  <div class="ml-4">
                    <h3 class="text-lg font-medium text-gray-900">{{ feature.title }}</h3>
                    <p class="mt-2 text-gray-600">{{ feature.description }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Workflow Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Seamless Integration With Your Workflow
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Designed to complement your existing systems and processes
          </p>
        </div>

        <div class="relative">
          <!-- Animated timeline bar -->
          <div class="hidden lg:block absolute top-1/2 left-0 right-0 h-1 bg-gray-200 transform -translate-y-1/2 z-0">
            <div 
              class="h-full bg-gradient-to-r from-indigo-500 to-purple-500 transition-all duration-1000 ease-in-out"
              :style="{ width: `${(activeStep + 1) * 20}%` }"
            ></div>
          </div>
          
          <div class="grid lg:grid-cols-5 gap-8">
            <div 
              v-for="(step, index) in workflowSteps"
              :key="index"
              class="relative group"
              @mouseenter="activeStep = index"
            >
              <!-- Animated step indicator -->
              <div class="hidden lg:flex absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 h-12 w-12 rounded-full bg-white border-4 border-gray-200 items-center justify-center z-10 transition-all duration-300 group-hover:border-indigo-500 group-hover:shadow-lg"
                :class="{ 
                  'border-indigo-500 scale-110': activeStep >= index,
                  'scale-100': activeStep < index
                }"
              >
                <div 
                  class="h-8 w-8 rounded-full flex items-center justify-center transition-all duration-300"
                  :class="{
                    'bg-indigo-600': activeStep >= index,
                    'bg-gray-200': activeStep < index
                  }"
                >
                  <component 
                    :is="step.icon" 
                    class="h-4 w-4 text-white" 
                    :class="{ 'text-gray-400': activeStep < index }"
                  />
                </div>
              </div>
              
              <div 
                class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-all duration-300 h-full flex flex-col"
                :class="{ 
                  'transform -translate-y-2 border-indigo-300': activeStep === index,
                  'border border-gray-200': activeStep !== index
                }"
              >
                <div class="flex-shrink-0 flex justify-center mb-4 lg:hidden">
                  <div class="h-12 w-12 rounded-full bg-indigo-100 flex items-center justify-center text-indigo-600">
                    <component :is="step.icon" class="h-6 w-6" />
                  </div>
                </div>
                <h3 class="text-lg font-medium text-gray-900 text-center mb-2">{{ step.title }}</h3>
                <p class="text-gray-600 text-center">{{ step.description }}</p>
                <ul v-if="step.details" class="mt-4 space-y-2 text-sm text-gray-600">
                  <li v-for="(detail, i) in step.details" :key="i" class="flex items-start">
                    <CheckCircleIcon class="h-4 w-4 text-indigo-500 mr-2 mt-0.5 flex-shrink-0" />
                    <span>{{ detail }}</span>
                  </li>
                </ul>
              </div>
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
            Ready to transform your clinical workflow?
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-indigo-100">
            Join hundreds of physicians who have reclaimed hours each week with Welkesa.
          </p>
          <div class="mt-10 flex justify-center gap-4">
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-full text-indigo-600 bg-white hover:bg-gray-100 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
            >
              Get Started
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
import { ref } from 'vue'
import {
  DocumentTextIcon,
  InboxIcon,
  ClipboardDocumentIcon as ClipboardListIcon,
  UserGroupIcon,
  CogIcon,
  ShieldCheckIcon,
  ClockIcon,
  ChartBarIcon,
  ArrowsRightLeftIcon,
  ChatBubbleLeftRightIcon,
  CheckCircleIcon
} from '@heroicons/vue/24/outline'

const hoveredService = ref(null)
const activeStep = ref(2) // Default to middle step

const services = ref([
  {
    title: 'AI-Supported Note Editing',
    description: 'Enhance your clinical documentation with our physician-AI collaboration',
    icon: DocumentTextIcon,
    features: [
      'Review and finalize AI-generated notes',
      'Contextual medical accuracy review',
      'Custom templates for your specialty',
      'SOAP, H&P, and procedure notes',
      'Formatting to your preferences'
    ],
    turnaround: '12-24 hour turnaround'
  },
  {
    title: 'Inbox & Lab Management',
    description: 'Streamline your patient communication and result tracking',
    icon: InboxIcon,
    features: [
      'Patient message triage',
      'Lab result tracking & flagging',
      'Medication refill requests',
      'Priority message identification',
      'Normal vs abnormal result sorting'
    ],
    turnaround: 'Same-day processing'
  },
  {
    title: 'Chart Preparation',
    description: 'Comprehensive pre-visit preparation and documentation',
    icon: ClipboardListIcon,
    features: [
      'Pre-visit patient summaries',
      'Referral letter generation',
      'Prior authorization support',
      'Insurance documentation',
      'Customizable templates'
    ],
    turnaround: '24-hour preparation'
  },
  {
    title: 'Dedicated MD Scribe',
    description: 'Your personal physician assistant for all documentation needs',
    icon: UserGroupIcon,
    features: [
      'US-trained physician scribe',
      'Specialty-matched expertise',
      'Consistent point of contact',
      'Learns your preferences',
      'Quality assurance reviews'
    ],
    turnaround: 'Dedicated support'
  },
  {
    title: 'Workflow Integration',
    description: 'Seamless connection with your existing systems',
    icon: CogIcon,
    features: [
      'EMR/EHR integration',
      'Voice dictation support',
      'Mobile app access',
      'Secure file sharing',
      'API connections'
    ],
    turnaround: '1-2 day setup'
  },
  {
    title: 'HIPAA Compliance',
    description: 'Enterprise-grade security for your patient data',
    icon: ShieldCheckIcon,
    features: [
      'End-to-end encryption',
      'Business Associate Agreement',
      'Audit logging',
      'Two-factor authentication',
      'Regular security audits'
    ],
    turnaround: 'Always protected'
  }
])

const floatingCards = ref([
  {
    title: 'Accuracy Rate',
    value: '98.7%',
    icon: ChartBarIcon,
    class: 'top-0 left-0 animate-float-1'
  },
  {
    title: 'Avg. Time Saved',
    value: '8.5 hrs/week',
    icon: ClockIcon,
    class: 'top-12 left-12 animate-float-2'
  },
  {
    title: 'EMR Integrations',
    value: '15+ systems',
    icon: ArrowsRightLeftIcon,
    class: 'bottom-4 left-8 animate-float-3'
  },
  {
    title: 'Physician Support',
    value: '24/7 available',
    icon: ChatBubbleLeftRightIcon,
    class: 'bottom-0 right-0 animate-float-4'
  }
])

const spotlightFeatures = ref([
  {
    title: 'Physician-Led Quality Control',
    description: 'Every note reviewed by US-trained physicians for clinical accuracy and relevance.',
    icon: UserGroupIcon
  },
  {
    title: 'Specialty-Specific Templates',
    description: 'Custom note templates tailored to your specialty and personal preferences.',
    icon: DocumentTextIcon
  },
  {
    title: 'Context-Aware AI',
    description: 'Our AI understands medical context, not just transcription, for better first drafts.',
    icon: CogIcon
  }
])

const workflowSteps = ref([
  {
    title: 'Share',
    description: 'Send us your notes, audio, or AI drafts',
    icon: ArrowsRightLeftIcon,
    details: [
      'Secure upload portal',
      'Direct EMR integration',
      'Mobile app option',
      'Voice dictation support'
    ]
  },
  {
    title: 'Process',
    description: 'Our physician scribes review and enhance',
    icon: CogIcon,
    details: [
      'MD-level clinical review',
      'AI-assisted formatting',
      'Contextual accuracy check',
      'Specialty-specific adjustments'
    ]
  },
  {
    title: 'Review',
    description: 'Receive your polished notes',
    icon: DocumentTextIcon,
    details: [
      '12-24 hour turnaround',
      'Highlighted key findings',
      'Structured for readability',
      'Ready for your signature'
    ]
  },
  {
    title: 'Finalize',
    description: 'Approve and submit to EMR',
    icon: CheckCircleIcon,
    details: [
      'One-click approval',
      'Auto-format for your EMR',
      'Direct EMR submission',
      'Revision requests available'
    ]
  },
  {
    title: 'Optimize',
    description: 'Continuous improvement',
    icon: ChartBarIcon,
    details: [
      'Regular feedback sessions',
      'Usage analytics',
      'Template refinements',
      'Workflow optimizations'
    ]
  }
])
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

@keyframes float-1 {
  0%, 100% { transform: translateY(0) rotate(-5deg); }
  50% { transform: translateY(-10px) rotate(5deg); }
}

@keyframes float-2 {
  0%, 100% { transform: translateY(-5px) rotate(3deg); }
  50% { transform: translateY(5px) rotate(-3deg); }
}

@keyframes float-3 {
  0%, 100% { transform: translateY(0) rotate(0); }
  50% { transform: translateY(-8px) rotate(2deg); }
}

@keyframes float-4 {
  0%, 100% { transform: translateY(-3px) rotate(-2deg); }
  50% { transform: translateY(3px) rotate(2deg); }
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

.animate-float-1 {
  animation: float-1 6s ease-in-out infinite;
}

.animate-float-2 {
  animation: float-2 7s ease-in-out infinite;
}

.animate-float-3 {
  animation: float-3 5s ease-in-out infinite;
}

.animate-float-4 {
  animation: float-4 6.5s ease-in-out infinite;
}

/* Smooth transitions for hover effects */
.transition-slow {
  transition: all 0.5s ease;
}
</style>