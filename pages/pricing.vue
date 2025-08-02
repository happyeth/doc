<template>
  <section class="py-20 bg-blue-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header -->
      <div class="text-center mb-16">
        <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
          PRICING PLANS
        </span>
        <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
          Physician-Focused Pricing
        </h2>
        <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
          Designed by doctors to maximize your time and revenue
        </p>
        
        <!-- Pricing Toggle -->
        <div class="mt-8 flex justify-center">
          <div class="bg-white p-1 rounded-lg shadow-sm flex">
            <button
              @click="billingCycle = 'monthly'"
              :class="{
                'bg-gradient-to-r from-blue-500 to-teal-400 text-white': billingCycle === 'monthly',
                'text-gray-700 hover:text-blue-600': billingCycle !== 'monthly'
              }"
              class="px-6 py-2 text-sm font-medium rounded-md transition-colors duration-300"
            >
              Monthly Billing
            </button>
            <button
              @click="billingCycle = 'annual'"
              :class="{
                'bg-gradient-to-r from-blue-500 to-teal-400 text-white': billingCycle === 'annual',
                'text-gray-700 hover:text-blue-600': billingCycle !== 'annual'
              }"
              class="px-6 py-2 text-sm font-medium rounded-md transition-colors duration-300"
            >
              Annual Billing
            </button>
          </div>
        </div>
        <p v-if="showAnnualSavings" class="mt-3 text-sm text-blue-600 font-medium">
          Save 15% with annual billing
        </p>
      </div>

      <!-- Pricing Cards -->
      <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        <!-- Resident Plan -->
        <div class="relative bg-white rounded-2xl shadow-lg overflow-hidden border border-gray-200 hover:border-blue-300 transition-all duration-300 transform hover:-translate-y-2">
          <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-blue-100 to-teal-100"></div>
          <div class="p-8">
            <div class="flex items-center mb-4">
              <div class="bg-blue-100 p-2 rounded-lg">
                <UserIcon class="h-6 w-6 text-blue-600" />
              </div>
              <h3 class="ml-3 text-xl font-bold text-gray-900">Resident</h3>
            </div>
            <p class="text-gray-600">For residents and fellows starting out</p>
            <div class="mt-8">
              <div class="flex items-baseline">
                <span class="text-4xl font-extrabold text-gray-900">${{ pricing.resident[billingCycle].price }}</span>
                <span class="ml-1 text-lg font-medium text-gray-500">/{{ billingCycle }}</span>
              </div>
              <p v-if="billingCycle === 'annual'" class="mt-1 text-sm text-gray-500">
                ${{ (pricing.resident[billingCycle].price / 12).toFixed(0) }} per month
              </p>
            </div>
            <ul class="mt-8 space-y-3">
              <li v-for="(feature, index) in pricing.resident.features" :key="index" class="flex">
                <CheckCircleIcon class="h-5 w-5 text-blue-500 flex-shrink-0" />
                <span class="ml-3 text-gray-600">{{ feature }}</span>
              </li>
            </ul>
          </div>
          <div class="px-8 pb-8">
            <button 
              @click="navigateTo('/signup?plan=resident')"
              class="w-full px-4 py-3 border border-transparent text-base font-medium rounded-full text-white bg-gradient-to-r from-blue-500 to-blue-600 hover:from-blue-600 hover:to-blue-700 shadow-lg hover:shadow-xl transition-all duration-300"
            >
              Get Started
            </button>
          </div>
          <div class="absolute top-0 right-0 bg-blue-500 text-white text-xs font-semibold px-3 py-1 rounded-bl-lg">
            Resident Discount
          </div>
        </div>

        <!-- Attending Plan (Popular) -->
        <div class="relative bg-white rounded-2xl shadow-xl overflow-hidden border-2 border-blue-500 transform hover:-translate-y-2 transition-all duration-300 z-10">
          <div class="absolute top-0 left-0 right-0 h-2 bg-gradient-to-r from-blue-500 to-teal-500"></div>
          <div class="p-8">
            <div class="flex justify-between items-start">
              <div class="flex items-center">
                <div class="bg-blue-100 p-2 rounded-lg">
                  <UserGroupIcon class="h-6 w-6 text-blue-600" />
                </div>
                <h3 class="ml-3 text-xl font-bold text-gray-900">Attending</h3>
              </div>
              <span class="inline-flex items-center px-3 py-1 rounded-full text-xs font-medium bg-blue-100 text-blue-800">
                Most Popular
              </span>
            </div>
            <p class="mt-2 text-gray-600">For practicing physicians with full patient loads</p>
            <div class="mt-8">
              <div class="flex items-baseline">
                <span class="text-4xl font-extrabold text-gray-900">${{ pricing.attending[billingCycle].price }}</span>
                <span class="ml-1 text-lg font-medium text-gray-500">/{{ billingCycle }}</span>
              </div>
              <p v-if="billingCycle === 'annual'" class="mt-1 text-sm text-gray-500">
                ${{ (pricing.attending[billingCycle].price / 12).toFixed(0) }} per month
              </p>
            </div>
            <ul class="mt-8 space-y-3">
              <li v-for="(feature, index) in pricing.attending.features" :key="index" class="flex">
                <CheckCircleIcon class="h-5 w-5 text-blue-500 flex-shrink-0" />
                <span class="ml-3 text-gray-600">{{ feature }}</span>
              </li>
            </ul>
          </div>
          <div class="px-8 pb-8">
            <button 
              @click="navigateTo('/signup?plan=attending')"
              class="w-full px-4 py-3 border border-transparent text-base font-medium rounded-full text-white bg-gradient-to-r from-blue-600 to-teal-500 hover:from-blue-700 hover:to-teal-600 shadow-lg hover:shadow-xl transition-all duration-300"
            >
              Start Free Trial
            </button>
          </div>
          <div class="absolute -top-3 right-4 bg-gradient-to-r from-blue-600 to-teal-500 text-white text-xs font-semibold px-3 py-1 rounded-lg shadow-md">
            Save {{ billingCycle === 'annual' ? '15%' : '10%' }}
          </div>
        </div>

        <!-- Group Practice Plan -->
        <div class="relative bg-white rounded-2xl shadow-lg overflow-hidden border border-gray-200 hover:border-blue-300 transition-all duration-300 transform hover:-translate-y-2">
          <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-blue-100 to-teal-100"></div>
          <div class="p-8">
            <div class="flex items-center mb-4">
              <div class="bg-blue-100 p-2 rounded-lg">
                <BuildingLibraryIcon class="h-6 w-6 text-blue-600" />
              </div>
              <h3 class="ml-3 text-xl font-bold text-gray-900">Group Practice</h3>
            </div>
            <p class="text-gray-600">For clinics and multi-provider practices</p>
            <div class="mt-8">
              <div class="flex items-baseline">
                <span class="text-4xl font-extrabold text-gray-900">${{ pricing.group[billingCycle].price }}</span>
                <span class="ml-1 text-lg font-medium text-gray-500">/{{ billingCycle }}</span>
              </div>
              <p v-if="billingCycle === 'annual'" class="mt-1 text-sm text-gray-500">
                ${{ (pricing.group[billingCycle].price / 12).toFixed(0) }} per month
              </p>
            </div>
            <ul class="mt-8 space-y-3">
              <li v-for="(feature, index) in pricing.group.features" :key="index" class="flex">
                <CheckCircleIcon class="h-5 w-5 text-blue-500 flex-shrink-0" />
                <span class="ml-3 text-gray-600">{{ feature }}</span>
              </li>
            </ul>
          </div>
          <div class="px-8 pb-8">
            <button 
              @click="navigateTo('/contact')"
              class="w-full px-4 py-3 border border-transparent text-base font-medium rounded-full text-blue-700 bg-blue-100 hover:bg-blue-200 shadow-lg hover:shadow-xl transition-all duration-300"
            >
              Contact Sales
            </button>
          </div>
          <div class="absolute top-0 right-0 bg-teal-500 text-white text-xs font-semibold px-3 py-1 rounded-bl-lg">
            Custom Solutions
          </div>
        </div>
      </div>

      <!-- Value Proposition -->
      <div class="mt-20 bg-gradient-to-r from-blue-900 to-indigo-900 rounded-2xl shadow-xl overflow-hidden">
        <div class="grid md:grid-cols-2">
          <div class="p-12 text-white">
            <h3 class="text-2xl font-bold mb-4">The doc2doc.health Advantage</h3>
            <p class="text-blue-200 mb-6">
              Our physician-led scribing service delivers more than just documentation - we provide clinical partnership that enhances your practice.
            </p>
            <ul class="space-y-4">
              <li class="flex items-start">
                <div class="flex-shrink-0 bg-blue-700 p-1 rounded-full">
                  <CheckCircleIcon class="h-5 w-5 text-blue-300" />
                </div>
                <span class="ml-3">Physician-trained scribes with clinical knowledge</span>
              </li>
              <li class="flex items-start">
                <div class="flex-shrink-0 bg-blue-700 p-1 rounded-full">
                  <CheckCircleIcon class="h-5 w-5 text-blue-300" />
                </div>
                <span class="ml-3">Specialty-specific documentation expertise</span>
              </li>
              <li class="flex items-start">
                <div class="flex-shrink-0 bg-blue-700 p-1 rounded-full">
                  <CheckCircleIcon class="h-5 w-5 text-blue-300" />
                </div>
                <span class="ml-3">HIPAA-compliant with military-grade security</span>
              </li>
              <li class="flex items-start">
                <div class="flex-shrink-0 bg-blue-700 p-1 rounded-full">
                  <CheckCircleIcon class="h-5 w-5 text-blue-300" />
                </div>
                <span class="ml-3">Average 2.5 hours saved daily per provider</span>
              </li>
            </ul>
          </div>
          <div class="hidden md:block relative">
            <img 
              src="https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80" 
              alt="Doctor reviewing charts" 
              class="w-full h-full object-cover"
            >
            <div class="absolute inset-0 bg-gradient-to-t from-blue-900/70 via-blue-900/20 to-transparent flex items-end p-8">
              <div class="text-white">
                <p class="text-lg font-medium">"doc2doc.health helped me see 4 more patients per day while reducing my burnout."</p>
                <p class="mt-2 text-blue-200">— Dr. Michael Chen, Internal Medicine</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Comparison Table -->
      <div class="mt-20 max-w-5xl mx-auto bg-white shadow-lg rounded-2xl overflow-hidden border border-gray-200">
        <div class="px-8 py-6 bg-gray-50 border-b border-gray-200">
          <h3 class="text-xl font-bold text-gray-900">Plan Comparison</h3>
          <p class="mt-1 text-gray-600">See how our plans match your practice needs</p>
        </div>
        <div class="divide-y divide-gray-200">
          <div v-for="(row, index) in comparisonTable" :key="index" class="grid grid-cols-4 gap-6 p-6 items-center">
            <div class="font-medium text-gray-900">{{ row.feature }}</div>
            <div class="text-center">
              <template v-if="row.resident === true">
                <CheckCircleIcon class="h-6 w-6 text-blue-500 mx-auto" />
              </template>
              <template v-else-if="row.resident === false">
                <XCircleIcon class="h-6 w-6 text-gray-300 mx-auto" />
              </template>
              <template v-else>
                <span class="text-gray-700">{{ row.resident }}</span>
              </template>
            </div>
            <div class="text-center">
              <template v-if="row.attending === true">
                <CheckCircleIcon class="h-6 w-6 text-blue-500 mx-auto" />
              </template>
              <template v-else-if="row.attending === false">
                <XCircleIcon class="h-6 w-6 text-gray-300 mx-auto" />
              </template>
              <template v-else>
                <span class="text-gray-700">{{ row.attending }}</span>
              </template>
            </div>
            <div class="text-center">
              <template v-if="row.group === true">
                <CheckCircleIcon class="h-6 w-6 text-blue-500 mx-auto" />
              </template>
              <template v-else-if="row.group === false">
                <XCircleIcon class="h-6 w-6 text-gray-300 mx-auto" />
              </template>
              <template v-else>
                <span class="text-gray-700">{{ row.group }}</span>
              </template>
            </div>
          </div>
        </div>
      </div>

      <!-- ROI Calculator -->
      <div class="mt-20 bg-white rounded-2xl shadow-lg overflow-hidden border border-gray-200">
        <div class="grid md:grid-cols-2">
          <div class="p-8 md:p-12">
            <h3 class="text-2xl font-bold text-gray-900 mb-4">Calculate Your Potential Savings</h3>
            <p class="text-gray-600 mb-6">
              See how much time and revenue you could gain with doc2doc.health
            </p>
            <div class="space-y-4">
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">Patients per day</label>
                <input 
                  v-model="calculator.patients" 
                  type="range" 
                  min="10" 
                  max="50" 
                  step="5"
                  class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer"
                >
                <div class="flex justify-between text-xs text-gray-500 mt-1">
                  <span>10</span>
                  <span>50+</span>
                </div>
                <div class="text-center font-medium text-blue-600 mt-1">{{ calculator.patients }} patients</div>
              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">Current charting time (hrs/day)</label>
                <input 
                  v-model="calculator.hours" 
                  type="range" 
                  min="1" 
                  max="5" 
                  step="0.5"
                  class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer"
                >
                <div class="flex justify-between text-xs text-gray-500 mt-1">
                  <span>1</span>
                  <span>5+</span>
                </div>
                <div class="text-center font-medium text-blue-600 mt-1">{{ calculator.hours }} hours</div>
              </div>
            </div>
            <div class="mt-8 p-4 bg-blue-50 rounded-lg border border-blue-100">
              <div class="text-sm text-gray-700 mb-2">Estimated with doc2doc.health:</div>
              <div class="flex justify-between items-center">
                <div>
                  <div class="text-xs text-gray-500">Time Saved</div>
                  <div class="text-lg font-bold text-blue-600">{{ calculatedSavings.hoursSaved }} hrs/day</div>
                </div>
                <div>
                  <div class="text-xs text-gray-500">Revenue Potential*</div>
                  <div class="text-lg font-bold text-blue-600">${{ calculatedSavings.revenue }}/day</div>
                </div>
              </div>
              <div class="mt-2 text-xs text-gray-500">*Based on seeing 2 additional patients at $150/visit</div>
            </div>
          </div>
          <div class="bg-blue-50 p-8 md:p-12 flex items-center justify-center">
            <div class="text-center">
              <div class="mx-auto h-24 w-24 bg-blue-100 rounded-full flex items-center justify-center mb-4">
                <ClockIcon class="h-12 w-12 text-blue-600" />
              </div>
              <h3 class="text-xl font-bold text-gray-900 mb-2">Time is Money</h3>
              <p class="text-gray-600 mb-4">
                Our physicians save an average of 2.5 hours daily on documentation
              </p>
              <button 
                @click="navigateTo('/demo')"
                class="px-6 py-3 border border-transparent text-base font-medium rounded-full text-white bg-gradient-to-r from-blue-600 to-teal-500 hover:from-blue-700 hover:to-teal-600 shadow-lg hover:shadow-xl transition-all duration-300"
              >
                Schedule Demo
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- FAQ Section -->
      <div class="mt-20 max-w-3xl mx-auto">
        <div class="text-center mb-12">
          <span class="inline-block px-4 py-1 text-sm font-semibold text-blue-600 bg-blue-100 rounded-full mb-4">
            HAVE QUESTIONS?
          </span>
          <h3 class="text-2xl font-bold text-gray-900">Frequently Asked Questions</h3>
        </div>
        <div class="space-y-4">
          <div 
            v-for="(faq, index) in faqs" 
            :key="index" 
            class="bg-white border border-gray-200 rounded-xl overflow-hidden hover:shadow-md transition-shadow duration-300"
          >
            <button 
              @click="toggleFAQ(index)"
              class="w-full px-6 py-4 text-left focus:outline-none flex justify-between items-center"
            >
              <span class="font-medium text-gray-900">{{ faq.question }}</span>
              <ChevronDownIcon 
                class="h-5 w-5 text-gray-500 transition-transform duration-200"
                :class="{ 'transform rotate-180': faq.open }"
              />
            </button>
            <div 
              v-show="faq.open" 
              class="px-6 pb-4 text-gray-600 transition-all duration-300"
            >
              {{ faq.answer }}
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom CTA -->
      <div class="mt-20 text-center bg-gradient-to-r from-blue-600 to-indigo-700 rounded-2xl p-12 text-white">
        <h3 class="text-2xl font-bold mb-4">Ready to transform your documentation workflow?</h3>
        <p class="text-xl text-blue-100 max-w-2xl mx-auto mb-8">
          Join hundreds of physicians who trust doc2doc.health with their clinical documentation
        </p>
        <div class="flex flex-wrap justify-center gap-4">
          <button 
            @click="navigateTo('/signup')"
            class="px-8 py-4 border border-transparent text-base font-medium rounded-full text-blue-600 bg-white hover:bg-gray-100 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
          >
            Start Free Trial
          </button>
          <button 
            @click="navigateTo('/contact')"
            class="px-8 py-4 border-2 border-white text-base font-medium rounded-full text-white hover:bg-blue-700/30 shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300"
          >
            Contact Our Team
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'
import { 
  CheckCircleIcon, 
  XCircleIcon, 
  ChevronDownIcon,
  UserIcon,
  UserGroupIcon,
  BuildingLibraryIcon,
  ClockIcon
} from '@heroicons/vue/24/outline'

