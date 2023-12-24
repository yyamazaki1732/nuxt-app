<template>
    <div class="l-root-container">
      <TheHeader />
      <div class=" bg-green-300">
        <nuxt />
      </div>
      <TheFooter />
    </div>
  </template>
  
  <script>
  import Vue from 'vue'
  import TheHeader from '@/components/elements/TheHeader.vue';
  import TheFooter from '@/components/elements/TheFooter.vue';
  export default Vue.extend({
    components: {
      TheHeader,
      TheFooter
    }
  }) 
  </script>