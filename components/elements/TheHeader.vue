<template>
    <header class="flex justify-between items-center bg-yellow-300 p-8">
        <h1 class="text-4xl">Header</h1>
        <nav class="l-nav">
          <ul class="flex gap-x-4">
            <li ><nuxt-link to="/">top</nuxt-link></li>
            <li ><nuxt-link to="/articles/">articles</nuxt-link></li>
          </ul>
        </nav>
    </header>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  
})
</script>