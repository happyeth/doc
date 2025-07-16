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
                    src="data:image/jpeg;base64,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" 
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
