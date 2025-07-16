<template>
  <div>
    <select v-model="filter" @change="filterTestimonials">
      <option value="all">All Specialties</option>
      <option value="Internal Medicine">Internal Medicine</option>
    </select>
    <TestimonialCard v-for="t in filteredTestimonials" :key="t.id" :testimonial="t" />
  </div>
</template>

<script setup>
// Client-side filtering (composable)
const { filteredTestimonials, filter, filterTestimonials } = useTestimonials();
</script>