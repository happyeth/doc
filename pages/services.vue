<template>
  <div class="bg-white">
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
              <span class="text-2xl font-bold">Welkesa</span>
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
                  <p class="text-lg font-medium">"Welkesa reduced my charting time from 3 hours to just 45 minutes daily"</p>
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

    <!-- About Welkesa -->
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
              At Welkesa, we provide virtual medical scribing services delivered exclusively by physicians and medical graduates. Our scribes are not just trained in documentation—they are trained in medicine.
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
              <p class="mt-6 text-gray-600">
                We work quietly in the background—so your focus stays on the patient, not the computer.
              </p>
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
        </p>
        <div class="mt-10">
          <img 
            src="https://images.unsplash.com/photo-1576091160550-2173dba999ef?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
            alt="Medical team"
            class="mx-auto rounded-xl shadow-xl w-full max-w-4xl"
          >
        </div>
      </div>
    </section>

    <!-- Who We Serve -->
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            OUR CLIENTS
          </span>
          <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
            Who We Serve
          </h2>
          <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
            We support providers across healthcare settings
          </p>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div 
            v-for="(client, index) in clients"
            :key="index"
            class="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 border border-gray-100 hover:border-blue-200"
          >
            <div class="bg-blue-100 p-3 rounded-lg w-12 h-12 flex items-center justify-center mb-4">
              <component :is="client.icon" class="h-6 w-6 text-blue-600" />
            </div>
            <h3 class="text-xl font-bold text-gray-900 mb-3">{{ client.title }}</h3>
            <p class="text-gray-600">{{ client.description }}</p>
            <ul class="mt-4 space-y-2">
              <li 
                v-for="(example, i) in client.examples"
                :key="i"
                class="flex items-start text-sm text-gray-600"
              >
                <CheckCircleIcon class="h-4 w-4 text-blue-500 mr-2 mt-0.5 flex-shrink-0" />
                <span>{{ example }}</span>
              </li>
            </ul>
          </div>
        </div>

        <div class="mt-16 text-center">
          <p class="text-lg text-gray-600 max-w-3xl mx-auto">
            No matter your setting—we're your virtual clinical partner.
          </p>
        </div>
      </div>
    </section>

    <!-- Final CTA -->
    <section class="py-20 bg-blue-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
          Ready to Work Smarter?
        </h2>
        <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
          Contact us today or schedule a free demo to learn how physician-level virtual scribing can transform your practice.
        </p>
        <div class="mt-10 flex flex-wrap justify-center gap-4">
          <button 
            @click="navigateTo('/contact')" 
            class="px-8 py-4 border border-transparent text-base font-medium rounded-full text-white bg-gradient-to-r from-blue-600 to-teal-500 hover:from-blue-700 hover:to-teal-600 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
          >
            Contact Us
          </button>
          <button 
            @click="navigateTo('/demo')" 
            class="px-8 py-4 border-2 border-blue-500 text-base font-medium rounded-full text-blue-600 bg-white hover:bg-blue-50 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
          >
            Schedule Demo
          </button>
        </div>
      </div>
    </section>

    <!-- Service Modal -->
    <TransitionRoot as="template" :show="serviceModalOpen">
      <Dialog as="div" class="relative z-50" @close="serviceModalOpen = false">
        <TransitionChild
          as="template"
          enter="ease-out duration-300"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="ease-in duration-200"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" />
        </TransitionChild>

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
                    <component :is="selectedService.icon" class="h-6 w-6 text-blue-600" />
                  </div>
                  <div class="mt-3 text-center sm:mt-5">
                    <DialogTitle as="h3" class="text-base font-semibold leading-6 text-gray-900">
                      {{ selectedService.title }}
                    </DialogTitle>
                    <div class="mt-2">
                      <p class="text-sm text-gray-500">
                        {{ selectedService.description }}
                      </p>
                    </div>
                  </div>
                </div>
                <div class="mt-6">
                  <h4 class="text-sm font-medium text-gray-900">Features:</h4>
                  <ul class="mt-2 space-y-2">
                    <li 
                      v-for="(feature, index) in selectedService.features"
                      :key="index"
                      class="flex items-start text-sm text-gray-600"
                    >
                      <CheckCircleIcon class="h-5 w-5 text-blue-500 mr-2 mt-0.5 flex-shrink-0" />
                      <span>{{ feature }}</span>
                    </li>
                  </ul>
                </div>
                <div class="mt-5 sm:mt-6 sm:grid sm:grid-flow-row-dense sm:grid-cols-2 sm:gap-3">
                  <button
                    type="button"
                    class="inline-flex w-full justify-center rounded-md bg-blue-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-blue-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600 sm:col-start-2"
                    @click="navigateTo('/contact')"
                  >
                    Contact Us
                  </button>
                  <button
                    type="button"
                    class="mt-3 inline-flex w-full justify-center rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50 sm:col-start-1 sm:mt-0"
                    @click="serviceModalOpen = false"
                    ref="cancelButtonRef"
                  >
                    Close
                  </button>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>

    <!-- Video Modal -->
    <TransitionRoot as="template" :show="videoModalOpen">
      <Dialog as="div" class="relative z-50" @close="videoModalOpen = false">
        <TransitionChild
          as="template"
          enter="ease-out duration-300"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="ease-in duration-200"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" />
        </TransitionChild>

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
                      Welkesa Service Demo
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
          </div>
        </div>
      </Dialog>
    </TransitionRoot>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {
  Dialog,
  DialogPanel,
  DialogTitle,
  TransitionChild,
  TransitionRoot,
} from '@headlessui/vue'
import {
  DocumentTextIcon,
  InboxIcon,
  ClipboardDocumentIcon as ClipboardListIcon,
  UserGroupIcon,
  CogIcon,
  ShieldCheckIcon,
  ClockIcon,
  PlayCircleIcon,
  ArrowRightIcon,
  CheckCircleIcon,
  StarIcon,
  BuildingOfficeIcon,
  UserIcon,
  ComputerDesktopIcon,
  HomeModernIcon
} from '@heroicons/vue/24/outline'

