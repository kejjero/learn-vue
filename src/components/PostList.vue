<template>
  <ul class="posts">
    <li class="post" v-for="post in posts">
      <h2>{{ post.title }}</h2>
      <p>{{ post.description }}</p>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  }
}
</script>

<style>
.posts {
  list-style: none;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  width: 100%;
  height: 100%;
  margin-top: 15px;
}

.post {
  border: 2px solid #000;
  padding: 15px 10px;
  width: 100%;
}
</style>