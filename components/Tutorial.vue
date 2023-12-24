<!-- Please remove this file from your project -->
<template>
      <div id="app" class="bg-blue-400 p-12">
        <NuxtLink to="/about">About page</NuxtLink>
        <h1 class="title">
          アプリ名
        </h1>
        <input type="text">
        <form>
          <button v-on:click="addItem">add</button>
        </form>
        <h2 class="subtitle">
          アプリ名
        </h2>
        NuxtLink
      </div>
</template>

<script>
export default {
  name: 'NuxtTutorial',
}
</script>