const billingCycle = ref('monthly') // 'monthly' or 'annual'

const showAnnualSavings = computed(() => billingCycle.value === 'annual')

const pricing = {
  resident: {
    monthly: { price: 199 },
    annual: { price: 1999 },
    features: [
      'Up to 30 notes/month',
      'Physician-assisted documentation',
      'Basic inbox management',
      'Email support',
      '24-48 hour turnaround',
      'Resident/Fellow discount'
    ]
  },
  attending: {
    monthly: { price: 499 },
    annual: { price: 4999 },
    features: [
      'Up to 120 notes/month',
      'Priority physician documentation',
      'Full inbox & lab tracking',
      'Chart preparation',
      'Phone & email support',
      '12-24 hour turnaround',
      'Dedicated MD scribe',
      'Specialty-matched support'
    ]
  },
  group: {
    monthly: { price: 'Custom' },
    annual: { price: 'Custom' },
    features: [
      'Unlimited notes',
      'Multiple provider support',
      'Custom workflows',
      '24/7 priority support',
      'Same-day turnaround',
      'Dedicated account manager',
      'EMR integration',
      'Analytics dashboard'
    ]
  }
}

const comparisonTable = [
  { feature: 'Physician Documentation', resident: true, attending: true, group: true },
  { feature: 'Notes Included', resident: '30/mo', attending: '120/mo', group: 'Unlimited' },
  { feature: 'Inbox & Lab Tracking', resident: 'Basic', attending: 'Full', group: 'Full + Priority' },
  { feature: 'Chart Preparation', resident: false, attending: true, group: true },
  { feature: 'Dedicated MD Scribe', resident: false, attending: true, group: true },
  { feature: 'Support Channels', resident: 'Email', attending: 'Email + Phone', group: '24/7 Priority' },
  { feature: 'Turnaround Time', resident: '24-48 hrs', attending: '12-24 hrs', group: 'Same day' },
  { feature: 'Multiple Providers', resident: false, attending: 'Add-on', group: true },
  { feature: 'EMR Integration', resident: 'Basic', attending: 'Advanced', group: 'Full Custom' }
]

