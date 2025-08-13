<template>
  <div class="bg-white">
<<<<<<< HEAD
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
=======
    <!-- Hero Section with Physician Background -->
    <section class="relative bg-gradient-to-br from-blue-900 to-indigo-900 overflow-hidden">
      <!-- Animated background elements -->
      <div class="absolute inset-0 z-0 opacity-30">
        <div class="absolute top-0 left-0 w-full h-full bg-[url('https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-1.2.1&auto=format&fit=crop&w=1800&q=80')] bg-cover bg-center"></div>
        <div class="absolute inset-0 bg-gradient-to-r from-blue-900/90 to-indigo-900/80"></div>
      </div>

      <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24 lg:py-32 z-10">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          <div class="text-white">
            <div class="flex items-center mb-6">
              <span class="text-2xl font-bold">doc2doc.health</span>
              <span class="ml-3 px-3 py-1 rounded-full bg-blue-100 text-blue-800 text-xs font-medium">Physician-Led</span>
            </div>
            <h1 class="text-4xl font-extrabold tracking-tight sm:text-5xl lg:text-6xl">
              <span class="block">Physician-Powered</span>
              <span class="block">Clinical Documentation</span>
            </h1>
            <p class="mt-6 text-xl text-blue-100 max-w-lg">
              Reduce documentation time by 50% with our physician-led virtual scribing service. 
              Focus on patients while we handle your charts with clinical precision.
            </p>
            <div class="mt-10 flex flex-wrap gap-4">
              <button 
                @click="navigateTo('/contact')" 
                class="px-8 py-4 border border-transparent text-base font-medium rounded-full text-blue-900 bg-gradient-to-r from-teal-300 to-blue-300 hover:from-teal-400 hover:to-blue-400 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
              >
                Start Free Trial
              </button>
              <button 
                @click="openVideoModal"
                class="px-8 py-4 border-2 border-blue-300 text-base font-medium rounded-full text-white bg-transparent hover:bg-blue-800/30 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300 flex items-center"
              >
                <PlayCircleIcon class="h-5 w-5 mr-2" />
                Watch Demo
              </button>
            </div>
          </div>
          <div class="relative">
            <div class="relative rounded-2xl overflow-hidden shadow-2xl transform rotate-1 hover:rotate-0 transition-transform duration-500 group">
              <img 
                src="https://images.unsplash.com/photo-1579684385127-1ef15d508118?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
                alt="Doctor consulting with patient"
                class="w-full h-auto group-hover:scale-105 transition-transform duration-500"
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
                  <ClockIcon class="h-8 w-8 text-blue-600" />
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

    <!-- About doc2doc.health -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
          <div class="mb-12 lg:mb-0">
            <img 
              src="https://images.unsplash.com/photo-1581056771107-24ca5f033842?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
              alt="Medical team collaborating"
              class="rounded-xl shadow-lg w-full h-auto"
            >
          </div>
          <div>
            <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
              OUR STORY
            </span>
            <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
              By Doctors, For Doctors
            </h2>
            <p class="mt-4 text-lg text-gray-600">
              At doc2doc.health, we provide virtual medical scribing services delivered exclusively by physicians and medical graduates. Our scribes are not just trained in documentation—they are trained in medicine.
            </p>
            <p class="mt-4 text-lg text-gray-600">
              With clinical experience and deep understanding of patient care, we bring unmatched accuracy, efficiency, and trust to every chart.
            </p>
            <p class="mt-4 text-lg text-gray-600">
              Our journey began when a group of physicians, overwhelmed by charting demands, realized that real solutions require real clinical knowledge. That's why we built a service by doctors, for doctors—freeing healthcare providers from the burden of documentation, so they can return their focus to where it belongs: the patient and have ample amount of time with their beloved ones as well.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- What We Do Section -->
    <section class="py-20 bg-blue-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            OUR SERVICES
          </span>
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            What We Do
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            We offer real-time virtual scribing, tailored to your workflow and specialty
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div 
            v-for="(service, index) in services"
            :key="index"
            class="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-blue-200 cursor-pointer"
            @click="openServiceModal(index)"
          >
            <div class="bg-blue-100 p-3 rounded-lg w-12 h-12 flex items-center justify-center mb-4">
              <component :is="service.icon" class="h-6 w-6 text-blue-600" />
            </div>
            <h3 class="text-xl font-bold text-gray-900 mb-3">{{ service.title }}</h3>
            <p class="text-gray-600">{{ service.description }}</p>
            <ul class="mt-4 space-y-2">
              <li 
                v-for="(feature, i) in service.features.slice(0, 2)"
                :key="i"
                class="flex items-start text-sm text-gray-600"
              >
                <CheckCircleIcon class="h-4 w-4 text-blue-500 mr-2 mt-0.5 flex-shrink-0" />
                <span>{{ feature }}</span>
              </li>
            </ul>
            <div class="mt-6 text-blue-600 font-medium flex items-center">
              Learn more <ArrowRightIcon class="h-4 w-4 ml-2" />
            </div>
          </div>
        </div>

        <div class="mt-16 bg-white rounded-xl shadow-lg overflow-hidden border border-gray-200">
          <div class="grid md:grid-cols-2">
            <div class="p-8 md:p-12">
              <h3 class="text-2xl font-bold text-gray-900 mb-4">Our Services Include:</h3>
              <ul class="space-y-4">
                <li class="flex items-start">
                  <CheckCircleIcon class="h-6 w-6 text-blue-500 mr-3 mt-0.5 flex-shrink-0" />
                  <span class="text-gray-700">Accurate, real-time charting during virtual or in-person visits (via remote access)</span>
                </li>
                <li class="flex items-start">
                  <CheckCircleIcon class="h-6 w-6 text-blue-500 mr-3 mt-0.5 flex-shrink-0" />
                  <span class="text-gray-700">Support for all major EMR systems</span>
                </li>
                <li class="flex items-start">
                  <CheckCircleIcon class="h-6 w-6 text-blue-500 mr-3 mt-0.5 flex-shrink-0" />
                  <span class="text-gray-700">Specialty-specific documentation with clinical insight</span>
                </li>
                <li class="flex items-start">
                  <CheckCircleIcon class="h-6 w-6 text-blue-500 mr-3 mt-0.5 flex-shrink-0" />
                  <span class="text-gray-700">HIPAA-compliant, secure, and confidential service</span>
                </li>
              </ul>
            </div>
            <div class="bg-blue-50 p-8 md:p-12 flex items-center justify-center">
              <img 
                src="https://images.unsplash.com/photo-1581595219315-a187dd40c322?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
                alt="Doctor using EMR system"
                class="rounded-lg shadow-md w-full h-auto"
              >
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Why We're Different -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
          <div class="mb-12 lg:mb-0">
            <div class="relative rounded-xl overflow-hidden shadow-lg">
              <img 
                src="https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
                alt="Physician reviewing charts"
                class="w-full h-auto"
              >
              <div class="absolute inset-0 bg-gradient-to-t from-blue-900/70 via-transparent to-transparent flex items-end p-8">
                <div class="text-white">
                  <p class="text-lg font-medium">"Our scribes are physicians, not just note-takers. That makes all the difference."</p>
                </div>
              </div>
            </div>
          </div>
          <div>
            <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
              OUR DIFFERENCE
            </span>
            <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
              Why We're Different
            </h2>
            <p class="mt-4 text-lg text-gray-600">
              Our scribes are physicians, not just note-takers. That makes all the difference.
            </p>
            
            <div class="mt-8 space-y-6">
              <div 
                v-for="(item, index) in differentiators"
                :key="index"
                class="flex items-start p-4 rounded-lg hover:bg-blue-50 transition-all duration-300"
              >
                <div class="flex-shrink-0 bg-blue-100 p-2 rounded-full">
                  <CheckCircleIcon class="h-5 w-5 text-blue-600" />
                </div>
                <div class="ml-4">
                  <h3 class="text-lg font-medium text-gray-900">{{ item }}</h3>
                </div>
              </div>
            </div>

            <p class="mt-8 text-lg text-gray-600">
              We elevate scribing into a clinical partnership—because we've walked in your shoes.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Our Mission -->
    <section class="py-20 bg-gradient-to-r from-blue-900 to-indigo-900">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-200 bg-blue-800/50 rounded-full mb-4">
          OUR MISSION
        </span>
        <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
          To improve the lives of healthcare providers
        </h2>
        <p class="mt-6 max-w-3xl mx-auto text-xl text-blue-200">
          By removing the burden of documentation, enhancing the quality of clinical records, and restoring time and energy for patient care—all through high-level, physician-powered virtual support.
