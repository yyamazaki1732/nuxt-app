<template>
  <div class="p-8">
    <h2 class="p-article-title">{{article.title}}</h2>
    <ul class="p-article-info">
      <li>user id: {{article.userId}}</li>
      <li>post id: {{article.id}}</li>
    </ul>
    <div class="p-article-body">
      <p>{{article.body}}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

const END_POINT = 'https://jsonplaceholder.typicode.com/posts';

export default {
  data() {
    return {
      article: {
        title: null,
        userId: null,
        body: null
      },
    }
  },
  async created() {
    try {

      const res = await axios.get(END_POINT + `/${this.$route.params.id}`);
      console.log(res.data);
      this.article = res.data;
    } catch (error) {
      console.log(`error: ${error}`);
    }
  }
}
</script>


<style scoped>
.p-article-info {
  margin-top: 28px;
  margin-left: 30px;
}

.p-article-body {
  margin-top: 28px;
}
</style>