const faqs = ref([
  {
    question: 'How does doc2doc.health differ from traditional scribes?',
    answer: 'Our scribes are all physicians or medical graduates with clinical experience, providing higher quality documentation with true medical understanding. We combine this expertise with AI efficiency for faster turnaround.',
    open: false
  },
  {
    question: 'What specialties do you support?',
    answer: 'We support all major specialties including Family Medicine, Internal Medicine, Pediatrics, Cardiology, Orthopedics, Neurology, and more. Each scribe is matched to your specialty for optimal documentation.',
    open: false
  },
  {
    question: 'Is there a long-term contract?',
    answer: 'No, all plans are month-to-month or annual with no long-term commitments. You can cancel anytime with 30 days notice.',
    open: false
  },
  {
    question: 'How does the free trial work?',
    answer: 'Our 14-day free trial gives you full access to the Attending plan features with up to 20 notes. No credit card required to start.',
    open: false
  },
  {
    question: 'Is doc2doc.health HIPAA compliant?',
    answer: 'Absolutely. We maintain strict HIPAA compliance with encrypted data, BAAs, and secure workflows. All scribes undergo HIPAA training and background checks.',
    open: false
  },
  {
    question: 'What EMR systems do you integrate with?',
    answer: 'We work with all major EMRs including Epic, Cerner, Meditech, Athena, eClinicalWorks, and more. Our team will configure the optimal workflow for your system.',
    open: false
  }
])

const calculator = ref({
  patients: 20,
  hours: 2.5
})

const calculatedSavings = computed(() => {
  return {
    hoursSaved: (calculator.value.hours * 0.6).toFixed(1), // 60% time savings
    revenue: (calculator.value.patients * 0.1 * 150).toFixed(0) // 10% more patients at $150/visit
  }
})

const toggleFAQ = (index) => {
  faqs.value[index].open = !faqs.value[index].open
}

const navigateTo = (path) => {
  // Router navigation logic here
  console.log(`Navigating to: ${path}`)
}
</script>

<style scoped>
/* Custom animations */
.animate-float {
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
  100% {
    transform: translateY(0px);
  }
}
</style>