>>>>>>> 2e6393cf27cbcb5162d7a2d90250b8982a1ef405
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

<<<<<<< HEAD
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div v-for="(service, index) in services" :key="index" class="bg-white p-8 rounded-xl shadow-sm hover:shadow-md transition-shadow">
            <div class="h-12 w-12 bg-green-100 rounded-lg flex items-center justify-center mb-4">
              <component :is="service.icon" class="h-6 w-6 text-green-600" />
            </div>
            <h3 class="text-lg font-semibold text-navy-900 mb-2">{{ service.title }}</h3>
            <p class="text-navy-600 text-sm">{{ service.description }}</p>
=======
        <div class="fixed inset-0 z-10 w-screen overflow-y-auto">
          <div class="flex min-h-full items-end justify-center p-4 text-center sm:items-center sm:p-0">
            <TransitionChild
              as="template"
              enter="ease-out duration-300"
              enter-from="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
              enter-to="opacity-100 translate-y-0 sm:scale-100"
              leave="ease-in duration-200"
              leave-from="opacity-100 translate-y-0 sm:scale-100"
              leave-to="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
            >
              <DialogPanel class="relative transform overflow-hidden rounded-lg bg-white px-4 pb-4 pt-5 text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-3xl sm:p-6">
                <div>
                  <div class="mx-auto flex h-12 w-12 items-center justify-center rounded-full bg-blue-100">
                    <PlayCircleIcon class="h-6 w-6 text-blue-600" />
                  </div>
                  <div class="mt-3 text-center sm:mt-5">
                    <DialogTitle as="h3" class="text-base font-semibold leading-6 text-gray-900">
                      doc2doc.health Service Demo
                    </DialogTitle>
                  </div>
                </div>
                <div class="mt-6 aspect-w-16 aspect-h-9">
                  <iframe 
                    class="w-full h-96 rounded-lg"
                    src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
                    title="YouTube video player" 
                    frameborder="0" 
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                    allowfullscreen
                  ></iframe>
                </div>
                <div class="mt-5 sm:mt-6 sm:grid sm:grid-flow-row-dense sm:grid-cols-2 sm:gap-3">
                  <button
                    type="button"
                    class="inline-flex w-full justify-center rounded-md bg-blue-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-blue-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600 sm:col-start-2"
                    @click="navigateTo('/demo')"
                  >
                    Schedule Live Demo
                  </button>
                  <button
                    type="button"
                    class="mt-3 inline-flex w-full justify-center rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50 sm:col-start-1 sm:mt-0"
                    @click="videoModalOpen = false"
                    ref="cancelButtonRef"
                  >
                    Close
                  </button>
                </div>
              </DialogPanel>
            </TransitionChild>
>>>>>>> 2e6393cf27cbcb5162d7a2d90250b8982a1ef405
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
<<<<<<< HEAD
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
=======
    title: 'Outpatient Clinics',
    description: 'Comprehensive clinic support',
    icon: BuildingOfficeIcon,
    examples: [
      'High-volume documentation',
      'Procedure note support',
]}])
>>>>>>> 2e6393cf27cbcb5162d7a2d90250b8982a1ef405
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