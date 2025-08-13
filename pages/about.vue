<template>
  <div class="bg-white">
    <!-- Hero Section -->
    <section class="relative bg-navy-900 text-white overflow-hidden">
      <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1576091160399-112ba8a25d16?ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80')] bg-cover bg-center opacity-20"></div>
      <div class="relative max-w-7xl mx-auto px-6 py-24 sm:py-32 lg:px-8 text-center">
        <div class="flex items-center justify-center mb-6">
          <span class="text-2xl font-bold text-green-400">doc2doc.health</span>
          <span class="ml-3 px-3 py-1 rounded-full bg-green-900/20 text-green-400 text-xs font-medium">Physician-Led</span>
        </div>
        <h1 class="text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl mb-6">
          <span class="block">By Physicians,</span>
          <span class="block text-green-400">For Physicians</span>
        </h1>
        <p class="text-xl text-navy-100 max-w-3xl mx-auto">
          Our mission is to free doctors from documentation burdens so they can focus on what matters most—patient care.
        </p>
      </div>
    </section>

    <!-- Our Story -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
          <div class="mb-12 lg:mb-0">
            <div class="relative rounded-2xl overflow-hidden shadow-xl">
              <img 
                src="https://images.unsplash.com/photo-1581056771107-24ca5f033842?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&h=600&q=80" 
                alt="Physician team discussing patient care"
                class="w-full h-auto object-cover"
              >
              <div class="absolute -bottom-6 -right-6 w-32 h-32 bg-green-500 rounded-full opacity-20"></div>
            </div>
          </div>
          <div>
            <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
              OUR STORY
            </span>
            <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl mb-6">
              Born from Physician Frustration
            </h2>
            <p class="text-navy-600 mb-4">
              In 2018, a group of physicians at a Boston teaching hospital grew increasingly frustrated with the time spent on documentation. Despite trying multiple scribe services, they found that non-clinical scribes often missed critical nuances in medical decision-making.
            </p>
            <p class="text-navy-600 mb-6">
              They envisioned a better way—a service where <strong>physicians document for physicians</strong>. doc2doc.health was founded to bring clinical expertise back into medical documentation.
            </p>
            <div class="flex items-center space-x-4">
              <div class="flex-shrink-0 bg-green-100 p-3 rounded-full">
                <UserGroupIcon class="h-6 w-6 text-green-600" />
              </div>
              <p class="text-sm text-navy-500">
                <strong>12+ Physician Founders</strong> across primary care and specialties
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Mission & Values -->
    <section class="py-20 bg-navy-50">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
            OUR MISSION
          </span>
          <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
            Restoring the Joy of Medicine
          </h2>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <div 
            v-for="(value, index) in values"
            :key="index"
            class="bg-white p-8 rounded-xl shadow-md hover:shadow-lg transition-all"
          >
            <div class="w-14 h-14 bg-green-100 rounded-lg flex items-center justify-center mb-6">
              <component :is="value.icon" class="h-6 w-6 text-green-600" />
            </div>
            <h3 class="text-xl font-semibold text-navy-900 mb-3">{{ value.title }}</h3>
            <p class="text-navy-600">{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
<section class="py-20 bg-white">
  <div class="max-w-7xl mx-auto px-6 lg:px-8">
    <div class="text-center mb-16">
      <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
        LEADERSHIP TEAM
      </span>
      <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
        Physician-Led Innovation
      </h2>
    </div>

    <div class="grid md:grid-cols-2 lg:grid-cols-2 gap-8 max-w-2xl mx-auto">
      <!-- Dr. Abel Elias -->
      <div class="bg-white rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-all">
        <div class="w-full h-64 bg-navy-100 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-32 w-32 text-navy-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
          </svg>
        </div>
        <div class="p-6">
          <h3 class="text-lg font-semibold text-navy-900">Dr. Abel Elias</h3>
          <p class="text-sm text-green-600 mb-2">Founder & CEO</p>
          <p class="text-sm text-navy-500">Physician entrepreneur leading innovation in healthcare technology.</p>
          <div class="mt-4 flex space-x-3">
            <a href="#" class="text-navy-400 hover:text-green-600">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-5 h-5">
                <path d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"/>
              </svg>
            </a>
          </div>
        </div>
      </div>

      <!-- Dr. Edilawit -->
      <div class="bg-white rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-all">
        <div class="w-full h-64 bg-navy-100 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-32 w-32 text-navy-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
          </svg>
        </div>
        <div class="p-6">
          <h3 class="text-lg font-semibold text-navy-900">Dr. Edilawit</h3>
          <p class="text-sm text-green-600 mb-2">Medical Director</p>
          <p class="text-sm text-navy-500">Talented physician overseeing clinical operations and patient care.</p>
          <div class="mt-4 flex space-x-3">
            <a href="#" class="text-navy-400 hover:text-green-600">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-5 h-5">
                <path d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"/>
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
<!-- Why Choose Us -->
<section class="py-20 bg-gradient-to-r from-gray-50 to-gray-100 text-gray-900">
  <div class="max-w-7xl mx-auto px-6 lg:px-8">
    <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
      <!-- Left Content -->
      <div class="mb-12 lg:mb-0">
        <span class="inline-block px-4 py-2 text-sm font-semibold text-green-700 bg-green-100 rounded-full shadow-sm mb-4">
          WHY CHOOSE US
        </span>
        <h2 class="text-3xl font-bold sm:text-4xl mb-6">
          The Physician Difference
        </h2>
        <p class="text-gray-700 mb-8 leading-relaxed">
          Traditional scribes take notes. Our physician scribes <strong class="text-green-700">understand medicine at your level</strong>, 
          ensuring accurate, clinically nuanced documentation that reflects your decision-making process.
        </p>
        <ul class="space-y-4">
          <li class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-green-600 flex-shrink-0 mt-1 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
            </svg>
            <span class="text-gray-700">Scribes are physicians or medical graduates with clinical experience</span>
          </li>
          <li class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-green-600 flex-shrink-0 mt-1 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
            </svg>
            <span class="text-gray-700">Specialty-matched documentation for precise terminology</span>
          </li>
          <li class="flex items-start">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-green-600 flex-shrink-0 mt-1 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
            </svg>
            <span class="text-gray-700">50%+ reduction in documentation time for most physicians</span>
          </li>
        </ul>
      </div>

      <!-- Right Image -->
      <div class="relative">
        <div class="bg-white p-1 rounded-2xl shadow-lg inline-block transform hover:scale-105 transition-transform duration-300">
          <img 
            src="data:image/jpeg;base64,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" 
            alt="Doctor reviewing notes with scribe"
            class="rounded-xl w-full h-auto"
          >
        </div>
        <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-green-200 rounded-full opacity-30 blur-lg -z-10"></div>
      </div>
    </div>
  </div>
</section>


    <!-- CTA Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8 text-center">
        <div class="bg-gradient-to-r from-green-500 to-green-600 rounded-2xl p-12 shadow-xl">
          <h2 class="text-3xl font-bold text-white sm:text-4xl mb-6">
            Ready to experience physician-powered scribing?
          </h2>
          <p class="text-xl text-green-100 max-w-2xl mx-auto mb-8">
            Join the movement to restore joy to medical practice.
          </p>
          <div class="flex flex-wrap justify-center gap-4">
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border border-transparent text-lg font-medium rounded-lg text-green-600 bg-white hover:bg-navy-100 shadow-md"
            >
              Schedule Demo
            </button>
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border-2 border-white text-lg font-medium rounded-lg text-white hover:bg-green-700 shadow-md"
            >
              Contact Us
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { 
  UserGroupIcon,
  LightBulbIcon,
  ShieldCheckIcon,
  CheckCircleIcon,
  ClockIcon
} from '@heroicons/vue/24/outline'

// Values data
const values = ref([
  {
    icon: UserGroupIcon,
    title: 'Physician First',
    description: 'Every scribe is a physician or medical graduate with clinical experience—no non-clinical scribes.'
  },
  {
    icon: ClockIcon,
    title: 'Time Reclaimed',
    description: 'We give you back 2.5+ hours daily to spend with patients, family, or yourself.'
  },
  {
    icon: ShieldCheckIcon,
    title: 'Clinical Integrity',
    description: 'Documentation that accurately reflects your medical decision-making process.'
  }
])

// Team data
const team = ref([
  {
    name: 'Dr. Sarah Chen, MD',
    role: 'Co-Founder & CEO',
    bio: 'Emergency physician turned entrepreneur. Founded doc2doc after documenting until midnight one too many times.',
    photo: 'https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&h=400&q=80',
    linkedin: '#'
  },
  {
    name: 'Dr. Michael Rodriguez, MD',
    role: 'Chief Medical Officer',
    bio: 'Board-certified internist leading our physician training and quality assurance programs.',
    photo: 'https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&h=400&q=80',
    linkedin: '#'
  },
  {
    name: 'Dr. Priya Patel, MD',
    role: 'Director of Specialty Services',
    bio: 'Cardiologist who ensures our specialists receive specialty-matched documentation support.',
    photo: 'https://images.unsplash.com/photo-1594824476967-48c8b964273f?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&h=400&q=80',
    linkedin: '#'
  },
  {
    name: 'Dr. James Wilson, MD',
    role: 'Head of Physician Experience',
    bio: 'Family physician focused on making doc2doc seamlessly integrate with clinical workflows.',
    photo: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&auto=format&fit=crop&w=400&h=400&q=80',
    linkedin: '#'
  }
])

const navigateTo = (path) => {
  // Router navigation logic here
  console.log(`Navigating to: ${path}`)
}
</script>

<style>
/* Custom color palette */
.bg-navy-900 {
  background-color: #0f172a;
}
.bg-navy-800 {
  background-color: #1e293b;
}
.bg-navy-50 {
  background-color: #f8fafc;
}
.text-navy-900 {
  color: #0f172a;
}
.text-navy-700 {
  color: #334155;
}
.text-navy-600 {
  color: #475569;
}
.text-navy-500 {
  color: #64748b;
}
.text-navy-400 {
  color: #94a3b8;
}
.text-navy-100 {
  color: #f1f5f9;
}
.bg-green-600 {
  background-color: #16a34a;
}
.bg-green-500 {
  background-color: #22c55e;
}
.text-green-600 {
  color: #16a34a;
}
.text-green-500 {
  color: #22c55e;
}
.text-green-400 {
  color: #4ade80;
}
.bg-green-100 {
  background-color: #dcfce7;
}
.border-navy-200 {
  border-color: #e2e8f0;
}
.border-navy-100 {
  border-color: #f1f5f9;
}
</style>