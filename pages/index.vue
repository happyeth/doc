<template>
  <div class="bg-white">
    <!-- Animated Hero Section -->
    <section class="relative bg-gradient-to-br from-blue-900 to-indigo-900 overflow-hidden min-h-screen flex items-center">
      <!-- Floating particles background -->
      <div class="absolute inset-0 z-0">
        <div v-for="i in 30" :key="i" 
             class="absolute rounded-full bg-blue-400 opacity-10"
             :style="{
               width: `${Math.random() * 20 + 5}px`,
               height: `${Math.random() * 20 + 5}px`,
               left: `${Math.random() * 100}%`,
               top: `${Math.random() * 100}%`,
               animation: `float ${Math.random() * 10 + 10}s linear infinite`,
               animationDelay: `${Math.random() * 5}s`
             }"></div>
      </div>

      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24 z-10">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="text-white">
            <div class="flex items-center mb-6">
              <span class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-300 to-teal-300">doc2doc.health</span>
            </div>
            <h1 class="text-4xl font-extrabold tracking-tight sm:text-5xl lg:text-6xl">
              <span class="block">Physician-Powered</span>
              <span class="block bg-clip-text text-transparent bg-gradient-to-r from-blue-300 to-teal-300">Clinical Documentation</span>
            </h1>
            <p class="mt-6 text-xl text-blue-100 max-w-lg">
              Reduce documentation time by 50% with our physician-led virtual scribing service. 
              Focus on patients while we handle your charts with clinical precision.
            </p>
            <div class="mt-10 flex flex-wrap gap-4">
              <button 
                @click="navigateTo('/contact')" 
                class="px-8 py-4 border border-transparent text-base font-medium rounded-full text-blue-900 bg-gradient-to-r from-teal-300 to-blue-300 hover:from-teal-400 hover:to-blue-400 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300 hover:scale-105"
              >
                Start Free Trial
              </button>
              <button 
                @click="navigateTo('/demo')" 
                class="px-8 py-4 border-2 border-blue-300 text-base font-medium rounded-full text-white bg-transparent hover:bg-blue-800/30 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
              >
                Schedule Demo
              </button>
            </div>
          </div>
          <div class="relative">
            <div class="relative rounded-2xl overflow-hidden shadow-2xl transform rotate-1 hover:rotate-0 transition-transform duration-500">
              <img 
                src="https://images.unsplash.com/photo-1579684385127-1ef15d508118?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
                alt="Doctor consulting with patient" 
                class="w-full h-auto"
              >
              <div class="absolute inset-0 bg-gradient-to-t from-blue-900/80 via-transparent to-transparent flex items-end p-8">
                <div class="text-white">
                  <p class="text-lg font-medium">"doc2doc.health reduced my charting time from 3 hours to just 45 minutes daily"</p>
                  <p class="mt-2 text-blue-200">— Dr. Sarah Johnson, Family Medicine</p>
                </div>
              </div>
            </div>
            <div class="absolute -bottom-6 -right-6 bg-white p-5 rounded-xl shadow-2xl border border-blue-100 transform hover:scale-110 transition-transform duration-300">
              <div class="flex items-center">
                <div class="bg-blue-100 p-3 rounded-lg">
                  <DocumentTextIcon class="h-8 w-8 text-blue-600" />
                </div>
                <div class="ml-3">
                  <p class="text-xs text-gray-500 font-medium">Average time saved</p>
                  <p class="text-2xl font-bold text-blue-600">2.5 hours/day</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section with Floating Animation -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            OUR MISSION
          </span>
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            <span class="block">By Doctors, For Doctors</span>
          </h2>
          <div class="mt-6 max-w-3xl mx-auto text-xl text-gray-600 leading-relaxed">
            <p class="mb-4">
              At doc2doc.health, we provide virtual medical scribing services delivered exclusively by physicians and medical graduates. 
              Our scribes are not just trained in documentation—they are trained in medicine.
            </p>
            <p>
              With clinical experience and deep understanding of patient care, we bring unmatched accuracy, efficiency, and trust to every chart.
            </p>
          </div>
        </div>

        <!-- Floating cards animation -->
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="(feature, index) in aboutFeatures"
            :key="index"
            class="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all duration-500 border border-gray-100 hover:border-blue-100 relative overflow-hidden group"
            :style="{ animation: `floatVertical ${5 + index}s ease-in-out infinite alternate` }"
          >
            <div class="absolute -right-10 -top-10 w-32 h-32 bg-blue-50 rounded-full opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
            <div class="relative z-10">
              <div class="flex items-center mb-4">
                <div class="flex-shrink-0 bg-blue-100 p-3 rounded-lg">
                  <component 
                    :is="feature.icon" 
                    class="h-6 w-6 text-blue-600" 
                    aria-hidden="true"
                  />
                </div>
                <h3 class="ml-3 text-lg font-medium text-gray-900">{{ feature.title }}</h3>
              </div>
              <p class="mt-2 text-gray-600">{{ feature.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section with Parallax Effect -->
    <section class="py-20 bg-gray-50 relative overflow-hidden">
      <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-1.2.1&auto=format&fit=cover&w=1500&q=80')] bg-cover bg-center opacity-5"></div>
      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            WHAT WE DO
          </span>
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Comprehensive Clinical Support
          </h2>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-2 gap-8">
          <div class="bg-white p-8 rounded-xl shadow-lg border border-gray-100">
            <h3 class="text-2xl font-bold text-gray-900 mb-6">Our Services</h3>
            <ul class="space-y-4">
              <li 
                v-for="(service, index) in servicesList"
                :key="index"
                class="flex items-start"
              >
                <CheckCircleIcon class="h-6 w-6 text-blue-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-gray-700">{{ service }}</span>
              </li>
            </ul>
          </div>
          <div class="bg-gradient-to-br from-blue-600 to-indigo-700 p-8 rounded-xl shadow-lg text-white">
            <h3 class="text-2xl font-bold mb-6">Why We're Different</h3>
            <ul class="space-y-4">
              <li 
                v-for="(point, index) in differentiators"
                :key="index"
                class="flex items-start"
              >
                <CheckCircleIcon class="h-6 w-6 text-blue-300 mr-3 mt-1 flex-shrink-0" />
                <span>{{ point }}</span>
              </li>
            </ul>
            <div class="mt-8 pt-6 border-t border-blue-400/30">
              <p class="font-medium">We elevate scribing into a clinical partnership—because we've walked in your shoes.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Specialty Support Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            WHO WE SERVE
          </span>
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Tailored for Your Specialty
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            Our physician scribes have experience across specialties
          </p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-6">
          <div 
            v-for="(specialty, index) in specialties"
            :key="index"
            class="bg-white p-5 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 text-center group transform hover:-translate-y-2"
          >
            <div class="mx-auto h-16 w-16 flex items-center justify-center mb-4 text-blue-600">
              <component :is="specialty.icon" class="h-12 w-12" />
            </div>
            <h3 class="text-sm font-medium text-gray-900">{{ specialty.name }}</h3>
            <p class="mt-1 text-xs text-gray-500">{{ specialty.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials with Fade Animation -->
    <section class="py-20 bg-blue-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            TRUSTED BY PHYSICIANS
          </span>
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            What Our Clients Say
          </h2>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <div 
            v-for="(testimonial, index) in testimonials"
            :key="index"
            class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-all duration-500 transform hover:-translate-y-3"
            :style="{ animation: `fadeIn ${index * 0.3 + 0.5}s ease-out` }"
          >
            <div class="flex items-center mb-4">
              <img 
                :src="testimonial.avatar" 
                :alt="testimonial.name" 
                class="h-12 w-12 rounded-full object-cover"
              >
              <div class="ml-4">
                <h3 class="text-lg font-medium text-gray-900">{{ testimonial.name }}</h3>
                <p class="text-sm text-gray-500">{{ testimonial.title }}</p>
              </div>
            </div>
            <div class="flex mb-3">
              <StarIcon v-for="i in 5" :key="i" class="h-5 w-5 text-yellow-400" />
            </div>
            <p class="text-gray-600 italic mb-4">"{{ testimonial.quote }}"</p>
            <div class="mt-4 pt-4 border-t border-gray-100 flex items-center text-sm text-gray-500">
              <CalendarIcon class="h-4 w-4 mr-2" />
              {{ testimonial.date }}
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Final CTA with Gradient Animation -->
    <section class="relative overflow-hidden">
      <div class="absolute inset-0 bg-gradient-to-r from-blue-600 to-indigo-700 animate-gradient-x"></div>
      <div class="relative max-w-7xl mx-auto px-4 py-16 sm:px-6 lg:px-8 lg:py-24 text-center">
        <h2 class="text-3xl font-extrabold tracking-tight text-white sm:text-4xl">
          Ready to reclaim your clinical day?
        </h2>
        <p class="mt-4 max-w-2xl mx-auto text-xl text-blue-100">
          Join hundreds of physicians who trust doc2doc.health with their documentation.
        </p>
        <div class="mt-10 flex flex-wrap justify-center gap-4">
          <button 
            @click="navigateTo('/contact')" 
            class="px-8 py-4 border border-transparent text-base font-medium rounded-full text-blue-600 bg-white hover:bg-gray-100 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
          >
            Start Free Trial
          </button>
          <button 
            @click="navigateTo('/demo')" 
            class="px-8 py-4 border-2 border-white text-base font-medium rounded-full text-white hover:bg-blue-700/30 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
          >
            Schedule Demo
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import {
  // Core icons
  UserGroupIcon,
  ClockIcon,
  DocumentTextIcon,
  ShieldCheckIcon,
  ChatBubbleLeftRightIcon as ChatAltIcon,
  CogIcon,
  InboxIcon,
  ClipboardDocumentListIcon as ClipboardListIcon,
  PhoneIcon,
  CheckCircleIcon,
  StarIcon,
  CalendarIcon,
  // Specialty icons
  HeartIcon,
  UserIcon,
  UserGroupIcon as FamilyMedicineIcon,
  AcademicCapIcon,
  BeakerIcon,
  CubeTransparentIcon as OrthopedicsIcon,
  CpuChipIcon as NeurologyIcon,
  ArrowTrendingUpIcon as GrowthIcon,
  BoltIcon as EnergyIcon,
  BuildingLibraryIcon as HospitalIcon
} from '@heroicons/vue/24/outline';

const router = useRouter();

// Specialty data with properly defined icons
const specialties = ref([
  { 
    name: 'Family Medicine', 
    icon: FamilyMedicineIcon,
    description: 'Comprehensive care for all ages'
  },
  { 
    name: 'Internal Medicine', 
    icon: BeakerIcon,
    description: 'Adult medical diagnosis'
  },
  { 
    name: 'Cardiology', 
    icon: HeartIcon,
    description: 'Heart specialists'
  },
  { 
    name: 'Orthopedics', 
    icon: OrthopedicsIcon,
    description: 'Musculoskeletal experts'
  },
  { 
    name: 'Pediatrics', 
    icon: AcademicCapIcon,
    description: 'Child healthcare'
  },
  { 
    name: 'Neurology', 
    icon: NeurologyIcon,
    description: 'Nervous system specialists'
  }
]);

// Testimonials data
const testimonials = ref([
  {
    name: 'Dr. Sarah Johnson',
    title: 'Family Medicine, CA',
    quote: 'doc2doc.health cut my charting time from 3 hours to just 45 minutes daily. The notes are clinically accurate and my patients have noticed I\'m more present during visits.',
    avatar: 'https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '2 months ago'
  },
  {
    name: 'Dr. Michael Chen',
    title: 'Cardiology, NY',
    quote: 'As a specialist, I need precise documentation. The physician scribes at doc2doc.health understand cardiology terminology and my notes have never been better.',
    avatar: 'https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '3 weeks ago'
  },
  {
    name: 'Dr. Priya Patel',
    title: 'Pediatrics, TX',
    quote: 'The combination of AI efficiency with physician review is game-changing. I\'ve regained time with my family while maintaining excellent documentation.',
    avatar: 'https://images.unsplash.com/photo-1594824476967-48c8b964273f?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '1 month ago'
  }
]);

// Features data
const aboutFeatures = ref([
  {
    title: 'Physician Scribes',
    description: 'Our scribes are foreign-trained MDs with clinical experience',
    icon: UserGroupIcon
  },
  {
    title: 'AI-Assisted',
    description: 'Combines physician insight with AI efficiency for faster turnaround',
    icon: CogIcon
  },
  {
    title: 'Specialty-Specific',
    description: 'Tailored documentation for your practice area',
    icon: DocumentTextIcon
  },
  {
    title: 'HIPAA Secure',
    description: 'Enterprise-grade security and compliance',
    icon: ShieldCheckIcon
  },
  {
    title: 'Dedicated Support',
    description: 'Personalized service with quality control',
    icon: ChatAltIcon
  },
  {
    title: 'Time Savings',
    description: 'Reduce documentation time by 50% or more',
    icon: ClockIcon
  }
]);

// Services list
const servicesList = ref([
  'Accurate, real-time charting during virtual or in-person visits',
  'Support for all major EMR systems',
  'Specialty-specific documentation with clinical insight',
  'HIPAA-compliant, secure, and confidential service',
  'Lab tracking and message management',
  'Chart preparation for upcoming visits'
]);

// Differentiators
const differentiators = ref([
  'Advanced clinical understanding',
  'Higher accuracy and efficiency',
  'Fewer clarifications needed',
  'Seamless collaboration with providers',
  'Reduced after-hours documentation',
  'Physician-to-physician communication'
]);

const navigateTo = (path) => {
  router.push(path);
};
</script>

<style>
@keyframes float {
  0% {
    transform: translateY(0) translateX(0);
  }
  50% {
    transform: translateY(-20px) translateX(10px);
  }
  100% {
    transform: translateY(0) translateX(0);
  }
}

@keyframes floatVertical {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-10px);
  }
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

@keyframes animate-gradient-x {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.animate-gradient-x {
  background-size: 200% 200%;
  animation: animate-gradient-x 8s ease infinite;
}

/* Specialty icon colors */
.text-blue-600 {
  color: #2563eb;
}
</style>