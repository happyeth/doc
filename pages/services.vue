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
<<<<<<< HEAD
              <p class="mt-6 text-gray-600">
                We work quietly in the background—so your focus stays on the patient, not the computer.
=======
              
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
>>>>>>> 6fbbe460fa5a5ecec7702898f6b9548b43e16804
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