const serviceModalOpen = ref(false)
const videoModalOpen = ref(false)
const selectedService = ref({})

const services = ref([
  {
    title: 'Real-Time Charting',
    description: 'Accurate documentation during virtual or in-person visits',
    icon: DocumentTextIcon,
    features: [
      'Real-time note taking during patient encounters',
      'Remote access to your EMR system',
      'Specialty-specific templates',
      'SOAP, H&P, and procedure notes',
      'Customizable to your preferences'
    ]
  },
  {
    title: 'EMR Support',
    description: 'Seamless integration with all major EMR systems',
    icon: ComputerDesktopIcon,
    features: [
      'Epic, Cerner, Meditech, and more',
      'Custom workflow configuration',
      'Template optimization for your EMR',
      'Quick note access and submission',
      'Secure remote access'
    ]
  },
  {
    title: 'Specialty Documentation',
    description: 'Clinical insight tailored to your specialty',
    icon: UserGroupIcon,
    features: [
      'Physician scribes matched to your specialty',
      'Specialty-specific terminology',
      'Procedure-specific templates',
      'Diagnosis code optimization',
      'Clinical decision support'
    ]
  },
  {
    title: 'HIPAA Compliance',
    description: 'Enterprise-grade security for patient data',
    icon: ShieldCheckIcon,
    features: [
      'End-to-end encryption',
      'Business Associate Agreement',
      'Audit logging',
      'Two-factor authentication',
      'Regular security audits'
    ]
  }
])

const differentiators = ref([
  'Advanced clinical understanding',
  'Higher accuracy and efficiency',
  'Fewer clarifications needed',
  'Seamless collaboration with providers',
  'Reduced after-hours documentation'
])

const clients = ref([
  {
    title: 'Telemedicine Practices',
    description: 'Support for virtual care providers',
    icon: ComputerDesktopIcon,
    examples: [
      'Real-time virtual scribing',
      'Platform integration',
      'Visit documentation',
      'Remote patient monitoring'
    ]
  },
  {
    title: 'Outpatient Clinics',
    description: 'Comprehensive clinic support',
    icon: BuildingOfficeIcon,
    examples: [
      'High-volume documentation',
      'Procedure note support',
      'Referral management',
      'Quality measure tracking'
    ]
  },
  {
    title: 'Primary Care',
    description: 'Full-spectrum primary care support',
    icon: UserIcon,
    examples: [
      'Preventive care documentation',
      'Chronic disease management',
      'Medication reconciliation',
      'Care coordination'
    ]
  },
  {
    title: 'Specialists',
    description: 'Specialty-specific documentation',
    icon: HomeModernIcon,
    examples: [
      'Specialty templates',
      'Procedure documentation',
      'Consult notes',
      'Diagnosis-specific coding'
    ]
  }
])

const openServiceModal = (index) => {
  selectedService.value = services.value[index]
  serviceModalOpen.value = true
}

const openVideoModal = () => {
  videoModalOpen.value = true
}

const navigateTo = (path) => {
  // Router navigation logic here
  console.log(`Navigating to: ${path}`)
}
</script>

<style>
/* Custom animations */
@keyframes float {
  0% {
    transform: translateY(0px) translateX(0px);
  }
  50% {
    transform: translateY(-20px) translateX(10px);
  }
  100% {
    transform: translateY(0px) translateX(0px);
  }
}

/* Smooth transitions */
.transition-slow {
  transition: all 0.5s ease;
}
</style>