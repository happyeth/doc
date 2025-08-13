<template>
  <div class="bg-white">
    <!-- Top Bar with Phone Number -->
    <div class="bg-navy-900 text-white py-2 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto flex justify-between items-center">
        <div class="flex items-center space-x-2">
          <PhoneIcon class="h-4 w-4 text-green-400" />
          <span class="text-sm font-medium">+1 (240) 475-1441</span>
        </div>
        <span class="text-xs text-green-400">{{ currentDate }}</span>
      </div>
    </div>

    <!-- Hero Section with Light Green Background -->
    <section class="relative bg-green-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 sm:py-24">
        <div class="text-center">
          <h1 class="text-4xl font-extrabold tracking-tight text-navy-900 sm:text-5xl lg:text-6xl">
            <span class="block">Welcome to doc2doc.health</span>
            <span class="block text-green-600">Physician-Powered Clinical Documentation</span>
          </h1>
          <p class="mt-6 text-xl text-navy-700 max-w-3xl mx-auto">
            Reduce documentation time by 50% with our physician-led virtual scribing service. 
            Focus on patients while we handle your charts with clinical precision.
          </p>
          <div class="mt-10 flex justify-center space-x-4">
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-green-600 hover:bg-green-700 shadow-lg hover:shadow-xl transition-all duration-300"
            >
              Contact Now
            </button>
            <button 
              @click="navigateTo('/contact')" 
              class="px-8 py-3 border-2 border-navy-900 text-base font-medium rounded-md text-navy-900 bg-white hover:bg-navy-50 shadow-lg hover:shadow-xl transition-all duration-300"
            >
              Schedule Demo
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section class="py-16 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
          <div class="mb-12 lg:mb-0">
            <img 
              src="https://images.unsplash.com/photo-1579684453423-f84349ef60b0?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
              alt="Doctor with patient" 
              class="rounded-xl shadow-lg w-full h-auto"
            >
          </div>
          <div>
            <h2 class="text-3xl font-extrabold text-navy-900 mb-6">About doc2doc.health</h2>
            <p class="text-navy-700 mb-4">
              At doc2doc.health, we provide virtual medical scribing services delivered exclusively by physicians and medical graduates. Our scribes are not just trained in documentation—they are trained in medicine.
            </p>
            <p class="text-navy-700 mb-6">
              With clinical experience and deep understanding of patient care, we bring unmatched accuracy, efficiency, and trust to every chart.
            </p>
            <p class="text-navy-700">
              Our journey began when a group of physicians, overwhelmed by charting demands, realized that real solutions require real clinical knowledge. That's why we built a service by doctors, for doctors—freeing healthcare providers from the burden of documentation, so they can return their focus to where it belongs: the patient and have ample amount of time with their beloved ones as well.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="py-16 bg-green-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <h2 class="text-3xl font-extrabold text-navy-900 sm:text-4xl">
            What We Do
          </h2>
          <div class="mt-4 h-1 w-20 bg-green-500 mx-auto"></div>
          <p class="mt-6 text-xl text-navy-700 max-w-3xl mx-auto">
            We offer real-time virtual scribing, tailored to your workflow and specialty.
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-2 gap-8">
          <div class="bg-white p-8 rounded-xl shadow-sm hover:shadow-md transition-all duration-300 border border-gray-100">
            <h3 class="text-2xl font-bold text-navy-900 mb-6">Our Services</h3>
            <ul class="space-y-4">
              <li class="flex items-start">
                <CheckCircleIcon class="h-6 w-6 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Accurate, real-time charting during virtual or in-person visits (via remote access)</span>
              </li>
              <li class="flex items-start">
                <CheckCircleIcon class="h-6 w-6 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Support for all major EMR systems</span>
              </li>
              <li class="flex items-start">
                <CheckCircleIcon class="h-6 w-6 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Specialty-specific documentation with clinical insight</span>
              </li>
              <li class="flex items-start">
                <CheckCircleIcon class="h-6 w-6 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">HIPAA-compliant, secure, and confidential service</span>
              </li>
            </ul>
            <p class="mt-6 text-navy-600 italic">
              We work quietly in the background—so your focus stays on the patient, not the computer.
            </p>
          </div>
          <div class="bg-white p-8 rounded-xl shadow-sm hover:shadow-md transition-all duration-300 border border-gray-100">
            <img 
              src="https://images.unsplash.com/photo-1581595219315-a187dd40c322?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
              alt="Doctor using computer" 
              class="rounded-lg mb-6 w-full h-auto"
            >
            <h3 class="text-2xl font-bold text-navy-900 mb-6">Why We're Different</h3>
            <p class="text-navy-700 mb-4">
              Our scribes are physicians, not just note-takers. That makes all the difference.
            </p>
            <ul class="space-y-3">
              <li class="flex items-start">
                <CheckIcon class="h-5 w-5 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Advanced clinical understanding</span>
              </li>
              <li class="flex items-start">
                <CheckIcon class="h-5 w-5 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Higher accuracy and efficiency</span>
              </li>
              <li class="flex items-start">
                <CheckIcon class="h-5 w-5 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Fewer clarifications</span>
              </li>
              <li class="flex items-start">
                <CheckIcon class="h-5 w-5 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Seamless collaboration with providers</span>
              </li>
              <li class="flex items-start">
                <CheckIcon class="h-5 w-5 text-green-500 mr-3 mt-1 flex-shrink-0" />
                <span class="text-navy-700">Reduced after-hours documentation</span>
              </li>
            </ul>
            <p class="mt-6 text-navy-600 italic">
              We elevate scribing into a clinical partnership—because we've walked in your shoes.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Mission Section -->
    <section class="py-16 bg-navy-900 text-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
          <div class="mb-12 lg:mb-0">
            <h2 class="text-3xl font-extrabold mb-6">Our Mission</h2>
            <p class="text-green-300 text-lg">
              To improve the lives of healthcare providers by removing the burden of documentation, enhancing the quality of clinical records, and restoring time and energy for patient care—all through high-level, physician-powered virtual support.
            </p>
          </div>
          <div>
            <img 
              src="https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
              alt="Medical team" 
              class="rounded-xl shadow-lg w-full h-auto"
            >
          </div>
        </div>
      </div>
    </section>

    <!-- Final CTA -->
    <section class="bg-navy-900 text-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 text-center">
        <h2 class="text-3xl font-extrabold tracking-tight sm:text-4xl">
          Ready to Work Smarter?
        </h2>
        <p class="mt-4 max-w-2xl mx-auto text-xl text-green-300">
          Contact us today or schedule a free demo to learn how physician-level virtual scribing can transform your practice.
        </p>
        <div class="mt-10 flex flex-wrap justify-center gap-4">
          <button 
            @click="navigateTo('/contact')" 
            class="px-8 py-3 border border-transparent text-base font-medium rounded-md text-navy-900 bg-green-400 hover:bg-green-500 shadow-lg hover:shadow-xl transition-all duration-300"
          >
            Contact Now
          </button>
          <button 
            @click="navigateTo('/demo')" 
            class="px-8 py-3 border-2 border-white text-base font-medium rounded-md text-white hover:bg-navy-800 shadow-lg hover:shadow-xl transition-all duration-300"
          >
            Schedule Demo
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import { useRouter } from 'vue-router';
import {
  PhoneIcon,
  CheckCircleIcon,
  CheckIcon,
  UserGroupIcon
} from '@heroicons/vue/24/outline';

const router = useRouter();

// Current date
const currentDate = computed(() => {
  const options = { day: 'numeric', month: 'long', hour: '2-digit', minute: '2-digit' };
  return new Date().toLocaleDateString('en-US', options);
});

const navigateTo = (path) => {
  router.push(path);
};
</script>

<style>
/* Custom color palette */
.bg-navy-900 {
  background-color: #0f172a;
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
.bg-green-50 {
  background-color: #f0fdf4;
}
.text-green-600 {
  color: #16a34a;
}
.bg-green-600 {
  background-color: #16a34a;
}
.hover\:bg-green-700:hover {
  background-color: #15803d;
}
.text-green-400 {
  color: #4ade80;
}
.bg-green-400 {
  background-color: #4ade80;
}
.hover\:bg-green-500:hover {
  background-color: #22c55e;
}
.text-green-300 {
  color: #86efac;
}
.bg-navy-800 {
  background-color: #1e293b;
}
.bg-navy-50 {
  background-color: #f1f5f9;
}

/* Transitions */
.transition-all {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms;
}
</style>