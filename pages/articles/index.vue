<template>
    <div class="p-8">

    <UserFilterBox @filter-id="filterHandler"/>
      <ul class="p-articles">
        <li v-for="item in articles" :key="item.id" class="p-articles__item">
            <nuxt-link :to="'/single/' + item.id">{{item.title}}</nuxt-link>    
        </li>
      </ul>

    </div>
  </template>
  
  <script>
    import Vue from 'vue';
  import axios from 'axios';
  import UserFilterBox from '@/components/elements/UserFilterBox.vue';

  const END_POINT = 'https://jsonplaceholder.typicode.com/posts';
  
  export default Vue.extend({
    components: {
    UserFilterBox
    },
    data() {
      return {
        articles: null,
      }
    },
    methods: {
        async filterHandler(text) {
  console.log(`filterHandler: ${text}`);

  try {
    const res = await axios.get(END_POINT + `?userId=${text}`);
    console.log(res.data);
    this.articles = res.data;
  } catch (error) {
    console.log(`error: ${error}`);
  }
}
  },
    async created() {
      try {
        const res = await axios.get(END_POINT + '?_limit=20');
        console.log(res.data);
        this.articles = res.data;
      } catch (error) {
        console.log(`error: ${error}`);
      }    1    }
  })
  </script>
  
  <style scoped>
  .p-articles {
    list-style: none;
  }
  
  .p-articles__item {
    padding: 5px 16px;
    border: #ccc solid 1px;
    border-radius: 5px;
  }
  
  .p-articles__item + .p-articles__item {
    margin-top: 4px;
  }
  </style>