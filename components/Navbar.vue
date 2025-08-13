<template>
  <nav class="fixed w-full bg-navy-900 z-[1000] shadow-lg transition-all duration-300 border-b border-navy-700">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-20 items-center">
        <!-- Logo with phone number -->
        <div class="flex items-center space-x-6">
          <!-- Phone number -->
          <div class="hidden md:flex items-center space-x-2">
            <svg class="w-5 h-5 text-teal-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
            </svg>
            <span class="text-teal-100 font-medium">+1 (240) 475-1441</span>
          </div>
          
          <!-- Logo with subtle glow -->
          <NuxtLink 
            to="/" 
            class="text-2xl font-bold text-white hover:text-teal-300 transition-colors duration-300 flex items-center"
          >
            <span class="mr-2 bg-clip-text text-transparent bg-gradient-to-r from-teal-300 to-blue-300">LOGO</span>
            <span class="h-6 w-6 rounded-full bg-teal-400 opacity-20 animate-pulse absolute ml-6"></span>
          </NuxtLink>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <NuxtLink 
            v-for="link in navLinks" 
            :key="link.path" 
            :to="link.path"
            class="text-teal-100 hover:text-white font-medium transition-all duration-300 relative group"
          >
            <span class="relative z-10">{{ link.name }}</span>
            <span 
              class="absolute -bottom-1 left-0 w-0 h-1 bg-gradient-to-r from-teal-400 to-blue-400 transition-all duration-300 group-hover:w-full"
              :class="{'w-full': $route.path === link.path}"
            ></span>
          </NuxtLink>
        </div>

        <!-- CTA Button with shine effect -->
        <div class="hidden md:flex items-center">
          <NuxtLink 
            to="/contact" 
            class="relative overflow-hidden px-6 py-2 rounded-md font-medium text-white bg-gradient-to-r from-teal-500 to-blue-600 hover:from-teal-600 hover:to-blue-700 transition-all duration-300 shadow-lg hover:shadow-xl group"
          >
            <span class="relative z-10">Contact us </span>
            <span class="absolute inset-0 bg-gradient-to-r from-white/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500 -rotate-12 origin-left transform translate-x-[-100%] group-hover:translate-x-[100%]"></span>
          </NuxtLink>
        </div>

        <!-- Mobile Menu Button -->
        <div class="md:hidden flex items-center">
          <button 
            @click="isOpen = !isOpen"
            class="inline-flex items-center justify-center p-2 rounded-md text-teal-100 hover:text-white focus:outline-none transition-all duration-300"
            aria-expanded="false"
          >
            <span class="sr-only">Open main menu</span>
            <svg 
              class="h-6 w-6 transform transition-all duration-300"
              :class="{'rotate-90': isOpen, 'text-white': isOpen}"
              xmlns="http://www.w3.org/2000/svg" 
              fill="none" 
              viewBox="0 0 24 24" 
              stroke="currentColor"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition
      enter-active-class="transition ease-out duration-300"
      enter-from-class="opacity-0 -translate-y-5"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition ease-in duration-200"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-5"
    >
      <div 
        v-show="isOpen"
        class="md:hidden bg-navy-800 shadow-xl rounded-b-lg overflow-hidden border-t border-navy-700"
      >
        <div class="px-2 pt-2 pb-4 space-y-2 sm:px-3">
          <!-- Mobile phone number -->
          <div class="flex items-center space-x-2 px-4 py-3">
            <svg class="w-5 h-5 text-teal-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
            </svg>
            <span class="text-teal-100 font-medium">+1 (240) 475-1441</span>
          </div>
          
          <NuxtLink
            v-for="link in navLinks"
            :key="link.path"
            :to="link.path"
            @click="isOpen = false"
            class="block px-4 py-3 rounded-lg text-base font-medium text-teal-100 hover:text-white hover:bg-navy-700/50 transition-all duration-300 flex items-center"
          >
            <span class="w-2 h-2 bg-teal-400 rounded-full mr-3" :class="{'opacity-100': $route.path === link.path, 'opacity-0': $route.path !== link.path}"></span>
            {{ link.name }}
          </NuxtLink>
          
          <div class="pt-2">
            <NuxtLink
              to="/contact"
              @click="isOpen = false"
              class="block w-full bg-gradient-to-r from-teal-500 to-blue-600 text-white px-6 py-3 rounded-lg font-medium hover:from-teal-600 hover:to-blue-700 transition-all duration-300 text-center shadow-lg"
            >
              Contact
            </NuxtLink>
          </div>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const navLinks = [
  { name: 'Home', path: '/' },
  { name: 'About', path: '/about' },
  { name: 'Services', path: '/services' },
  { name: 'Testimonials', path: '/testimonials' },
]

const isOpen = ref(false)
</script>

<style scoped>
.router-link-active {
  @apply text-white font-semibold;
}

.transition-all {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 300ms;
}

/* Custom navy color palette */
.bg-navy-900 {
  background-color: #0f172a;
}
.bg-navy-800 {
  background-color: #1e293b;
}
.border-navy-700 {
  border-color: #334155;
}
.text-teal-100 {
  color: #ccfbf1;
}
.text-teal-300 {
  color: #5eead4;
}
.text-teal-400 {
  color: #2dd4bf;
}
.bg-teal-400 {
  background-color: #2dd4bf;
}

/* Logo pulse animation */
@keyframes pulse {
  0%, 100% {
    opacity: 0.2;
    transform: scale(1);
  }
  50% {
    opacity: 0.4;
    transform: scale(1.1);
  }
}
.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}
</style>