<template>
  <section class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header -->
      <div class="text-center mb-16">
        <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
          Simple, Transparent Pricing
        </h2>
        <p class="mt-4 max-w-2xl mx-auto text-xl text-gray-600">
          Choose the plan that fits your practice needs
        </p>
        
        <!-- Pricing Toggle -->
        <div class="mt-8 flex justify-center">
          <PricingToggle 
            v-model="billingCycle"
            class="bg-white shadow-sm"
          />
        </div>
        <p v-if="showAnnualSavings" class="mt-3 text-sm text-indigo-600 font-medium">
          Save 15% with annual billing
        </p>
      </div>

      <!-- Pricing Cards -->
      <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        <!-- Basic Plan -->
        <div class="relative bg-white rounded-2xl shadow-lg overflow-hidden border border-gray-200 hover:border-indigo-300 transition-all duration-300 transform hover:-translate-y-2">
          <div class="p-6">
            <h3 class="text-lg font-medium text-gray-900">Starter</h3>
            <p class="mt-2 text-gray-600">For individual physicians getting started</p>
            <div class="mt-8">
              <div class="flex items-baseline">
                <span class="text-4xl font-extrabold text-gray-900">${{ pricing.starter[billingCycle].price }}</span>
                <span class="ml-1 text-lg font-medium text-gray-500">/{{ billingCycle }}</span>
              </div>
              <p v-if="billingCycle === 'annual'" class="mt-1 text-sm text-gray-500">
                ${{ (pricing.starter[billingCycle].price / 12).toFixed(0) }} per month
              </p>
            </div>
            <ul class="mt-8 space-y-3">
              <li v-for="(feature, index) in pricing.starter.features" :key="index" class="flex">
                <CheckCircleIcon class="h-5 w-5 text-indigo-500 flex-shrink-0" />
                <span class="ml-3 text-gray-600">{{ feature }}</span>
              </li>
            </ul>
          </div>
          <div class="px-6 pb-8">
            <button 
              @click="navigateTo('/signup?plan=starter')"
              class="w-full px-4 py-3 border border-transparent text-base font-medium rounded-md text-white bg-gradient-to-r from-indigo-500 to-indigo-600 hover:from-indigo-600 hover:to-indigo-700 shadow-sm"
            >
              Get Started
            </button>
          </div>
          <div v-if="popularPlan !== 'starter'" class="absolute top-0 right-0 bg-indigo-500 text-white text-xs font-semibold px-3 py-1 rounded-bl-lg">
            Most Affordable
          </div>
        </div>

        <!-- Professional Plan (Popular) -->
        <div class="relative bg-white rounded-2xl shadow-xl overflow-hidden border-2 border-indigo-500 transform hover:-translate-y-2 transition-all duration-300 z-10">
          <div class="absolute top-0 left-0 right-0 h-2 bg-gradient-to-r from-indigo-500 to-purple-500"></div>
          <div class="p-6">
            <div class="flex justify-between items-start">
              <div>
                <h3 class="text-lg font-medium text-gray-900">Professional</h3>
                <p class="mt-2 text-gray-600">For busy practitioners needing full support</p>
              </div>
              <span class="inline-flex items-center px-3 py-1 rounded-full text-xs font-medium bg-indigo-100 text-indigo-800">
                Most Popular
              </span>
            </div>
            <div class="mt-8">
              <div class="flex items-baseline">
                <span class="text-4xl font-extrabold text-gray-900">${{ pricing.professional[billingCycle].price }}</span>
                <span class="ml-1 text-lg font-medium text-gray-500">/{{ billingCycle }}</span>
              </div>
              <p v-if="billingCycle === 'annual'" class="mt-1 text-sm text-gray-500">
                ${{ (pricing.professional[billingCycle].price / 12).toFixed(0) }} per month
              </p>
            </div>
            <ul class="mt-8 space-y-3">
              <li v-for="(feature, index) in pricing.professional.features" :key="index" class="flex">
                <CheckCircleIcon class="h-5 w-5 text-indigo-500 flex-shrink-0" />
                <span class="ml-3 text-gray-600">{{ feature }}</span>
              </li>
            </ul>
          </div>
          <div class="px-6 pb-8">
            <button 
              @click="navigateTo('/signup?plan=professional')"
              class="w-full px-4 py-3 border border-transparent text-base font-medium rounded-md text-white bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 shadow-sm"
            >
              Start Free Trial
            </button>
          </div>
        </div>

        <!-- Enterprise Plan -->
        <div class="relative bg-white rounded-2xl shadow-lg overflow-hidden border border-gray-200 hover:border-indigo-300 transition-all duration-300 transform hover:-translate-y-2">
          <div class="p-6">
            <h3 class="text-lg font-medium text-gray-900">Enterprise</h3>
            <p class="mt-2 text-gray-600">For clinics and large practices</p>
            <div class="mt-8">
              <div class="flex items-baseline">
                <span class="text-4xl font-extrabold text-gray-900">${{ pricing.enterprise[billingCycle].price }}</span>
                <span class="ml-1 text-lg font-medium text-gray-500">/{{ billingCycle }}</span>
              </div>
              <p v-if="billingCycle === 'annual'" class="mt-1 text-sm text-gray-500">
                ${{ (pricing.enterprise[billingCycle].price / 12).toFixed(0) }} per month
              </p>
            </div>
            <ul class="mt-8 space-y-3">
              <li v-for="(feature, index) in pricing.enterprise.features" :key="index" class="flex">
                <CheckCircleIcon class="h-5 w-5 text-indigo-500 flex-shrink-0" />
                <span class="ml-3 text-gray-600">{{ feature }}</span>
              </li>
            </ul>
          </div>
          <div class="px-6 pb-8">
            <button 
              @click="navigateTo('/contact')"
              class="w-full px-4 py-3 border border-transparent text-base font-medium rounded-md text-indigo-700 bg-indigo-100 hover:bg-indigo-200 shadow-sm"
            >
              Contact Sales
            </button>
          </div>
          <div v-if="pricing.enterprise.custom" class="absolute top-0 right-0 bg-purple-500 text-white text-xs font-semibold px-3 py-1 rounded-bl-lg">
            Custom Solutions
          </div>
        </div>
      </div>

      <!-- Comparison Table -->
      <div class="mt-16 max-w-4xl mx-auto bg-white shadow-lg rounded-xl overflow-hidden border border-gray-200">
        <div class="px-6 py-4 bg-gray-50 border-b border-gray-200">
          <h3 class="text-lg font-medium text-gray-900">Plan Comparison</h3>
        </div>
        <div class="divide-y divide-gray-200">
          <div v-for="(row, index) in comparisonTable" :key="index" class="grid grid-cols-4 gap-4 p-6 items-center">
            <div class="font-medium text-gray-900">{{ row.feature }}</div>
            <div class="text-center">
              <template v-if="row.starter === true">
                <CheckCircleIcon class="h-5 w-5 text-indigo-500 mx-auto" />
              </template>
              <template v-else-if="row.starter === false">
                <XCircleIcon class="h-5 w-5 text-gray-300 mx-auto" />
              </template>
              <template v-else>
                {{ row.starter }}
              </template>
            </div>
            <div class="text-center">
              <template v-if="row.professional === true">
                <CheckCircleIcon class="h-5 w-5 text-indigo-500 mx-auto" />
              </template>
              <template v-else-if="row.professional === false">
                <XCircleIcon class="h-5 w-5 text-gray-300 mx-auto" />
              </template>
              <template v-else>
                {{ row.professional }}
              </template>
            </div>
            <div class="text-center">
              <template v-if="row.enterprise === true">
                <CheckCircleIcon class="h-5 w-5 text-indigo-500 mx-auto" />
              </template>
              <template v-else-if="row.enterprise === false">
                <XCircleIcon class="h-5 w-5 text-gray-300 mx-auto" />
              </template>
              <template v-else>
                {{ row.enterprise }}
              </template>
            </div>
          </div>
        </div>
      </div>

      <!-- FAQ Section -->
      <div class="mt-20 max-w-3xl mx-auto">
        <h3 class="text-2xl font-bold text-center text-gray-900 mb-8">Frequently Asked Questions</h3>
        <div class="space-y-4">
          <div v-for="(faq, index) in faqs" :key="index" class="bg-white border border-gray-200 rounded-lg overflow-hidden">
            <button 
              @click="toggleFAQ(index)"
              class="w-full px-6 py-4 text-left focus:outline-none"
            >
              <div class="flex items-center justify-between">
                <span class="font-medium text-gray-900">{{ faq.question }}</span>
                <ChevronDownIcon 
                  class="h-5 w-5 text-gray-500 transition-transform duration-200"
                  :class="{ 'transform rotate-180': faq.open }"
                />
              </div>
            </button>
            <div v-show="faq.open" class="px-6 pb-4 text-gray-600">
              {{ faq.answer }}
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom CTA -->
      <div class="mt-20 text-center">
        <h3 class="text-xl font-medium text-gray-900">Need something custom?</h3>
        <p class="mt-2 text-gray-600">We can create a tailored solution for your practice</p>
        <div class="mt-6">
          <button 
            @click="navigateTo('/contact')"
            class="px-6 py-3 border border-transparent text-base font-medium rounded-md text-white bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 shadow-sm"
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
import { CheckCircleIcon, XCircleIcon, ChevronDownIcon } from '@heroicons/vue/24/outline'
import PricingToggle from '@/components/PricingToggle.vue'

