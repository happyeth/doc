<template>
  <nav class="fixed w-full bg-white z-[1000] shadow-lg transition-all duration-300 border-b border-gray-100">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-20 items-center">
        <!-- Logo with pulse animation -->
        <div class="flex-shrink-0 flex items-center">
          <NuxtLink 
            to="/" 
            class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-600 to-teal-500 hover:from-blue-700 hover:to-teal-600 transition-all duration-500 flex items-center"
          >
            <span class="mr-2">doc2doc.health</span>
            <svg class="w-6 h-6 text-blue-500 animate-pulse" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path>
            </svg>
          </NuxtLink>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <NuxtLink 
            v-for="link in navLinks" 
            :key="link.path" 
            :to="link.path"
            class="text-gray-700 hover:text-blue-600 font-medium transition-all duration-300 relative group"
          >
            <span class="relative z-10">{{ link.name }}</span>
            <span 
              class="absolute -bottom-1 left-0 w-0 h-1 bg-gradient-to-r from-blue-500 to-teal-400 transition-all duration-500 group-hover:w-full"
              :class="{'w-full': $route.path === link.path}"
            ></span>
          </NuxtLink>
        </div>

        <!-- Auth Buttons -->
        <div class="hidden md:flex items-center space-x-4">
          <template v-if="!currentUser">
            <NuxtLink 
              to="/login" 
              class="bg-gradient-to-r from-blue-600 to-teal-500 text-white px-6 py-2 rounded-full font-medium hover:shadow-lg transition-all duration-300 hover:scale-[1.03] transform hover:shadow-blue-200/50"
            >
              Login
            </NuxtLink>
            <NuxtLink 
              to="/contact" 
              class="bg-white border border-blue-600 text-blue-600 px-6 py-2 rounded-full font-medium hover:shadow-lg transition-all duration-300 hover:scale-[1.03] transform hover:shadow-blue-200/50 hover:bg-blue-50"
            >
              Contact Now
            </NuxtLink>
          </template>
          <template v-else>
            <!-- User Profile Dropdown -->
            <div class="relative">
              <button 
                @click="userDropdownOpen = !userDropdownOpen"
                class="flex items-center space-x-2 focus:outline-none group"
              >
                <div class="relative">
                  <img 
                    class="h-10 w-10 rounded-full border-2 border-blue-100 group-hover:border-blue-300 transition-colors"
                    :src="currentUser.avatar"
                    :alt="currentUser.name"
                  >
                  <span class="absolute bottom-0 right-0 h-3 w-3 rounded-full bg-green-500 border-2 border-white"></span>
                </div>
                <ChevronDownIcon 
                  class="h-5 w-5 text-gray-500 group-hover:text-blue-600 transition-colors transform duration-200"
                  :class="{'rotate-180': userDropdownOpen}"
                />
              </button>

              <!-- Dropdown Menu -->
              <transition
                enter-active-class="transition ease-out duration-100"
                enter-from-class="transform opacity-0 scale-95"
                enter-to-class="transform opacity-100 scale-100"
                leave-active-class="transition ease-in duration-75"
                leave-from-class="transform opacity-100 scale-100"
                leave-to-class="transform opacity-0 scale-95"
              >
                <div 
                  v-show="userDropdownOpen"
                  class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 focus:outline-none z-50"
                  @click.away="userDropdownOpen = false"
                >
                  <div class="py-1">
                    <NuxtLink 
                      to="/dashboard" 
                      class="block px-4 py-2 text-sm text-gray-700 hover:bg-blue-50 hover:text-blue-600"
                      @click="userDropdownOpen = false"
                    >
                      Dashboard
                    </NuxtLink>
                    <button 
                      @click="logout"
                      class="block w-full text-left px-4 py-2 text-sm text-red-600 hover:bg-red-50 hover:text-red-700"
                    >
                      Sign Out
                    </button>
                  </div>
                </div>
              </transition>
            </div>
          </template>
        </div>

        <!-- Mobile Menu Button -->
        <div class="md:hidden flex items-center">
          <button 
            @click="isOpen = !isOpen"
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-700 hover:text-blue-600 focus:outline-none transition-all duration-300"
            aria-expanded="false"
          >
            <span class="sr-only">Open main menu</span>
            <svg 
              class="h-6 w-6 transform transition-all duration-300"
              :class="{'rotate-90': isOpen, 'text-blue-600': isOpen}"
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
        class="md:hidden bg-white shadow-xl rounded-b-lg overflow-hidden border-t border-gray-100"
      >
        <div class="px-2 pt-2 pb-4 space-y-2 sm:px-3">
          <NuxtLink
            v-for="link in navLinks"
            :key="link.path"
            :to="link.path"
            @click="isOpen = false"
            class="block px-4 py-3 rounded-lg text-base font-medium text-gray-700 hover:text-blue-600 hover:bg-blue-50 transition-all duration-300 flex items-center"
          >
            <span class="w-2 h-2 bg-blue-500 rounded-full mr-3" :class="{'opacity-100': $route.path === link.path, 'opacity-0': $route.path !== link.path}"></span>
            {{ link.name }}
          </NuxtLink>
          
          <div class="pt-2 space-y-2">
            <template v-if="!currentUser">
              <NuxtLink
                to="/login"
                @click="isOpen = false"
                class="block w-full bg-gradient-to-r from-blue-600 to-teal-500 text-white px-6 py-3 rounded-lg font-medium hover:shadow-lg transition-all duration-300 text-center"
              >
                Login
              </NuxtLink>
              <NuxtLink
                to="/contact"
                @click="isOpen = false"
                class="block w-full bg-white border border-blue-600 text-blue-600 px-6 py-3 rounded-lg font-medium hover:shadow-lg transition-all duration-300 text-center hover:bg-blue-50"
              >
                Contact Now
              </NuxtLink>
            </template>
            <template v-else>
              <NuxtLink
                to="/dashboard"
                @click="isOpen = false"
                class="block px-4 py-3 rounded-lg text-base font-medium text-gray-700 hover:text-blue-600 hover:bg-blue-50 transition-all duration-300 flex items-center"
              >
                <span class="w-2 h-2 bg-blue-500 rounded-full mr-3"></span>
                Dashboard
              </NuxtLink>
              <button
                @click="logout"
                class="w-full flex items-center px-4 py-3 rounded-lg text-base font-medium text-red-600 hover:bg-red-50 hover:text-red-700 transition-all duration-300"
              >
                <span class="w-2 h-2 bg-red-500 rounded-full mr-3"></span>
                Sign Out
              </button>
            </template>
          </div>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { ChevronDownIcon } from '@heroicons/vue/24/outline'

const navLinks = [
  { name: 'Home', path: '/' },
  { name: 'Pricing', path: '/pricing' },
  { name: 'Services', path: '/services' },
  { name: 'Contact', path: '/contact' }
]

const currentUser = ref(null) // Set to your user object when logged in
const isOpen = ref(false)
const userDropdownOpen = ref(false)

const logout = () => {
  currentUser.value = null
  userDropdownOpen.value = false
  isOpen.value = false
  // navigateTo('/')
}
</script>

<style scoped>
.router-link-active {
  @apply text-blue-600 font-semibold;
}

.transition-all {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}

/* Animation for the pulse effect */
@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}
</style>