<template>
  <div class="bg-white">
    <!-- Hero Section -->
    <section class="relative bg-navy-900 text-white overflow-hidden">
      <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1576091160399-112ba8a25d16?ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80')] bg-cover bg-center opacity-20"></div>
      <div class="relative max-w-7xl mx-auto px-6 py-24 sm:py-32 lg:px-8 text-center">
        <h1 class="text-4xl font-bold tracking-tight sm:text-5xl lg:text-6xl mb-6">
          <span class="block">Physician-Powered</span>
          <span class="block text-green-400">Medical Scribing</span>
        </h1>
        <p class="text-xl text-navy-100 max-w-3xl mx-auto">
          Unparalleled clinical documentation by physicians, for physicians
        </p>
        <div class="mt-10 flex justify-center gap-4">
          <button 
            @click="navigateTo('/contact')" 
            class="px-8 py-3 rounded-lg bg-white text-navy-900 font-semibold hover:bg-navy-100 transition-colors shadow-lg"
          >
            Contact Us
          </button>
        </div>
      </div>
    </section>

    <!-- Logo Cloud -->
   

    <!-- Value Proposition -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
            WHY WELKESA
          </span>
          <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
            The Gold Standard in Medical Scribing
          </h2>
        </div>

        <div class="grid md:grid-cols-3 gap-12">
          <div v-for="(value, index) in values" :key="index" class="text-center">
            <div class="mx-auto h-16 w-16 bg-green-100 rounded-full flex items-center justify-center mb-4">
              <component :is="value.icon" class="h-8 w-8 text-green-600" />
            </div>
            <h3 class="text-xl font-semibold text-navy-900 mb-3">{{ value.title }}</h3>
            <p class="text-navy-600">{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Services -->
    <section class="py-20 bg-navy-50">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
            OUR SERVICES
          </span>
          <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
            Comprehensive Scribing Solutions
          </h2>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div v-for="(service, index) in services" :key="index" class="bg-white p-8 rounded-xl shadow-sm hover:shadow-md transition-shadow">
            <div class="h-12 w-12 bg-green-100 rounded-lg flex items-center justify-center mb-4">
              <component :is="service.icon" class="h-6 w-6 text-green-600" />
            </div>
            <h3 class="text-lg font-semibold text-navy-900 mb-2">{{ service.title }}</h3>
            <p class="text-navy-600 text-sm">{{ service.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- How It Works -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-600 bg-green-100 rounded-full mb-4">
            HOW IT WORKS
          </span>
          <h2 class="text-3xl font-bold text-navy-900 sm:text-4xl">
            Simple Integration, Immediate Results
          </h2>
        </div>

        <div class="relative">
          <div class="hidden lg:block absolute top-0 left-1/2 h-full w-0.5 bg-green-100 transform -translate-x-1/2"></div>
          <div class="space-y-12 lg:space-y-0">
            <div v-for="(step, index) in steps" :key="index" class="relative lg:grid lg:grid-cols-2 lg:gap-8">
              <div :class="{'lg:order-last': index % 2 !== 0}" class="lg:py-8">
                <div class="lg:pr-8">
                  <div class="lg:absolute lg:top-0 lg:left-1/2 lg:h-6 lg:w-6 lg:bg-green-500 lg:rounded-full lg:transform lg:-translate-x-1/2 -translate-y-3"></div>
                  <h3 class="text-xl font-semibold text-navy-900 mb-2">{{ step.title }}</h3>
                  <p class="text-navy-600">{{ step.description }}</p>
                </div>
              </div>
              <div class="mt-6 lg:mt-0 lg:py-8">
                <div class="lg:pl-8">
                  <div class="bg-navy-50 rounded-xl p-6">
                    <img :src="step.image" :alt="step.title" class="rounded-lg shadow-sm">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="py-20 bg-navy-900 text-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-2 text-sm font-semibold text-green-400 bg-green-900/20 rounded-full mb-4">
            TESTIMONIALS
          </span>
          <h2 class="text-3xl font-bold text-white sm:text-4xl">
            Trusted by Healthcare Professionals
          </h2>
        </div>

        <div class="grid md:grid-cols-2 gap-8">
          <div v-for="(testimonial, index) in testimonials" :key="index" class="bg-navy-800 p-8 rounded-xl">
            <div class="flex mb-4">
              <StarIcon v-for="i in 5" :key="i" class="h-5 w-5 text-yellow-400" />
            </div>
            <p class="italic text-navy-100 mb-6">"{{ testimonial.quote }}"</p>
            <div class="flex items-center">
              <img :src="testimonial.avatar" :alt="testimonial.name" class="h-12 w-12 rounded-full">
              <div class="ml-4">
                <h3 class="font-semibold">{{ testimonial.name }}</h3>
                <p class="text-navy-300 text-sm">{{ testimonial.title }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section class="py-20 bg-green-600 text-white">
      <div class="max-w-7xl mx-auto px-6 lg:px-8 text-center">
        <h2 class="text-3xl font-bold sm:text-4xl mb-6">
          Ready to transform your practice?
        </h2>
        <p class="text-xl text-green-100 max-w-3xl mx-auto mb-8">
          Experience the Welkesa difference with a free demo
        </p>
        <button 
          @click="navigateTo('/contact')" 
          class="px-8 py-3 rounded-lg bg-white text-navy-900 font-semibold hover:bg-navy-100 transition-colors shadow-lg"
        >
          Get Started Today
        </button>
      </div>
    </section>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router';
import {
  UserGroupIcon,
  ClockIcon,
  ShieldCheckIcon,
  DocumentTextIcon,
  VideoCameraIcon,
  ComputerDesktopIcon,
  ClipboardDocumentCheckIcon,
  StarIcon,
  ChatBubbleBottomCenterTextIcon,
  PhoneArrowUpRightIcon,
  UserPlusIcon,
  ChartBarIcon
} from '@heroicons/vue/24/outline';

const router = useRouter();


const values = [
  {
    icon: UserGroupIcon,
    title: 'Physician Scribes',
    description: 'Our scribes are physicians and medical graduates with clinical experience'
  },
  {
    icon: ClockIcon,
    title: 'Time Savings',
    description: 'Reduce documentation time by 50% or more'
  },
  {
    icon: ShieldCheckIcon,
    title: 'HIPAA Compliant',
    description: 'Enterprise-grade security for all patient data'
  }
];

const services = [
  {
    icon: VideoCameraIcon,
    title: 'Virtual Visits',
    description: 'Real-time documentation for telehealth appointments'
  },
  {
    icon: ComputerDesktopIcon,
    title: 'In-Person Scribing',
    description: 'Remote scribing for in-office visits'
  },
  {
    icon: DocumentTextIcon,
    title: 'EMR Expertise',
    description: 'Support for all major EMR systems'
  },
  {
    icon: ClipboardDocumentCheckIcon,
    title: 'Specialty Support',
    description: 'Specialty-specific documentation'
  }
];

const steps = [
  {
    title: 'Initial Consultation',
    description: 'We learn about your practice, specialty, and documentation needs',
    image: 'https://images.unsplash.com/photo-1579684453423-f84349ef60b0?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80'
  },
  {
    title: 'Workflow Integration',
    description: 'Our team integrates seamlessly with your EMR and clinical workflow',
    image: 'https://images.unsplash.com/photo-1581093450021-4a7360e9a7b3?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80'
  },
  {
    title: 'Ongoing Support',
    description: 'Dedicated account manager and continuous quality improvement',
    image: 'https://images.unsplash.com/photo-1585435557343-3b92c03c9a60?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80'
  }
];

const testimonials = [
  {
    name: 'Dr. Sarah Johnson',
    title: 'Family Medicine Physician',
    quote: 'Welkesa has cut my documentation time in half while improving note quality. Having a physician scribe makes all the difference.',
    avatar: 'https://images.unsplash.com/photo-1594824476967-48c8b964273f?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80'
  },
  {
    name: 'Dr. Michael Chen',
    title: 'Cardiologist',
    quote: 'My notes now accurately reflect clinical decision-making without constant corrections. The physician-level understanding is invaluable.',
    avatar: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&auto=format&fit=crop&w=200&h=200&q=80'
  }
];

const navigateTo = (path) => {
  router.push(path);
};
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
.text-navy-600 {
  color: #475569;
}
.text-navy-300 {
  color: #cbd5e1;
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
.bg-green-400 {
  background-color: #4ade80;
}
.text-green-400 {
  color: #4ade80;
}
.bg-green-100 {
  background-color: #dcfce7;
}
.text-green-600 {
  color: #16a34a;
}
</style>