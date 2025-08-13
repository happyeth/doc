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
          <span class="block">Trusted by</span>
          <span class="block text-green-400">Healthcare Professionals</span>
        </h1>
        <p class="text-xl text-navy-100 max-w-3xl mx-auto">
          Real stories from physicians who regained time for patient care with our virtual scribing.
        </p>
      </div>
    </section>

    <!-- Testimonial Grid -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
            PHYSICIAN TESTIMONIALS
          </span>
          <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
            What Doctors Are Saying
          </h2>
        </div>

        <!-- Filter Tabs -->
        <div class="flex justify-center mb-12">
          <div class="inline-flex rounded-lg bg-navy-50 p-1">
            <button 
              v-for="(filter, index) in filters" 
              :key="index"
              @click="activeFilter = filter.value"
              :class="{
                'bg-white shadow-md': activeFilter === filter.value,
                'text-navy-600 hover:text-navy-900': activeFilter !== filter.value
              }"
              class="px-4 py-2 text-sm font-medium rounded-md transition-all"
            >
              {{ filter.label }}
            </button>
          </div>
        </div>

        <!-- Testimonial Cards -->
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="(testimonial, index) in filteredTestimonials"
            :key="index"
            class="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 border border-navy-100"
          >
            <div class="flex items-center mb-4">
              <img 
                :src="testimonial.avatar" 
                :alt="testimonial.name" 
                class="h-12 w-12 rounded-full object-cover"
              >
              <div class="ml-4">
                <h3 class="text-lg font-semibold text-navy-900">{{ testimonial.name }}</h3>
                <p class="text-sm text-navy-500">{{ testimonial.specialty }}</p>
              </div>
            </div>
            <div class="flex mb-3">
              <StarIcon v-for="i in 5" :key="i" class="h-5 w-5 text-yellow-400" />
            </div>
            <p class="text-navy-600 italic mb-6">"{{ testimonial.quote }}"</p>
            <div class="mt-4 pt-4 border-t border-navy-100 flex items-center text-sm text-navy-500">
              <CalendarIcon class="h-4 w-4 mr-2" />
              {{ testimonial.date }}
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Video Testimonials -->
    <section class="py-20 bg-navy-50">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
            VIDEO TESTIMONIALS
          </span>
          <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
            Hear It From Our Physicians
          </h2>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="(video, index) in videoTestimonials"
            :key="index"
            class="bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-all duration-300"
          >
            <div class="relative pt-[56.25%] bg-navy-900">
              <img 
                :src="video.thumbnail" 
                :alt="video.name"
                class="absolute inset-0 w-full h-full object-cover opacity-80"
              >
              <div class="absolute inset-0 flex items-center justify-center">
                <button class="bg-green-600 hover:bg-green-700 rounded-full p-4 shadow-lg transition-all">
                  <PlayIcon class="h-6 w-6 text-white" />
                </button>
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-lg font-semibold text-navy-900 mb-2">{{ video.name }}</h3>
              <p class="text-sm text-navy-500 mb-4">{{ video.specialty }}</p>
              <p class="text-navy-600">{{ video.excerpt }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="py-20 bg-green-600 text-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-white rounded-full mb-4">
            BY THE NUMBERS
          </span>
          <h2 class="text-3xl font-bold sm:text-4xl">
            The doc2doc.health Impact
          </h2>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <div 
            v-for="(stat, index) in stats"
            :key="index"
            class="bg-white/10 p-8 rounded-xl backdrop-blur-sm"
          >
            <div class="text-4xl font-bold mb-2">{{ stat.value }}</div>
            <p class="text-green-100">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8 text-center">
        <div class="bg-gradient-to-r from-green-500 to-green-600 rounded-2xl p-8 shadow-xl">
          <h2 class="text-3xl font-bold text-white sm:text-4xl mb-6">
            Ready to experience the difference?
          </h2>
          <p class="text-xl text-green-100 max-w-2xl mx-auto mb-8">
            Join hundreds of physicians who trust doc2doc.health with their clinical documentation.
          </p>
          <div class="flex flex-wrap justify-center gap-4">
            <button 
              @click="navigateTo('/demo')" 
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
import { ref, computed } from 'vue'
import { 
  StarIcon,
  CalendarIcon,
  PlayIcon
} from '@heroicons/vue/24/outline'

// Testimonial data
const testimonials = ref([
  {
    name: 'Dr. Sarah Johnson',
    specialty: 'Family Medicine, CA',
    quote: 'doc2doc.health cut my charting time from 3 hours to just 45 minutes daily. The physician scribes understand clinical context perfectly.',
    avatar: 'https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '2 months ago',
    category: 'primary-care'
  },
  {
    name: 'Dr. Michael Chen',
    specialty: 'Cardiology, NY',
    quote: 'As a specialist, I need precise documentation. The physician scribes at doc2doc.health understand cardiology terminology flawlessly.',
    avatar: 'https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '3 weeks ago',
    category: 'specialty'
  },
  {
    name: 'Dr. Priya Patel',
    specialty: 'Pediatrics, TX',
    quote: 'The combination of physician expertise with AI efficiency is game-changing. I\'ve regained time with my family while maintaining excellent documentation.',
    avatar: 'https://images.unsplash.com/photo-1594824476967-48c8b964273f?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '1 month ago',
    category: 'specialty'
  },
  {
    name: 'Dr. James Wilson',
    specialty: 'Internal Medicine, FL',
    quote: 'After trying multiple scribe services, doc2doc.health is the only one where I don\'t have to constantly correct the notes. They just get it right the first time.',
    avatar: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '2 weeks ago',
    category: 'primary-care'
  },
  {
    name: 'Dr. Emily Rodriguez',
    specialty: 'Endocrinology, IL',
    quote: 'The accuracy of complex endocrine documentation has improved dramatically since switching to doc2doc.health. My coding has never been better.',
    avatar: 'https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '5 months ago',
    category: 'specialty'
  },
  {
    name: 'Dr. Robert Kim',
    specialty: 'Emergency Medicine, WA',
    quote: 'In the ED, speed and accuracy are critical. doc2doc.health delivers both, allowing me to focus on patient care during busy shifts.',
    avatar: 'https://images.unsplash.com/photo-1568602471122-7832951cc4c5?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80',
    date: '3 months ago',
    category: 'emergency'
  }
])

const videoTestimonials = ref([
  {
    name: 'Dr. Amanda Lee',
    specialty: 'Neurology, MA',
    excerpt: 'See how doc2doc.health handles complex neurology documentation',
    thumbnail: 'https://images.unsplash.com/photo-1559839734-2b71ea197ec2?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&h=400&q=80'
  },
  {
    name: 'Dr. Carlos Mendez',
    specialty: 'Oncology, CA',
    excerpt: 'How our oncology practice improved documentation quality',
    thumbnail: 'https://images.unsplash.com/photo-1622253692010-333f2da6031d?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&h=400&q=80'
  },
  {
    name: 'Dr. Lisa Thompson',
    specialty: 'Family Medicine, OR',
    excerpt: 'Regaining work-life balance with virtual scribing',
    thumbnail: 'https://images.unsplash.com/photo-1594824476967-48c8b964273f?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&h=400&q=80'
  }
])

const stats = ref([
  { value: '2.5+ hours', label: 'Daily time saved per physician' },
  { value: '98%', label: 'Satisfaction rate' },
  { value: '24/48 hrs', label: 'Average onboarding time' }
])

const filters = ref([
  { label: 'All Specialties', value: 'all' },
  { label: 'Primary Care', value: 'primary-care' },
  { label: 'Specialists', value: 'specialty' },
  { label: 'Emergency', value: 'emergency' }
])

const activeFilter = ref('all')

const filteredTestimonials = computed(() => {
  if (activeFilter.value === 'all') return testimonials.value
  return testimonials.value.filter(t => t.category === activeFilter.value)
})

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