<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <p>{{ post.id }}</p>
      <p>{{ post.header }}</p>
      <p>{{ post.content }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      posts: [],
    };
  },
  async mounted() {
    let req = await axios.get("http://127.0.0.1:8000/api/posts");
    this.posts = req.data;
  },
};
</script>

<style scoped>
.my-text {
  color: brown;
}
</style>