const billingCycle = ref('monthly') // 'monthly' or 'annual'

const showAnnualSavings = computed(() => billingCycle.value === 'annual')

const popularPlan = ref('professional')

const pricing = {
  starter: {
    monthly: { price: 99 },
    annual: { price: 999 },
    features: [
      'Up to 20 notes/month',
      'AI-supported note editing',
      'Basic inbox management',
      'Email support',
      '1-2 day turnaround'
    ]
  },
  professional: {
    monthly: { price: 299 },
    annual: { price: 2999 },
    features: [
      'Up to 100 notes/month',
      'Priority AI-supported editing',
      'Full inbox & lab tracking',
      'Chart preparation',
      'Phone & email support',
      '12-24 hour turnaround',
      'Dedicated MD scribe'
    ]
  },
  enterprise: {
    monthly: { price: 'Custom' },
    annual: { price: 'Custom' },
    features: [
      'Unlimited notes',
      'All Professional features',
      'Multiple provider support',
      'Custom workflows',
      '24/7 priority support',
      'Same-day turnaround',
      'Dedicated account manager'
    ],
    custom: true
  }
}

const comparisonTable = [
  { feature: 'AI-Supported Note Editing', starter: true, professional: true, enterprise: true },
  { feature: 'Inbox & Lab Tracking', starter: 'Basic', professional: 'Full', enterprise: 'Full + Priority' },
  { feature: 'Chart Preparation', starter: false, professional: true, enterprise: true },
  { feature: 'Dedicated MD Scribe', starter: false, professional: true, enterprise: true },
  { feature: 'Support Channels', starter: 'Email', professional: 'Email + Phone', enterprise: '24/7 Priority' },
  { feature: 'Turnaround Time', starter: '1-2 days', professional: '12-24 hours', enterprise: 'Same day' },
  { feature: 'Monthly Notes Included', starter: '20', professional: '100', enterprise: 'Unlimited' },
  { feature: 'Multiple Providers', starter: false, professional: 'Add-on', enterprise: true }
]

const faqs = ref([
  {
    question: 'What happens if I exceed my monthly note limit?',
    answer: 'We\'ll automatically charge $5 per additional note for Starter plans and $3 per additional note for Professional plans. Enterprise plans have no limits.',
    open: false
  },
  {
    question: 'Can I switch between monthly and annual billing?',
    answer: 'Yes, you can change your billing cycle at any time from your account settings. Changes will take effect at your next billing date.',
    open: false
  },
  {
    question: 'Is there a contract or long-term commitment?',
    answer: 'No, all plans are month-to-month or annual with no long-term contracts. You can cancel anytime.',
    open: false
  },
  {
    question: 'How does the free trial work?',
    answer: 'The 14-day free trial gives you full access to the Professional plan features. No credit card required to start.',
    open: false
  },
  {
    question: 'Is Welkesa HIPAA compliant?',
    answer: 'Absolutely. We maintain strict HIPAA compliance with encrypted data, BAAs, and secure workflows to protect patient information.',
    open: false
  }
])

const toggleFAQ = (index) => {
  faqs.value[index].open = !faqs.value[index].open
}
</script>

<style scoped>
/* Add any custom styles here if needed */
</style>